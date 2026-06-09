# Microsoft.VisualStudio.Setup.Utility.MicrosoftUpdateUtilities::ReadFromRegistry

- ea: `0x282f0`
- end: `0x283aa`
- name: `Microsoft.VisualStudio.Setup.Utility.MicrosoftUpdateUtilities::ReadFromRegistry`
- size: `186`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x282b0`
- `0x282d0`

## callees

- `0x282f0`
- `0x289d0`

## string_xrefs

- `0x28314`: `Detected '{0}' in the {1} registry value in {2}.`
- `0x28360`: `Error reading registry key '`
- `0x28391`: ` registry value in list of known places.`

## pseudocode

```c

```

## disassembly

```asm
0x282f0  ldarg.0
0x282f1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x282f6  stloc.0
0x282f7  br.s     loc_28342
0x282f9  ldloc.0
0x282fa  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x282ff  stloc.1
0x28300  ldarg.1
0x28301  ldloc.1
0x28302  ldsfld   string Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::AllowMUUpdateServiceEnabledRegValue
0x28307  ldloca.s 2
0x28309  call     bool Microsoft.VisualStudio.Setup.Utility.RegistryUtility::TryGetRegValue(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry registry, string regKey, string regValue, [out] object& dataValue)
0x2830e  brfalse.s loc_28342
0x28310  ldarg.2
0x28311  brfalse.s loc_2832F
0x28313  ldarg.2
0x28314  ldstr    aDetected0InThe// "Detected '{0}' in the {1} registry valu"...
0x28319  ldloc.2
0x2831a  ldsfld   string Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::AllowMUUpdateServiceEnabledRegValue
0x2831f  ldloc.1
0x28320  call     string [mscorlib]System.String::Format(string, object, object, object)
0x28325  call     T0x2B000003
0x2832a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2832f  ldloc.2
0x28330  callvirt instance string [mscorlib]System.Object::ToString()
0x28335  ldloca.s 3
0x28337  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x2833c  pop
0x2833d  ldloc.3
0x2833e  stloc.s  4
0x28340  leave.s  loc_283A7
0x28342  ldloc.0
0x28343  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x28348  brtrue.s loc_282F9
0x2834a  leave.s  loc_28356
0x2834c  ldloc.0
0x2834d  brfalse.s loc_28355
0x2834f  ldloc.0
0x28350  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x28355  endfinally
0x28356  leave.s  loc_28383
0x28358  stloc.s  5
0x2835a  ldarg.2
0x2835b  brfalse.s loc_2837E
0x2835d  ldarg.2
0x2835e  ldloc.s  5
0x28360  ldstr    aErrorReadingRe// "Error reading registry key '"
0x28365  ldsfld   string Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::AllowMUUpdateServiceEnabledRegValue
0x2836a  ldstr    asc_7FEB6// "'"
0x2836f  call     string [mscorlib]System.String::Concat(string, string, string)
0x28374  call     T0x2B000003
0x28379  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x2837e  ldc.i4.0
0x2837f  stloc.s  4
0x28381  leave.s  loc_283A7
0x28383  ldarg.2
0x28384  brfalse.s loc_283A5
0x28386  ldarg.2
0x28387  ldstr    aCouldNotFind// "Could not find "
0x2838c  ldsfld   string Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::AllowMUUpdateServiceEnabledRegValue
0x28391  ldstr    aRegistryValueI// " registry value in list of known places"...
0x28396  call     string [mscorlib]System.String::Concat(string, string, string)
0x2839b  call     T0x2B000003
0x283a0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x283a5  ldc.i4.0
0x283a6  ret
0x283a7  ldloc.s  4
0x283a9  ret
```
