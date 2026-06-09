# Microsoft.VisualStudio.Setup.Extension.ExtensionsHelper::.cctor

- ea: `0x37310`
- end: `0x3752e`
- name: `Microsoft.VisualStudio.Setup.Extension.ExtensionsHelper::.cctor`
- size: `542`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, installer_update, broker_com_uri`

## string_xrefs

- `0x37320`: `Microsoft.VisualStudio.Community`
- `0x3731b`: `Microsoft.VisualStudio.Product.Community`
- `0x373aa`: `community`
- `0x373b7`: `microsoft.visualstudio.community`
- `0x373c4`: `microsoft.visualstudio.communityx86`

## pseudocode

```c

```

## disassembly

```asm
0x37310  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x37315  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x3731a  dup
0x3731b  ldstr    aMicrosoftVisua_31// "Microsoft.VisualStudio.Product.Communit"...
0x37320  ldstr    aMicrosoftVisua_7// "Microsoft.VisualStudio.Community"
0x37325  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x3732a  dup
0x3732b  ldstr    aMicrosoftVisua_32// "Microsoft.VisualStudio.Product.Professi"...
0x37330  ldstr    aMicrosoftVisua_33// "Microsoft.VisualStudio.Professional"
0x37335  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x3733a  dup
0x3733b  ldstr    aMicrosoftVisua_34// "Microsoft.VisualStudio.Product.Enterpri"...
0x37340  ldstr    aMicrosoftVisua_35// "Microsoft.VisualStudio.Enterprise"
0x37345  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x3734a  dup
0x3734b  ldstr    aMicrosoftVisua_36// "Microsoft.VisualStudio.Product.SQL"
0x37350  ldstr    aMicrosoftVisua_37// "Microsoft.VisualStudio.SQL"
0x37355  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x3735a  dup
0x3735b  ldstr    aMicrosoftVisua_38// "Microsoft.VisualStudio.Product.TeamExpl"...
0x37360  ldstr    aMicrosoftVisua_39// "Microsoft.VisualStudio.TeamExplorer"
0x37365  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x3736a  dup
0x3736b  ldstr    aMicrosoftVisua_40// "Microsoft.VisualStudio.Product.WDExpres"...
0x37370  ldstr    aMicrosoftVisua_41// "Microsoft.VisualStudio.VSWinDesktopExpr"...
0x37375  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x3737a  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.VisualStudio.Setup.Extension.ExtensionsHelper::productIdToTargetMapping
0x3737f  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x37384  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x37389  dup
0x3738a  ldstr    aIntegrated// "integrated"
0x3738f  ldc.i4   0x3FE
0x37394  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x37399  dup
0x3739a  ldstr    aMicrosoftVisua_42// "microsoft.visualstudio.integratedshell"
0x3739f  ldc.i4   0x3FE
0x373a4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x373a9  dup
0x373aa  ldstr    aCommunity// "community"
0x373af  ldc.i4.s 0x3E
0x373b1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x373b6  dup
0x373b7  ldstr    aMicrosoftVisua_43// "microsoft.visualstudio.community"
0x373bc  ldc.i4.s 0x3E
0x373be  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x373c3  dup
0x373c4  ldstr    aMicrosoftVisua_44// "microsoft.visualstudio.communityx86"
0x373c9  ldc.i4.s 0x3E
0x373cb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x373d0  dup
0x373d1  ldstr    aPro// "pro"
0x373d6  ldc.i4.s 0x1E
0x373d8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x373dd  dup
0x373de  ldstr    aProfessional// "professional"
0x373e3  ldc.i4.s 0x1E
0x373e5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x373ea  dup
0x373eb  ldstr    aMicrosoftVisua_45// "microsoft.visualstudio.pro"
0x373f0  ldc.i4.s 0x1E
0x373f2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x373f7  dup
0x373f8  ldstr    aMicrosoftVisua_46// "microsoft.visualstudio.professional"
0x373fd  ldc.i4.s 0x1E
0x373ff  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x37404  dup
0x37405  ldstr    aMicrosoftVisua_47// "microsoft.visualstudio.professionalx86"
0x3740a  ldc.i4.s 0x1E
0x3740c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x37411  dup
0x37412  ldstr    aPremium// "premium"
0x37417  ldc.i4.s 0xE
0x37419  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x3741e  dup
0x3741f  ldstr    aMicrosoftVisua_48// "microsoft.visualstudio.premium"
0x37424  ldc.i4.s 0xE
0x37426  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x3742b  dup
0x3742c  ldstr    aEnterprise// "enterprise"
0x37431  ldc.i4.2
0x37432  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x37437  dup
0x37438  ldstr    aMicrosoftVisua_49// "microsoft.visualstudio.enterprise"
0x3743d  ldc.i4.2
0x3743e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x37443  dup
0x37444  ldstr    aMicrosoftVisua_50// "microsoft.visualstudio.enterprisex86"
0x37449  ldc.i4.2
0x3744a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x3744f  dup
0x37450  ldstr    aWindesktop// "windesktop"
0x37455  ldc.i4.1
0x37456  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x3745b  dup
0x3745c  ldstr    aWindesktopexpr// "windesktopexpress"
0x37461  ldc.i4.1
0x37462  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x37467  dup
0x37468  ldstr    aVswindesktopex// "vswindesktopexpress"
0x3746d  ldc.i4.1
0x3746e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x37473  dup
0x37474  ldstr    aMicrosoftVisua_51// "microsoft.visualstudio.vswindesktopexpr"...
0x37479  ldc.i4.1
0x3747a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x3747f  dup
0x37480  ldstr    aExpressAll// "express_all"
0x37485  ldc.i4.1
0x37486  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x3748b  dup
0x3748c  ldstr    aMicrosoftVisua_52// "microsoft.visualstudio.express_all"
0x37491  ldc.i4.1
0x37492  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x37497  dup
0x37498  ldstr    aVsls// "vsls"
0x3749d  ldc.i4.s 0x7E
0x3749f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x374a4  dup
0x374a5  ldstr    aMicrosoftVisua_53// "microsoft.visualstudio.vsls"
0x374aa  ldc.i4.s 0x7E
0x374ac  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x374b1  dup
0x374b2  ldstr    aUltimate// "ultimate"
0x374b7  ldc.i4.6
0x374b8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x374bd  dup
0x374be  ldstr    aMicrosoftVisua_54// "microsoft.visualstudio.ultimate"
0x374c3  ldc.i4.6
0x374c4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x374c9  dup
0x374ca  ldstr    aMicrosoftVisua_55// "microsoft.visualstudio.teamexplorer"
0x374cf  ldc.i4   0x80
0x374d4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x374d9  dup
0x374da  ldstr    aMicrosoftVisua_56// "microsoft.visualstudio.sql"
0x374df  ldc.i4   0x100
0x374e4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget>::set_Item(var<u1>, !!T0)
0x374e9  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype Microsoft.VisualStudio.Setup.Extension.VSExtensionTarget> Microsoft.VisualStudio.Setup.Extension.ExtensionsHelper::targetIdToSkuMapping
0x374ee  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x374f3  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x374f8  dup
0x374f9  ldstr    aX86// "x86"
0x374fe  ldstr    aX86// "x86"
0x37503  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x37508  dup
0x37509  ldstr    aX64// "x64"
0x3750e  ldstr    aAmd64// "amd64"
0x37513  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x37518  dup
0x37519  ldstr    aArm64_0// "arm64"
0x3751e  ldstr    aArm64_0// "arm64"
0x37523  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x37528  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.VisualStudio.Setup.Extension.ExtensionsHelper::productArchMapping
0x3752d  ret
```
