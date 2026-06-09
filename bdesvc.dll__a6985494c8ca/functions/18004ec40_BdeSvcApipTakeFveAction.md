# BdeSvcApipTakeFveAction

- ea: `0x18004ec40`
- end: `0x18004f264`
- name: `BdeSvcApipTakeFveAction`
- size: `1572`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18001c6c8`
- `0x180031430`
- `0x180034070`
- `0x1800498d0`
- `0x18004ec40`
- `0x18007e010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18004ecb2`
- `RPCRT4!RpcImpersonateClient` at `0x18004ecb2`
- `RPCRT4!RpcRevertToSelf` at `0x18004ede5`
- `RPCRT4!RpcRevertToSelf` at `0x18004ef71`
- `RPCRT4!RpcRevertToSelf` at `0x18004f13b`
- `RPCRT4!RpcRevertToSelf` at `0x18004ede5`
- `RPCRT4!RpcRevertToSelf` at `0x18004ef71`
- `RPCRT4!RpcRevertToSelf` at `0x18004f13b`
- `FVEAPI!FveGetSecureBootBindingState` at `0x18004f1c4`
- `FVEAPI!FveGetSecureBootBindingState` at `0x18004f1c4`
- `FVEAPI!FveQueryDeviceEncryptionSupport` at `0x18004eff6`
- `FVEAPI!FveQueryDeviceEncryptionSupport` at `0x18004eff6`

## pseudocode

```c
__int64 __fastcall BdeSvcApipTakeFveAction(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        int *a4,
        unsigned int a5,
        __int64 a6,
        unsigned int a7,
        _DWORD *a8,
        _DWORD *a9)
{
  unsigned int v12; // eax
  unsigned int v13; // esi
  PVOID *v14; // rcx
  unsigned int v15; // esi
  unsigned int v16; // ebx
  _QWORD *v17; // rdx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  unsigned int v24; // eax
  unsigned int v25; // r15d
  PVOID *v26; // rcx
  __int64 v27; // rdx
  __int128 v28; // xmm0
  int v29; // eax
  int v30; // r15d
  int v31; // eax
  __int64 v32; // r9
  unsigned int v33; // eax
  unsigned int v34; // r15d
  int SecureBootBindingState; // eax
  int v36; // ebx
  int v37; // eax
  _QWORD v38[7]; // [rsp+30h] [rbp-59h] BYREF
  _QWORD *v39; // [rsp+68h] [rbp-21h]
  __int128 v40; // [rsp+70h] [rbp-19h] BYREF
  int v41; // [rsp+80h] [rbp-9h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 378, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
  v12 = RpcImpersonateClient(0);
  v13 = v12;
  if ( v12 )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 379, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v12);
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
    v15 = v13 | 0x80010000;
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 0x40) != 0 )
      WPP_SF_d(v14[2], 380, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v15);
    *a9 = 0;
    goto LABEL_24;
  }
  v15 = 0;
  if ( !a3 )
  {
    v37 = BdeSvcResumeProtection(a2);
    v16 = v37;
    if ( v37 >= 0 )
      goto LABEL_23;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_23;
    v20 = 381;
    v32 = (unsigned int)v37;
    goto LABEL_70;
  }
  if ( a3 != 1 )
  {
    if ( a3 != 2 )
    {
      if ( a3 == 3 )
      {
        v38[0] = &std::_Func_impl_no_alloc<long (*)(void const *,unsigned long,unsigned long &,bool *),long,void const *,unsigned long,unsigned long &,bool *>::`vftable';
        v38[1] = BdeSvcNetworkStateChangeCallback;
        v39 = v38;
        WnfSubscriptions::CreateWnfSubscription(&WNF_SEB_NETWORK_STATE_CHANGES, v38);
        if ( v39 )
        {
          v17 = v38;
          LOBYTE(v17) = v39 != v38;
          (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v39 + 32LL))(v39, v17);
        }
        v16 = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 396, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, a3);
        v16 = -2147024846;
      }
      goto LABEL_23;
    }
    v41 = 0;
    v40 = 0;
    if ( !a4 )
    {
      v19 = WPP_GLOBAL_Control;
      v16 = -2147024809;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_23;
      v20 = 388;
      goto LABEL_69;
    }
    v21 = a5;
    if ( a5 < 0x14 )
    {
      v22 = WPP_GLOBAL_Control;
      v16 = -2147024809;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_23;
      v23 = 389;
      goto LABEL_81;
    }
    if ( a4[2] < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      v16 = -2147024809;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_23;
      v20 = 390;
      goto LABEL_69;
    }
    if ( !a6 )
    {
      v19 = WPP_GLOBAL_Control;
      v16 = -2147467261;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_23;
      v20 = 391;
      goto LABEL_69;
    }
    v21 = a7;
    if ( a7 < 0x14 )
    {
      if ( a8 )
        *a8 = 20;
      v22 = WPP_GLOBAL_Control;
      v16 = -2147024774;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_23;
      v23 = 392;
      goto LABEL_81;
    }
    v24 = RpcRevertToSelf();
    v25 = v24;
    if ( v24 )
    {
      v26 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 393, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v24);
        v26 = (PVOID *)WPP_GLOBAL_Control;
      }
      v15 = v25 | 0x80010000;
      if ( v26 == &WPP_GLOBAL_Control || (*((_BYTE *)v26 + 28) & 0x40) == 0 )
        goto LABEL_90;
      v27 = 394;
LABEL_89:
      WPP_SF_d(v26[2], v27, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v15);
LABEL_90:
      v16 = 0;
      goto LABEL_23;
    }
    v28 = *(_OWORD *)a4;
    v41 = a4[4];
    v40 = v28;
    v29 = FveQueryDeviceEncryptionSupport(&v40);
    v30 = v29;
    if ( v29 >= 0 )
    {
      v31 = v41;
      *(_OWORD *)a6 = v40;
      *(_DWORD *)(a6 + 16) = v31;
      if ( a8 )
        *a8 = 20;
      *a9 = v30;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          395,
          &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
          (unsigned int)v29);
      *a9 = v30;
    }
    goto LABEL_24;
  }
  if ( !a6 )
  {
    v19 = WPP_GLOBAL_Control;
    v16 = -2147467261;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_23;
    v20 = 382;
    goto LABEL_69;
  }
  if ( (a6 & 0xFFFFFFFFFFFFFFFCuLL) != a6 )
  {
    v19 = WPP_GLOBAL_Control;
    v16 = -2147467261;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_23;
    v20 = 383;
LABEL_69:
    v32 = v16;
LABEL_70:
    WPP_SF_d(v19[2], v20, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v32);
LABEL_23:
    *a9 = v16;
    RpcRevertToSelf();
    goto LABEL_24;
  }
  v21 = a7;
  if ( a7 < 4 )
  {
    if ( a8 )
      *a8 = 4;
    v22 = WPP_GLOBAL_Control;
    v16 = -2147024774;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_23;
    v23 = 384;
LABEL_81:
    WPP_SF_DD(v22[2], v23, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v21, v16);
    goto LABEL_23;
  }
  v33 = RpcRevertToSelf();
  v34 = v33;
  if ( v33 )
  {
    v26 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 385, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v33);
      v26 = (PVOID *)WPP_GLOBAL_Control;
    }
    v15 = v34 | 0x80010000;
    if ( v26 == &WPP_GLOBAL_Control || (*((_BYTE *)v26 + 28) & 0x40) == 0 )
      goto LABEL_90;
    v27 = 386;
    goto LABEL_89;
  }
  SecureBootBindingState = FveGetSecureBootBindingState(a6 & 0xFFFFFFFFFFFFFFFCuLL | 1);
  v36 = SecureBootBindingState;
  if ( SecureBootBindingState >= 0 )
  {
    if ( a8 )
      *a8 = 4;
    *a9 = SecureBootBindingState;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        387,
        &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
        (unsigned int)SecureBootBindingState);
    *a9 = v36;
  }
LABEL_24:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 397, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v15);
  return v15;
}

```

## disassembly

```asm
0x18004ec40  mov     [rsp-8+arg_0], rbx
0x18004ec45  push    rbp
0x18004ec46  push    rsi
0x18004ec47  push    rdi
0x18004ec48  push    r12
0x18004ec4a  push    r13
0x18004ec4c  push    r14
0x18004ec4e  push    r15
0x18004ec50  lea     rbp, [rsp-7]
0x18004ec55  sub     rsp, 90h
0x18004ec5c  mov     rax, cs:__security_cookie
0x18004ec63  xor     rax, rsp
0x18004ec66  mov     [rbp+37h+var_38], rax
0x18004ec6a  mov     rbx, [rbp+37h+arg_28]
0x18004ec6e  mov     r13, r9
0x18004ec71  mov     r14, [rbp+37h+arg_38]
0x18004ec75  mov     r15d, r8d
0x18004ec78  mov     rdi, [rbp+37h+arg_40]
0x18004ec7f  mov     r12, rdx
0x18004ec82  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ec89  lea     rax, WPP_GLOBAL_Control
0x18004ec90  cmp     rcx, rax
0x18004ec93  jz      short loc_18004ECB0
0x18004ec95  test    byte ptr [rcx+1Ch], 20h
0x18004ec99  jz      short loc_18004ECB0
0x18004ec9b  mov     rcx, [rcx+10h]
0x18004ec9f  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004eca6  mov     edx, 17Ah
0x18004ecab  call    WPP_SF_
0x18004ecb0  xor     ecx, ecx; BindingHandle
0x18004ecb2  call    cs:__imp_RpcImpersonateClient
0x18004ecb9  nop     dword ptr [rax+rax+00h]
0x18004ecbe  mov     esi, eax
0x18004ecc0  test    eax, eax
0x18004ecc2  jz      short loc_18004ED30
0x18004ecc4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004eccb  lea     r14, WPP_GLOBAL_Control
0x18004ecd2  cmp     rcx, r14
0x18004ecd5  jz      short loc_18004ECFC
0x18004ecd7  test    byte ptr [rcx+1Ch], 2
0x18004ecdb  jz      short loc_18004ECFC
0x18004ecdd  mov     rcx, [rcx+10h]
0x18004ece1  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004ece8  mov     edx, 17Bh
0x18004eced  mov     r9d, eax
0x18004ecf0  call    WPP_SF_d
0x18004ecf5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ecfc  or      esi, 80010000h
0x18004ed02  cmp     rcx, r14
0x18004ed05  jz      short loc_18004ED25
0x18004ed07  test    byte ptr [rcx+1Ch], 40h
0x18004ed0b  jz      short loc_18004ED25
0x18004ed0d  mov     rcx, [rcx+10h]
0x18004ed11  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004ed18  mov     edx, 17Ch
0x18004ed1d  mov     r9d, esi
0x18004ed20  call    WPP_SF_d
0x18004ed25  mov     dword ptr [rdi], 0
0x18004ed2b  jmp     loc_18004EDF1
0x18004ed30  xor     esi, esi
0x18004ed32  mov     eax, r15d
0x18004ed35  test    r15d, r15d
0x18004ed38  jz      loc_18004F224
0x18004ed3e  sub     eax, 1
0x18004ed41  jz      loc_18004F05F
0x18004ed47  sub     eax, 1
0x18004ed4a  jz      loc_18004EE45
0x18004ed50  cmp     eax, 1
0x18004ed53  jz      short loc_18004ED8D
0x18004ed55  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ed5c  lea     r14, WPP_GLOBAL_Control
0x18004ed63  cmp     rcx, r14
0x18004ed66  jz      short loc_18004ED86
0x18004ed68  test    byte ptr [rcx+1Ch], 2
0x18004ed6c  jz      short loc_18004ED86
0x18004ed6e  mov     rcx, [rcx+10h]
0x18004ed72  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004ed79  mov     edx, 18Ch
0x18004ed7e  mov     r9d, r15d
0x18004ed81  call    WPP_SF_d
0x18004ed86  mov     ebx, 80070032h
0x18004ed8b  jmp     short loc_18004EDE3
0x18004ed8d  lea     rax, ??_7?$_Func_impl_no_alloc@P6AJPEBXKAEAKPEA_N@ZJPEBXKAEAKPEA_N@std@@6B@; const std::_Func_impl_no_alloc<long (*)(void const *,ulong,ulong &,bool *),long,void const *,ulong,ulong &,bool *>::`vftable'
0x18004ed94  mov     [rbp+37h+var_90], rax
0x18004ed98  lea     rdx, [rbp+37h+var_90]
0x18004ed9c  lea     rax, ?BdeSvcNetworkStateChangeCallback@@YAJPEBXKAEAKPEA_N@Z; BdeSvcNetworkStateChangeCallback(void const *,ulong,ulong &,bool *)
0x18004eda3  mov     [rbp+37h+var_88], rax
0x18004eda7  lea     rcx, WNF_SEB_NETWORK_STATE_CHANGES
0x18004edae  lea     rax, [rbp+37h+var_90]
0x18004edb2  mov     [rbp+37h+var_58], rax
0x18004edb6  call    ?CreateWnfSubscription@WnfSubscriptions@@SAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AJPEBXKAEAKPEA_N@Z@std@@@Z; WnfSubscriptions::CreateWnfSubscription(_WNF_STATE_NAME const &,std::function<long (void const *,ulong,ulong &,bool *)> &&)
0x18004edbb  mov     rcx, [rbp+37h+var_58]
0x18004edbf  test    rcx, rcx
0x18004edc2  jz      short loc_18004EDDA
0x18004edc4  mov     rax, [rcx]
0x18004edc7  lea     rdx, [rbp+37h+var_90]
0x18004edcb  cmp     rcx, rdx
0x18004edce  setnz   dl
0x18004edd1  mov     rax, [rax+20h]
0x18004edd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004edda  xor     ebx, ebx
0x18004eddc  lea     r14, WPP_GLOBAL_Control
0x18004ede3  mov     [rdi], ebx
0x18004ede5  call    cs:__imp_RpcRevertToSelf
0x18004edec  nop     dword ptr [rax+rax+00h]
0x18004edf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004edf8  cmp     rcx, r14
0x18004edfb  jz      short loc_18004EE1B
0x18004edfd  test    byte ptr [rcx+1Ch], 20h
0x18004ee01  jz      short loc_18004EE1B
0x18004ee03  mov     rcx, [rcx+10h]
0x18004ee07  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004ee0e  mov     edx, 18Dh
0x18004ee13  mov     r9d, esi
0x18004ee16  call    WPP_SF_d
0x18004ee1b  mov     eax, esi
0x18004ee1d  mov     rcx, [rbp+37h+var_38]
0x18004ee21  xor     rcx, rsp; StackCookie
0x18004ee24  call    __security_check_cookie
0x18004ee29  mov     rbx, [rsp+0C0h+arg_0]
0x18004ee31  add     rsp, 90h
0x18004ee38  pop     r15
0x18004ee3a  pop     r14
0x18004ee3c  pop     r13
0x18004ee3e  pop     r12
0x18004ee40  pop     rdi
0x18004ee41  pop     rsi
0x18004ee42  pop     rbp
0x18004ee43  retn
0x18004ee45  xor     eax, eax
0x18004ee47  xorps   xmm0, xmm0
0x18004ee4a  mov     [rbp+37h+var_40], eax
0x18004ee4d  movups  [rbp+37h+var_50], xmm0
0x18004ee51  test    r13, r13
0x18004ee54  jnz     short loc_18004EE86
0x18004ee56  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ee5d  lea     r14, WPP_GLOBAL_Control
0x18004ee64  mov     ebx, 80070057h
0x18004ee69  cmp     rcx, r14
0x18004ee6c  jz      loc_18004EDE3
0x18004ee72  test    byte ptr [rcx+1Ch], 2
0x18004ee76  jz      loc_18004EDE3
0x18004ee7c  mov     edx, 184h
0x18004ee81  jmp     loc_18004F08F
0x18004ee86  mov     r9d, [rbp+37h+arg_20]
0x18004ee8a  mov     r12d, 14h
0x18004ee90  cmp     r9d, r12d
0x18004ee93  jnb     short loc_18004EEC5
0x18004ee95  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ee9c  lea     r14, WPP_GLOBAL_Control
0x18004eea3  mov     ebx, 80070057h
0x18004eea8  cmp     rcx, r14
0x18004eeab  jz      loc_18004EDE3
0x18004eeb1  test    byte ptr [rcx+1Ch], 2
0x18004eeb5  jz      loc_18004EDE3
0x18004eebb  mov     edx, 185h
0x18004eec0  jmp     loc_18004F122
0x18004eec5  cmp     [r13+8], eax
0x18004eec9  jge     short loc_18004EEFB
0x18004eecb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004eed2  lea     r14, WPP_GLOBAL_Control
0x18004eed9  mov     ebx, 80070057h
0x18004eede  cmp     rcx, r14
0x18004eee1  jz      loc_18004EDE3
0x18004eee7  test    byte ptr [rcx+1Ch], 2
0x18004eeeb  jz      loc_18004EDE3
0x18004eef1  mov     edx, 186h
0x18004eef6  jmp     loc_18004F08F
0x18004eefb  test    rbx, rbx
0x18004eefe  jnz     short loc_18004EF30
0x18004ef00  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ef07  lea     r14, WPP_GLOBAL_Control
0x18004ef0e  mov     ebx, 80004003h
0x18004ef13  cmp     rcx, r14
0x18004ef16  jz      loc_18004EDE3
0x18004ef1c  test    byte ptr [rcx+1Ch], 2
0x18004ef20  jz      loc_18004EDE3
0x18004ef26  mov     edx, 187h
0x18004ef2b  jmp     loc_18004F08F
0x18004ef30  mov     r9d, [rbp+37h+arg_30]
0x18004ef34  cmp     r9d, r12d
0x18004ef37  jnb     short loc_18004EF71
0x18004ef39  test    r14, r14
0x18004ef3c  jz      short loc_18004EF41
0x18004ef3e  mov     [r14], r12d
0x18004ef41  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ef48  lea     r14, WPP_GLOBAL_Control
0x18004ef4f  mov     ebx, 8007007Ah
0x18004ef54  cmp     rcx, r14
0x18004ef57  jz      loc_18004EDE3
0x18004ef5d  test    byte ptr [rcx+1Ch], 2
0x18004ef61  jz      loc_18004EDE3
0x18004ef67  mov     edx, 188h
0x18004ef6c  jmp     loc_18004F122
0x18004ef71  call    cs:__imp_RpcRevertToSelf
0x18004ef78  nop     dword ptr [rax+rax+00h]
0x18004ef7d  mov     r15d, eax
0x18004ef80  test    eax, eax
0x18004ef82  jz      short loc_18004EFE2
0x18004ef84  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ef8b  lea     r14, WPP_GLOBAL_Control
0x18004ef92  cmp     rcx, r14
0x18004ef95  jz      short loc_18004EFBC
0x18004ef97  test    byte ptr [rcx+1Ch], 2
0x18004ef9b  jz      short loc_18004EFBC
0x18004ef9d  mov     rcx, [rcx+10h]
0x18004efa1  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004efa8  mov     edx, 189h
0x18004efad  mov     r9d, eax
0x18004efb0  call    WPP_SF_d
0x18004efb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004efbc  mov     esi, r15d
0x18004efbf  or      esi, 80010000h
0x18004efc5  cmp     rcx, r14
0x18004efc8  jz      loc_18004F1B2
0x18004efce  test    byte ptr [rcx+1Ch], 40h
0x18004efd2  jz      loc_18004F1B2
0x18004efd8  mov     edx, 18Ah
0x18004efdd  jmp     loc_18004F19F
0x18004efe2  movups  xmm0, xmmword ptr [r13+0]
0x18004efe7  mov     eax, [r13+10h]
0x18004efeb  lea     rcx, [rbp+37h+var_50]
0x18004efef  mov     [rbp+37h+var_40], eax
0x18004eff2  movups  [rbp+37h+var_50], xmm0
0x18004eff6  call    cs:__imp_FveQueryDeviceEncryptionSupport
0x18004effd  nop     dword ptr [rax+rax+00h]
0x18004f002  mov     r15d, eax
0x18004f005  test    eax, eax
0x18004f007  jns     short loc_18004F042
0x18004f009  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f010  lea     r14, WPP_GLOBAL_Control
0x18004f017  cmp     rcx, r14
0x18004f01a  jz      short loc_18004F03A
0x18004f01c  test    byte ptr [rcx+1Ch], 2
0x18004f020  jz      short loc_18004F03A
0x18004f022  mov     rcx, [rcx+10h]
0x18004f026  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004f02d  mov     edx, 18Bh
0x18004f032  mov     r9d, eax
0x18004f035  call    WPP_SF_d
0x18004f03a  mov     [rdi], r15d
0x18004f03d  jmp     loc_18004EDF1
0x18004f042  mov     eax, [rbp+37h+var_40]
0x18004f045  movups  xmm0, [rbp+37h+var_50]
0x18004f049  movups  xmmword ptr [rbx], xmm0
0x18004f04c  mov     [rbx+10h], eax
0x18004f04f  test    r14, r14
0x18004f052  jz      short loc_18004F057
0x18004f054  mov     [r14], r12d
0x18004f057  mov     [rdi], r15d
0x18004f05a  jmp     loc_18004F218
0x18004f05f  test    rbx, rbx
0x18004f062  jnz     short loc_18004F0A7
0x18004f064  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f06b  lea     r14, WPP_GLOBAL_Control
0x18004f072  mov     ebx, 80004003h
0x18004f077  cmp     rcx, r14
0x18004f07a  jz      loc_18004EDE3
0x18004f080  test    byte ptr [rcx+1Ch], 2
0x18004f084  jz      loc_18004EDE3
0x18004f08a  mov     edx, 17Eh
0x18004f08f  mov     r9d, ebx
0x18004f092  mov     rcx, [rcx+10h]
0x18004f096  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004f09d  call    WPP_SF_d
0x18004f0a2  jmp     loc_18004EDE3
0x18004f0a7  mov     rax, rbx
0x18004f0aa  and     rax, 0FFFFFFFFFFFFFFFCh
0x18004f0ae  cmp     rax, rbx
0x18004f0b1  jz      short loc_18004F0E0
0x18004f0b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f0ba  lea     r14, WPP_GLOBAL_Control
0x18004f0c1  mov     ebx, 80004003h
0x18004f0c6  cmp     rcx, r14
0x18004f0c9  jz      loc_18004EDE3
0x18004f0cf  test    byte ptr [rcx+1Ch], 2
0x18004f0d3  jz      loc_18004EDE3
0x18004f0d9  mov     edx, 17Fh
0x18004f0de  jmp     short loc_18004F08F
0x18004f0e0  mov     r9d, [rbp+37h+arg_30]
0x18004f0e4  mov     r12d, 4
0x18004f0ea  cmp     r9d, r12d
0x18004f0ed  jnb     short loc_18004F13B
0x18004f0ef  test    r14, r14
0x18004f0f2  jz      short loc_18004F0F7
0x18004f0f4  mov     [r14], r12d
0x18004f0f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f0fe  lea     r14, WPP_GLOBAL_Control
0x18004f105  mov     ebx, 8007007Ah
0x18004f10a  cmp     rcx, r14
0x18004f10d  jz      loc_18004EDE3
0x18004f113  test    byte ptr [rcx+1Ch], 2
0x18004f117  jz      loc_18004EDE3
0x18004f11d  mov     edx, 180h
0x18004f122  mov     rcx, [rcx+10h]
0x18004f126  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004f12d  mov     [rsp+0C0h+var_A0], ebx
0x18004f131  call    WPP_SF_DD
0x18004f136  jmp     loc_18004EDE3
0x18004f13b  call    cs:__imp_RpcRevertToSelf
  ... truncated ...
```
