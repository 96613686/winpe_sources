# ::<CrtImplementationDetails>.LanguageSupport.IsDllNameCppSupportLike

- ea: `0x1830`
- end: `0x18af`
- name: `::<CrtImplementationDetails>.LanguageSupport.IsDllNameCppSupportLike`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18b0`

## callees

- `0x1830`

## pseudocode

```c

```

## disassembly

```asm
0x1830  ldarg.1
0x1831  ldarg.2
0x1832  ldc.i4.5
0x1833  call     instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x1838  brtrue.s loc_183C
0x183a  ldc.i4.0
0x183b  ret
0x183c  ldarg.1
0x183d  call     instance int32 [mscorlib]System.String::get_Length()
0x1842  stloc.1
0x1843  ldarg.2
0x1844  call     instance int32 [mscorlib]System.String::get_Length()
0x1849  stloc.2
0x184a  ldloc.2
0x184b  stloc.0
0x184c  ldloc.2
0x184d  ldloc.1
0x184e  bge.s    loc_18AD
0x1850  ldarg.1
0x1851  ldloc.0
0x1852  call     instance char [mscorlib]System.String::get_Chars(int32)
0x1857  ldc.i4.s 0x30
0x1859  blt.un.s loc_186E
0x185b  ldarg.1
0x185c  ldloc.0
0x185d  call     instance char [mscorlib]System.String::get_Chars(int32)
0x1862  ldc.i4.s 0x39
0x1864  bgt.un.s loc_186E
0x1866  ldloc.0
0x1867  ldc.i4.1
0x1868  add
0x1869  stloc.0
0x186a  ldloc.0
0x186b  ldloc.1
0x186c  blt.s    loc_1850
0x186e  ldloc.0
0x186f  ldloc.2
0x1870  beq.s    loc_18AD
0x1872  ldloc.0
0x1873  ldloc.1
0x1874  bge.s    loc_1890
0x1876  ldarg.1
0x1877  ldloc.0
0x1878  call     instance char [mscorlib]System.String::get_Chars(int32)
0x187d  ldc.i4.s 0x64
0x187f  beq.s    loc_188C
0x1881  ldarg.1
0x1882  ldloc.0
0x1883  call     instance char [mscorlib]System.String::get_Chars(int32)
0x1888  ldc.i4.s 0x44
0x188a  bne.un.s loc_1890
0x188c  ldloc.0
0x188d  ldc.i4.1
0x188e  add
0x188f  stloc.0
0x1890  ldloc.0
0x1891  ldc.i4.4
0x1892  add
0x1893  ldloc.1
0x1894  bne.un.s loc_18A8
0x1896  ldarg.1
0x1897  ldstr    aDll// ".dll"
0x189c  ldc.i4.5
0x189d  call     instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x18a2  brfalse.s loc_18A8
0x18a4  ldc.i4.1
0x18a5  stloc.3
0x18a6  br.s     loc_18AA
0x18a8  ldc.i4.0
0x18a9  stloc.3
0x18aa  ldloc.3
0x18ab  conv.u1
0x18ac  ret
0x18ad  ldc.i4.0
0x18ae  ret
```
