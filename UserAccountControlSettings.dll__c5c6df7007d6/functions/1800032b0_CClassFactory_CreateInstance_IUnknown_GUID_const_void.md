# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800032b0`
- end: `0x1800032d4`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `36`
- prototype: `__int64 __fastcall(__int64 (__fastcall **this)(const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800032b0`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance(
        __int64 (__fastcall **this)(const struct _GUID *, void **),
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  else
    return this[2](a3, a4);
}

```

## disassembly

```asm
0x1800032b0  mov     qword ptr [r9], 0
0x1800032b7  mov     rax, rcx
0x1800032ba  test    rdx, rdx
0x1800032bd  jz      short loc_1800032C5
0x1800032bf  mov     eax, 80040110h
0x1800032c4  retn
0x1800032c5  mov     rax, [rax+10h]
0x1800032c9  mov     rdx, r9
0x1800032cc  mov     rcx, r8
0x1800032cf  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
