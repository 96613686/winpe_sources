# Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance::FillInFields

- ea: `0xb310c0`
- end: `0xb31a70`
- name: `Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance::FillInFields`
- size: `2480`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0xb31050`

## callees

- `0xb15b90`
- `0xb19670`
- `0xb1a4a0`
- `0xb1cf40`
- `0xb1cfb0`
- `0xb1dca0`
- `0xb310c0`
- `0xb46870`
- `0xb468b0`
- `0xb69610`

## string_xrefs

- `0xb3163b`: `ApplicationRegistry_MetadataException_Unknown`
- `0xb318a8`: `ApplicationRegistry_MetadataException_Unknown`
- `0xb312bf`: `UpdaterField`
- `0xb312ce`: `UpdaterField`
- `0xb3138c`: `UpdaterField`
- `0xb3139b`: `UpdaterField`
- `0xb3148b`: `PreUpdaterField`
- `0xb3149a`: `PreUpdaterField`
- `0xb31106`: `ApplicationRegistry_Exception_Entity_cs24`
- `0xb3125b`: `ApplicationRegistry_Exception_Entity_CreatorUpdaterMismatch`
- `0xb31427`: `ApplicationRegistry_Exception_Entity_CreatorUpdaterMismatch`
- `0xb31328`: `ApplicationRegistry_Exception_Entity_cs25`
- `0xb315fa`: `ApplicationRegistry_Exception_Entity_cs27`
- `0xb31857`: `ApplicationRegistry_Exception_Entity_cs27`
- `0xb316f8`: `ApplicationRegistry_Exception_Entity_cs26`
- `0xb31761`: `Updater`
- `0xb319e2`: `ApplicationRegistry_Exception_Entity_cs28`

## pseudocode

```c

