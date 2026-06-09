# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000a810`
- end: `0x18000a864`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `84`
- prototype: `int(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000a810`
- `0x18000c7d0`
- `0x180015010`

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
0x18000a810  push    rbx
0x18000a812  sub     rsp, 20h
0x18000a816  mov     r11, r8
0x18000a819  mov     r10, rdx
0x18000a81c  mov     rbx, rcx
0x18000a81f  mov     eax, 80004003h
0x18000a824  test    r9, r9
0x18000a827  jz      short loc_18000A85E
0x18000a829  mov     qword ptr [r9], 0
0x18000a830  test    rdx, rdx
0x18000a833  jz      short loc_18000A84C
0x18000a835  mov     rcx, r8; struct _GUID *
0x18000a838  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x18000a83d  test    eax, eax
0x18000a83f  jnz     short loc_18000A84C
0x18000a841  mov     eax, 80040110h
0x18000a846  add     rsp, 20h
0x18000a84a  pop     rbx
0x18000a84b  retn
0x18000a84c  mov     rax, [rbx+40h]
0x18000a850  mov     r8, r9
0x18000a853  mov     rdx, r11
0x18000a856  mov     rcx, r10
0x18000a859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a85e  add     rsp, 20h
0x18000a862  pop     rbx
0x18000a863  retn
```
