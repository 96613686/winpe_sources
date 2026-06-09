# Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1::GetModelStateValidationErrors

- ea: `0xbdb0`
- end: `0xbe65`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1::GetModelStateValidationErrors`
- size: `181`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xbdb0`

## pseudocode

```c

```

## disassembly

```asm
0xbdb0  newobj   instance void class <>c__DisplayClass8_0<var<u1>>::.ctor()
0xbdb5  stloc.0
0xbdb6  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xbdbb  stloc.1
0xbdbc  ldarg.0
0xbdbd  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0xbdc2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Web.Http]System.Web.Http.ModelBinding.ModelState>> [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary::GetEnumerator()
0xbdc7  stloc.2
0xbdc8  br.s     loc_BE21
0xbdca  ldloc.2
0xbdcb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Web.Http]System.Web.Http.ModelBinding.ModelState>>::get_Current()
0xbdd0  stloc.3
0xbdd1  ldloca.s 3
0xbdd3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Web.Http]System.Web.Http.ModelBinding.ModelState>::get_Value()
0xbdd8  callvirt instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelErrorCollection [System.Web.Http]System.Web.Http.ModelBinding.ModelState::get_Errors()
0xbddd  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Web.Http]System.Web.Http.ModelBinding.ModelError>::GetEnumerator()
0xbde2  stloc.s  4
0xbde4  br.s     loc_BE0A
0xbde6  ldloc.s  4
0xbde8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Web.Http]System.Web.Http.ModelBinding.ModelError>::get_Current()
0xbded  stloc.s  5
0xbdef  ldloc.s  5
0xbdf1  callvirt instance class [mscorlib]System.Exception [System.Web.Http]System.Web.Http.ModelBinding.ModelError::get_Exception()
0xbdf6  brfalse.s loc_BE0A
0xbdf8  ldloc.1
0xbdf9  ldloc.s  5
0xbdfb  callvirt instance class [mscorlib]System.Exception [System.Web.Http]System.Web.Http.ModelBinding.ModelError::get_Exception()
0xbe00  callvirt instance string [mscorlib]System.Exception::get_Message()
0xbe05  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbe0a  ldloc.s  4
0xbe0c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xbe11  brtrue.s loc_BDE6
0xbe13  leave.s  loc_BE21
0xbe15  ldloc.s  4
0xbe17  brfalse.s loc_BE20
0xbe19  ldloc.s  4
0xbe1b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbe20  endfinally
0xbe21  ldloc.2
0xbe22  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xbe27  brtrue.s loc_BDCA
0xbe29  leave.s  loc_BE35
0xbe2b  ldloc.2
0xbe2c  brfalse.s loc_BE34
0xbe2e  ldloc.2
0xbe2f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbe34  endfinally
0xbe35  ldloc.0
0xbe36  ldstr    asc_13212// ","
0xbe3b  ldloc.1
0xbe3c  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0xbe41  stfld    string class <>c__DisplayClass8_0<var<u1>>::combinedErrorsString
0xbe46  ldarg.0
0xbe47  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xbe4c  ldc.i4.2
0xbe4d  ldloc.0
0xbe4e  ldftn    instance string class <>c__DisplayClass8_0<var<u1>>::<GetModelStateValidationErrors>b__0()
0xbe54  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xbe59  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xbe5e  ldloc.0
0xbe5f  ldfld    string class <>c__DisplayClass8_0<var<u1>>::combinedErrorsString
0xbe64  ret
```
