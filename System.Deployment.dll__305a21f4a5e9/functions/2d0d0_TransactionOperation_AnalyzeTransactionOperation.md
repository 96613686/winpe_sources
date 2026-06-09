# TransactionOperation::AnalyzeTransactionOperation

- ea: `0x2d0d0`
- end: `0x2d6c3`
- name: `TransactionOperation::AnalyzeTransactionOperation`
- size: `1523`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2d070`

## callees

- `0xd5b0`
- `0x23020`
- `0x2d0d0`

## string_xrefs

- `0x2d119`: `LogFile_TransactionStageComponent`
- `0x2d16d`: `LogFile_TransactionStageComponentFailure`
- `0x2d39b`: `LogFile_TransactionInstallDeployment`
- `0x2d3ed`: `LogFile_TransactionInstallDeploymentFailure`
- `0x2d470`: `LogFile_TransactionUninstallDeployment`
- `0x2d4c2`: `LogFile_TransactionUninstallDeploymentFailure`
- `0x2d5ea`: `LogFile_TransactionStageComponentFile`
- `0x2d63c`: `LogFile_TransactionStageComponentFileFailure`

## pseudocode

```c

```

## disassembly

```asm
0x2d0d0  ldstr    asc_2F208// ""
0x2d0d5  stloc.0
0x2d0d6  ldarg.1
0x2d0d7  ldfld    valuetype System.Deployment.Internal.Isolation.StoreTransactionOperationType System.Deployment.Internal.Isolation.StoreTransactionOperation::Operation
0x2d0dc  ldc.i4.s 0x14
0x2d0de  bne.un   loc_2D1A1
0x2d0e3  ldarg.1
0x2d0e4  ldfld    valuetype System.Deployment.Internal.Isolation.StoreTransactionData System.Deployment.Internal.Isolation.StoreTransactionOperation::Data
0x2d0e9  ldfld    native int System.Deployment.Internal.Isolation.StoreTransactionData::DataPtr
0x2d0ee  ldtoken  System.Deployment.Internal.Isolation.StoreOperationStageComponent
0x2d0f3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d0f8  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x2d0fd  unbox.any System.Deployment.Internal.Isolation.StoreOperationStageComponent
0x2d102  stloc.1
0x2d103  ldarg.2
0x2d104  stloc.2
0x2d105  ldloca.s 2
0x2d107  constrained. Disposition
0x2d10d  callvirt instance string [mscorlib]System.Object::ToString()
0x2d112  stloc.0
0x2d113  ldarg.0
0x2d114  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x2d119  ldstr    aLogfileTransac_8// "LogFile_TransactionStageComponent"
0x2d11e  call     string System.Deployment.Application.Resources::GetString(string s)
0x2d123  ldc.i4.4
0x2d124  newarr   [mscorlib]System.Object
0x2d129  dup
0x2d12a  ldc.i4.0
0x2d12b  ldloc.1
0x2d12c  box      System.Deployment.Internal.Isolation.StoreOperationStageComponent
0x2d131  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2d136  callvirt instance string [mscorlib]System.Object::ToString()
0x2d13b  stelem.ref
0x2d13c  dup
0x2d13d  ldc.i4.1
0x2d13e  ldloc.0
0x2d13f  stelem.ref
0x2d140  dup
0x2d141  ldc.i4.2
0x2d142  ldarg.3
0x2d143  box      [mscorlib]System.Int32
0x2d148  stelem.ref
0x2d149  dup
0x2d14a  ldc.i4.3
0x2d14b  ldloc.1
0x2d14c  ldfld    string System.Deployment.Internal.Isolation.StoreOperationStageComponent::ManifestPath
0x2d151  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x2d156  stelem.ref
0x2d157  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2d15c  stfld    string TransactionOperation::_message
0x2d161  ldloc.2
0x2d162  brtrue   loc_2D6B8
0x2d167  ldarg.0
0x2d168  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x2d16d  ldstr    aLogfileTransac_9// "LogFile_TransactionStageComponentFailur"...
0x2d172  call     string System.Deployment.Application.Resources::GetString(string s)
0x2d177  ldc.i4.1
0x2d178  newarr   [mscorlib]System.Object
0x2d17d  dup
0x2d17e  ldc.i4.0
0x2d17f  ldloc.1
0x2d180  ldfld    string System.Deployment.Internal.Isolation.StoreOperationStageComponent::ManifestPath
0x2d185  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x2d18a  stelem.ref
0x2d18b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2d190  stfld    string TransactionOperation::_failureMessage
0x2d195  ldarg.0
0x2d196  ldc.i4.1
0x2d197  stfld    bool TransactionOperation::_failed
0x2d19c  br       loc_2D6B8
0x2d1a1  ldarg.1
0x2d1a2  ldfld    valuetype System.Deployment.Internal.Isolation.StoreTransactionOperationType System.Deployment.Internal.Isolation.StoreTransactionOperation::Operation
0x2d1a7  ldc.i4.s 0x15
0x2d1a9  bne.un   loc_2D273
0x2d1ae  ldarg.1
0x2d1af  ldfld    valuetype System.Deployment.Internal.Isolation.StoreTransactionData System.Deployment.Internal.Isolation.StoreTransactionOperation::Data
0x2d1b4  ldfld    native int System.Deployment.Internal.Isolation.StoreTransactionData::DataPtr
0x2d1b9  ldtoken  System.Deployment.Internal.Isolation.StoreOperationPinDeployment
0x2d1be  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d1c3  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x2d1c8  unbox.any System.Deployment.Internal.Isolation.StoreOperationPinDeployment
0x2d1cd  stloc.3
0x2d1ce  ldarg.2
0x2d1cf  stloc.s  4
0x2d1d1  ldloca.s 4
0x2d1d3  constrained. Disposition
0x2d1d9  callvirt instance string [mscorlib]System.Object::ToString()
0x2d1de  stloc.0
0x2d1df  ldloc.3
0x2d1e0  ldfld    class System.Deployment.Internal.Isolation.IDefinitionAppId System.Deployment.Internal.Isolation.StoreOperationPinDeployment::Application
0x2d1e5  newobj   instance void System.Deployment.Application.DefinitionAppId::.ctor(class System.Deployment.Internal.Isolation.IDefinitionAppId idComPtr)
0x2d1ea  stloc.s  5
0x2d1ec  ldarg.0
0x2d1ed  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x2d1f2  ldstr    aLogfileTransac_10// "LogFile_TransactionPinDeployment"
0x2d1f7  call     string System.Deployment.Application.Resources::GetString(string s)
0x2d1fc  ldc.i4.4
0x2d1fd  newarr   [mscorlib]System.Object
0x2d202  dup
0x2d203  ldc.i4.0
0x2d204  ldloc.3
0x2d205  box      System.Deployment.Internal.Isolation.StoreOperationPinDeployment
0x2d20a  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2d20f  callvirt instance string [mscorlib]System.Object::ToString()
0x2d214  stelem.ref
0x2d215  dup
0x2d216  ldc.i4.1
0x2d217  ldloc.0
0x2d218  stelem.ref
0x2d219  dup
0x2d21a  ldc.i4.2
0x2d21b  ldarg.3
0x2d21c  box      [mscorlib]System.Int32
0x2d221  stelem.ref
0x2d222  dup
0x2d223  ldc.i4.3
0x2d224  ldloc.s  5
0x2d226  callvirt instance string [mscorlib]System.Object::ToString()
0x2d22b  stelem.ref
0x2d22c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2d231  stfld    string TransactionOperation::_message
0x2d236  ldloc.s  4
0x2d238  brtrue   loc_2D6B8
0x2d23d  ldarg.0
0x2d23e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x2d243  ldstr    aLogfileTransac_11// "LogFile_TransactionPinDeploymentFailure"
0x2d248  call     string System.Deployment.Application.Resources::GetString(string s)
0x2d24d  ldc.i4.1
0x2d24e  newarr   [mscorlib]System.Object
0x2d253  dup
0x2d254  ldc.i4.0
0x2d255  ldloc.s  5
0x2d257  callvirt instance string [mscorlib]System.Object::ToString()
0x2d25c  stelem.ref
0x2d25d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2d262  stfld    string TransactionOperation::_failureMessage
0x2d267  ldarg.0
0x2d268  ldc.i4.1
0x2d269  stfld    bool TransactionOperation::_failed
0x2d26e  br       loc_2D6B8
0x2d273  ldarg.1
0x2d274  ldfld    valuetype System.Deployment.Internal.Isolation.StoreTransactionOperationType System.Deployment.Internal.Isolation.StoreTransactionOperation::Operation
0x2d279  ldc.i4.s 0x16
0x2d27b  bne.un   loc_2D348
0x2d280  ldarg.1
0x2d281  ldfld    valuetype System.Deployment.Internal.Isolation.StoreTransactionData System.Deployment.Internal.Isolation.StoreTransactionOperation::Data
0x2d286  ldfld    native int System.Deployment.Internal.Isolation.StoreTransactionData::DataPtr
0x2d28b  ldtoken  System.Deployment.Internal.Isolation.StoreOperationUnpinDeployment
0x2d290  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d295  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x2d29a  unbox.any System.Deployment.Internal.Isolation.StoreOperationUnpinDeployment
0x2d29f  stloc.s  6
0x2d2a1  ldarg.2
0x2d2a2  stloc.s  7
0x2d2a4  ldloca.s 7
0x2d2a6  constrained. Disposition
0x2d2ac  callvirt instance string [mscorlib]System.Object::ToString()
0x2d2b1  stloc.0
0x2d2b2  ldloc.s  6
0x2d2b4  ldfld    class System.Deployment.Internal.Isolation.IDefinitionAppId System.Deployment.Internal.Isolation.StoreOperationUnpinDeployment::Application
0x2d2b9  newobj   instance void System.Deployment.Application.DefinitionAppId::.ctor(class System.Deployment.Internal.Isolation.IDefinitionAppId idComPtr)
0x2d2be  stloc.s  8
0x2d2c0  ldarg.0
0x2d2c1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x2d2c6  ldstr    aLogfileTransac_12// "LogFile_TransactionUnPinDeployment"
0x2d2cb  call     string System.Deployment.Application.Resources::GetString(string s)
0x2d2d0  ldc.i4.4
0x2d2d1  newarr   [mscorlib]System.Object
0x2d2d6  dup
0x2d2d7  ldc.i4.0
0x2d2d8  ldloc.s  6
0x2d2da  box      System.Deployment.Internal.Isolation.StoreOperationUnpinDeployment
0x2d2df  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2d2e4  callvirt instance string [mscorlib]System.Object::ToString()
0x2d2e9  stelem.ref
0x2d2ea  dup
0x2d2eb  ldc.i4.1
0x2d2ec  ldloc.0
0x2d2ed  stelem.ref
0x2d2ee  dup
0x2d2ef  ldc.i4.2
0x2d2f0  ldarg.3
0x2d2f1  box      [mscorlib]System.Int32
0x2d2f6  stelem.ref
0x2d2f7  dup
0x2d2f8  ldc.i4.3
0x2d2f9  ldloc.s  8
0x2d2fb  callvirt instance string [mscorlib]System.Object::ToString()
0x2d300  stelem.ref
0x2d301  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2d306  stfld    string TransactionOperation::_message
0x2d30b  ldloc.s  7
0x2d30d  brtrue   loc_2D6B8
0x2d312  ldarg.0
0x2d313  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x2d318  ldstr    aLogfileTransac_13// "LogFile_TransactionUnPinDeploymentFailu"...
0x2d31d  call     string System.Deployment.Application.Resources::GetString(string s)
0x2d322  ldc.i4.1
0x2d323  newarr   [mscorlib]System.Object
0x2d328  dup
0x2d329  ldc.i4.0
0x2d32a  ldloc.s  8
0x2d32c  callvirt instance string [mscorlib]System.Object::ToString()
0x2d331  stelem.ref
0x2d332  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2d337  stfld    string TransactionOperation::_failureMessage
0x2d33c  ldarg.0
0x2d33d  ldc.i4.1
0x2d33e  stfld    bool TransactionOperation::_failed
0x2d343  br       loc_2D6B8
0x2d348  ldarg.1
0x2d349  ldfld    valuetype System.Deployment.Internal.Isolation.StoreTransactionOperationType System.Deployment.Internal.Isolation.StoreTransactionOperation::Operation
0x2d34e  ldc.i4.s 0x18
0x2d350  bne.un   loc_2D41D
0x2d355  ldarg.1
0x2d356  ldfld    valuetype System.Deployment.Internal.Isolation.StoreTransactionData System.Deployment.Internal.Isolation.StoreTransactionOperation::Data
0x2d35b  ldfld    native int System.Deployment.Internal.Isolation.StoreTransactionData::DataPtr
0x2d360  ldtoken  System.Deployment.Internal.Isolation.StoreOperationInstallDeployment
0x2d365  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d36a  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x2d36f  unbox.any System.Deployment.Internal.Isolation.StoreOperationInstallDeployment
0x2d374  stloc.s  9
0x2d376  ldarg.2
0x2d377  stloc.s  0xA
0x2d379  ldloca.s 0xA
0x2d37b  constrained. Disposition
0x2d381  callvirt instance string [mscorlib]System.Object::ToString()
0x2d386  stloc.0
0x2d387  ldloc.s  9
0x2d389  ldfld    class System.Deployment.Internal.Isolation.IDefinitionAppId System.Deployment.Internal.Isolation.StoreOperationInstallDeployment::Application
0x2d38e  newobj   instance void System.Deployment.Application.DefinitionAppId::.ctor(class System.Deployment.Internal.Isolation.IDefinitionAppId idComPtr)
0x2d393  stloc.s  0xB
0x2d395  ldarg.0
0x2d396  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x2d39b  ldstr    aLogfileTransac_14// "LogFile_TransactionInstallDeployment"
0x2d3a0  call     string System.Deployment.Application.Resources::GetString(string s)
0x2d3a5  ldc.i4.4
0x2d3a6  newarr   [mscorlib]System.Object
0x2d3ab  dup
0x2d3ac  ldc.i4.0
0x2d3ad  ldloc.s  9
0x2d3af  box      System.Deployment.Internal.Isolation.StoreOperationInstallDeployment
0x2d3b4  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2d3b9  callvirt instance string [mscorlib]System.Object::ToString()
0x2d3be  stelem.ref
0x2d3bf  dup
0x2d3c0  ldc.i4.1
0x2d3c1  ldloc.0
0x2d3c2  stelem.ref
0x2d3c3  dup
0x2d3c4  ldc.i4.2
0x2d3c5  ldarg.3
0x2d3c6  box      [mscorlib]System.Int32
0x2d3cb  stelem.ref
0x2d3cc  dup
0x2d3cd  ldc.i4.3
0x2d3ce  ldloc.s  0xB
0x2d3d0  callvirt instance string [mscorlib]System.Object::ToString()
0x2d3d5  stelem.ref
0x2d3d6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2d3db  stfld    string TransactionOperation::_message
0x2d3e0  ldloc.s  0xA
0x2d3e2  brtrue   loc_2D6B8
0x2d3e7  ldarg.0
0x2d3e8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x2d3ed  ldstr    aLogfileTransac_15// "LogFile_TransactionInstallDeploymentFai"...
0x2d3f2  call     string System.Deployment.Application.Resources::GetString(string s)
0x2d3f7  ldc.i4.1
0x2d3f8  newarr   [mscorlib]System.Object
0x2d3fd  dup
0x2d3fe  ldc.i4.0
0x2d3ff  ldloc.s  0xB
0x2d401  callvirt instance string [mscorlib]System.Object::ToString()
0x2d406  stelem.ref
0x2d407  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2d40c  stfld    string TransactionOperation::_failureMessage
0x2d411  ldarg.0
0x2d412  ldc.i4.1
0x2d413  stfld    bool TransactionOperation::_failed
0x2d418  br       loc_2D6B8
0x2d41d  ldarg.1
0x2d41e  ldfld    valuetype System.Deployment.Internal.Isolation.StoreTransactionOperationType System.Deployment.Internal.Isolation.StoreTransactionOperation::Operation
0x2d423  ldc.i4.s 0x19
0x2d425  bne.un   loc_2D4F2
0x2d42a  ldarg.1
0x2d42b  ldfld    valuetype System.Deployment.Internal.Isolation.StoreTransactionData System.Deployment.Internal.Isolation.StoreTransactionOperation::Data
0x2d430  ldfld    native int System.Deployment.Internal.Isolation.StoreTransactionData::DataPtr
0x2d435  ldtoken  System.Deployment.Internal.Isolation.StoreOperationUninstallDeployment
0x2d43a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d43f  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x2d444  unbox.any System.Deployment.Internal.Isolation.StoreOperationUninstallDeployment
0x2d449  stloc.s  0xC
0x2d44b  ldarg.2
0x2d44c  stloc.s  0xD
0x2d44e  ldloca.s 0xD
0x2d450  constrained. Disposition
0x2d456  callvirt instance string [mscorlib]System.Object::ToString()
0x2d45b  stloc.0
0x2d45c  ldloc.s  0xC
0x2d45e  ldfld    class System.Deployment.Internal.Isolation.IDefinitionAppId System.Deployment.Internal.Isolation.StoreOperationUninstallDeployment::Application
  ... truncated ...
```
