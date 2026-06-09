# NGenTask.Logger::Init

- ea: `0x2b10`
- end: `0x2c23`
- name: `NGenTask.Logger::Init`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x2990`

## callees

- `0x1cf0`
- `0x2b10`
- `0x2ce0`
- `0x2cf0`

## pseudocode

```c

```

## disassembly

```asm
0x2b10  ldc.i4.0
0x2b11  stloc.0
0x2b12  ldc.i4.0
0x2b13  stloc.1
0x2b14  ldarg.0
0x2b15  stloc.2
0x2b16  ldc.i4.0
0x2b17  stloc.3
0x2b18  br.s     loc_2B66
0x2b1a  ldloc.2
0x2b1b  ldloc.3
0x2b1c  ldelem.ref
0x2b1d  stloc.s  4
0x2b1f  ldloc.s  4
0x2b21  ldstr    aRuntimewide// "/RuntimeWide"
0x2b26  ldc.i4.5
0x2b27  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x2b2c  brfalse.s loc_2B32
0x2b2e  ldc.i4.1
0x2b2f  stloc.0
0x2b30  br.s     loc_2B62
0x2b32  ldloc.s  4
0x2b34  ldstr    aVerbose// "/Verbose"
0x2b39  ldc.i4.5
0x2b3a  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x2b3f  brfalse.s loc_2B4B
0x2b41  ldc.i4.3
0x2b42  call     void NGenTask.Logger::set_MaxLogLevel(valuetype LogLevel value)
0x2b47  ldc.i4.1
0x2b48  stloc.1
0x2b49  br.s     loc_2B62
0x2b4b  ldloc.s  4
0x2b4d  ldstr    aSilent// "/Silent"
0x2b52  ldc.i4.5
0x2b53  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x2b58  brfalse.s loc_2B62
0x2b5a  ldc.i4.1
0x2b5b  call     void NGenTask.Logger::set_MaxLogLevel(valuetype LogLevel value)
0x2b60  ldc.i4.1
0x2b61  stloc.1
0x2b62  ldloc.3
0x2b63  ldc.i4.1
0x2b64  add
0x2b65  stloc.3
0x2b66  ldloc.3
0x2b67  ldloc.2
0x2b68  ldlen
0x2b69  conv.i4
0x2b6a  blt.s    loc_2B1A
0x2b6c  nop
0x2b6d  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x2b72  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x2b77  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x2b7c  stloc.s  5
0x2b7e  ldloc.0
0x2b7f  brfalse.s loc_2B87
0x2b81  ldloc.s  5
0x2b83  stloc.s  6
0x2b85  br.s     loc_2BE1
0x2b87  ldloc.s  5
0x2b89  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x2b8e  stloc.s  8
0x2b90  ldloc.s  8
0x2b92  call     string NGenTask.TaskExecutive::ComputeShortVersionString(string version)
0x2b97  stloc.s  9
0x2b99  ldloc.s  9
0x2b9b  brtrue.s loc_2BA1
0x2b9d  ldloc.s  8
0x2b9f  stloc.s  9
0x2ba1  ldstr    aMicrosoftClr// "Microsoft\\CLR_"
0x2ba6  ldloc.s  9
0x2ba8  call     string [mscorlib]System.String::Concat(string, string)
0x2bad  stloc.s  0xA
0x2baf  ldstr    aLocalappdata// "LOCALAPPDATA"
0x2bb4  call     string [mscorlib]System.Environment::GetEnvironmentVariable(string)
0x2bb9  stloc.s  6
0x2bbb  ldloc.s  6
0x2bbd  brtrue.s loc_2BC5
0x2bbf  ldloc.s  5
0x2bc1  stloc.s  6
0x2bc3  br.s     loc_2BE1
0x2bc5  ldloc.s  6
0x2bc7  ldloc.s  0xA
0x2bc9  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2bce  stloc.s  6
0x2bd0  ldloc.s  6
0x2bd2  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x2bd7  brtrue.s loc_2BE1
0x2bd9  ldloc.s  6
0x2bdb  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x2be0  pop
0x2be1  ldc.i4.2
0x2be2  stloc.s  7
0x2be4  ldloc.s  6
0x2be6  ldstr    aNgen_0// "ngen"
0x2beb  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2bf0  ldloc.0
0x2bf1  ldc.i4.0
0x2bf2  ceq
0x2bf4  ldloca.s 7
0x2bf6  call     bool NGenTask.Logger::CorInitSvcLogger(string filename, bool userLocal, [out] valuetype LogLevel& logLevel)
0x2bfb  brtrue.s loc_2C09
0x2bfd  ldc.i4   0x80000000
0x2c02  call     void NGenTask.Logger::set_MaxLogLevel(valuetype LogLevel value)
0x2c07  br.s     loc_2C13
0x2c09  ldloc.1
0x2c0a  brtrue.s loc_2C13
0x2c0c  ldloc.s  7
0x2c0e  call     void NGenTask.Logger::set_MaxLogLevel(valuetype LogLevel value)
0x2c13  leave.s  loc_2C22
0x2c15  pop
0x2c16  ldc.i4   0x80000000
0x2c1b  call     void NGenTask.Logger::set_MaxLogLevel(valuetype LogLevel value)
0x2c20  leave.s  loc_2C22
0x2c22  ret
```
