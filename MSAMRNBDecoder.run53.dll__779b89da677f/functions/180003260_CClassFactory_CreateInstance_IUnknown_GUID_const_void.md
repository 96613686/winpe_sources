# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003260`
- end: `0x18000327d`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `29`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003260`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance(
        __int64 (__fastcall **this)(const struct _GUID *, void **),
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  if ( a2 )
    return 2147746064LL;
  else
    return this[2](a3, a4);
}

```

## disassembly

```asm
0x180003260  mov     rax, rcx
0x180003263  test    rdx, rdx
0x180003266  jz      short loc_18000326E
0x180003268  mov     eax, 80040110h
0x18000326d  retn
0x18000326e  mov     rax, [rax+10h]
0x180003272  mov     rdx, r9
0x180003275  mov     rcx, r8
0x180003278  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
