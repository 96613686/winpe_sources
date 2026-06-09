# Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::get_ExtensionSettings

- ea: `0x460`
- end: `0x644`
- name: `Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::get_ExtensionSettings`
- size: `484`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x410`
- `0xe10`

## callees

- `0x90`
- `0xa0`
- `0xb0`
- `0xc0`
- `0xd0`
- `0xe0`
- `0xf0`
- `0x460`
- `0x790`

## string_xrefs

- `0x625`: `OverWrite`
- `0x5c0`: `WRITEMODE`

## pseudocode

```c

```

## disassembly

```asm
0x460  ldarg.0
0x461  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x466  brtrue   loc_63D
0x46b  ldarg.0
0x46c  ldc.i4.4
0x46d  newarr   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting
0x472  stfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x477  ldarg.0
0x478  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x47d  ldc.i4.0
0x47e  newobj   instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::.ctor()
0x483  stelem.ref
0x484  ldarg.0
0x485  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x48a  ldc.i4.0
0x48b  ldelem.ref
0x48c  ldstr    aFilename// "FILENAME"
0x491  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Name(string)
0x496  ldarg.0
0x497  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x49c  ldc.i4.0
0x49d  ldelem.ref
0x49e  call     string Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_FileNameSetting()
0x4a3  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_DisplayName(string)
0x4a8  ldarg.0
0x4a9  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x4ae  ldc.i4.0
0x4af  ldelem.ref
0x4b0  ldc.i4.0
0x4b1  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_ReadOnly(bool)
0x4b6  ldarg.0
0x4b7  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x4bc  ldc.i4.0
0x4bd  ldelem.ref
0x4be  ldc.i4.1
0x4bf  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Required(bool)
0x4c4  ldarg.0
0x4c5  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x4ca  ldc.i4.1
0x4cb  newobj   instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::.ctor()
0x4d0  stelem.ref
0x4d1  ldarg.0
0x4d2  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x4d7  ldc.i4.1
0x4d8  ldelem.ref
0x4d9  ldstr    aPath// "PATH"
0x4de  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Name(string)
0x4e3  ldarg.0
0x4e4  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x4e9  ldc.i4.1
0x4ea  ldelem.ref
0x4eb  call     string Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_PathSetting()
0x4f0  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_DisplayName(string)
0x4f5  ldarg.0
0x4f6  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x4fb  ldc.i4.1
0x4fc  ldelem.ref
0x4fd  ldc.i4.0
0x4fe  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_ReadOnly(bool)
0x503  ldarg.0
0x504  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x509  ldc.i4.1
0x50a  ldelem.ref
0x50b  ldc.i4.1
0x50c  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Required(bool)
0x511  ldarg.0
0x512  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x517  ldc.i4.2
0x518  newobj   instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::.ctor()
0x51d  stelem.ref
0x51e  ldarg.0
0x51f  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x524  ldc.i4.2
0x525  ldelem.ref
0x526  ldstr    aRenderFormat// "RENDER_FORMAT"
0x52b  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Name(string)
0x530  ldarg.0
0x531  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x536  ldc.i4.2
0x537  ldelem.ref
0x538  call     string Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_RenderFormatSetting()
0x53d  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_DisplayName(string)
0x542  ldarg.0
0x543  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x548  ldc.i4.2
0x549  ldelem.ref
0x54a  ldc.i4.0
0x54b  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_ReadOnly(bool)
0x550  ldarg.0
0x551  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::get_RenderFormats()
0x556  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Keys()
0x55b  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x560  stloc.0
0x561  br.s     loc_590
0x563  ldloc.0
0x564  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x569  castclass [mscorlib]System.String
0x56e  stloc.1
0x56f  ldarg.0
0x570  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::get_RenderFormats()
0x575  ldloc.1
0x576  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x57b  castclass [mscorlib]System.String
0x580  stloc.2
0x581  ldarg.0
0x582  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x587  ldc.i4.2
0x588  ldelem.ref
0x589  ldloc.2
0x58a  ldloc.1
0x58b  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::AddValidValue(string, string)
0x590  ldloc.0
0x591  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x596  brtrue.s loc_563
0x598  leave.s  loc_5AB
0x59a  ldloc.0
0x59b  isinst   [mscorlib]System.IDisposable
0x5a0  stloc.3
0x5a1  ldloc.3
0x5a2  brfalse.s loc_5AA
0x5a4  ldloc.3
0x5a5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5aa  endfinally
0x5ab  ldarg.0
0x5ac  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x5b1  ldc.i4.3
0x5b2  newobj   instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::.ctor()
0x5b7  stelem.ref
0x5b8  ldarg.0
0x5b9  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x5be  ldc.i4.3
0x5bf  ldelem.ref
0x5c0  ldstr    aWritemode// "WRITEMODE"
0x5c5  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Name(string)
0x5ca  ldarg.0
0x5cb  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x5d0  ldc.i4.3
0x5d1  ldelem.ref
0x5d2  call     string Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_WriteModeSetting()
0x5d7  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_DisplayName(string)
0x5dc  ldarg.0
0x5dd  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x5e2  ldc.i4.3
0x5e3  ldelem.ref
0x5e4  ldc.i4.0
0x5e5  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_ReadOnly(bool)
0x5ea  ldarg.0
0x5eb  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x5f0  ldc.i4.3
0x5f1  ldelem.ref
0x5f2  call     string Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_None()
0x5f7  ldstr    aNone// "None"
0x5fc  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::AddValidValue(string, string)
0x601  ldarg.0
0x602  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x607  ldc.i4.3
0x608  ldelem.ref
0x609  call     string Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_AutoIncrementLabel()
0x60e  ldstr    aAutoincrement// "AutoIncrement"
0x613  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::AddValidValue(string, string)
0x618  ldarg.0
0x619  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x61e  ldc.i4.3
0x61f  ldelem.ref
0x620  call     string Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_OverWrite()
0x625  ldstr    aOverwrite// "OverWrite"
0x62a  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::AddValidValue(string, string)
0x62f  ldarg.0
0x630  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x635  ldc.i4.3
0x636  ldelem.ref
0x637  ldc.i4.0
0x638  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Required(bool)
0x63d  ldarg.0
0x63e  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_settings
0x643  ret
```
