# CWMVideoDecMediaObject::QueryInterface(_GUID const &,void * *)

- ea: `0x180007660`
- end: `0x180007672`
- name: `?QueryInterface@CWMVideoDecMediaObject@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: `__int64 __fastcall(CWMVideoDecMediaObject *__hidden this, const struct _GUID *, void **)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180007680`
- `0x1800076a0`
- `0x1800076c0`
- `0x1800076e0`
- `0x180007700`

## callees

- `0x180022010`

## pseudocode

```c
__int64 __fastcall CWMVideoDecMediaObject::QueryInterface(
        CWMVideoDecMediaObject *this,
        const struct _GUID *a2,
        void **a3)
{
  return (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 42))(
           *((_QWORD *)this + 42),
           a2,
           a3);
}

```

## disassembly

```asm
0x180007660  mov     rcx, [rcx+150h]
0x180007667  mov     rax, [rcx]
0x18000766a  mov     rax, [rax]
0x18000766d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
