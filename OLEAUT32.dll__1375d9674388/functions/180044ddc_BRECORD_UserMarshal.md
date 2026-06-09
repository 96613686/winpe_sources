# BRECORD_UserMarshal

- ea: `0x180044ddc`
- end: `0x180044f9c`
- name: `BRECORD_UserMarshal`
- size: `448`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003d540`
- `0x180045970`

## callees

- `0x180044ddc`
- `0x1800716f0`
- `0x18009c010`

## import_xrefs

- `combase!WdtpInterfacePointer_UserMarshal` at `0x180044e4c`
- `combase!WdtpInterfacePointer_UserMarshal` at `0x180044e4c`
- `combase!__imp_CoDoesOtherSideSupportUDTMarshaling` at `0x180044e0e`
- `combase!__imp_CoDoesOtherSideSupportUDTMarshaling` at `0x180044e0e`
- `RPCRT4!RpcRaiseException` at `0x180044e1d`
- `RPCRT4!RpcRaiseException` at `0x180044ea4`
- `RPCRT4!RpcRaiseException` at `0x180044f66`
- `RPCRT4!RpcRaiseException` at `0x180044e1d`
- `RPCRT4!RpcRaiseException` at `0x180044ea4`
- `RPCRT4!RpcRaiseException` at `0x180044f66`

## pseudocode

```c
unsigned __int8 *__fastcall BRECORD_UserMarshal(
        unsigned int *a1,
        unsigned __int8 *a2,
        unsigned int a3,
        __int64 (__fastcall ***a4)(_QWORD, GUID *, __int64 *),
        __int64 a5)
{
  unsigned __int8 *result; // rax
  unsigned __int8 *v9; // rdi
  unsigned __int8 *v10; // rax
  __int64 v11; // r15
  unsigned __int8 *v12; // rbx
  __int64 (__fastcall **v13)(_QWORD, GUID *, __int64 *); // rax
  RPC_STATUS v14; // eax
  __int64 (__fastcall **v15)(_QWORD, GUID *, __int64 *); // rax
  __int64 v16; // r13
  unsigned int v17; // r14d
  int i; // esi
  __int64 v19; // r9
  __int64 v20; // r8
  RPC_STATUS v21; // r13d
  int v22; // eax
  unsigned int v23; // [rsp+40h] [rbp-20h] BYREF
  __int64 v24; // [rsp+48h] [rbp-18h] BYREF
  __int64 v25; // [rsp+50h] [rbp-10h]
  unsigned __int8 *v26; // [rsp+58h] [rbp-8h]
  unsigned __int8 *v27; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int v28; // [rsp+B8h] [rbp+58h] BYREF

  v27 = a2;
  if ( !a4 )
    return a2;
  if ( !(unsigned int)CoDoesOtherSideSupportUDTMarshaling(a1) )
    RpcRaiseException(1733);
  AlignAndZeroGap(&v27, 3u);
  v9 = v27;
  v10 = (unsigned __int8 *)WdtpInterfacePointer_UserMarshal(a1, *a1, v27 + 16, a4, &IID_IRecordInfo);
  v11 = a5;
  v12 = v10;
  v27 = v10;
  if ( a5 )
  {
    AlignAndZeroGap(&v27, 3u);
    v13 = *a4;
    v12 = v27 + 4;
    v24 = 0;
    v26 = v27 + 4;
    v14 = (*v13)(a4, &IID_ITypeMarshal, &v24);
    if ( v14 < 0 )
      RpcRaiseException(v14);
    v15 = *a4;
    v16 = *((_QWORD *)a1 + 1);
    v25 = v16;
    v23 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), unsigned int *))v15[8])(a4, &v23);
    v17 = 0;
    for ( i = 1; v17 < a3; v11 += v23 )
    {
      v19 = *(_QWORD *)(v16 + 200);
      v20 = *(unsigned int *)(v16 + 196);
      v28 = 0;
      v21 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, int, unsigned __int8 *, unsigned int *))(*(_QWORD *)v24 + 32LL))(
              v24,
              v11,
              v20,
              v19,
              -1,
              v12,
              &v28);
      if ( v21 < 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        RpcRaiseException(v21);
      }
      ++v17;
      v16 = v25;
      v12 += v28;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v22 = (_DWORD)v12 - (_DWORD)v26;
    *(_DWORD *)v27 = (_DWORD)v12 - (_DWORD)v26;
  }
  else
  {
    v22 = 0;
    i = 0;
  }
  *(_DWORD *)v9 = i;
  *((_DWORD *)v9 + 1) = v22;
  result = v12;
  *((_DWORD *)v9 + 2) = 1919251285;
  *((_DWORD *)v9 + 3) = v11;
  return result;
}

