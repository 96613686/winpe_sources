# Microsoft.ReportingServices.Diagnostics.Utilities.RSExceptionHandler::HandleException

- ea: `0xfe40`
- end: `0xfecc`
- name: `Microsoft.ReportingServices.Diagnostics.Utilities.RSExceptionHandler::HandleException`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x6480`
- `0x64c0`
- `0x94a0`
- `0x96d0`
- `0xa930`
- `0xfe40`

## pseudocode

```c

```

## disassembly

```asm
0xfe40  ldstr    aRsexceptionhan// "RSExceptionHandler"
0xfe45  call     object [mscorlib]System.Runtime.Remoting.Messaging.CallContext::GetData(string)
0xfe4a  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0xfe4f  stloc.0
0xfe50  ldloc.0
0xfe51  brfalse.s loc_FE7D
0xfe53  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfe58  ldstr    aRsexceptionhan_0// "RSExceptionHandler: secondary exception"...
0xfe5d  ldloc.0
0xfe5e  ldarg.2
0xfe5f  callvirt instance class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSExceptionCreatedEventArgs::get_Exception()
0xfe64  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0xfe69  stloc.1
0xfe6a  call     class Microsoft.ReportingServices.Diagnostics.Dumper Microsoft.ReportingServices.Diagnostics.Dumper::get_Current()
0xfe6f  ldarg.2
0xfe70  callvirt instance class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSExceptionCreatedEventArgs::get_Exception()
0xfe75  ldloc.1
0xfe76  ldc.i4.1
0xfe77  callvirt instance void Microsoft.ReportingServices.Diagnostics.Dumper::DumpHere(class [mscorlib]System.Exception optionalException, string assertionMessage, bool unhandledException)
0xfe7c  ret
0xfe7d  nop
0xfe7e  ldstr    aRsexceptionhan// "RSExceptionHandler"
0xfe83  ldarg.2
0xfe84  callvirt instance class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSExceptionCreatedEventArgs::get_Exception()
0xfe89  call     void [mscorlib]System.Runtime.Remoting.Messaging.CallContext::SetData(string, object)
0xfe8e  ldarg.0
0xfe8f  ldfld    class [mscorlib]System.Func`1<string> Microsoft.ReportingServices.Diagnostics.Utilities.RSExceptionHandler::m_actorUriFunc
0xfe94  callvirt instance var<u1> class [mscorlib]System.Func`1<string>::Invoke()
0xfe99  stloc.2
0xfe9a  call     string Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ServerProductName()
0xfe9f  stloc.3
0xfea0  call     class Microsoft.ReportingServices.Diagnostics.RSConfiguration Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0xfea5  callvirt instance string Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ServerProductVersion()
0xfeaa  stloc.s  4
0xfeac  ldarg.2
0xfead  callvirt instance class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSExceptionCreatedEventArgs::get_Exception()
0xfeb2  stloc.0
0xfeb3  ldloc.0
0xfeb4  ldloc.2
0xfeb5  ldloc.3
0xfeb6  ldloc.s  4
0xfeb8  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::SetExceptionProperties(string, string, string)
0xfebd  leave.s  loc_FECB
0xfebf  ldstr    aRsexceptionhan// "RSExceptionHandler"
0xfec4  ldnull
0xfec5  call     void [mscorlib]System.Runtime.Remoting.Messaging.CallContext::SetData(string, object)
0xfeca  endfinally
0xfecb  ret
```
