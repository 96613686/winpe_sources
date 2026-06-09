# System.Xaml.XamlLanguage::.cctor

- ea: `0x97d0`
- end: `0x9da2`
- name: `System.Xaml.XamlLanguage::.cctor`
- size: `1490`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x97f0`: `http://www.w3.org/XML/1998/namespace`
- `0x97d8`: `http://schemas.microsoft.com/winfx/2006/xaml`

## pseudocode

```c

```

## disassembly

```asm
0x97d0  ldc.i4.1
0x97d1  newarr   [mscorlib]System.String
0x97d6  dup
0x97d7  ldc.i4.0
0x97d8  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/winfx/2006"...
0x97dd  stelem.ref
0x97de  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0x97e3  stsfld   class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string> System.Xaml.XamlLanguage::s_xamlNamespaces
0x97e8  ldc.i4.1
0x97e9  newarr   [mscorlib]System.String
0x97ee  dup
0x97ef  ldc.i4.0
0x97f0  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x97f5  stelem.ref
0x97f6  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0x97fb  stsfld   class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string> System.Xaml.XamlLanguage::s_xmlNamespaces
0x9800  ldnull
0x9801  ldftn    class System.Xaml.XamlSchemaContext System.Xaml.XamlLanguage::GetSchemaContext()
0x9807  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlSchemaContext>::.ctor(object, native int)
0x980c  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlSchemaContext>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x9811  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlSchemaContext> System.Xaml.XamlLanguage::s_schemaContext
0x9816  ldsfld   class <>c <>c::<>9
0x981b  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_0()
0x9821  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x9826  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x982b  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_array
0x9830  ldsfld   class <>c <>c::<>9
0x9835  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_1()
0x983b  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x9840  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x9845  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_null
0x984a  ldsfld   class <>c <>c::<>9
0x984f  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_2()
0x9855  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x985a  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x985f  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_reference
0x9864  ldsfld   class <>c <>c::<>9
0x9869  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_3()
0x986f  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x9874  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x9879  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_static
0x987e  ldsfld   class <>c <>c::<>9
0x9883  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_4()
0x9889  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x988e  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x9893  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_type
0x9898  ldsfld   class <>c <>c::<>9
0x989d  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_5()
0x98a3  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x98a8  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x98ad  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_string
0x98b2  ldsfld   class <>c <>c::<>9
0x98b7  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_6()
0x98bd  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x98c2  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x98c7  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_double
0x98cc  ldsfld   class <>c <>c::<>9
0x98d1  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_7()
0x98d7  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x98dc  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x98e1  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_int32
0x98e6  ldsfld   class <>c <>c::<>9
0x98eb  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_8()
0x98f1  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x98f6  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x98fb  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_boolean
0x9900  ldsfld   class <>c <>c::<>9
0x9905  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_9()
0x990b  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x9910  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x9915  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_member
0x991a  ldsfld   class <>c <>c::<>9
0x991f  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_10()
0x9925  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x992a  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x992f  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_property
0x9934  ldsfld   class <>c <>c::<>9
0x9939  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_11()
0x993f  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x9944  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x9949  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_xDataHolder
0x994e  ldsfld   class <>c <>c::<>9
0x9953  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_12()
0x9959  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x995e  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x9963  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_object
0x9968  ldsfld   class <>c <>c::<>9
0x996d  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_13()
0x9973  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x9978  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x997d  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_listOfObject
0x9982  ldsfld   class <>c <>c::<>9
0x9987  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_14()
0x998d  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x9992  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x9997  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_listOfMembers
0x999c  ldsfld   class <>c <>c::<>9
0x99a1  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_15()
0x99a7  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x99ac  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x99b1  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_listOfAttributes
0x99b6  ldsfld   class <>c <>c::<>9
0x99bb  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_16()
0x99c1  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x99c6  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x99cb  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_markupExtension
0x99d0  ldsfld   class <>c <>c::<>9
0x99d5  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_17()
0x99db  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x99e0  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x99e5  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_iNameScope
0x99ea  ldsfld   class <>c <>c::<>9
0x99ef  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_18()
0x99f5  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x99fa  ldc.i4.1
0x99fb  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x9a00  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_iXmlSerializable
0x9a05  ldsfld   class <>c <>c::<>9
0x9a0a  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_19()
0x9a10  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x9a15  ldc.i4.1
0x9a16  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x9a1b  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_positionalParameterDescriptor
0x9a20  ldsfld   class <>c <>c::<>9
0x9a25  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_20()
0x9a2b  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x9a30  ldc.i4.1
0x9a31  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x9a36  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_char
0x9a3b  ldsfld   class <>c <>c::<>9
0x9a40  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_21()
0x9a46  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x9a4b  ldc.i4.1
0x9a4c  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x9a51  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_single
0x9a56  ldsfld   class <>c <>c::<>9
0x9a5b  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_22()
0x9a61  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x9a66  ldc.i4.1
0x9a67  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x9a6c  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_byte
0x9a71  ldsfld   class <>c <>c::<>9
0x9a76  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_23()
0x9a7c  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x9a81  ldc.i4.1
0x9a82  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x9a87  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_int16
0x9a8c  ldsfld   class <>c <>c::<>9
0x9a91  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_24()
0x9a97  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x9a9c  ldc.i4.1
0x9a9d  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x9aa2  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_int64
0x9aa7  ldsfld   class <>c <>c::<>9
0x9aac  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_25()
0x9ab2  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x9ab7  ldc.i4.1
0x9ab8  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x9abd  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_decimal
0x9ac2  ldsfld   class <>c <>c::<>9
0x9ac7  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_26()
0x9acd  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x9ad2  ldc.i4.1
0x9ad3  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x9ad8  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_uri
0x9add  ldsfld   class <>c <>c::<>9
0x9ae2  ldftn    instance class System.Xaml.XamlType <>c::<.cctor>b__204_27()
0x9ae8  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlType>::.ctor(object, native int)
0x9aed  ldc.i4.1
0x9aee  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlType>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x9af3  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::s_timespan
0x9af8  ldnull
0x9af9  ldftn    class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class System.Xaml.XamlType> System.Xaml.XamlLanguage::GetAllTypes()
0x9aff  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class System.Xaml.XamlType>>::.ctor(object, native int)
0x9b04  newobj   instance void class [mscorlib]System.Lazy`1<class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class System.Xaml.XamlType>>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x9b09  stsfld   class [mscorlib]System.Lazy`1<class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class System.Xaml.XamlType>> System.Xaml.XamlLanguage::s_allTypes
0x9b0e  ldsfld   class <>c <>c::<>9
0x9b13  ldftn    instance class System.Xaml.XamlDirective <>c::<.cctor>b__204_28()
0x9b19  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlDirective>::.ctor(object, native int)
0x9b1e  ldc.i4.1
0x9b1f  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x9b24  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective> System.Xaml.XamlLanguage::s_asyncRecords
0x9b29  ldsfld   class <>c <>c::<>9
0x9b2e  ldftn    instance class System.Xaml.XamlDirective <>c::<.cctor>b__204_29()
0x9b34  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlDirective>::.ctor(object, native int)
0x9b39  ldc.i4.1
0x9b3a  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x9b3f  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective> System.Xaml.XamlLanguage::s_arguments
0x9b44  ldsfld   class <>c <>c::<>9
0x9b49  ldftn    instance class System.Xaml.XamlDirective <>c::<.cctor>b__204_30()
0x9b4f  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlDirective>::.ctor(object, native int)
0x9b54  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x9b59  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective> System.Xaml.XamlLanguage::s_class
0x9b5e  ldsfld   class <>c <>c::<>9
0x9b63  ldftn    instance class System.Xaml.XamlDirective <>c::<.cctor>b__204_31()
0x9b69  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlDirective>::.ctor(object, native int)
0x9b6e  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x9b73  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective> System.Xaml.XamlLanguage::s_classModifier
0x9b78  ldsfld   class <>c <>c::<>9
0x9b7d  ldftn    instance class System.Xaml.XamlDirective <>c::<.cctor>b__204_32()
0x9b83  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlDirective>::.ctor(object, native int)
0x9b88  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x9b8d  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective> System.Xaml.XamlLanguage::s_code
0x9b92  ldsfld   class <>c <>c::<>9
0x9b97  ldftn    instance class System.Xaml.XamlDirective <>c::<.cctor>b__204_33()
0x9b9d  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlDirective>::.ctor(object, native int)
0x9ba2  ldc.i4.1
0x9ba3  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x9ba8  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective> System.Xaml.XamlLanguage::s_connectionId
0x9bad  ldsfld   class <>c <>c::<>9
0x9bb2  ldftn    instance class System.Xaml.XamlDirective <>c::<.cctor>b__204_34()
0x9bb8  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlDirective>::.ctor(object, native int)
0x9bbd  ldc.i4.1
0x9bbe  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x9bc3  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective> System.Xaml.XamlLanguage::s_factoryMethod
0x9bc8  ldsfld   class <>c <>c::<>9
0x9bcd  ldftn    instance class System.Xaml.XamlDirective <>c::<.cctor>b__204_35()
0x9bd3  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlDirective>::.ctor(object, native int)
0x9bd8  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x9bdd  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective> System.Xaml.XamlLanguage::s_fieldModifier
0x9be2  ldsfld   class <>c <>c::<>9
0x9be7  ldftn    instance class System.Xaml.XamlDirective <>c::<.cctor>b__204_36()
0x9bed  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlDirective>::.ctor(object, native int)
0x9bf2  ldc.i4.1
0x9bf3  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x9bf8  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective> System.Xaml.XamlLanguage::s_items
0x9bfd  ldsfld   class <>c <>c::<>9
0x9c02  ldftn    instance class System.Xaml.XamlDirective <>c::<.cctor>b__204_37()
0x9c08  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlDirective>::.ctor(object, native int)
0x9c0d  ldc.i4.1
0x9c0e  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x9c13  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective> System.Xaml.XamlLanguage::s_initialization
0x9c18  ldsfld   class <>c <>c::<>9
0x9c1d  ldftn    instance class System.Xaml.XamlDirective <>c::<.cctor>b__204_38()
0x9c23  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlDirective>::.ctor(object, native int)
0x9c28  ldc.i4.1
0x9c29  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x9c2e  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective> System.Xaml.XamlLanguage::s_key
0x9c33  ldsfld   class <>c <>c::<>9
0x9c38  ldftn    instance class System.Xaml.XamlDirective <>c::<.cctor>b__204_39()
0x9c3e  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlDirective>::.ctor(object, native int)
0x9c43  ldc.i4.1
0x9c44  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x9c49  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective> System.Xaml.XamlLanguage::s_members
0x9c4e  ldsfld   class <>c <>c::<>9
0x9c53  ldftn    instance class System.Xaml.XamlDirective <>c::<.cctor>b__204_40()
0x9c59  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlDirective>::.ctor(object, native int)
0x9c5e  ldc.i4.1
0x9c5f  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x9c64  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective> System.Xaml.XamlLanguage::s_classAttributes
0x9c69  ldsfld   class <>c <>c::<>9
0x9c6e  ldftn    instance class System.Xaml.XamlDirective <>c::<.cctor>b__204_41()
0x9c74  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlDirective>::.ctor(object, native int)
0x9c79  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x9c7e  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective> System.Xaml.XamlLanguage::s_name
0x9c83  ldsfld   class <>c <>c::<>9
0x9c88  ldftn    instance class System.Xaml.XamlDirective <>c::<.cctor>b__204_42()
0x9c8e  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlDirective>::.ctor(object, native int)
0x9c93  ldc.i4.1
0x9c94  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x9c99  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective> System.Xaml.XamlLanguage::s_positionalParameters
0x9c9e  ldsfld   class <>c <>c::<>9
0x9ca3  ldftn    instance class System.Xaml.XamlDirective <>c::<.cctor>b__204_43()
0x9ca9  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlDirective>::.ctor(object, native int)
0x9cae  ldc.i4.1
0x9caf  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x9cb4  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective> System.Xaml.XamlLanguage::s_shared
0x9cb9  ldsfld   class <>c <>c::<>9
0x9cbe  ldftn    instance class System.Xaml.XamlDirective <>c::<.cctor>b__204_44()
0x9cc4  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlDirective>::.ctor(object, native int)
0x9cc9  ldc.i4.1
0x9cca  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x9ccf  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective> System.Xaml.XamlLanguage::s_subclass
0x9cd4  ldsfld   class <>c <>c::<>9
0x9cd9  ldftn    instance class System.Xaml.XamlDirective <>c::<.cctor>b__204_45()
0x9cdf  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlDirective>::.ctor(object, native int)
0x9ce4  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x9ce9  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective> System.Xaml.XamlLanguage::s_synchronousMode
0x9cee  ldsfld   class <>c <>c::<>9
0x9cf3  ldftn    instance class System.Xaml.XamlDirective <>c::<.cctor>b__204_46()
0x9cf9  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlDirective>::.ctor(object, native int)
0x9cfe  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x9d03  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective> System.Xaml.XamlLanguage::s_typeArguments
0x9d08  ldsfld   class <>c <>c::<>9
0x9d0d  ldftn    instance class System.Xaml.XamlDirective <>c::<.cctor>b__204_47()
0x9d13  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlDirective>::.ctor(object, native int)
0x9d18  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x9d1d  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective> System.Xaml.XamlLanguage::s_uid
0x9d22  ldsfld   class <>c <>c::<>9
0x9d27  ldftn    instance class System.Xaml.XamlDirective <>c::<.cctor>b__204_48()
0x9d2d  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlDirective>::.ctor(object, native int)
0x9d32  ldc.i4.1
0x9d33  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x9d38  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective> System.Xaml.XamlLanguage::s_unknownContent
0x9d3d  ldsfld   class <>c <>c::<>9
0x9d42  ldftn    instance class System.Xaml.XamlDirective <>c::<.cctor>b__204_49()
0x9d48  newobj   instance void class [mscorlib]System.Func`1<class System.Xaml.XamlDirective>::.ctor(object, native int)
0x9d4d  newobj   instance void class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x9d52  stsfld   class [mscorlib]System.Lazy`1<class System.Xaml.XamlDirective> System.Xaml.XamlLanguage::s_base
0x9d57  ldsfld   class <>c <>c::<>9
  ... truncated ...
```
