# System.Deployment.Application.ApplicationDeployment::.ctor

- ea: `0xc300`
- end: `0xc469`
- name: `System.Deployment.Application.ApplicationDeployment::.ctor`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0xc470`

## callees

- `0xc300`
- `0xd590`
- `0xd5f0`
- `0xd600`
- `0xda80`
- `0xdbd0`
- `0x14780`
- `0x14790`
- `0x1ed00`
- `0x1ed40`
- `0x1f0b0`
- `0x1f8a0`
- `0x23020`

## string_xrefs

- `0xc3c9`: `Ex_SubNotInstalled`
- `0xc3f1`: `Ex_AppIdNotMatchInstalled`

## pseudocode

```c

```

## disassembly

```asm
0xc300  ldarg.0
0xc301  call     instance void [mscorlib]System.Object::.ctor()
0xc306  ldarg.1
0xc307  callvirt instance int32 [mscorlib]System.String::get_Length()
0xc30c  ldc.i4   0x10000
0xc311  ble.s    loc_C323
0xc313  ldstr    aExAppidtoolong// "Ex_AppIdTooLong"
0xc318  call     string System.Deployment.Application.Resources::GetString(string s)
0xc31d  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(string message)
0xc322  throw
0xc323  nop
0xc324  ldarg.0
0xc325  ldarg.1
0xc326  newobj   instance void System.Deployment.Application.DefinitionAppId::.ctor(string text)
0xc32b  stfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.ApplicationDeployment::_fullAppId
0xc330  leave.s  loc_C380
0xc332  stloc.3
0xc333  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0xc338  ldstr    aExSubappidnotv// "Ex_SubAppIdNotValid"
0xc33d  call     string System.Deployment.Application.Resources::GetString(string s)
0xc342  ldc.i4.1
0xc343  newarr   [mscorlib]System.Object
0xc348  dup
0xc349  ldc.i4.0
0xc34a  ldarg.1
0xc34b  stelem.ref
0xc34c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xc351  ldloc.3
0xc352  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(string message, class [mscorlib]System.Exception innerException)
0xc357  throw
0xc358  stloc.s  4
0xc35a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0xc35f  ldstr    aExSubappidnotv// "Ex_SubAppIdNotValid"
0xc364  call     string System.Deployment.Application.Resources::GetString(string s)
0xc369  ldc.i4.1
0xc36a  newarr   [mscorlib]System.Object
0xc36f  dup
0xc370  ldc.i4.0
0xc371  ldarg.1
0xc372  stelem.ref
0xc373  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xc378  ldloc.s  4
0xc37a  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(string message, class [mscorlib]System.Exception innerException)
0xc37f  throw
0xc380  ldarg.0
0xc381  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.ApplicationDeployment::_fullAppId
0xc386  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.DefinitionAppId::get_DeploymentIdentity()
0xc38b  stloc.0
0xc38c  ldarg.0
0xc38d  ldloc.0
0xc38e  callvirt instance class [mscorlib]System.Version System.Deployment.Application.DefinitionIdentity::get_Version()
0xc393  stfld    class [mscorlib]System.Version System.Deployment.Application.ApplicationDeployment::_currentVersion
0xc398  ldloc.0
0xc399  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.DefinitionIdentity::ToSubscriptionId()
0xc39e  stloc.1
0xc39f  ldarg.0
0xc3a0  call     class System.Deployment.Application.SubscriptionStore System.Deployment.Application.SubscriptionStore::get_CurrentUser()
0xc3a5  stfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.ApplicationDeployment::_subStore
0xc3aa  ldarg.0
0xc3ab  ldarg.0
0xc3ac  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.ApplicationDeployment::_subStore
0xc3b1  ldloc.1
0xc3b2  callvirt instance class System.Deployment.Application.SubscriptionState System.Deployment.Application.SubscriptionStore::GetSubscriptionState(class System.Deployment.Application.DefinitionIdentity subId)
0xc3b7  stfld    class System.Deployment.Application.SubscriptionState System.Deployment.Application.ApplicationDeployment::_subState
0xc3bc  ldarg.0
0xc3bd  ldfld    class System.Deployment.Application.SubscriptionState System.Deployment.Application.ApplicationDeployment::_subState
0xc3c2  callvirt instance bool System.Deployment.Application.SubscriptionState::get_IsInstalled()
0xc3c7  brtrue.s loc_C3D9
0xc3c9  ldstr    aExSubnotinstal// "Ex_SubNotInstalled"
0xc3ce  call     string System.Deployment.Application.Resources::GetString(string s)
0xc3d3  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(string message)
0xc3d8  throw
0xc3d9  ldarg.0
0xc3da  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.ApplicationDeployment::_fullAppId
0xc3df  ldarg.0
0xc3e0  ldfld    class System.Deployment.Application.SubscriptionState System.Deployment.Application.ApplicationDeployment::_subState
0xc3e5  callvirt instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionState::get_CurrentBind()
0xc3ea  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xc3ef  brtrue.s loc_C401
0xc3f1  ldstr    aExAppidnotmatc// "Ex_AppIdNotMatchInstalled"
0xc3f6  call     string System.Deployment.Application.Resources::GetString(string s)
0xc3fb  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(string message)
0xc400  throw
0xc401  ldarg.0
0xc402  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.ApplicationDeployment::_fullAppId
0xc407  callvirt instance string System.Deployment.Application.DefinitionAppId::get_Codebase()
0xc40c  newobj   instance void [System]System.Uri::.ctor(string)
0xc411  stloc.2
0xc412  ldloc.2
0xc413  callvirt instance bool [System]System.Uri::get_IsFile()
0xc418  brfalse.s loc_C42E
0xc41a  ldarg.0
0xc41b  ldc.i4.1
0xc41c  ldloc.2
0xc41d  callvirt instance string [System]System.Uri::get_LocalPath()
0xc422  newobj   instance void [mscorlib]System.Security.Permissions.FileIOPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.FileIOPermissionAccess, string)
0xc427  stfld    class [mscorlib]System.Security.CodeAccessPermission System.Deployment.Application.ApplicationDeployment::accessPermission
0xc42c  br.s     loc_C446
0xc42e  ldarg.0
0xc42f  ldc.i4.s 0x40
0xc431  ldarg.0
0xc432  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.ApplicationDeployment::_fullAppId
0xc437  callvirt instance string System.Deployment.Application.DefinitionAppId::get_Codebase()
0xc43c  newobj   instance void [System]System.Net.WebPermission::.ctor(valuetype [System]System.Net.NetworkAccess, string)
0xc441  stfld    class [mscorlib]System.Security.CodeAccessPermission System.Deployment.Application.ApplicationDeployment::accessPermission
0xc446  ldarg.0
0xc447  ldfld    class [mscorlib]System.Security.CodeAccessPermission System.Deployment.Application.ApplicationDeployment::accessPermission
0xc44c  callvirt instance void [mscorlib]System.Security.CodeAccessPermission::Demand()
0xc451  ldarg.0
0xc452  newobj   instance void [System]System.ComponentModel.EventHandlerList::.ctor()
0xc457  stfld    class [System]System.ComponentModel.EventHandlerList System.Deployment.Application.ApplicationDeployment::_events
0xc45c  ldarg.0
0xc45d  ldnull
0xc45e  call     class [System]System.ComponentModel.AsyncOperation [System]System.ComponentModel.AsyncOperationManager::CreateOperation(object)
0xc463  stfld    class [System]System.ComponentModel.AsyncOperation System.Deployment.Application.ApplicationDeployment::asyncOperation
0xc468  ret
```
