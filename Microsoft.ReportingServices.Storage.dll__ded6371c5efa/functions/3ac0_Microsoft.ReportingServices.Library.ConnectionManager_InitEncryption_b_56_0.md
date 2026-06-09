# Microsoft.ReportingServices.Library.ConnectionManager::<InitEncryption>b__56_0

- ea: `0x3ac0`
- end: `0x3b71`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::<InitEncryption>b__56_0`
- size: `177`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x2850`
- `0x32f0`
- `0x3420`
- `0x3670`
- `0x3710`
- `0x3ac0`

## pseudocode

```c

```

## disassembly

```asm
0x3ac0  call     void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::AcquireWriterLock()
0x3ac5  call     bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::get_IsInitialized()
0x3aca  brfalse.s loc_3AD1
0x3acc  leave    loc_3B70
0x3ad1  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x3ad6  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x3adb  brfalse.s loc_3AFB
0x3add  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x3ae2  ldc.i4.3
0x3ae3  ldstr    aInitializingCr// "Initializing crypto as user: {0}"
0x3ae8  ldc.i4.1
0x3ae9  newarr   [mscorlib]System.Object
0x3aee  dup
0x3aef  ldc.i4.0
0x3af0  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserUtil::GetWindowsIdentityName()
0x3af5  stelem.ref
0x3af6  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x3afb  ldarg.0
0x3afc  newobj   instance void Microsoft.ReportingServices.Library.KeyStorage::.ctor(class Microsoft.ReportingServices.Library.ConnectionManager manager)
0x3b01  stloc.0
0x3b02  ldarg.0
0x3b03  ldc.i4   0x1000
0x3b08  call     instance void Microsoft.ReportingServices.Library.ConnectionManager::BeginTransaction(valuetype [System.Data]System.Data.IsolationLevel isoLevel)
0x3b0d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x3b12  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x3b17  brfalse.s loc_3B29
0x3b19  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x3b1e  ldc.i4.3
0x3b1f  ldstr    aExportingPubli// "Exporting public key"
0x3b24  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x3b29  call     unsigned int8[] [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::GetPublicKey()
0x3b2e  stloc.1
0x3b2f  ldarg.0
0x3b30  ldloc.0
0x3b31  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x3b36  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_InstallationID()
0x3b3b  ldloc.1
0x3b3c  call     instance void Microsoft.ReportingServices.Library.ConnectionManager::GetSymmetricKey(class Microsoft.ReportingServices.Library.KeyStorage storage, valuetype [mscorlib]System.Guid installationID, unsigned int8[] publicKey)
0x3b41  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::get_Current()
0x3b46  ldc.i4.s 0x77
0x3b48  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::ResetWriteOnceEvent(valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Event)
0x3b4d  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::get_Current()
0x3b52  ldc.i4.s 0x78
0x3b54  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::ResetWriteOnceEvent(valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Event)
0x3b59  ldarg.0
0x3b5a  call     instance void Microsoft.ReportingServices.Library.ConnectionManager::CommitTransaction()
0x3b5f  leave.s  loc_3B70
0x3b61  pop
0x3b62  ldarg.0
0x3b63  call     instance void Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage()
0x3b68  rethrow
0x3b6a  call     void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.SymmetricKeyEncryption::ReleaseWriterLock()
0x3b6f  endfinally
0x3b70  ret
```
