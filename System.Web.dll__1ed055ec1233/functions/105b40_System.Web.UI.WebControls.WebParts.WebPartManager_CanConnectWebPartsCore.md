# System.Web.UI.WebControls.WebParts.WebPartManager::CanConnectWebPartsCore

- ea: `0x105b40`
- end: `0x106016`
- name: `System.Web.UI.WebControls.WebParts.WebPartManager::CanConnectWebPartsCore`
- size: `1238`
- prototype: ``
- caller_count: `2`
- callee_count: `28`
- tags: `broker_com_uri`

## callers

- `0x105b30`
- `0x106700`

## callees

- `0x34f20`
- `0x34fa0`
- `0x5f1b0`
- `0x611a0`
- `0x66530`
- `0xf3810`
- `0xf3830`
- `0xf3840`
- `0xf3850`
- `0xf3870`
- `0xf3880`
- `0xf6ec0`
- `0xfd4e0`
- `0x1005b0`
- `0x100d10`
- `0x1011d0`
- `0x102b10`
- `0x102b50`
- `0x102c60`
- `0x102ca0`
- `0x104ac0`
- `0x104b30`
- `0x104f20`
- `0x105b40`
- `0x10bb00`
- `0x10bea0`
- `0x10c680`
- `0x10c690`

## string_xrefs

- `0x105eb8`: `WebPartConnection_IncompatibleSecondaryInterfaces`
- `0x105e5b`: `WebPartConnection_NoCommonInterface`
- `0x105f56`: `WebPartConnection_IncompatibleProviderTransformer`
- `0x105f9e`: `WebPartConnection_IncompatibleConsumerTransformer`

## pseudocode

```c

```

## disassembly

