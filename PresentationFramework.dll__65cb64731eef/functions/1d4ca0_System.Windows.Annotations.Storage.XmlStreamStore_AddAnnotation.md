# System.Windows.Annotations.Storage.XmlStreamStore::AddAnnotation

- ea: `0x1d4ca0`
- end: `0x1d4d52`
- name: `System.Windows.Annotations.Storage.XmlStreamStore::AddAnnotation`
- size: `178`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x38c40`
- `0x1cf610`
- `0x1d4aa0`
- `0x1d4ae0`
- `0x1d4b70`
- `0x1d4ca0`
- `0x1d5800`
- `0x1d5870`
- `0x2478e0`
- `0x247b20`

## string_xrefs

- `0x1d4ce1`: `AnnotationAlreadyExists`
- `0x1d4d09`: `AnnotationAlreadyExists`

## pseudocode

```c

```

## disassembly

```asm
0x1d4ca0  ldarg.1
0x1d4ca1  brtrue.s loc_1D4CAE
0x1d4ca3  ldstr    aNewannotation// "newAnnotation"
0x1d4ca8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1d4cad  throw
0x1d4cae  ldarg.0
0x1d4caf  call     instance object System.Windows.Annotations.Storage.AnnotationStore::get_SyncRoot()
0x1d4cb4  stloc.0
0x1d4cb5  ldc.i4.0
0x1d4cb6  stloc.1
0x1d4cb7  ldloc.0
0x1d4cb8  ldloca.s 1
0x1d4cba  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1d4cbf  ldc.i4.s 0x10
0x1d4cc1  ldc.i4   0xBC5
0x1d4cc6  call     void [WindowsBase]MS.Utility.EventTrace::EasyTraceEvent(valuetype [WindowsBase]MS.Utility.EventTrace/Keyword, valuetype [WindowsBase]MS.Utility.EventTrace/Event)
0x1d4ccb  ldarg.0
0x1d4ccc  call     instance void System.Windows.Annotations.Storage.XmlStreamStore::CheckStatus()
0x1d4cd1  ldarg.0
0x1d4cd2  ldarg.1
0x1d4cd3  callvirt instance valuetype [mscorlib]System.Guid System.Windows.Annotations.Annotation::get_Id()
0x1d4cd8  call     instance class [System.Xml]System.Xml.XPath.XPathNavigator System.Windows.Annotations.Storage.XmlStreamStore::GetAnnotationNodeForId(valuetype [mscorlib]System.Guid id)
0x1d4cdd  stloc.2
0x1d4cde  ldloc.2
0x1d4cdf  brfalse.s loc_1D4CF6
0x1d4ce1  ldstr    aAnnotationalre_0// "AnnotationAlreadyExists"
0x1d4ce6  call     string System.Windows.SR::Get(string id)
0x1d4ceb  ldstr    aNewannotation// "newAnnotation"
0x1d4cf0  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1d4cf5  throw
0x1d4cf6  ldarg.0
0x1d4cf7  ldfld    class MS.Internal.Annotations.Storage.StoreAnnotationsMap System.Windows.Annotations.Storage.XmlStreamStore::_storeAnnotationsMap
0x1d4cfc  ldarg.1
0x1d4cfd  callvirt instance valuetype [mscorlib]System.Guid System.Windows.Annotations.Annotation::get_Id()
0x1d4d02  callvirt instance class System.Windows.Annotations.Annotation MS.Internal.Annotations.Storage.StoreAnnotationsMap::FindAnnotation(valuetype [mscorlib]System.Guid id)
0x1d4d07  brfalse.s loc_1D4D1E
0x1d4d09  ldstr    aAnnotationalre_0// "AnnotationAlreadyExists"
0x1d4d0e  call     string System.Windows.SR::Get(string id)
0x1d4d13  ldstr    aNewannotation// "newAnnotation"
0x1d4d18  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1d4d1d  throw
0x1d4d1e  ldarg.0
0x1d4d1f  ldfld    class MS.Internal.Annotations.Storage.StoreAnnotationsMap System.Windows.Annotations.Storage.XmlStreamStore::_storeAnnotationsMap
0x1d4d24  ldarg.1
0x1d4d25  ldc.i4.1
0x1d4d26  callvirt instance void MS.Internal.Annotations.Storage.StoreAnnotationsMap::AddAnnotation(class System.Windows.Annotations.Annotation annotation, bool dirty)
0x1d4d2b  leave.s  loc_1D4D44
0x1d4d2d  ldc.i4.s 0x10
0x1d4d2f  ldc.i4   0xBC6
0x1d4d34  call     void [WindowsBase]MS.Utility.EventTrace::EasyTraceEvent(valuetype [WindowsBase]MS.Utility.EventTrace/Keyword, valuetype [WindowsBase]MS.Utility.EventTrace/Event)
0x1d4d39  endfinally
0x1d4d3a  ldloc.1
0x1d4d3b  brfalse.s loc_1D4D43
0x1d4d3d  ldloc.0
0x1d4d3e  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1d4d43  endfinally
0x1d4d44  ldarg.0
0x1d4d45  ldc.i4.0
0x1d4d46  ldarg.1
0x1d4d47  newobj   instance void System.Windows.Annotations.Storage.StoreContentChangedEventArgs::.ctor(valuetype System.Windows.Annotations.Storage.StoreContentAction action, class System.Windows.Annotations.Annotation annotation)
0x1d4d4c  callvirt instance void System.Windows.Annotations.Storage.AnnotationStore::OnStoreContentChanged(class System.Windows.Annotations.Storage.StoreContentChangedEventArgs e)
0x1d4d51  ret
```
