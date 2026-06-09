# System.Printing.PrintSystemUNCPathResolver::ValidateAndCapturePrinterName

- ea: `0x198b0`
- end: `0x19978`
- name: `System.Printing.PrintSystemUNCPathResolver::ValidateAndCapturePrinterName`
- size: `200`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0xac40`
- `0x14ad0`
- `0x198b0`

## string_xrefs

- `0x198cc`: `PrintSystemUNCPathResolver.Attribute`
- `0x1994d`: `PrintSystemUNCPathResolver.Printer`

## pseudocode

```c

```

## disassembly

```asm
0x198b0  ldarg.0
0x198b1  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x198b6  ldtoken  System.Printing.IndexedProperties.PrintStringProperty
0x198bb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x198c0  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x198c5  brfalse.s loc_198EB
0x198c7  newobj   instance void System.Printing.InternalExceptionResourceManager::.ctor()
0x198cc  ldstr    aPrintsystemunc_0// "PrintSystemUNCPathResolver.Attribute"
0x198d1  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x198d6  call     instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentUICulture()
0x198db  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x198e0  ldstr    aAttributevalue// "attributeValue"
0x198e5  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x198ea  throw
0x198eb  ldarg.0
0x198ec  castclass System.Printing.IndexedProperties.PrintStringProperty
0x198f1  callvirt instance object System.Printing.IndexedProperties.PrintStringProperty::get_Value()
0x198f6  castclass [mscorlib]System.String
0x198fb  stloc.1
0x198fc  ldloc.1
0x198fd  brfalse.s loc_19948
0x198ff  ldloc.1
0x19900  call     instance int32 [mscorlib]System.String::get_Length()
0x19905  ldc.i4   0x101
0x1990a  clt
0x1990c  conv.u1
0x1990d  stloc.0
0x1990e  ldloc.1
0x1990f  call     instance int32 [mscorlib]System.String::get_Length()
0x19914  ldc.i4.1
0x19915  bge.s    loc_1991A
0x19917  ldc.i4.0
0x19918  br.s     loc_1991B
0x1991a  ldc.i4.1
0x1991b  stloc.s  4
0x1991d  ldloc.0
0x1991e  ldloc.s  4
0x19920  conv.u1
0x19921  and
0x19922  stloc.0
0x19923  ldloc.1
0x19924  ldc.i4.s 0x2C
0x19926  call     instance int32 [mscorlib]System.String::IndexOf(char)
0x1992b  ldc.i4.0
0x1992c  clt
0x1992e  stloc.3
0x1992f  ldloc.0
0x19930  ldloc.3
0x19931  conv.u1
0x19932  and
0x19933  stloc.0
0x19934  ldloc.1
0x19935  ldc.i4.s 0x5C
0x19937  call     instance int32 [mscorlib]System.String::IndexOf(char)
0x1993c  ldc.i4.0
0x1993d  clt
0x1993f  stloc.2
0x19940  ldloc.0
0x19941  ldloc.2
0x19942  conv.u1
0x19943  and
0x19944  stloc.0
0x19945  ldloc.0
0x19946  brtrue.s loc_1996C
0x19948  newobj   instance void System.Printing.InternalExceptionResourceManager::.ctor()
0x1994d  ldstr    aPrintsystemunc_2// "PrintSystemUNCPathResolver.Printer"
0x19952  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x19957  call     instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentUICulture()
0x1995c  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x19961  ldstr    aAttributevalue// "attributeValue"
0x19966  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1996b  throw
0x1996c  ldarg.1
0x1996d  brfalse.s loc_19976
0x1996f  ldarg.1
0x19970  ldloc.1
0x19971  stfld    string System.Printing.PrintSystemUNCPathResolver::printerName
0x19976  ldloc.0
0x19977  ret
```
