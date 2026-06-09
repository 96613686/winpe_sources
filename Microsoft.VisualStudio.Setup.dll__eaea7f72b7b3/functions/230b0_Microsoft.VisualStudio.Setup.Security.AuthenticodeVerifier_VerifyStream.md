# Microsoft.VisualStudio.Setup.Security.AuthenticodeVerifier::VerifyStream

- ea: `0x230b0`
- end: `0x232f0`
- name: `Microsoft.VisualStudio.Setup.Security.AuthenticodeVerifier::VerifyStream`
- size: `576`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x22e50`

## callees

- `0xeff0`
- `0x199a0`
- `0x22df0`
- `0x22e10`
- `0x230b0`
- `0x25660`
- `0x256d0`
- `0x257c0`
- `0x257e0`
- `0x25800`
- `0x25810`
- `0x25820`

## string_xrefs

- `0x2314b`: `Original path for file: `
- `0x231fc`: `Unable to get signer during WinVerifyTrust for '{0}': {1}`

## pseudocode

```c

```

## disassembly

```asm
0x230b0  ldc.i4.0
0x230b1  stloc.0
0x230b2  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::.ctor()
0x230b7  dup
0x230b8  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x230bd  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_ResourceManager(class [mscorlib]System.Resources.ResourceManager)
0x230c2  dup
0x230c3  ldstr    aAuthenticodeve// "AuthenticodeVerificationResult_Args2"
0x230c8  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_ResourceId(string)
0x230cd  stloc.2
0x230ce  ldc.i4.1
0x230cf  stloc.3
0x230d0  br       loc_2328B
0x230d5  ldarg.1
0x230d6  callvirt instance class [mscorlib]Microsoft.Win32.SafeHandles.SafeFileHandle [mscorlib]System.IO.FileStream::get_SafeFileHandle()
0x230db  ldarg.2
0x230dc  newobj   instance void Microsoft.VisualStudio.Setup.Security.WINTRUST_DATA::.ctor(class [mscorlib]System.Runtime.InteropServices.SafeHandle file, string path)
0x230e1  stloc.s  4
0x230e3  ldloc.s  4
0x230e5  ldarg.0
0x230e6  call     instance bool Microsoft.VisualStudio.Setup.Security.AuthenticodeVerifier::get_CheckHashOnly()
0x230eb  callvirt instance void Microsoft.VisualStudio.Setup.Security.WINTRUST_DATA::set_CheckHashOnly(bool value)
0x230f0  ldloc.s  4
0x230f2  ldarg.0
0x230f3  call     instance bool Microsoft.VisualStudio.Setup.Security.AuthenticodeVerifier::get_EnableRevocationChecks()
0x230f8  callvirt instance void Microsoft.VisualStudio.Setup.Security.WINTRUST_DATA::set_EnableRevocationChecks(bool value)
0x230fd  ldsfld   native int Microsoft.VisualStudio.Setup.Security.NativeMethods::INVALID_HANDLE_VALUE
0x23102  ldsfld   valuetype [mscorlib]System.Guid Microsoft.VisualStudio.Setup.Security.NativeMethods::WINTRUST_ACTION_GENERIC_VERIFY_V2
0x23107  ldloc.s  4
0x23109  call     int32 Microsoft.VisualStudio.Setup.Security.NativeMethods::WinVerifyTrust(native int hWnd, [in] [hasfieldmarshal] valuetype [mscorlib]System.Guid pgActionID, [in] [out] [hasfieldmarshal] class Microsoft.VisualStudio.Setup.Security.WINTRUST_DATA pWVTData)
0x2310e  stloc.0
0x2310f  ldloc.0
0x23110  brfalse.s loc_2312C
0x23112  ldloc.s  4
0x23114  ldc.i4.1
0x23115  callvirt instance void Microsoft.VisualStudio.Setup.Security.WINTRUST_DATA::set_CheckRevocationCache(bool value)
0x2311a  ldsfld   native int Microsoft.VisualStudio.Setup.Security.NativeMethods::INVALID_HANDLE_VALUE
0x2311f  ldsfld   valuetype [mscorlib]System.Guid Microsoft.VisualStudio.Setup.Security.NativeMethods::WINTRUST_ACTION_GENERIC_VERIFY_V2
0x23124  ldloc.s  4
0x23126  call     int32 Microsoft.VisualStudio.Setup.Security.NativeMethods::WinVerifyTrust(native int hWnd, [in] [hasfieldmarshal] valuetype [mscorlib]System.Guid pgActionID, [in] [out] [hasfieldmarshal] class Microsoft.VisualStudio.Setup.Security.WINTRUST_DATA pWVTData)
0x2312b  stloc.0
0x2312c  ldnull
0x2312d  stloc.s  5
0x2312f  ldarg.3
0x23130  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x23135  brfalse.s loc_2313C
0x23137  ldarg.2
0x23138  stloc.s  5
0x2313a  br.s     loc_23166
0x2313c  ldarg.3
0x2313d  stloc.s  5
0x2313f  ldarg.0
0x23140  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.AuthenticodeVerifier::log
0x23145  dup
0x23146  brtrue.s loc_2314B
0x23148  pop
0x23149  br.s     loc_23166
0x2314b  ldstr    aOriginalPathFo// "Original path for file: "
0x23150  ldarg.2
0x23151  ldstr    aIs// " is: "
0x23156  ldarg.3
0x23157  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x2315c  call     T0x2B000003
0x23161  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x23166  ldloc.2
0x23167  ldc.i4.2
0x23168  newarr   [mscorlib]System.Object
0x2316d  dup
0x2316e  ldc.i4.0
0x2316f  ldloc.0
0x23170  box      [mscorlib]System.Int32
0x23175  stelem.ref
0x23176  dup
0x23177  ldc.i4.1
0x23178  ldloc.s  5
0x2317a  stelem.ref
0x2317b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_ResourceArgs(object[])
0x23180  ldloc.2
0x23181  ldc.i4.2
0x23182  newarr   [mscorlib]System.Object
0x23187  dup
0x23188  ldc.i4.0
0x23189  ldloc.0
0x2318a  box      [mscorlib]System.Int32
0x2318f  stelem.ref
0x23190  dup
0x23191  ldc.i4.1
0x23192  ldloc.s  5
0x23194  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x23199  stelem.ref
0x2319a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_TelemetryResourceArgs(object[])
0x2319f  ldarg.0
0x231a0  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.AuthenticodeVerifier::log
0x231a5  dup
0x231a6  brtrue.s loc_231AB
0x231a8  pop
0x231a9  br.s     loc_231BC
0x231ab  ldloc.2
0x231ac  ldc.i4.0
0x231ad  call     string Microsoft.VisualStudio.Setup.Extensions::GetNeutralMessage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation, bool information)
0x231b2  call     T0x2B000003
0x231b7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x231bc  ldloc.0
0x231bd  ldc.i4   0x800B0100
0x231c2  beq.s    loc_2321C
0x231c4  ldloc.0
0x231c5  ldc.i4   0x800B0003
0x231ca  beq.s    loc_2321C
0x231cc  ldloc.s  4
0x231ce  callvirt instance string Microsoft.VisualStudio.Setup.Security.WINTRUST_DATA::GetSubjectName()
0x231d3  stloc.1
0x231d4  ldloc.1
0x231d5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x231da  brtrue.s loc_231EC
0x231dc  ldloc.2
0x231dd  ldc.i4.1
0x231de  newarr   [mscorlib]System.String
0x231e3  dup
0x231e4  ldc.i4.0
0x231e5  ldloc.1
0x231e6  stelem.ref
0x231e7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_Signers(class [mscorlib]System.Collections.Generic.IList`1<string>)
0x231ec  leave.s  loc_2321C
0x231ee  stloc.s  6
0x231f0  ldarg.0
0x231f1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.AuthenticodeVerifier::log
0x231f6  dup
0x231f7  brtrue.s loc_231FC
0x231f9  pop
0x231fa  br.s     loc_2321A
0x231fc  ldstr    aUnableToGetSig// "Unable to get signer during WinVerifyTr"...
0x23201  ldc.i4.2
0x23202  newarr   [mscorlib]System.Object
0x23207  dup
0x23208  ldc.i4.0
0x23209  ldarg.2
0x2320a  stelem.ref
0x2320b  dup
0x2320c  ldc.i4.1
0x2320d  ldloc.s  6
0x2320f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x23214  stelem.ref
0x23215  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2321a  leave.s  loc_2321C
0x2321c  ldloc.s  4
0x2321e  callvirt instance void Microsoft.VisualStudio.Setup.Security.WINTRUST_DATA::PrepareClose()
0x23223  ldsfld   native int Microsoft.VisualStudio.Setup.Security.NativeMethods::INVALID_HANDLE_VALUE
0x23228  ldsfld   valuetype [mscorlib]System.Guid Microsoft.VisualStudio.Setup.Security.NativeMethods::WINTRUST_ACTION_GENERIC_VERIFY_V2
0x2322d  ldloc.s  4
0x2322f  call     int32 Microsoft.VisualStudio.Setup.Security.NativeMethods::WinVerifyTrust(native int hWnd, [in] [hasfieldmarshal] valuetype [mscorlib]System.Guid pgActionID, [in] [out] [hasfieldmarshal] class Microsoft.VisualStudio.Setup.Security.WINTRUST_DATA pWVTData)
0x23234  pop
0x23235  leave.s  loc_23243
0x23237  ldloc.s  4
0x23239  brfalse.s loc_23242
0x2323b  ldloc.s  4
0x2323d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x23242  endfinally
0x23243  ldloc.3
0x23244  ldc.i4.3
0x23245  bge.s    loc_23292
0x23247  ldloc.0
0x23248  ldc.i4   0x800B0100
0x2324d  beq.s    loc_23257
0x2324f  ldloc.0
0x23250  ldc.i4   0x800B0003
0x23255  bne.un.s loc_23292
0x23257  ldarg.0
0x23258  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.AuthenticodeVerifier::log
0x2325d  dup
0x2325e  brtrue.s loc_23263
0x23260  pop
0x23261  br.s     loc_23278
0x23263  ldstr    aRetryingValida// "Retrying validation for: "
0x23268  ldarg.2
0x23269  call     string [mscorlib]System.String::Concat(string, string)
0x2326e  call     T0x2B000003
0x23273  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x23278  ldc.i4   0x3E8
0x2327d  call     class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Threading.Tasks.Task::Delay(int32)
0x23282  callvirt instance void [mscorlib]System.Threading.Tasks.Task::Wait()
0x23287  ldloc.3
0x23288  ldc.i4.1
0x23289  add
0x2328a  stloc.3
0x2328b  ldloc.3
0x2328c  ldc.i4.3
0x2328d  ble      loc_230D5
0x23292  ldloc.0
0x23293  ldc.i4   0x800B0003
0x23298  bgt.s    loc_232AE
0x2329a  ldloc.0
0x2329b  ldc.i4   0x80092010
0x232a0  beq.s    loc_232E7
0x232a2  ldloc.0
0x232a3  ldc.i4   0x800B0001
0x232a8  sub
0x232a9  ldc.i4.2
0x232aa  ble.un.s loc_232DE
0x232ac  br.s     loc_232E7
0x232ae  ldloc.0
0x232af  ldc.i4   0x800B0100
0x232b4  beq.s    loc_232CC
0x232b6  ldloc.0
0x232b7  ldc.i4   0x800B0109
0x232bc  sub
0x232bd  ldc.i4.1
0x232be  ble.un.s loc_232D5
0x232c0  ldloc.0
0x232c1  brtrue.s loc_232E7
0x232c3  ldloc.2
0x232c4  ldc.i4.0
0x232c5  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_Result(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult)
0x232ca  br.s     loc_232EE
0x232cc  ldloc.2
0x232cd  ldc.i4.1
0x232ce  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_Result(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult)
0x232d3  br.s     loc_232EE
0x232d5  ldloc.2
0x232d6  ldc.i4.3
0x232d7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_Result(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult)
0x232dc  br.s     loc_232EE
0x232de  ldloc.2
0x232df  ldc.i4.5
0x232e0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_Result(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult)
0x232e5  br.s     loc_232EE
0x232e7  ldloc.2
0x232e8  ldc.i4.2
0x232e9  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_Result(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult)
0x232ee  ldloc.2
0x232ef  ret
```
