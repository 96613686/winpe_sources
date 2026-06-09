# System.Windows.Baml2006.Baml2006Reader::Common_Process_Property

- ea: `0x41800`
- end: `0x4188b`
- name: `System.Windows.Baml2006.Baml2006Reader::Common_Process_Property`
- size: `139`
- prototype: ``
- caller_count: `16`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x406b0`
- `0x40730`
- `0x40850`
- `0x40b30`
- `0x40c10`
- `0x40f90`
- `0x416b0`
- `0x419a0`
- `0x41bd0`
- `0x41cf0`
- `0x42130`
- `0x421f0`
- `0x42490`
- `0x424e0`
- `0x42530`
- `0x42b60`

## callees

- `0x38c40`
- `0x38c70`
- `0x41800`
- `0x42c90`
- `0x43790`
- `0x43830`
- `0x43850`
- `0x43950`
- `0x43970`

## string_xrefs

- `0x41839`: `PropertyFoundOutsideStartElement`

## pseudocode

```c

```

## disassembly

```asm
0x41800  ldarg.0
0x41801  ldfld    class System.Windows.Baml2006.Baml2006ReaderContext System.Windows.Baml2006.Baml2006Reader::_context
0x41806  callvirt instance bool System.Windows.Baml2006.Baml2006ReaderContext::get_InsideKeyRecord()
0x4180b  brtrue.s loc_4181A
0x4180d  ldarg.0
0x4180e  ldfld    class System.Windows.Baml2006.Baml2006ReaderContext System.Windows.Baml2006.Baml2006Reader::_context
0x41813  callvirt instance bool System.Windows.Baml2006.Baml2006ReaderContext::get_InsideStaticResource()
0x41818  brfalse.s loc_4181B
0x4181a  ret
0x4181b  ldarg.0
0x4181c  call     instance void System.Windows.Baml2006.Baml2006Reader::RemoveImplicitFrame()
0x41821  ldarg.0
0x41822  ldfld    class System.Windows.Baml2006.Baml2006ReaderContext System.Windows.Baml2006.Baml2006Reader::_context
0x41827  callvirt instance class System.Windows.Baml2006.Baml2006ReaderFrame System.Windows.Baml2006.Baml2006ReaderContext::get_CurrentFrame()
0x4182c  callvirt instance class [System.Xaml]System.Xaml.XamlType System.Windows.Baml2006.Baml2006ReaderFrame::get_XamlType()
0x41831  ldnull
0x41832  call     bool [System.Xaml]System.Xaml.XamlType::op_Equality(class [System.Xaml]System.Xaml.XamlType, class [System.Xaml]System.Xaml.XamlType)
0x41837  brfalse.s loc_41849
0x41839  ldstr    aPropertyfoundo// "PropertyFoundOutsideStartElement"
0x4183e  call     string System.Windows.SR::Get(string id)
0x41843  newobj   instance void [System.Xaml]System.Xaml.XamlParseException::.ctor(string)
0x41848  throw
0x41849  ldarg.0
0x4184a  ldfld    class System.Windows.Baml2006.Baml2006ReaderContext System.Windows.Baml2006.Baml2006Reader::_context
0x4184f  callvirt instance class System.Windows.Baml2006.Baml2006ReaderFrame System.Windows.Baml2006.Baml2006ReaderContext::get_CurrentFrame()
0x41854  callvirt instance class [System.Xaml]System.Xaml.XamlMember System.Windows.Baml2006.Baml2006ReaderFrame::get_Member()
0x41859  ldnull
0x4185a  call     bool [System.Xaml]System.Xaml.XamlMember::op_Inequality(class [System.Xaml]System.Xaml.XamlMember, class [System.Xaml]System.Xaml.XamlMember)
0x4185f  brfalse.s loc_4188A
0x41861  ldstr    aPropertyoutofo// "PropertyOutOfOrder"
0x41866  ldc.i4.1
0x41867  newarr   [mscorlib]System.Object
0x4186c  dup
0x4186d  ldc.i4.0
0x4186e  ldarg.0
0x4186f  ldfld    class System.Windows.Baml2006.Baml2006ReaderContext System.Windows.Baml2006.Baml2006Reader::_context
0x41874  callvirt instance class System.Windows.Baml2006.Baml2006ReaderFrame System.Windows.Baml2006.Baml2006ReaderContext::get_CurrentFrame()
0x41879  callvirt instance class [System.Xaml]System.Xaml.XamlMember System.Windows.Baml2006.Baml2006ReaderFrame::get_Member()
0x4187e  stelem.ref
0x4187f  call     string System.Windows.SR::Get(string id, object[] args)
0x41884  newobj   instance void [System.Xaml]System.Xaml.XamlParseException::.ctor(string)
0x41889  throw
0x4188a  ret
```
