# Microsoft.VisualStudio.Setup.Planner::.cctor

- ea: `0x189f0`
- end: `0x18ae9`
- name: `Microsoft.VisualStudio.Setup.Planner::.cctor`
- size: `249`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## string_xrefs

- `0x18a07`: `Microsoft.CodeAnalysis.Compilers`
- `0x18a2b`: `Microsoft.VisualStudio.Community`
- `0x18a37`: `Microsoft.VisualStudio.Community.Resources`
- `0x18a43`: `Microsoft.VisualStudio.Community.x64`
- `0x18a4f`: `Microsoft.VisualStudio.Community.x86`
- `0x18aa3`: `Microsoft.VisualStudio.VC.Templates.Pro`
- `0x18acb`: `Microsoft.VisualStudio.Setup.Configuration`

## pseudocode

```c

```

## disassembly

```asm
0x189f0  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x189f5  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x189fa  dup
0x189fb  ldstr    aMicrosoftBuild// "Microsoft.Build"
0x18a00  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x18a05  pop
0x18a06  dup
0x18a07  ldstr    aMicrosoftCodea// "Microsoft.CodeAnalysis.Compilers"
0x18a0c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x18a11  pop
0x18a12  dup
0x18a13  ldstr    aMicrosoftVisua_5// "Microsoft.VisualC.ClangC2"
0x18a18  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x18a1d  pop
0x18a1e  dup
0x18a1f  ldstr    aMicrosoftVisua_6// "Microsoft.VisualStudio.VC.MSBuild.Base"
0x18a24  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x18a29  pop
0x18a2a  dup
0x18a2b  ldstr    aMicrosoftVisua_7// "Microsoft.VisualStudio.Community"
0x18a30  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x18a35  pop
0x18a36  dup
0x18a37  ldstr    aMicrosoftVisua_8// "Microsoft.VisualStudio.Community.Resour"...
0x18a3c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x18a41  pop
0x18a42  dup
0x18a43  ldstr    aMicrosoftVisua_9// "Microsoft.VisualStudio.Community.x64"
0x18a48  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x18a4d  pop
0x18a4e  dup
0x18a4f  ldstr    aMicrosoftVisua_10// "Microsoft.VisualStudio.Community.x86"
0x18a54  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x18a59  pop
0x18a5a  dup
0x18a5b  ldstr    aMicrosoftVisua_11// "Microsoft.VisualStudio.TestTools.TestPl"...
0x18a60  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x18a65  pop
0x18a66  dup
0x18a67  ldstr    aMicrosoftVisua_12// "Microsoft.VisualStudio.TestTools.TestPl"...
0x18a6c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x18a71  pop
0x18a72  dup
0x18a73  ldstr    aMicrosoftVisua_13// "Microsoft.VisualStudio.VC.Ide.Android"
0x18a78  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x18a7d  pop
0x18a7e  dup
0x18a7f  ldstr    aMicrosoftVisua_14// "Microsoft.VisualStudio.VC.Ide.ATL"
0x18a84  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x18a89  pop
0x18a8a  dup
0x18a8b  ldstr    aMicrosoftVisua_15// "Microsoft.VisualStudio.VC.Ide.iOS"
0x18a90  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x18a95  pop
0x18a96  dup
0x18a97  ldstr    aMicrosoftVisua_16// "Microsoft.VisualStudio.VC.Ide.Pro"
0x18a9c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x18aa1  pop
0x18aa2  dup
0x18aa3  ldstr    aMicrosoftVisua_17// "Microsoft.VisualStudio.VC.Templates.Pro"
0x18aa8  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x18aad  pop
0x18aae  dup
0x18aaf  ldstr    aMicrosoftVisua_18// "Microsoft.VisualStudio.WebProject.Resou"...
0x18ab4  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x18ab9  pop
0x18aba  dup
0x18abb  ldstr    aMicrosoftVisua_19// "Microsoft.VisualStudio.WebProject"
0x18ac0  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x18ac5  pop
0x18ac6  stsfld   class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Planner::PackagesWithDuplicateFiles
0x18acb  ldstr    aMicrosoftVisua_20// "Microsoft.VisualStudio.Setup.Configurat"...
0x18ad0  stsfld   string Microsoft.VisualStudio.Setup.Planner::ConfigurationPackageId
0x18ad5  ldc.r8   20.0
0x18ade  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x18ae3  stsfld   valuetype [mscorlib]System.TimeSpan Microsoft.VisualStudio.Setup.Planner::DefaultDownloadMessageBusRateLimit
0x18ae8  ret
```
