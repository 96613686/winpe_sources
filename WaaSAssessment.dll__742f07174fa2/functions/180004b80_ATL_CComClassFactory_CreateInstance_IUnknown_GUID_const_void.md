# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180004b80`
- end: `0x180004be2`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004b80`
- `0x18001b010`

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
0x180004b80  sub     rsp, 28h
0x180004b84  mov     r11, rcx
0x180004b87  mov     rax, r8
0x180004b8a  xor     ecx, ecx
0x180004b8c  mov     r10, rdx
0x180004b8f  mov     r8d, 80004003h
0x180004b95  test    r9, r9
0x180004b98  jz      short loc_180004BDA
0x180004b9a  mov     [r9], rcx
0x180004b9d  test    rdx, rdx
0x180004ba0  jz      short loc_180004BC5
0x180004ba2  cmp     [rax], ecx
0x180004ba4  jnz     short loc_180004BBD
0x180004ba6  cmp     [rax+4], ecx
0x180004ba9  jnz     short loc_180004BBD
0x180004bab  cmp     dword ptr [rax+8], 0C0h
0x180004bb2  jnz     short loc_180004BBD
0x180004bb4  cmp     dword ptr [rax+0Ch], 46000000h
0x180004bbb  jz      short loc_180004BC5
0x180004bbd  mov     r8d, 80040110h
0x180004bc3  jmp     short loc_180004BDA
0x180004bc5  mov     rdx, rax
0x180004bc8  mov     r8, r9
0x180004bcb  mov     rax, [r11+40h]
0x180004bcf  mov     rcx, r10
0x180004bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bd7  mov     r8d, eax
0x180004bda  mov     eax, r8d
0x180004bdd  add     rsp, 28h
0x180004be1  retn
```
