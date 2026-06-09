# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140005d20`
- end: `0x140005d82`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(unsigned int (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140005d20`
- `0x140008010`

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
0x140005d20  sub     rsp, 28h
0x140005d24  mov     r11, rcx
0x140005d27  mov     rax, r8
0x140005d2a  xor     ecx, ecx
0x140005d2c  mov     r10, rdx
0x140005d2f  mov     r8d, 80004003h
0x140005d35  test    r9, r9
0x140005d38  jz      short loc_140005D7A
0x140005d3a  mov     [r9], rcx
0x140005d3d  test    rdx, rdx
0x140005d40  jz      short loc_140005D65
0x140005d42  cmp     [rax], ecx
0x140005d44  jnz     short loc_140005D5D
0x140005d46  cmp     [rax+4], ecx
0x140005d49  jnz     short loc_140005D5D
0x140005d4b  cmp     dword ptr [rax+8], 0C0h
0x140005d52  jnz     short loc_140005D5D
0x140005d54  cmp     dword ptr [rax+0Ch], 46000000h
0x140005d5b  jz      short loc_140005D65
0x140005d5d  mov     r8d, 80040110h
0x140005d63  jmp     short loc_140005D7A
0x140005d65  mov     rdx, rax
0x140005d68  mov     r8, r9
0x140005d6b  mov     rax, [r11+40h]
0x140005d6f  mov     rcx, r10
0x140005d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005d77  mov     r8d, eax
0x140005d7a  mov     eax, r8d
0x140005d7d  add     rsp, 28h
0x140005d81  retn
```
