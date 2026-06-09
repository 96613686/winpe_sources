# System.Printing.PrintSystemUNCPathResolver::ValidateCollectionAndCaptureParameters

- ea: `0x19ab0`
- end: `0x19b52`
- name: `System.Printing.PrintSystemUNCPathResolver::ValidateCollectionAndCaptureParameters`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x196d0`

## callees

- `0xac40`
- `0x19ab0`
- `0x19bb0`

## string_xrefs

- `0x19b32`: `PrintSystemUNCPathResolver.Entries`

## pseudocode

```c

```

## disassembly

```asm
0x19ab0  ldc.i4.1
0x19ab1  stloc.1
0x19ab2  ldarg.1
0x19ab3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x19ab8  brfalse  loc_19B51
0x19abd  ldloc.1
0x19abe  brfalse.s loc_19B2D
0x19ac0  ldarg.1
0x19ac1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x19ac6  castclass [mscorlib]System.Collections.DictionaryEntry
0x19acb  stloc.0
0x19acc  ldloc.0
0x19acd  unbox    [mscorlib]System.Collections.DictionaryEntry
0x19ad2  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Key()
0x19ad7  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x19adc  ldtoken  [mscorlib]System.String
0x19ae1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ae6  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x19aeb  brfalse.s loc_19B20
0x19aed  ldsfld   class [mscorlib]System.Collections.Hashtable System.Printing.PrintSystemUNCPathResolver::parametersMapping
0x19af2  ldloc.0
0x19af3  unbox    [mscorlib]System.Collections.DictionaryEntry
0x19af8  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Key()
0x19afd  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x19b02  castclass ValidateAndCaptureStringParameter
0x19b07  stloc.2
0x19b08  ldloc.2
0x19b09  brfalse.s loc_19B20
0x19b0b  ldloc.2
0x19b0c  ldloc.0
0x19b0d  unbox    [mscorlib]System.Collections.DictionaryEntry
0x19b12  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Value()
0x19b17  ldarg.0
0x19b18  callvirt instance bool ValidateAndCaptureStringParameter::Invoke([hasfieldmarshal] object value, class System.Printing.PrintSystemUNCPathResolver parameter)
0x19b1d  pop
0x19b1e  br.s     loc_19B22
0x19b20  ldc.i4.0
0x19b21  stloc.1
0x19b22  ldarg.1
0x19b23  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x19b28  brtrue.s loc_19ABD
0x19b2a  ldloc.1
0x19b2b  brtrue.s loc_19B51
0x19b2d  newobj   instance void System.Printing.InternalExceptionResourceManager::.ctor()
0x19b32  ldstr    aPrintsystemunc// "PrintSystemUNCPathResolver.Entries"
0x19b37  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x19b3c  call     instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentUICulture()
0x19b41  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x19b46  ldstr    aEnumerator// "enumerator"
0x19b4b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x19b50  throw
0x19b51  ret
```