```asm
0x105b40  ldarg.0
0x105b41  call     instance class System.Web.UI.WebControls.WebParts.WebPartPersonalization System.Web.UI.WebControls.WebParts.WebPartManager::get_Personalization()
0x105b46  callvirt instance bool System.Web.UI.WebControls.WebParts.WebPartPersonalization::get_IsModifiable()
0x105b4b  brtrue.s loc_105B61
0x105b4d  ldarg.s  6
0x105b4f  brfalse.s loc_105B5F
0x105b51  ldarg.0
0x105b52  call     instance class System.Web.UI.WebControls.WebParts.WebPartPersonalization System.Web.UI.WebControls.WebParts.WebPartManager::get_Personalization()
0x105b57  ldc.i4.1
0x105b58  callvirt instance void System.Web.UI.WebControls.WebParts.WebPartPersonalization::EnsureEnabled(bool ensureModifiable)
0x105b5d  br.s     loc_105B61
0x105b5f  ldc.i4.0
0x105b60  ret
0x105b61  ldarg.1
0x105b62  brtrue.s loc_105B6F
0x105b64  ldstr    aProvider// "provider"
0x105b69  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x105b6e  throw
0x105b6f  ldarg.0
0x105b70  callvirt instance class System.Web.UI.ControlCollection System.Web.UI.Control::get_Controls()
0x105b75  ldarg.1
0x105b76  callvirt instance bool System.Web.UI.ControlCollection::Contains(class System.Web.UI.Control c)
0x105b7b  brtrue.s loc_105B92
0x105b7d  ldstr    aUnknownwebpart// "UnknownWebPart"
0x105b82  call     string System.Web.SR::GetString(string name)
0x105b87  ldstr    aProvider// "provider"
0x105b8c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x105b91  throw
0x105b92  ldarg.3
0x105b93  brtrue.s loc_105BA0
0x105b95  ldstr    aConsumer// "consumer"
0x105b9a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x105b9f  throw
0x105ba0  ldarg.0
0x105ba1  callvirt instance class System.Web.UI.ControlCollection System.Web.UI.Control::get_Controls()
0x105ba6  ldarg.3
0x105ba7  callvirt instance bool System.Web.UI.ControlCollection::Contains(class System.Web.UI.Control c)
0x105bac  brtrue.s loc_105BC3
0x105bae  ldstr    aUnknownwebpart// "UnknownWebPart"
0x105bb3  call     string System.Web.SR::GetString(string name)
0x105bb8  ldstr    aConsumer// "consumer"
0x105bbd  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x105bc2  throw
0x105bc3  ldarg.2
0x105bc4  brtrue.s loc_105BD1
0x105bc6  ldstr    aProviderconnec_0// "providerConnectionPoint"
0x105bcb  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x105bd0  throw
0x105bd1  ldarg.s  4
0x105bd3  brtrue.s loc_105BE0
0x105bd5  ldstr    aConsumerconnec_0// "consumerConnectionPoint"
0x105bda  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x105bdf  throw
0x105be0  ldarg.1
0x105be1  callvirt instance class System.Web.UI.Control System.Web.UI.WebControls.WebParts.WebPart::ToControl()
0x105be6  stloc.0
0x105be7  ldarg.3
0x105be8  callvirt instance class System.Web.UI.Control System.Web.UI.WebControls.WebParts.WebPart::ToControl()
0x105bed  stloc.1
0x105bee  ldarg.2
0x105bef  callvirt instance class [mscorlib]System.Type System.Web.UI.WebControls.WebParts.ConnectionPoint::get_ControlType()
0x105bf4  ldloc.0
0x105bf5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x105bfa  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x105bff  brfalse.s loc_105C16
0x105c01  ldstr    aWebpartmanager_20// "WebPartManager_InvalidConnectionPoint"
0x105c06  call     string System.Web.SR::GetString(string name)
0x105c0b  ldstr    aProviderconnec_0// "providerConnectionPoint"
0x105c10  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x105c15  throw
0x105c16  ldarg.s  4
0x105c18  callvirt instance class [mscorlib]System.Type System.Web.UI.WebControls.WebParts.ConnectionPoint::get_ControlType()
0x105c1d  ldloc.1
0x105c1e  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x105c23  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x105c28  brfalse.s loc_105C3F
0x105c2a  ldstr    aWebpartmanager_20// "WebPartManager_InvalidConnectionPoint"
0x105c2f  call     string System.Web.SR::GetString(string name)
0x105c34  ldstr    aConsumerconnec_0// "consumerConnectionPoint"
0x105c39  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x105c3e  throw
0x105c3f  ldarg.1
0x105c40  ldarg.3
0x105c41  bne.un.s loc_105C59
0x105c43  ldarg.s  6
0x105c45  brfalse.s loc_105C57
0x105c47  ldstr    aWebpartmanager_21// "WebPartManager_CantConnectToSelf"
0x105c4c  call     string System.Web.SR::GetString(string name)
0x105c51  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x105c56  throw
0x105c57  ldc.i4.0
0x105c58  ret
0x105c59  ldarg.1
0x105c5a  callvirt instance bool System.Web.UI.WebControls.WebParts.WebPart::get_IsClosed()
0x105c5f  brfalse.s loc_105C86
0x105c61  ldarg.s  6
0x105c63  brfalse.s loc_105C84
0x105c65  ldstr    aWebpartmanager_22// "WebPartManager_CantConnectClosed"
0x105c6a  ldc.i4.1
0x105c6b  newarr   [mscorlib]System.Object
0x105c70  dup
0x105c71  ldc.i4.0
0x105c72  ldarg.1
0x105c73  callvirt instance string System.Web.UI.Control::get_ID()
0x105c78  stelem.ref
0x105c79  call     string System.Web.SR::GetString(string name, object[] args)
0x105c7e  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x105c83  throw
0x105c84  ldc.i4.0
0x105c85  ret
0x105c86  ldarg.3
0x105c87  callvirt instance bool System.Web.UI.WebControls.WebParts.WebPart::get_IsClosed()
0x105c8c  brfalse.s loc_105CB3
0x105c8e  ldarg.s  6
0x105c90  brfalse.s loc_105CB1
0x105c92  ldstr    aWebpartmanager_22// "WebPartManager_CantConnectClosed"
0x105c97  ldc.i4.1
0x105c98  newarr   [mscorlib]System.Object
0x105c9d  dup
0x105c9e  ldc.i4.0
0x105c9f  ldarg.3
0x105ca0  callvirt instance string System.Web.UI.Control::get_ID()
0x105ca5  stelem.ref
0x105ca6  call     string System.Web.SR::GetString(string name, object[] args)
0x105cab  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x105cb0  throw
0x105cb1  ldc.i4.0
0x105cb2  ret
0x105cb3  ldarg.2
0x105cb4  ldloc.0
0x105cb5  callvirt instance bool System.Web.UI.WebControls.WebParts.ConnectionPoint::GetEnabled(class System.Web.UI.Control control)
0x105cba  brtrue.s loc_105CEA
0x105cbc  ldarg.s  6
0x105cbe  brfalse.s loc_105CE8
0x105cc0  ldstr    aWebpartconnect_2// "WebPartConnection_DisabledConnectionPoi"...
0x105cc5  ldc.i4.2
0x105cc6  newarr   [mscorlib]System.Object
0x105ccb  dup
0x105ccc  ldc.i4.0
0x105ccd  ldarg.2
0x105cce  callvirt instance string System.Web.UI.WebControls.WebParts.ConnectionPoint::get_ID()
0x105cd3  stelem.ref
0x105cd4  dup
0x105cd5  ldc.i4.1
0x105cd6  ldarg.1
0x105cd7  callvirt instance string System.Web.UI.Control::get_ID()
0x105cdc  stelem.ref
0x105cdd  call     string System.Web.SR::GetString(string name, object[] args)
0x105ce2  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x105ce7  throw
0x105ce8  ldc.i4.0
0x105ce9  ret
0x105cea  ldarg.s  4
0x105cec  ldloc.1
0x105ced  callvirt instance bool System.Web.UI.WebControls.WebParts.ConnectionPoint::GetEnabled(class System.Web.UI.Control control)
0x105cf2  brtrue.s loc_105D23
0x105cf4  ldarg.s  6
0x105cf6  brfalse.s loc_105D21
0x105cf8  ldstr    aWebpartconnect_2// "WebPartConnection_DisabledConnectionPoi"...
0x105cfd  ldc.i4.2
0x105cfe  newarr   [mscorlib]System.Object
0x105d03  dup
0x105d04  ldc.i4.0
0x105d05  ldarg.s  4
0x105d07  callvirt instance string System.Web.UI.WebControls.WebParts.ConnectionPoint::get_ID()
0x105d0c  stelem.ref
0x105d0d  dup
0x105d0e  ldc.i4.1
0x105d0f  ldarg.3
0x105d10  callvirt instance string System.Web.UI.Control::get_ID()
0x105d15  stelem.ref
0x105d16  call     string System.Web.SR::GetString(string name, object[] args)
0x105d1b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x105d20  throw
0x105d21  ldc.i4.0
0x105d22  ret
0x105d23  ldarg.2
0x105d24  callvirt instance bool System.Web.UI.WebControls.WebParts.ConnectionPoint::get_AllowsMultipleConnections()
0x105d29  brtrue.s loc_105DA9
0x105d2b  ldarg.0
0x105d2c  call     instance class System.Web.UI.WebControls.WebParts.WebPartConnectionCollection System.Web.UI.WebControls.WebParts.WebPartManager::get_Connections()
0x105d31  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x105d36  stloc.2
0x105d37  br.s     loc_105D8B
0x105d39  ldloc.2
0x105d3a  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x105d3f  castclass System.Web.UI.WebControls.WebParts.WebPartConnection
0x105d44  stloc.3
0x105d45  ldloc.3
0x105d46  callvirt instance class System.Web.UI.WebControls.WebParts.WebPart System.Web.UI.WebControls.WebParts.WebPartConnection::get_Provider()
0x105d4b  ldarg.1
0x105d4c  bne.un.s loc_105D8B
0x105d4e  ldloc.3
0x105d4f  callvirt instance class System.Web.UI.WebControls.WebParts.ProviderConnectionPoint System.Web.UI.WebControls.WebParts.WebPartConnection::get_ProviderConnectionPoint()
0x105d54  ldarg.2
0x105d55  bne.un.s loc_105D8B
0x105d57  ldarg.s  6
0x105d59  brfalse.s loc_105D83
0x105d5b  ldstr    aWebpartconnect_24// "WebPartConnection_Duplicate"
0x105d60  ldc.i4.2
0x105d61  newarr   [mscorlib]System.Object
0x105d66  dup
0x105d67  ldc.i4.0
0x105d68  ldarg.2
0x105d69  callvirt instance string System.Web.UI.WebControls.WebParts.ConnectionPoint::get_ID()
0x105d6e  stelem.ref
0x105d6f  dup
0x105d70  ldc.i4.1
0x105d71  ldarg.1
0x105d72  callvirt instance string System.Web.UI.Control::get_ID()
0x105d77  stelem.ref
0x105d78  call     string System.Web.SR::GetString(string name, object[] args)
0x105d7d  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x105d82  throw
0x105d83  ldc.i4.0
0x105d84  stloc.s  4
0x105d86  leave    loc_106013
0x105d8b  ldloc.2
0x105d8c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x105d91  brtrue.s loc_105D39
0x105d93  leave.s  loc_105DA9
0x105d95  ldloc.2
0x105d96  isinst   [mscorlib]System.IDisposable
0x105d9b  stloc.s  5
0x105d9d  ldloc.s  5
0x105d9f  brfalse.s loc_105DA8
0x105da1  ldloc.s  5
0x105da3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x105da8  endfinally
0x105da9  ldarg.s  4
0x105dab  callvirt instance bool System.Web.UI.WebControls.WebParts.ConnectionPoint::get_AllowsMultipleConnections()
0x105db0  brtrue   loc_105E3C
0x105db5  ldarg.0
0x105db6  call     instance class System.Web.UI.WebControls.WebParts.WebPartConnectionCollection System.Web.UI.WebControls.WebParts.WebPartManager::get_Connections()
0x105dbb  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x105dc0  stloc.s  6
0x105dc2  br.s     loc_105E1C
0x105dc4  ldloc.s  6
0x105dc6  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x105dcb  castclass System.Web.UI.WebControls.WebParts.WebPartConnection
0x105dd0  stloc.s  7
0x105dd2  ldloc.s  7
0x105dd4  callvirt instance class System.Web.UI.WebControls.WebParts.WebPart System.Web.UI.WebControls.WebParts.WebPartConnection::get_Consumer()
0x105dd9  ldarg.3
0x105dda  bne.un.s loc_105E1C
0x105ddc  ldloc.s  7
0x105dde  callvirt instance class System.Web.UI.WebControls.WebParts.ConsumerConnectionPoint System.Web.UI.WebControls.WebParts.WebPartConnection::get_ConsumerConnectionPoint()
0x105de3  ldarg.s  4
0x105de5  bne.un.s loc_105E1C
0x105de7  ldarg.s  6
0x105de9  brfalse.s loc_105E14
0x105deb  ldstr    aWebpartconnect_24// "WebPartConnection_Duplicate"
0x105df0  ldc.i4.2
0x105df1  newarr   [mscorlib]System.Object
0x105df6  dup
0x105df7  ldc.i4.0
0x105df8  ldarg.s  4
0x105dfa  callvirt instance string System.Web.UI.WebControls.WebParts.ConnectionPoint::get_ID()
0x105dff  stelem.ref
0x105e00  dup
0x105e01  ldc.i4.1
0x105e02  ldarg.3
0x105e03  callvirt instance string System.Web.UI.Control::get_ID()
0x105e08  stelem.ref
0x105e09  call     string System.Web.SR::GetString(string name, object[] args)
0x105e0e  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x105e13  throw
0x105e14  ldc.i4.0
0x105e15  stloc.s  4
0x105e17  leave    loc_106013
0x105e1c  ldloc.s  6
0x105e1e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x105e23  brtrue.s loc_105DC4
0x105e25  leave.s  loc_105E3C
0x105e27  ldloc.s  6
0x105e29  isinst   [mscorlib]System.IDisposable
0x105e2e  stloc.s  5
0x105e30  ldloc.s  5
0x105e32  brfalse.s loc_105E3B
0x105e34  ldloc.s  5
0x105e36  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x105e3b  endfinally
0x105e3c  ldarg.s  5
0x105e3e  brtrue   loc_105EF9
0x105e43  ldarg.2
0x105e44  callvirt instance class [mscorlib]System.Type System.Web.UI.WebControls.WebParts.ConnectionPoint::get_InterfaceType()
0x105e49  ldarg.s  4
0x105e4b  callvirt instance class [mscorlib]System.Type System.Web.UI.WebControls.WebParts.ConnectionPoint::get_InterfaceType()
0x105e50  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x105e55  brfalse.s loc_105E9C
0x105e57  ldarg.s  6
0x105e59  brfalse.s loc_105E9A
0x105e5b  ldstr    aWebpartconnect_4// "WebPartConnection_NoCommonInterface"
0x105e60  ldc.i4.4
0x105e61  newarr   [mscorlib]System.String
0x105e66  dup
0x105e67  ldc.i4.0
0x105e68  ldarg.2
0x105e69  callvirt instance string System.Web.UI.WebControls.WebParts.ConnectionPoint::get_DisplayName()
0x105e6e  stelem.ref
  ... truncated ...
```
