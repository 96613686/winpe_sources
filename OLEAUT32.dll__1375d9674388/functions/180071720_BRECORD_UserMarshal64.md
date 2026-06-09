# BRECORD_UserMarshal64

- ea: `0x180071720`
- end: `0x1800718e3`
- name: `BRECORD_UserMarshal64`
- size: `451`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180045180`
- `0x180045d50`

## callees

- `0x1800716f0`
- `0x180071720`
- `0x18009c010`

## import_xrefs

- `combase!WdtpInterfacePointer_UserMarshal64` at `0x180071790`
- `combase!WdtpInterfacePointer_UserMarshal64` at `0x180071790`
- `combase!__imp_CoDoesOtherSideSupportUDTMarshaling` at `0x180071752`
- `combase!__imp_CoDoesOtherSideSupportUDTMarshaling` at `0x180071752`
- `RPCRT4!RpcRaiseException` at `0x180071761`
- `RPCRT4!RpcRaiseException` at `0x1800717e8`
- `RPCRT4!RpcRaiseException` at `0x1800718a8`
- `RPCRT4!RpcRaiseException` at `0x180071761`
- `RPCRT4!RpcRaiseException` at `0x1800717e8`
- `RPCRT4!RpcRaiseException` at `0x1800718a8`

## pseudocode

```c
unsigned __int8 *__fastcall BRECORD_UserMarshal64(
        unsigned int *a1,
        unsigned __int8 *a2,
        unsigned int a3,
        __int64 (__fastcall ***a4)(_QWORD, GUID *, __int64 *),
        __int64 a5)
{
  unsigned __int8 *v9; // rbx
  unsigned __int8 *v10; // rax
  __int64 v11; // r15
  unsigned __int8 *v12; // rdi
  __int64 (__fastcall **v13)(_QWORD, GUID *, __int64 *); // rax
  RPC_STATUS v14; // eax
  __int64 (__fastcall **v15)(_QWORD, GUID *, __int64 *); // rax
  __int64 v16; // r13
  unsigned int i; // esi
  __int64 v18; // r9
  __int64 v19; // r8
  RPC_STATUS v20; // r14d
  __int64 v21; // rcx
  __int64 v22; // rax
  unsigned int v23; // [rsp+40h] [rbp-20h] BYREF
  __int64 v24; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int8 *v25; // [rsp+50h] [rbp-10h]
  unsigned __int8 *v26; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int v27; // [rsp+B8h] [rbp+58h] BYREF

  v26 = a2;
  if ( !a4 )
    return a2;
  if ( !(unsigned int)CoDoesOtherSideSupportUDTMarshaling(a1) )
    RpcRaiseException(1733);
  AlignAndZeroGap(&v26, 7u);
  v9 = v26;
  v10 = (unsigned __int8 *)WdtpInterfacePointer_UserMarshal64(a1, *a1, v26 + 24, a4, &IID_IRecordInfo);
  v11 = a5;
  v12 = v10;
  v26 = v10;
  if ( a5 )
  {
    AlignAndZeroGap(&v26, 7u);
    v13 = *a4;
    v12 = v26 + 8;
    v24 = 0;
    v25 = v26 + 8;
    v14 = (*v13)(a4, &IID_ITypeMarshal, &v24);
    if ( v14 < 0 )
      RpcRaiseException(v14);
    v15 = *a4;
    v16 = *((_QWORD *)a1 + 1);
    v23 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), unsigned int *))v15[8])(a4, &v23);
    for ( i = 0; i < a3; v11 += v23 )
    {
      v18 = *(_QWORD *)(v16 + 200);
      v19 = *(unsigned int *)(v16 + 196);
      v27 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, int, unsigned __int8 *, unsigned int *))(*(_QWORD *)v24 + 32LL))(
              v24,
              v11,
              v19,
              v18,
              -1,
              v12,
              &v27);
      if ( v20 < 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        RpcRaiseException(v20);
      }
      ++i;
      v12 += v27;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v21 = (unsigned int)((_DWORD)v12 - (_DWORD)v25);
    *(_QWORD *)v26 = v21;
    v22 = 4;
    *(_DWORD *)v9 = 1;
  }
  else
  {
    LODWORD(v21) = 0;
    *(_QWORD *)v9 = 0;
    v22 = 8;
  }
  *(_DWORD *)&v9[v22] = v21;
  *(_QWORD *)&v9[v22 + 4] = 1919251285;
  *(_QWORD *)&v9[v22 + 12] = v11;
  return v12;
}

