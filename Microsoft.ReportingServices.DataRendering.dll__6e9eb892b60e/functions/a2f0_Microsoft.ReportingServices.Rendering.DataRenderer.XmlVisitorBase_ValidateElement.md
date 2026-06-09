# Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::ValidateElement

- ea: `0xa2f0`
- end: `0xa399`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::ValidateElement`
- size: `169`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xab80`
- `0xb340`
- `0xb3f0`

## callees

- `0xa2f0`

## pseudocode

```c

```

## disassembly

```asm
0xa2f0  ldarg.0
0xa2f1  ldfld    class Scope Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_currentScope
0xa2f6  ldfld    class [mscorlib]System.Collections.Hashtable Scope::Elements
0xa2fb  ldarg.1
0xa2fc  ldind.ref
0xa2fd  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0xa302  brfalse.s loc_A380
0xa304  ldarg.0
0xa305  ldfld    class Scope Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_currentScope
0xa30a  ldfld    class [mscorlib]System.Collections.Hashtable Scope::Elements
0xa30f  ldarg.1
0xa310  ldind.ref
0xa311  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xa316  unbox.any [mscorlib]System.Int32
0xa31b  stloc.0
0xa31c  ldloc.0
0xa31d  ldc.i4.1
0xa31e  add
0xa31f  stloc.0
0xa320  ldarg.0
0xa321  ldfld    class Scope Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_currentScope
0xa326  ldfld    class [mscorlib]System.Collections.Hashtable Scope::Elements
0xa32b  ldarg.1
0xa32c  ldind.ref
0xa32d  ldloc.0
0xa32e  box      [mscorlib]System.Int32
0xa333  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0xa338  ldarg.1
0xa339  ldind.ref
0xa33a  ldstr    asc_EEAC// "_"
0xa33f  ldloca.s 0
0xa341  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa346  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xa34b  call     string [mscorlib]System.String::Concat(string, string, string)
0xa350  stloc.1
0xa351  ldarg.0
0xa352  ldfld    class Scope Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_currentScope
0xa357  ldfld    class [mscorlib]System.Collections.Hashtable Scope::Elements
0xa35c  ldloc.1
0xa35d  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0xa362  brtrue.s loc_A31C
0xa364  ldarg.1
0xa365  ldloc.1
0xa366  stind.ref
0xa367  ldarg.0
0xa368  ldfld    class Scope Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_currentScope
0xa36d  ldfld    class [mscorlib]System.Collections.Hashtable Scope::Elements
0xa372  ldarg.1
0xa373  ldind.ref
0xa374  ldc.i4.0
0xa375  box      [mscorlib]System.Int32
0xa37a  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xa37f  ret
0xa380  ldarg.0
0xa381  ldfld    class Scope Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_currentScope
0xa386  ldfld    class [mscorlib]System.Collections.Hashtable Scope::Elements
0xa38b  ldarg.1
0xa38c  ldind.ref
0xa38d  ldc.i4.0
0xa38e  box      [mscorlib]System.Int32
0xa393  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xa398  ret
```
