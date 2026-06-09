# System.Net.Http.Formatting.FormUrlEncodedJson::ParseInternal

- ea: `0x6140`
- end: `0x621d`
- name: `System.Net.Http.Formatting.FormUrlEncodedJson::ParseInternal`
- size: `221`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x60e0`
- `0x60f0`
- `0x6100`
- `0x6120`

## callees

- `0x37f0`
- `0x6140`
- `0x6220`
- `0x6360`
- `0x6660`
- `0xb330`
- `0xb3c0`
- `0xb410`

## pseudocode

```c

```

## disassembly

```asm
0x6140  ldarg.0
0x6141  brtrue.s loc_614E
0x6143  ldstr    aNamevaluepairs// "nameValuePairs"
0x6148  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x614d  throw
0x614e  ldarg.1
0x614f  ldc.i4.0
0x6150  bgt.s    loc_6169
0x6152  ldstr    aMaxdepth// "maxDepth"
0x6157  ldarg.1
0x6158  box      [mscorlib]System.Int32
0x615d  ldc.i4.1
0x615e  box      [mscorlib]System.Int32
0x6163  call     class [mscorlib]System.ArgumentOutOfRangeException System.Web.Http.Error::ArgumentMustBeGreaterThanOrEqualTo(string parameterName, object actualValue, object minValue)
0x6168  throw
0x6169  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::.ctor()
0x616e  stloc.0
0x616f  ldarg.0
0x6170  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::GetEnumerator()
0x6175  stloc.1
0x6176  br       loc_61FB
0x617b  ldloc.1
0x617c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Current()
0x6181  stloc.2
0x6182  ldloca.s 2
0x6184  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x6189  stloc.3
0x618a  ldloca.s 2
0x618c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x6191  stloc.s  4
0x6193  ldloc.3
0x6194  brtrue.s loc_61DB
0x6196  ldloc.s  4
0x6198  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x619d  brfalse.s loc_61BD
0x619f  ldarg.2
0x61a0  brfalse.s loc_61B8
0x61a2  ldstr    aNamevaluepairs// "nameValuePairs"
0x61a7  call     string System.Net.Http.Properties.Resources::get_QueryStringNameShouldNotNull()
0x61ac  ldc.i4.0
0x61ad  newarr   [mscorlib]System.Object
0x61b2  call     class [mscorlib]System.ArgumentException System.Web.Http.Error::Argument(string parameterName, string messageFormat, object[] messageArgs)
0x61b7  throw
0x61b8  ldnull
0x61b9  stloc.s  6
0x61bb  leave.s  loc_621A
0x61bd  ldc.i4.1
0x61be  newarr   [mscorlib]System.String
0x61c3  dup
0x61c4  ldc.i4.0
0x61c5  ldloc.s  4
0x61c7  stelem.ref
0x61c8  stloc.s  5
0x61ca  ldloc.0
0x61cb  ldloc.s  5
0x61cd  ldnull
0x61ce  ldarg.2
0x61cf  call     bool System.Net.Http.Formatting.FormUrlEncodedJson::Insert(class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject root, string[] path, string value, bool throwOnError)
0x61d4  brtrue.s loc_61FB
0x61d6  ldnull
0x61d7  stloc.s  6
0x61d9  leave.s  loc_621A
0x61db  ldloc.3
0x61dc  ldarg.1
0x61dd  ldarg.2
0x61de  call     string[] System.Net.Http.Formatting.FormUrlEncodedJson::GetPath(string key, int32 maxDepth, bool throwOnError)
0x61e3  stloc.s  7
0x61e5  ldloc.s  7
0x61e7  brfalse.s loc_61F6
0x61e9  ldloc.0
0x61ea  ldloc.s  7
0x61ec  ldloc.s  4
0x61ee  ldarg.2
0x61ef  call     bool System.Net.Http.Formatting.FormUrlEncodedJson::Insert(class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject root, string[] path, string value, bool throwOnError)
0x61f4  brtrue.s loc_61FB
0x61f6  ldnull
0x61f7  stloc.s  6
0x61f9  leave.s  loc_621A
0x61fb  ldloc.1
0x61fc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6201  brtrue   loc_617B
0x6206  leave.s  loc_6212
0x6208  ldloc.1
0x6209  brfalse.s loc_6211
0x620b  ldloc.1
0x620c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6211  endfinally
0x6212  ldloc.0
0x6213  call     void System.Net.Http.Formatting.FormUrlEncodedJson::FixContiguousArrays(class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken jv)
0x6218  ldloc.0
0x6219  ret
0x621a  ldloc.s  6
0x621c  ret
```
