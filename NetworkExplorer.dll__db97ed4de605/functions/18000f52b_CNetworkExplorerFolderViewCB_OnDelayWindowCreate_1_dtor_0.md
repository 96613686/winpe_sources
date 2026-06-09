# _CNetworkExplorerFolderViewCB::_OnDelayWindowCreate_::_1_::dtor$0

- ea: `0x18000f52b`
- end: `0x18000f537`
- name: `_CNetworkExplorerFolderViewCB::_OnDelayWindowCreate_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008d50`

## pseudocode

```c
void __fastcall CNetworkExplorerFolderViewCB::_OnDelayWindowCreate_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  NetworkLegacyUxTelemetry::NetworkExplorerOpen::~NetworkExplorerOpen((NetworkLegacyUxTelemetry::NetworkExplorerOpen *)(a2 + 32));
}

```

## disassembly

```asm
0x18000f52b  lea     rcx, [rdx+20h]; this
0x18000f532  jmp     ??1NetworkExplorerOpen@NetworkLegacyUxTelemetry@@QEAA@XZ; NetworkLegacyUxTelemetry::NetworkExplorerOpen::~NetworkExplorerOpen(void)
```
