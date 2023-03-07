// Подключение к базе данных
$host = 'localhost';
$user = 'root';
$password = '';
$dbname = 'blog';
$dsn = "mysql:host=$host;dbname=$dbname";
$pdo = new PDO($dsn, $user, $password);

// Создание таблицы "posts"
$sql = "CREATE TABLE posts (
        id INT(11) AUTO_INCREMENT PRIMARY KEY,
        title VARCHAR(255) NOT NULL,
        content TEXT NOT NULL,
        photo VARCHAR(255),
        created_at DATETIME DEFAULT CURRENT_TIMESTAMP
        )";
$pdo->exec($sql);

// Создание таблицы "comments"
$sql = "CREATE TABLE comments (
        id INT(11) AUTO_INCREMENT PRIMARY KEY,
        post_id INT(11) NOT NULL,
        name VARCHAR(255) NOT NULL,
        content TEXT NOT NULL,
        created_at DATETIME DEFAULT CURRENT_TIMESTAMP
        )";
$pdo->exec($sql);
