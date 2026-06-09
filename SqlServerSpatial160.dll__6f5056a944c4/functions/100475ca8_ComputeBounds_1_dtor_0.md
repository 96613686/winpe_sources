# _ComputeBounds_::_1_::dtor$0

- ea: `0x100475ca8`
- end: `0x100475cb4`
- name: `_ComputeBounds_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1004226e0`

## pseudocode

```c
void __fastcall ComputeBounds_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CBoundsModule::~CBoundsModule((CBoundsModule *)(a2 + 80));
}

```

## disassembly

```asm
0x100475ca8  lea     rcx, [rdx+50h]; this
0x100475caf  jmp     ??1CBoundsModule@@UEAA@XZ
```
