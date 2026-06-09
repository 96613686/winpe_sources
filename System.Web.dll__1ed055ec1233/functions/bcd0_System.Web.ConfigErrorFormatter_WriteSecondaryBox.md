# System.Web.ConfigErrorFormatter::WriteSecondaryBox

- ea: `0xbcd0`
- end: `0xbd4d`
- name: `System.Web.ConfigErrorFormatter::WriteSecondaryBox`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x9ec0`
- `0xa100`
- `0xa270`
- `0xbcd0`
- `0xbd50`
- `0x34fa0`

## string_xrefs

- `0xbd08`: `additionalConfigErrorInfo`
- `0xbd10`: `AdditionalConfigErrorInfo`

## pseudocode

```c

```

## disassembly

```asm
0xbcd0  ldarg.0
0xbcd1  ldfld    class [mscorlib]System.Exception System.Web.ConfigErrorFormatter::_e
0xbcd6  castclass [System]System.Configuration.ConfigurationException
0xbcdb  call     class System.Web.ErrorFormatter System.Web.ConfigErrorFormatter::GetFormatterForInnerException(class [mscorlib]System.Exception e)
0xbce0  stloc.0
0xbce1  ldloc.0
0xbce2  brfalse.s loc_BCEC
0xbce4  ldarg.0
0xbce5  ldfld    bool System.Web.ErrorFormatter::_fusionLogWritten
0xbcea  brfalse.s loc_BCF5
0xbcec  ldarg.0
0xbced  ldarg.1
0xbcee  ldarg.2
0xbcef  call     instance void System.Web.ErrorFormatter::WriteSecondaryBox(class [mscorlib]System.Text.StringBuilder sb, bool dontShowSensitiveInfo)
0xbcf4  ret
0xbcf5  ldarg.1
0xbcf6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbcfb  ldstr    aBrDivClassExpa// "<br><div class=\"expandable\" onclick="...
0xbd00  ldc.i4.2
0xbd01  newarr   [mscorlib]System.Object
0xbd06  dup
0xbd07  ldc.i4.0
0xbd08  ldstr    aAdditionalconf_0// "additionalConfigErrorInfo"
0xbd0d  stelem.ref
0xbd0e  dup
0xbd0f  ldc.i4.1
0xbd10  ldstr    aAdditionalconf_1// "AdditionalConfigErrorInfo"
0xbd15  call     string System.Web.SR::GetString(string name)
0xbd1a  stelem.ref
0xbd1b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbd20  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xbd25  pop
0xbd26  ldloc.0
0xbd27  callvirt instance void System.Web.ErrorFormatter::PrepareFormatter()
0xbd2c  ldloc.0
0xbd2d  ldarg.1
0xbd2e  ldarg.2
0xbd2f  callvirt instance void System.Web.ErrorFormatter::WriteErrorDetails(class [mscorlib]System.Text.StringBuilder sb, bool dontShowSensitiveInfo)
0xbd34  ldarg.1
0xbd35  ldstr    aDiv// "            \r\n\r\n</div>\r\n"
0xbd3a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xbd3f  pop
0xbd40  ldarg.1
0xbd41  ldstr    aScriptTypeText// "\r\n        <script type=\"text/javascr"...
0xbd46  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xbd4b  pop
0xbd4c  ret
```
