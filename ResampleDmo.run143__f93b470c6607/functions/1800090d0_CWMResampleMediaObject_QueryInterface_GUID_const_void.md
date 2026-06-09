# CWMResampleMediaObject::QueryInterface(_GUID const &,void * *)

- ea: `0x1800090d0`
- end: `0x1800090df`
- name: `?QueryInterface@CWMResampleMediaObject@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `15`
- prototype: `__int64 __fastcall(CWMResampleMediaObject *__hidden this, const struct _GUID *, void **)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18006b6f0`
- `0x18006b700`
- `0x18006b720`
- `0x18006b740`
- `0x18006b760`
- `0x180081a40`
- `0x180081a60`
- `0x180081a80`
- `0x180081aa0`

## callees

- `0x180085010`

## pseudocode

```c
__int64 __fastcall CWMResampleMediaObject::QueryInterface(
        CWMResampleMediaObject *this,
        const struct _GUID *a2,
        void **a3)
{
  return (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this - 2))(
           *((_QWORD *)this - 2),
           a2,
           a3);
}

```

## disassembly

```asm
0x1800090d0  mov     rcx, [rcx-10h]
0x1800090d4  mov     rax, [rcx]
0x1800090d7  mov     rax, [rax]
0x1800090da  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
