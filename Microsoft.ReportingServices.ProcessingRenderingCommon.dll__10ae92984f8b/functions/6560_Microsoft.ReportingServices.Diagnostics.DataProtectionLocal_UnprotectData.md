# Microsoft.ReportingServices.Diagnostics.DataProtectionLocal::UnprotectData

- ea: `0x6560`
- end: `0x65f3`
- name: `Microsoft.ReportingServices.Diagnostics.DataProtectionLocal::UnprotectData`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x6550`

## callees

- `0x4000`
- `0x4110`
- `0x4150`
- `0x4190`
- `0x6560`
- `0x66f0`

## pseudocode

```c

```

## disassembly

```asm
0x6560  ldnull
0x6561  stloc.0
0x6562  ldnull
0x6563  stloc.1
0x6564  ldnull
0x6565  stloc.2
0x6566  ldarg.0
0x6567  newobj   instance void Microsoft.ReportingServices.Diagnostics.SafeCryptoBlobIn::.ctor(unsigned int8[] data)
0x656c  stloc.1
0x656d  newobj   instance void Microsoft.ReportingServices.Diagnostics.SafeCryptoBlobOut::.ctor()
0x6572  stloc.2
0x6573  ldloc.1
0x6574  ldnull
0x6575  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x657a  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x657f  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x6584  ldarg.1
0x6585  ldloc.2
0x6586  call     bool Microsoft.ReportingServices.Diagnostics.NativeMethods::CryptUnprotectData(class Microsoft.ReportingServices.Diagnostics.SafeCryptoBlobIn dataIn, class [mscorlib]System.Text.StringBuilder ppszDataDescr, native int optionalEntropy, native int pvReserved, native int pPromptStruct, int32 dwFlags, class Microsoft.ReportingServices.Diagnostics.SafeCryptoBlobOut pDataOut)
0x658b  brfalse.s loc_65BB
0x658d  ldloc.2
0x658e  callvirt instance valuetype DATA_BLOB Microsoft.ReportingServices.Diagnostics.SafeCryptoBlobOut::get_Blob()
0x6593  stloc.3
0x6594  ldloc.3
0x6595  ldfld    int32 DATA_BLOB::cbData
0x659a  newarr   [mscorlib]System.Byte
0x659f  stloc.0
0x65a0  ldloc.3
0x65a1  ldfld    native int DATA_BLOB::pbData
0x65a6  ldloc.0
0x65a7  ldc.i4.0
0x65a8  ldloc.3
0x65a9  ldfld    int32 DATA_BLOB::cbData
0x65ae  call     void [mscorlib]System.Runtime.InteropServices.Marshal::Copy(native int, unsigned int8[], int32, int32)
0x65b3  ldloc.2
0x65b4  callvirt instance void Microsoft.ReportingServices.Diagnostics.SafeCryptoBlobOut::ZeroBuffer()
0x65b9  leave.s  loc_65F1
0x65bb  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x65c0  stloc.s  4
0x65c2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x65c7  ldstr    aCryptunprotect// "CryptUnprotectData: Win32 error:{0}"
0x65cc  ldloc.s  4
0x65ce  box      [mscorlib]System.Int32
0x65d3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x65d8  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(string)
0x65dd  throw
0x65de  ldloc.1
0x65df  brfalse.s loc_65E7
0x65e1  ldloc.1
0x65e2  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x65e7  ldloc.2
0x65e8  brfalse.s loc_65F0
0x65ea  ldloc.2
0x65eb  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x65f0  endfinally
0x65f1  ldloc.0
0x65f2  ret
```
