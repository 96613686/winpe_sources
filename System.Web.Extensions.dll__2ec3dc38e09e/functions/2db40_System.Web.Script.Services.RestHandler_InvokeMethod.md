# System.Web.Script.Services.RestHandler::InvokeMethod

- ea: `0x2db40`
- end: `0x2dc1f`
- name: `System.Web.Script.Services.RestHandler::InvokeMethod`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x2dc20`

## callees

- `0x2b7b0`
- `0x2d910`
- `0x2db40`
- `0x2e1e0`
- `0x2e3f0`
- `0x2e810`
- `0x2f140`
- `0x2f1d0`
- `0x2f230`
- `0x2f260`
- `0x2f280`
- `0x2f2d0`
- `0x2f6d0`
- `0x31f00`

## string_xrefs

- `0x2dbd4`: `text/xml`
- `0x2dbfd`: `application/json`

## pseudocode

```c

```

## disassembly

```asm
0x2db40  ldarg.1
0x2db41  ldarg.0
0x2db42  call     void System.Web.Script.Services.RestHandler::InitializeCachePolicy(class System.Web.Script.Services.WebServiceMethodData methodData, class [System.Web]System.Web.HttpContext context)
0x2db47  ldnull
0x2db48  stloc.0
0x2db49  ldarg.1
0x2db4a  callvirt instance bool System.Web.Script.Services.WebServiceMethodData::get_IsStatic()
0x2db4f  brtrue.s loc_2DB67
0x2db51  ldarg.1
0x2db52  callvirt instance class System.Web.Script.Services.WebServiceData System.Web.Script.Services.WebServiceMethodData::get_Owner()
0x2db57  callvirt instance class System.Web.Script.Services.WebServiceTypeData System.Web.Script.Services.WebServiceData::get_TypeData()
0x2db5c  callvirt instance class [mscorlib]System.Type System.Web.Script.Services.WebServiceTypeData::get_Type()
0x2db61  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x2db66  stloc.0
0x2db67  ldarg.1
0x2db68  ldloc.0
0x2db69  ldarg.2
0x2db6a  callvirt instance object System.Web.Script.Services.WebServiceMethodData::CallMethodFromRawParams(object target, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> parameters)
0x2db6f  stloc.1
0x2db70  ldnull
0x2db71  stloc.3
0x2db72  ldarg.1
0x2db73  callvirt instance bool System.Web.Script.Services.WebServiceMethodData::get_UseXmlResponse()
0x2db78  brfalse.s loc_2DBDC
0x2db7a  ldloc.1
0x2db7b  isinst   [mscorlib]System.String
0x2db80  stloc.3
0x2db81  ldloc.3
0x2db82  brfalse.s loc_2DB8C
0x2db84  ldarg.1
0x2db85  callvirt instance bool System.Web.Script.Services.WebServiceMethodData::get_XmlSerializeString()
0x2db8a  brfalse.s loc_2DBD4
0x2db8c  nop
0x2db8d  ldloc.1
0x2db8e  call     string System.Web.Script.Services.ServicesUtilities::XmlSerializeObjectToString(object obj)
0x2db93  stloc.3
0x2db94  leave.s  loc_2DBD4
0x2db96  stloc.s  4
0x2db98  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x2db9d  call     string System.Web.Resources.AtlasWeb::get_WebService_InvalidXmlReturnType()
0x2dba2  ldc.i4.3
0x2dba3  newarr   [mscorlib]System.Object
0x2dba8  dup
0x2dba9  ldc.i4.0
0x2dbaa  ldarg.1
0x2dbab  callvirt instance string System.Web.Script.Services.WebServiceMethodData::get_MethodName()
0x2dbb0  stelem.ref
0x2dbb1  dup
0x2dbb2  ldc.i4.1
0x2dbb3  ldloc.1
0x2dbb4  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2dbb9  callvirt instance string [mscorlib]System.Type::get_FullName()
0x2dbbe  stelem.ref
0x2dbbf  dup
0x2dbc0  ldc.i4.2
0x2dbc1  ldloc.s  4
0x2dbc3  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2dbc8  stelem.ref
0x2dbc9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2dbce  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2dbd3  throw
0x2dbd4  ldstr    aTextXml// "text/xml"
0x2dbd9  stloc.2
0x2dbda  br.s     loc_2DC03
0x2dbdc  ldstr    aD_0// "{\"d\":"
0x2dbe1  ldarg.1
0x2dbe2  callvirt instance class System.Web.Script.Services.WebServiceData System.Web.Script.Services.WebServiceMethodData::get_Owner()
0x2dbe7  callvirt instance class System.Web.Script.Serialization.JavaScriptSerializer System.Web.Script.Services.WebServiceData::get_Serializer()
0x2dbec  ldloc.1
0x2dbed  callvirt instance string System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object obj)
0x2dbf2  ldstr    asc_3F82E// "}"
0x2dbf7  call     string [mscorlib]System.String::Concat(string, string, string)
0x2dbfc  stloc.3
0x2dbfd  ldstr    aApplicationJso// "application/json"
0x2dc02  stloc.2
0x2dc03  ldarg.0
0x2dc04  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2dc09  ldloc.2
0x2dc0a  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x2dc0f  ldloc.3
0x2dc10  brfalse.s loc_2DC1E
0x2dc12  ldarg.0
0x2dc13  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2dc18  ldloc.3
0x2dc19  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x2dc1e  ret
```
