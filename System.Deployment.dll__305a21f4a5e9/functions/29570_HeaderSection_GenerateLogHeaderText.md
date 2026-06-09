# HeaderSection::GenerateLogHeaderText

- ea: `0x29570`
- end: `0x2971a`
- name: `HeaderSection::GenerateLogHeaderText`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x294b0`

## callees

- `0x23020`
- `0x29500`
- `0x29520`
- `0x29540`
- `0x29550`
- `0x29570`

## string_xrefs

- `0x2958c`: `dfshim.dll`
- `0x29581`: `dfdll.dll`
- `0x29576`: `clr.dll`
- `0x295a3`: `system.deployment.dll`
- `0x29692`: `LogFile_HeaderClrDllVersion`
- `0x296bd`: `LogFile_HeaderDfdllVersion`

## pseudocode

```c

```

## disassembly

```asm
0x29570  call     string HeaderSection::GetExecutingAssemblyPath()
0x29575  stloc.0
0x29576  ldstr    aClrDll// "clr.dll"
0x2957b  call     string HeaderSection::GetModulePathInClrFolder(string moduleName)
0x29580  stloc.1
0x29581  ldstr    aDfdllDll// "dfdll.dll"
0x29586  call     string HeaderSection::GetModulePathInClrFolder(string moduleName)
0x2958b  stloc.2
0x2958c  ldstr    aDfshimDll// "dfshim.dll"
0x29591  call     string HeaderSection::GetModulePath(string moduleName)
0x29596  stloc.3
0x29597  ldloc.0
0x29598  call     class [System]System.Diagnostics.FileVersionInfo HeaderSection::GetVersionInfo(string modulePath)
0x2959d  stloc.s  4
0x2959f  ldloc.s  4
0x295a1  brtrue.s loc_295B6
0x295a3  ldstr    aSystemDeployme_1// "system.deployment.dll"
0x295a8  call     string HeaderSection::GetModulePathInClrFolder(string moduleName)
0x295ad  stloc.0
0x295ae  ldloc.0
0x295af  call     class [System]System.Diagnostics.FileVersionInfo HeaderSection::GetVersionInfo(string modulePath)
0x295b4  stloc.s  4
0x295b6  ldloc.1
0x295b7  call     class [System]System.Diagnostics.FileVersionInfo HeaderSection::GetVersionInfo(string modulePath)
0x295bc  stloc.s  5
0x295be  ldloc.2
0x295bf  call     class [System]System.Diagnostics.FileVersionInfo HeaderSection::GetVersionInfo(string modulePath)
0x295c4  stloc.s  6
0x295c6  ldloc.3
0x295c7  call     class [System]System.Diagnostics.FileVersionInfo HeaderSection::GetVersionInfo(string modulePath)
0x295cc  stloc.s  7
0x295ce  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x295d3  stloc.s  8
0x295d5  ldloc.s  8
0x295d7  ldstr    aLogfileHeader// "LogFile_Header"
0x295dc  call     string System.Deployment.Application.Resources::GetString(string s)
0x295e1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x295e6  pop
0x295e7  ldloc.s  8
0x295e9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x295ee  ldstr    aLogfileHeadero// "LogFile_HeaderOSVersion"
0x295f3  call     string System.Deployment.Application.Resources::GetString(string s)
0x295f8  ldc.i4.2
0x295f9  newarr   [mscorlib]System.Object
0x295fe  dup
0x295ff  ldc.i4.0
0x29600  call     class [mscorlib]System.OperatingSystem [mscorlib]System.Environment::get_OSVersion()
0x29605  callvirt instance valuetype [mscorlib]System.PlatformID [mscorlib]System.OperatingSystem::get_Platform()
0x2960a  stloc.s  9
0x2960c  ldloca.s 9
0x2960e  constrained. [mscorlib]System.PlatformID
0x29614  callvirt instance string [mscorlib]System.Object::ToString()
0x29619  stelem.ref
0x2961a  dup
0x2961b  ldc.i4.1
0x2961c  call     class [mscorlib]System.OperatingSystem [mscorlib]System.Environment::get_OSVersion()
0x29621  callvirt instance class [mscorlib]System.Version [mscorlib]System.OperatingSystem::get_Version()
0x29626  callvirt instance string [mscorlib]System.Object::ToString()
0x2962b  stelem.ref
0x2962c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x29631  pop
0x29632  ldloc.s  8
0x29634  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x29639  ldstr    aLogfileHeaderc// "LogFile_HeaderCLRVersion"
0x2963e  call     string System.Deployment.Application.Resources::GetString(string s)
0x29643  ldc.i4.1
0x29644  newarr   [mscorlib]System.Object
0x29649  dup
0x2964a  ldc.i4.0
0x2964b  call     class [mscorlib]System.Version [mscorlib]System.Environment::get_Version()
0x29650  callvirt instance string [mscorlib]System.Object::ToString()
0x29655  stelem.ref
0x29656  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x2965b  pop
0x2965c  ldloc.s  4
0x2965e  brfalse.s loc_29687
0x29660  ldloc.s  8
0x29662  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x29667  ldstr    aLogfileHeaders// "LogFile_HeaderSystemDeploymentVersion"
0x2966c  call     string System.Deployment.Application.Resources::GetString(string s)
0x29671  ldc.i4.1
0x29672  newarr   [mscorlib]System.Object
0x29677  dup
0x29678  ldc.i4.0
0x29679  ldloc.s  4
0x2967b  callvirt instance string [System]System.Diagnostics.FileVersionInfo::get_FileVersion()
0x29680  stelem.ref
0x29681  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x29686  pop
0x29687  ldloc.s  5
0x29689  brfalse.s loc_296B2
0x2968b  ldloc.s  8
0x2968d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x29692  ldstr    aLogfileHeaderc_0// "LogFile_HeaderClrDllVersion"
0x29697  call     string System.Deployment.Application.Resources::GetString(string s)
0x2969c  ldc.i4.1
0x2969d  newarr   [mscorlib]System.Object
0x296a2  dup
0x296a3  ldc.i4.0
0x296a4  ldloc.s  5
0x296a6  callvirt instance string [System]System.Diagnostics.FileVersionInfo::get_FileVersion()
0x296ab  stelem.ref
0x296ac  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x296b1  pop
0x296b2  ldloc.s  6
0x296b4  brfalse.s loc_296DD
0x296b6  ldloc.s  8
0x296b8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x296bd  ldstr    aLogfileHeaderd// "LogFile_HeaderDfdllVersion"
0x296c2  call     string System.Deployment.Application.Resources::GetString(string s)
0x296c7  ldc.i4.1
0x296c8  newarr   [mscorlib]System.Object
0x296cd  dup
0x296ce  ldc.i4.0
0x296cf  ldloc.s  6
0x296d1  callvirt instance string [System]System.Diagnostics.FileVersionInfo::get_FileVersion()
0x296d6  stelem.ref
0x296d7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x296dc  pop
0x296dd  ldloc.s  7
0x296df  brfalse.s loc_29708
0x296e1  ldloc.s  8
0x296e3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x296e8  ldstr    aLogfileHeaderd_0// "LogFile_HeaderDfshimVersion"
0x296ed  call     string System.Deployment.Application.Resources::GetString(string s)
0x296f2  ldc.i4.1
0x296f3  newarr   [mscorlib]System.Object
0x296f8  dup
0x296f9  ldc.i4.0
0x296fa  ldloc.s  7
0x296fc  callvirt instance string [System]System.Diagnostics.FileVersionInfo::get_FileVersion()
0x29701  stelem.ref
0x29702  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x29707  pop
0x29708  leave.s  loc_29712
0x2970a  stloc.s  0xA
0x2970c  leave.s  loc_29712
0x2970e  stloc.s  0xB
0x29710  leave.s  loc_29712
0x29712  ldloc.s  8
0x29714  callvirt instance string [mscorlib]System.Object::ToString()
0x29719  ret
```
