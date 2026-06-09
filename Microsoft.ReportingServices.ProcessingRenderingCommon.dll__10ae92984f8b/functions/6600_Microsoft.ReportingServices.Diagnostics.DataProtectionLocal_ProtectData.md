# Microsoft.ReportingServices.Diagnostics.DataProtectionLocal::ProtectData

- ea: `0x6600`
- end: `0x669d`
- name: `Microsoft.ReportingServices.Diagnostics.DataProtectionLocal::ProtectData`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x6530`

## callees

- `0x4000`
- `0x4090`
- `0x4110`
- `0x4150`
- `0x6600`
- `0x66e0`

## pseudocode

```c

```

## disassembly

```asm
0x6600  ldstr    aDefault// "Default"
0x6605  stloc.0
0x6606  ldnull
0x6607  stloc.1
0x6608  ldnull
0x6609  stloc.2
0x660a  ldnull
0x660b  stloc.3
0x660c  ldarg.0
0x660d  newobj   instance void Microsoft.ReportingServices.Diagnostics.SafeCryptoBlobIn::.ctor(unsigned int8[] data)
0x6612  stloc.2
0x6613  newobj   instance void Microsoft.ReportingServices.Diagnostics.SafeCryptoBlobOut::.ctor()
0x6618  stloc.3
0x6619  ldloc.2
0x661a  ldloc.0
0x661b  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x6620  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x6625  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x662a  ldarg.1
0x662b  ldloc.3
0x662c  call     bool Microsoft.ReportingServices.Diagnostics.NativeMethods::CryptProtectData(class Microsoft.ReportingServices.Diagnostics.SafeCryptoBlobIn dataIn, string szDataDescr, native int optionalEntropy, native int pvReserved, native int pPromptStruct, int32 dwFlags, class Microsoft.ReportingServices.Diagnostics.SafeCryptoBlobOut pDataOut)
0x6631  ldloc.2
0x6632  callvirt instance void Microsoft.ReportingServices.Diagnostics.SafeCryptoBlobIn::ZeroBuffer()
0x6637  brfalse.s loc_6665
0x6639  ldloc.3
0x663a  callvirt instance valuetype DATA_BLOB Microsoft.ReportingServices.Diagnostics.SafeCryptoBlobOut::get_Blob()
0x663f  stloc.s  4
0x6641  ldloc.s  4
0x6643  ldfld    int32 DATA_BLOB::cbData
0x6648  newarr   [mscorlib]System.Byte
0x664d  stloc.1
0x664e  ldloc.s  4
0x6650  ldfld    native int DATA_BLOB::pbData
0x6655  ldloc.1
0x6656  ldc.i4.0
0x6657  ldloc.s  4
0x6659  ldfld    int32 DATA_BLOB::cbData
0x665e  call     void [mscorlib]System.Runtime.InteropServices.Marshal::Copy(native int, unsigned int8[], int32, int32)
0x6663  leave.s  loc_669B
0x6665  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x666a  stloc.s  5
0x666c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6671  ldstr    aCryptprotectda// "CryptProtectData: Win32 error:{0}"
0x6676  ldloc.s  5
0x6678  box      [mscorlib]System.Int32
0x667d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x6682  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(string)
0x6687  throw
0x6688  ldloc.2
0x6689  brfalse.s loc_6691
0x668b  ldloc.2
0x668c  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x6691  ldloc.3
0x6692  brfalse.s loc_669A
0x6694  ldloc.3
0x6695  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x669a  endfinally
0x669b  ldloc.1
0x669c  ret
```
