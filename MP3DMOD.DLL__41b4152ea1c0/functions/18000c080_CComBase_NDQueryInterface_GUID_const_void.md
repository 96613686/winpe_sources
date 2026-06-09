# CComBase::NDQueryInterface(_GUID const &,void * *)

- ea: `0x18000c080`
- end: `0x18000c0c9`
- name: `?NDQueryInterface@CComBase@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `73`
- prototype: `__int64 __fastcall(CComBase *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c0d0`

## callees

- `0x18000c080`
- `0x18000c168`

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
0x18000c080  sub     rsp, 28h
0x18000c084  test    r8, r8
0x18000c087  jz      short loc_18000C0C2
0x18000c089  mov     rax, [rdx]
0x18000c08c  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18000c093  jnz     short loc_18000C0A0
0x18000c095  mov     rax, [rdx+8]
0x18000c099  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x18000c0a0  test    rax, rax
0x18000c0a3  jnz     short loc_18000C0B4
0x18000c0a5  mov     rdx, r8
0x18000c0a8  call    CodecDSPGetInterface
0x18000c0ad  xor     eax, eax
0x18000c0af  add     rsp, 28h
0x18000c0b3  retn
0x18000c0b4  mov     qword ptr [r8], 0
0x18000c0bb  mov     eax, 80004002h
0x18000c0c0  jmp     short loc_18000C0AF
0x18000c0c2  mov     eax, 80004003h
0x18000c0c7  jmp     short loc_18000C0AF
```
