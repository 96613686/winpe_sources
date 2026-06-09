# CComBase::NDQueryInterface(_GUID const &,void * *)

- ea: `0x180006a20`
- end: `0x180006a69`
- name: `?NDQueryInterface@CComBase@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `73`
- prototype: `__int64 __fastcall(CComBase *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006a20`
- `0x180006bd8`

## pseudocode

```c
__int64 __fastcall CComBase::NDQueryInterface(CComBase *this, const struct _GUID *a2, void **a3)
{
  __int64 v3; // rax

  if ( !a3 )
    return 2147500035LL;
  v3 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
    v3 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IUnknown.Data4;
  if ( v3 )
  {
    *a3 = 0;
    return 2147500034LL;
  }
  else
  {
    CodecDSPGetInterface(this, a3);
    return 0;
  }
}

```

## disassembly

```asm
0x180006a20  sub     rsp, 28h
0x180006a24  test    r8, r8
0x180006a27  jz      short loc_180006A53
0x180006a29  mov     rax, [rdx]
0x180006a2c  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x180006a33  jnz     short loc_180006A40
0x180006a35  mov     rax, [rdx+8]
0x180006a39  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180006a40  test    rax, rax
0x180006a43  jz      short loc_180006A5D
0x180006a45  mov     qword ptr [r8], 0
0x180006a4c  mov     eax, 80004002h
0x180006a51  jmp     short loc_180006A58
0x180006a53  mov     eax, 80004003h
0x180006a58  add     rsp, 28h
0x180006a5c  retn
0x180006a5d  mov     rdx, r8
0x180006a60  call    CodecDSPGetInterface
0x180006a65  xor     eax, eax
0x180006a67  jmp     short loc_180006A58
```
