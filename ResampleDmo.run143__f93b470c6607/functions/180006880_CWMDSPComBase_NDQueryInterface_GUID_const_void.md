# CWMDSPComBase::NDQueryInterface(_GUID const &,void * *)

- ea: `0x180006880`
- end: `0x1800068c9`
- name: `?NDQueryInterface@CWMDSPComBase@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `73`
- prototype: `__int64 __fastcall(CWMDSPComBase *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006880`
- `0x180006bd8`

## pseudocode

```c
__int64 __fastcall CWMDSPComBase::NDQueryInterface(CWMDSPComBase *this, const struct _GUID *a2, void **a3)
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
0x180006880  sub     rsp, 28h
0x180006884  test    r8, r8
0x180006887  jz      short loc_1800068C2
0x180006889  mov     rax, [rdx]
0x18000688c  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x180006893  jnz     short loc_1800068A0
0x180006895  mov     rax, [rdx+8]
0x180006899  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x1800068a0  test    rax, rax
0x1800068a3  jnz     short loc_1800068B4
0x1800068a5  mov     rdx, r8
0x1800068a8  call    CodecDSPGetInterface
0x1800068ad  xor     eax, eax
0x1800068af  add     rsp, 28h
0x1800068b3  retn
0x1800068b4  mov     qword ptr [r8], 0
0x1800068bb  mov     eax, 80004002h
0x1800068c0  jmp     short loc_1800068AF
0x1800068c2  mov     eax, 80004003h
0x1800068c7  jmp     short loc_1800068AF
```
