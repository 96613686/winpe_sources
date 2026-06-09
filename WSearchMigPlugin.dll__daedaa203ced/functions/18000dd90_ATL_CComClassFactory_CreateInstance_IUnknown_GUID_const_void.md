# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000dd90`
- end: `0x18000ddf2`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(unsigned int (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000dd90`
- `0x180018010`

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
0x18000dd90  sub     rsp, 28h
0x18000dd94  mov     r11, rcx
0x18000dd97  mov     rax, r8
0x18000dd9a  xor     ecx, ecx
0x18000dd9c  mov     r10, rdx
0x18000dd9f  mov     r8d, 80004003h
0x18000dda5  test    r9, r9
0x18000dda8  jz      short loc_18000DDEA
0x18000ddaa  mov     [r9], rcx
0x18000ddad  test    rdx, rdx
0x18000ddb0  jz      short loc_18000DDD5
0x18000ddb2  cmp     [rax], ecx
0x18000ddb4  jnz     short loc_18000DDCD
0x18000ddb6  cmp     [rax+4], ecx
0x18000ddb9  jnz     short loc_18000DDCD
0x18000ddbb  cmp     dword ptr [rax+8], 0C0h
0x18000ddc2  jnz     short loc_18000DDCD
0x18000ddc4  cmp     dword ptr [rax+0Ch], 46000000h
0x18000ddcb  jz      short loc_18000DDD5
0x18000ddcd  mov     r8d, 80040110h
0x18000ddd3  jmp     short loc_18000DDEA
0x18000ddd5  mov     rdx, rax
0x18000ddd8  mov     r8, r9
0x18000dddb  mov     rax, [r11+40h]
0x18000dddf  mov     rcx, r10
0x18000dde2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dde7  mov     r8d, eax
0x18000ddea  mov     eax, r8d
0x18000dded  add     rsp, 28h
0x18000ddf1  retn
```
