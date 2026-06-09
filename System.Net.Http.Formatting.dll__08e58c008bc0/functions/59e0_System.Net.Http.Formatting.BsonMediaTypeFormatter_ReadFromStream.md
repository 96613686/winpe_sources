# System.Net.Http.Formatting.BsonMediaTypeFormatter::ReadFromStream

- ea: `0x59e0`
- end: `0x5b2d`
- name: `System.Net.Http.Formatting.BsonMediaTypeFormatter::ReadFromStream`
- size: `333`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x35d0`
- `0x35f0`
- `0x5680`
- `0x59e0`
- `0x5c90`
- `0xb3c0`
- `0xb4b0`

## string_xrefs

- `0x59f7`: `readStream`

## pseudocode

```c

```

## disassembly

```asm
0x59e0  ldarg.1
0x59e1  ldnull
0x59e2  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x59e7  brfalse.s loc_59F4
0x59e9  ldstr    aType// "type"
0x59ee  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x59f3  throw
0x59f4  ldarg.2
0x59f5  brtrue.s loc_5A02
0x59f7  ldstr    aReadstream// "readStream"
0x59fc  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x5a01  throw
0x5a02  ldarg.3
0x5a03  brtrue.s loc_5A10
0x5a05  ldstr    aEffectiveencod// "effectiveEncoding"
0x5a0a  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x5a0f  throw
0x5a10  ldarg.1
0x5a11  call     bool System.Net.Http.Formatting.BsonMediaTypeFormatter::IsSimpleType(class [mscorlib]System.Type type)
0x5a16  brtrue.s loc_5A2D
0x5a18  ldarg.1
0x5a19  ldtoken  unsigned int8[]
0x5a1e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5a23  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x5a28  brfalse  loc_5B1E
0x5a2d  ldsfld   class [mscorlib]System.Type System.Net.Http.Formatting.BsonMediaTypeFormatter::OpenDictionaryType
0x5a32  ldc.i4.2
0x5a33  newarr   [mscorlib]System.Type
0x5a38  dup
0x5a39  ldc.i4.0
0x5a3a  ldtoken  [mscorlib]System.String
0x5a3f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5a44  stelem.ref
0x5a45  dup
0x5a46  ldc.i4.1
0x5a47  ldarg.1
0x5a48  stelem.ref
0x5a49  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::MakeGenericType(class [mscorlib]System.Type[])
0x5a4e  stloc.0
0x5a4f  ldarg.0
0x5a50  ldloc.0
0x5a51  ldarg.2
0x5a52  ldarg.3
0x5a53  ldarg.s  4
0x5a55  call     instance object System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::ReadFromStream(class [mscorlib]System.Type type, class [mscorlib]System.IO.Stream readStream, class [mscorlib]System.Text.Encoding effectiveEncoding, class System.Net.Http.Formatting.IFormatterLogger formatterLogger)
0x5a5a  isinst   [mscorlib]System.Collections.IDictionary
0x5a5f  stloc.1
0x5a60  ldloc.1
0x5a61  brtrue.s loc_5A7D
0x5a63  call     string System.Net.Http.Properties.Resources::get_MediaTypeFormatter_BsonParseError_MissingData()
0x5a68  ldc.i4.1
0x5a69  newarr   [mscorlib]System.Object
0x5a6e  dup
0x5a6f  ldc.i4.0
0x5a70  ldloc.0
0x5a71  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x5a76  stelem.ref
0x5a77  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(string messageFormat, object[] messageArgs)
0x5a7c  throw
0x5a7d  ldsfld   string [mscorlib]System.String::Empty
0x5a82  stloc.2
0x5a83  ldloc.1
0x5a84  callvirt instance class [mscorlib]System.Collections.IDictionaryEnumerator [mscorlib]System.Collections.IDictionary::GetEnumerator()
0x5a89  stloc.3
0x5a8a  br.s     loc_5ADD
0x5a8c  ldloc.3
0x5a8d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5a92  unbox.any [mscorlib]System.Collections.DictionaryEntry
0x5a97  stloc.s  4
0x5a99  ldloc.1
0x5a9a  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x5a9f  ldc.i4.1
0x5aa0  bne.un.s loc_5AC5
0x5aa2  ldloca.s 4
0x5aa4  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Key()
0x5aa9  isinst   [mscorlib]System.String
0x5aae  ldstr    aValue_0// "Value"
0x5ab3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5ab8  brfalse.s loc_5AC5
0x5aba  ldloca.s 4
0x5abc  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Value()
0x5ac1  stloc.s  5
0x5ac3  leave.s  loc_5B2A
0x5ac5  ldloca.s 4
0x5ac7  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Key()
0x5acc  brfalse.s loc_5AE5
0x5ace  ldloca.s 4
0x5ad0  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Key()
0x5ad5  callvirt instance string [mscorlib]System.Object::ToString()
0x5ada  stloc.2
0x5adb  leave.s  loc_5AFB
0x5add  ldloc.3
0x5ade  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5ae3  brtrue.s loc_5A8C
0x5ae5  leave.s  loc_5AFB
0x5ae7  ldloc.3
0x5ae8  isinst   [mscorlib]System.IDisposable
0x5aed  stloc.s  6
0x5aef  ldloc.s  6
0x5af1  brfalse.s loc_5AFA
0x5af3  ldloc.s  6
0x5af5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5afa  endfinally
0x5afb  call     string System.Net.Http.Properties.Resources::get_MediaTypeFormatter_BsonParseError_UnexpectedData()
0x5b00  ldc.i4.2
0x5b01  newarr   [mscorlib]System.Object
0x5b06  dup
0x5b07  ldc.i4.0
0x5b08  ldloc.1
0x5b09  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x5b0e  box      [mscorlib]System.Int32
0x5b13  stelem.ref
0x5b14  dup
0x5b15  ldc.i4.1
0x5b16  ldloc.2
0x5b17  stelem.ref
0x5b18  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(string messageFormat, object[] messageArgs)
0x5b1d  throw
0x5b1e  ldarg.0
0x5b1f  ldarg.1
0x5b20  ldarg.2
0x5b21  ldarg.3
0x5b22  ldarg.s  4
0x5b24  call     instance object System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::ReadFromStream(class [mscorlib]System.Type type, class [mscorlib]System.IO.Stream readStream, class [mscorlib]System.Text.Encoding effectiveEncoding, class System.Net.Http.Formatting.IFormatterLogger formatterLogger)
0x5b29  ret
0x5b2a  ldloc.s  5
0x5b2c  ret
```
