# Microsoft.ReportingServices.Library.Reencryptor::ReencryptKey

- ea: `0x1500`
- end: `0x1579`
- name: `Microsoft.ReportingServices.Library.Reencryptor::ReencryptKey`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xe20`

## callees

- `0x1500`

## string_xrefs

- `0x1529`: `Reencryption: Failed to export symmetric key for current installation! InstallationID='{0}'`
- `0x1549`: `Reencryption: Failed to export symmetric key. Installation will no longer have access to secure information. InstallationID='{0}', Exception='{1}'`

## pseudocode

```c

```

## disassembly

```asm
0x1500  ldarga.s 2
0x1502  constrained. [mscorlib]System.Guid
0x1508  callvirt instance string [mscorlib]System.Object::ToString()
0x150d  stloc.0
0x150e  ldnull
0x150f  stloc.1
0x1510  ldarg.0
0x1511  ldfld    class [ReportingServicesNativeClient]RSManagedCrypto.RSCrypto Microsoft.ReportingServices.Library.Reencryptor::m_newKeyManager
0x1516  ldarg.1
0x1517  callvirt instance unsigned int8[] [ReportingServicesNativeClient]RSManagedCrypto.RSCrypto::ExportSymmetricKey(unsigned int8[])
0x151c  stloc.1
0x151d  leave.s  loc_156A
0x151f  stloc.2
0x1520  ldarg.3
0x1521  brfalse.s loc_1543
0x1523  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x1528  ldc.i4.1
0x1529  ldstr    aReencryptionFa_2// "Reencryption: Failed to export symmetri"...
0x152e  ldc.i4.1
0x152f  newarr   [mscorlib]System.Object
0x1534  dup
0x1535  ldc.i4.0
0x1536  ldloc.0
0x1537  stelem.ref
0x1538  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x153d  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.FailedToExportSymmetricKeyException::.ctor()
0x1542  throw
0x1543  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x1548  ldc.i4.1
0x1549  ldstr    aReencryptionFa_3// "Reencryption: Failed to export symmetri"...
0x154e  ldc.i4.2
0x154f  newarr   [mscorlib]System.Object
0x1554  dup
0x1555  ldc.i4.0
0x1556  ldloc.0
0x1557  stelem.ref
0x1558  dup
0x1559  ldc.i4.1
0x155a  ldloc.2
0x155b  callvirt instance string [mscorlib]System.Object::ToString()
0x1560  stelem.ref
0x1561  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1566  ldnull
0x1567  stloc.1
0x1568  leave.s  loc_156A
0x156a  ldarg.0
0x156b  ldfld    class Microsoft.ReportingServices.Library.ActivationDB Microsoft.ReportingServices.Library.Reencryptor::m_database
0x1570  ldarg.2
0x1571  ldloc.1
0x1572  ldarg.1
0x1573  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.KeyStorage::SetKeysForInstallation(valuetype [mscorlib]System.Guid, unsigned int8[], unsigned int8[])
0x1578  ret
```
