# System.Web.UI.ScriptManager::get_SplitFrameworkScripts

- ea: `0x143f0`
- end: `0x144b4`
- name: `System.Web.UI.ScriptManager::get_SplitFrameworkScripts`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x14ed0`

## callees

- `0x143f0`

## string_xrefs

- `0x14401`: `MicrosoftAjaxComponentModel.js`
- `0x1440d`: `MicrosoftAjaxComponentModel.debug.js`
- `0x14491`: `MicrosoftAjaxWebServices.js`
- `0x1449d`: `MicrosoftAjaxWebServices.debug.js`

## pseudocode

```c

```

## disassembly

```asm
0x143f0  ldsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> System.Web.UI.ScriptManager::_splitFrameworkScript
0x143f5  brtrue   loc_144AE
0x143fa  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x143ff  stloc.0
0x14400  ldloc.0
0x14401  ldstr    aMicrosoftajaxc// "MicrosoftAjaxComponentModel.js"
0x14406  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1440b  pop
0x1440c  ldloc.0
0x1440d  ldstr    aMicrosoftajaxc_0// "MicrosoftAjaxComponentModel.debug.js"
0x14412  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x14417  pop
0x14418  ldloc.0
0x14419  ldstr    aMicrosoftajaxc_1// "MicrosoftAjaxCore.js"
0x1441e  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x14423  pop
0x14424  ldloc.0
0x14425  ldstr    aMicrosoftajaxc_2// "MicrosoftAjaxCore.debug.js"
0x1442a  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1442f  pop
0x14430  ldloc.0
0x14431  ldstr    aMicrosoftajaxg// "MicrosoftAjaxGlobalization.js"
0x14436  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1443b  pop
0x1443c  ldloc.0
0x1443d  ldstr    aMicrosoftajaxg_0// "MicrosoftAjaxGlobalization.debug.js"
0x14442  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x14447  pop
0x14448  ldloc.0
0x14449  ldstr    aMicrosoftajaxh// "MicrosoftAjaxHistory.js"
0x1444e  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x14453  pop
0x14454  ldloc.0
0x14455  ldstr    aMicrosoftajaxh_0// "MicrosoftAjaxHistory.debug.js"
0x1445a  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1445f  pop
0x14460  ldloc.0
0x14461  ldstr    aMicrosoftajaxn// "MicrosoftAjaxNetwork.js"
0x14466  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1446b  pop
0x1446c  ldloc.0
0x1446d  ldstr    aMicrosoftajaxn_0// "MicrosoftAjaxNetwork.debug.js"
0x14472  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x14477  pop
0x14478  ldloc.0
0x14479  ldstr    aMicrosoftajaxs// "MicrosoftAjaxSerialization.js"
0x1447e  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x14483  pop
0x14484  ldloc.0
0x14485  ldstr    aMicrosoftajaxs_0// "MicrosoftAjaxSerialization.debug.js"
0x1448a  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1448f  pop
0x14490  ldloc.0
0x14491  ldstr    aMicrosoftajaxw// "MicrosoftAjaxWebServices.js"
0x14496  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1449b  pop
0x1449c  ldloc.0
0x1449d  ldstr    aMicrosoftajaxw_0// "MicrosoftAjaxWebServices.debug.js"
0x144a2  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x144a7  pop
0x144a8  ldloc.0
0x144a9  stsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> System.Web.UI.ScriptManager::_splitFrameworkScript
0x144ae  ldsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> System.Web.UI.ScriptManager::_splitFrameworkScript
0x144b3  ret
```
