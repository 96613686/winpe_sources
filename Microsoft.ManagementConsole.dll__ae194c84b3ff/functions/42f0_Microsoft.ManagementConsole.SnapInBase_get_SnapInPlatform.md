# Microsoft.ManagementConsole.SnapInBase::get_SnapInPlatform

- ea: `0x42f0`
- end: `0x4306`
- name: `Microsoft.ManagementConsole.SnapInBase::get_SnapInPlatform`
- size: `22`
- prototype: ``
- caller_count: `48`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1c80`
- `0x44c0`
- `0x4680`
- `0x48d0`
- `0x4900`
- `0x4b20`
- `0x66d0`
- `0x74e0`
- `0x8c20`
- `0x8c50`
- `0xa000`
- `0xa050`
- `0xa0c0`
- `0xa390`
- `0xa3e0`
- `0xa430`
- `0xa7e0`
- `0xa830`
- `0xa880`
- `0xa8d0`
- `0xa970`
- `0xa9f0`
- `0xaed0`
- `0xafc0`
- `0xb020`
- `0xb190`
- `0xb220`
- `0xb720`
- `0xb780`
- `0xb840`
- `0xb8a0`
- `0xb8f0`
- `0xb930`
- `0xbdf0`
- `0xc1f0`
- `0xc280`
- `0xc4b0`
- `0xc590`
- `0xc690`
- `0xca50`
- `0xcab0`
- `0xd3c0`
- `0xe4a0`
- `0xe4d0`
- `0xe630`
- `0xe7e0`
- `0xe840`
- `0xe880`

## callees

- `0x42f0`
- `0x7ec0`

## pseudocode

```c

```

## disassembly

```asm
0x42f0  ldarg.0
0x42f1  ldfld    class Microsoft.ManagementConsole.Internal.SnapInClient Microsoft.ManagementConsole.SnapInBase::_snapInClient
0x42f6  brtrue.s loc_42FA
0x42f8  ldnull
0x42f9  ret
0x42fa  ldarg.0
0x42fb  ldfld    class Microsoft.ManagementConsole.Internal.SnapInClient Microsoft.ManagementConsole.SnapInBase::_snapInClient
0x4300  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform Microsoft.ManagementConsole.Internal.SnapInClient::get_SnapInPlatform()
0x4305  ret
```
