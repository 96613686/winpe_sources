# System.Deployment.Application.ApplicationActivator::SkipUpdate

- ea: `0xbfe0`
- end: `0xc040`
- name: `System.Deployment.Application.ApplicationActivator::SkipUpdate`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0xb4c0`

## callees

- `0xbfe0`
- `0x17cd0`
- `0x17d40`
- `0x1ee40`
- `0x1ee60`

## string_xrefs

- `0xbfe0`: `SkipUpdate called.`
- `0xc015`: `Skipped Update. UpdateSkipTime was `
- `0xc034`: `Update is not skipped.`

## pseudocode

```c

```

## disassembly

```asm
0xbfe0  ldstr    aSkipupdateCall// "SkipUpdate called."
0xbfe5  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0xbfea  ldarg.0
0xbfeb  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_UpdateSkippedDeployment()
0xbff0  brfalse.s loc_C034
0xbff2  ldarg.1
0xbff3  brfalse.s loc_C034
0xbff5  ldarg.0
0xbff6  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_UpdateSkippedDeployment()
0xbffb  ldarg.1
0xbffc  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xc001  brfalse.s loc_C034
0xc003  ldarg.0
0xc004  callvirt instance valuetype [mscorlib]System.DateTime System.Deployment.Application.SubscriptionState::get_UpdateSkipTime()
0xc009  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xc00e  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xc013  brfalse.s loc_C034
0xc015  ldstr    aSkippedUpdateU// "Skipped Update. UpdateSkipTime was "
0xc01a  ldarg.0
0xc01b  callvirt instance valuetype [mscorlib]System.DateTime System.Deployment.Application.SubscriptionState::get_UpdateSkipTime()
0xc020  stloc.0
0xc021  ldloca.s 0
0xc023  call     instance string [mscorlib]System.DateTime::ToString()
0xc028  call     string [mscorlib]System.String::Concat(string, string)
0xc02d  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xc032  ldc.i4.1
0xc033  ret
0xc034  ldstr    aUpdateIsNotSki// "Update is not skipped."
0xc039  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xc03e  ldc.i4.0
0xc03f  ret
```
