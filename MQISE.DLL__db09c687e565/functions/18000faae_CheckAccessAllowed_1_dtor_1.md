# _CheckAccessAllowed_::_1_::dtor$1

- ea: `0x18000faae`
- end: `0x18000faba`
- name: `_CheckAccessAllowed_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800038fc`

## pseudocode

```c
void __fastcall CheckAccessAllowed_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CHandle::~CHandle((CHandle *)(a2 + 88));
}

```

## disassembly

```asm
0x18000faae  lea     rcx, [rdx+58h]; this
0x18000fab5  jmp     ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
```
