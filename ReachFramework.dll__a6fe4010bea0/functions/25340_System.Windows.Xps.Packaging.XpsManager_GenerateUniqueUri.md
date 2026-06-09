# System.Windows.Xps.Packaging.XpsManager::GenerateUniqueUri

- ea: `0x25340`
- end: `0x25593`
- name: `System.Windows.Xps.Packaging.XpsManager::GenerateUniqueUri`
- size: `595`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1f1a0`
- `0x1f2c0`
- `0x1f720`
- `0x1f840`
- `0x1fa30`
- `0x249a0`

## callees

- `0x20000`
- `0x20010`
- `0x20020`
- `0x25340`
- `0x255a0`
- `0x25810`

## pseudocode

```c

```

## disassembly

```asm
0x25340  ldarg.0
0x25341  ldarg.1
0x25342  call     instance string System.Windows.Xps.Packaging.XpsManager::GetContentCounterKey(class [WindowsBase]MS.Internal.ContentType contentType)
0x25347  stloc.0
0x25348  ldarg.0
0x25349  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_FixedDocumentContentType()
0x2534e  call     instance string System.Windows.Xps.Packaging.XpsManager::GetContentCounterKey(class [WindowsBase]MS.Internal.ContentType contentType)
0x25353  stloc.1
0x25354  ldarg.0
0x25355  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> System.Windows.Xps.Packaging.XpsManager::_contentTypes
0x2535a  ldloc.0
0x2535b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0x25360  stloc.2
0x25361  ldc.i4.0
0x25362  stloc.3
0x25363  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x25368  stloc.s  4
0x2536a  ldarg.0
0x2536b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> System.Windows.Xps.Packaging.XpsManager::_contentTypes
0x25370  ldloc.1
0x25371  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::ContainsKey(var<u1>)
0x25376  brfalse.s loc_25387
0x25378  ldarg.0
0x25379  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> System.Windows.Xps.Packaging.XpsManager::_contentTypes
0x2537e  ldloc.1
0x2537f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0x25384  ldc.i4.1
0x25385  sub
0x25386  stloc.3
0x25387  ldarg.1
0x25388  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_DocumentSequenceContentType()
0x2538d  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0x25392  brfalse.s loc_253B4
0x25394  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x25399  ldstr    a0Fdseq// "{0}.fdseq"
0x2539e  ldc.i4.1
0x2539f  newarr   [mscorlib]System.Object
0x253a4  dup
0x253a5  ldc.i4.0
0x253a6  ldloc.0
0x253a7  stelem.ref
0x253a8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x253ad  stloc.s  5
0x253af  br       loc_25567
0x253b4  ldarg.1
0x253b5  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_FixedDocumentContentType()
0x253ba  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0x253bf  brfalse.s loc_25401
0x253c1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x253c6  ldstr    aDocuments0Fixe// "/Documents/{0}/FixedDocument.fdoc"
0x253cb  ldc.i4.1
0x253cc  newarr   [mscorlib]System.Object
0x253d1  dup
0x253d2  ldc.i4.0
0x253d3  ldloc.2
0x253d4  box      [mscorlib]System.Int32
0x253d9  stelem.ref
0x253da  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x253df  stloc.s  5
0x253e1  ldarg.0
0x253e2  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_FixedPageContentType()
0x253e7  call     instance string System.Windows.Xps.Packaging.XpsManager::GetContentCounterKey(class [WindowsBase]MS.Internal.ContentType contentType)
0x253ec  stloc.s  6
0x253ee  ldarg.0
0x253ef  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> System.Windows.Xps.Packaging.XpsManager::_contentTypes
0x253f4  ldloc.s  6
0x253f6  ldc.i4.1
0x253f7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::set_Item(var<u1>, !!T0)
0x253fc  br       loc_25567
0x25401  ldarg.1
0x25402  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_FixedPageContentType()
0x25407  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0x2540c  brfalse.s loc_2543C
0x2540e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x25413  ldstr    aDocuments0Page// "/Documents/{0}/Pages/{1}.fpage"
0x25418  ldc.i4.2
0x25419  newarr   [mscorlib]System.Object
0x2541e  dup
0x2541f  ldc.i4.0
0x25420  ldloc.3
0x25421  box      [mscorlib]System.Int32
0x25426  stelem.ref
0x25427  dup
0x25428  ldc.i4.1
0x25429  ldloc.2
0x2542a  box      [mscorlib]System.Int32
0x2542f  stelem.ref
0x25430  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x25435  stloc.s  5
0x25437  br       loc_25567
0x2543c  ldloc.0
0x2543d  ldstr    aDictionary// "Dictionary"
0x25442  ldc.i4.5
0x25443  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x25448  brfalse.s loc_25470
0x2544a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2544f  ldstr    aResources0Dict// "/Resources/{0}.dict"
0x25454  ldc.i4.1
0x25455  newarr   [mscorlib]System.Object
0x2545a  dup
0x2545b  ldc.i4.0
0x2545c  ldloc.s  4
0x2545e  box      [mscorlib]System.Guid
0x25463  stelem.ref
0x25464  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x25469  stloc.s  5
0x2546b  br       loc_25567
0x25470  ldloc.0
0x25471  ldstr    aFont// "Font"
0x25476  ldc.i4.5
0x25477  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x2547c  brfalse.s loc_254A4
0x2547e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x25483  ldstr    aResources0Ttf// "/Resources/{0}.ttf"
0x25488  ldc.i4.1
0x25489  newarr   [mscorlib]System.Object
0x2548e  dup
0x2548f  ldc.i4.0
0x25490  ldloc.s  4
0x25492  box      [mscorlib]System.Guid
0x25497  stelem.ref
0x25498  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2549d  stloc.s  5
0x2549f  br       loc_25567
0x254a4  ldloc.0
0x254a5  ldstr    aColorcontext// "ColorContext"
0x254aa  ldc.i4.5
0x254ab  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x254b0  brfalse.s loc_254D8
0x254b2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x254b7  ldstr    aResources0Icc// "/Resources/{0}.icc"
0x254bc  ldc.i4.1
0x254bd  newarr   [mscorlib]System.Object
0x254c2  dup
0x254c3  ldc.i4.0
0x254c4  ldloc.s  4
0x254c6  box      [mscorlib]System.Guid
0x254cb  stelem.ref
0x254cc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x254d1  stloc.s  5
0x254d3  br       loc_25567
0x254d8  ldloc.0
0x254d9  ldstr    aResourcedictio// "ResourceDictionary"
0x254de  ldc.i4.5
0x254df  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x254e4  brfalse.s loc_25509
0x254e6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x254eb  ldstr    aResources0Dict// "/Resources/{0}.dict"
0x254f0  ldc.i4.1
0x254f1  newarr   [mscorlib]System.Object
0x254f6  dup
0x254f7  ldc.i4.0
0x254f8  ldloc.s  4
0x254fa  box      [mscorlib]System.Guid
0x254ff  stelem.ref
0x25500  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x25505  stloc.s  5
0x25507  br.s     loc_25567
0x25509  ldloc.0
0x2550a  ldstr    aImage_0// "Image"
0x2550f  ldc.i4.5
0x25510  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x25515  brfalse.s loc_25543
0x25517  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2551c  ldstr    aResources01// "/Resources/{0}.{1}"
0x25521  ldc.i4.2
0x25522  newarr   [mscorlib]System.Object
0x25527  dup
0x25528  ldc.i4.0
0x25529  ldloc.s  4
0x2552b  box      [mscorlib]System.Guid
0x25530  stelem.ref
0x25531  dup
0x25532  ldc.i4.1
0x25533  ldarg.1
0x25534  call     string System.Windows.Xps.Packaging.XpsManager::LookupImageExtension(class [WindowsBase]MS.Internal.ContentType contentType)
0x25539  stelem.ref
0x2553a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2553f  stloc.s  5
0x25541  br.s     loc_25567
0x25543  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x25548  ldstr    a0S01Xaml// "/{0}s/{0}_{1}.xaml"
0x2554d  ldc.i4.2
0x2554e  newarr   [mscorlib]System.Object
0x25553  dup
0x25554  ldc.i4.0
0x25555  ldloc.0
0x25556  stelem.ref
0x25557  dup
0x25558  ldc.i4.1
0x25559  ldloc.2
0x2555a  box      [mscorlib]System.Int32
0x2555f  stelem.ref
0x25560  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x25565  stloc.s  5
0x25567  ldloc.2
0x25568  ldc.i4.1
0x25569  add
0x2556a  stloc.2
0x2556b  ldarg.0
0x2556c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> System.Windows.Xps.Packaging.XpsManager::_contentTypes
0x25571  ldloc.0
0x25572  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Remove(var<u1>)
0x25577  pop
0x25578  ldarg.0
0x25579  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> System.Windows.Xps.Packaging.XpsManager::_contentTypes
0x2557e  ldloc.0
0x2557f  ldloc.2
0x25580  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::set_Item(var<u1>, !!T0)
0x25585  ldloc.s  5
0x25587  ldc.i4.2
0x25588  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x2558d  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::CreatePartUri(class [System]System.Uri)
0x25592  ret
```
