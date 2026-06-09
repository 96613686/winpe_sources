# System.Xml.Xsl.Runtime.XsltFunctions::MSStringCompare

- ea: `0x34930`
- end: `0x349ba`
- name: `System.Xml.Xsl.Runtime.XsltFunctions::MSStringCompare`
- size: `138`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3780`
- `0x34930`
- `0x34b60`

## string_xrefs

- `0x3497b`: `Xslt_InvalidCompareOption`

## pseudocode

```c

```

## disassembly

```asm
0x34930  ldarg.2
0x34931  call     class [mscorlib]System.Globalization.CultureInfo System.Xml.Xsl.Runtime.XsltFunctions::GetCultureInfo(string lang)
0x34936  stloc.0
0x34937  ldc.i4.0
0x34938  stloc.1
0x34939  ldc.i4.0
0x3493a  stloc.2
0x3493b  ldc.i4.0
0x3493c  stloc.s  4
0x3493e  br.s     loc_3496B
0x34940  ldarg.3
0x34941  ldloc.s  4
0x34943  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x34948  stloc.s  5
0x3494a  ldloc.s  5
0x3494c  ldc.i4.s 0x69
0x3494e  beq.s    loc_34958
0x34950  ldloc.s  5
0x34952  ldc.i4.s 0x75
0x34954  beq.s    loc_3495D
0x34956  br.s     loc_34961
0x34958  ldc.i4.s 0x19
0x3495a  stloc.1
0x3495b  br.s     loc_34965
0x3495d  ldc.i4.1
0x3495e  stloc.2
0x3495f  br.s     loc_34965
0x34961  ldc.i4.1
0x34962  stloc.2
0x34963  ldc.i4.1
0x34964  stloc.1
0x34965  ldloc.s  4
0x34967  ldc.i4.1
0x34968  add
0x34969  stloc.s  4
0x3496b  ldloc.s  4
0x3496d  ldarg.3
0x3496e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x34973  blt.s    loc_34940
0x34975  ldloc.2
0x34976  brfalse.s loc_34992
0x34978  ldloc.1
0x34979  brfalse.s loc_34990
0x3497b  ldstr    aXsltInvalidcom// "Xslt_InvalidCompareOption"
0x34980  ldc.i4.1
0x34981  newarr   [mscorlib]System.String
0x34986  dup
0x34987  ldc.i4.0
0x34988  ldarg.3
0x34989  stelem.ref
0x3498a  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x3498f  throw
0x34990  ldc.i4.1
0x34991  stloc.1
0x34992  ldloc.0
0x34993  callvirt instance class [mscorlib]System.Globalization.CompareInfo [mscorlib]System.Globalization.CultureInfo::get_CompareInfo()
0x34998  ldarg.0
0x34999  ldarg.1
0x3499a  ldloc.1
0x3499b  callvirt instance int32 [mscorlib]System.Globalization.CompareInfo::Compare(string, string, valuetype [mscorlib]System.Globalization.CompareOptions)
0x349a0  stloc.3
0x349a1  ldloc.2
0x349a2  brfalse.s loc_349B7
0x349a4  ldloc.3
0x349a5  brtrue.s loc_349B7
0x349a7  ldloc.0
0x349a8  callvirt instance class [mscorlib]System.Globalization.CompareInfo [mscorlib]System.Globalization.CultureInfo::get_CompareInfo()
0x349ad  ldarg.0
0x349ae  ldarg.1
0x349af  ldc.i4.0
0x349b0  callvirt instance int32 [mscorlib]System.Globalization.CompareInfo::Compare(string, string, valuetype [mscorlib]System.Globalization.CompareOptions)
0x349b5  neg
0x349b6  stloc.3
0x349b7  ldloc.3
0x349b8  conv.r8
0x349b9  ret
```
