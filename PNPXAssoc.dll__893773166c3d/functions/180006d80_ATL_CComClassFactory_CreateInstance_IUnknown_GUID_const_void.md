# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180006d80`
- end: `0x180006de2`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006d80`
- `0x180014010`

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
0x180006d80  sub     rsp, 28h
0x180006d84  mov     r11, rcx
0x180006d87  mov     rax, r8
0x180006d8a  xor     ecx, ecx
0x180006d8c  mov     r10, rdx
0x180006d8f  mov     r8d, 80004003h
0x180006d95  test    r9, r9
0x180006d98  jz      short loc_180006DDA
0x180006d9a  mov     [r9], rcx
0x180006d9d  test    rdx, rdx
0x180006da0  jz      short loc_180006DC5
0x180006da2  cmp     [rax], ecx
0x180006da4  jnz     short loc_180006DBD
0x180006da6  cmp     [rax+4], ecx
0x180006da9  jnz     short loc_180006DBD
0x180006dab  cmp     dword ptr [rax+8], 0C0h
0x180006db2  jnz     short loc_180006DBD
0x180006db4  cmp     dword ptr [rax+0Ch], 46000000h
0x180006dbb  jz      short loc_180006DC5
0x180006dbd  mov     r8d, 80040110h
0x180006dc3  jmp     short loc_180006DDA
0x180006dc5  mov     rdx, rax
0x180006dc8  mov     r8, r9
0x180006dcb  mov     rax, [r11+40h]
0x180006dcf  mov     rcx, r10
0x180006dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dd7  mov     r8d, eax
0x180006dda  mov     eax, r8d
0x180006ddd  add     rsp, 28h
0x180006de1  retn
```
