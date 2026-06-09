# System.Web.ClientServices.Providers.ProxyHelper::CreateWebRequestAndGetResponse

- ea: `0x36b00`
- end: `0x36c98`
- name: `System.Web.ClientServices.Providers.ProxyHelper::CreateWebRequestAndGetResponse`
- size: `408`
- prototype: ``
- caller_count: `7`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x339a0`
- `0x33c90`
- `0x344a0`
- `0x34b80`
- `0x35210`
- `0x35b70`
- `0x35e00`

## callees

- `0x28250`
- `0x2a730`
- `0x31d10`
- `0x31e90`
- `0x32db0`
- `0x333e0`
- `0x33430`
- `0x36b00`
- `0x36ca0`
- `0x36d40`
- `0x36df0`
- `0x36e90`

## string_xrefs

- `0x36b14`: `application/json; charset=utf-8`

## pseudocode

```c

```

## disassembly

```asm
0x36b00  ldarg.0
0x36b01  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(string)
0x36b06  castclass [System]System.Net.HttpWebRequest
0x36b0b  stloc.0
0x36b0c  ldloc.0
0x36b0d  ldc.i4.1
0x36b0e  callvirt instance void [System]System.Net.WebRequest::set_UseDefaultCredentials(bool)
0x36b13  ldloc.0
0x36b14  ldstr    aApplicationJso_1// "application/json; charset=utf-8"
0x36b19  callvirt instance void [System]System.Net.WebRequest::set_ContentType(string)
0x36b1e  ldloc.0
0x36b1f  ldc.i4.1
0x36b20  callvirt instance void [System]System.Net.HttpWebRequest::set_AllowAutoRedirect(bool)
0x36b25  ldloc.0
0x36b26  ldstr    aPost// "POST"
0x36b2b  callvirt instance void [System]System.Net.WebRequest::set_Method(string)
0x36b30  ldarg.1
0x36b31  ldind.ref
0x36b32  brtrue.s loc_36B40
0x36b34  ldarg.1
0x36b35  ldarg.0
0x36b36  ldarg.2
0x36b37  ldarg.3
0x36b38  ldarg.s  4
0x36b3a  call     class [System]System.Net.CookieContainer System.Web.ClientServices.Providers.ProxyHelper::ConstructCookieContainer(string serverUri, string username, string connectionString, string connectionStringProvider)
0x36b3f  stind.ref
0x36b40  ldarg.1
0x36b41  ldind.ref
0x36b42  brfalse.s loc_36B4C
0x36b44  ldloc.0
0x36b45  ldarg.1
0x36b46  ldind.ref
0x36b47  callvirt instance void [System]System.Net.HttpWebRequest::set_CookieContainer(class [System]System.Net.CookieContainer)
0x36b4c  ldarg.s  5
0x36b4e  brfalse.s loc_36B87
0x36b50  ldarg.s  5
0x36b52  ldlen
0x36b53  brfalse.s loc_36B87
0x36b55  ldarg.s  5
0x36b57  ldarg.s  6
0x36b59  call     unsigned int8[] System.Web.ClientServices.Providers.ProxyHelper::GetSerializedParameters(string[] paramNames, object[] paramValues)
0x36b5e  stloc.1
0x36b5f  ldloc.0
0x36b60  ldloc.1
0x36b61  ldlen
0x36b62  conv.i4
0x36b63  conv.i8
0x36b64  callvirt instance void [System]System.Net.WebRequest::set_ContentLength(int64)
0x36b69  ldloc.0
0x36b6a  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebRequest::GetRequestStream()
0x36b6f  stloc.2
0x36b70  ldloc.2
0x36b71  ldloc.1
0x36b72  ldc.i4.0
0x36b73  ldloc.1
0x36b74  ldlen
0x36b75  conv.i4
0x36b76  callvirt instance void [mscorlib]System.IO.Stream::Write(unsigned int8[], int32, int32)
0x36b7b  leave.s  loc_36B8F
0x36b7d  ldloc.2
0x36b7e  brfalse.s loc_36B86
0x36b80  ldloc.2
0x36b81  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36b86  endfinally
0x36b87  ldloc.0
0x36b88  ldc.i4.0
0x36b89  conv.i8
0x36b8a  callvirt instance void [System]System.Net.WebRequest::set_ContentLength(int64)
0x36b8f  nop
0x36b90  ldloc.0
0x36b91  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebRequest::GetResponse()
0x36b96  castclass [System]System.Net.HttpWebResponse
0x36b9b  stloc.3
0x36b9c  ldloc.3
0x36b9d  brtrue.s loc_36BAA
0x36b9f  call     string System.Web.Resources.AtlasWeb::get_ClientService_BadJsonResponse()
0x36ba4  newobj   instance void [System]System.Net.WebException::.ctor(string)
0x36ba9  throw
0x36baa  ldloc.3
0x36bab  ldarg.1
0x36bac  ldind.ref
0x36bad  ldarg.0
0x36bae  ldarg.2
0x36baf  ldarg.3
0x36bb0  ldarg.s  4
0x36bb2  call     void System.Web.ClientServices.Providers.ProxyHelper::GetCookiesFromResponse(class [System]System.Net.HttpWebResponse response, class [System]System.Net.CookieContainer cookies, string serverUri, string username, string connectionString, string connectionStringProvider)
0x36bb7  ldarg.s  7
0x36bb9  ldnull
0x36bba  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x36bbf  brfalse.s loc_36BC9
0x36bc1  ldnull
0x36bc2  stloc.s  8
0x36bc4  leave    loc_36C95
0x36bc9  call     bool [System.Web]System.Web.Util.AppSettings::get_UseLegacyClientServicesJsonHandling()
0x36bce  brtrue.s loc_36BD7
0x36bd0  newobj   instance void System.Web.Script.Serialization.DictionaryTypeResolver::.ctor()
0x36bd5  br.s     loc_36BDC
0x36bd7  newobj   instance void System.Web.Script.Serialization.SimpleTypeResolver::.ctor()
0x36bdc  stloc.s  4
0x36bde  ldloc.s  4
0x36be0  newobj   instance void System.Web.Script.Serialization.JavaScriptSerializer::.ctor(class System.Web.Script.Serialization.JavaScriptTypeResolver resolver)
0x36be5  stloc.s  5
0x36be7  ldloc.3
0x36be8  call     string System.Web.ClientServices.Providers.ProxyHelper::GetResponseString(class [System]System.Net.HttpWebResponse response)
0x36bed  stloc.s  6
0x36bef  ldloc.s  5
0x36bf1  ldloc.s  6
0x36bf3  callvirt instance object System.Web.Script.Serialization.JavaScriptSerializer::DeserializeObject(string input)
0x36bf8  isinst   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>
0x36bfd  stloc.s  7
0x36bff  ldloc.s  7
0x36c01  brfalse.s loc_36C11
0x36c03  ldloc.s  7
0x36c05  ldstr    aD// "d"
0x36c0a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x36c0f  brtrue.s loc_36C1C
0x36c11  call     string System.Web.Resources.AtlasWeb::get_ClientService_BadJsonResponse()
0x36c16  newobj   instance void [System]System.Net.WebException::.ctor(string)
0x36c1b  throw
0x36c1c  ldloc.s  7
0x36c1e  ldstr    aD// "d"
0x36c23  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x36c28  ldarg.s  7
0x36c2a  ldloc.s  5
0x36c2c  call     object System.Web.Script.Serialization.ObjectConverter::ConvertObjectToType(object o, class [mscorlib]System.Type type, class System.Web.Script.Serialization.JavaScriptSerializer serializer)
0x36c31  stloc.s  8
0x36c33  leave.s  loc_36C95
0x36c35  ldloc.3
0x36c36  brfalse.s loc_36C3E
0x36c38  ldloc.3
0x36c39  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36c3e  endfinally
0x36c3f  stloc.s  9
0x36c41  ldloc.s  9
0x36c43  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x36c48  castclass [System]System.Net.HttpWebResponse
0x36c4d  stloc.s  0xA
0x36c4f  ldloc.s  0xA
0x36c51  brtrue.s loc_36C55
0x36c53  rethrow
0x36c55  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x36c5a  call     string System.Web.Resources.AtlasWeb::get_ProxyHelper_BadStatusCode()
0x36c5f  ldc.i4.2
0x36c60  newarr   [mscorlib]System.Object
0x36c65  dup
0x36c66  ldc.i4.0
0x36c67  ldloc.s  0xA
0x36c69  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0x36c6e  stloc.s  0xB
0x36c70  ldloca.s 0xB
0x36c72  constrained. [System]System.Net.HttpStatusCode
0x36c78  callvirt instance string [mscorlib]System.Object::ToString()
0x36c7d  stelem.ref
0x36c7e  dup
0x36c7f  ldc.i4.1
0x36c80  ldloc.s  0xA
0x36c82  call     string System.Web.ClientServices.Providers.ProxyHelper::GetResponseString(class [System]System.Net.HttpWebResponse response)
0x36c87  stelem.ref
0x36c88  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x36c8d  ldloc.s  9
0x36c8f  newobj   instance void [System]System.Net.WebException::.ctor(string, class [mscorlib]System.Exception)
0x36c94  throw
0x36c95  ldloc.s  8
0x36c97  ret
```
