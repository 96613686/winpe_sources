# System.Printing.PrintSystemUNCPathResolver::ValidateUNCName

- ea: `0x19980`
- end: `0x199f2`
- name: `System.Printing.PrintSystemUNCPathResolver::ValidateUNCName`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x19a00`

## callees

- `0xac40`
- `0x19980`

## string_xrefs

- `0x199d1`: `PrintSystemUNCPathResolver.UNC`

## pseudocode

```c

```

## disassembly

```asm
0x19980  ldarg.0
0x19981  brfalse.s loc_199CC
0x19983  ldarg.0
0x19984  call     instance int32 [mscorlib]System.String::get_Length()
0x19989  ldc.i4   0x204
0x1998e  bge.s    loc_199CC
0x19990  ldarg.0
0x19991  call     instance int32 [mscorlib]System.String::get_Length()
0x19996  ldc.i4.1
0x19997  blt.s    loc_199CC
0x19999  ldarg.0
0x1999a  ldc.i4.s 0x2C
0x1999c  call     instance int32 [mscorlib]System.String::IndexOf(char)
0x199a1  ldc.i4.0
0x199a2  bge.s    loc_199CC
0x199a4  ldarg.0
0x199a5  ldstr    asc_2537E// "\\\\"
0x199aa  ldc.i4.4
0x199ab  call     instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x199b0  brfalse.s loc_199CC
0x199b2  ldarg.0
0x199b3  ldstr    asc_255B8// "\\\\\\"
0x199b8  ldc.i4.4
0x199b9  call     instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x199be  brtrue.s loc_199CC
0x199c0  ldarg.0
0x199c1  ldc.i4.s 0x5C
0x199c3  ldc.i4.3
0x199c4  call     instance int32 [mscorlib]System.String::IndexOf(char, int32)
0x199c9  ldc.i4.0
0x199ca  bge.s    loc_199F0
0x199cc  newobj   instance void System.Printing.InternalExceptionResourceManager::.ctor()
0x199d1  ldstr    aPrintsystemunc_3// "PrintSystemUNCPathResolver.UNC"
0x199d6  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x199db  call     instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentUICulture()
0x199e0  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x199e5  ldstr    aName_0// "name"
0x199ea  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x199ef  throw
0x199f0  ldc.i4.1
0x199f1  ret
```
