# Microsoft.BIServer.HostingEnvironment.BIServerTelemetryConfiguration::ReadCpeRegKey

- ea: `0x21f0`
- end: `0x2243`
- name: `Microsoft.BIServer.HostingEnvironment.BIServerTelemetryConfiguration::ReadCpeRegKey`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2160`
- `0x2250`

## callees

- `0x21f0`

## pseudocode

```c

```

## disassembly

```asm
0x21f0  ldstr    aSoftwareMicros// "Software\\Microsoft\\Microsoft SQL Serv"...
0x21f5  stloc.0
0x21f6  ldnull
0x21f7  stloc.1
0x21f8  ldnull
0x21f9  stloc.2
0x21fa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x21ff  ldloc.0
0x2200  ldarg.0
0x2201  ldfld    string Microsoft.BIServer.HostingEnvironment.BIServerTelemetryConfiguration::_instanceName
0x2206  ldstr    aCpe// "\\CPE"
0x220b  call     string [mscorlib]System.String::Concat(string, string)
0x2210  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x2215  stloc.3
0x2216  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x221b  ldloc.3
0x221c  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x2221  stloc.2
0x2222  ldloc.2
0x2223  brtrue.s loc_222A
0x2225  ldnull
0x2226  stloc.s  4
0x2228  leave.s  loc_2240
0x222a  ldloc.2
0x222b  ldarg.1
0x222c  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x2231  stloc.1
0x2232  leave.s  loc_223E
0x2234  ldloc.2
0x2235  brfalse.s loc_223D
0x2237  ldloc.2
0x2238  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::Close()
0x223d  endfinally
0x223e  ldloc.1
0x223f  ret
0x2240  ldloc.s  4
0x2242  ret
```
