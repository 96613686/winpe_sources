# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180004e90`
- end: `0x180004ef2`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004e90`
- `0x18000f010`

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
0x180004e90  sub     rsp, 28h
0x180004e94  mov     r11, rcx
0x180004e97  mov     rax, r8
0x180004e9a  xor     ecx, ecx
0x180004e9c  mov     r10, rdx
0x180004e9f  mov     r8d, 80004003h
0x180004ea5  test    r9, r9
0x180004ea8  jz      short loc_180004EEA
0x180004eaa  mov     [r9], rcx
0x180004ead  test    rdx, rdx
0x180004eb0  jz      short loc_180004ED5
0x180004eb2  cmp     [rax], ecx
0x180004eb4  jnz     short loc_180004ECD
0x180004eb6  cmp     [rax+4], ecx
0x180004eb9  jnz     short loc_180004ECD
0x180004ebb  cmp     dword ptr [rax+8], 0C0h
0x180004ec2  jnz     short loc_180004ECD
0x180004ec4  cmp     dword ptr [rax+0Ch], 46000000h
0x180004ecb  jz      short loc_180004ED5
0x180004ecd  mov     r8d, 80040110h
0x180004ed3  jmp     short loc_180004EEA
0x180004ed5  mov     rdx, rax
0x180004ed8  mov     r8, r9
0x180004edb  mov     rax, [r11+40h]
0x180004edf  mov     rcx, r10
0x180004ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ee7  mov     r8d, eax
0x180004eea  mov     eax, r8d
0x180004eed  add     rsp, 28h
0x180004ef1  retn
```
