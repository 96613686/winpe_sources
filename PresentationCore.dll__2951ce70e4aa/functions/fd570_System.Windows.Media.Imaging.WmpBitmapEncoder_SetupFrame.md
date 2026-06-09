# System.Windows.Media.Imaging.WmpBitmapEncoder::SetupFrame

- ea: `0xfd570`
- end: `0xfda0b`
- name: `System.Windows.Media.Imaging.WmpBitmapEncoder::SetupFrame`
- size: `1179`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0xf37c0`
- `0xf37d0`
- `0xfbce0`
- `0xfc280`
- `0xfd570`
- `0x106440`
- `0x153830`
- `0x153a50`

## string_xrefs

- `0xfd8ec`: `CompressedDomainTranscode`

## pseudocode

```c

```

## disassembly

```asm
0xfd570  ldloca.s 1
0xfd572  initobj  System.Windows.Media.Imaging.PROPBAG2
0xfd578  ldloca.s 0
0xfd57a  initobj  System.Windows.Media.Imaging.PROPVARIANT
0xfd580  ldarg.0
0xfd581  ldfld    float32 System.Windows.Media.Imaging.WmpBitmapEncoder::_imagequalitylevel
0xfd586  ldc.r4   0.89999998
0xfd58b  beq.s    loc_FD5CD
0xfd58d  ldloca.s 1
0xfd58f  ldstr    aImagequality// "ImageQuality"
0xfd594  call     instance void System.Windows.Media.Imaging.PROPBAG2::Init(string name)
0xfd599  ldloca.s 0
0xfd59b  ldarg.0
0xfd59c  ldfld    float32 System.Windows.Media.Imaging.WmpBitmapEncoder::_imagequalitylevel
0xfd5a1  conv.r4
0xfd5a2  box      [mscorlib]System.Single
0xfd5a7  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Init(object value)
0xfd5ac  ldarg.2
0xfd5ad  ldc.i4.1
0xfd5ae  ldloca.s 1
0xfd5b0  ldloca.s 0
0xfd5b2  call     int32 IPropertyBag2::Write(class System.Windows.Media.SafeMILHandle THIS_PTR, unsigned int32 cProperties, valuetype System.Windows.Media.Imaging.PROPBAG2& propBag, valuetype System.Windows.Media.Imaging.PROPVARIANT& propValue)
0xfd5b7  call     void MS.Internal.HRESULT::Check(int32 hr)
0xfd5bc  leave.s  loc_FD5CD
0xfd5be  ldloca.s 1
0xfd5c0  call     instance void System.Windows.Media.Imaging.PROPBAG2::Clear()
0xfd5c5  ldloca.s 0
0xfd5c7  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Clear()
0xfd5cc  endfinally
0xfd5cd  ldarg.0
0xfd5ce  ldfld    valuetype MS.Internal.WICBitmapTransformOptions System.Windows.Media.Imaging.WmpBitmapEncoder::_transformation
0xfd5d3  brfalse.s loc_FD615
0xfd5d5  ldloca.s 1
0xfd5d7  ldstr    aBitmaptransfor// "BitmapTransform"
0xfd5dc  call     instance void System.Windows.Media.Imaging.PROPBAG2::Init(string name)
0xfd5e1  ldloca.s 0
0xfd5e3  ldarg.0
0xfd5e4  ldfld    valuetype MS.Internal.WICBitmapTransformOptions System.Windows.Media.Imaging.WmpBitmapEncoder::_transformation
0xfd5e9  conv.u1
0xfd5ea  box      [mscorlib]System.Byte
0xfd5ef  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Init(object value)
0xfd5f4  ldarg.2
0xfd5f5  ldc.i4.1
0xfd5f6  ldloca.s 1
0xfd5f8  ldloca.s 0
0xfd5fa  call     int32 IPropertyBag2::Write(class System.Windows.Media.SafeMILHandle THIS_PTR, unsigned int32 cProperties, valuetype System.Windows.Media.Imaging.PROPBAG2& propBag, valuetype System.Windows.Media.Imaging.PROPVARIANT& propValue)
0xfd5ff  call     void MS.Internal.HRESULT::Check(int32 hr)
0xfd604  leave.s  loc_FD615
0xfd606  ldloca.s 1
0xfd608  call     instance void System.Windows.Media.Imaging.PROPBAG2::Clear()
0xfd60d  ldloca.s 0
0xfd60f  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Clear()
0xfd614  endfinally
0xfd615  ldarg.0
0xfd616  ldfld    bool System.Windows.Media.Imaging.WmpBitmapEncoder::_lossless
0xfd61b  brfalse.s loc_FD65C
0xfd61d  ldloca.s 1
0xfd61f  ldstr    aLossless// "Lossless"
0xfd624  call     instance void System.Windows.Media.Imaging.PROPBAG2::Init(string name)
0xfd629  ldloca.s 0
0xfd62b  ldarg.0
0xfd62c  ldfld    bool System.Windows.Media.Imaging.WmpBitmapEncoder::_lossless
0xfd631  box      [mscorlib]System.Boolean
0xfd636  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Init(object value)
0xfd63b  ldarg.2
0xfd63c  ldc.i4.1
0xfd63d  ldloca.s 1
0xfd63f  ldloca.s 0
0xfd641  call     int32 IPropertyBag2::Write(class System.Windows.Media.SafeMILHandle THIS_PTR, unsigned int32 cProperties, valuetype System.Windows.Media.Imaging.PROPBAG2& propBag, valuetype System.Windows.Media.Imaging.PROPVARIANT& propValue)
0xfd646  call     void MS.Internal.HRESULT::Check(int32 hr)
0xfd64b  leave.s  loc_FD65C
0xfd64d  ldloca.s 1
0xfd64f  call     instance void System.Windows.Media.Imaging.PROPBAG2::Clear()
0xfd654  ldloca.s 0
0xfd656  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Clear()
0xfd65b  endfinally
0xfd65c  ldarg.0
0xfd65d  ldfld    bool System.Windows.Media.Imaging.WmpBitmapEncoder::_usecodecoptions
0xfd662  brfalse.s loc_FD6A3
0xfd664  ldloca.s 1
0xfd666  ldstr    aUsecodecoption// "UseCodecOptions"
0xfd66b  call     instance void System.Windows.Media.Imaging.PROPBAG2::Init(string name)
0xfd670  ldloca.s 0
0xfd672  ldarg.0
0xfd673  ldfld    bool System.Windows.Media.Imaging.WmpBitmapEncoder::_usecodecoptions
0xfd678  box      [mscorlib]System.Boolean
0xfd67d  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Init(object value)
0xfd682  ldarg.2
0xfd683  ldc.i4.1
0xfd684  ldloca.s 1
0xfd686  ldloca.s 0
0xfd688  call     int32 IPropertyBag2::Write(class System.Windows.Media.SafeMILHandle THIS_PTR, unsigned int32 cProperties, valuetype System.Windows.Media.Imaging.PROPBAG2& propBag, valuetype System.Windows.Media.Imaging.PROPVARIANT& propValue)
0xfd68d  call     void MS.Internal.HRESULT::Check(int32 hr)
0xfd692  leave.s  loc_FD6A3
0xfd694  ldloca.s 1
0xfd696  call     instance void System.Windows.Media.Imaging.PROPBAG2::Clear()
0xfd69b  ldloca.s 0
0xfd69d  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Clear()
0xfd6a2  endfinally
0xfd6a3  ldarg.0
0xfd6a4  ldfld    unsigned int8 System.Windows.Media.Imaging.WmpBitmapEncoder::_qualitylevel
0xfd6a9  ldc.i4.s 0xA
0xfd6ab  beq.s    loc_FD6EC
0xfd6ad  ldloca.s 1
0xfd6af  ldstr    aQuality// "Quality"
0xfd6b4  call     instance void System.Windows.Media.Imaging.PROPBAG2::Init(string name)
0xfd6b9  ldloca.s 0
0xfd6bb  ldarg.0
0xfd6bc  ldfld    unsigned int8 System.Windows.Media.Imaging.WmpBitmapEncoder::_qualitylevel
0xfd6c1  box      [mscorlib]System.Byte
0xfd6c6  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Init(object value)
0xfd6cb  ldarg.2
0xfd6cc  ldc.i4.1
0xfd6cd  ldloca.s 1
0xfd6cf  ldloca.s 0
0xfd6d1  call     int32 IPropertyBag2::Write(class System.Windows.Media.SafeMILHandle THIS_PTR, unsigned int32 cProperties, valuetype System.Windows.Media.Imaging.PROPBAG2& propBag, valuetype System.Windows.Media.Imaging.PROPVARIANT& propValue)
0xfd6d6  call     void MS.Internal.HRESULT::Check(int32 hr)
0xfd6db  leave.s  loc_FD6EC
0xfd6dd  ldloca.s 1
0xfd6df  call     instance void System.Windows.Media.Imaging.PROPBAG2::Clear()
0xfd6e4  ldloca.s 0
0xfd6e6  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Clear()
0xfd6eb  endfinally
0xfd6ec  ldarg.0
0xfd6ed  ldfld    unsigned int8 System.Windows.Media.Imaging.WmpBitmapEncoder::_subsamplinglevel
0xfd6f2  ldc.i4.3
0xfd6f3  beq.s    loc_FD734
0xfd6f5  ldloca.s 1
0xfd6f7  ldstr    aSubsampling// "Subsampling"
0xfd6fc  call     instance void System.Windows.Media.Imaging.PROPBAG2::Init(string name)
0xfd701  ldloca.s 0
0xfd703  ldarg.0
0xfd704  ldfld    unsigned int8 System.Windows.Media.Imaging.WmpBitmapEncoder::_subsamplinglevel
0xfd709  box      [mscorlib]System.Byte
0xfd70e  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Init(object value)
0xfd713  ldarg.2
0xfd714  ldc.i4.1
0xfd715  ldloca.s 1
0xfd717  ldloca.s 0
0xfd719  call     int32 IPropertyBag2::Write(class System.Windows.Media.SafeMILHandle THIS_PTR, unsigned int32 cProperties, valuetype System.Windows.Media.Imaging.PROPBAG2& propBag, valuetype System.Windows.Media.Imaging.PROPVARIANT& propValue)
0xfd71e  call     void MS.Internal.HRESULT::Check(int32 hr)
0xfd723  leave.s  loc_FD734
0xfd725  ldloca.s 1
0xfd727  call     instance void System.Windows.Media.Imaging.PROPBAG2::Clear()
0xfd72c  ldloca.s 0
0xfd72e  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Clear()
0xfd733  endfinally
0xfd734  ldarg.0
0xfd735  ldfld    unsigned int8 System.Windows.Media.Imaging.WmpBitmapEncoder::_overlaplevel
0xfd73a  ldc.i4.1
0xfd73b  beq.s    loc_FD77C
0xfd73d  ldloca.s 1
0xfd73f  ldstr    aOverlap// "Overlap"
0xfd744  call     instance void System.Windows.Media.Imaging.PROPBAG2::Init(string name)
0xfd749  ldloca.s 0
0xfd74b  ldarg.0
0xfd74c  ldfld    unsigned int8 System.Windows.Media.Imaging.WmpBitmapEncoder::_overlaplevel
0xfd751  box      [mscorlib]System.Byte
0xfd756  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Init(object value)
0xfd75b  ldarg.2
0xfd75c  ldc.i4.1
0xfd75d  ldloca.s 1
0xfd75f  ldloca.s 0
0xfd761  call     int32 IPropertyBag2::Write(class System.Windows.Media.SafeMILHandle THIS_PTR, unsigned int32 cProperties, valuetype System.Windows.Media.Imaging.PROPBAG2& propBag, valuetype System.Windows.Media.Imaging.PROPVARIANT& propValue)
0xfd766  call     void MS.Internal.HRESULT::Check(int32 hr)
0xfd76b  leave.s  loc_FD77C
0xfd76d  ldloca.s 1
0xfd76f  call     instance void System.Windows.Media.Imaging.PROPBAG2::Clear()
0xfd774  ldloca.s 0
0xfd776  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Clear()
0xfd77b  endfinally
0xfd77c  ldarg.0
0xfd77d  ldfld    int16 System.Windows.Media.Imaging.WmpBitmapEncoder::_horizontaltileslices
0xfd782  brfalse.s loc_FD7C4
0xfd784  ldloca.s 1
0xfd786  ldstr    aHorizontaltile// "HorizontalTileSlices"
0xfd78b  call     instance void System.Windows.Media.Imaging.PROPBAG2::Init(string name)
0xfd790  ldloca.s 0
0xfd792  ldarg.0
0xfd793  ldfld    int16 System.Windows.Media.Imaging.WmpBitmapEncoder::_horizontaltileslices
0xfd798  conv.u2
0xfd799  box      [mscorlib]System.UInt16
0xfd79e  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Init(object value)
0xfd7a3  ldarg.2
0xfd7a4  ldc.i4.1
0xfd7a5  ldloca.s 1
0xfd7a7  ldloca.s 0
0xfd7a9  call     int32 IPropertyBag2::Write(class System.Windows.Media.SafeMILHandle THIS_PTR, unsigned int32 cProperties, valuetype System.Windows.Media.Imaging.PROPBAG2& propBag, valuetype System.Windows.Media.Imaging.PROPVARIANT& propValue)
0xfd7ae  call     void MS.Internal.HRESULT::Check(int32 hr)
0xfd7b3  leave.s  loc_FD7C4
0xfd7b5  ldloca.s 1
0xfd7b7  call     instance void System.Windows.Media.Imaging.PROPBAG2::Clear()
0xfd7bc  ldloca.s 0
0xfd7be  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Clear()
0xfd7c3  endfinally
0xfd7c4  ldarg.0
0xfd7c5  ldfld    int16 System.Windows.Media.Imaging.WmpBitmapEncoder::_verticaltileslices
0xfd7ca  brfalse.s loc_FD80C
0xfd7cc  ldloca.s 1
0xfd7ce  ldstr    aVerticaltilesl// "VerticalTileSlices"
0xfd7d3  call     instance void System.Windows.Media.Imaging.PROPBAG2::Init(string name)
0xfd7d8  ldloca.s 0
0xfd7da  ldarg.0
0xfd7db  ldfld    int16 System.Windows.Media.Imaging.WmpBitmapEncoder::_verticaltileslices
0xfd7e0  conv.u2
0xfd7e1  box      [mscorlib]System.UInt16
0xfd7e6  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Init(object value)
0xfd7eb  ldarg.2
0xfd7ec  ldc.i4.1
0xfd7ed  ldloca.s 1
0xfd7ef  ldloca.s 0
0xfd7f1  call     int32 IPropertyBag2::Write(class System.Windows.Media.SafeMILHandle THIS_PTR, unsigned int32 cProperties, valuetype System.Windows.Media.Imaging.PROPBAG2& propBag, valuetype System.Windows.Media.Imaging.PROPVARIANT& propValue)
0xfd7f6  call     void MS.Internal.HRESULT::Check(int32 hr)
0xfd7fb  leave.s  loc_FD80C
0xfd7fd  ldloca.s 1
0xfd7ff  call     instance void System.Windows.Media.Imaging.PROPBAG2::Clear()
0xfd804  ldloca.s 0
0xfd806  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Clear()
0xfd80b  endfinally
0xfd80c  ldarg.0
0xfd80d  ldfld    bool System.Windows.Media.Imaging.WmpBitmapEncoder::_frequencyorder
0xfd812  brtrue.s loc_FD853
0xfd814  ldloca.s 1
0xfd816  ldstr    aFrequencyorder// "FrequencyOrder"
0xfd81b  call     instance void System.Windows.Media.Imaging.PROPBAG2::Init(string name)
0xfd820  ldloca.s 0
0xfd822  ldarg.0
0xfd823  ldfld    bool System.Windows.Media.Imaging.WmpBitmapEncoder::_frequencyorder
0xfd828  box      [mscorlib]System.Boolean
0xfd82d  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Init(object value)
0xfd832  ldarg.2
0xfd833  ldc.i4.1
0xfd834  ldloca.s 1
0xfd836  ldloca.s 0
0xfd838  call     int32 IPropertyBag2::Write(class System.Windows.Media.SafeMILHandle THIS_PTR, unsigned int32 cProperties, valuetype System.Windows.Media.Imaging.PROPBAG2& propBag, valuetype System.Windows.Media.Imaging.PROPVARIANT& propValue)
0xfd83d  call     void MS.Internal.HRESULT::Check(int32 hr)
0xfd842  leave.s  loc_FD853
0xfd844  ldloca.s 1
0xfd846  call     instance void System.Windows.Media.Imaging.PROPBAG2::Clear()
0xfd84b  ldloca.s 0
0xfd84d  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Clear()
0xfd852  endfinally
0xfd853  ldarg.0
0xfd854  ldfld    bool System.Windows.Media.Imaging.WmpBitmapEncoder::_interleavedalpha
0xfd859  brfalse.s loc_FD89A
0xfd85b  ldloca.s 1
0xfd85d  ldstr    aInterleavedalp// "InterleavedAlpha"
0xfd862  call     instance void System.Windows.Media.Imaging.PROPBAG2::Init(string name)
0xfd867  ldloca.s 0
0xfd869  ldarg.0
0xfd86a  ldfld    bool System.Windows.Media.Imaging.WmpBitmapEncoder::_interleavedalpha
0xfd86f  box      [mscorlib]System.Boolean
0xfd874  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Init(object value)
0xfd879  ldarg.2
0xfd87a  ldc.i4.1
0xfd87b  ldloca.s 1
0xfd87d  ldloca.s 0
0xfd87f  call     int32 IPropertyBag2::Write(class System.Windows.Media.SafeMILHandle THIS_PTR, unsigned int32 cProperties, valuetype System.Windows.Media.Imaging.PROPBAG2& propBag, valuetype System.Windows.Media.Imaging.PROPVARIANT& propValue)
0xfd884  call     void MS.Internal.HRESULT::Check(int32 hr)
0xfd889  leave.s  loc_FD89A
0xfd88b  ldloca.s 1
0xfd88d  call     instance void System.Windows.Media.Imaging.PROPBAG2::Clear()
0xfd892  ldloca.s 0
0xfd894  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Clear()
0xfd899  endfinally
0xfd89a  ldarg.0
0xfd89b  ldfld    unsigned int8 System.Windows.Media.Imaging.WmpBitmapEncoder::_alphaqualitylevel
0xfd8a0  ldc.i4.1
0xfd8a1  beq.s    loc_FD8E2
0xfd8a3  ldloca.s 1
0xfd8a5  ldstr    aAlphaquality// "AlphaQuality"
0xfd8aa  call     instance void System.Windows.Media.Imaging.PROPBAG2::Init(string name)
0xfd8af  ldloca.s 0
0xfd8b1  ldarg.0
0xfd8b2  ldfld    unsigned int8 System.Windows.Media.Imaging.WmpBitmapEncoder::_alphaqualitylevel
0xfd8b7  box      [mscorlib]System.Byte
0xfd8bc  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Init(object value)
0xfd8c1  ldarg.2
0xfd8c2  ldc.i4.1
0xfd8c3  ldloca.s 1
0xfd8c5  ldloca.s 0
0xfd8c7  call     int32 IPropertyBag2::Write(class System.Windows.Media.SafeMILHandle THIS_PTR, unsigned int32 cProperties, valuetype System.Windows.Media.Imaging.PROPBAG2& propBag, valuetype System.Windows.Media.Imaging.PROPVARIANT& propValue)
0xfd8cc  call     void MS.Internal.HRESULT::Check(int32 hr)
0xfd8d1  leave.s  loc_FD8E2
0xfd8d3  ldloca.s 1
0xfd8d5  call     instance void System.Windows.Media.Imaging.PROPBAG2::Clear()
0xfd8da  ldloca.s 0
0xfd8dc  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Clear()
0xfd8e1  endfinally
0xfd8e2  ldarg.0
0xfd8e3  ldfld    bool System.Windows.Media.Imaging.WmpBitmapEncoder::_compresseddomaintranscode
0xfd8e8  brtrue.s loc_FD929
0xfd8ea  ldloca.s 1
0xfd8ec  ldstr    aCompresseddoma// "CompressedDomainTranscode"
0xfd8f1  call     instance void System.Windows.Media.Imaging.PROPBAG2::Init(string name)
0xfd8f6  ldloca.s 0
0xfd8f8  ldarg.0
0xfd8f9  ldfld    bool System.Windows.Media.Imaging.WmpBitmapEncoder::_compresseddomaintranscode
0xfd8fe  box      [mscorlib]System.Boolean
0xfd903  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Init(object value)
  ... truncated ...
```
