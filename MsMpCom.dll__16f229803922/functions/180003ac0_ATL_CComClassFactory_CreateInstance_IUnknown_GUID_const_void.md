# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003ac0`
- end: `0x180003b22`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003ac0`
- `0x18000a010`

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
0x180003ac0  sub     rsp, 28h
0x180003ac4  mov     r11, rcx
0x180003ac7  mov     rax, r8
0x180003aca  xor     ecx, ecx
0x180003acc  mov     r10, rdx
0x180003acf  mov     r8d, 80004003h
0x180003ad5  test    r9, r9
0x180003ad8  jz      short loc_180003B1A
0x180003ada  mov     [r9], rcx
0x180003add  test    rdx, rdx
0x180003ae0  jz      short loc_180003B05
0x180003ae2  cmp     [rax], ecx
0x180003ae4  jnz     short loc_180003AFD
0x180003ae6  cmp     [rax+4], ecx
0x180003ae9  jnz     short loc_180003AFD
0x180003aeb  cmp     dword ptr [rax+8], 0C0h
0x180003af2  jnz     short loc_180003AFD
0x180003af4  cmp     dword ptr [rax+0Ch], 46000000h
0x180003afb  jz      short loc_180003B05
0x180003afd  mov     r8d, 80040110h
0x180003b03  jmp     short loc_180003B1A
0x180003b05  mov     rdx, rax
0x180003b08  mov     r8, r9
0x180003b0b  mov     rax, [r11+40h]
0x180003b0f  mov     rcx, r10
0x180003b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b17  mov     r8d, eax
0x180003b1a  mov     eax, r8d
0x180003b1d  add     rsp, 28h
0x180003b21  retn
```
