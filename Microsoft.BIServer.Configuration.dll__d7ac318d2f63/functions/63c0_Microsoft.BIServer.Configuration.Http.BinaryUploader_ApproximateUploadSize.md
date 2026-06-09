# Microsoft.BIServer.Configuration.Http.BinaryUploader::ApproximateUploadSize

- ea: `0x63c0`
- end: `0x63f6`
- name: `Microsoft.BIServer.Configuration.Http.BinaryUploader::ApproximateUploadSize`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7590`

## callees

- `0x63c0`

## pseudocode

```c

```

## disassembly

```asm
0x63c0  ldarg.0
0x63c1  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Content()
0x63c6  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x63cb  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::get_ContentLength()
0x63d0  stloc.0
0x63d1  ldloca.s 0
0x63d3  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x63d8  brtrue.s loc_63DD
0x63da  ldc.i4.0
0x63db  conv.i8
0x63dc  ret
0x63dd  ldarg.0
0x63de  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Content()
0x63e3  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x63e8  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::get_ContentLength()
0x63ed  stloc.1
0x63ee  ldloca.s 1
0x63f0  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0x63f5  ret
```
