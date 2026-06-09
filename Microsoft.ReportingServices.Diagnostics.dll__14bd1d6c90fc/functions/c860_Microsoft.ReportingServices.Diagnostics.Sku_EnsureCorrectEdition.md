# Microsoft.ReportingServices.Diagnostics.Sku::EnsureCorrectEdition

- ea: `0xc860`
- end: `0xc988`
- name: `Microsoft.ReportingServices.Diagnostics.Sku::EnsureCorrectEdition`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1b0`

## callees

- `0xc860`
- `0xca00`
- `0xcb00`
- `0xcec0`

## pseudocode

```c

```

## disassembly

```asm
0xc860  ldarg.0
0xc861  call     valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.SqlServerSkuType [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.SkuUtil::GetSqlSku(class [System.Data]System.Data.IDbConnection)
0xc866  stloc.0
0xc867  leave.s  loc_C874
0xc869  ldstr    aSelectServerpr// "SELECT SERVERPROPERTY failed to execute"...
0xc86e  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(class [mscorlib]System.Exception, string)
0xc873  throw
0xc874  ldloc.0
0xc875  brtrue.s loc_C882
0xc877  ldstr    aCannotGetEditi// "Cannot get edition information from cat"...
0xc87c  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(string)
0xc881  throw
0xc882  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0xc887  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0xc88c  brfalse.s loc_C8B4
0xc88e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0xc893  ldc.i4.3
0xc894  ldstr    aCatalogSqlServ// "Catalog SQL Server Edition = {0}"
0xc899  ldc.i4.1
0xc89a  newarr   [mscorlib]System.Object
0xc89f  dup
0xc8a0  ldc.i4.0
0xc8a1  ldloca.s 0
0xc8a3  constrained. [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.SqlServerSkuType
0xc8a9  callvirt instance string [mscorlib]System.Object::ToString()
0xc8ae  stelem.ref
0xc8af  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xc8b4  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0xc8b9  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_InstanceID()
0xc8be  call     valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType Microsoft.ReportingServices.Diagnostics.Sku::GetInstalledSku(string instanceId)
0xc8c3  stloc.1
0xc8c4  ldloc.1
0xc8c5  ldloc.0
0xc8c6  ldarg.1
0xc8c7  ldnull
0xc8c8  ldftn    bool Microsoft.ReportingServices.Diagnostics.Sku::IsLocalValue(string value)
0xc8ce  newobj   instance void [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.SkuUtil/LocalDbServerVerifier::.ctor(object, native int)
0xc8d3  ldarg.2
0xc8d4  call     valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.SkuUtil/SkuVerificationErrorCode [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.SkuUtil::EnsureCorrectEdition(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType, valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.SqlServerSkuType, string, class [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.SkuUtil/LocalDbServerVerifier, bool)
0xc8d9  stloc.2
0xc8da  ldloc.2
0xc8db  ldc.i4.1
0xc8dc  bne.un.s loc_C8E9
0xc8de  ldc.i4.2
0xc8df  call     void Microsoft.ReportingServices.Diagnostics.SkuResources::ThrowOperationNotSupportedException(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures feature)
0xc8e4  br       loc_C986
0xc8e9  ldloc.2
0xc8ea  brfalse  loc_C986
0xc8ef  ldloc.1
0xc8f0  ldloca.s 3
0xc8f2  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.SqlServerSkuType> [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.SkuUtil::GetSupportedDatabaseSkus(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType, class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.SqlServerSkuType>&)
0xc8f7  stloc.s  4
0xc8f9  ldloc.2
0xc8fa  ldc.i4.2
0xc8fb  bne.un.s loc_C941
0xc8fd  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0xc902  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0xc907  brfalse.s loc_C939
0xc909  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0xc90e  ldc.i4.1
0xc90f  ldstr    aRequiredSkus0A// "required SKUs: {0} - actual SKU: {1}"
0xc914  ldc.i4.2
0xc915  newarr   [mscorlib]System.Object
0xc91a  dup
0xc91b  ldc.i4.0
0xc91c  ldloc.s  4
0xc91e  call     string Microsoft.ReportingServices.Diagnostics.Sku::GetSkuListForTrace(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.SqlServerSkuType> skus)
0xc923  stelem.ref
0xc924  dup
0xc925  ldc.i4.1
0xc926  ldloca.s 0
0xc928  constrained. [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.SqlServerSkuType
0xc92e  callvirt instance string [mscorlib]System.Object::ToString()
0xc933  stelem.ref
0xc934  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xc939  ldc.i4.1
0xc93a  call     void Microsoft.ReportingServices.Diagnostics.SkuResources::ThrowOperationNotSupportedException(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures feature)
0xc93f  br.s     loc_C986
0xc941  ldloc.2
0xc942  ldc.i4.3
0xc943  bne.un.s loc_C986
0xc945  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0xc94a  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0xc94f  brfalse.s loc_C980
0xc951  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0xc956  ldc.i4.1
0xc957  ldstr    aRestrictedSkus// "restricted SKUs: {0} - actual SKU: {1}"
0xc95c  ldc.i4.2
0xc95d  newarr   [mscorlib]System.Object
0xc962  dup
0xc963  ldc.i4.0
0xc964  ldloc.3
0xc965  call     string Microsoft.ReportingServices.Diagnostics.Sku::GetSkuListForTrace(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.SqlServerSkuType> skus)
0xc96a  stelem.ref
0xc96b  dup
0xc96c  ldc.i4.1
0xc96d  ldloca.s 0
0xc96f  constrained. [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.SqlServerSkuType
0xc975  callvirt instance string [mscorlib]System.Object::ToString()
0xc97a  stelem.ref
0xc97b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xc980  ldc.i4.1
0xc981  call     void Microsoft.ReportingServices.Diagnostics.SkuResources::ThrowOperationNotSupportedException(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures feature)
0xc986  ldloc.0
0xc987  ret
```
