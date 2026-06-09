# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800035c0`
- end: `0x180003617`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `87`
- prototype: `__int64 __fastcall(__int64 (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003310`
- `0x1800035c0`
- `0x18000c010`

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
0x1800035c0  push    rbx
0x1800035c2  sub     rsp, 20h
0x1800035c6  mov     r11, r8
0x1800035c9  mov     r10, rdx
0x1800035cc  mov     rbx, rcx
0x1800035cf  test    r9, r9
0x1800035d2  jz      short loc_1800035FD
0x1800035d4  mov     qword ptr [r9], 0
0x1800035db  test    rdx, rdx
0x1800035de  jnz     short loc_180003604
0x1800035e0  mov     rax, [rbx+40h]
0x1800035e4  mov     r8, r9
0x1800035e7  mov     rdx, r11
0x1800035ea  mov     rcx, r10
0x1800035ed  add     rsp, 20h
0x1800035f1  pop     rbx
0x1800035f2  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800035f7  add     rsp, 20h
0x1800035fb  pop     rbx
0x1800035fc  retn
0x1800035fd  mov     eax, 80004003h
0x180003602  jmp     short loc_1800035F7
0x180003604  mov     rcx, r11; struct _GUID *
0x180003607  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x18000360c  test    eax, eax
0x18000360e  jnz     short loc_1800035E0
0x180003610  mov     eax, 80040110h
0x180003615  jmp     short loc_1800035F7
```
