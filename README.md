
    public function conv($x, $v)
    {
        $f=0;
        foreach ($x as $val) {
            if ($f==0) {
                $d[$val]= $v;
                $f=1;
                $dval = $val;
                continue;
            }
            $d[$val] = $d;
            unset($d[$dval]);
            $dval = $val;
        }
        return $d;
    }

    public function impl3($ar)
    {
        $na=[];
        foreach ($ar as $key1 => $val1) {
            foreach ($val1 as $key2 => $val2) {
                foreach ($val2 as $key3 => $val3) {
                    $s=$key1.'.'.$key2.'.'.$key3;
                    $na[$s]=$val3;
                }
            }
        }
        return $na;
    }

    public function expl3($ar)
    {
        $newData = [];
        foreach ($ar as $key => $val) {
            $rm = explode('.', $key);
         //   $rm = array_reverse($rm);
            foreach ($rm as $val2) {
                $newData[$rm[0]][$rm[1]][$rm[2]] = $val;
            }
        }
        return $newData;
    }
