# Microsoft.ReportingServices.Library.Native::IsAdmin

- ea: `0x3f40`
- end: `0x3f92`
- name: `Microsoft.ReportingServices.Library.Native::IsAdmin`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x3e90`
- `0x3f40`
- `0x4100`

## string_xrefs

- `0x3f5d`: `CheckTokenMembership: Win32 error:{0}, can't validate the user with sid:{1} is admin`

## pseudocode

```c

```

## disassembly

```asm
0x3f40  ldc.i4.0
0x3f41  stloc.0
0x3f42  ldnull
0x3f43  stloc.1
0x3f44  ldc.i4.0
0x3f45  stloc.2
0x3f46  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeSidPtr Microsoft.ReportingServices.Library.Native::GetAdminSid()
0x3f4b  stloc.1
0x3f4c  ldarg.0
0x3f4d  ldloc.1
0x3f4e  ldloca.s 2
0x3f50  call     bool Microsoft.ReportingServices.Library.Native::CheckTokenMembership(native int token, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeSidPtr sidToCheck, [out] bool& isMember)
0x3f55  brtrue.s loc_3F80
0x3f57  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x3f5c  stloc.0
0x3f5d  ldstr    aChecktokenmemb// "CheckTokenMembership: Win32 error:{0}, "...
0x3f62  ldloc.0
0x3f63  box      [mscorlib]System.Int32
0x3f68  ldloc.1
0x3f69  call     string [mscorlib]System.String::Format(string, object, object)
0x3f6e  stloc.3
0x3f6f  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x3f74  ldc.i4.1
0x3f75  ldloc.3
0x3f76  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::TraceException(valuetype [System]System.Diagnostics.TraceLevel, string)
0x3f7b  ldc.i4.0
0x3f7c  stloc.s  4
0x3f7e  leave.s  loc_3F8F
0x3f80  ldloc.2
0x3f81  stloc.s  4
0x3f83  leave.s  loc_3F8F
0x3f85  ldloc.1
0x3f86  brfalse.s loc_3F8E
0x3f88  ldloc.1
0x3f89  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x3f8e  endfinally
0x3f8f  ldloc.s  4
0x3f91  ret
```
