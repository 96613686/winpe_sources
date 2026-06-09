# CAccountCleanupFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180005f60`
- end: `0x180005f99`
- name: `?CreateInstance@CAccountCleanupFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `57`
- prototype: `__int64 __fastcall(CAccountCleanupFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005f60`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall CAccountCleanupFactory::CreateInstance(
        CAccountCleanupFactory *this,
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
0x180005f60  test    r9, r9
0x180005f63  jnz     short loc_180005F6C
0x180005f65  mov     eax, 80004003h
0x180005f6a  jmp     short locret_180005F98
0x180005f6c  mov     qword ptr [r9], 0
0x180005f73  test    rdx, rdx
0x180005f76  jz      short loc_180005F7F
0x180005f78  mov     eax, 80040110h
0x180005f7d  jmp     short locret_180005F98
0x180005f7f  mov     rax, [rcx+10h]
0x180005f83  test    rax, rax
0x180005f86  jz      short loc_180005F93
0x180005f88  mov     rdx, r9
0x180005f8b  mov     rcx, r8
0x180005f8e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180005f93  mov     eax, 80004005h
0x180005f98  retn
```
