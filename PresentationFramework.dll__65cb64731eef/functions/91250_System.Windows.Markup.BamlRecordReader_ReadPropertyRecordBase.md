# System.Windows.Markup.BamlRecordReader::ReadPropertyRecordBase

- ea: `0x91250`
- end: `0x9157b`
- name: `System.Windows.Markup.BamlRecordReader::ReadPropertyRecordBase`
- size: `811`
- prototype: ``
- caller_count: `3`
- callee_count: `28`
- tags: `broker_com_uri`

## callers

- `0x90bb0`
- `0x90c00`
- `0x90c60`

## callees

- `0x38c70`
- `0x90fa0`
- `0x91250`
- `0x91580`
- `0x924f0`
- `0x92900`
- `0x933e0`
- `0x93540`
- `0x93560`
- `0x93580`
- `0x935b0`
- `0x938a0`
- `0x93940`
- `0x93bd0`
- `0x93c20`
- `0x93c30`
- `0x93c80`
- `0x93cc0`
- `0x93d60`
- `0x93dc0`
- `0x93e20`
- `0x99910`
- `0xaa9e0`
- `0xaaa40`
- `0xad150`
- `0xad180`
- `0xad490`
- `0xaddb0`

## string_xrefs

- `0x91404`: `ParserCantCreateDelegate`
- `0x91499`: `ParserCantCreateDelegate`

## pseudocode

```c

```

## disassembly

