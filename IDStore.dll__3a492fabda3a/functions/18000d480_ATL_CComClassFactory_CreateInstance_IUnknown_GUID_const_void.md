# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000d480`
- end: `0x18000d4d7`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `87`
- prototype: `__int64 __fastcall(__int64 (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000d450`
- `0x18000d480`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactory::CreateInstance(
        __int64 (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **),
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  const struct _GUID *v4; // r11
  struct IUnknown *v5; // r10

  v4 = a3;
  v5 = a2;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( !a2 || (unsigned int)ATL::InlineIsEqualUnknown(a3) )
    return this[8](v5, v4, a4);
  else
    return 2147746064LL;
}

```

## disassembly

```asm
0x18000d480  push    rbx
0x18000d482  sub     rsp, 20h
0x18000d486  mov     r11, r8
0x18000d489  mov     r10, rdx
0x18000d48c  mov     rbx, rcx
0x18000d48f  test    r9, r9
0x18000d492  jz      short loc_18000D4BD
0x18000d494  mov     qword ptr [r9], 0
0x18000d49b  test    rdx, rdx
0x18000d49e  jnz     short loc_18000D4C4
0x18000d4a0  mov     rax, [rbx+40h]
0x18000d4a4  mov     r8, r9
0x18000d4a7  mov     rdx, r11
0x18000d4aa  mov     rcx, r10
0x18000d4ad  add     rsp, 20h
0x18000d4b1  pop     rbx
0x18000d4b2  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4b7  add     rsp, 20h
0x18000d4bb  pop     rbx
0x18000d4bc  retn
0x18000d4bd  mov     eax, 80004003h
0x18000d4c2  jmp     short loc_18000D4B7
0x18000d4c4  mov     rcx, r11; struct _GUID *
0x18000d4c7  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x18000d4cc  test    eax, eax
0x18000d4ce  jnz     short loc_18000D4A0
0x18000d4d0  mov     eax, 80040110h
0x18000d4d5  jmp     short loc_18000D4B7
```
