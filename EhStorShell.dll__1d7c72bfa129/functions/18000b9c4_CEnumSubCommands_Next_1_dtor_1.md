# _CEnumSubCommands::Next_::_1_::dtor$1

- ea: `0x18000b9c4`
- end: `0x18000b9d0`
- name: `_CEnumSubCommands::Next_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005b60`

## pseudocode

```c
void __fastcall CEnumSubCommands::Next_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)(a2 + 56));
}

```

## disassembly

```asm
0x18000b9c4  lea     rcx, [rdx+38h]
0x18000b9cb  jmp     ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
```
