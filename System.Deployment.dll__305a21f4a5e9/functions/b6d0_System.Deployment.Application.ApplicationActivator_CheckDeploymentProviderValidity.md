# System.Deployment.Application.ApplicationActivator::CheckDeploymentProviderValidity

- ea: `0xb6d0`
- end: `0xb823`
- name: `System.Deployment.Application.ApplicationActivator::CheckDeploymentProviderValidity`
- size: `339`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0xae50`
- `0xb4c0`

## callees

- `0xb6d0`
- `0xc220`
- `0x146f0`
- `0x14700`
- `0x17d40`
- `0x1ede0`
- `0x23020`
- `0x23cd0`
- `0x23fa0`
- `0x23fe0`
- `0x24b30`
- `0x24b90`

## string_xrefs

- `0xb75b`: `providerCodebaseUri=`
- `0xb7a4`: `ErrorMessage_DeploymentUriDifferent`
- `0xb7d3`: `Ex_DeploymentUriDifferentExText`

## pseudocode

```c

```

## disassembly

```asm
0xb6d0  ldarg.1
0xb6d1  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0xb6d6  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0xb6db  callvirt instance bool System.Deployment.Application.Manifest.Deployment::get_Install()
0xb6e0  brfalse  loc_B822
0xb6e5  ldarg.1
0xb6e6  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0xb6eb  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0xb6f0  callvirt instance class [System]System.Uri System.Deployment.Application.Manifest.Deployment::get_ProviderCodebaseUri()
0xb6f5  ldnull
0xb6f6  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0xb6fb  brfalse  loc_B822
0xb700  ldarg.2
0xb701  brfalse  loc_B822
0xb706  ldarg.2
0xb707  callvirt instance class [System]System.Uri System.Deployment.Application.SubscriptionState::get_DeploymentProviderUri()
0xb70c  ldnull
0xb70d  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0xb712  brfalse  loc_B822
0xb717  ldarg.2
0xb718  callvirt instance class [System]System.Uri System.Deployment.Application.SubscriptionState::get_DeploymentProviderUri()
0xb71d  callvirt instance string [System]System.Uri::get_Query()
0xb722  brfalse.s loc_B737
0xb724  ldarg.2
0xb725  callvirt instance class [System]System.Uri System.Deployment.Application.SubscriptionState::get_DeploymentProviderUri()
0xb72a  callvirt instance string [System]System.Uri::get_Query()
0xb72f  callvirt instance int32 [mscorlib]System.String::get_Length()
0xb734  ldc.i4.0
0xb735  bgt.s    loc_B73F
0xb737  ldarg.2
0xb738  callvirt instance class [System]System.Uri System.Deployment.Application.SubscriptionState::get_DeploymentProviderUri()
0xb73d  br.s     loc_B750
0xb73f  ldarg.2
0xb740  callvirt instance class [System]System.Uri System.Deployment.Application.SubscriptionState::get_DeploymentProviderUri()
0xb745  ldc.i4.2
0xb746  callvirt instance string [System]System.Uri::GetLeftPart(valuetype [System]System.UriPartial)
0xb74b  newobj   instance void [System]System.Uri::.ctor(string)
0xb750  stloc.0
0xb751  ldstr    aCheckingDeploy// "Checking deployment provider validity."
0xb756  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xb75b  ldstr    aProvidercodeba// "providerCodebaseUri="
0xb760  ldloc.0
0xb761  dup
0xb762  brtrue.s loc_B768
0xb764  pop
0xb765  ldnull
0xb766  br.s     loc_B76D
0xb768  callvirt instance string [mscorlib]System.Object::ToString()
0xb76d  call     string [mscorlib]System.String::Concat(string, string)
0xb772  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xb777  ldstr    aActdescToappco// "actDesc.ToAppCodebase()="
0xb77c  ldarg.1
0xb77d  callvirt instance string System.Deployment.Application.ActivationDescription::ToAppCodebase()
0xb782  call     string [mscorlib]System.String::Concat(string, string)
0xb787  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xb78c  ldloc.0
0xb78d  ldarg.1
0xb78e  callvirt instance string System.Deployment.Application.ActivationDescription::ToAppCodebase()
0xb793  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xb798  brtrue   loc_B822
0xb79d  ldc.i4.s 0x16
0xb79f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0xb7a4  ldstr    aErrormessageDe// "ErrorMessage_DeploymentUriDifferent"
0xb7a9  call     string System.Deployment.Application.Resources::GetString(string s)
0xb7ae  ldc.i4.1
0xb7af  newarr   [mscorlib]System.Object
0xb7b4  dup
0xb7b5  ldc.i4.0
0xb7b6  ldarg.1
0xb7b7  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0xb7bc  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0xb7c1  callvirt instance string System.Deployment.Application.Manifest.Description::get_FilteredProduct()
0xb7c6  stelem.ref
0xb7c7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb7cc  ldc.i4.s 0x16
0xb7ce  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0xb7d3  ldstr    aExDeploymentur// "Ex_DeploymentUriDifferentExText"
0xb7d8  call     string System.Deployment.Application.Resources::GetString(string s)
0xb7dd  ldc.i4.3
0xb7de  newarr   [mscorlib]System.Object
0xb7e3  dup
0xb7e4  ldc.i4.0
0xb7e5  ldarg.1
0xb7e6  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0xb7eb  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0xb7f0  callvirt instance string System.Deployment.Application.Manifest.Description::get_FilteredProduct()
0xb7f5  stelem.ref
0xb7f6  dup
0xb7f7  ldc.i4.1
0xb7f8  ldarg.1
0xb7f9  ldfld    class [System]System.Uri System.Deployment.Application.CommitApplicationParams::DeploySourceUri
0xb7fe  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0xb803  stelem.ref
0xb804  dup
0xb805  ldc.i4.2
0xb806  ldarg.2
0xb807  callvirt instance class [System]System.Uri System.Deployment.Application.SubscriptionState::get_DeploymentProviderUri()
0xb80c  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0xb811  stelem.ref
0xb812  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb817  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0xb81c  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0xb821  throw
0xb822  ret
```
