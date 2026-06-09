# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::get_ExtensionSettings

- ea: `0xa30`
- end: `0xdf0`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::get_ExtensionSettings`
- size: `960`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x90`
- `0xa0`
- `0xb0`
- `0xc0`
- `0xd0`
- `0xe0`
- `0xf0`
- `0x790`
- `0xa30`
- `0x3b80`
- `0x3b90`
- `0x3ba0`
- `0x3bc0`
- `0x3bd0`
- `0x3be0`

## string_xrefs

- `0xc03`: `OverWrite`
- `0xb9e`: `WRITEMODE`

## pseudocode

```c

```

## disassembly

```asm
0xa30  ldarg.0
0xa31  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xa36  brtrue   loc_DE9
0xa3b  ldarg.0
0xa3c  ldc.i4.8
0xa3d  newarr   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting
0xa42  stfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xa47  ldarg.0
0xa48  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xa4d  ldc.i4.0
0xa4e  newobj   instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::.ctor()
0xa53  stelem.ref
0xa54  ldarg.0
0xa55  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xa5a  ldc.i4.0
0xa5b  ldelem.ref
0xa5c  ldstr    aFilename// "FILENAME"
0xa61  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Name(string)
0xa66  ldarg.0
0xa67  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xa6c  ldc.i4.0
0xa6d  ldelem.ref
0xa6e  call     string Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_FileNameSetting()
0xa73  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_DisplayName(string)
0xa78  ldarg.0
0xa79  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xa7e  ldc.i4.0
0xa7f  ldelem.ref
0xa80  ldc.i4.0
0xa81  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_ReadOnly(bool)
0xa86  ldarg.0
0xa87  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xa8c  ldc.i4.0
0xa8d  ldelem.ref
0xa8e  ldc.i4.1
0xa8f  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Required(bool)
0xa94  ldarg.0
0xa95  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xa9a  ldc.i4.1
0xa9b  newobj   instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::.ctor()
0xaa0  stelem.ref
0xaa1  ldarg.0
0xaa2  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xaa7  ldc.i4.1
0xaa8  ldelem.ref
0xaa9  ldstr    aPath// "PATH"
0xaae  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Name(string)
0xab3  ldarg.0
0xab4  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xab9  ldc.i4.1
0xaba  ldelem.ref
0xabb  call     string Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_PathSetting()
0xac0  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_DisplayName(string)
0xac5  ldarg.0
0xac6  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xacb  ldc.i4.1
0xacc  ldelem.ref
0xacd  ldc.i4.0
0xace  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_ReadOnly(bool)
0xad3  ldarg.0
0xad4  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xad9  ldc.i4.1
0xada  ldelem.ref
0xadb  ldc.i4.1
0xadc  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Required(bool)
0xae1  ldarg.0
0xae2  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xae7  ldc.i4.2
0xae8  newobj   instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::.ctor()
0xaed  stelem.ref
0xaee  ldarg.0
0xaef  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xaf4  ldc.i4.2
0xaf5  ldelem.ref
0xaf6  ldstr    aRenderFormat// "RENDER_FORMAT"
0xafb  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Name(string)
0xb00  ldarg.0
0xb01  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xb06  ldc.i4.2
0xb07  ldelem.ref
0xb08  call     string Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_RenderFormatSetting()
0xb0d  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_DisplayName(string)
0xb12  ldarg.0
0xb13  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xb18  ldc.i4.2
0xb19  ldelem.ref
0xb1a  ldc.i4.0
0xb1b  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_ReadOnly(bool)
0xb20  ldarg.0
0xb21  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xb26  ldc.i4.2
0xb27  ldelem.ref
0xb28  ldc.i4.1
0xb29  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Required(bool)
0xb2e  ldarg.0
0xb2f  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::get_RenderFormats()
0xb34  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Keys()
0xb39  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0xb3e  stloc.0
0xb3f  br.s     loc_B6E
0xb41  ldloc.0
0xb42  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xb47  castclass [mscorlib]System.String
0xb4c  stloc.1
0xb4d  ldarg.0
0xb4e  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::get_RenderFormats()
0xb53  ldloc.1
0xb54  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xb59  castclass [mscorlib]System.String
0xb5e  stloc.2
0xb5f  ldarg.0
0xb60  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xb65  ldc.i4.2
0xb66  ldelem.ref
0xb67  ldloc.2
0xb68  ldloc.1
0xb69  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::AddValidValue(string, string)
0xb6e  ldloc.0
0xb6f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xb74  brtrue.s loc_B41
0xb76  leave.s  loc_B89
0xb78  ldloc.0
0xb79  isinst   [mscorlib]System.IDisposable
0xb7e  stloc.3
0xb7f  ldloc.3
0xb80  brfalse.s loc_B88
0xb82  ldloc.3
0xb83  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb88  endfinally
0xb89  ldarg.0
0xb8a  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xb8f  ldc.i4.3
0xb90  newobj   instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::.ctor()
0xb95  stelem.ref
0xb96  ldarg.0
0xb97  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xb9c  ldc.i4.3
0xb9d  ldelem.ref
0xb9e  ldstr    aWritemode// "WRITEMODE"
0xba3  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Name(string)
0xba8  ldarg.0
0xba9  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xbae  ldc.i4.3
0xbaf  ldelem.ref
0xbb0  call     string Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_WriteModeSetting()
0xbb5  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_DisplayName(string)
0xbba  ldarg.0
0xbbb  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xbc0  ldc.i4.3
0xbc1  ldelem.ref
0xbc2  ldc.i4.0
0xbc3  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_ReadOnly(bool)
0xbc8  ldarg.0
0xbc9  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xbce  ldc.i4.3
0xbcf  ldelem.ref
0xbd0  call     string Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_None()
0xbd5  ldstr    aNone// "None"
0xbda  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::AddValidValue(string, string)
0xbdf  ldarg.0
0xbe0  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xbe5  ldc.i4.3
0xbe6  ldelem.ref
0xbe7  call     string Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_AutoIncrementLabel()
0xbec  ldstr    aAutoincrement// "AutoIncrement"
0xbf1  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::AddValidValue(string, string)
0xbf6  ldarg.0
0xbf7  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xbfc  ldc.i4.3
0xbfd  ldelem.ref
0xbfe  call     string Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_OverWrite()
0xc03  ldstr    aOverwrite// "OverWrite"
0xc08  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::AddValidValue(string, string)
0xc0d  ldarg.0
0xc0e  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xc13  ldc.i4.3
0xc14  ldelem.ref
0xc15  ldc.i4.0
0xc16  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Required(bool)
0xc1b  ldarg.0
0xc1c  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xc21  ldc.i4.4
0xc22  newobj   instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::.ctor()
0xc27  stelem.ref
0xc28  ldarg.0
0xc29  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xc2e  ldc.i4.4
0xc2f  ldelem.ref
0xc30  ldstr    aFileextn// "FILEEXTN"
0xc35  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Name(string)
0xc3a  ldarg.0
0xc3b  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xc40  ldc.i4.4
0xc41  ldelem.ref
0xc42  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_FileExtensionSetting()
0xc47  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_DisplayName(string)
0xc4c  ldarg.0
0xc4d  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xc52  ldc.i4.4
0xc53  ldelem.ref
0xc54  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_True()
0xc59  ldc.i4.1
0xc5a  stloc.s  4
0xc5c  ldloca.s 4
0xc5e  call     instance string [mscorlib]System.Boolean::ToString()
0xc63  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::AddValidValue(string, string)
0xc68  ldarg.0
0xc69  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xc6e  ldc.i4.4
0xc6f  ldelem.ref
0xc70  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_False()
0xc75  ldc.i4.0
0xc76  stloc.s  4
0xc78  ldloca.s 4
0xc7a  call     instance string [mscorlib]System.Boolean::ToString()
0xc7f  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::AddValidValue(string, string)
0xc84  ldarg.0
0xc85  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xc8a  ldc.i4.4
0xc8b  ldelem.ref
0xc8c  ldc.i4.0
0xc8d  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_ReadOnly(bool)
0xc92  ldarg.0
0xc93  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xc98  ldc.i4.4
0xc99  ldelem.ref
0xc9a  ldc.i4.0
0xc9b  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Required(bool)
0xca0  ldarg.0
0xca1  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xca6  ldc.i4.5
0xca7  newobj   instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::.ctor()
0xcac  stelem.ref
0xcad  ldarg.0
0xcae  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xcb3  ldc.i4.5
0xcb4  ldelem.ref
0xcb5  ldstr    aUsername// "USERNAME"
0xcba  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Name(string)
0xcbf  ldarg.0
0xcc0  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xcc5  ldc.i4.5
0xcc6  ldelem.ref
0xcc7  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_UsernameSetting()
0xccc  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_DisplayName(string)
0xcd1  ldarg.0
0xcd2  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xcd7  ldc.i4.5
0xcd8  ldelem.ref
0xcd9  ldc.i4.0
0xcda  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_ReadOnly(bool)
0xcdf  ldarg.0
0xce0  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xce5  ldc.i4.5
0xce6  ldelem.ref
0xce7  ldc.i4.0
0xce8  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Required(bool)
0xced  ldarg.0
0xcee  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xcf3  ldc.i4.5
0xcf4  ldelem.ref
0xcf5  ldc.i4.1
0xcf6  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Encrypted(bool)
0xcfb  ldarg.0
0xcfc  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xd01  ldc.i4.6
0xd02  newobj   instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::.ctor()
0xd07  stelem.ref
0xd08  ldarg.0
0xd09  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xd0e  ldc.i4.6
0xd0f  ldelem.ref
0xd10  ldstr    aPassword// "PASSWORD"
0xd15  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Name(string)
0xd1a  ldarg.0
0xd1b  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xd20  ldc.i4.6
0xd21  ldelem.ref
0xd22  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_PasswordSetting()
0xd27  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_DisplayName(string)
0xd2c  ldarg.0
0xd2d  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xd32  ldc.i4.6
0xd33  ldelem.ref
0xd34  ldc.i4.0
0xd35  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_ReadOnly(bool)
0xd3a  ldarg.0
0xd3b  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xd40  ldc.i4.6
0xd41  ldelem.ref
0xd42  ldc.i4.0
0xd43  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Required(bool)
0xd48  ldarg.0
0xd49  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
0xd4e  ldc.i4.6
0xd4f  ldelem.ref
0xd50  ldc.i4.1
0xd51  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Encrypted(bool)
0xd56  ldarg.0
0xd57  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::m_settings
  ... truncated ...
```
