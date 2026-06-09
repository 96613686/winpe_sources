# InRecordTryAttributes::WriteStartMember

- ea: `0x2d4c0`
- end: `0x2d67b`
- name: `InRecordTryAttributes::WriteStartMember`
- size: `443`
- prototype: ``
- caller_count: `0`
- callee_count: `36`
- tags: ``

## callees

- `0x8860`
- `0x8b20`
- `0x8b80`
- `0x8be0`
- `0xa590`
- `0xa6c0`
- `0xa6e0`
- `0xa6f0`
- `0xb280`
- `0xd0f0`
- `0xd110`
- `0xd130`
- `0xd1a0`
- `0xd370`
- `0xefa0`
- `0xf950`
- `0xfb90`
- `0xfc40`
- `0xfd40`
- `0xfdf0`
- `0x11f20`
- `0x2cb10`
- `0x2cb20`
- `0x2cb40`
- `0x2cb80`
- `0x2cd20`
- `0x2cd90`
- `0x2ce10`
- `0x2d1d0`
- `0x2d490`
- `0x2d4c0`
- `0x2d6d0`
- `0x2dde0`
- `0x2e0f0`
- `0x2e4c0`
- `0x2ebe0`

## pseudocode

```c

```

## disassembly

```asm
0x2d4c0  ldarg.1
0x2d4c1  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d4c6  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0x2d4cb  callvirt instance class System.Xaml.XamlType Frame::get_Type()
0x2d4d0  stloc.0
0x2d4d1  ldarg.2
0x2d4d2  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Items()
0x2d4d7  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x2d4dc  brfalse.s loc_2D4EF
0x2d4de  ldloc.0
0x2d4df  ldnull
0x2d4e0  call     bool System.Xaml.XamlType::op_Inequality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x2d4e5  brfalse.s loc_2D4EF
0x2d4e7  ldloc.0
0x2d4e8  callvirt instance bool System.Xaml.XamlType::get_IsWhitespaceSignificantCollection()
0x2d4ed  brtrue.s loc_2D4FC
0x2d4ef  ldarg.2
0x2d4f0  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_UnknownContent()
0x2d4f5  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x2d4fa  brfalse.s loc_2D503
0x2d4fc  ldarg.1
0x2d4fd  ldc.i4.1
0x2d4fe  stfld    bool System.Xaml.XamlXmlWriter::isFirstElementOfWhitespaceSignificantCollection
0x2d503  ldarg.2
0x2d504  callvirt instance bool System.Xaml.XamlMember::get_IsAttachable()
0x2d509  brtrue.s loc_2D513
0x2d50b  ldarg.2
0x2d50c  callvirt instance bool System.Xaml.XamlMember::get_IsDirective()
0x2d511  brfalse.s loc_2D54F
0x2d513  ldarg.1
0x2d514  ldarg.2
0x2d515  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> System.Xaml.XamlMember::GetXamlNamespaces()
0x2d51a  ldloca.s 2
0x2d51c  callvirt instance string System.Xaml.XamlXmlWriter::LookupPrefix(class [mscorlib]System.Collections.Generic.IList`1<string> namespaces, [out] string& chosenNamespace)
0x2d521  stloc.3
0x2d522  ldloc.3
0x2d523  brfalse.s loc_2D52F
0x2d525  ldarg.1
0x2d526  ldloc.2
0x2d527  ldloc.3
0x2d528  callvirt instance bool System.Xaml.XamlXmlWriter::IsShadowed(string ns, string prefix)
0x2d52d  brfalse.s loc_2D54F
0x2d52f  ldarg.1
0x2d530  call     class WriterState InRecord::get_State()
0x2d535  stfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d53a  ldarg.1
0x2d53b  ldc.i4.1
0x2d53c  callvirt instance void System.Xaml.XamlXmlWriter::WriteDeferredNamespaces(valuetype System.Xaml.XamlNodeType nodeType)
0x2d541  ldarg.1
0x2d542  ldfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d547  ldarg.1
0x2d548  ldarg.2
0x2d549  callvirt instance void WriterState::WriteStartMember(class System.Xaml.XamlXmlWriter writer, class System.Xaml.XamlMember property)
0x2d54e  ret
0x2d54f  ldarg.1
0x2d550  ldarg.2
0x2d551  callvirt instance void System.Xaml.XamlXmlWriter::CheckMemberForUniqueness(class System.Xaml.XamlMember property)
0x2d556  ldarg.1
0x2d557  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d55c  newobj   instance void Frame::.ctor()
0x2d561  dup
0x2d562  ldc.i4.4
0x2d563  callvirt instance void Frame::set_AllocatingNodeType(valuetype System.Xaml.XamlNodeType value)
0x2d568  dup
0x2d569  ldarg.1
0x2d56a  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d56f  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0x2d574  callvirt instance class System.Xaml.XamlType Frame::get_Type()
0x2d579  callvirt instance void Frame::set_Type(class System.Xaml.XamlType value)
0x2d57e  dup
0x2d57f  ldarg.2
0x2d580  callvirt instance void Frame::set_Member(class System.Xaml.XamlMember value)
0x2d585  callvirt instance void class [System]System.Collections.Generic.Stack`1<class Frame>::Push(var<u1>)
0x2d58a  ldarg.1
0x2d58b  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d590  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0x2d595  callvirt instance class System.Xaml.XamlType Frame::get_Type()
0x2d59a  stloc.1
0x2d59b  ldarg.2
0x2d59c  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_PositionalParameters()
0x2d5a1  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x2d5a6  brfalse.s loc_2D5F1
0x2d5a8  ldarg.1
0x2d5a9  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d5ae  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Pop()
0x2d5b3  pop
0x2d5b4  ldloc.1
0x2d5b5  ldnull
0x2d5b6  call     bool System.Xaml.XamlType::op_Inequality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x2d5bb  brfalse.s loc_2D5D5
0x2d5bd  ldloc.1
0x2d5be  callvirt instance bool System.Xaml.XamlType::get_ConstructionRequiresArguments()
0x2d5c3  brfalse.s loc_2D5D5
0x2d5c5  ldstr    aExpandposition// "ExpandPositionalParametersinTypeWithNoD"...
0x2d5ca  call     string System.Xaml.SR::Get(string id)
0x2d5cf  newobj   instance void System.Xaml.XamlXmlWriterException::.ctor(string message)
0x2d5d4  throw
0x2d5d5  ldarg.1
0x2d5d6  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2d5db  call     class WriterState InRecordTryAttributes::get_State()
0x2d5e0  callvirt instance void PositionalParameterStateInfo::set_ReturnState(class WriterState value)
0x2d5e5  ldarg.1
0x2d5e6  call     class WriterState ExpandPositionalParameters::get_State()
0x2d5eb  stfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d5f0  ret
0x2d5f1  ldarg.2
0x2d5f2  call     bool System.Xaml.XamlXmlWriter::IsImplicit(class System.Xaml.XamlMember xamlMember)
0x2d5f7  brfalse.s loc_2D60C
0x2d5f9  ldarg.1
0x2d5fa  ldc.i4.1
0x2d5fb  callvirt instance void System.Xaml.XamlXmlWriter::WriteDeferredNamespaces(valuetype System.Xaml.XamlNodeType nodeType)
0x2d600  ldarg.1
0x2d601  call     class WriterState InMember::get_State()
0x2d606  stfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d60b  ret
0x2d60c  ldarg.2
0x2d60d  ldloc.1
0x2d60e  callvirt instance class System.Xaml.XamlMember System.Xaml.XamlType::get_ContentProperty()
0x2d613  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x2d618  brfalse.s loc_2D626
0x2d61a  ldarg.1
0x2d61b  call     class WriterState TryContentPropertyInTryAttributesState::get_State()
0x2d620  stfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d625  ret
0x2d626  ldarg.2
0x2d627  callvirt instance bool System.Xaml.XamlMember::get_IsDirective()
0x2d62c  brfalse.s loc_2D66F
0x2d62e  ldarg.2
0x2d62f  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_Type()
0x2d634  ldnull
0x2d635  call     bool System.Xaml.XamlType::op_Inequality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x2d63a  brfalse.s loc_2D66F
0x2d63c  ldarg.2
0x2d63d  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_Type()
0x2d642  callvirt instance bool System.Xaml.XamlType::get_IsCollection()
0x2d647  brtrue.s loc_2D656
0x2d649  ldarg.2
0x2d64a  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_Type()
0x2d64f  callvirt instance bool System.Xaml.XamlType::get_IsDictionary()
0x2d654  brfalse.s loc_2D66F
0x2d656  ldarg.1
0x2d657  ldc.i4.1
0x2d658  callvirt instance void System.Xaml.XamlXmlWriter::WriteDeferredNamespaces(valuetype System.Xaml.XamlNodeType nodeType)
0x2d65d  ldarg.1
0x2d65e  call     void WriterState::WriteMemberAsElement(class System.Xaml.XamlXmlWriter writer)
0x2d663  ldarg.1
0x2d664  call     class WriterState InMember::get_State()
0x2d669  stfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d66e  ret
0x2d66f  ldarg.1
0x2d670  call     class WriterState InMemberTryAttributes::get_State()
0x2d675  stfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d67a  ret
```
