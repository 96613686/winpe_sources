# _ServerFolder::CreateSubFolder_::_1_::dtor$0

- ea: `0x180018b5b`
- end: `0x180018b67`
- name: `_ServerFolder::CreateSubFolder_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180016400`

## pseudocode

```c
__int64 __fastcall ServerFolder::CreateSubFolder_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<DiskFolder>::~ComPtr<DiskFolder>((__int64 *)(a2 + 80));
}

```

## disassembly

```asm
0x180018b5b  lea     rcx, [rdx+50h]
0x180018b62  jmp     ??1?$ComPtr@VDiskFolder@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<DiskFolder>::~ComPtr<DiskFolder>(void)
```
