# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002f00`
- end: `0x180002f63`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002f00`
- `0x18000e4a0`

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
      return this[2](a2, a3, a4);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180002f00  sub     rsp, 28h
0x180002f04  mov     r11, rcx
0x180002f07  mov     rax, r8
0x180002f0a  xor     ecx, ecx
0x180002f0c  mov     r10, rdx
0x180002f0f  mov     r8d, 80004003h
0x180002f15  test    r9, r9
0x180002f18  jz      short loc_180002F5B
0x180002f1a  mov     [r9], rcx
0x180002f1d  test    rdx, rdx
0x180002f20  jz      short loc_180002F45
0x180002f22  cmp     [rax], ecx
0x180002f24  jnz     short loc_180002F3D
0x180002f26  cmp     [rax+4], ecx
0x180002f29  jnz     short loc_180002F3D
0x180002f2b  cmp     dword ptr [rax+8], 0C0h
0x180002f32  jnz     short loc_180002F3D
0x180002f34  cmp     dword ptr [rax+0Ch], 46000000h
0x180002f3b  jz      short loc_180002F45
0x180002f3d  mov     r8d, 80040110h
0x180002f43  jmp     short loc_180002F5B
0x180002f45  mov     rdx, rax
0x180002f48  mov     r8, r9
0x180002f4b  mov     rax, [r11+10h]
0x180002f4f  mov     rcx, r10
0x180002f52  call    cs:__guard_dispatch_icall_fptr
0x180002f58  mov     r8d, eax
0x180002f5b  mov     eax, r8d
0x180002f5e  add     rsp, 28h
0x180002f62  retn
```
