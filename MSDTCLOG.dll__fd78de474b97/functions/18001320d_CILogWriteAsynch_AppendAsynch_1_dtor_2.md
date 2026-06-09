# _CILogWriteAsynch::AppendAsynch_::_1_::dtor$2

- ea: `0x18001320d`
- end: `0x180013219`
- name: `_CILogWriteAsynch::AppendAsynch_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000428c`

## pseudocode

```c
void __fastcall CILogWriteAsynch::AppendAsynch_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  CLock::~CLock((CLock *)(a2 + 80));
}

```

## disassembly

```asm
0x18001320d  lea     rcx, [rdx+50h]; this
0x180013214  jmp     ??1CLock@@QEAA@XZ; CLock::~CLock(void)
```
