# System.Printing.PrintSystemUNCPathResolver::ValidateAndCaptureServerName

- ea: `0x197d0`
- end: `0x198b0`
- name: `System.Printing.PrintSystemUNCPathResolver::ValidateAndCaptureServerName`
- size: `224`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0xac40`
- `0x14ad0`
- `0x197d0`

## string_xrefs

- `0x197ec`: `PrintSystemUNCPathResolver.Attribute`
- `0x19885`: `PrintSystemUNCPathResolver.Server`

## pseudocode

```c

```

## disassembly

```asm
0x197d0  ldarg.0
0x197d1  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x197d6  ldtoken  System.Printing.IndexedProperties.PrintStringProperty
0x197db  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x197e0  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x197e5  brfalse.s loc_1980B
0x197e7  newobj   instance void System.Printing.InternalExceptionResourceManager::.ctor()
0x197ec  ldstr    aPrintsystemunc_0// "PrintSystemUNCPathResolver.Attribute"
0x197f1  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x197f6  call     instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentUICulture()
0x197fb  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x19800  ldstr    aAttributevalue// "attributeValue"
0x19805  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1980a  throw
0x1980b  ldarg.0
0x1980c  castclass System.Printing.IndexedProperties.PrintStringProperty
0x19811  callvirt instance object System.Printing.IndexedProperties.PrintStringProperty::get_Value()
0x19816  castclass [mscorlib]System.String
0x1981b  stloc.1
0x1981c  ldloc.1
0x1981d  brfalse.s loc_19879
0x1981f  ldloc.1
0x19820  call     instance int32 [mscorlib]System.String::get_Length()
0x19825  ldc.i4   0x101
0x1982a  clt
0x1982c  conv.u1
0x1982d  stloc.0
0x1982e  ldloc.1
0x1982f  call     instance int32 [mscorlib]System.String::get_Length()
0x19834  ldc.i4.1
0x19835  bge.s    loc_1983A
0x19837  ldc.i4.0
0x19838  br.s     loc_1983B
0x1983a  ldc.i4.1
0x1983b  stloc.s  4
0x1983d  ldloc.0
0x1983e  ldloc.s  4
0x19840  conv.u1
0x19841  and
0x19842  stloc.0
0x19843  ldloc.1
0x19844  ldc.i4.s 0x2C
0x19846  call     instance int32 [mscorlib]System.String::IndexOf(char)
0x1984b  ldc.i4.0
0x1984c  clt
0x1984e  stloc.3
0x1984f  ldloc.0
0x19850  ldloc.3
0x19851  conv.u1
0x19852  and
0x19853  stloc.0
0x19854  ldloc.0
0x19855  brfalse.s loc_19880
0x19857  ldloc.1
0x19858  ldstr    asc_2537E// "\\\\"
0x1985d  ldc.i4.4
0x1985e  call     instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x19863  brfalse.s loc_1987D
0x19865  ldloc.1
0x19866  ldc.i4.s 0x5C
0x19868  ldc.i4.3
0x19869  call     instance int32 [mscorlib]System.String::IndexOf(char, int32)
0x1986e  ldc.i4.0
0x1986f  clt
0x19871  stloc.2
0x19872  ldloc.0
0x19873  ldloc.2
0x19874  conv.u1
0x19875  and
0x19876  stloc.0
0x19877  br.s     loc_1987D
0x19879  ldc.i4.1
0x1987a  stloc.0
0x1987b  br.s     loc_198A4
0x1987d  ldloc.0
0x1987e  brtrue.s loc_198A4
0x19880  newobj   instance void System.Printing.InternalExceptionResourceManager::.ctor()
0x19885  ldstr    aPrintsystemunc_1// "PrintSystemUNCPathResolver.Server"
0x1988a  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1988f  call     instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentUICulture()
0x19894  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x19899  ldstr    aAttributevalue// "attributeValue"
0x1989e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x198a3  throw
0x198a4  ldarg.1
0x198a5  brfalse.s loc_198AE
0x198a7  ldarg.1
0x198a8  ldloc.1
0x198a9  stfld    string System.Printing.PrintSystemUNCPathResolver::serverName
0x198ae  ldloc.0
0x198af  ret
```
