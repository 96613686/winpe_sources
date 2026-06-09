# System.Web.UI.WebControls.WebParts.WebPartConnection::Activate

- ea: `0x102d80`
- end: `0x103119`
- name: `System.Web.UI.WebControls.WebParts.WebPartConnection::Activate`
- size: `921`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `broker_com_uri`

## callers

- `0x1055b0`

## callees

- `0x169c0`
- `0x34f20`
- `0x34fa0`
- `0x5ef80`
- `0xf3840`
- `0xf3870`
- `0xf3880`
- `0xf6e90`
- `0xf6ec0`
- `0xfd4e0`
- `0xfd4f0`
- `0x1005b0`
- `0x100b80`
- `0x100d10`
- `0x101070`
- `0x1011d0`
- `0x102b10`
- `0x102b50`
- `0x102c60`
- `0x102ca0`
- `0x102d30`
- `0x102d60`
- `0x102d80`
- `0x104ac0`
- `0x10c5f0`
- `0x10c680`
- `0x10c690`
- `0x10c920`

## string_xrefs

- `0x102e8c`: `WebPartConnection_IncompatibleSecondaryInterfaces`
- `0x102ecd`: `WebPartConnection_NoCommonInterface`
- `0x10303c`: `WebPartConnection_IncompatibleProviderTransformer`
- `0x103063`: `WebPartConnection_IncompatibleProviderTransformerWithType`
- `0x1030ba`: `WebPartConnection_IncompatibleConsumerTransformer`
- `0x1030e1`: `WebPartConnection_IncompatibleConsumerTransformerWithType`

## pseudocode

```c

```

## disassembly

