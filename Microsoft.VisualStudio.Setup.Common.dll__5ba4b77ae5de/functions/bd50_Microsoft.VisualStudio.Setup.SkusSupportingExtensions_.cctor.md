# Microsoft.VisualStudio.Setup.SkusSupportingExtensions::.cctor

- ea: `0xbd50`
- end: `0xbdcc`
- name: `Microsoft.VisualStudio.Setup.SkusSupportingExtensions::.cctor`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, installer_update, broker_com_uri`

## string_xrefs

- `0xbd67`: `Microsoft.VisualStudio.Product.Community`

## pseudocode

```c

```

## disassembly

```asm
0xbd50  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xbd55  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0xbd5a  dup
0xbd5b  ldstr    aMicrosoftVisua_0// "Microsoft.VisualStudio.Product.Client64"
0xbd60  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xbd65  pop
0xbd66  dup
0xbd67  ldstr    aMicrosoftVisua_1// "Microsoft.VisualStudio.Product.Communit"...
0xbd6c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xbd71  pop
0xbd72  dup
0xbd73  ldstr    aMicrosoftVisua_2// "Microsoft.VisualStudio.Product.Enterpri"...
0xbd78  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xbd7d  pop
0xbd7e  dup
0xbd7f  ldstr    aMicrosoftVisua_3// "Microsoft.VisualStudio.Product.Professi"...
0xbd84  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xbd89  pop
0xbd8a  dup
0xbd8b  ldstr    aMicrosoftVisua_4// "Microsoft.VisualStudio.Product.Server32"
0xbd90  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xbd95  pop
0xbd96  dup
0xbd97  ldstr    aMicrosoftVisua_5// "Microsoft.VisualStudio.Product.Server64"
0xbd9c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xbda1  pop
0xbda2  dup
0xbda3  ldstr    aMicrosoftVisua_6// "Microsoft.VisualStudio.Product.SQL"
0xbda8  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xbdad  pop
0xbdae  dup
0xbdaf  ldstr    aMicrosoftVisua_7// "Microsoft.VisualStudio.Product.WDExpres"...
0xbdb4  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xbdb9  pop
0xbdba  dup
0xbdbb  ldstr    aMicrosoftVisua_8// "Microsoft.VisualStudio.Product.TeamExpl"...
0xbdc0  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xbdc5  pop
0xbdc6  stsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.VisualStudio.Setup.SkusSupportingExtensions::List
0xbdcb  ret
```
