# System.ComponentModel.Design.DesignerHost::System.ComponentModel.Design.IDesignerHost.DestroyComponent

- ea: `0x5f450`
- end: `0x5f531`
- name: `System.ComponentModel.Design.DesignerHost::System.ComponentModel.Design.IDesignerHost.DestroyComponent`
- size: `225`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x5f450`
- `0x8eec0`

## string_xrefs

- `0x5f453`: `component`
- `0x5f4b4`: `DesignerHostCantDestroyInheritedComponent`
- `0x5f4cf`: `DesignerHostCantDestroyInheritedComponent`
- `0x5f4f2`: `DesignerHostDestroyComponentTransaction`

## pseudocode

```c

```

## disassembly

```asm
0x5f450  ldarg.1
0x5f451  brtrue.s loc_5F45E
0x5f453  ldstr    aComponent// "component"
0x5f458  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5f45d  throw
0x5f45e  ldarg.1
0x5f45f  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0x5f464  brfalse.s loc_5F481
0x5f466  ldarg.1
0x5f467  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0x5f46c  callvirt instance string [System]System.ComponentModel.ISite::get_Name()
0x5f471  brfalse.s loc_5F481
0x5f473  ldarg.1
0x5f474  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0x5f479  callvirt instance string [System]System.ComponentModel.ISite::get_Name()
0x5f47e  stloc.0
0x5f47f  br.s     loc_5F48D
0x5f481  ldarg.1
0x5f482  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x5f487  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x5f48c  stloc.0
0x5f48d  ldarg.1
0x5f48e  call     class [System]System.ComponentModel.AttributeCollection [System]System.ComponentModel.TypeDescriptor::GetAttributes(object)
0x5f493  ldtoken  [System]System.ComponentModel.InheritanceAttribute
0x5f498  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5f49d  callvirt instance class [mscorlib]System.Attribute [System]System.ComponentModel.AttributeCollection::get_Item(class [mscorlib]System.Type)
0x5f4a2  castclass [System]System.ComponentModel.InheritanceAttribute
0x5f4a7  stloc.1
0x5f4a8  ldloc.1
0x5f4a9  brfalse.s loc_5F4DB
0x5f4ab  ldloc.1
0x5f4ac  callvirt instance valuetype [System]System.ComponentModel.InheritanceLevel [System]System.ComponentModel.InheritanceAttribute::get_InheritanceLevel()
0x5f4b1  ldc.i4.3
0x5f4b2  beq.s    loc_5F4DB
0x5f4b4  ldstr    aDesignerhostca// "DesignerHostCantDestroyInheritedCompone"...
0x5f4b9  ldc.i4.1
0x5f4ba  newarr   [mscorlib]System.Object
0x5f4bf  dup
0x5f4c0  ldc.i4.0
0x5f4c1  ldloc.0
0x5f4c2  stelem.ref
0x5f4c3  call     string System.Design.SR::GetString(string name, object[] args)
0x5f4c8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x5f4cd  stloc.2
0x5f4ce  ldloc.2
0x5f4cf  ldstr    aDesignerhostca// "DesignerHostCantDestroyInheritedCompone"...
0x5f4d4  callvirt instance void [mscorlib]System.Exception::set_HelpLink(string)
0x5f4d9  ldloc.2
0x5f4da  throw
0x5f4db  ldarg.0
0x5f4dc  callvirt instance bool [System]System.ComponentModel.Design.IDesignerHost::get_InTransaction()
0x5f4e1  brfalse.s loc_5F4F1
0x5f4e3  ldarg.0
0x5f4e4  ldarg.1
0x5f4e5  callvirt instance void [System]System.ComponentModel.Container::Remove(class [System]System.ComponentModel.IComponent)
0x5f4ea  ldarg.1
0x5f4eb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5f4f0  ret
0x5f4f1  ldarg.0
0x5f4f2  ldstr    aDesignerhostde_0// "DesignerHostDestroyComponentTransaction"
0x5f4f7  ldc.i4.1
0x5f4f8  newarr   [mscorlib]System.Object
0x5f4fd  dup
0x5f4fe  ldc.i4.0
0x5f4ff  ldloc.0
0x5f500  stelem.ref
0x5f501  call     string System.Design.SR::GetString(string name, object[] args)
0x5f506  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0x5f50b  dup
0x5f50c  stloc.3
0x5f50d  stloc.s  4
0x5f50f  ldarg.0
0x5f510  ldarg.1
0x5f511  callvirt instance void [System]System.ComponentModel.Container::Remove(class [System]System.ComponentModel.IComponent)
0x5f516  ldarg.1
0x5f517  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5f51c  ldloc.3
0x5f51d  callvirt instance void [System]System.ComponentModel.Design.DesignerTransaction::Commit()
0x5f522  leave.s  loc_5F530
0x5f524  ldloc.s  4
0x5f526  brfalse.s loc_5F52F
0x5f528  ldloc.s  4
0x5f52a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5f52f  endfinally
0x5f530  ret
```
