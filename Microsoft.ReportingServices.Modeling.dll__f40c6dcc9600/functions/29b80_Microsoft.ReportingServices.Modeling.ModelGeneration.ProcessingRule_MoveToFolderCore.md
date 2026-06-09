# Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::MoveToFolderCore

- ea: `0x29b80`
- end: `0x29cc1`
- name: `Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::MoveToFolderCore`
- size: `321`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x97d0`
- `0x13a60`
- `0x13b10`
- `0x13b20`
- `0x13df0`
- `0x148b0`
- `0x14c60`
- `0x14c80`
- `0x298b0`
- `0x29a70`
- `0x29b80`

## string_xrefs

- `0x29bbd`: `Cannot create folder as child of `

## pseudocode

```c

```

## disassembly

```asm
0x29b80  ldarg.1
0x29b81  brfalse.s loc_29B86
0x29b83  ldarg.2
0x29b84  brtrue.s loc_29B91
0x29b86  ldstr    aItemOrFolderfr// "item or folderFragment is null"
0x29b8b  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x29b90  throw
0x29b91  ldarg.1
0x29b92  callvirt instance class Microsoft.ReportingServices.Modeling.IOwnedModelItemCollection Microsoft.ReportingServices.Modeling.ModelItem::get_OwnerCollection()
0x29b97  brtrue.s loc_29BA4
0x29b99  ldstr    aItemOwnercolle// "item.OwnerCollection is null"
0x29b9e  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x29ba3  throw
0x29ba4  call     T0x2B000010
0x29ba9  stloc.0
0x29baa  ldarg.1
0x29bab  callvirt instance class Microsoft.ReportingServices.Modeling.IOwnedModelItemCollection Microsoft.ReportingServices.Modeling.ModelItem::get_OwnerCollection()
0x29bb0  ldloc.0
0x29bb1  box      mvar<u1>
0x29bb6  callvirt instance bool Microsoft.ReportingServices.Modeling.IOwnedModelItemCollection::CanContain(class Microsoft.ReportingServices.Modeling.ModelItem item)
0x29bbb  brtrue.s loc_29BDF
0x29bbd  ldstr    aCannotCreateFo// "Cannot create folder as child of "
0x29bc2  ldarg.1
0x29bc3  callvirt instance class Microsoft.ReportingServices.Modeling.ModelItem Microsoft.ReportingServices.Modeling.ModelItem::get_ParentItem()
0x29bc8  dup
0x29bc9  brtrue.s loc_29BCF
0x29bcb  pop
0x29bcc  ldnull
0x29bcd  br.s     loc_29BD4
0x29bcf  callvirt instance string [mscorlib]System.Object::ToString()
0x29bd4  call     string [mscorlib]System.String::Concat(string, string)
0x29bd9  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x29bde  throw
0x29bdf  ldloc.0
0x29be0  box      mvar<u1>
0x29be5  ldarg.2
0x29be6  callvirt instance void Microsoft.ReportingServices.Modeling.ModelItem::LoadFragment(class [System.Xml]System.Xml.XPath.IXPathNavigable fragment)
0x29beb  ldloc.0
0x29bec  box      mvar<u1>
0x29bf1  callvirt instance string Microsoft.ReportingServices.Modeling.ModelItem::get_Name()
0x29bf6  callvirt instance int32 [mscorlib]System.String::get_Length()
0x29bfb  brtrue.s loc_29C08
0x29bfd  ldstr    aFolderNameIsEm// "Folder name is empty"
0x29c02  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x29c07  throw
0x29c08  ldarg.1
0x29c09  callvirt instance class Microsoft.ReportingServices.Modeling.IOwnedModelItemCollection Microsoft.ReportingServices.Modeling.ModelItem::get_OwnerCollection()
0x29c0e  ldloc.0
0x29c0f  box      mvar<u1>
0x29c14  callvirt instance string Microsoft.ReportingServices.Modeling.ModelItem::get_Name()
0x29c19  callvirt instance class Microsoft.ReportingServices.Modeling.ModelItem Microsoft.ReportingServices.Modeling.IOwnedModelItemCollection::get_Item(string name)
0x29c1e  stloc.1
0x29c1f  ldloc.1
0x29c20  isinst   mvar<u1>
0x29c25  brfalse.s loc_29C30
0x29c27  ldloc.1
0x29c28  unbox.any mvar<u1>
0x29c2d  stloc.0
0x29c2e  br.s     loc_29C51
0x29c30  ldarg.0
0x29c31  ldloc.0
0x29c32  box      mvar<u1>
0x29c37  ldarg.1
0x29c38  callvirt instance class Microsoft.ReportingServices.Modeling.IOwnedModelItemCollection Microsoft.ReportingServices.Modeling.ModelItem::get_OwnerCollection()
0x29c3d  call     instance void Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::InsertItemSortedByName(class Microsoft.ReportingServices.Modeling.ModelItem item, class Microsoft.ReportingServices.Modeling.IOwnedModelItemCollection coll)
0x29c42  ldloc.1
0x29c43  brfalse.s loc_29C51
0x29c45  ldarg.0
0x29c46  ldloc.0
0x29c47  box      mvar<u1>
0x29c4c  call     instance void Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::FixNameCollisions(class Microsoft.ReportingServices.Modeling.ModelItem item)
0x29c51  ldloc.0
0x29c52  box      mvar<u1>
0x29c57  callvirt instance class Microsoft.ReportingServices.Modeling.IOwnedModelItemCollection Microsoft.ReportingServices.Modeling.IFolderItem::get_Items()
0x29c5c  ldarg.1
0x29c5d  callvirt instance bool Microsoft.ReportingServices.Modeling.IOwnedModelItemCollection::CanContain(class Microsoft.ReportingServices.Modeling.ModelItem item)
0x29c62  brtrue.s loc_29CA2
0x29c64  ldstr    aFolderItemMism// "Folder/item mismatch ("
0x29c69  ldloc.0
0x29c6a  box      mvar<u1>
0x29c6f  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x29c74  dup
0x29c75  brtrue.s loc_29C7B
0x29c77  pop
0x29c78  ldnull
0x29c79  br.s     loc_29C80
0x29c7b  callvirt instance string [mscorlib]System.Object::ToString()
0x29c80  ldstr    aCannotContain// " cannot contain "
0x29c85  ldarg.1
0x29c86  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x29c8b  dup
0x29c8c  brtrue.s loc_29C92
0x29c8e  pop
0x29c8f  ldnull
0x29c90  br.s     loc_29C97
0x29c92  callvirt instance string [mscorlib]System.Object::ToString()
0x29c97  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x29c9c  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x29ca1  throw
0x29ca2  ldarg.1
0x29ca3  callvirt instance class Microsoft.ReportingServices.Modeling.IOwnedModelItemCollection Microsoft.ReportingServices.Modeling.ModelItem::get_OwnerCollection()
0x29ca8  ldarg.1
0x29ca9  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.ReportingServices.Modeling.ModelItem>::Remove(var<u1>)
0x29cae  pop
0x29caf  ldloc.0
0x29cb0  box      mvar<u1>
0x29cb5  callvirt instance class Microsoft.ReportingServices.Modeling.IOwnedModelItemCollection Microsoft.ReportingServices.Modeling.IFolderItem::get_Items()
0x29cba  ldarg.1
0x29cbb  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.ReportingServices.Modeling.ModelItem>::Add(var<u1>)
0x29cc0  ret
```
