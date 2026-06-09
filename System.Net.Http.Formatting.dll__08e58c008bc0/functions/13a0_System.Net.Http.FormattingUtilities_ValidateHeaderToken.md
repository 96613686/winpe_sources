# System.Net.Http.FormattingUtilities::ValidateHeaderToken

- ea: `0x13a0`
- end: `0x13dc`
- name: `System.Net.Http.FormattingUtilities::ValidateHeaderToken`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x4200`

## callees

- `0x13a0`

## pseudocode

```c

```

## disassembly

```asm
0x13a0  ldarg.0
0x13a1  brtrue.s loc_13A5
0x13a3  ldc.i4.0
0x13a4  ret
0x13a5  ldarg.0
0x13a6  stloc.0
0x13a7  ldc.i4.0
0x13a8  stloc.1
0x13a9  br.s     loc_13D1
0x13ab  ldloc.0
0x13ac  ldloc.1
0x13ad  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x13b2  stloc.2
0x13b3  ldloc.2
0x13b4  ldc.i4.s 0x21
0x13b6  blt.s    loc_13CB
0x13b8  ldloc.2
0x13b9  ldc.i4.s 0x7E
0x13bb  bgt.s    loc_13CB
0x13bd  ldstr    asc_F26C// "()<>@,;:\\\"/[]?={}"
0x13c2  ldloc.2
0x13c3  call     instance int32 [mscorlib]System.String::IndexOf(char)
0x13c8  ldc.i4.m1
0x13c9  beq.s    loc_13CD
0x13cb  ldc.i4.0
0x13cc  ret
0x13cd  ldloc.1
0x13ce  ldc.i4.1
0x13cf  add
0x13d0  stloc.1
0x13d1  ldloc.1
0x13d2  ldloc.0
0x13d3  callvirt instance int32 [mscorlib]System.String::get_Length()
0x13d8  blt.s    loc_13AB
0x13da  ldc.i4.1
0x13db  ret
```
