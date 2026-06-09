# FunctionInfo`1::CheckArity

- ea: `0x57050`
- end: `0x570b4`
- name: `FunctionInfo`1::CheckArity`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x286e0`
- `0x57050`

## string_xrefs

- `0x5705d`: `XPath_NArgsExpected`
- `0x5706b`: `XPath_NOrMArgsExpected`
- `0x57077`: `XPath_AtLeastNArgsExpected`
- `0x5707f`: `XPath_AtMostMArgsExpected`

## pseudocode

```c

```

## disassembly

```asm
0x57050  ldarg.0
0x57051  ldarg.3
0x57052  bgt.s    loc_57059
0x57054  ldarg.3
0x57055  ldarg.1
0x57056  bgt.s    loc_57059
0x57058  ret
0x57059  ldarg.0
0x5705a  ldarg.1
0x5705b  bne.un.s loc_57065
0x5705d  ldstr    aXpathNargsexpe// "XPath_NArgsExpected"
0x57062  stloc.0
0x57063  br.s     loc_57085
0x57065  ldarg.1
0x57066  ldarg.0
0x57067  ldc.i4.1
0x57068  add
0x57069  bne.un.s loc_57073
0x5706b  ldstr    aXpathNormargse// "XPath_NOrMArgsExpected"
0x57070  stloc.0
0x57071  br.s     loc_57085
0x57073  ldarg.3
0x57074  ldarg.0
0x57075  bge.s    loc_5707F
0x57077  ldstr    aXpathAtleastna// "XPath_AtLeastNArgsExpected"
0x5707c  stloc.0
0x5707d  br.s     loc_57085
0x5707f  ldstr    aXpathAtmostmar// "XPath_AtMostMArgsExpected"
0x57084  stloc.0
0x57085  ldloc.0
0x57086  ldc.i4.3
0x57087  newarr   [mscorlib]System.String
0x5708c  dup
0x5708d  ldc.i4.0
0x5708e  ldarg.2
0x5708f  stelem.ref
0x57090  dup
0x57091  ldc.i4.1
0x57092  ldarga.s 0
0x57094  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x57099  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x5709e  stelem.ref
0x5709f  dup
0x570a0  ldc.i4.2
0x570a1  ldarga.s 1
0x570a3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x570a8  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x570ad  stelem.ref
0x570ae  newobj   instance void System.Xml.Xsl.XPath.XPathCompileException::.ctor(string resId, string[] args)
0x570b3  throw
```
