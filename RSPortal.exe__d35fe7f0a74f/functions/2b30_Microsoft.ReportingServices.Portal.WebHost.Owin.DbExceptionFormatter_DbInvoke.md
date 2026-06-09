# Microsoft.ReportingServices.Portal.WebHost.Owin.DbExceptionFormatter::DbInvoke

- ea: `0x2b30`
- end: `0x2b79`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.DbExceptionFormatter::DbInvoke`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2a70`
- `0x39b0`

## callees

- `0x2b30`
- `0x2b80`

## pseudocode

```c

```

## disassembly

```asm
0x2b30  ldarg.1
0x2b31  ldarg.0
0x2b32  callvirt instance var<u1> class [mscorlib]System.Func`2<class [Microsoft.Owin]Microsoft.Owin.IOwinContext, bool>::Invoke(void)
0x2b37  stloc.0
0x2b38  leave.s  loc_2B77
0x2b3a  stloc.1
0x2b3b  ldarg.0
0x2b3c  ldc.i4.2
0x2b3d  ldloc.1
0x2b3e  call     void Microsoft.ReportingServices.Portal.WebHost.Owin.DbExceptionFormatter::FormatResult(class [Microsoft.Owin]Microsoft.Owin.IOwinContext context, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorReason errorState, class [mscorlib]System.Exception e)
0x2b43  leave.s  loc_2B75
0x2b45  stloc.2
0x2b46  ldarg.0
0x2b47  ldc.i4.1
0x2b48  ldloc.2
0x2b49  call     void Microsoft.ReportingServices.Portal.WebHost.Owin.DbExceptionFormatter::FormatResult(class [Microsoft.Owin]Microsoft.Owin.IOwinContext context, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorReason errorState, class [mscorlib]System.Exception e)
0x2b4e  leave.s  loc_2B75
0x2b50  stloc.3
0x2b51  ldarg.0
0x2b52  ldc.i4.4
0x2b53  ldloc.3
0x2b54  call     void Microsoft.ReportingServices.Portal.WebHost.Owin.DbExceptionFormatter::FormatResult(class [Microsoft.Owin]Microsoft.Owin.IOwinContext context, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorReason errorState, class [mscorlib]System.Exception e)
0x2b59  leave.s  loc_2B75
0x2b5b  stloc.s  4
0x2b5d  ldarg.0
0x2b5e  ldc.i4.3
0x2b5f  ldloc.s  4
0x2b61  call     void Microsoft.ReportingServices.Portal.WebHost.Owin.DbExceptionFormatter::FormatResult(class [Microsoft.Owin]Microsoft.Owin.IOwinContext context, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorReason errorState, class [mscorlib]System.Exception e)
0x2b66  leave.s  loc_2B75
0x2b68  stloc.s  5
0x2b6a  ldarg.0
0x2b6b  ldc.i4.1
0x2b6c  ldloc.s  5
0x2b6e  call     void Microsoft.ReportingServices.Portal.WebHost.Owin.DbExceptionFormatter::FormatResult(class [Microsoft.Owin]Microsoft.Owin.IOwinContext context, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorReason errorState, class [mscorlib]System.Exception e)
0x2b73  leave.s  loc_2B75
0x2b75  ldc.i4.0
0x2b76  ret
0x2b77  ldloc.0
0x2b78  ret
```
