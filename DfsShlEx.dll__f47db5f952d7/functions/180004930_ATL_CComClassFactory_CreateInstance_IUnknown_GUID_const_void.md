# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180004930`
- end: `0x180004992`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004930`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactory::CreateInstance(
        unsigned int (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **),
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v5; // r8d

  v5 = -2147467261;
  if ( a4 )
  {
    *a4 = 0;
    if ( a2
      && (a3->Data1 || *(_DWORD *)&a3->Data2 || *(_DWORD *)a3->Data4 != 192 || *(_DWORD *)&a3->Data4[4] != 1174405120) )
    {
      return (unsigned int)-2147221232;
    }
    else
    {
      return this[8](a2, a3, a4);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180004930  sub     rsp, 28h
0x180004934  mov     r11, rcx
0x180004937  mov     rax, r8
0x18000493a  xor     ecx, ecx
0x18000493c  mov     r10, rdx
0x18000493f  mov     r8d, 80004003h
0x180004945  test    r9, r9
0x180004948  jz      short loc_18000498A
0x18000494a  mov     [r9], rcx
0x18000494d  test    rdx, rdx
0x180004950  jz      short loc_180004975
0x180004952  cmp     [rax], ecx
0x180004954  jnz     short loc_18000496D
0x180004956  cmp     [rax+4], ecx
0x180004959  jnz     short loc_18000496D
0x18000495b  cmp     dword ptr [rax+8], 0C0h
0x180004962  jnz     short loc_18000496D
0x180004964  cmp     dword ptr [rax+0Ch], 46000000h
0x18000496b  jz      short loc_180004975
0x18000496d  mov     r8d, 80040110h
0x180004973  jmp     short loc_18000498A
0x180004975  mov     rdx, rax
0x180004978  mov     r8, r9
0x18000497b  mov     rax, [r11+40h]
0x18000497f  mov     rcx, r10
0x180004982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004987  mov     r8d, eax
0x18000498a  mov     eax, r8d
0x18000498d  add     rsp, 28h
0x180004991  retn
```