```

## disassembly

```asm
0xb310c0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.Pair`2<class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor, class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor>>::.ctor()
0xb310c5  stloc.0
0xb310c6  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.Pair`2<class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor, class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor>>::.ctor()
0xb310cb  stloc.1
0xb310cc  ldarg.2
0xb310cd  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IView [Microsoft.BusinessData]Microsoft.BusinessData.Runtime.IFieldValueDictionary::get_ViewDefinition()
0xb310d2  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.Collections.IFieldCollection [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IView::get_Fields()
0xb310d7  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IField>::GetEnumerator()
0xb310dc  stloc.s  0x14
0xb310de  br       loc_B311CA
0xb310e3  ldloc.s  0x14
0xb310e5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IField>::get_Current()
0xb310ea  stloc.2
0xb310eb  ldloc.0
0xb310ec  ldloc.2
0xb310ed  callvirt instance string [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IField::get_Name()
0xb310f2  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.Pair`2<class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor, class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor>>::ContainsKey(var<u1>)
0xb310f7  brfalse  loc_B3119E
0xb310fc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb31101  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb31106  ldstr    aApplicationreg_284// "ApplicationRegistry_Exception_Entity_cs"...
0xb3110b  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb31110  ldc.i4.4
0xb31111  newarr   [mscorlib]System.Object
0xb31116  stloc.s  0x15
0xb31118  ldloc.s  0x15
0xb3111a  ldc.i4.0
0xb3111b  ldloc.2
0xb3111c  callvirt instance string [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IField::get_Name()
0xb31121  stelem.ref
0xb31122  ldloc.s  0x15
0xb31124  ldc.i4.1
0xb31125  ldarg.2
0xb31126  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IView [Microsoft.BusinessData]Microsoft.BusinessData.Runtime.IFieldValueDictionary::get_ViewDefinition()
0xb3112b  castclass Microsoft.SharePoint.BusinessData.MetadataModel.View
0xb31130  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethodInstance Microsoft.SharePoint.BusinessData.MetadataModel.View::get_MethodInstance()
0xb31135  callvirt instance string [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMetadataStruct::get_Name()
0xb3113a  stelem.ref
0xb3113b  ldloc.s  0x15
0xb3113d  ldc.i4.2
0xb3113e  ldarg.2
0xb3113f  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IView [Microsoft.BusinessData]Microsoft.BusinessData.Runtime.IFieldValueDictionary::get_ViewDefinition()
0xb31144  castclass Microsoft.SharePoint.BusinessData.MetadataModel.View
0xb31149  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethodInstance Microsoft.SharePoint.BusinessData.MetadataModel.View::get_MethodInstance()
0xb3114e  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethodInstance::GetMethod()
0xb31153  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IDataClass [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod::GetDataClass()
0xb31158  callvirt instance string [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMetadataStruct::get_Name()
0xb3115d  stelem.ref
0xb3115e  ldloc.s  0x15
0xb31160  ldc.i4.3
0xb31161  ldarg.2
0xb31162  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IView [Microsoft.BusinessData]Microsoft.BusinessData.Runtime.IFieldValueDictionary::get_ViewDefinition()
0xb31167  castclass Microsoft.SharePoint.BusinessData.MetadataModel.View
0xb3116c  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethodInstance Microsoft.SharePoint.BusinessData.MetadataModel.View::get_MethodInstance()
0xb31171  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethodInstance::GetMethod()
0xb31176  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IDataClass [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod::GetDataClass()
0xb3117b  callvirt instance string [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IDataClass::get_Namespace()
0xb31180  stelem.ref
0xb31181  ldloc.s  0x15
0xb31183  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb31188  ldloc.2
0xb31189  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IField::get_TypeDescriptor()
0xb3118e  ldstr    aName_0// "Name"
0xb31193  call     class [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.IExceptionHelper Microsoft.SharePoint.BusinessData.Infrastructure.ExceptionHelper::get_Instance()
0xb31198  newobj   instance void [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.InvalidMetadataObjectException::.ctor(string, class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMetadataObject, string, class [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.IExceptionHelper)
0xb3119d  throw
0xb3119e  ldloc.0
0xb3119f  ldloc.2
0xb311a0  callvirt instance string [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IField::get_Name()
0xb311a5  ldloca.s 0x16
0xb311a7  initobj  valuetype [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.Pair`2<class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor, class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor>
0xb311ad  ldloc.s  0x16
0xb311af  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.Pair`2<class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor, class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor>>::set_Item(var<u1>, !!T0)
0xb311b4  ldloc.1
0xb311b5  ldloc.2
0xb311b6  callvirt instance string [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IField::get_Name()
0xb311bb  ldloca.s 0x17
0xb311bd  initobj  valuetype [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.Pair`2<class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor, class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor>
0xb311c3  ldloc.s  0x17
0xb311c5  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.Pair`2<class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor, class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor>>::set_Item(var<u1>, !!T0)
0xb311ca  ldloc.s  0x14
0xb311cc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xb311d1  brtrue   loc_B310E3
0xb311d6  leave.s  loc_B311E4
0xb311d8  ldloc.s  0x14
0xb311da  brfalse.s loc_B311E3
0xb311dc  ldloc.s  0x14
0xb311de  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb311e3  endfinally
0xb311e4  ldarg.1
0xb311e5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter>::GetEnumerator()
0xb311ea  stloc.s  0x18
0xb311ec  br       loc_B314EC
0xb311f1  ldloc.s  0x18
0xb311f3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter>::get_Current()
0xb311f8  stloc.3
0xb311f9  ldloc.3
0xb311fa  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter::GetRootTypeDescriptor()
0xb311ff  castclass Microsoft.SharePoint.BusinessData.MetadataModel.ITypeDescriptorInternal
0xb31204  ldsfld   class Microsoft.SharePoint.BusinessData.MetadataModel.Filter Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance::CS$<>9__CachedAnonymousMethodDelegate2
0xb31209  brtrue.s loc_B3121C
0xb3120b  ldnull
0xb3120c  ldftn    bool Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance::<FillInFields>b__0(class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor candidate)
0xb31212  newobj   instance void Microsoft.SharePoint.BusinessData.MetadataModel.Filter::.ctor(object object, native int method)
0xb31217  stsfld   class Microsoft.SharePoint.BusinessData.MetadataModel.Filter Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance::CS$<>9__CachedAnonymousMethodDelegate2
0xb3121c  ldsfld   class Microsoft.SharePoint.BusinessData.MetadataModel.Filter Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance::CS$<>9__CachedAnonymousMethodDelegate2
0xb31221  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.Collections.ITypeDescriptorCollection Microsoft.SharePoint.BusinessData.MetadataModel.ITypeDescriptorInternal::GetTypeDescriptorsRecursive(class Microsoft.SharePoint.BusinessData.MetadataModel.Filter filterDelegate)
0xb31226  stloc.s  4
0xb31228  ldloc.s  4
0xb3122a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor>::GetEnumerator()
0xb3122f  stloc.s  0x19
0xb31231  br       loc_B313AB
0xb31236  ldloc.s  0x19
0xb31238  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor>::get_Current()
0xb3123d  stloc.s  5
0xb3123f  ldloc.0
0xb31240  ldloc.s  5
0xb31242  callvirt instance string [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMetadataStruct::get_Name()
0xb31247  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.Pair`2<class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor, class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor>>::ContainsKey(var<u1>)
0xb3124c  brtrue   loc_B312DE
0xb31251  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb31256  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb3125b  ldstr    aApplicationreg_285// "ApplicationRegistry_Exception_Entity_Cr"...
0xb31260  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb31265  ldc.i4.5
0xb31266  newarr   [mscorlib]System.Object
0xb3126b  stloc.s  0x1A
0xb3126d  ldloc.s  0x1A
0xb3126f  ldc.i4.0
0xb31270  ldloc.s  5
0xb31272  callvirt instance string [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMetadataStruct::get_Name()
0xb31277  stelem.ref
0xb31278  ldloc.s  0x1A
0xb3127a  ldc.i4.1
0xb3127b  ldloc.s  5
0xb3127d  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor::GetParameter()
0xb31282  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter::GetMethod()
0xb31287  stelem.ref
0xb31288  ldloc.s  0x1A
0xb3128a  ldc.i4.2
0xb3128b  ldloc.s  5
0xb3128d  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor::GetParameter()
0xb31292  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter::GetMethod()
0xb31297  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IDataClass [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod::GetDataClass()
0xb3129c  callvirt instance string [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IDataClass::get_Namespace()
0xb312a1  stelem.ref
0xb312a2  ldloc.s  0x1A
0xb312a4  ldc.i4.3
0xb312a5  ldloc.s  5
0xb312a7  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor::GetParameter()
0xb312ac  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter::GetMethod()
0xb312b1  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IDataClass [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod::GetDataClass()
0xb312b6  callvirt instance string [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMetadataStruct::get_Name()
0xb312bb  stelem.ref
0xb312bc  ldloc.s  0x1A
0xb312be  ldc.i4.4
0xb312bf  ldstr    aUpdaterfield// "UpdaterField"
0xb312c4  stelem.ref
0xb312c5  ldloc.s  0x1A
0xb312c7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb312cc  ldloc.s  5
0xb312ce  ldstr    aUpdaterfield// "UpdaterField"
0xb312d3  call     class [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.IExceptionHelper Microsoft.SharePoint.BusinessData.Infrastructure.ExceptionHelper::get_Instance()
0xb312d8  newobj   instance void [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.InvalidMetadataObjectException::.ctor(string, class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMetadataObject, string, class [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.IExceptionHelper)
0xb312dd  throw
0xb312de  ldloc.0
0xb312df  ldloc.s  5
0xb312e1  callvirt instance string [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMetadataStruct::get_Name()
0xb312e6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.Pair`2<class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor, class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor>>::get_Item(void)
0xb312eb  stloc.s  6
0xb312ed  ldloca.s 6
0xb312ef  call     instance var<u1> valuetype [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.Pair`2<class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor, class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor>::get_First()
0xb312f4  brtrue.s loc_B3131E
0xb312f6  ldloca.s 6
0xb312f8  call     instance var<u1> valuetype [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.Pair`2<class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor, class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor>::get_Second()
0xb312fd  brtrue.s loc_B3131E
0xb312ff  ldloc.0
0xb31300  ldloc.s  5
0xb31302  callvirt instance string [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMetadataStruct::get_Name()
0xb31307  ldloc.3
0xb31308  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter::GetRootTypeDescriptor()
0xb3130d  ldloc.s  5
0xb3130f  newobj   instance void valuetype [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.Pair`2<class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor, class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor>::.ctor(var<u1>, !!T0)
0xb31314  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.Pair`2<class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor, class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor>>::set_Item(var<u1>, !!T0)
0xb31319  br       loc_B313AB
0xb3131e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb31323  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb31328  ldstr    aApplicationreg_286// "ApplicationRegistry_Exception_Entity_cs"...
0xb3132d  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb31332  ldc.i4.5
0xb31333  newarr   [mscorlib]System.Object
0xb31338  stloc.s  0x1B
0xb3133a  ldloc.s  0x1B
0xb3133c  ldc.i4.0
0xb3133d  ldloc.s  5
0xb3133f  callvirt instance string [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMetadataStruct::get_Name()
0xb31344  stelem.ref
0xb31345  ldloc.s  0x1B
0xb31347  ldc.i4.1
0xb31348  ldloc.s  5
0xb3134a  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor::GetParameter()
0xb3134f  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter::GetMethod()
0xb31354  stelem.ref
0xb31355  ldloc.s  0x1B
0xb31357  ldc.i4.2
0xb31358  ldloc.s  5
0xb3135a  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor::GetParameter()
0xb3135f  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter::GetMethod()
0xb31364  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IDataClass [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod::GetDataClass()
0xb31369  callvirt instance string [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IDataClass::get_Namespace()
0xb3136e  stelem.ref
0xb3136f  ldloc.s  0x1B
0xb31371  ldc.i4.3
0xb31372  ldloc.s  5
0xb31374  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor::GetParameter()
0xb31379  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter::GetMethod()
0xb3137e  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IDataClass [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod::GetDataClass()
0xb31383  callvirt instance string [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMetadataStruct::get_Name()
0xb31388  stelem.ref
0xb31389  ldloc.s  0x1B
0xb3138b  ldc.i4.4
0xb3138c  ldstr    aUpdaterfield// "UpdaterField"
0xb31391  stelem.ref
0xb31392  ldloc.s  0x1B
0xb31394  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb31399  ldloc.s  5
0xb3139b  ldstr    aUpdaterfield// "UpdaterField"
0xb313a0  call     class [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.IExceptionHelper Microsoft.SharePoint.BusinessData.Infrastructure.ExceptionHelper::get_Instance()
0xb313a5  newobj   instance void [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.InvalidMetadataObjectException::.ctor(string, class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMetadataObject, string, class [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.IExceptionHelper)
0xb313aa  throw
0xb313ab  ldloc.s  0x19
0xb313ad  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xb313b2  brtrue   loc_B31236
0xb313b7  leave.s  loc_B313C5
0xb313b9  ldloc.s  0x19
0xb313bb  brfalse.s loc_B313C4
0xb313bd  ldloc.s  0x19
0xb313bf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb313c4  endfinally
0xb313c5  ldloc.3
0xb313c6  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter::GetRootTypeDescriptor()
0xb313cb  castclass Microsoft.SharePoint.BusinessData.MetadataModel.ITypeDescriptorInternal
0xb313d0  ldsfld   class Microsoft.SharePoint.BusinessData.MetadataModel.Filter Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance::CS$<>9__CachedAnonymousMethodDelegate3
0xb313d5  brtrue.s loc_B313E8
0xb313d7  ldnull
0xb313d8  ldftn    bool Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance::<FillInFields>b__1(class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor candidate)
0xb313de  newobj   instance void Microsoft.SharePoint.BusinessData.MetadataModel.Filter::.ctor(object object, native int method)
0xb313e3  stsfld   class Microsoft.SharePoint.BusinessData.MetadataModel.Filter Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance::CS$<>9__CachedAnonymousMethodDelegate3
0xb313e8  ldsfld   class Microsoft.SharePoint.BusinessData.MetadataModel.Filter Microsoft.SharePoint.BusinessData.Runtime.AbstractEntityInstance::CS$<>9__CachedAnonymousMethodDelegate3
0xb313ed  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.Collections.ITypeDescriptorCollection Microsoft.SharePoint.BusinessData.MetadataModel.ITypeDescriptorInternal::GetTypeDescriptorsRecursive(class Microsoft.SharePoint.BusinessData.MetadataModel.Filter filterDelegate)
0xb313f2  stloc.s  4
0xb313f4  ldloc.s  4
0xb313f6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor>::GetEnumerator()
0xb313fb  stloc.s  0x1C
0xb313fd  br       loc_B314D2
0xb31402  ldloc.s  0x1C
0xb31404  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor>::get_Current()
0xb31409  stloc.s  7
0xb3140b  ldloc.0
0xb3140c  ldloc.s  7
0xb3140e  callvirt instance string [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMetadataStruct::get_Name()
0xb31413  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.Pair`2<class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor, class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor>>::ContainsKey(var<u1>)
0xb31418  brtrue   loc_B314AA
0xb3141d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb31422  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb31427  ldstr    aApplicationreg_285// "ApplicationRegistry_Exception_Entity_Cr"...
0xb3142c  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb31431  ldc.i4.5
0xb31432  newarr   [mscorlib]System.Object
0xb31437  stloc.s  0x1D
0xb31439  ldloc.s  0x1D
0xb3143b  ldc.i4.0
0xb3143c  ldloc.s  7
0xb3143e  callvirt instance string [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMetadataStruct::get_Name()
0xb31443  stelem.ref
0xb31444  ldloc.s  0x1D
0xb31446  ldc.i4.1
0xb31447  ldloc.s  7
0xb31449  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor::GetParameter()
0xb3144e  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter::GetMethod()
0xb31453  stelem.ref
0xb31454  ldloc.s  0x1D
0xb31456  ldc.i4.2
0xb31457  ldloc.s  7
0xb31459  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor::GetParameter()
0xb3145e  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter::GetMethod()
0xb31463  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IDataClass [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod::GetDataClass()
0xb31468  callvirt instance string [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IDataClass::get_Namespace()
0xb3146d  stelem.ref
0xb3146e  ldloc.s  0x1D
0xb31470  ldc.i4.3
0xb31471  ldloc.s  7
0xb31473  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor::GetParameter()
0xb31478  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter::GetMethod()
0xb3147d  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IDataClass [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod::GetDataClass()
0xb31482  callvirt instance string [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMetadataStruct::get_Name()
0xb31487  stelem.ref
0xb31488  ldloc.s  0x1D
0xb3148a  ldc.i4.4
0xb3148b  ldstr    aPreupdaterfiel// "PreUpdaterField"
  ... truncated ...
```
