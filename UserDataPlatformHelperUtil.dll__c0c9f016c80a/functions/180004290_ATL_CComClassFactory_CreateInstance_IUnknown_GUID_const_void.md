# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180004290`
- end: `0x1800042f2`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(unsigned int (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004290`
- `0x18000b010`

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
0x180004290  sub     rsp, 28h
0x180004294  mov     r11, rcx
0x180004297  mov     rax, r8
0x18000429a  xor     ecx, ecx
0x18000429c  mov     r10, rdx
0x18000429f  mov     r8d, 80004003h
0x1800042a5  test    r9, r9
0x1800042a8  jz      short loc_1800042EA
0x1800042aa  mov     [r9], rcx
0x1800042ad  test    rdx, rdx
0x1800042b0  jz      short loc_1800042D5
0x1800042b2  cmp     [rax], ecx
0x1800042b4  jnz     short loc_1800042CD
0x1800042b6  cmp     [rax+4], ecx
0x1800042b9  jnz     short loc_1800042CD
0x1800042bb  cmp     dword ptr [rax+8], 0C0h
0x1800042c2  jnz     short loc_1800042CD
0x1800042c4  cmp     dword ptr [rax+0Ch], 46000000h
0x1800042cb  jz      short loc_1800042D5
0x1800042cd  mov     r8d, 80040110h
0x1800042d3  jmp     short loc_1800042EA
0x1800042d5  mov     rdx, rax
0x1800042d8  mov     r8, r9
0x1800042db  mov     rax, [r11+40h]
0x1800042df  mov     rcx, r10
0x1800042e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042e7  mov     r8d, eax
0x1800042ea  mov     eax, r8d
0x1800042ed  add     rsp, 28h
0x1800042f1  retn
```
