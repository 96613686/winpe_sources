# System.Web.Configuration.PagesSection::.cctor

- ea: `0x14f390`
- end: `0x14f880`
- name: `System.Web.Configuration.PagesSection::.cctor`
- size: `1264`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1584b0`
- `0x158510`
- `0x158550`
- `0x15ace0`

## string_xrefs

- `0x14f3c4`: `controlRenderingCompatibilityVersion`
- `0x14f5c2`: `compilationMode`

## pseudocode

```c

```

## disassembly

```asm
0x14f390  ldsfld   class [mscorlib]System.Version System.Web.Util.VersionUtil::FrameworkDefault
0x14f395  stsfld   class [mscorlib]System.Version System.Web.Configuration.PagesSection::_controlRenderingDefaultVersion
0x14f39a  ldsfld   class [mscorlib]System.Version System.Web.Util.VersionUtil::Framework35
0x14f39f  stsfld   class [mscorlib]System.Version System.Web.Configuration.PagesSection::_controlRenderingMinimumVersion
0x14f3a4  ldstr    aBuffer// "buffer"
0x14f3a9  ldtoken  [mscorlib]System.Boolean
0x14f3ae  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f3b3  ldc.i4.1
0x14f3b4  box      [mscorlib]System.Boolean
0x14f3b9  ldc.i4.0
0x14f3ba  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f3bf  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propBuffer
0x14f3c4  ldstr    aControlrenderi// "controlRenderingCompatibilityVersion"
0x14f3c9  ldtoken  [mscorlib]System.Version
0x14f3ce  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f3d3  ldsfld   class [mscorlib]System.Version System.Web.Configuration.PagesSection::_controlRenderingDefaultVersion
0x14f3d8  call     class [System]System.ComponentModel.TypeConverter System.Web.Configuration.StdValidatorsAndConverters::get_VersionConverter()
0x14f3dd  ldsfld   class [mscorlib]System.Version System.Web.Configuration.PagesSection::_controlRenderingMinimumVersion
0x14f3e2  newobj   instance void System.Web.Configuration.VersionValidator::.ctor(class [mscorlib]System.Version minimumVersion)
0x14f3e7  ldc.i4.0
0x14f3e8  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, class [System]System.ComponentModel.TypeConverter, class [System.Configuration]System.Configuration.ConfigurationValidatorBase, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f3ed  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propControlRenderingCompatibilityVersion
0x14f3f2  ldstr    aEnablesessions_1// "enableSessionState"
0x14f3f7  ldtoken  [mscorlib]System.String
0x14f3fc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f401  ldstr    aTrue// "true"
0x14f406  ldc.i4.0
0x14f407  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f40c  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propEnableSessionState
0x14f411  ldstr    aEnableviewstat_1// "enableViewState"
0x14f416  ldtoken  [mscorlib]System.Boolean
0x14f41b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f420  ldc.i4.1
0x14f421  box      [mscorlib]System.Boolean
0x14f426  ldc.i4.0
0x14f427  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f42c  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propEnableViewState
0x14f431  ldstr    aEnableviewstat_2// "enableViewStateMac"
0x14f436  ldtoken  [mscorlib]System.Boolean
0x14f43b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f440  ldc.i4.1
0x14f441  box      [mscorlib]System.Boolean
0x14f446  ldc.i4.0
0x14f447  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f44c  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propEnableViewStateMac
0x14f451  ldstr    aEnableeventval_0// "enableEventValidation"
0x14f456  ldtoken  [mscorlib]System.Boolean
0x14f45b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f460  ldc.i4.1
0x14f461  box      [mscorlib]System.Boolean
0x14f466  ldc.i4.0
0x14f467  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f46c  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propEnableEventValidation
0x14f471  ldstr    aSmartnavigatio_0// "smartNavigation"
0x14f476  ldtoken  [mscorlib]System.Boolean
0x14f47b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f480  ldc.i4.0
0x14f481  box      [mscorlib]System.Boolean
0x14f486  ldc.i4.0
0x14f487  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f48c  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propSmartNavigation
0x14f491  ldstr    aAutoeventwireu_0// "autoEventWireup"
0x14f496  ldtoken  [mscorlib]System.Boolean
0x14f49b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f4a0  ldc.i4.1
0x14f4a1  box      [mscorlib]System.Boolean
0x14f4a6  ldc.i4.0
0x14f4a7  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f4ac  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propAutoEventWireup
0x14f4b1  ldstr    aPagebasetype// "pageBaseType"
0x14f4b6  ldtoken  [mscorlib]System.String
0x14f4bb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f4c0  ldstr    aSystemWebUiPag// "System.Web.UI.Page"
0x14f4c5  ldc.i4.0
0x14f4c6  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f4cb  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propPageBaseType
0x14f4d0  ldstr    aUsercontrolbas// "userControlBaseType"
0x14f4d5  ldtoken  [mscorlib]System.String
0x14f4da  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f4df  ldstr    aSystemWebUiUse// "System.Web.UI.UserControl"
0x14f4e4  ldc.i4.0
0x14f4e5  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f4ea  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propUserControlBaseType
0x14f4ef  ldstr    aValidatereques_1// "validateRequest"
0x14f4f4  ldtoken  [mscorlib]System.Boolean
0x14f4f9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f4fe  ldc.i4.1
0x14f4ff  box      [mscorlib]System.Boolean
0x14f504  ldc.i4.0
0x14f505  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f50a  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propValidateRequest
0x14f50f  ldstr    aMasterpagefile_1// "masterPageFile"
0x14f514  ldtoken  [mscorlib]System.String
0x14f519  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f51e  ldsfld   string [mscorlib]System.String::Empty
0x14f523  ldc.i4.0
0x14f524  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f529  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propMasterPageFile
0x14f52e  ldstr    aTheme_0// "theme"
0x14f533  ldtoken  [mscorlib]System.String
0x14f538  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f53d  ldsfld   string [mscorlib]System.String::Empty
0x14f542  ldc.i4.0
0x14f543  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f548  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propTheme
0x14f54d  ldstr    aNamespaces// "namespaces"
0x14f552  ldtoken  System.Web.Configuration.NamespaceCollection
0x14f557  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f55c  ldnull
0x14f55d  ldc.i4.1
0x14f55e  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f563  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propNamespaces
0x14f568  ldstr    aControls// "controls"
0x14f56d  ldtoken  System.Web.Configuration.TagPrefixCollection
0x14f572  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f577  ldnull
0x14f578  ldc.i4.1
0x14f579  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f57e  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propControls
0x14f583  ldstr    aTagmapping// "tagMapping"
0x14f588  ldtoken  System.Web.Configuration.TagMapCollection
0x14f58d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f592  ldnull
0x14f593  ldc.i4.1
0x14f594  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f599  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propTagMapping
0x14f59e  ldstr    aMaxpagestatefi_0// "maxPageStateFieldLength"
0x14f5a3  ldtoken  [mscorlib]System.Int32
0x14f5a8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f5ad  ldsfld   int32 System.Web.UI.Page::DefaultMaxPageStateFieldLength
0x14f5b2  box      [mscorlib]System.Int32
0x14f5b7  ldc.i4.0
0x14f5b8  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f5bd  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propMaxPageStateFieldLength
0x14f5c2  ldstr    aCompilationmod_0// "compilationMode"
0x14f5c7  ldtoken  System.Web.UI.CompilationMode
0x14f5cc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f5d1  ldc.i4.2
0x14f5d2  box      System.Web.UI.CompilationMode
0x14f5d7  ldc.i4.0
0x14f5d8  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f5dd  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propCompilationMode
0x14f5e2  ldstr    aStylesheetthem_0// "styleSheetTheme"
0x14f5e7  ldtoken  [mscorlib]System.String
0x14f5ec  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f5f1  ldsfld   string [mscorlib]System.String::Empty
0x14f5f6  ldc.i4.0
0x14f5f7  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f5fc  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propStyleSheetTheme
0x14f601  ldstr    aPageparserfilt// "pageParserFilterType"
0x14f606  ldtoken  [mscorlib]System.String
0x14f60b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f610  ldsfld   string [mscorlib]System.String::Empty
0x14f615  ldc.i4.0
0x14f616  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f61b  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propPageParserFilterType
0x14f620  ldstr    aViewstateencry_1// "viewStateEncryptionMode"
0x14f625  ldtoken  System.Web.UI.ViewStateEncryptionMode
0x14f62a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f62f  ldc.i4.0
0x14f630  box      System.Web.UI.ViewStateEncryptionMode
0x14f635  ldc.i4.0
0x14f636  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f63b  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propViewStateEncryptionMode
0x14f640  ldstr    aMaintainscroll// "maintainScrollPositionOnPostBack"
0x14f645  ldtoken  [mscorlib]System.Boolean
0x14f64a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f64f  ldc.i4.0
0x14f650  box      [mscorlib]System.Boolean
0x14f655  ldc.i4.0
0x14f656  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f65b  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propMaintainScrollPosition
0x14f660  ldstr    aAsynctimeout_1// "asyncTimeout"
0x14f665  ldtoken  [mscorlib]System.TimeSpan
0x14f66a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f66f  ldsfld   int32 System.Web.UI.Page::DefaultAsyncTimeoutSeconds
0x14f674  conv.r8
0x14f675  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x14f67a  box      [mscorlib]System.TimeSpan
0x14f67f  call     class [System]System.ComponentModel.TypeConverter System.Web.Configuration.StdValidatorsAndConverters::get_TimeSpanSecondsConverter()
0x14f684  call     class [System.Configuration]System.Configuration.ConfigurationValidatorBase System.Web.Configuration.StdValidatorsAndConverters::get_PositiveTimeSpanValidator()
0x14f689  ldc.i4.0
0x14f68a  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, class [System]System.ComponentModel.TypeConverter, class [System.Configuration]System.Configuration.ConfigurationValidatorBase, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f68f  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propAsyncTimeout
0x14f694  ldstr    aRenderallhidde// "renderAllHiddenFieldsAtTopOfForm"
0x14f699  ldtoken  [mscorlib]System.Boolean
0x14f69e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f6a3  ldc.i4.1
0x14f6a4  box      [mscorlib]System.Boolean
0x14f6a9  ldc.i4.0
0x14f6aa  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f6af  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propRenderAllHiddenFieldsAtTopOfForm
0x14f6b4  ldstr    aClientidmode_0// "clientIDMode"
0x14f6b9  ldtoken  System.Web.UI.ClientIDMode
0x14f6be  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f6c3  ldc.i4.2
0x14f6c4  box      System.Web.UI.ClientIDMode
0x14f6c9  ldc.i4.0
0x14f6ca  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f6cf  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propClientIDMode
0x14f6d4  ldstr    aIgnoredevicefi// "ignoreDeviceFilters"
0x14f6d9  ldtoken  System.Web.Configuration.IgnoreDeviceFilterElementCollection
0x14f6de  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f6e3  ldnull
0x14f6e4  ldc.i4.1
0x14f6e5  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x14f6ea  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propIgnoreDeviceFilters
0x14f6ef  newobj   instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::.ctor()
0x14f6f4  stsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f6f9  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f6fe  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propBuffer
0x14f703  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f708  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f70d  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propControlRenderingCompatibilityVersion
0x14f712  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f717  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f71c  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propEnableSessionState
0x14f721  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f726  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f72b  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propEnableViewState
0x14f730  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f735  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f73a  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propEnableViewStateMac
0x14f73f  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f744  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f749  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propEnableEventValidation
0x14f74e  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f753  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f758  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propSmartNavigation
0x14f75d  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f762  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f767  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propAutoEventWireup
0x14f76c  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f771  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f776  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propPageBaseType
0x14f77b  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f780  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f785  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propUserControlBaseType
0x14f78a  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f78f  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f794  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propValidateRequest
0x14f799  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f79e  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f7a3  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propMasterPageFile
0x14f7a8  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f7ad  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f7b2  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propTheme
0x14f7b7  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f7bc  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f7c1  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propStyleSheetTheme
0x14f7c6  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f7cb  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f7d0  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propNamespaces
0x14f7d5  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f7da  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f7df  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propControls
0x14f7e4  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f7e9  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f7ee  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propTagMapping
0x14f7f3  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f7f8  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f7fd  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propMaxPageStateFieldLength
0x14f802  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f807  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f80c  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propCompilationMode
0x14f811  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f816  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f81b  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propPageParserFilterType
0x14f820  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f825  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f82a  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propViewStateEncryptionMode
0x14f82f  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f834  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f839  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propMaintainScrollPosition
0x14f83e  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f843  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f848  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propAsyncTimeout
0x14f84d  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f852  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f857  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propRenderAllHiddenFieldsAtTopOfForm
0x14f85c  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f861  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f866  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propClientIDMode
0x14f86b  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f870  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.PagesSection::_properties
0x14f875  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.PagesSection::_propIgnoreDeviceFilters
0x14f87a  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x14f87f  ret
```