```asm
0x102d80  ldarg.0
0x102d81  call     instance class System.Web.UI.WebControls.WebParts.WebPartTransformerCollection System.Web.UI.WebControls.WebParts.WebPartConnection::get_Transformers()
0x102d86  callvirt instance void System.Web.UI.WebControls.WebParts.WebPartTransformerCollection::SetReadOnly()
0x102d8b  ldarg.0
0x102d8c  call     instance class System.Web.UI.WebControls.WebParts.WebPart System.Web.UI.WebControls.WebParts.WebPartConnection::get_Provider()
0x102d91  stloc.0
0x102d92  ldarg.0
0x102d93  call     instance class System.Web.UI.WebControls.WebParts.WebPart System.Web.UI.WebControls.WebParts.WebPartConnection::get_Consumer()
0x102d98  stloc.1
0x102d99  ldloc.0
0x102d9a  callvirt instance class System.Web.UI.Control System.Web.UI.WebControls.WebParts.WebPart::ToControl()
0x102d9f  stloc.2
0x102da0  ldloc.1
0x102da1  callvirt instance class System.Web.UI.Control System.Web.UI.WebControls.WebParts.WebPart::ToControl()
0x102da6  stloc.3
0x102da7  ldarg.0
0x102da8  call     instance class System.Web.UI.WebControls.WebParts.ProviderConnectionPoint System.Web.UI.WebControls.WebParts.WebPartConnection::get_ProviderConnectionPoint()
0x102dad  stloc.s  4
0x102daf  ldloc.s  4
0x102db1  ldloc.2
0x102db2  callvirt instance bool System.Web.UI.WebControls.WebParts.ConnectionPoint::GetEnabled(class System.Web.UI.Control control)
0x102db7  brtrue.s loc_102DE3
0x102db9  ldloc.1
0x102dba  ldstr    aWebpartconnect_2// "WebPartConnection_DisabledConnectionPoi"...
0x102dbf  ldc.i4.2
0x102dc0  newarr   [mscorlib]System.Object
0x102dc5  dup
0x102dc6  ldc.i4.0
0x102dc7  ldloc.s  4
0x102dc9  callvirt instance string System.Web.UI.WebControls.WebParts.ConnectionPoint::get_DisplayName()
0x102dce  stelem.ref
0x102dcf  dup
0x102dd0  ldc.i4.1
0x102dd1  ldloc.0
0x102dd2  callvirt instance string System.Web.UI.WebControls.WebParts.WebPart::get_DisplayTitle()
0x102dd7  stelem.ref
0x102dd8  call     string System.Web.SR::GetString(string name, object[] args)
0x102ddd  callvirt instance void System.Web.UI.WebControls.WebParts.WebPart::SetConnectErrorMessage(string connectErrorMessage)
0x102de2  ret
0x102de3  ldarg.0
0x102de4  call     instance class System.Web.UI.WebControls.WebParts.ConsumerConnectionPoint System.Web.UI.WebControls.WebParts.WebPartConnection::get_ConsumerConnectionPoint()
0x102de9  stloc.s  5
0x102deb  ldloc.s  5
0x102ded  ldloc.3
0x102dee  callvirt instance bool System.Web.UI.WebControls.WebParts.ConnectionPoint::GetEnabled(class System.Web.UI.Control control)
0x102df3  brtrue.s loc_102E1F
0x102df5  ldloc.1
0x102df6  ldstr    aWebpartconnect_2// "WebPartConnection_DisabledConnectionPoi"...
0x102dfb  ldc.i4.2
0x102dfc  newarr   [mscorlib]System.Object
0x102e01  dup
0x102e02  ldc.i4.0
0x102e03  ldloc.s  5
0x102e05  callvirt instance string System.Web.UI.WebControls.WebParts.ConnectionPoint::get_DisplayName()
0x102e0a  stelem.ref
0x102e0b  dup
0x102e0c  ldc.i4.1
0x102e0d  ldloc.1
0x102e0e  callvirt instance string System.Web.UI.WebControls.WebParts.WebPart::get_DisplayTitle()
0x102e13  stelem.ref
0x102e14  call     string System.Web.SR::GetString(string name, object[] args)
0x102e19  callvirt instance void System.Web.UI.WebControls.WebParts.WebPart::SetConnectErrorMessage(string connectErrorMessage)
0x102e1e  ret
0x102e1f  ldloc.0
0x102e20  callvirt instance bool System.Web.UI.WebControls.WebParts.WebPart::get_IsClosed()
0x102e25  brtrue   loc_103118
0x102e2a  ldloc.1
0x102e2b  callvirt instance bool System.Web.UI.WebControls.WebParts.WebPart::get_IsClosed()
0x102e30  brtrue   loc_103118
0x102e35  ldarg.0
0x102e36  call     instance class System.Web.UI.WebControls.WebParts.WebPartTransformer System.Web.UI.WebControls.WebParts.WebPartConnection::get_Transformer()
0x102e3b  stloc.s  6
0x102e3d  ldloc.s  6
0x102e3f  brtrue   loc_102F0D
0x102e44  ldloc.s  4
0x102e46  callvirt instance class [mscorlib]System.Type System.Web.UI.WebControls.WebParts.ConnectionPoint::get_InterfaceType()
0x102e4b  ldloc.s  5
0x102e4d  callvirt instance class [mscorlib]System.Type System.Web.UI.WebControls.WebParts.ConnectionPoint::get_InterfaceType()
0x102e52  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x102e57  brfalse.s loc_102ECC
0x102e59  ldloc.s  4
0x102e5b  ldloc.2
0x102e5c  callvirt instance class System.Web.UI.WebControls.WebParts.ConnectionInterfaceCollection System.Web.UI.WebControls.WebParts.ProviderConnectionPoint::GetSecondaryInterfaces(class System.Web.UI.Control control)
0x102e61  stloc.s  7
0x102e63  ldloc.s  5
0x102e65  ldloc.3
0x102e66  ldloc.s  7
0x102e68  callvirt instance bool System.Web.UI.WebControls.WebParts.ConsumerConnectionPoint::SupportsConnection(class System.Web.UI.Control control, class System.Web.UI.WebControls.WebParts.ConnectionInterfaceCollection secondaryInterfaces)
0x102e6d  brfalse.s loc_102E8B
0x102e6f  ldloc.s  4
0x102e71  ldloc.2
0x102e72  callvirt instance object System.Web.UI.WebControls.WebParts.ProviderConnectionPoint::GetObject(class System.Web.UI.Control control)
0x102e77  stloc.s  8
0x102e79  ldloc.s  5
0x102e7b  ldloc.3
0x102e7c  ldloc.s  8
0x102e7e  callvirt instance void System.Web.UI.WebControls.WebParts.ConsumerConnectionPoint::SetObject(class System.Web.UI.Control control, object data)
0x102e83  ldarg.0
0x102e84  ldc.i4.1
0x102e85  stfld    bool System.Web.UI.WebControls.WebParts.WebPartConnection::_isActive
0x102e8a  ret
0x102e8b  ldloc.1
0x102e8c  ldstr    aWebpartconnect_3// "WebPartConnection_IncompatibleSecondary"...
0x102e91  ldc.i4.4
0x102e92  newarr   [mscorlib]System.String
0x102e97  dup
0x102e98  ldc.i4.0
0x102e99  ldloc.s  5
0x102e9b  callvirt instance string System.Web.UI.WebControls.WebParts.ConnectionPoint::get_DisplayName()
0x102ea0  stelem.ref
0x102ea1  dup
0x102ea2  ldc.i4.1
0x102ea3  ldloc.1
0x102ea4  callvirt instance string System.Web.UI.WebControls.WebParts.WebPart::get_DisplayTitle()
0x102ea9  stelem.ref
0x102eaa  dup
0x102eab  ldc.i4.2
0x102eac  ldloc.s  4
0x102eae  callvirt instance string System.Web.UI.WebControls.WebParts.ConnectionPoint::get_DisplayName()
0x102eb3  stelem.ref
0x102eb4  dup
0x102eb5  ldc.i4.3
0x102eb6  ldloc.0
0x102eb7  callvirt instance string System.Web.UI.WebControls.WebParts.WebPart::get_DisplayTitle()
0x102ebc  stelem.ref
0x102ebd  stloc.s  9
0x102ebf  ldloc.s  9
0x102ec1  call     string System.Web.SR::GetString(string name, object[] args)
0x102ec6  callvirt instance void System.Web.UI.WebControls.WebParts.WebPart::SetConnectErrorMessage(string connectErrorMessage)
0x102ecb  ret
0x102ecc  ldloc.1
0x102ecd  ldstr    aWebpartconnect_4// "WebPartConnection_NoCommonInterface"
0x102ed2  ldc.i4.4
0x102ed3  newarr   [mscorlib]System.String
0x102ed8  dup
0x102ed9  ldc.i4.0
0x102eda  ldloc.s  4
0x102edc  callvirt instance string System.Web.UI.WebControls.WebParts.ConnectionPoint::get_DisplayName()
0x102ee1  stelem.ref
0x102ee2  dup
0x102ee3  ldc.i4.1
0x102ee4  ldloc.0
0x102ee5  callvirt instance string System.Web.UI.WebControls.WebParts.WebPart::get_DisplayTitle()
0x102eea  stelem.ref
0x102eeb  dup
0x102eec  ldc.i4.2
0x102eed  ldloc.s  5
0x102eef  callvirt instance string System.Web.UI.WebControls.WebParts.ConnectionPoint::get_DisplayName()
0x102ef4  stelem.ref
0x102ef5  dup
0x102ef6  ldc.i4.3
0x102ef7  ldloc.1
0x102ef8  callvirt instance string System.Web.UI.WebControls.WebParts.WebPart::get_DisplayTitle()
0x102efd  stelem.ref
0x102efe  stloc.s  9
0x102f00  ldloc.s  9
0x102f02  call     string System.Web.SR::GetString(string name, object[] args)
0x102f07  callvirt instance void System.Web.UI.WebControls.WebParts.WebPart::SetConnectErrorMessage(string connectErrorMessage)
0x102f0c  ret
0x102f0d  ldloc.s  6
0x102f0f  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x102f14  stloc.s  0xA
0x102f16  ldarg.0
0x102f17  ldfld    class System.Web.UI.WebControls.WebParts.WebPartManager System.Web.UI.WebControls.WebParts.WebPartConnection::_webPartManager
0x102f1c  callvirt instance class System.Web.UI.WebControls.WebParts.TransformerTypeCollection System.Web.UI.WebControls.WebParts.WebPartManager::get_AvailableTransformers()
0x102f21  ldloc.s  0xA
0x102f23  callvirt instance bool System.Web.UI.WebControls.WebParts.TransformerTypeCollection::Contains(class [mscorlib]System.Type value)
0x102f28  brtrue.s loc_102F7B
0x102f2a  ldarg.0
0x102f2b  ldfld    class System.Web.UI.WebControls.WebParts.WebPartManager System.Web.UI.WebControls.WebParts.WebPartConnection::_webPartManager
0x102f30  callvirt instance class System.Web.HttpContext System.Web.UI.Control::get_Context()
0x102f35  brfalse.s loc_102F57
0x102f37  ldarg.0
0x102f38  ldfld    class System.Web.UI.WebControls.WebParts.WebPartManager System.Web.UI.WebControls.WebParts.WebPartConnection::_webPartManager
0x102f3d  callvirt instance class System.Web.HttpContext System.Web.UI.Control::get_Context()
0x102f42  callvirt instance bool System.Web.HttpContext::get_IsCustomErrorEnabled()
0x102f47  brfalse.s loc_102F57
0x102f49  ldstr    aWebpartconnect_5// "WebPartConnection_TransformerNotAvailab"...
0x102f4e  call     string System.Web.SR::GetString(string name)
0x102f53  stloc.s  0xD
0x102f55  br.s     loc_102F73
0x102f57  ldstr    aWebpartconnect_6// "WebPartConnection_TransformerNotAvailab"...
0x102f5c  ldc.i4.1
0x102f5d  newarr   [mscorlib]System.Object
0x102f62  dup
0x102f63  ldc.i4.0
0x102f64  ldloc.s  0xA
0x102f66  callvirt instance string [mscorlib]System.Type::get_FullName()
0x102f6b  stelem.ref
0x102f6c  call     string System.Web.SR::GetString(string name, object[] args)
0x102f71  stloc.s  0xD
0x102f73  ldloc.1
0x102f74  ldloc.s  0xD
0x102f76  callvirt instance void System.Web.UI.WebControls.WebParts.WebPart::SetConnectErrorMessage(string connectErrorMessage)
0x102f7b  ldloc.s  0xA
0x102f7d  call     class [mscorlib]System.Type System.Web.UI.WebControls.WebParts.WebPartTransformerAttribute::GetConsumerType(class [mscorlib]System.Type transformerType)
0x102f82  stloc.s  0xB
0x102f84  ldloc.s  0xA
0x102f86  call     class [mscorlib]System.Type System.Web.UI.WebControls.WebParts.WebPartTransformerAttribute::GetProviderType(class [mscorlib]System.Type transformerType)
0x102f8b  stloc.s  0xC
0x102f8d  ldloc.s  4
0x102f8f  callvirt instance class [mscorlib]System.Type System.Web.UI.WebControls.WebParts.ConnectionPoint::get_InterfaceType()
0x102f94  ldloc.s  0xB
0x102f96  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x102f9b  brfalse.s loc_10300D
0x102f9d  ldloc.s  0xC
0x102f9f  ldloc.s  5
0x102fa1  callvirt instance class [mscorlib]System.Type System.Web.UI.WebControls.WebParts.ConnectionPoint::get_InterfaceType()
0x102fa6  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x102fab  brfalse.s loc_10300D
0x102fad  ldloc.s  5
0x102faf  ldloc.3
0x102fb0  ldsfld   class System.Web.UI.WebControls.WebParts.ConnectionInterfaceCollection System.Web.UI.WebControls.WebParts.ConnectionInterfaceCollection::Empty
0x102fb5  callvirt instance bool System.Web.UI.WebControls.WebParts.ConsumerConnectionPoint::SupportsConnection(class System.Web.UI.Control control, class System.Web.UI.WebControls.WebParts.ConnectionInterfaceCollection secondaryInterfaces)
0x102fba  brfalse.s loc_102FE3
0x102fbc  ldloc.s  4
0x102fbe  ldloc.2
0x102fbf  callvirt instance object System.Web.UI.WebControls.WebParts.ProviderConnectionPoint::GetObject(class System.Web.UI.Control control)
0x102fc4  stloc.s  0xE
0x102fc6  ldloc.s  6
0x102fc8  ldloc.s  0xE
0x102fca  callvirt instance object System.Web.UI.WebControls.WebParts.WebPartTransformer::Transform(object providerData)
0x102fcf  stloc.s  0xF
0x102fd1  ldloc.s  5
0x102fd3  ldloc.3
0x102fd4  ldloc.s  0xF
0x102fd6  callvirt instance void System.Web.UI.WebControls.WebParts.ConsumerConnectionPoint::SetObject(class System.Web.UI.Control control, object data)
0x102fdb  ldarg.0
0x102fdc  ldc.i4.1
0x102fdd  stfld    bool System.Web.UI.WebControls.WebParts.WebPartConnection::_isActive
0x102fe2  ret
0x102fe3  ldloc.1
0x102fe4  ldstr    aWebpartconnect_7// "WebPartConnection_ConsumerRequiresSecon"...
0x102fe9  ldc.i4.2
0x102fea  newarr   [mscorlib]System.Object
0x102fef  dup
0x102ff0  ldc.i4.0
0x102ff1  ldloc.s  5
0x102ff3  callvirt instance string System.Web.UI.WebControls.WebParts.ConnectionPoint::get_DisplayName()
0x102ff8  stelem.ref
0x102ff9  dup
0x102ffa  ldc.i4.1
0x102ffb  ldloc.1
0x102ffc  callvirt instance string System.Web.UI.WebControls.WebParts.WebPart::get_DisplayTitle()
0x103001  stelem.ref
0x103002  call     string System.Web.SR::GetString(string name, object[] args)
0x103007  callvirt instance void System.Web.UI.WebControls.WebParts.WebPart::SetConnectErrorMessage(string connectErrorMessage)
0x10300c  ret
0x10300d  ldloc.s  4
0x10300f  callvirt instance class [mscorlib]System.Type System.Web.UI.WebControls.WebParts.ConnectionPoint::get_InterfaceType()
0x103014  ldloc.s  0xB
0x103016  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x10301b  brfalse.s loc_10309B
0x10301d  ldarg.0
0x10301e  ldfld    class System.Web.UI.WebControls.WebParts.WebPartManager System.Web.UI.WebControls.WebParts.WebPartConnection::_webPartManager
0x103023  callvirt instance class System.Web.HttpContext System.Web.UI.Control::get_Context()
0x103028  brfalse.s loc_103063
0x10302a  ldarg.0
0x10302b  ldfld    class System.Web.UI.WebControls.WebParts.WebPartManager System.Web.UI.WebControls.WebParts.WebPartConnection::_webPartManager
0x103030  callvirt instance class System.Web.HttpContext System.Web.UI.Control::get_Context()
0x103035  callvirt instance bool System.Web.HttpContext::get_IsCustomErrorEnabled()
0x10303a  brfalse.s loc_103063
0x10303c  ldstr    aWebpartconnect_8// "WebPartConnection_IncompatibleProviderT"...
0x103041  ldc.i4.2
0x103042  newarr   [mscorlib]System.Object
0x103047  dup
0x103048  ldc.i4.0
0x103049  ldloc.s  4
0x10304b  callvirt instance string System.Web.UI.WebControls.WebParts.ConnectionPoint::get_DisplayName()
0x103050  stelem.ref
0x103051  dup
0x103052  ldc.i4.1
0x103053  ldloc.0
0x103054  callvirt instance string System.Web.UI.WebControls.WebParts.WebPart::get_DisplayTitle()
0x103059  stelem.ref
0x10305a  call     string System.Web.SR::GetString(string name, object[] args)
0x10305f  stloc.s  0x10
0x103061  br.s     loc_103092
0x103063  ldstr    aWebpartconnect_9// "WebPartConnection_IncompatibleProviderT"...
0x103068  ldc.i4.3
0x103069  newarr   [mscorlib]System.Object
0x10306e  dup
0x10306f  ldc.i4.0
0x103070  ldloc.s  4
0x103072  callvirt instance string System.Web.UI.WebControls.WebParts.ConnectionPoint::get_DisplayName()
0x103077  stelem.ref
0x103078  dup
0x103079  ldc.i4.1
0x10307a  ldloc.0
0x10307b  callvirt instance string System.Web.UI.WebControls.WebParts.WebPart::get_DisplayTitle()
0x103080  stelem.ref
0x103081  dup
0x103082  ldc.i4.2
0x103083  ldloc.s  0xA
0x103085  callvirt instance string [mscorlib]System.Type::get_FullName()
0x10308a  stelem.ref
0x10308b  call     string System.Web.SR::GetString(string name, object[] args)
0x103090  stloc.s  0x10
0x103092  ldloc.1
0x103093  ldloc.s  0x10
  ... truncated ...
```
