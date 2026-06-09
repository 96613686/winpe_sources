# _CILogStorage::OpenLogStreamByClassID_::_1_::dtor$0

- ea: `0x1800130c6`
- end: `0x1800130d2`
- name: `_CILogStorage::OpenLogStreamByClassID_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, authz_impersonation`

## callees

- `0x180001300`

## pseudocode

```c
void __fastcall CILogStorage::OpenLogStreamByClassID_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 120));
}

```

## disassembly

```asm
0x1800130c6  mov     rcx, [rdx+78h]; Block
0x1800130cd  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
