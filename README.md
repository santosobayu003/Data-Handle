# Data-Handle
Model data handle menggunakan framework Laravel 8.x

```php
<?php

namespace App\Models;

use Illuminate\Database\Eloquent\Model;
use Illuminate\Support\Facades\DB;

class My_model extends Model
{
    public function create_data($table, $data)
    {
        return DB::table($table)->insert($data);
    }

    public function read_data($table)
    {
        return DB::table($table)->get();
    }

    public function update_data($table, $where, $id,  $data)
    {
        return DB::table($table)->where($where, $id)->update($data);
    }

    public function delete_data($table, $where, $id)
    {
        return DB::table($table)->where($where, $id)->delete();
    }

    public function select_where_id($table, $where, $id)
    {
        return DB::table($table)->where($where, $id)->first();
    }

    public function specific_where($table, $where, $where_value, $and_where, $and_where_value)
    {
        return DB::table($table)
            ->where($where, $where_value)
            ->where($and_where, $and_where_value)
            ->get();
    }
}
```
