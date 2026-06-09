# _CLogMgr::_Write_::_1_::dtor$1

- ea: `0x180013de2`
- end: `0x180013dee`
- name: `_CLogMgr::_Write_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000428c`

## pseudocode

```c
void __fastcall CLogMgr::_Write_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CLock::~CLock((CLock *)(a2 + 136));
}

```

## disassembly

```asm
0x180013de2  lea     rcx, [rdx+88h]; this
0x180013de9  jmp     ??1CLock@@QEAA@XZ; CLock::~CLock(void)
```
