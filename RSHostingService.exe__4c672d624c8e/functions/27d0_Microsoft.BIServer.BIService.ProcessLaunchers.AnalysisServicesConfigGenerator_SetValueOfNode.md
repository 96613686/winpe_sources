# Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::SetValueOfNode

- ea: `0x27d0`
- end: `0x2843`
- name: `Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::SetValueOfNode`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x26c0`

## callees

- `0x27d0`
- `0x3c60`

## pseudocode

```c

```

## disassembly

```asm
0x27d0  ldarg.2
0x27d1  ldc.i4.1
0x27d2  newarr   [mscorlib]System.Char
0x27d7  dup
0x27d8  ldc.i4.0
0x27d9  ldc.i4.s 0x2F
0x27db  stelem.i2
0x27dc  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x27e1  ldarg.1
0x27e2  stloc.0
0x27e3  stloc.1
0x27e4  ldc.i4.0
0x27e5  stloc.2
0x27e6  br.s     loc_2835
0x27e8  newobj   instance void <>c__DisplayClass6_0::.ctor()
0x27ed  stloc.3
0x27ee  ldloc.3
0x27ef  ldloc.1
0x27f0  ldloc.2
0x27f1  ldelem.ref
0x27f2  stfld    string <>c__DisplayClass6_0::nodeName
0x27f7  ldloc.0
0x27f8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Elements()
0x27fd  ldloc.3
0x27fe  ldftn    instance bool <>c__DisplayClass6_0::<SetValueOfNode>b__0(class [System.Xml.Linq]System.Xml.Linq.XElement p)
0x2804  newobj   instance void class [mscorlib]System.Func`2<class [System.Xml.Linq]System.Xml.Linq.XElement, bool>::.ctor(object, native int)
0x2809  call     T0x2B00001C
0x280e  stloc.s  4
0x2810  ldloc.s  4
0x2812  brtrue.s loc_282E
0x2814  ldloc.3
0x2815  ldfld    string <>c__DisplayClass6_0::nodeName
0x281a  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::Get(string)
0x281f  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XElement::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName)
0x2824  stloc.s  4
0x2826  ldloc.0
0x2827  ldloc.s  4
0x2829  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XContainer::Add(object)
0x282e  ldloc.s  4
0x2830  stloc.0
0x2831  ldloc.2
0x2832  ldc.i4.1
0x2833  add
0x2834  stloc.2
0x2835  ldloc.2
0x2836  ldloc.1
0x2837  ldlen
0x2838  conv.i4
0x2839  blt.s    loc_27E8
0x283b  ldloc.0
0x283c  ldarg.3
0x283d  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XElement::set_Value(string)
0x2842  ret
```
