# System.Windows.Application::LoadComponent

- ea: `0x6300`
- end: `0x6460`
- name: `System.Windows.Application::LoadComponent`
- size: `352`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x6300`
- `0x7960`
- `0x7e40`
- `0x8040`
- `0x8050`
- `0x8060`
- `0x38c40`
- `0x38c70`
- `0x9bc60`
- `0xacd00`
- `0xad220`
- `0xad240`
- `0xb3040`

## string_xrefs

- `0x6303`: `component`
- `0x6358`: `AbsoluteUriNotAllowed`
- `0x6432`: `UriNotMatchWithRootType`

## pseudocode

```c

```

## disassembly

```asm
0x6300  ldarg.0
0x6301  brtrue.s loc_630E
0x6303  ldstr    aComponent// "component"
0x6308  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x630d  throw
0x630e  ldarg.1
0x630f  ldnull
0x6310  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x6315  brfalse.s loc_6322
0x6317  ldstr    aResourcelocato// "resourceLocator"
0x631c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6321  throw
0x6322  ldarg.1
0x6323  callvirt instance string [System]System.Uri::get_OriginalString()
0x6328  brtrue.s loc_6350
0x632a  ldstr    aArgumentproper// "ArgumentPropertyMustNotBeNull"
0x632f  ldc.i4.2
0x6330  newarr   [mscorlib]System.Object
0x6335  dup
0x6336  ldc.i4.0
0x6337  ldstr    aResourcelocato// "resourceLocator"
0x633c  stelem.ref
0x633d  dup
0x633e  ldc.i4.1
0x633f  ldstr    aOriginalstring// "OriginalString"
0x6344  stelem.ref
0x6345  call     string System.Windows.SR::Get(string id, object[] args)
0x634a  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x634f  throw
0x6350  ldarg.1
0x6351  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x6356  brfalse.s loc_6368
0x6358  ldstr    aAbsoluteurinot// "AbsoluteUriNotAllowed"
0x635d  call     string System.Windows.SR::Get(string id)
0x6362  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x6367  throw
0x6368  call     class [System]System.Uri [PresentationCore]System.Windows.Navigation.BaseUriHelper::get_PackAppBaseUri()
0x636d  ldarg.1
0x636e  newobj   instance void [System]System.Uri::.ctor(class [System]System.Uri, class [System]System.Uri)
0x6373  stloc.0
0x6374  newobj   instance void System.Windows.Markup.ParserContext::.ctor()
0x6379  stloc.1
0x637a  ldloc.1
0x637b  ldloc.0
0x637c  callvirt instance void System.Windows.Markup.ParserContext::set_BaseUri(class [System]System.Uri value)
0x6381  ldc.i4.1
0x6382  stloc.2
0x6383  ldnull
0x6384  stloc.3
0x6385  ldloc.0
0x6386  call     bool System.Windows.Application::IsComponentBeingLoadedFromOuterLoadBaml(class [System]System.Uri curComponentUri)
0x638b  brfalse.s loc_63C4
0x638d  ldsfld   class [System]System.Collections.Generic.Stack`1<class System.Windows.NestedBamlLoadInfo> System.Windows.Application::s_NestedBamlLoadInfo
0x6392  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class System.Windows.NestedBamlLoadInfo>::Peek()
0x6397  stloc.s  5
0x6399  ldloc.s  5
0x639b  callvirt instance class [mscorlib]System.IO.Stream System.Windows.NestedBamlLoadInfo::get_BamlStream()
0x63a0  stloc.3
0x63a1  ldloc.3
0x63a2  ldc.i4.0
0x63a3  conv.i8
0x63a4  ldc.i4.0
0x63a5  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x63aa  pop
0x63ab  ldloc.1
0x63ac  ldloc.s  5
0x63ae  callvirt instance bool System.Windows.NestedBamlLoadInfo::get_SkipJournaledProperties()
0x63b3  callvirt instance void System.Windows.Markup.ParserContext::set_SkipJournaledProperties(bool value)
0x63b8  ldloc.s  5
0x63ba  ldnull
0x63bb  callvirt instance void System.Windows.NestedBamlLoadInfo::set_BamlUri(class [System]System.Uri value)
0x63c0  ldc.i4.0
0x63c1  stloc.2
0x63c2  br.s     loc_640D
0x63c4  ldarg.1
0x63c5  call     class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Application::GetResourceOrContentPart(class [System]System.Uri uri)
0x63ca  stloc.s  6
0x63cc  ldloc.s  6
0x63ce  callvirt instance string [WindowsBase]System.IO.Packaging.PackagePart::get_ContentType()
0x63d3  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0x63d8  stloc.s  7
0x63da  ldloc.s  6
0x63dc  callvirt instance class [mscorlib]System.IO.Stream [WindowsBase]System.IO.Packaging.PackagePart::GetStream()
0x63e1  stloc.3
0x63e2  ldc.i4.1
0x63e3  stloc.2
0x63e4  ldsfld   class [WindowsBase]MS.Internal.ContentType [PresentationCore]MS.Internal.MimeTypeMapper::BamlMime
0x63e9  ldloc.s  7
0x63eb  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0x63f0  brtrue.s loc_640D
0x63f2  ldstr    aContenttypenot// "ContentTypeNotSupported"
0x63f7  ldc.i4.1
0x63f8  newarr   [mscorlib]System.Object
0x63fd  dup
0x63fe  ldc.i4.0
0x63ff  ldloc.s  7
0x6401  stelem.ref
0x6402  call     string System.Windows.SR::Get(string id, object[] args)
0x6407  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x640c  throw
0x640d  ldloc.3
0x640e  isinst   System.Windows.Markup.IStreamInfo
0x6413  stloc.s  4
0x6415  ldloc.s  4
0x6417  brfalse.s loc_6432
0x6419  ldloc.s  4
0x641b  callvirt instance class [mscorlib]System.Reflection.Assembly System.Windows.Markup.IStreamInfo::get_Assembly()
0x6420  ldarg.0
0x6421  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x6426  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x642b  call     bool [mscorlib]System.Reflection.Assembly::op_Inequality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x6430  brfalse.s loc_6455
0x6432  ldstr    aUrinotmatchwit// "UriNotMatchWithRootType"
0x6437  ldc.i4.2
0x6438  newarr   [mscorlib]System.Object
0x643d  dup
0x643e  ldc.i4.0
0x643f  ldarg.0
0x6440  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x6445  stelem.ref
0x6446  dup
0x6447  ldc.i4.1
0x6448  ldarg.1
0x6449  stelem.ref
0x644a  call     string System.Windows.SR::Get(string id, object[] args)
0x644f  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x6454  throw
0x6455  ldloc.3
0x6456  ldloc.1
0x6457  ldarg.0
0x6458  ldloc.2
0x6459  call     object System.Windows.Markup.XamlReader::LoadBaml(class [mscorlib]System.IO.Stream stream, class System.Windows.Markup.ParserContext parserContext, object parent, bool closeStream)
0x645e  pop
0x645f  ret
```
