# _CCommandHandler::EnumSubCommands_::_1_::dtor$0

- ea: `0x18000bd68`
- end: `0x18000bd74`
- name: `_CCommandHandler::EnumSubCommands_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180005b60`

## pseudocode

```c
void __fastcall CCommandHandler::EnumSubCommands_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)(a2 + 88));
}

```

## disassembly

```asm
0x18000bd68  lea     rcx, [rdx+58h]
0x18000bd6f  jmp     ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
```
