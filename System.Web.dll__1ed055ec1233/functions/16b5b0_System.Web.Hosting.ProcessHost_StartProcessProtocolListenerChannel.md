# System.Web.Hosting.ProcessHost::StartProcessProtocolListenerChannel

- ea: `0x16b5b0`
- end: `0x16b697`
- name: `System.Web.Hosting.ProcessHost::StartProcessProtocolListenerChannel`
- size: `231`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x29e30`
- `0x34f20`
- `0x34fa0`
- `0x568c0`
- `0x153920`
- `0x1539d0`
- `0x153bb0`
- `0x16b350`
- `0x16b450`
- `0x16b5b0`
- `0x16c370`

## string_xrefs

- `0x16b5d3`: `Unknown_protocol_id`
- `0x16b5b3`: `protocolId`

## pseudocode

```c

```

## disassembly

```asm
0x16b5b0  ldarg.1
0x16b5b1  brtrue.s loc_16B5BE
0x16b5b3  ldstr    aProtocolid// "protocolId"
0x16b5b8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x16b5bd  throw
0x16b5be  ldarg.0
0x16b5bf  call     instance class System.Web.Configuration.ProtocolsSection System.Web.Hosting.ProcessHost::get_ProtocolsConfig()
0x16b5c4  callvirt instance class System.Web.Configuration.ProtocolCollection System.Web.Configuration.ProtocolsSection::get_Protocols()
0x16b5c9  ldarg.1
0x16b5ca  callvirt instance class System.Web.Configuration.ProtocolElement System.Web.Configuration.ProtocolCollection::get_Item(string name)
0x16b5cf  stloc.0
0x16b5d0  ldloc.0
0x16b5d1  brtrue.s loc_16B5ED
0x16b5d3  ldstr    aUnknownProtoco// "Unknown_protocol_id"
0x16b5d8  ldc.i4.1
0x16b5d9  newarr   [mscorlib]System.Object
0x16b5de  dup
0x16b5df  ldc.i4.0
0x16b5e0  ldarg.1
0x16b5e1  stelem.ref
0x16b5e2  call     string System.Web.SR::GetString(string name, object[] args)
0x16b5e7  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x16b5ec  throw
0x16b5ed  ldnull
0x16b5ee  stloc.1
0x16b5ef  ldnull
0x16b5f0  stloc.2
0x16b5f1  ldarg.0
0x16b5f2  ldloc.0
0x16b5f3  ldloc.0
0x16b5f4  callvirt instance string System.Web.Configuration.ProtocolElement::get_ProcessHandlerType()
0x16b5f9  ldtoken  System.Web.Hosting.ProcessProtocolHandler
0x16b5fe  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16b603  ldstr    aProcesshandler_0// "ProcessHandlerType"
0x16b608  call     instance class [mscorlib]System.Type System.Web.Hosting.ProcessHost::ValidateAndGetType(class System.Web.Configuration.ProtocolElement element, string typeName, class [mscorlib]System.Type assignableType, string elementPropertyName)
0x16b60d  stloc.2
0x16b60e  ldarg.0
0x16b60f  stloc.3
0x16b610  ldc.i4.0
0x16b611  stloc.s  4
0x16b613  ldloc.3
0x16b614  ldloca.s 4
0x16b616  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x16b61b  ldarg.0
0x16b61c  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Hosting.ProcessHost::_protocolHandlers
0x16b621  ldarg.1
0x16b622  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x16b627  isinst   System.Web.Hosting.ProcessProtocolHandler
0x16b62c  stloc.1
0x16b62d  ldloc.1
0x16b62e  brtrue.s loc_16B649
0x16b630  ldloc.2
0x16b631  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x16b636  castclass System.Web.Hosting.ProcessProtocolHandler
0x16b63b  stloc.1
0x16b63c  ldarg.0
0x16b63d  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Hosting.ProcessHost::_protocolHandlers
0x16b642  ldarg.1
0x16b643  ldloc.1
0x16b644  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x16b649  leave.s  loc_16B656
0x16b64b  ldloc.s  4
0x16b64d  brfalse.s loc_16B655
0x16b64f  ldloc.3
0x16b650  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x16b655  endfinally
0x16b656  ldloc.1
0x16b657  brfalse.s loc_16B661
0x16b659  ldloc.1
0x16b65a  ldarg.2
0x16b65b  ldarg.0
0x16b65c  callvirt instance void System.Web.Hosting.ProcessProtocolHandler::StartListenerChannel(class System.Web.Hosting.IListenerChannelCallback listenerChannelCallback, class System.Web.Hosting.IAdphManager AdphManager)
0x16b661  leave.s  loc_16B696
0x16b663  stloc.s  5
0x16b665  newobj   instance void System.Web.ProcessImpersonationContext::.ctor()
0x16b66a  stloc.s  6
0x16b66c  ldloc.s  5
0x16b66e  ldc.i4.1
0x16b66f  newarr   [mscorlib]System.String
0x16b674  dup
0x16b675  ldc.i4.0
0x16b676  ldstr    aInvalidProcess// "Invalid_Process_Prot_Type"
0x16b67b  call     string System.Web.SR::GetString(string name)
0x16b680  stelem.ref
0x16b681  call     void System.Web.Util.Misc::ReportUnhandledException(class [mscorlib]System.Exception e, string[] strings)
0x16b686  leave.s  loc_16B694
0x16b688  ldloc.s  6
0x16b68a  brfalse.s loc_16B693
0x16b68c  ldloc.s  6
0x16b68e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16b693  endfinally
0x16b694  rethrow
0x16b696  ret
```
