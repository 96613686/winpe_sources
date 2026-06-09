# System.Deployment.Application.ComponentStore::GetPropertyString

- ea: `0xeb60`
- end: `0xebd9`
- name: `System.Deployment.Application.ComponentStore::GetPropertyString`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0xebe0`
- `0xec60`
- `0xece0`
- `0xed30`
- `0xed80`
- `0xee00`
- `0xee60`

## callees

- `0x2c70`
- `0xd5e0`
- `0xeb60`
- `0xfa10`
- `0x146f0`
- `0x23020`

## pseudocode

```c

```

## disassembly

```asm
0xeb60  ldarg.0
0xeb61  ldfld    class System.Deployment.Internal.Isolation.Store System.Deployment.Application.ComponentStore::_store
0xeb66  ldc.i4.0
0xeb67  ldarg.1
0xeb68  callvirt instance class System.Deployment.Internal.Isolation.IDefinitionAppId System.Deployment.Application.DefinitionAppId::get_ComPointer()
0xeb6d  ldarg.0
0xeb6e  call     instance valuetype System.Deployment.Internal.Isolation.StoreApplicationReference System.Deployment.Application.ComponentStore::get_InstallReference()
0xeb73  ldsfld   valuetype [mscorlib]System.Guid System.Deployment.Application.Constants::DeploymentPropertySet
0xeb78  ldarg.2
0xeb79  callvirt instance unsigned int8[] System.Deployment.Internal.Isolation.Store::GetDeploymentProperty(valuetype GetPackagePropertyFlags Flags, class System.Deployment.Internal.Isolation.IDefinitionAppId Deployment, valuetype System.Deployment.Internal.Isolation.StoreApplicationReference Reference, valuetype [mscorlib]System.Guid PropertySet, string PropertyName)
0xeb7e  stloc.0
0xeb7f  leave.s  loc_EB86
0xeb81  pop
0xeb82  ldnull
0xeb83  stloc.2
0xeb84  leave.s  loc_EBD7
0xeb86  ldloc.0
0xeb87  ldlen
0xeb88  conv.i4
0xeb89  stloc.1
0xeb8a  ldloc.1
0xeb8b  brfalse.s loc_EBA2
0xeb8d  ldloc.0
0xeb8e  ldlen
0xeb8f  conv.i4
0xeb90  ldc.i4.2
0xeb91  rem
0xeb92  brtrue.s loc_EBA2
0xeb94  ldloc.0
0xeb95  ldloc.1
0xeb96  ldc.i4.2
0xeb97  sub
0xeb98  ldelem.u1
0xeb99  brtrue.s loc_EBA2
0xeb9b  ldloc.0
0xeb9c  ldloc.1
0xeb9d  ldc.i4.1
0xeb9e  sub
0xeb9f  ldelem.u1
0xeba0  brfalse.s loc_EBC7
0xeba2  ldc.i4.8
0xeba3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0xeba8  ldstr    aExInvalidstore// "Ex_InvalidStoreMetaData"
0xebad  call     string System.Deployment.Application.Resources::GetString(string s)
0xebb2  ldc.i4.1
0xebb3  newarr   [mscorlib]System.Object
0xebb8  dup
0xebb9  ldc.i4.0
0xebba  ldarg.2
0xebbb  stelem.ref
0xebbc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xebc1  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0xebc6  throw
0xebc7  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Unicode()
0xebcc  ldloc.0
0xebcd  ldc.i4.0
0xebce  ldloc.1
0xebcf  ldc.i4.2
0xebd0  sub
0xebd1  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[], int32, int32)
0xebd6  ret
0xebd7  ldloc.2
0xebd8  ret
```
