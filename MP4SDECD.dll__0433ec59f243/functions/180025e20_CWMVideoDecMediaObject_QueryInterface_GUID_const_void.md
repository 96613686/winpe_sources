# CWMVideoDecMediaObject::QueryInterface(_GUID const &,void * *)

- ea: `0x180025e20`
- end: `0x180025e32`
- name: `?QueryInterface@CWMVideoDecMediaObject@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: `__int64 __fastcall(CWMVideoDecMediaObject *__hidden this, const struct _GUID *, void **)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x18002d8b0`
- `0x18002d8d0`
- `0x18002d8f0`
- `0x18002d910`
- `0x18002d930`
- `0x18002d950`
- `0x18002d970`
- `0x18002d990`
- `0x18002d9b0`
- `0x18002d9d0`
- `0x18002d9f0`

## callees

- `0x180046010`

## pseudocode

```c
__int64 __fastcall CWMVideoDecMediaObject::QueryInterface(
        CWMVideoDecMediaObject *this,
        const struct _GUID *a2,
        void **a3)
{
  return (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 44))(
           *((_QWORD *)this + 44),
           a2,
           a3);
}

```

## disassembly

```asm
0x180025e20  mov     rcx, [rcx+160h]
0x180025e27  mov     rax, [rcx]
0x180025e2a  mov     rax, [rax]
0x180025e2d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
