# CComBase::NDQueryInterface(_GUID const &,void * *)

- ea: `0x18002ead0`
- end: `0x18002eb19`
- name: `?NDQueryInterface@CComBase@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `73`
- prototype: `__int64 __fastcall(CComBase *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180025090`

## callees

- `0x180025268`
- `0x18002ead0`

## pseudocode

```c
__int64 __fastcall CComBase::NDQueryInterface(CComBase *this, const struct _GUID *a2, void **a3)
{
  __int64 v4; // rax

  if ( !a3 )
    return 2147500035LL;
  v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
    v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IUnknown.Data4;
  if ( v4 )
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
0x18002ead0  sub     rsp, 28h
0x18002ead4  test    r8, r8
0x18002ead7  jnz     short loc_18002EAE0
0x18002ead9  mov     eax, 80004003h
0x18002eade  jmp     short loc_18002EB14
0x18002eae0  mov     rax, [rdx]
0x18002eae3  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18002eaea  jnz     short loc_18002EAF7
0x18002eaec  mov     rax, [rdx+8]
0x18002eaf0  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x18002eaf7  test    rax, rax
0x18002eafa  jnz     short loc_18002EB08
0x18002eafc  mov     rdx, r8
0x18002eaff  call    CodecDSPGetInterface
0x18002eb04  xor     eax, eax
0x18002eb06  jmp     short loc_18002EB14
0x18002eb08  mov     qword ptr [r8], 0
0x18002eb0f  mov     eax, 80004002h
0x18002eb14  add     rsp, 28h
0x18002eb18  retn
```
