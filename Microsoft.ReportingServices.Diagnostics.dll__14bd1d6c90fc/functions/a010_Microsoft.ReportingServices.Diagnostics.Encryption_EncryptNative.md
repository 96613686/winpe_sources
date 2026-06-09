# Microsoft.ReportingServices.Diagnostics.Encryption::EncryptNative

- ea: `0xa010`
- end: `0xa0b2`
- name: `Microsoft.ReportingServices.Diagnostics.Encryption::EncryptNative`
- size: `162`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xaf40`
- `0xd090`

## callees

- `0xa010`

## pseudocode

```c

```

## disassembly

```asm
0xa010  ldarg.0
0xa011  brtrue.s loc_A015
0xa013  ldnull
0xa014  ret
0xa015  ldstr    aDefault_1// "Default"
0xa01a  stloc.0
0xa01b  ldnull
0xa01c  stloc.1
0xa01d  ldnull
0xa01e  stloc.2
0xa01f  ldnull
0xa020  stloc.3
0xa021  ldarg.0
0xa022  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeCryptoBlobIn::.ctor(unsigned int8[])
0xa027  stloc.2
0xa028  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeCryptoBlobOut::.ctor()
0xa02d  stloc.3
0xa02e  ldloc.2
0xa02f  ldloc.0
0xa030  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xa035  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xa03a  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xa03f  ldarg.1
0xa040  ldloc.3
0xa041  call     bool [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.NativeMethods::CryptProtectData(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeCryptoBlobIn, string, native int, native int, native int, int32, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeCryptoBlobOut)
0xa046  ldloc.2
0xa047  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeCryptoBlobIn::ZeroBuffer()
0xa04c  brfalse.s loc_A07A
0xa04e  ldloc.3
0xa04f  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.NativeMethods/DATA_BLOB [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeCryptoBlobOut::get_Blob()
0xa054  stloc.s  4
0xa056  ldloc.s  4
0xa058  ldfld    int32 [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.NativeMethods/DATA_BLOB::cbData
0xa05d  newarr   [mscorlib]System.Byte
0xa062  stloc.1
0xa063  ldloc.s  4
0xa065  ldfld    native int [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.NativeMethods/DATA_BLOB::pbData
0xa06a  ldloc.1
0xa06b  ldc.i4.0
0xa06c  ldloc.s  4
0xa06e  ldfld    int32 [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.NativeMethods/DATA_BLOB::cbData
0xa073  call     void [mscorlib]System.Runtime.InteropServices.Marshal::Copy(native int, unsigned int8[], int32, int32)
0xa078  leave.s  loc_A0B0
0xa07a  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0xa07f  stloc.s  5
0xa081  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa086  ldstr    aCryptprotectda// "CryptProtectData: Win32 error:{0}"
0xa08b  ldloc.s  5
0xa08d  box      [mscorlib]System.Int32
0xa092  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xa097  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(string)
0xa09c  throw
0xa09d  ldloc.2
0xa09e  brfalse.s loc_A0A6
0xa0a0  ldloc.2
0xa0a1  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0xa0a6  ldloc.3
0xa0a7  brfalse.s loc_A0AF
0xa0a9  ldloc.3
0xa0aa  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0xa0af  endfinally
0xa0b0  ldloc.1
0xa0b1  ret
```
