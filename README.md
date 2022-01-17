# Schwesig's World


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Organization Chart Plugin</title>
  <link rel="icon" href="img/logo.png">
  <link rel="stylesheet" href="css/jquery.orgchart.css">
  <link rel="stylesheet" href="css/style.css">
</head>
<body>
  <div id="chart-container"></div>

  <script type="text/javascript" src="js/jquery.min.js"></script>
  <script type="text/javascript" src="js/jquery.mockjax.min.js"></script>
  <script type="text/javascript" src="js/jquery.orgchart.js"></script>
  <script type="text/javascript">
    $(function() {
    
      $.mockjax({
        url: '/orgchart/initdata',
        responseTime: 1000,
        contentType: 'application/json',
        responseText: {
          'name': 'Lao Lao',
          'title': 'general manager',
          'children': [
            { 'name': 'Bo Miao', 'title': 'department manager' },
            { 'name': 'Su Miao', 'title': 'department manager',
              'children': [
                { 'name': 'Tie Hua', 'title': 'senior engineer' },
                { 'name': 'Hei Hei', 'title': 'senior engineer',
                  'children': [
                    { 'name': 'Pang Pang', 'title': 'engineer' },
                    { 'name': 'Xiang Xiang', 'title': 'UE engineer' }
                  ]
                }
              ]
            },
            { 'name': 'Yu Jie', 'title': 'department manager' },
            { 'name': 'Yu Li', 'title': 'department manager' },
            { 'name': 'Hong Miao', 'title': 'department manager' },
            { 'name': 'Yu Wei', 'title': 'department manager' },
            { 'name': 'Chun Miao', 'title': 'department manager' },
            { 'name': 'Yu Tie', 'title': 'department manager' }
          ]
        }
      });

      $('#chart-container').orgchart({
        'data' : '/orgchart/initdata',
        'nodeContent': 'title'
      });

    });
  </script>
  </body>
</html>
