# System.Deployment.Application.SubscriptionStateInternal::ToString

- ea: `0xfcb0`
- end: `0xff00`
- name: `System.Deployment.Application.SubscriptionStateInternal::ToString`
- size: `592`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0xfcb0`

## string_xrefs

- `0xfcb7`: `IsInstalled=`
- `0xfde9`: `DeploymentProviderUri=`
- `0xfe7d`: `UpdateSkipTime=`
- `0xfea5`: `UpdateSkippedDeployment=`

## pseudocode

```c

```

## disassembly

```asm
0xfcb0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xfcb5  stloc.0
0xfcb6  ldloc.0
0xfcb7  ldstr    aIsinstalled// "IsInstalled="
0xfcbc  ldarg.0
0xfcbd  ldflda   bool System.Deployment.Application.SubscriptionStateInternal::IsInstalled
0xfcc2  call     instance string [mscorlib]System.Boolean::ToString()
0xfcc7  ldstr    asc_3279C// "\r\n"
0xfccc  call     string [mscorlib]System.String::Concat(string, string, string)
0xfcd1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xfcd6  pop
0xfcd7  ldloc.0
0xfcd8  ldstr    aIsshellvisible_0// "IsShellVisible="
0xfcdd  ldarg.0
0xfcde  ldflda   bool System.Deployment.Application.SubscriptionStateInternal::IsShellVisible
0xfce3  call     instance string [mscorlib]System.Boolean::ToString()
0xfce8  ldstr    asc_3279C// "\r\n"
0xfced  call     string [mscorlib]System.String::Concat(string, string, string)
0xfcf2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xfcf7  pop
0xfcf8  ldloc.0
0xfcf9  ldstr    aCurrentbind_0// "CurrentBind="
0xfcfe  ldarg.0
0xfcff  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::CurrentBind
0xfd04  brtrue.s loc_FD0D
0xfd06  ldstr    aNull// "null"
0xfd0b  br.s     loc_FD18
0xfd0d  ldarg.0
0xfd0e  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::CurrentBind
0xfd13  callvirt instance string [mscorlib]System.Object::ToString()
0xfd18  ldstr    asc_3279C// "\r\n"
0xfd1d  call     string [mscorlib]System.String::Concat(string, string, string)
0xfd22  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xfd27  pop
0xfd28  ldloc.0
0xfd29  ldstr    aPreviousbind_0// "PreviousBind="
0xfd2e  ldarg.0
0xfd2f  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::PreviousBind
0xfd34  brtrue.s loc_FD3D
0xfd36  ldstr    aNull// "null"
0xfd3b  br.s     loc_FD48
0xfd3d  ldarg.0
0xfd3e  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::PreviousBind
0xfd43  callvirt instance string [mscorlib]System.Object::ToString()
0xfd48  ldstr    asc_3279C// "\r\n"
0xfd4d  call     string [mscorlib]System.String::Concat(string, string, string)
0xfd52  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xfd57  pop
0xfd58  ldloc.0
0xfd59  ldstr    aPendingbind_0// "PendingBind="
0xfd5e  ldarg.0
0xfd5f  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::PendingBind
0xfd64  brtrue.s loc_FD6D
0xfd66  ldstr    aNull// "null"
0xfd6b  br.s     loc_FD78
0xfd6d  ldarg.0
0xfd6e  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::PendingBind
0xfd73  callvirt instance string [mscorlib]System.Object::ToString()
0xfd78  ldstr    asc_3279C// "\r\n"
0xfd7d  call     string [mscorlib]System.String::Concat(string, string, string)
0xfd82  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xfd87  pop
0xfd88  ldloc.0
0xfd89  ldstr    aPendingdeploym_1// "PendingDeployment="
0xfd8e  ldarg.0
0xfd8f  ldfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionStateInternal::PendingDeployment
0xfd94  brtrue.s loc_FD9D
0xfd96  ldstr    aNull// "null"
0xfd9b  br.s     loc_FDA8
0xfd9d  ldarg.0
0xfd9e  ldfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionStateInternal::PendingDeployment
0xfda3  callvirt instance string [mscorlib]System.Object::ToString()
0xfda8  ldstr    asc_3279C// "\r\n"
0xfdad  call     string [mscorlib]System.String::Concat(string, string, string)
0xfdb2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xfdb7  pop
0xfdb8  ldloc.0
0xfdb9  ldstr    aExcludeddeploy_0// "ExcludedDeployment="
0xfdbe  ldarg.0
0xfdbf  ldfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionStateInternal::ExcludedDeployment
0xfdc4  brtrue.s loc_FDCD
0xfdc6  ldstr    aNull// "null"
0xfdcb  br.s     loc_FDD8
0xfdcd  ldarg.0
0xfdce  ldfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionStateInternal::ExcludedDeployment
0xfdd3  callvirt instance string [mscorlib]System.Object::ToString()
0xfdd8  ldstr    asc_3279C// "\r\n"
0xfddd  call     string [mscorlib]System.String::Concat(string, string, string)
0xfde2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xfde7  pop
0xfde8  ldloc.0
0xfde9  ldstr    aDeploymentprov_0// "DeploymentProviderUri="
0xfdee  ldarg.0
0xfdef  ldfld    class [System]System.Uri System.Deployment.Application.SubscriptionStateInternal::DeploymentProviderUri
0xfdf4  ldnull
0xfdf5  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0xfdfa  brtrue.s loc_FE03
0xfdfc  ldstr    aNull// "null"
0xfe01  br.s     loc_FE0E
0xfe03  ldarg.0
0xfe04  ldfld    class [System]System.Uri System.Deployment.Application.SubscriptionStateInternal::DeploymentProviderUri
0xfe09  callvirt instance string [mscorlib]System.Object::ToString()
0xfe0e  ldstr    asc_3279C// "\r\n"
0xfe13  call     string [mscorlib]System.String::Concat(string, string, string)
0xfe18  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xfe1d  pop
0xfe1e  ldloc.0
0xfe1f  ldstr    aMinimumrequire_0// "MinimumRequiredVersion="
0xfe24  ldarg.0
0xfe25  ldfld    class [mscorlib]System.Version System.Deployment.Application.SubscriptionStateInternal::MinimumRequiredVersion
0xfe2a  ldnull
0xfe2b  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0xfe30  brtrue.s loc_FE39
0xfe32  ldstr    aNull// "null"
0xfe37  br.s     loc_FE44
0xfe39  ldarg.0
0xfe3a  ldfld    class [mscorlib]System.Version System.Deployment.Application.SubscriptionStateInternal::MinimumRequiredVersion
0xfe3f  callvirt instance string [mscorlib]System.Object::ToString()
0xfe44  ldstr    asc_3279C// "\r\n"
0xfe49  call     string [mscorlib]System.String::Concat(string, string, string)
0xfe4e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xfe53  pop
0xfe54  ldloc.0
0xfe55  ldstr    aLastchecktime_0// "LastCheckTime="
0xfe5a  ldarg.0
0xfe5b  ldfld    valuetype [mscorlib]System.DateTime System.Deployment.Application.SubscriptionStateInternal::LastCheckTime
0xfe60  pop
0xfe61  ldarg.0
0xfe62  ldflda   valuetype [mscorlib]System.DateTime System.Deployment.Application.SubscriptionStateInternal::LastCheckTime
0xfe67  call     instance string [mscorlib]System.DateTime::ToString()
0xfe6c  ldstr    asc_3279C// "\r\n"
0xfe71  call     string [mscorlib]System.String::Concat(string, string, string)
0xfe76  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xfe7b  pop
0xfe7c  ldloc.0
0xfe7d  ldstr    aUpdateskiptime_0// "UpdateSkipTime="
0xfe82  ldarg.0
0xfe83  ldfld    valuetype [mscorlib]System.DateTime System.Deployment.Application.SubscriptionStateInternal::UpdateSkipTime
0xfe88  pop
0xfe89  ldarg.0
0xfe8a  ldflda   valuetype [mscorlib]System.DateTime System.Deployment.Application.SubscriptionStateInternal::UpdateSkipTime
0xfe8f  call     instance string [mscorlib]System.DateTime::ToString()
0xfe94  ldstr    asc_3279C// "\r\n"
0xfe99  call     string [mscorlib]System.String::Concat(string, string, string)
0xfe9e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xfea3  pop
0xfea4  ldloc.0
0xfea5  ldstr    aUpdateskippedd_0// "UpdateSkippedDeployment="
0xfeaa  ldarg.0
0xfeab  ldfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionStateInternal::UpdateSkippedDeployment
0xfeb0  brtrue.s loc_FEB9
0xfeb2  ldstr    aNull// "null"
0xfeb7  br.s     loc_FEC4
0xfeb9  ldarg.0
0xfeba  ldfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionStateInternal::UpdateSkippedDeployment
0xfebf  callvirt instance string [mscorlib]System.Object::ToString()
0xfec4  ldstr    asc_3279C// "\r\n"
0xfec9  call     string [mscorlib]System.String::Concat(string, string, string)
0xfece  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xfed3  pop
0xfed4  ldloc.0
0xfed5  ldstr    aApptype_0// "appType="
0xfeda  ldarg.0
0xfedb  ldfld    valuetype System.Deployment.Application.AppType System.Deployment.Application.SubscriptionStateInternal::appType
0xfee0  conv.u2
0xfee1  stloc.1
0xfee2  ldloca.s 1
0xfee4  call     instance string [mscorlib]System.UInt16::ToString()
0xfee9  ldstr    asc_3279C// "\r\n"
0xfeee  call     string [mscorlib]System.String::Concat(string, string, string)
0xfef3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xfef8  pop
0xfef9  ldloc.0
0xfefa  callvirt instance string [mscorlib]System.Object::ToString()
0xfeff  ret
```
