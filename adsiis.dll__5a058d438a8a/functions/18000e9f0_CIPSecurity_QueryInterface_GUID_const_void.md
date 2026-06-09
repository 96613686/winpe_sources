# CIPSecurity::QueryInterface(_GUID const &,void * *)

- ea: `0x18000e9f0`
- end: `0x18000ea78`
- name: `?QueryInterface@CIPSecurity@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `136`
- prototype: `__int64 __fastcall(CIPSecurity *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000e9f0`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CIPSecurity::QueryInterface(CIPSecurity *this, const struct _GUID *a2, void **a3)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax

  if ( !a3 )
    return 2147500035LL;
  v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
    v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IUnknown.Data4;
  if ( !v4 )
    goto LABEL_13;
  v5 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IISIPSecurity.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IISIPSecurity.Data1 )
    v5 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IISIPSecurity.Data4;
  if ( !v5 )
    goto LABEL_13;
  v6 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IDispatch.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IDispatch.Data1 )
    v6 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IDispatch.Data4;
  if ( v6 )
  {
    *a3 = 0;
    return 2147500034LL;
  }
  else
  {
LABEL_13:
    *a3 = this;
    (*(void (__fastcall **)(CIPSecurity *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
}

```

## disassembly

```asm
0x18000e9f0  sub     rsp, 28h
0x18000e9f4  test    r8, r8
0x18000e9f7  jnz     short loc_18000EA00
0x18000e9f9  mov     eax, 80004003h
0x18000e9fe  jmp     short loc_18000EA73
0x18000ea00  mov     rax, [rdx]
0x18000ea03  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18000ea0a  jnz     short loc_18000EA17
0x18000ea0c  mov     rax, [rdx+8]
0x18000ea10  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x18000ea17  test    rax, rax
0x18000ea1a  jz      short loc_18000EA62
0x18000ea1c  mov     rax, [rdx]
0x18000ea1f  sub     rax, qword ptr cs:IID_IISIPSecurity.Data1
0x18000ea26  jnz     short loc_18000EA33
0x18000ea28  mov     rax, [rdx+8]
0x18000ea2c  sub     rax, qword ptr cs:IID_IISIPSecurity.Data4
0x18000ea33  test    rax, rax
0x18000ea36  jz      short loc_18000EA62
0x18000ea38  mov     rax, [rdx]
0x18000ea3b  sub     rax, qword ptr cs:IID_IDispatch.Data1
0x18000ea42  jnz     short loc_18000EA4F
0x18000ea44  mov     rax, [rdx+8]
0x18000ea48  sub     rax, qword ptr cs:IID_IDispatch.Data4
0x18000ea4f  test    rax, rax
0x18000ea52  jz      short loc_18000EA62
0x18000ea54  mov     qword ptr [r8], 0
0x18000ea5b  mov     eax, 80004002h
0x18000ea60  jmp     short loc_18000EA73
0x18000ea62  mov     [r8], rcx
0x18000ea65  mov     rax, [rcx]
0x18000ea68  mov     rax, [rax+8]
0x18000ea6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea71  xor     eax, eax
0x18000ea73  add     rsp, 28h
0x18000ea77  retn
```