```asm
0x91250  ldarg.0
0x91251  call     instance class System.Windows.Markup.ReaderContextStackData System.Windows.Markup.BamlRecordReader::get_CurrentContext()
0x91256  callvirt instance bool System.Windows.Markup.ReaderContextStackData::get_CreateUsingTypeConverter()
0x9125b  brfalse.s loc_9126A
0x9125d  ldarg.0
0x9125e  call     instance class System.Windows.Markup.ParserContext System.Windows.Markup.BamlRecordReader::get_ParserContext()
0x91263  ldarg.1
0x91264  callvirt instance void System.Windows.Markup.ParserContext::set_XmlSpace(string value)
0x91269  ret
0x9126a  ldarg.0
0x9126b  call     instance object System.Windows.Markup.BamlRecordReader::GetCurrentObjectData()
0x91270  stloc.0
0x91271  ldloca.s 1
0x91273  ldarg.0
0x91274  ldarg.2
0x91275  ldloc.0
0x91276  isinst   [WindowsBase]System.Windows.DependencyObject
0x9127b  ldnull
0x9127c  cgt.un
0x9127e  call     instance void System.Windows.Markup.WpfPropertyDefinition::.ctor(class System.Windows.Markup.BamlRecordReader reader, int16 attributeId, bool targetIsDependencyObject)
0x91283  ldloca.s 1
0x91285  call     instance valuetype System.Windows.Markup.BamlAttributeUsage System.Windows.Markup.WpfPropertyDefinition::get_AttributeUsage()
0x9128a  stloc.2
0x9128b  ldloc.2
0x9128c  ldc.i4.1
0x9128d  sub
0x9128e  switch   loc_912AB, loc_912B9, loc_912A1
0x9129f  br.s     loc_912C5
0x912a1  ldarg.0
0x912a2  ldarg.1
0x912a3  ldloc.0
0x912a4  call     instance void System.Windows.Markup.BamlRecordReader::DoRegisterName(string name, object element)
0x912a9  br.s     loc_912C5
0x912ab  ldarg.0
0x912ac  call     instance class System.Windows.Markup.ParserContext System.Windows.Markup.BamlRecordReader::get_ParserContext()
0x912b1  ldarg.1
0x912b2  callvirt instance void System.Windows.Markup.ParserContext::set_XmlLang(string value)
0x912b7  br.s     loc_912C5
0x912b9  ldarg.0
0x912ba  call     instance class System.Windows.Markup.ParserContext System.Windows.Markup.BamlRecordReader::get_ParserContext()
0x912bf  ldarg.1
0x912c0  callvirt instance void System.Windows.Markup.ParserContext::set_XmlSpace(string value)
0x912c5  ldloca.s 1
0x912c7  call     instance class [WindowsBase]System.Windows.DependencyProperty System.Windows.Markup.WpfPropertyDefinition::get_DependencyProperty()
0x912cc  brfalse.s loc_9130C
0x912ce  ldarg.0
0x912cf  ldloc.0
0x912d0  castclass [WindowsBase]System.Windows.DependencyObject
0x912d5  ldloca.s 1
0x912d7  call     instance class [mscorlib]System.Type System.Windows.Markup.WpfPropertyDefinition::get_PropertyType()
0x912dc  ldloca.s 1
0x912de  call     instance string System.Windows.Markup.WpfPropertyDefinition::get_Name()
0x912e3  ldloca.s 1
0x912e5  call     instance class [WindowsBase]System.Windows.DependencyProperty System.Windows.Markup.WpfPropertyDefinition::get_DependencyProperty()
0x912ea  ldarg.1
0x912eb  ldarg.3
0x912ec  call     instance object System.Windows.Markup.BamlRecordReader::ParseProperty(object element, class [mscorlib]System.Type propertyType, string propertyName, object dpOrPi, string attribValue, int16 converterTypeId)
0x912f1  stloc.3
0x912f2  ldloc.3
0x912f3  ldsfld   object [WindowsBase]System.Windows.DependencyProperty::UnsetValue
0x912f8  beq      loc_91511
0x912fd  ldarg.0
0x912fe  ldloc.0
0x912ff  ldloc.1
0x91300  ldloc.3
0x91301  call     instance bool System.Windows.Markup.BamlRecordReader::SetPropertyValue(object o, valuetype System.Windows.Markup.WpfPropertyDefinition propertyDefinition, object value)
0x91306  pop
0x91307  br       loc_91511
0x9130c  ldloca.s 1
0x9130e  call     instance class [mscorlib]System.Reflection.PropertyInfo System.Windows.Markup.WpfPropertyDefinition::get_PropertyInfo()
0x91313  ldnull
0x91314  call     bool [mscorlib]System.Reflection.PropertyInfo::op_Inequality(class [mscorlib]System.Reflection.PropertyInfo, class [mscorlib]System.Reflection.PropertyInfo)
0x91319  brfalse.s loc_91357
0x9131b  ldarg.0
0x9131c  ldloc.0
0x9131d  ldloca.s 1
0x9131f  call     instance class [mscorlib]System.Type System.Windows.Markup.WpfPropertyDefinition::get_PropertyType()
0x91324  ldloca.s 1
0x91326  call     instance string System.Windows.Markup.WpfPropertyDefinition::get_Name()
0x9132b  ldloca.s 1
0x9132d  call     instance class [mscorlib]System.Reflection.PropertyInfo System.Windows.Markup.WpfPropertyDefinition::get_PropertyInfo()
0x91332  ldarg.1
0x91333  ldarg.3
0x91334  call     instance object System.Windows.Markup.BamlRecordReader::ParseProperty(object element, class [mscorlib]System.Type propertyType, string propertyName, object dpOrPi, string attribValue, int16 converterTypeId)
0x91339  stloc.s  4
0x9133b  ldloc.s  4
0x9133d  ldsfld   object [WindowsBase]System.Windows.DependencyProperty::UnsetValue
0x91342  beq      loc_91511
0x91347  ldarg.0
0x91348  ldloc.0
0x91349  ldloc.1
0x9134a  ldloc.s  4
0x9134c  call     instance bool System.Windows.Markup.BamlRecordReader::SetPropertyValue(object o, valuetype System.Windows.Markup.WpfPropertyDefinition propertyDefinition, object value)
0x91351  pop
0x91352  br       loc_91511
0x91357  ldloca.s 1
0x91359  call     instance class [mscorlib]System.Reflection.MethodInfo System.Windows.Markup.WpfPropertyDefinition::get_AttachedPropertySetter()
0x9135e  ldnull
0x9135f  call     bool [mscorlib]System.Reflection.MethodInfo::op_Inequality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0x91364  brfalse.s loc_913A2
0x91366  ldarg.0
0x91367  ldloc.0
0x91368  ldloca.s 1
0x9136a  call     instance class [mscorlib]System.Type System.Windows.Markup.WpfPropertyDefinition::get_PropertyType()
0x9136f  ldloca.s 1
0x91371  call     instance string System.Windows.Markup.WpfPropertyDefinition::get_Name()
0x91376  ldloca.s 1
0x91378  call     instance class [mscorlib]System.Reflection.MethodInfo System.Windows.Markup.WpfPropertyDefinition::get_AttachedPropertySetter()
0x9137d  ldarg.1
0x9137e  ldarg.3
0x9137f  call     instance object System.Windows.Markup.BamlRecordReader::ParseProperty(object element, class [mscorlib]System.Type propertyType, string propertyName, object dpOrPi, string attribValue, int16 converterTypeId)
0x91384  stloc.s  5
0x91386  ldloc.s  5
0x91388  ldsfld   object [WindowsBase]System.Windows.DependencyProperty::UnsetValue
0x9138d  beq      loc_91511
0x91392  ldarg.0
0x91393  ldloc.0
0x91394  ldloc.1
0x91395  ldloc.s  5
0x91397  call     instance bool System.Windows.Markup.BamlRecordReader::SetPropertyValue(object o, valuetype System.Windows.Markup.WpfPropertyDefinition propertyDefinition, object value)
0x9139c  pop
0x9139d  br       loc_91511
0x913a2  ldc.i4.0
0x913a3  stloc.s  6
0x913a5  ldnull
0x913a6  stloc.s  7
0x913a8  ldc.i4.0
0x913a9  stloc.s  8
0x913ab  ldarg.0
0x913ac  ldfld    class [System.Xaml]System.Windows.Markup.IComponentConnector System.Windows.Markup.BamlRecordReader::_componentConnector
0x913b1  brfalse.s loc_913C8
0x913b3  ldarg.0
0x913b4  ldfld    object System.Windows.Markup.BamlRecordReader::_rootElement
0x913b9  brfalse.s loc_913C8
0x913bb  ldarg.0
0x913bc  ldarg.2
0x913bd  ldloca.s 8
0x913bf  ldloca.s 6
0x913c1  call     instance object System.Windows.Markup.BamlRecordReader::GetREOrEiFromAttributeId(int16 id, [out] bool& isInternal, [out] bool& isRE)
0x913c6  stloc.s  7
0x913c8  ldloc.s  7
0x913ca  brfalse  loc_914FF
0x913cf  ldloc.s  6
0x913d1  brfalse  loc_9146B
0x913d6  ldloc.s  7
0x913d8  isinst   [PresentationCore]System.Windows.RoutedEvent
0x913dd  stloc.s  0xA
0x913df  ldarg.0
0x913e0  call     instance class System.Windows.Markup.ParserContext System.Windows.Markup.BamlRecordReader::get_ParserContext()
0x913e5  ldloc.s  0xA
0x913e7  callvirt instance class [mscorlib]System.Type [PresentationCore]System.Windows.RoutedEvent::get_HandlerType()
0x913ec  ldarg.0
0x913ed  call     instance class System.Windows.Markup.ParserContext System.Windows.Markup.BamlRecordReader::get_ParserContext()
0x913f2  callvirt instance object System.Windows.Markup.ParserContext::get_RootElement()
0x913f7  ldarg.1
0x913f8  call     class [mscorlib]System.Delegate System.Windows.Markup.XamlTypeMapper::CreateDelegate(class System.Windows.Markup.ParserContext pc, class [mscorlib]System.Type delegateType, object target, string handler)
0x913fd  stloc.s  9
0x913ff  ldloc.s  9
0x91401  brtrue.s loc_9141B
0x91403  ldarg.0
0x91404  ldstr    aParsercantcrea// "ParserCantCreateDelegate"
0x91409  ldloc.s  0xA
0x9140b  callvirt instance class [mscorlib]System.Type [PresentationCore]System.Windows.RoutedEvent::get_HandlerType()
0x91410  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x91415  ldarg.1
0x91416  call     instance void System.Windows.Markup.BamlRecordReader::ThrowException(string id, string parameter1, string parameter2)
0x9141b  ldloc.0
0x9141c  isinst   [PresentationCore]System.Windows.UIElement
0x91421  stloc.s  0xB
0x91423  ldloc.s  0xB
0x91425  brfalse.s loc_91437
0x91427  ldloc.s  0xB
0x91429  ldloc.s  0xA
0x9142b  ldloc.s  9
0x9142d  callvirt instance void [PresentationCore]System.Windows.UIElement::AddHandler(class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x91432  br       loc_914FD
0x91437  ldloc.0
0x91438  isinst   [PresentationCore]System.Windows.ContentElement
0x9143d  stloc.s  0xC
0x9143f  ldloc.s  0xC
0x91441  brfalse.s loc_91453
0x91443  ldloc.s  0xC
0x91445  ldloc.s  0xA
0x91447  ldloc.s  9
0x91449  callvirt instance void [PresentationCore]System.Windows.ContentElement::AddHandler(class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x9144e  br       loc_914FD
0x91453  ldloc.0
0x91454  isinst   [PresentationCore]System.Windows.UIElement3D
0x91459  stloc.s  0xD
0x9145b  ldloc.s  0xD
0x9145d  ldloc.s  0xA
0x9145f  ldloc.s  9
0x91461  callvirt instance void [PresentationCore]System.Windows.UIElement3D::AddHandler(class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x91466  br       loc_914FD
0x9146b  ldloc.s  7
0x9146d  isinst   [mscorlib]System.Reflection.EventInfo
0x91472  stloc.s  0xE
0x91474  ldarg.0
0x91475  call     instance class System.Windows.Markup.ParserContext System.Windows.Markup.BamlRecordReader::get_ParserContext()
0x9147a  ldloc.s  0xE
0x9147c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.EventInfo::get_EventHandlerType()
0x91481  ldarg.0
0x91482  call     instance class System.Windows.Markup.ParserContext System.Windows.Markup.BamlRecordReader::get_ParserContext()
0x91487  callvirt instance object System.Windows.Markup.ParserContext::get_RootElement()
0x9148c  ldarg.1
0x9148d  call     class [mscorlib]System.Delegate System.Windows.Markup.XamlTypeMapper::CreateDelegate(class System.Windows.Markup.ParserContext pc, class [mscorlib]System.Type delegateType, object target, string handler)
0x91492  stloc.s  9
0x91494  ldloc.s  9
0x91496  brtrue.s loc_914B0
0x91498  ldarg.0
0x91499  ldstr    aParsercantcrea// "ParserCantCreateDelegate"
0x9149e  ldloc.s  0xE
0x914a0  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.EventInfo::get_EventHandlerType()
0x914a5  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x914aa  ldarg.1
0x914ab  call     instance void System.Windows.Markup.BamlRecordReader::ThrowException(string id, string parameter1, string parameter2)
0x914b0  ldloc.s  8
0x914b2  brfalse.s loc_914F3
0x914b4  ldarg.0
0x914b5  call     instance class System.Windows.Markup.ParserContext System.Windows.Markup.BamlRecordReader::get_ParserContext()
0x914ba  ldarg.0
0x914bb  call     instance class System.Windows.Markup.ParserContext System.Windows.Markup.BamlRecordReader::get_ParserContext()
0x914c0  callvirt instance object System.Windows.Markup.ParserContext::get_RootElement()
0x914c5  ldloc.s  0xE
0x914c7  ldloc.0
0x914c8  ldloc.s  9
0x914ca  call     bool System.Windows.Markup.XamlTypeMapper::AddInternalEventHandler(class System.Windows.Markup.ParserContext pc, object rootElement, class [mscorlib]System.Reflection.EventInfo eventInfo, object target, class [mscorlib]System.Delegate handler)
0x914cf  stloc.s  0xF
0x914d1  ldloc.s  0xF
0x914d3  brtrue.s loc_914FD
0x914d5  ldarg.0
0x914d6  ldstr    aParsercantseta// "ParserCantSetAttribute"
0x914db  ldstr    aEvent// "event"
0x914e0  ldloc.s  0xE
0x914e2  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x914e7  ldstr    aAdd// "add"
0x914ec  call     instance void System.Windows.Markup.BamlRecordReader::ThrowException(string id, string parameter1, string parameter2, string parameter3)
0x914f1  br.s     loc_914FD
0x914f3  ldloc.s  0xE
0x914f5  ldloc.0
0x914f6  ldloc.s  9
0x914f8  callvirt instance void [mscorlib]System.Reflection.EventInfo::AddEventHandler(object, class [mscorlib]System.Delegate)
0x914fd  leave.s  loc_9157A
0x914ff  ldarg.0
0x91500  ldstr    aParsercantgetd// "ParserCantGetDPOrPi"
0x91505  ldloca.s 1
0x91507  call     instance string System.Windows.Markup.WpfPropertyDefinition::get_Name()
0x9150c  call     instance void System.Windows.Markup.BamlRecordReader::ThrowException(string id, string parameter)
0x91511  leave.s  loc_9157A
0x91513  stloc.s  0x10
0x91515  ldloc.s  0x10
0x91517  call     bool [WindowsBase]MS.Internal.CriticalExceptions::IsCriticalException(class [mscorlib]System.Exception)
0x9151c  brtrue.s loc_91527
0x9151e  ldloc.s  0x10
0x91520  isinst   System.Windows.Markup.XamlParseException
0x91525  brfalse.s loc_91529
0x91527  rethrow
0x91529  ldloc.s  0x10
0x9152b  isinst   [mscorlib]System.Reflection.TargetInvocationException
0x91530  stloc.s  0x11
0x91532  ldloc.s  0x11
0x91534  brfalse.s loc_9153F
0x91536  ldloc.s  0x11
0x91538  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x9153d  stloc.s  0x10
0x9153f  ldarg.0
0x91540  ldstr    aParsercannotse// "ParserCannotSetValue"
0x91545  ldc.i4.3
0x91546  newarr   [mscorlib]System.Object
0x9154b  dup
0x9154c  ldc.i4.0
0x9154d  ldloc.0
0x9154e  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x91553  callvirt instance string [mscorlib]System.Type::get_FullName()
0x91558  stelem.ref
0x91559  dup
0x9155a  ldc.i4.1
0x9155b  ldloca.s 1
0x9155d  call     instance class System.Windows.Markup.BamlAttributeInfoRecord System.Windows.Markup.WpfPropertyDefinition::get_AttributeInfo()
0x91562  callvirt instance string System.Windows.Markup.BamlAttributeInfoRecord::get_Name()
0x91567  stelem.ref
0x91568  dup
0x91569  ldc.i4.2
0x9156a  ldarg.1
0x9156b  stelem.ref
0x9156c  call     string System.Windows.SR::Get(string id, object[] args)
0x91571  ldloc.s  0x10
0x91573  call     instance void System.Windows.Markup.BamlRecordReader::ThrowExceptionWithLine(string message, class [mscorlib]System.Exception innerException)
0x91578  leave.s  loc_9157A
0x9157a  ret
```
