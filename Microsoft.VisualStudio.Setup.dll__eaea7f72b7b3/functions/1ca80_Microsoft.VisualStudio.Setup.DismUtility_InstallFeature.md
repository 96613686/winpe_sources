# Microsoft.VisualStudio.Setup.DismUtility::InstallFeature

- ea: `0x1ca80`
- end: `0x1cb0f`
- name: `Microsoft.VisualStudio.Setup.DismUtility::InstallFeature`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x6d320`

## callees

- `0x1ca80`
- `0x1cb40`

## string_xrefs

- `0x1ca81`: `windowsFeatureName`
- `0x1cad9`: `/online /quiet /norestart /Enable-Feature /FeatureName:"`
- `0x1caf1`: ` /logPath:"`

## pseudocode

```c

```

## disassembly

```asm
0x1ca80  ldarg.0
0x1ca81  ldstr    aWindowsfeature// "windowsFeatureName"
0x1ca86  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x1ca8b  call     class [mscorlib]System.OperatingSystem [mscorlib]System.Environment::get_OSVersion()
0x1ca90  stloc.0
0x1ca91  ldc.i4.0
0x1ca92  stloc.1
0x1ca93  ldloc.0
0x1ca94  callvirt instance class [mscorlib]System.Version [mscorlib]System.OperatingSystem::get_Version()
0x1ca99  ldnull
0x1ca9a  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x1ca9f  brfalse.s loc_1CAC1
0x1caa1  ldloc.0
0x1caa2  callvirt instance class [mscorlib]System.Version [mscorlib]System.OperatingSystem::get_Version()
0x1caa7  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x1caac  ldc.i4.6
0x1caad  bne.un.s loc_1CABF
0x1caaf  ldloc.0
0x1cab0  callvirt instance class [mscorlib]System.Version [mscorlib]System.OperatingSystem::get_Version()
0x1cab5  callvirt instance int32 [mscorlib]System.Version::get_Minor()
0x1caba  ldc.i4.1
0x1cabb  ceq
0x1cabd  br.s     loc_1CAC0
0x1cabf  ldc.i4.0
0x1cac0  stloc.1
0x1cac1  ldloc.1
0x1cac2  brtrue.s loc_1CACB
0x1cac4  ldstr    aAll// "/All"
0x1cac9  br.s     loc_1CAD0
0x1cacb  ldsfld   string [mscorlib]System.String::Empty
0x1cad0  stloc.2
0x1cad1  ldc.i4.7
0x1cad2  newarr   [mscorlib]System.String
0x1cad7  dup
0x1cad8  ldc.i4.0
0x1cad9  ldstr    aOnlineQuietNor_0// "/online /quiet /norestart /Enable-Featu"...
0x1cade  stelem.ref
0x1cadf  dup
0x1cae0  ldc.i4.1
0x1cae1  ldarg.0
0x1cae2  stelem.ref
0x1cae3  dup
0x1cae4  ldc.i4.2
0x1cae5  ldstr    asc_89CF4// "\" "
0x1caea  stelem.ref
0x1caeb  dup
0x1caec  ldc.i4.3
0x1caed  ldloc.2
0x1caee  stelem.ref
0x1caef  dup
0x1caf0  ldc.i4.4
0x1caf1  ldstr    aLogpath_1// " /logPath:\""
0x1caf6  stelem.ref
0x1caf7  dup
0x1caf8  ldc.i4.5
0x1caf9  ldarg.1
0x1cafa  stelem.ref
0x1cafb  dup
0x1cafc  ldc.i4.6
0x1cafd  ldstr    aLoglevel4// "\" /LogLevel:4"
0x1cb02  stelem.ref
0x1cb03  call     string [mscorlib]System.String::Concat(string[])
0x1cb08  ldarg.2
0x1cb09  call     class Microsoft.VisualStudio.Setup.Result Microsoft.VisualStudio.Setup.DismUtility::Install(string arguments, class [mscorlib]System.IServiceProvider serviceProvider)
0x1cb0e  ret
```
