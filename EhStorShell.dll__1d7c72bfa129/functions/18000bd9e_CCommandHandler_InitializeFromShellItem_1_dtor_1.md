# _CCommandHandler::InitializeFromShellItem_::_1_::dtor$1

- ea: `0x18000bd9e`
- end: `0x18000bdaa`
- name: `_CCommandHandler::InitializeFromShellItem_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180005b60`

## pseudocode

```c
void __fastcall CCommandHandler::InitializeFromShellItem_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)(a2 + 40));
}

```

## disassembly

```asm
0x18000bd9e  lea     rcx, [rdx+28h]
0x18000bda5  jmp     ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
```
