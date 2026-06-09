# System.Net.Http.UriExtensions::ParseQueryString

- ea: `0x2f50`
- end: `0x2f70`
- name: `System.Net.Http.UriExtensions::ParseQueryString`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x2f50`
- `0x5ef0`
- `0x5fd0`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x2f50  ldarg.0
0x2f51  ldnull
0x2f52  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x2f57  brfalse.s loc_2F64
0x2f59  ldstr    aAddress// "address"
0x2f5e  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x2f63  throw
0x2f64  ldarg.0
0x2f65  newobj   instance void System.Net.Http.Formatting.FormDataCollection::.ctor(class [System]System.Uri uri)
0x2f6a  call     instance class [System]System.Collections.Specialized.NameValueCollection System.Net.Http.Formatting.FormDataCollection::ReadAsNameValueCollection()
0x2f6f  ret
```
