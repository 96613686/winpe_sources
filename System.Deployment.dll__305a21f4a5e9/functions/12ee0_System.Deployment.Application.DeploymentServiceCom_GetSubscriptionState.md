# System.Deployment.Application.DeploymentServiceCom::GetSubscriptionState

- ea: `0x12ee0`
- end: `0x12f84`
- name: `System.Deployment.Application.DeploymentServiceCom::GetSubscriptionState`
- size: `164`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x12a70`
- `0x12ec0`

## callees

- `0xd930`
- `0xda80`
- `0x12ee0`
- `0x146f0`
- `0x14700`
- `0x1f0b0`
- `0x1f170`
- `0x1f8a0`
- `0x23020`

## string_xrefs

- `0x12ee8`: `Ex_ComArgSubIdentityNull`
- `0x12f0a`: `Ex_ComArgSubIdentityNotValid`
- `0x12f31`: `Ex_ComArgSubIdentityNotValid`
- `0x12f60`: `Ex_ComArgSubIdentityWithVersion`

## pseudocode

```c

```

## disassembly

```asm
0x12ee0  ldarg.1
0x12ee1  brtrue.s loc_12EF8
0x12ee3  ldstr    aTextualsubid// "textualSubId"
0x12ee8  ldstr    aExComargsubide// "Ex_ComArgSubIdentityNull"
0x12eed  call     string System.Deployment.Application.Resources::GetString(string s)
0x12ef2  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string, string)
0x12ef7  throw
0x12ef8  ldnull
0x12ef9  stloc.0
0x12efa  ldarg.1
0x12efb  newobj   instance void System.Deployment.Application.DefinitionIdentity::.ctor(string text)
0x12f00  stloc.0
0x12f01  leave.s  loc_12F51
0x12f03  stloc.2
0x12f04  ldc.i4.8
0x12f05  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x12f0a  ldstr    aExComargsubide_0// "Ex_ComArgSubIdentityNotValid"
0x12f0f  call     string System.Deployment.Application.Resources::GetString(string s)
0x12f14  ldc.i4.1
0x12f15  newarr   [mscorlib]System.Object
0x12f1a  dup
0x12f1b  ldc.i4.0
0x12f1c  ldarg.1
0x12f1d  stelem.ref
0x12f1e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12f23  ldloc.2
0x12f24  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x12f29  throw
0x12f2a  stloc.3
0x12f2b  ldc.i4.8
0x12f2c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x12f31  ldstr    aExComargsubide_0// "Ex_ComArgSubIdentityNotValid"
0x12f36  call     string System.Deployment.Application.Resources::GetString(string s)
0x12f3b  ldc.i4.1
0x12f3c  newarr   [mscorlib]System.Object
0x12f41  dup
0x12f42  ldc.i4.0
0x12f43  ldarg.1
0x12f44  stelem.ref
0x12f45  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12f4a  ldloc.3
0x12f4b  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x12f50  throw
0x12f51  ldloc.0
0x12f52  callvirt instance class [mscorlib]System.Version System.Deployment.Application.DefinitionIdentity::get_Version()
0x12f57  ldnull
0x12f58  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x12f5d  brfalse.s loc_12F70
0x12f5f  ldc.i4.8
0x12f60  ldstr    aExComargsubide_1// "Ex_ComArgSubIdentityWithVersion"
0x12f65  call     string System.Deployment.Application.Resources::GetString(string s)
0x12f6a  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x12f6f  throw
0x12f70  call     class System.Deployment.Application.SubscriptionStore System.Deployment.Application.SubscriptionStore::get_CurrentUser()
0x12f75  stloc.1
0x12f76  ldloc.1
0x12f77  callvirt instance void System.Deployment.Application.SubscriptionStore::RefreshStorePointer()
0x12f7c  ldloc.1
0x12f7d  ldloc.0
0x12f7e  callvirt instance class System.Deployment.Application.SubscriptionState System.Deployment.Application.SubscriptionStore::GetSubscriptionState(class System.Deployment.Application.DefinitionIdentity subId)
0x12f83  ret
```
