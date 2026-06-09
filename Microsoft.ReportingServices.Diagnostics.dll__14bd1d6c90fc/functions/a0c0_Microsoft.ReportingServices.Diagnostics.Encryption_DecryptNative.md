# Microsoft.ReportingServices.Diagnostics.Encryption::DecryptNative

- ea: `0xa0c0`
- end: `0xa158`
- name: `Microsoft.ReportingServices.Diagnostics.Encryption::DecryptNative`
- size: `152`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xaf50`
- `0xd0a0`

## callees

- `0xa0c0`

## pseudocode

```c

```

## disassembly

```asm
0xa0c0  ldarg.0
0xa0c1  brtrue.s loc_A0C5
0xa0c3  ldnull
0xa0c4  ret
0xa0c5  ldnull
0xa0c6  stloc.0
0xa0c7  ldnull
0xa0c8  stloc.1
0xa0c9  ldnull
0xa0ca  stloc.2
0xa0cb  ldarg.0
0xa0cc  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeCryptoBlobIn::.ctor(unsigned int8[])
0xa0d1  stloc.1
0xa0d2  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeCryptoBlobOut::.ctor()
0xa0d7  stloc.2
0xa0d8  ldloc.1
0xa0d9  ldnull
0xa0da  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xa0df  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xa0e4  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xa0e9  ldarg.1
0xa0ea  ldloc.2
0xa0eb  call     bool [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.NativeMethods::CryptUnprotectData(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeCryptoBlobIn, class [mscorlib]System.Text.StringBuilder, native int, native int, native int, int32, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeCryptoBlobOut)
0xa0f0  brfalse.s loc_A120
0xa0f2  ldloc.2
0xa0f3  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.NativeMethods/DATA_BLOB [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeCryptoBlobOut::get_Blob()
0xa0f8  stloc.3
0xa0f9  ldloc.3
0xa0fa  ldfld    int32 [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.NativeMethods/DATA_BLOB::cbData
0xa0ff  newarr   [mscorlib]System.Byte
0xa104  stloc.0
0xa105  ldloc.3
0xa106  ldfld    native int [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.NativeMethods/DATA_BLOB::pbData
0xa10b  ldloc.0
0xa10c  ldc.i4.0
0xa10d  ldloc.3
0xa10e  ldfld    int32 [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.NativeMethods/DATA_BLOB::cbData
0xa113  call     void [mscorlib]System.Runtime.InteropServices.Marshal::Copy(native int, unsigned int8[], int32, int32)
0xa118  ldloc.2
0xa119  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeCryptoBlobOut::ZeroBuffer()
0xa11e  leave.s  loc_A156
0xa120  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0xa125  stloc.s  4
0xa127  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa12c  ldstr    aCryptunprotect// "CryptUnprotectData: Win32 error:{0}"
0xa131  ldloc.s  4
0xa133  box      [mscorlib]System.Int32
0xa138  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xa13d  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(string)
0xa142  throw
0xa143  ldloc.1
0xa144  brfalse.s loc_A14C
0xa146  ldloc.1
0xa147  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0xa14c  ldloc.2
0xa14d  brfalse.s loc_A155
0xa14f  ldloc.2
0xa150  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0xa155  endfinally
0xa156  ldloc.0
0xa157  ret
```
