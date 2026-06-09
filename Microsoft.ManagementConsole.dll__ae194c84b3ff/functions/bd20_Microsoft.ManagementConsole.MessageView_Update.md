# Microsoft.ManagementConsole.MessageView::Update

- ea: `0xbd20`
- end: `0xbdec`
- name: `Microsoft.ManagementConsole.MessageView::Update`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x9d70`
- `0xb2d0`
- `0xbd20`
- `0xbdf0`

## string_xrefs

- `0xbd21`: `Update`

## pseudocode

```c

```

## disassembly

```asm
0xbd20  ldarg.0
0xbd21  ldstr    aUpdate// "Update"
0xbd26  call     instance void Microsoft.ManagementConsole.View::ThrowIfShutdown(string viewOperation)
0xbd2b  ldarg.0
0xbd2c  call     instance bool Microsoft.ManagementConsole.View::get_Initialized()
0xbd31  brtrue.s loc_BD82
0xbd33  ldarg.0
0xbd34  dup
0xbd35  ldfld    valuetype PreInitializedFields Microsoft.ManagementConsole.MessageView::_preInitializedFields
0xbd3a  ldc.i4.1
0xbd3b  or
0xbd3c  stfld    valuetype PreInitializedFields Microsoft.ManagementConsole.MessageView::_preInitializedFields
0xbd41  ldarg.0
0xbd42  dup
0xbd43  ldfld    valuetype PreInitializedFields Microsoft.ManagementConsole.MessageView::_preInitializedFields
0xbd48  ldc.i4.2
0xbd49  or
0xbd4a  stfld    valuetype PreInitializedFields Microsoft.ManagementConsole.MessageView::_preInitializedFields
0xbd4f  ldarg.0
0xbd50  dup
0xbd51  ldfld    valuetype PreInitializedFields Microsoft.ManagementConsole.MessageView::_preInitializedFields
0xbd56  ldc.i4.4
0xbd57  or
0xbd58  stfld    valuetype PreInitializedFields Microsoft.ManagementConsole.MessageView::_preInitializedFields
0xbd5d  ldarg.0
0xbd5e  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.MessageViewDescriptionData Microsoft.ManagementConsole.MessageView::_data
0xbd63  ldarg.1
0xbd64  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.MessageViewDescriptionData::set_Title(string)
0xbd69  ldarg.0
0xbd6a  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.MessageViewDescriptionData Microsoft.ManagementConsole.MessageView::_data
0xbd6f  ldarg.2
0xbd70  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.MessageViewDescriptionData::set_BodyText(string)
0xbd75  ldarg.0
0xbd76  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.MessageViewDescriptionData Microsoft.ManagementConsole.MessageView::_data
0xbd7b  ldarg.3
0xbd7c  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.MessageViewDescriptionData::set_IconId(valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.MessageViewIcon)
0xbd81  ret
0xbd82  ldc.i4.0
0xbd83  stloc.0
0xbd84  ldarg.0
0xbd85  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.MessageViewDescriptionData Microsoft.ManagementConsole.MessageView::_data
0xbd8a  callvirt instance string [MMCFxCommon]Microsoft.ManagementConsole.Internal.MessageViewDescriptionData::get_Title()
0xbd8f  ldarg.1
0xbd90  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xbd95  brfalse.s loc_BDA5
0xbd97  ldarg.0
0xbd98  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.MessageViewDescriptionData Microsoft.ManagementConsole.MessageView::_data
0xbd9d  ldarg.1
0xbd9e  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.MessageViewDescriptionData::set_Title(string)
0xbda3  ldc.i4.1
0xbda4  stloc.0
0xbda5  ldarg.0
0xbda6  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.MessageViewDescriptionData Microsoft.ManagementConsole.MessageView::_data
0xbdab  callvirt instance string [MMCFxCommon]Microsoft.ManagementConsole.Internal.MessageViewDescriptionData::get_BodyText()
0xbdb0  ldarg.2
0xbdb1  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xbdb6  brfalse.s loc_BDC6
0xbdb8  ldarg.0
0xbdb9  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.MessageViewDescriptionData Microsoft.ManagementConsole.MessageView::_data
0xbdbe  ldarg.2
0xbdbf  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.MessageViewDescriptionData::set_BodyText(string)
0xbdc4  ldc.i4.1
0xbdc5  stloc.0
0xbdc6  ldarg.0
0xbdc7  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.MessageViewDescriptionData Microsoft.ManagementConsole.MessageView::_data
0xbdcc  callvirt instance valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.MessageViewIcon [MMCFxCommon]Microsoft.ManagementConsole.Internal.MessageViewDescriptionData::get_IconId()
0xbdd1  ldarg.3
0xbdd2  beq.s    loc_BDE2
0xbdd4  ldarg.0
0xbdd5  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.MessageViewDescriptionData Microsoft.ManagementConsole.MessageView::_data
0xbdda  ldarg.3
0xbddb  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.MessageViewDescriptionData::set_IconId(valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.MessageViewIcon)
0xbde0  ldc.i4.1
0xbde1  stloc.0
0xbde2  ldloc.0
0xbde3  brfalse.s loc_BDEB
0xbde5  ldarg.0
0xbde6  call     instance void Microsoft.ManagementConsole.MessageView::Synchronize()
0xbdeb  ret
```
