# System.Printing.PrintSystemUNCPathResolver::ValidateUNCPath

- ea: `0x19760`
- end: `0x197c4`
- name: `System.Printing.PrintSystemUNCPathResolver::ValidateUNCPath`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0xe650`
- `0x13c20`

## callees

- `0x19760`

## pseudocode

```c

```

## disassembly

```asm
0x19760  ldc.i4.0
0x19761  stloc.0
0x19762  ldarg.0
0x19763  brfalse.s loc_197C2
0x19765  ldarg.0
0x19766  call     instance int32 [mscorlib]System.String::get_Length()
0x1976b  ldc.i4   0x204
0x19770  bge.s    loc_197C2
0x19772  ldarg.0
0x19773  call     instance int32 [mscorlib]System.String::get_Length()
0x19778  ldc.i4.1
0x19779  blt.s    loc_197C2
0x1977b  ldarg.0
0x1977c  ldc.i4.s 0x2C
0x1977e  call     instance int32 [mscorlib]System.String::IndexOf(char)
0x19783  ldc.i4.0
0x19784  bge.s    loc_197C2
0x19786  ldarg.0
0x19787  ldstr    asc_2537E// "\\\\"
0x1978c  ldc.i4.4
0x1978d  call     instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x19792  brfalse.s loc_197C2
0x19794  ldarg.0
0x19795  ldstr    asc_255B8// "\\\\\\"
0x1979a  ldc.i4.4
0x1979b  call     instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x197a0  brtrue.s loc_197C2
0x197a2  ldarg.0
0x197a3  ldc.i4.s 0x5C
0x197a5  ldc.i4.3
0x197a6  call     instance int32 [mscorlib]System.String::IndexOf(char, int32)
0x197ab  ldc.i4.0
0x197ac  blt.s    loc_197C2
0x197ae  ldarg.0
0x197af  ldstr    aHttp// "\\\\http://"
0x197b4  ldc.i4.5
0x197b5  call     instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x197ba  ldc.i4.0
0x197bb  beq.s    loc_197C0
0x197bd  ldloc.0
0x197be  br.s     loc_197C1
0x197c0  ldc.i4.1
0x197c1  stloc.0
0x197c2  ldloc.0
0x197c3  ret
```
