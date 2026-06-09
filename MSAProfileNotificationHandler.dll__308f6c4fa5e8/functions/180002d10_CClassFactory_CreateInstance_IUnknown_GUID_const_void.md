# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002d10`
- end: `0x180002d49`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `57`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002d10`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance(
        CClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 (__fastcall *v5)(const struct _GUID *, void **); // rax

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  v5 = (__int64 (__fastcall *)(const struct _GUID *, void **))*((_QWORD *)this + 2);
  if ( v5 )
    return v5(a3, a4);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x180002d10  test    r9, r9
0x180002d13  jnz     short loc_180002D1C
0x180002d15  mov     eax, 80004003h
0x180002d1a  jmp     short locret_180002D48
0x180002d1c  mov     qword ptr [r9], 0
0x180002d23  test    rdx, rdx
0x180002d26  jz      short loc_180002D2F
0x180002d28  mov     eax, 80040110h
0x180002d2d  jmp     short locret_180002D48
0x180002d2f  mov     rax, [rcx+10h]
0x180002d33  test    rax, rax
0x180002d36  jz      short loc_180002D43
0x180002d38  mov     rdx, r9
0x180002d3b  mov     rcx, r8
0x180002d3e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002d43  mov     eax, 80004005h
0x180002d48  retn
```