```

## disassembly

```asm
0x180044ddc  mov     [rsp-38h+arg_0], rbx
0x180044de1  mov     [rsp-38h+arg_8], rdx
0x180044de6  push    rbp
0x180044de7  push    rsi
0x180044de8  push    rdi
0x180044de9  push    r12
0x180044deb  push    r13
0x180044ded  push    r14
0x180044def  push    r15
0x180044df1  mov     rbp, rsp
0x180044df4  sub     rsp, 60h
0x180044df8  mov     rsi, r9
0x180044dfb  mov     r12d, r8d
0x180044dfe  mov     r14, rcx
0x180044e01  test    r9, r9
0x180044e04  jnz     short loc_180044E0E
0x180044e06  mov     rax, rdx
0x180044e09  jmp     loc_180044F84
0x180044e0e  call    cs:__imp_CoDoesOtherSideSupportUDTMarshaling
0x180044e14  test    eax, eax
0x180044e16  jnz     short loc_180044E24
0x180044e18  mov     ecx, 6C5h; exception
0x180044e1d  call    cs:__imp_RpcRaiseException
0x180044e23  int     3; Trap to Debugger
0x180044e24  mov     dl, 3; unsigned __int8
0x180044e26  lea     rcx, [rbp+arg_8]; unsigned __int8 **
0x180044e2a  call    ?AlignAndZeroGap@@YAXAEAPEAEE@Z; AlignAndZeroGap(uchar * &,uchar)
0x180044e2f  mov     rdi, [rbp+arg_8]
0x180044e33  lea     rax, IID_IRecordInfo
0x180044e3a  mov     edx, [r14]
0x180044e3d  mov     r9, rsi
0x180044e40  mov     rcx, r14
0x180044e43  mov     [rsp+60h+var_40], rax
0x180044e48  lea     r8, [rdi+10h]
0x180044e4c  call    cs:__imp_WdtpInterfacePointer_UserMarshal
0x180044e52  mov     r15, [rbp+arg_20]
0x180044e56  mov     rbx, rax
0x180044e59  mov     [rbp+arg_8], rax
0x180044e5d  test    r15, r15
0x180044e60  jz      loc_180044F6D
0x180044e66  mov     dl, 3; unsigned __int8
0x180044e68  lea     rcx, [rbp+arg_8]; unsigned __int8 **
0x180044e6c  call    ?AlignAndZeroGap@@YAXAEAPEAEE@Z; AlignAndZeroGap(uchar * &,uchar)
0x180044e71  mov     rax, [rsi]
0x180044e74  lea     r8, [rbp+var_18]
0x180044e78  mov     rbx, [rbp+arg_8]
0x180044e7c  lea     rdx, IID_ITypeMarshal
0x180044e83  add     rbx, 4
0x180044e87  mov     [rbp+var_18], 0
0x180044e8f  mov     rcx, rsi
0x180044e92  mov     [rbp+var_8], rbx
0x180044e96  mov     rax, [rax]
0x180044e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e9e  test    eax, eax
0x180044ea0  jns     short loc_180044EAB
0x180044ea2  mov     ecx, eax; exception
0x180044ea4  call    cs:__imp_RpcRaiseException
0x180044eaa  int     3; Trap to Debugger
0x180044eab  mov     rax, [rsi]
0x180044eae  lea     rdx, [rbp+var_20]
0x180044eb2  mov     r13, [r14+8]
0x180044eb6  mov     rcx, rsi
0x180044eb9  mov     [rbp+var_10], r13
0x180044ebd  mov     [rbp+var_20], 0
0x180044ec4  mov     rax, [rax+40h]
0x180044ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ecd  xor     r14d, r14d
0x180044ed0  lea     esi, [r14+1]
0x180044ed4  test    r12d, r12d
0x180044ed7  jz      short loc_180044F36
0x180044ed9  mov     rcx, [rbp+var_18]
0x180044edd  lea     rdx, [rbp+arg_18]
0x180044ee1  mov     r9, [r13+0C8h]
0x180044ee8  mov     r8d, [r13+0C4h]
0x180044eef  mov     [rsp+60h+var_30], rdx
0x180044ef4  mov     rdx, r15
0x180044ef7  mov     [rbp+arg_18], 0
0x180044efe  mov     rax, [rcx]
0x180044f01  mov     [rsp+60h+var_38], rbx
0x180044f06  mov     dword ptr [rsp+60h+var_40], 0FFFFFFFFh
0x180044f0e  mov     rax, [rax+20h]
0x180044f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f17  mov     r13d, eax
0x180044f1a  test    eax, eax
0x180044f1c  js      short loc_180044F53
0x180044f1e  mov     eax, [rbp+arg_18]
0x180044f21  add     r14d, esi
0x180044f24  mov     r13, [rbp+var_10]
0x180044f28  add     rbx, rax
0x180044f2b  mov     eax, [rbp+var_20]
0x180044f2e  add     r15, rax
0x180044f31  cmp     r14d, r12d
0x180044f34  jb      short loc_180044ED9
0x180044f36  mov     rcx, [rbp+var_18]
0x180044f3a  mov     rax, [rcx]
0x180044f3d  mov     rax, [rax+10h]
0x180044f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f46  mov     rcx, [rbp+arg_8]
0x180044f4a  mov     eax, ebx
0x180044f4c  sub     eax, dword ptr [rbp+var_8]
0x180044f4f  mov     [rcx], eax
0x180044f51  jmp     short loc_180044F71
0x180044f53  mov     rcx, [rbp+var_18]
0x180044f57  mov     rax, [rcx]
0x180044f5a  mov     rax, [rax+10h]
0x180044f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f63  mov     ecx, r13d; exception
0x180044f66  call    cs:__imp_RpcRaiseException
0x180044f6c  int     3; Trap to Debugger
0x180044f6d  xor     eax, eax
0x180044f6f  xor     esi, esi
0x180044f71  mov     [rdi], esi
0x180044f73  mov     [rdi+4], eax
0x180044f76  mov     rax, rbx
0x180044f79  mov     dword ptr [rdi+8], 72657355h
0x180044f80  mov     [rdi+0Ch], r15d
0x180044f84  mov     rbx, [rsp+60h+arg_0]
0x180044f8c  add     rsp, 60h
0x180044f90  pop     r15
0x180044f92  pop     r14
0x180044f94  pop     r13
0x180044f96  pop     r12
0x180044f98  pop     rdi
0x180044f99  pop     rsi
0x180044f9a  pop     rbp
0x180044f9b  retn
```