```

## disassembly

```asm
0x180071720  mov     [rsp-38h+arg_0], rbx
0x180071725  mov     [rsp-38h+arg_8], rdx
0x18007172a  push    rbp
0x18007172b  push    rsi
0x18007172c  push    rdi
0x18007172d  push    r12
0x18007172f  push    r13
0x180071731  push    r14
0x180071733  push    r15
0x180071735  mov     rbp, rsp
0x180071738  sub     rsp, 60h
0x18007173c  mov     rsi, r9
0x18007173f  mov     r12d, r8d
0x180071742  mov     r14, rcx
0x180071745  test    r9, r9
0x180071748  jnz     short loc_180071752
0x18007174a  mov     rax, rdx
0x18007174d  jmp     loc_1800718CB
0x180071752  call    cs:__imp_CoDoesOtherSideSupportUDTMarshaling
0x180071758  test    eax, eax
0x18007175a  jnz     short loc_180071768
0x18007175c  mov     ecx, 6C5h; exception
0x180071761  call    cs:__imp_RpcRaiseException
0x180071767  int     3; Trap to Debugger
0x180071768  mov     dl, 7; unsigned __int8
0x18007176a  lea     rcx, [rbp+arg_8]; unsigned __int8 **
0x18007176e  call    ?AlignAndZeroGap@@YAXAEAPEAEE@Z; AlignAndZeroGap(uchar * &,uchar)
0x180071773  mov     rbx, [rbp+arg_8]
0x180071777  lea     rax, IID_IRecordInfo
0x18007177e  mov     edx, [r14]
0x180071781  mov     r9, rsi
0x180071784  mov     rcx, r14
0x180071787  mov     [rsp+60h+var_40], rax
0x18007178c  lea     r8, [rbx+18h]
0x180071790  call    cs:__imp_WdtpInterfacePointer_UserMarshal64
0x180071796  mov     r15, [rbp+arg_20]
0x18007179a  mov     rdi, rax
0x18007179d  mov     [rbp+arg_8], rax
0x1800717a1  test    r15, r15
0x1800717a4  jz      loc_1800718AF
0x1800717aa  mov     dl, 7; unsigned __int8
0x1800717ac  lea     rcx, [rbp+arg_8]; unsigned __int8 **
0x1800717b0  call    ?AlignAndZeroGap@@YAXAEAPEAEE@Z; AlignAndZeroGap(uchar * &,uchar)
0x1800717b5  mov     rax, [rsi]
0x1800717b8  lea     r8, [rbp+var_18]
0x1800717bc  mov     rdi, [rbp+arg_8]
0x1800717c0  lea     rdx, IID_ITypeMarshal
0x1800717c7  add     rdi, 8
0x1800717cb  mov     [rbp+var_18], 0
0x1800717d3  mov     rcx, rsi
0x1800717d6  mov     [rbp+var_10], rdi
0x1800717da  mov     rax, [rax]
0x1800717dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800717e2  test    eax, eax
0x1800717e4  jns     short loc_1800717EF
0x1800717e6  mov     ecx, eax; exception
0x1800717e8  call    cs:__imp_RpcRaiseException
0x1800717ee  int     3; Trap to Debugger
0x1800717ef  mov     rax, [rsi]
0x1800717f2  lea     rdx, [rbp+var_20]
0x1800717f6  mov     r13, [r14+8]
0x1800717fa  mov     rcx, rsi
0x1800717fd  mov     [rbp+var_20], 0
0x180071804  mov     rax, [rax+40h]
0x180071808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007180d  xor     esi, esi
0x18007180f  test    r12d, r12d
0x180071812  jz      short loc_18007186C
0x180071814  mov     rcx, [rbp+var_18]
0x180071818  lea     rdx, [rbp+arg_18]
0x18007181c  mov     r9, [r13+0C8h]
0x180071823  mov     r8d, [r13+0C4h]
0x18007182a  mov     [rsp+60h+var_30], rdx
0x18007182f  mov     rdx, r15
0x180071832  mov     [rbp+arg_18], 0
0x180071839  mov     rax, [rcx]
0x18007183c  mov     [rsp+60h+var_38], rdi
0x180071841  mov     dword ptr [rsp+60h+var_40], 0FFFFFFFFh
0x180071849  mov     rax, [rax+20h]
0x18007184d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071852  mov     r14d, eax
0x180071855  test    eax, eax
0x180071857  js      short loc_180071895
0x180071859  mov     eax, [rbp+arg_18]
0x18007185c  inc     esi
0x18007185e  add     rdi, rax
0x180071861  mov     eax, [rbp+var_20]
0x180071864  add     r15, rax
0x180071867  cmp     esi, r12d
0x18007186a  jb      short loc_180071814
0x18007186c  mov     rcx, [rbp+var_18]
0x180071870  mov     rax, [rcx]
0x180071873  mov     rax, [rax+10h]
0x180071877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007187c  mov     rax, [rbp+arg_8]
0x180071880  mov     ecx, edi
0x180071882  sub     ecx, dword ptr [rbp+var_10]
0x180071885  mov     [rax], rcx
0x180071888  mov     eax, 4
0x18007188d  mov     dword ptr [rbx], 1
0x180071893  jmp     short loc_1800718B7
0x180071895  mov     rcx, [rbp+var_18]
0x180071899  mov     rax, [rcx]
0x18007189c  mov     rax, [rax+10h]
0x1800718a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800718a5  mov     ecx, r14d; exception
0x1800718a8  call    cs:__imp_RpcRaiseException
0x1800718ae  int     3; Trap to Debugger
0x1800718af  xor     ecx, ecx
0x1800718b1  mov     [rbx], rcx
0x1800718b4  lea     eax, [rcx+8]
0x1800718b7  mov     [rax+rbx], ecx
0x1800718ba  mov     qword ptr [rax+rbx+4], 72657355h
0x1800718c3  mov     [rax+rbx+0Ch], r15
0x1800718c8  mov     rax, rdi
0x1800718cb  mov     rbx, [rsp+60h+arg_0]
0x1800718d3  add     rsp, 60h
0x1800718d7  pop     r15
0x1800718d9  pop     r14
0x1800718db  pop     r13
0x1800718dd  pop     r12
0x1800718df  pop     rdi
0x1800718e0  pop     rsi
0x1800718e1  pop     rbp
0x1800718e2  retn
```
