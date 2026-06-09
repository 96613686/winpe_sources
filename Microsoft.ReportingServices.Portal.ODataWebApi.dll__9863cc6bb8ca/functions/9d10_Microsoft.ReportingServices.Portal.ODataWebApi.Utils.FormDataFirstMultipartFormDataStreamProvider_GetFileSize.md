# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::GetFileSize

- ea: `0x9d10`
- end: `0x9e48`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::GetFileSize`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x9b70`

## callees

- `0x9d10`

## pseudocode

```c

```

## disassembly

```asm
0x9d10  ldarg.1
0x9d11  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x9d16  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::get_ContentLength()
0x9d1b  stloc.0
0x9d1c  ldloca.s 0
0x9d1e  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x9d23  brfalse  loc_9E45
0x9d28  ldarg.1
0x9d29  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x9d2e  callvirt instance class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::get_ContentType()
0x9d33  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [System.Net.Http]System.Net.Http.Headers.NameValueHeaderValue> [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::get_Parameters()
0x9d38  call     T0x2B0000DA
0x9d3d  stloc.1
0x9d3e  ldloc.1
0x9d3f  brfalse  loc_9E45
0x9d44  ldloc.1
0x9d45  callvirt instance string [System.Net.Http]System.Net.Http.Headers.NameValueHeaderValue::get_Value()
0x9d4a  stloc.2
0x9d4b  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x9d50  stloc.3
0x9d51  ldarg.0
0x9d52  call     instance class [System]System.Collections.Specialized.NameValueCollection [System.Net.Http.Formatting]System.Net.Http.MultipartFormDataStreamProvider::get_FormData()
0x9d57  callvirt instance string[] [System]System.Collections.Specialized.NameValueCollection::get_AllKeys()
0x9d5c  stloc.s  4
0x9d5e  ldc.i4.0
0x9d5f  stloc.s  5
0x9d61  br.s     loc_9DB8
0x9d63  ldloc.s  4
0x9d65  ldloc.s  5
0x9d67  ldelem.ref
0x9d68  stloc.s  6
0x9d6a  ldarg.0
0x9d6b  call     instance class [System]System.Collections.Specialized.NameValueCollection [System.Net.Http.Formatting]System.Net.Http.MultipartFormDataStreamProvider::get_FormData()
0x9d70  ldloc.s  6
0x9d72  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9d77  stloc.s  7
0x9d79  ldloc.3
0x9d7a  ldstr    a0// "--{0}"
0x9d7f  ldloc.2
0x9d80  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x9d85  pop
0x9d86  ldloc.3
0x9d87  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x9d8c  pop
0x9d8d  ldloc.3
0x9d8e  ldstr    aContentDisposi// "Content-Disposition: form-data; name=\""...
0x9d93  ldloc.s  6
0x9d95  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x9d9a  pop
0x9d9b  ldloc.3
0x9d9c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x9da1  pop
0x9da2  ldloc.3
0x9da3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x9da8  pop
0x9da9  ldloc.3
0x9daa  ldloc.s  7
0x9dac  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x9db1  pop
0x9db2  ldloc.s  5
0x9db4  ldc.i4.1
0x9db5  add
0x9db6  stloc.s  5
0x9db8  ldloc.s  5
0x9dba  ldloc.s  4
0x9dbc  ldlen
0x9dbd  conv.i4
0x9dbe  blt.s    loc_9D63
0x9dc0  ldloc.3
0x9dc1  ldstr    a0// "--{0}"
0x9dc6  ldloc.2
0x9dc7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x9dcc  pop
0x9dcd  ldloc.3
0x9dce  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x9dd3  pop
0x9dd4  ldloc.3
0x9dd5  ldstr    aContentDisposi_0// "Content-Disposition: form-data; name=\""...
0x9dda  ldarg.0
0x9ddb  call     instance class [System]System.Collections.Specialized.NameValueCollection [System.Net.Http.Formatting]System.Net.Http.MultipartFormDataStreamProvider::get_FormData()
0x9de0  ldstr    aName// "Name"
0x9de5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9dea  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x9def  pop
0x9df0  ldloc.3
0x9df1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x9df6  pop
0x9df7  ldarg.2
0x9df8  brfalse.s loc_9E13
0x9dfa  ldloc.3
0x9dfb  ldstr    aContentType0// "Content-Type: {0}"
0x9e00  ldarg.2
0x9e01  callvirt instance string [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::get_MediaType()
0x9e06  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x9e0b  pop
0x9e0c  ldloc.3
0x9e0d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x9e12  pop
0x9e13  ldloc.3
0x9e14  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x9e19  pop
0x9e1a  ldloc.3
0x9e1b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x9e20  pop
0x9e21  ldloc.3
0x9e22  ldstr    a0_0// "--{0}--"
0x9e27  ldloc.2
0x9e28  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x9e2d  pop
0x9e2e  ldloc.3
0x9e2f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x9e34  pop
0x9e35  ldloca.s 0
0x9e37  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0x9e3c  ldloc.3
0x9e3d  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x9e42  conv.i8
0x9e43  sub
0x9e44  ret
0x9e45  ldc.i4.0
0x9e46  conv.i8
0x9e47  ret
```
