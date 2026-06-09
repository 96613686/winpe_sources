# _CheckAccessAllowed_::_1_::dtor$0

- ea: `0x18000fa9c`
- end: `0x18000faa8`
- name: `_CheckAccessAllowed_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800038dc`

## pseudocode

```c
void __fastcall CheckAccessAllowed_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CAutoLocalFreePtr::~CAutoLocalFreePtr((CAutoLocalFreePtr *)(a2 + 96));
}

```

## disassembly

```asm
0x18000fa9c  lea     rcx, [rdx+60h]; this
0x18000faa3  jmp     ??1CAutoLocalFreePtr@@QEAA@XZ; CAutoLocalFreePtr::~CAutoLocalFreePtr(void)
```
