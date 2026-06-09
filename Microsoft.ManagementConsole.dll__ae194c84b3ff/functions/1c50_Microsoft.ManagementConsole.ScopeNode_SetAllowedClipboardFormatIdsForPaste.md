# Microsoft.ManagementConsole.ScopeNode::SetAllowedClipboardFormatIdsForPaste

- ea: `0x1c50`
- end: `0x1c68`
- name: `Microsoft.ManagementConsole.ScopeNode::SetAllowedClipboardFormatIdsForPaste`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x6f0`

## pseudocode

```c

```

## disassembly

```asm
0x1c50  ldarg.0
0x1c51  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.ScopeNode::_data
0x1c56  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.PasteTargetInfo [MMCFxCommon]Microsoft.ManagementConsole.Internal.ScopeNodeData::get_PasteTargetInfo()
0x1c5b  ldarg.1
0x1c5c  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.PasteTargetInfo::SetAllowedClipboardFormats(string[])
0x1c61  ldarg.0
0x1c62  call     instance void Microsoft.ManagementConsole.Node::Notify()
0x1c67  ret
```
