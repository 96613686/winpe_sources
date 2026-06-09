# _CILogWrite::SetCheckpoint_::_1_::dtor$0

- ea: `0x180013194`
- end: `0x1800131a0`
- name: `_CILogWrite::SetCheckpoint_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000428c`

## pseudocode

```c
void __fastcall CILogWrite::SetCheckpoint_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CLock::~CLock((CLock *)(a2 + 88));
}

```

## disassembly

```asm
0x180013194  lea     rcx, [rdx+58h]; this
0x18001319b  jmp     ??1CLock@@QEAA@XZ; CLock::~CLock(void)
```
