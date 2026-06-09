# System.Net.Http.Formatting.JsonMediaTypeFormatter::GetDataContractSerializer

- ea: `0x7ba0`
- end: `0x7c08`
- name: `System.Net.Http.Formatting.JsonMediaTypeFormatter::GetDataContractSerializer`
- size: `104`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x7980`
- `0x7a60`

## callees

- `0x39b0`
- `0x7ba0`
- `0xb4b0`
- `0xd660`

## pseudocode

```c

```

## disassembly

```asm
0x7ba0  newobj   instance void <>c__DisplayClass27_0::.ctor()
0x7ba5  stloc.0
0x7ba6  ldloc.0
0x7ba7  ldarg.0
0x7ba8  stfld    class System.Net.Http.Formatting.JsonMediaTypeFormatter <>c__DisplayClass27_0::<>4__this
0x7bad  ldloc.0
0x7bae  ldarg.1
0x7baf  stfld    class [mscorlib]System.Type <>c__DisplayClass27_0::type
0x7bb4  ldarg.0
0x7bb5  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer> System.Net.Http.Formatting.JsonMediaTypeFormatter::_dataContractSerializerCache
0x7bba  ldloc.0
0x7bbb  ldfld    class [mscorlib]System.Type <>c__DisplayClass27_0::type
0x7bc0  ldloc.0
0x7bc1  ldftn    instance class [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer <>c__DisplayClass27_0::<GetDataContractSerializer>b__0(class [mscorlib]System.Type t)
0x7bc7  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Type, class [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer>::.ctor(object, native int)
0x7bcc  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer>::GetOrAdd(void, var<u1>)
0x7bd1  stloc.1
0x7bd2  ldloc.1
0x7bd3  brtrue.s loc_7C06
0x7bd5  call     string System.Net.Http.Properties.Resources::get_SerializerCannotSerializeType()
0x7bda  ldc.i4.2
0x7bdb  newarr   [mscorlib]System.Object
0x7be0  dup
0x7be1  ldc.i4.0
0x7be2  ldtoken  [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer
0x7be7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7bec  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x7bf1  stelem.ref
0x7bf2  dup
0x7bf3  ldc.i4.1
0x7bf4  ldloc.0
0x7bf5  ldfld    class [mscorlib]System.Type <>c__DisplayClass27_0::type
0x7bfa  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x7bff  stelem.ref
0x7c00  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(string messageFormat, object[] messageArgs)
0x7c05  throw
0x7c06  ldloc.1
0x7c07  ret
```
