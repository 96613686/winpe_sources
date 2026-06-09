# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180005550`
- end: `0x1800055b2`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005550`
- `0x180015010`

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
0x180005550  sub     rsp, 28h
0x180005554  mov     r11, rcx
0x180005557  mov     rax, r8
0x18000555a  xor     ecx, ecx
0x18000555c  mov     r10, rdx
0x18000555f  mov     r8d, 80004003h
0x180005565  test    r9, r9
0x180005568  jz      short loc_1800055AA
0x18000556a  mov     [r9], rcx
0x18000556d  test    rdx, rdx
0x180005570  jz      short loc_180005595
0x180005572  cmp     [rax], ecx
0x180005574  jnz     short loc_18000558D
0x180005576  cmp     [rax+4], ecx
0x180005579  jnz     short loc_18000558D
0x18000557b  cmp     dword ptr [rax+8], 0C0h
0x180005582  jnz     short loc_18000558D
0x180005584  cmp     dword ptr [rax+0Ch], 46000000h
0x18000558b  jz      short loc_180005595
0x18000558d  mov     r8d, 80040110h
0x180005593  jmp     short loc_1800055AA
0x180005595  mov     rdx, rax
0x180005598  mov     r8, r9
0x18000559b  mov     rax, [r11+40h]
0x18000559f  mov     rcx, r10
0x1800055a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055a7  mov     r8d, eax
0x1800055aa  mov     eax, r8d
0x1800055ad  add     rsp, 28h
0x1800055b1  retn
```
