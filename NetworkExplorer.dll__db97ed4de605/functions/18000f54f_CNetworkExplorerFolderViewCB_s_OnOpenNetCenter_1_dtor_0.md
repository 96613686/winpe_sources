# _CNetworkExplorerFolderViewCB::s_OnOpenNetCenter_::_1_::dtor$0

- ea: `0x18000f54f`
- end: `0x18000f55b`
- name: `_CNetworkExplorerFolderViewCB::s_OnOpenNetCenter_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008a74`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolderViewCB::s_OnOpenNetCenter_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IOpenControlPanel>::~ComPtr<IOpenControlPanel>((__int64 *)(a2 + 88));
}

```

## disassembly

```asm
0x18000f54f  lea     rcx, [rdx+58h]
0x18000f556  jmp     ??1?$ComPtr@UIOpenControlPanel@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IOpenControlPanel>::~ComPtr<IOpenControlPanel>(void)
```
