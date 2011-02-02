## Validation Class

### Basic usage

	require '/path/to/modules/witty/witty.php';
	Witty::init();

	$data = array(
		'username' => 'foo',
		'password' => '',
	);

	$validation = Witty::instance('Validation');
	$validation->data = $data;

	$validation
		->rule('username', 'not_empty')
		->rule('username', 'min_length', array(3))
		->rule('password', 'not_empty')
		;

	if(!$validation->check())
	{
		var_dump($validation->errors);
	}

### output

	array (
	  'username' => 
	  array (
		'field' => 'username',
		'value' => 3,
		'rule' => 'min_length',
	  ),
	  'password' => 
	  array (
		'field' => 'password',
		'value' => NULL,
		'rule' => 'not_empty',
	  ),
	)

