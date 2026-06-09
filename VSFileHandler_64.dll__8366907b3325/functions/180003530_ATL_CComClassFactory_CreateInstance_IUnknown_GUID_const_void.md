# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003530`
- end: `0x18000358d`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `93`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003530`

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
0x180003530  sub     rsp, 28h
0x180003534  mov     r11, rcx
0x180003537  mov     rax, r8
0x18000353a  xor     ecx, ecx
0x18000353c  mov     r10, rdx
0x18000353f  mov     r8d, 80004003h
0x180003545  test    r9, r9
0x180003548  jz      short loc_180003585
0x18000354a  mov     [r9], rcx
0x18000354d  test    rdx, rdx
0x180003550  jz      short loc_180003575
0x180003552  cmp     [rax], ecx
0x180003554  jnz     short loc_18000356D
0x180003556  cmp     [rax+4], ecx
0x180003559  jnz     short loc_18000356D
0x18000355b  cmp     dword ptr [rax+8], 0C0h
0x180003562  jnz     short loc_18000356D
0x180003564  cmp     dword ptr [rax+0Ch], 46000000h
0x18000356b  jz      short loc_180003575
0x18000356d  mov     r8d, 80040110h
0x180003573  jmp     short loc_180003585
0x180003575  mov     r8, r9
0x180003578  mov     rdx, rax
0x18000357b  mov     rcx, r10
0x18000357e  call    qword ptr [r11+40h]
0x180003582  mov     r8d, eax
0x180003585  mov     eax, r8d
0x180003588  add     rsp, 28h
0x18000358c  retn
```
