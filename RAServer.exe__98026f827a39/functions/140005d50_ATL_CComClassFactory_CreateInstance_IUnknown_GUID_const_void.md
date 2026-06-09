# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140005d50`
- end: `0x140005da4`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `84`
- prototype: `__int64 __fastcall(__int64 (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140005d50`
- `0x140007328`
- `0x140017010`

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
  __int64 result; // rax

  v4 = a3;
  v5 = a2;
  result = 2147500035LL;
  if ( a4 )
  {
    *a4 = 0;
    if ( !a2 || (unsigned int)ATL::InlineIsEqualUnknown(a3) )
      return this[8](v5, v4, a4);
    else
      return 2147746064LL;
  }
  return result;
}

```

## disassembly

```asm
0x140005d50  push    rbx
0x140005d52  sub     rsp, 20h
0x140005d56  mov     r11, r8
0x140005d59  mov     r10, rdx
0x140005d5c  mov     rbx, rcx
0x140005d5f  mov     eax, 80004003h
0x140005d64  test    r9, r9
0x140005d67  jz      short loc_140005D9E
0x140005d69  mov     qword ptr [r9], 0
0x140005d70  test    rdx, rdx
0x140005d73  jz      short loc_140005D8C
0x140005d75  mov     rcx, r8; struct _GUID *
0x140005d78  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x140005d7d  test    eax, eax
0x140005d7f  jnz     short loc_140005D8C
0x140005d81  mov     eax, 80040110h
0x140005d86  add     rsp, 20h
0x140005d8a  pop     rbx
0x140005d8b  retn
0x140005d8c  mov     rax, [rbx+40h]
0x140005d90  mov     r8, r9
0x140005d93  mov     rdx, r11
0x140005d96  mov     rcx, r10
0x140005d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005d9e  add     rsp, 20h
0x140005da2  pop     rbx
0x140005da3  retn
```
