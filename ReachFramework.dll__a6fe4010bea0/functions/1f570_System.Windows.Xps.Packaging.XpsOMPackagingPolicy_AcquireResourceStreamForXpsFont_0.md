# System.Windows.Xps.Packaging.XpsOMPackagingPolicy::AcquireResourceStreamForXpsFont_0

- ea: `0x1f570`
- end: `0x1f62f`
- name: `System.Windows.Xps.Packaging.XpsOMPackagingPolicy::AcquireResourceStreamForXpsFont_0`
- size: `191`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config`

## callees

- `0x1bc20`
- `0x1eee0`
- `0x1ef70`
- `0x1f570`
- `0x1fa20`
- `0x1fa50`
- `0x1fa80`
- `0x2e7c0`
- `0x2e820`
- `0x2e830`
- `0x2e840`
- `0x2e870`
- `0x3cb00`
- `0x3d560`
- `0x3da80`

## string_xrefs

- `0x1f610`: `ReachSerialization_NoFixedPageWriter`

## pseudocode

```c

```

## disassembly

```asm
0x1f570  ldnull
0x1f571  stloc.0
0x1f572  ldarg.0
0x1f573  ldfld    class [mscorlib]System.Collections.Hashtable System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_fontsCache
0x1f578  ldarg.1
0x1f579  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x1f57e  castclass System.Windows.Xps.Serialization.ResourceStreamCacheItem
0x1f583  stloc.1
0x1f584  ldloc.1
0x1f585  brtrue   loc_1F620
0x1f58a  newobj   instance void System.Windows.Xps.Serialization.ResourceStreamCacheItem::.ctor()
0x1f58f  stloc.1
0x1f590  ldarg.0
0x1f591  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentFixedPageXmlWriter
0x1f596  brfalse.s loc_1F610
0x1f598  ldarg.0
0x1f599  call     instance class [System]System.Uri System.Windows.Xps.Packaging.XpsOMPackagingPolicy::GenerateUriForObfuscatedFont()
0x1f59e  stloc.2
0x1f59f  ldarg.0
0x1f5a0  ldloc.2
0x1f5a1  call     instance class System.Windows.Xps.Serialization.RCW.IOpcPartUri System.Windows.Xps.Packaging.XpsOMPackagingPolicy::GenerateIOpcPartUri(class [System]System.Uri uri)
0x1f5a6  stloc.3
0x1f5a7  call     class [System.Printing]MS.Internal.PrintWin32Thunk.XpsPrintStream [System.Printing]MS.Internal.PrintWin32Thunk.XpsPrintStream::CreateXpsPrintStream()
0x1f5ac  stloc.s  4
0x1f5ae  ldloc.s  4
0x1f5b0  callvirt instance class [mscorlib]System.Runtime.InteropServices.ComTypes.IStream [System.Printing]MS.Internal.PrintWin32Thunk.XpsPrintStream::GetManagedIStream()
0x1f5b5  stloc.s  5
0x1f5b7  ldarg.0
0x1f5b8  ldfld    class System.Windows.Xps.Serialization.RCW.IXpsOMObjectFactory System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_xpsOMFactory
0x1f5bd  ldloc.s  5
0x1f5bf  ldc.i4.2
0x1f5c0  ldloc.3
0x1f5c1  ldc.i4.1
0x1f5c2  callvirt instance class System.Windows.Xps.Serialization.RCW.IXpsOMFontResource System.Windows.Xps.Serialization.RCW.IXpsOMObjectFactory::CreateFontResource([hasfieldmarshal] class [mscorlib]System.Runtime.InteropServices.ComTypes.IStream, [in] [hasfieldmarshal] valuetype System.Windows.Xps.Serialization.RCW.XPS_FONT_EMBEDDING acquiredStream, [in] class System.Windows.Xps.Serialization.RCW.IOpcPartUri fontEmbedding, [in] [hasfieldmarshal] int32 partUri)
0x1f5c7  stloc.s  6
0x1f5c9  ldarg.0
0x1f5ca  ldfld    class System.Windows.Xps.Serialization.RCW.IXpsOMPartResources System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_xpsPartResources
0x1f5cf  callvirt instance class System.Windows.Xps.Serialization.RCW.IXpsOMFontResourceCollection System.Windows.Xps.Serialization.RCW.IXpsOMPartResources::GetFontResources()
0x1f5d4  stloc.s  7
0x1f5d6  ldloc.s  7
0x1f5d8  ldloc.s  6
0x1f5da  callvirt instance void System.Windows.Xps.Serialization.RCW.IXpsOMFontResourceCollection::Append([in] [hasfieldmarshal] class System.Windows.Xps.Serialization.RCW.IXpsOMFontResource value)
0x1f5df  ldloc.s  4
0x1f5e1  ldloc.2
0x1f5e2  newobj   instance void System.Windows.Xps.Serialization.XpsResourceStream::.ctor(class [mscorlib]System.IO.Stream stream, class [System]System.Uri uri)
0x1f5e7  stloc.s  8
0x1f5e9  ldloc.1
0x1f5ea  ldloc.s  8
0x1f5ec  callvirt instance void System.Windows.Xps.Serialization.ResourceStreamCacheItem::set_XpsResourceStream(class System.Windows.Xps.Serialization.XpsResourceStream value)
0x1f5f1  ldarg.0
0x1f5f2  ldfld    class [mscorlib]System.Collections.Hashtable System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_fontsCache
0x1f5f7  ldarg.1
0x1f5f8  ldloc.1
0x1f5f9  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1f5fe  ldloc.s  8
0x1f600  stloc.0
0x1f601  leave.s  loc_1F62D
0x1f603  pop
0x1f604  ldarg.0
0x1f605  call     instance void System.Windows.Xps.Packaging.XpsOMPackagingPolicy::Invalidate()
0x1f60a  newobj   instance void System.Printing.PrintingCanceledException::.ctor()
0x1f60f  throw
0x1f610  ldstr    aReachserializa_0// "ReachSerialization_NoFixedPageWriter"
0x1f615  call     string System.Windows.Xps.SR::Get(string id)
0x1f61a  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x1f61f  throw
0x1f620  ldloc.1
0x1f621  callvirt instance class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.ResourceStreamCacheItem::get_XpsResourceStream()
0x1f626  stloc.0
0x1f627  ldloc.1
0x1f628  callvirt instance void System.Windows.Xps.Serialization.ResourceStreamCacheItem::IncRef()
0x1f62d  ldloc.0
0x1f62e  ret
```
