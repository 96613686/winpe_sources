# Microsoft.VisualStudio.Setup.Cache.Instance::.ctor

- ea: `0x1a110`
- end: `0x1a36e`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::.ctor`
- size: `606`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x90b0`
- `0x9130`
- `0x1a980`
- `0x1a9a0`
- `0x1aa50`
- `0x1aaf0`
- `0x1ae10`
- `0x1bc50`
- `0x1bff0`

## pseudocode

```c

```

## disassembly

```asm
0x1a110  ldarg.0
0x1a111  newobj   instance void [mscorlib]System.Object::.ctor()
0x1a116  stfld    object Microsoft.VisualStudio.Setup.Cache.Instance::syncRoot
0x1a11b  ldarg.0
0x1a11c  call     instance void [mscorlib]System.Object::.ctor()
0x1a121  ldarg.0
0x1a122  newobj   instance void class [System]System.Collections.ObjectModel.ObservableCollection`1<class Microsoft.VisualStudio.Setup.LocalizedResource>::.ctor()
0x1a127  stfld    class [System]System.Collections.ObjectModel.ObservableCollection`1<class Microsoft.VisualStudio.Setup.LocalizedResource> Microsoft.VisualStudio.Setup.Cache.Instance::localizedResources
0x1a12c  ldarg.0
0x1a12d  ldfld    class [System]System.Collections.ObjectModel.ObservableCollection`1<class Microsoft.VisualStudio.Setup.LocalizedResource> Microsoft.VisualStudio.Setup.Cache.Instance::localizedResources
0x1a132  ldarg.0
0x1a133  ldftn    instance void Microsoft.VisualStudio.Setup.Cache.Instance::<.ctor>b__52_0(object source, class [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs args)
0x1a139  newobj   instance void [System]System.Collections.Specialized.NotifyCollectionChangedEventHandler::.ctor(object, native int)
0x1a13e  callvirt instance void class [System]System.Collections.ObjectModel.ObservableCollection`1<class Microsoft.VisualStudio.Setup.LocalizedResource>::add_CollectionChanged(class [System]System.Collections.Specialized.NotifyCollectionChangedEventHandler)
0x1a143  ldarg.0
0x1a144  newobj   instance void class [System]System.Collections.ObjectModel.ObservableCollection`1<class Microsoft.VisualStudio.Setup.LocalizedResource>::.ctor()
0x1a149  stfld    class [System]System.Collections.ObjectModel.ObservableCollection`1<class Microsoft.VisualStudio.Setup.LocalizedResource> Microsoft.VisualStudio.Setup.Cache.Instance::channelResources
0x1a14e  ldarg.0
0x1a14f  ldfld    class [System]System.Collections.ObjectModel.ObservableCollection`1<class Microsoft.VisualStudio.Setup.LocalizedResource> Microsoft.VisualStudio.Setup.Cache.Instance::channelResources
0x1a154  ldarg.0
0x1a155  ldftn    instance void Microsoft.VisualStudio.Setup.Cache.Instance::<.ctor>b__52_1(object source, class [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs args)
0x1a15b  newobj   instance void [System]System.Collections.Specialized.NotifyCollectionChangedEventHandler::.ctor(object, native int)
0x1a160  callvirt instance void class [System]System.Collections.ObjectModel.ObservableCollection`1<class Microsoft.VisualStudio.Setup.LocalizedResource>::add_CollectionChanged(class [System]System.Collections.Specialized.NotifyCollectionChangedEventHandler)
0x1a165  ldarg.0
0x1a166  ldnull
0x1a167  newobj   instance void Microsoft.VisualStudio.Setup.Cache.PackageReferenceCollection::.ctor([opt] class [mscorlib]System.Collections.Generic.IEqualityComparer`1<class Microsoft.VisualStudio.Setup.Cache.PackageReference> comparer)
0x1a16c  stfld    class Microsoft.VisualStudio.Setup.Cache.PackageReferenceCollection Microsoft.VisualStudio.Setup.Cache.Instance::<Packages>k__BackingField
0x1a171  ldarg.0
0x1a172  call     instance class Microsoft.VisualStudio.Setup.Cache.PackageReferenceCollection Microsoft.VisualStudio.Setup.Cache.Instance::get_Packages()
0x1a177  ldarg.0
0x1a178  ldftn    instance void Microsoft.VisualStudio.Setup.Cache.Instance::<.ctor>b__52_2(object source, class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<class Microsoft.VisualStudio.Setup.Cache.PackageReference> args)
0x1a17e  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<class Microsoft.VisualStudio.Setup.Cache.PackageReference>>::.ctor(object, native int)
0x1a183  callvirt instance void class Microsoft.VisualStudio.Setup.Cache.IndexedCollection`1<class Microsoft.VisualStudio.Setup.Cache.PackageReference>::add_CollectionChanged(class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<var<u1>>>)
0x1a188  ldarg.0
0x1a189  ldnull
0x1a18a  newobj   instance void Microsoft.VisualStudio.Setup.Cache.SelectablePackageReferenceCollection::.ctor([opt] class [mscorlib]System.Collections.Generic.IEqualityComparer`1<class Microsoft.VisualStudio.Setup.Cache.SelectablePackageReference> comparer)
0x1a18f  stfld    class Microsoft.VisualStudio.Setup.Cache.SelectablePackageReferenceCollection Microsoft.VisualStudio.Setup.Cache.Instance::<SelectedPackages>k__BackingField
0x1a194  ldarg.0
0x1a195  call     instance class Microsoft.VisualStudio.Setup.Cache.SelectablePackageReferenceCollection Microsoft.VisualStudio.Setup.Cache.Instance::get_SelectedPackages()
0x1a19a  ldarg.0
0x1a19b  ldftn    instance void Microsoft.VisualStudio.Setup.Cache.Instance::<.ctor>b__52_3(object source, class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<class Microsoft.VisualStudio.Setup.Cache.SelectablePackageReference> args)
0x1a1a1  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<class Microsoft.VisualStudio.Setup.Cache.SelectablePackageReference>>::.ctor(object, native int)
0x1a1a6  callvirt instance void class Microsoft.VisualStudio.Setup.Cache.IndexedCollection`1<class Microsoft.VisualStudio.Setup.Cache.SelectablePackageReference>::add_CollectionChanged(class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<var<u1>>>)
0x1a1ab  ldarg.0
0x1a1ac  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Globalization.CultureInfo, class Microsoft.VisualStudio.Setup.LocalizedResource>::.ctor()
0x1a1b1  stfld    class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Globalization.CultureInfo, class Microsoft.VisualStudio.Setup.LocalizedResource> Microsoft.VisualStudio.Setup.Cache.Instance::cachedProductResources
0x1a1b6  ldarg.0
0x1a1b7  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Globalization.CultureInfo, class Microsoft.VisualStudio.Setup.LocalizedResource>::.ctor()
0x1a1bc  stfld    class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Globalization.CultureInfo, class Microsoft.VisualStudio.Setup.LocalizedResource> Microsoft.VisualStudio.Setup.Cache.Instance::cachedChannelResources
0x1a1c1  ldarg.0
0x1a1c2  ldsfld   class [mscorlib]System.StringComparer Microsoft.VisualStudio.Setup.Cache.Instance::Comparer
0x1a1c7  newobj   instance void class Microsoft.VisualStudio.Setup.Cache.ObservableDictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x1a1cc  stfld    class Microsoft.VisualStudio.Setup.Cache.IObservableDictionary`2<string, string> Microsoft.VisualStudio.Setup.Cache.Instance::properties
0x1a1d1  ldarg.0
0x1a1d2  ldfld    class Microsoft.VisualStudio.Setup.Cache.IObservableDictionary`2<string, string> Microsoft.VisualStudio.Setup.Cache.Instance::properties
0x1a1d7  ldarg.0
0x1a1d8  ldftn    instance void Microsoft.VisualStudio.Setup.Cache.Instance::<.ctor>b__52_4(object source, class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> args)
0x1a1de  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>>::.ctor(object, native int)
0x1a1e3  callvirt instance void class Microsoft.VisualStudio.Setup.INotifyCollectionChanged`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::add_CollectionChanged(class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<var<u1>>>)
0x1a1e8  ldarg.0
0x1a1e9  ldarg.0
0x1a1ea  ldfld    class Microsoft.VisualStudio.Setup.Cache.IObservableDictionary`2<string, string> Microsoft.VisualStudio.Setup.Cache.Instance::properties
0x1a1ef  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyDictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IDictionary`2<var<u1>, !!T0>)
0x1a1f4  stfld    class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string> Microsoft.VisualStudio.Setup.Cache.Instance::propertiesRO
0x1a1f9  ldarg.0
0x1a1fa  ldsfld   class [mscorlib]System.StringComparer Microsoft.VisualStudio.Setup.Cache.Instance::Comparer
0x1a1ff  newobj   instance void class Microsoft.VisualStudio.Setup.Cache.ObservableDictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x1a204  stfld    class Microsoft.VisualStudio.Setup.Cache.IObservableDictionary`2<string, string> Microsoft.VisualStudio.Setup.Cache.Instance::userProperties
0x1a209  ldarg.0
0x1a20a  ldfld    class Microsoft.VisualStudio.Setup.Cache.IObservableDictionary`2<string, string> Microsoft.VisualStudio.Setup.Cache.Instance::userProperties
0x1a20f  ldarg.0
0x1a210  ldftn    instance void Microsoft.VisualStudio.Setup.Cache.Instance::<.ctor>b__52_5(object source, class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> args)
0x1a216  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>>::.ctor(object, native int)
0x1a21b  callvirt instance void class Microsoft.VisualStudio.Setup.INotifyCollectionChanged`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::add_CollectionChanged(class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<var<u1>>>)
0x1a220  ldarg.0
0x1a221  ldarg.0
0x1a222  ldfld    class Microsoft.VisualStudio.Setup.Cache.IObservableDictionary`2<string, string> Microsoft.VisualStudio.Setup.Cache.Instance::userProperties
0x1a227  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyDictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IDictionary`2<var<u1>, !!T0>)
0x1a22c  stfld    class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string> Microsoft.VisualStudio.Setup.Cache.Instance::userPropertiesRO
0x1a231  ldarg.0
0x1a232  ldsfld   class [mscorlib]System.StringComparer Microsoft.VisualStudio.Setup.Cache.Instance::Comparer
0x1a237  newobj   instance void class Microsoft.VisualStudio.Setup.Cache.ObservableDictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x1a23c  stfld    class Microsoft.VisualStudio.Setup.Cache.IObservableDictionary`2<string, string> Microsoft.VisualStudio.Setup.Cache.Instance::temporaryProperties
0x1a241  ldarg.0
0x1a242  ldfld    class Microsoft.VisualStudio.Setup.Cache.IObservableDictionary`2<string, string> Microsoft.VisualStudio.Setup.Cache.Instance::temporaryProperties
0x1a247  ldarg.0
0x1a248  ldftn    instance void Microsoft.VisualStudio.Setup.Cache.Instance::<.ctor>b__52_6(object source, class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> args)
0x1a24e  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>>::.ctor(object, native int)
0x1a253  callvirt instance void class Microsoft.VisualStudio.Setup.INotifyCollectionChanged`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::add_CollectionChanged(class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<var<u1>>>)
0x1a258  ldarg.0
0x1a259  ldarg.0
0x1a25a  ldfld    class Microsoft.VisualStudio.Setup.Cache.IObservableDictionary`2<string, string> Microsoft.VisualStudio.Setup.Cache.Instance::temporaryProperties
0x1a25f  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyDictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IDictionary`2<var<u1>, !!T0>)
0x1a264  stfld    class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string> Microsoft.VisualStudio.Setup.Cache.Instance::temporaryPropertiesRO
0x1a269  ldarg.0
0x1a26a  ldsfld   class [mscorlib]System.StringComparer Microsoft.VisualStudio.Setup.Cache.Instance::Comparer
0x1a26f  newobj   instance void class Microsoft.VisualStudio.Setup.Cache.ObservableDictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x1a274  stfld    class Microsoft.VisualStudio.Setup.Cache.ObservableDictionary`2<string, string> Microsoft.VisualStudio.Setup.Cache.Instance::featureProperties
0x1a279  ldarg.0
0x1a27a  ldfld    class Microsoft.VisualStudio.Setup.Cache.ObservableDictionary`2<string, string> Microsoft.VisualStudio.Setup.Cache.Instance::featureProperties
0x1a27f  ldarg.0
0x1a280  ldftn    instance void Microsoft.VisualStudio.Setup.Cache.Instance::<.ctor>b__52_7(object source, class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> args)
0x1a286  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>>::.ctor(object, native int)
0x1a28b  callvirt instance void class Microsoft.VisualStudio.Setup.Cache.ObservableDictionary`2<string, string>::add_CollectionChanged(class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>>>)
0x1a290  ldarg.0
0x1a291  ldarg.0
0x1a292  ldfld    class Microsoft.VisualStudio.Setup.Cache.ObservableDictionary`2<string, string> Microsoft.VisualStudio.Setup.Cache.Instance::featureProperties
0x1a297  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyDictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IDictionary`2<var<u1>, !!T0>)
0x1a29c  stfld    class [mscorlib]System.Collections.ObjectModel.ReadOnlyDictionary`2<string, string> Microsoft.VisualStudio.Setup.Cache.Instance::featurePropertiesRO
0x1a2a1  ldarg.0
0x1a2a2  ldnull
0x1a2a3  newobj   instance void class Microsoft.VisualStudio.Setup.Cache.IndexedCollection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x1a2a8  stfld    class Microsoft.VisualStudio.Setup.Cache.IndexedCollection`1<string> Microsoft.VisualStudio.Setup.Cache.Instance::previousLayoutPaths
0x1a2ad  ldarg.0
0x1a2ae  ldfld    class Microsoft.VisualStudio.Setup.Cache.IndexedCollection`1<string> Microsoft.VisualStudio.Setup.Cache.Instance::previousLayoutPaths
0x1a2b3  ldarg.0
0x1a2b4  ldftn    instance void Microsoft.VisualStudio.Setup.Cache.Instance::<.ctor>b__52_8(object source, class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<string> args)
0x1a2ba  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<string>>::.ctor(object, native int)
0x1a2bf  callvirt instance void class Microsoft.VisualStudio.Setup.Cache.IndexedCollection`1<string>::add_CollectionChanged(class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<var<u1>>>)
0x1a2c4  ldarg.0
0x1a2c5  ldc.i4.8
0x1a2c6  call     instance void Microsoft.VisualStudio.Setup.Cache.Instance::set_State(valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState value)
0x1a2cb  ldarg.0
0x1a2cc  ldnull
0x1a2cd  stfld    string Microsoft.VisualStudio.Setup.Cache.Instance::installationPath
0x1a2d2  ldarg.0
0x1a2d3  ldnull
0x1a2d4  stfld    class Microsoft.VisualStudio.Setup.Cache.ErrorState Microsoft.VisualStudio.Setup.Cache.Instance::errors
0x1a2d9  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x1a2de  newobj   instance void class Microsoft.VisualStudio.Setup.Cache.ObservableDictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x1a2e3  stloc.0
0x1a2e4  ldloc.0
0x1a2e5  ldarg.0
0x1a2e6  ldftn    instance void Microsoft.VisualStudio.Setup.Cache.Instance::<.ctor>b__52_9(object _, class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> _)
0x1a2ec  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>>::.ctor(object, native int)
0x1a2f1  callvirt instance void class Microsoft.VisualStudio.Setup.Cache.ObservableDictionary`2<string, string>::add_CollectionChanged(class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>>>)
0x1a2f6  ldarg.0
0x1a2f7  ldloc.0
0x1a2f8  stfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.VisualStudio.Setup.Cache.Instance::<GroupConfigFiles>k__BackingField
0x1a2fd  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x1a302  newobj   instance void class Microsoft.VisualStudio.Setup.Cache.ObservableDictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x1a307  stloc.1
0x1a308  ldloc.1
0x1a309  ldarg.0
0x1a30a  ldftn    instance void Microsoft.VisualStudio.Setup.Cache.Instance::<.ctor>b__52_10(object _, class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> _)
0x1a310  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>>::.ctor(object, native int)
0x1a315  callvirt instance void class Microsoft.VisualStudio.Setup.Cache.ObservableDictionary`2<string, string>::add_CollectionChanged(class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>>>)
0x1a31a  ldarg.0
0x1a31b  ldloc.1
0x1a31c  stfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.VisualStudio.Setup.Cache.Instance::<UsingGroupConfigFiles>k__BackingField
0x1a321  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x1a326  newobj   instance void class Microsoft.VisualStudio.Setup.Cache.ObservableDictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x1a32b  stloc.2
0x1a32c  ldloc.2
0x1a32d  ldarg.0
0x1a32e  ldftn    instance void Microsoft.VisualStudio.Setup.Cache.Instance::<.ctor>b__52_11(object _, class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> _)
0x1a334  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>>::.ctor(object, native int)
0x1a339  callvirt instance void class Microsoft.VisualStudio.Setup.Cache.ObservableDictionary`2<string, string>::add_CollectionChanged(class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>>>)
0x1a33e  ldarg.0
0x1a33f  ldloc.2
0x1a340  stfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.VisualStudio.Setup.Cache.Instance::<PendingGroupFileRenames>k__BackingField
0x1a345  ldarg.0
0x1a346  newobj   instance void Microsoft.VisualStudio.Setup.NgenState::.ctor()
0x1a34b  stfld    class Microsoft.VisualStudio.Setup.NgenState Microsoft.VisualStudio.Setup.Cache.Instance::<NgenState>k__BackingField
0x1a350  ldarg.0
0x1a351  call     instance class Microsoft.VisualStudio.Setup.NgenState Microsoft.VisualStudio.Setup.Cache.Instance::get_NgenState()
0x1a356  ldarg.0
0x1a357  ldftn    instance void Microsoft.VisualStudio.Setup.Cache.Instance::<.ctor>b__52_12(object _, class [System]System.ComponentModel.PropertyChangedEventArgs _)
0x1a35d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventHandler::.ctor(object, native int)
0x1a362  callvirt instance void Microsoft.VisualStudio.Setup.NgenState::add_PropertyChanged(class [System]System.ComponentModel.PropertyChangedEventHandler value)
0x1a367  ldarg.0
0x1a368  call     instance void Microsoft.VisualStudio.Setup.Cache.Instance::ResetChanged()
0x1a36d  ret
```
