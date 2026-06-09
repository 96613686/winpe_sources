# Microsoft.Reporting.WebForms.EmbeddedResourceOperation::LoadScriptFiles

- ea: `0x9110`
- end: `0x92e7`
- name: `Microsoft.Reporting.WebForms.EmbeddedResourceOperation::LoadScriptFiles`
- size: `471`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x90d0`

## callees

- `0x9020`
- `0x9880`

## string_xrefs

- `0x9112`: `Microsoft.Reporting.WebForms.Scripts.Common.js`
- `0x928d`: `Common.js`

## pseudocode

```c

```

## disassembly

```asm
0x9110  ldarg.1
0x9111  ldarg.0
0x9112  ldstr    aMicrosoftRepor_12// "Microsoft.Reporting.WebForms.Scripts.Co"...
0x9117  ldloca.s 0
0x9119  callvirt instance unsigned int8[] Microsoft.Reporting.WebForms.EmbeddedResourceOperation::GetResource(string resourceName, [out] string& mimeType)
0x911e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int8>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x9123  ldarg.1
0x9124  ldarg.0
0x9125  ldstr    aMicrosoftRepor_13// "Microsoft.Reporting.WebForms.Scripts.To"...
0x912a  ldloca.s 0
0x912c  callvirt instance unsigned int8[] Microsoft.Reporting.WebForms.EmbeddedResourceOperation::GetResource(string resourceName, [out] string& mimeType)
0x9131  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int8>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x9136  ldarg.1
0x9137  ldarg.0
0x9138  ldstr    aMicrosoftRepor_14// "Microsoft.Reporting.WebForms.Scripts.Ho"...
0x913d  ldloca.s 0
0x913f  callvirt instance unsigned int8[] Microsoft.Reporting.WebForms.EmbeddedResourceOperation::GetResource(string resourceName, [out] string& mimeType)
0x9144  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int8>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x9149  ldarg.1
0x914a  ldarg.0
0x914b  ldstr    aMicrosoftRepor_15// "Microsoft.Reporting.WebForms.Scripts.St"...
0x9150  ldloca.s 0
0x9152  callvirt instance unsigned int8[] Microsoft.Reporting.WebForms.EmbeddedResourceOperation::GetResource(string resourceName, [out] string& mimeType)
0x9157  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int8>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x915c  ldarg.1
0x915d  ldarg.0
0x915e  ldstr    aMicrosoftRepor_16// "Microsoft.Reporting.WebForms.Scripts.In"...
0x9163  ldloca.s 0
0x9165  callvirt instance unsigned int8[] Microsoft.Reporting.WebForms.EmbeddedResourceOperation::GetResource(string resourceName, [out] string& mimeType)
0x916a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int8>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x916f  ldarg.1
0x9170  ldarg.0
0x9171  ldstr    aMicrosoftRepor_17// "Microsoft.Reporting.WebForms.Scripts.Pa"...
0x9176  ldloca.s 0
0x9178  callvirt instance unsigned int8[] Microsoft.Reporting.WebForms.EmbeddedResourceOperation::GetResource(string resourceName, [out] string& mimeType)
0x917d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int8>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x9182  ldarg.1
0x9183  ldarg.0
0x9184  ldstr    aMicrosoftRepor_18// "Microsoft.Reporting.WebForms.Scripts.Pr"...
0x9189  ldloca.s 0
0x918b  callvirt instance unsigned int8[] Microsoft.Reporting.WebForms.EmbeddedResourceOperation::GetResource(string resourceName, [out] string& mimeType)
0x9190  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int8>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x9195  ldarg.1
0x9196  ldarg.0
0x9197  ldstr    aMicrosoftRepor_19// "Microsoft.Reporting.WebForms.Scripts.Re"...
0x919c  ldloca.s 0
0x919e  callvirt instance unsigned int8[] Microsoft.Reporting.WebForms.EmbeddedResourceOperation::GetResource(string resourceName, [out] string& mimeType)
0x91a3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int8>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x91a8  ldarg.1
0x91a9  ldarg.0
0x91aa  ldstr    aMicrosoftRepor_20// "Microsoft.Reporting.WebForms.Scripts.Re"...
0x91af  ldloca.s 0
0x91b1  callvirt instance unsigned int8[] Microsoft.Reporting.WebForms.EmbeddedResourceOperation::GetResource(string resourceName, [out] string& mimeType)
0x91b6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int8>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x91bb  ldarg.1
0x91bc  ldarg.0
0x91bd  ldstr    aMicrosoftRepor_21// "Microsoft.Reporting.WebForms.Scripts.Se"...
0x91c2  ldloca.s 0
0x91c4  callvirt instance unsigned int8[] Microsoft.Reporting.WebForms.EmbeddedResourceOperation::GetResource(string resourceName, [out] string& mimeType)
0x91c9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int8>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x91ce  ldarg.1
0x91cf  ldarg.0
0x91d0  ldstr    aMicrosoftRepor_22// "Microsoft.Reporting.WebForms.Scripts.Sc"...
0x91d5  ldloca.s 0
0x91d7  callvirt instance unsigned int8[] Microsoft.Reporting.WebForms.EmbeddedResourceOperation::GetResource(string resourceName, [out] string& mimeType)
0x91dc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int8>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x91e1  ldarg.1
0x91e2  ldarg.0
0x91e3  ldstr    aMicrosoftRepor_23// "Microsoft.Reporting.WebForms.Scripts.Sc"...
0x91e8  ldloca.s 0
0x91ea  callvirt instance unsigned int8[] Microsoft.Reporting.WebForms.EmbeddedResourceOperation::GetResource(string resourceName, [out] string& mimeType)
0x91ef  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int8>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x91f4  ldarg.1
0x91f5  ldarg.0
0x91f6  ldstr    aMicrosoftRepor_24// "Microsoft.Reporting.WebForms.Scripts.Te"...
0x91fb  ldloca.s 0
0x91fd  callvirt instance unsigned int8[] Microsoft.Reporting.WebForms.EmbeddedResourceOperation::GetResource(string resourceName, [out] string& mimeType)
0x9202  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int8>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x9207  ldarg.1
0x9208  ldarg.0
0x9209  ldstr    aMicrosoftRepor_25// "Microsoft.Reporting.WebForms.Scripts.To"...
0x920e  ldloca.s 0
0x9210  callvirt instance unsigned int8[] Microsoft.Reporting.WebForms.EmbeddedResourceOperation::GetResource(string resourceName, [out] string& mimeType)
0x9215  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int8>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x921a  ldarg.1
0x921b  ldarg.0
0x921c  ldstr    aMicrosoftRepor_26// "Microsoft.Reporting.WebForms.Scripts.Re"...
0x9221  ldloca.s 0
0x9223  callvirt instance unsigned int8[] Microsoft.Reporting.WebForms.EmbeddedResourceOperation::GetResource(string resourceName, [out] string& mimeType)
0x9228  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int8>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x922d  ldarg.1
0x922e  ldarg.0
0x922f  ldstr    aMicrosoftRepor_27// "Microsoft.Reporting.WebForms.Scripts.To"...
0x9234  ldloca.s 0
0x9236  callvirt instance unsigned int8[] Microsoft.Reporting.WebForms.EmbeddedResourceOperation::GetResource(string resourceName, [out] string& mimeType)
0x923b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int8>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x9240  ldarg.1
0x9241  ldarg.0
0x9242  ldstr    aMicrosoftRepor_28// "Microsoft.Reporting.WebForms.Scripts.Sp"...
0x9247  ldloca.s 0
0x9249  callvirt instance unsigned int8[] Microsoft.Reporting.WebForms.EmbeddedResourceOperation::GetResource(string resourceName, [out] string& mimeType)
0x924e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int8>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x9253  ldarg.1
0x9254  ldarg.0
0x9255  ldstr    aMicrosoftRepor_29// "Microsoft.Reporting.WebForms.Scripts.Re"...
0x925a  ldloca.s 0
0x925c  callvirt instance unsigned int8[] Microsoft.Reporting.WebForms.EmbeddedResourceOperation::GetResource(string resourceName, [out] string& mimeType)
0x9261  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int8>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x9266  ldarg.1
0x9267  ldarg.0
0x9268  ldstr    aMicrosoftRepor_30// "Microsoft.Reporting.WebForms.Scripts.As"...
0x926d  ldloca.s 0
0x926f  callvirt instance unsigned int8[] Microsoft.Reporting.WebForms.EmbeddedResourceOperation::GetResource(string resourceName, [out] string& mimeType)
0x9274  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int8>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x9279  ldarg.1
0x927a  ldarg.0
0x927b  ldstr    aMicrosoftRepor_31// "Microsoft.Reporting.WebForms.Scripts.Do"...
0x9280  ldloca.s 0
0x9282  callvirt instance unsigned int8[] Microsoft.Reporting.WebForms.EmbeddedResourceOperation::GetResource(string resourceName, [out] string& mimeType)
0x9287  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int8>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x928c  ldarg.1
0x928d  ldstr    aCommonJs// "Common.js"
0x9292  ldloca.s 0
0x9294  call     unsigned int8[] Microsoft.Reporting.WebForms.LocalHtmlRenderer::GetResource(string name, [out] string& mimeType)
0x9299  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int8>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x929e  ldarg.1
0x929f  ldstr    aFitproportiona// "FitProportional.js"
0x92a4  ldloca.s 0
0x92a6  call     unsigned int8[] Microsoft.Reporting.WebForms.LocalHtmlRenderer::GetResource(string name, [out] string& mimeType)
0x92ab  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int8>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x92b0  ldarg.1
0x92b1  ldstr    aFixedheaderJs// "FixedHeader.js"
0x92b6  ldloca.s 0
0x92b8  call     unsigned int8[] Microsoft.Reporting.WebForms.LocalHtmlRenderer::GetResource(string name, [out] string& mimeType)
0x92bd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int8>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x92c2  ldarg.1
0x92c3  ldstr    aCangrowfalseJs// "CanGrowFalse.js"
0x92c8  ldloca.s 0
0x92ca  call     unsigned int8[] Microsoft.Reporting.WebForms.LocalHtmlRenderer::GetResource(string name, [out] string& mimeType)
0x92cf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int8>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x92d4  ldarg.1
0x92d5  ldstr    aImageconsolida// "ImageConsolidation.js"
0x92da  ldloca.s 0
0x92dc  call     unsigned int8[] Microsoft.Reporting.WebForms.LocalHtmlRenderer::GetResource(string name, [out] string& mimeType)
0x92e1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int8>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x92e6  ret
```
