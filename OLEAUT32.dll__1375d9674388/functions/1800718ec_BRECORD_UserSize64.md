# BRECORD_UserSize64

- ea: `0x1800718ec`
- end: `0x180071aaf`
- name: `BRECORD_UserSize64`
- size: `451`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180032270`
- `0x180045620`

## callees

- `0x180030ac8`
- `0x180030af8`
- `0x1800718ec`
- `0x18009c010`

## import_xrefs

- `combase!WdtpInterfacePointer_UserSize64` at `0x18007196b`
- `combase!WdtpInterfacePointer_UserSize64` at `0x18007196b`
- `combase!__imp_CoDoesOtherSideSupportUDTMarshaling` at `0x18007191b`
- `combase!__imp_CoDoesOtherSideSupportUDTMarshaling` at `0x18007191b`
- `RPCRT4!RpcRaiseException` at `0x18007192a`
- `RPCRT4!RpcRaiseException` at `0x1800719c6`
- `RPCRT4!RpcRaiseException` at `0x180071a56`
- `RPCRT4!RpcRaiseException` at `0x180071a70`
- `RPCRT4!RpcRaiseException` at `0x18007192a`
- `RPCRT4!RpcRaiseException` at `0x1800719c6`
- `RPCRT4!RpcRaiseException` at `0x180071a56`
- `RPCRT4!RpcRaiseException` at `0x180071a70`

## pseudocode

```c
__int64 __fastcall BRECORD_UserSize64(
        unsigned int *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 (__fastcall ***a4)(_QWORD, GUID *, __int64 *),
        __int64 a5)
{
  unsigned int v8; // eax
  __int64 v9; // rsi
  __int64 (__fastcall **v10)(_QWORD, GUID *, __int64 *); // rax
  RPC_STATUS v11; // eax
  __int64 (__fastcall **v12)(_QWORD, GUID *, __int64 *); // rax
  __int64 v13; // r13
  unsigned int v14; // ebx
  unsigned int i; // edi
  __int64 v16; // r9
  __int64 v17; // r8
  RPC_STATUS v18; // r14d
  unsigned int v20; // [rsp+30h] [rbp-10h] BYREF
  __int64 v21; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v22; // [rsp+78h] [rbp+38h] BYREF
  int v23; // [rsp+88h] [rbp+48h] BYREF

  v22 = a2;
  if ( a4 )
  {
    if ( !(unsigned int)CoDoesOtherSideSupportUDTMarshaling(a1) )
      RpcRaiseException(1733);
    Safe_Length_Align(&v22, 7);
    ULongAdd_RpcRaiseIfFailed(v22, 0x18u, &v22);
    v8 = WdtpInterfacePointer_UserSize64(a1, *a1, v22, a4, &IID_IRecordInfo);
    v9 = a5;
    a2 = v8;
    v22 = v8;
    if ( a5 )
    {
      Safe_Length_Align(&v22, 7);
      ULongAdd_RpcRaiseIfFailed(v22, 8u, &v22);
      v10 = *a4;
      v21 = 0;
      v11 = (*v10)(a4, &IID_ITypeMarshal, &v21);
      if ( v11 < 0 )
        RpcRaiseException(v11);
      v12 = *a4;
      v13 = *((_QWORD *)a1 + 1);
      v20 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), unsigned int *))v12[8])(a4, &v20);
      v14 = 0;
      for ( i = 0; i < a3; ++i )
      {
        v16 = *(_QWORD *)(v13 + 200);
        v17 = *(unsigned int *)(v13 + 196);
        v23 = 0;
        v18 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, int *))(*(_QWORD *)v21 + 24LL))(
                v21,
                v9,
                v17,
                v16,
                &v23);
        if ( v18 < 0 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          RpcRaiseException(v18);
        }
        if ( v14 + v23 < v14 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          RpcRaiseException(-2147418096);
        }
        v14 += v23;
        v9 += v20;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      ULongAdd_RpcRaiseIfFailed(v22, v14, &v22);
      return v22;
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1800718ec  mov     [rsp-28h+arg_0], rbx
0x1800718f1  mov     [rsp-28h+arg_10], rsi
0x1800718f6  mov     [rsp-28h+arg_8], edx
0x1800718fa  push    rbp
0x1800718fb  push    rdi
0x1800718fc  push    r13
0x1800718fe  push    r14
0x180071900  push    r15
0x180071902  mov     rbp, rsp
0x180071905  sub     rsp, 40h
0x180071909  mov     rbx, r9
0x18007190c  mov     r15d, r8d
0x18007190f  mov     rdi, rcx
0x180071912  test    r9, r9
0x180071915  jz      loc_180071A94
0x18007191b  call    cs:__imp_CoDoesOtherSideSupportUDTMarshaling
0x180071921  test    eax, eax
0x180071923  jnz     short loc_180071931
0x180071925  mov     ecx, 6C5h; exception
0x18007192a  call    cs:__imp_RpcRaiseException
0x180071930  int     3; Trap to Debugger
0x180071931  mov     r14d, 7
0x180071937  lea     rcx, [rbp+arg_8]; unsigned int *
0x18007193b  mov     edx, r14d; int
0x18007193e  call    ?Safe_Length_Align@@YAXAEAKH@Z; Safe_Length_Align(ulong &,int)
0x180071943  mov     ecx, [rbp+arg_8]; unsigned int
0x180071946  lea     r8, [rbp+arg_8]; unsigned int *
0x18007194a  lea     edx, [r14+11h]; unsigned int
0x18007194e  call    ?ULongAdd_RpcRaiseIfFailed@@YAXKKPEAK@Z; ULongAdd_RpcRaiseIfFailed(ulong,ulong,ulong *)
0x180071953  mov     r8d, [rbp+arg_8]
0x180071957  lea     rax, IID_IRecordInfo
0x18007195e  mov     edx, [rdi]
0x180071960  mov     r9, rbx
0x180071963  mov     rcx, rdi
0x180071966  mov     [rsp+40h+var_20], rax
0x18007196b  call    cs:__imp_WdtpInterfacePointer_UserSize64
0x180071971  mov     rsi, [rbp+arg_20]
0x180071975  mov     edx, eax
0x180071977  mov     [rbp+arg_8], eax
0x18007197a  test    rsi, rsi
0x18007197d  jz      loc_180071A94
0x180071983  mov     edx, r14d; int
0x180071986  lea     rcx, [rbp+arg_8]; unsigned int *
0x18007198a  call    ?Safe_Length_Align@@YAXAEAKH@Z; Safe_Length_Align(ulong &,int)
0x18007198f  mov     ecx, [rbp+arg_8]; unsigned int
0x180071992  lea     r8, [rbp+arg_8]; unsigned int *
0x180071996  lea     edx, [r14+1]; unsigned int
0x18007199a  call    ?ULongAdd_RpcRaiseIfFailed@@YAXKKPEAK@Z; ULongAdd_RpcRaiseIfFailed(ulong,ulong,ulong *)
0x18007199f  mov     rax, [rbx]
0x1800719a2  lea     r8, [rbp+var_8]
0x1800719a6  lea     rdx, IID_ITypeMarshal
0x1800719ad  mov     [rbp+var_8], 0
0x1800719b5  mov     rcx, rbx
0x1800719b8  mov     rax, [rax]
0x1800719bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800719c0  test    eax, eax
0x1800719c2  jns     short loc_1800719CD
0x1800719c4  mov     ecx, eax; exception
0x1800719c6  call    cs:__imp_RpcRaiseException
0x1800719cc  int     3; Trap to Debugger
0x1800719cd  mov     rax, [rbx]
0x1800719d0  lea     rdx, [rbp+var_10]
0x1800719d4  mov     r13, [rdi+8]
0x1800719d8  mov     rcx, rbx
0x1800719db  mov     [rbp+var_10], 0
0x1800719e2  mov     rax, [rax+40h]
0x1800719e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800719eb  xor     ebx, ebx
0x1800719ed  xor     edi, edi
0x1800719ef  mov     rcx, [rbp+var_8]
0x1800719f3  cmp     edi, r15d
0x1800719f6  jnb     short loc_180071A77
0x1800719f8  mov     r9, [r13+0C8h]
0x1800719ff  lea     rdx, [rbp+arg_18]
0x180071a03  mov     r8d, [r13+0C4h]
0x180071a0a  mov     [rbp+arg_18], 0
0x180071a11  mov     rax, [rcx]
0x180071a14  mov     [rsp+40h+var_20], rdx
0x180071a19  mov     rdx, rsi
0x180071a1c  mov     rax, [rax+18h]
0x180071a20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071a25  mov     r14d, eax
0x180071a28  test    eax, eax
0x180071a2a  js      short loc_180071A5D
0x180071a2c  mov     ecx, [rbp+arg_18]
0x180071a2f  add     ecx, ebx
0x180071a31  cmp     ecx, ebx
0x180071a33  jb      short loc_180071A41
0x180071a35  mov     eax, [rbp+var_10]
0x180071a38  mov     ebx, ecx
0x180071a3a  add     rsi, rax
0x180071a3d  inc     edi
0x180071a3f  jmp     short loc_1800719EF
0x180071a41  mov     rcx, [rbp+var_8]
0x180071a45  mov     rax, [rcx]
0x180071a48  mov     rax, [rax+10h]
0x180071a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071a51  mov     ecx, 80010010h; exception
0x180071a56  call    cs:__imp_RpcRaiseException
0x180071a5c  int     3; Trap to Debugger
0x180071a5d  mov     rcx, [rbp+var_8]
0x180071a61  mov     rax, [rcx]
0x180071a64  mov     rax, [rax+10h]
0x180071a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071a6d  mov     ecx, r14d; exception
0x180071a70  call    cs:__imp_RpcRaiseException
0x180071a76  int     3; Trap to Debugger
0x180071a77  mov     rax, [rcx]
0x180071a7a  mov     rax, [rax+10h]
0x180071a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071a83  mov     ecx, [rbp+arg_8]; unsigned int
0x180071a86  lea     r8, [rbp+arg_8]; unsigned int *
0x180071a8a  mov     edx, ebx; unsigned int
0x180071a8c  call    ?ULongAdd_RpcRaiseIfFailed@@YAXKKPEAK@Z; ULongAdd_RpcRaiseIfFailed(ulong,ulong,ulong *)
0x180071a91  mov     edx, [rbp+arg_8]
0x180071a94  lea     r11, [rsp+40h+var_s0]
0x180071a99  mov     eax, edx
0x180071a9b  mov     rbx, [r11+30h]
0x180071a9f  mov     rsi, [r11+40h]
0x180071aa3  mov     rsp, r11
0x180071aa6  pop     r15
0x180071aa8  pop     r14
0x180071aaa  pop     r13
0x180071aac  pop     rdi
0x180071aad  pop     rbp
0x180071aae  retn
```
