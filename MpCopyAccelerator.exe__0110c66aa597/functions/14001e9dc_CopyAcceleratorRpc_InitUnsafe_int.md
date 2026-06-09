# CopyAcceleratorRpc::InitUnsafe(int)

- ea: `0x14001e9dc`
- end: `0x14001eedf`
- name: `?InitUnsafe@CopyAcceleratorRpc@@AEAAJH@Z`
- size: `1283`
- prototype: `__int64 __fastcall(CopyAcceleratorRpc *__hidden this, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14001d700`

## callees

- `0x140001440`
- `0x140004054`
- `0x14000405c`
- `0x140005c20`
- `0x14001d9e0`
- `0x14001da4c`
- `0x14001da70`
- `0x14001dac4`
- `0x14001e9dc`
- `0x140020220`
- `0x140024148`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x14001ea2f`
- `KERNEL32!DebugBreak` at `0x14001ea2f`
- `RPCRT4!RpcServerInqBindings` at `0x14001eaf8`
- `RPCRT4!RpcServerInqBindings` at `0x14001eaf8`
- `RPCRT4!RpcEpRegisterW` at `0x14001eb40`
- `RPCRT4!RpcEpRegisterW` at `0x14001eb40`
- `RPCRT4!RpcServerRegisterIf3` at `0x14001ec42`
- `RPCRT4!RpcServerRegisterIf3` at `0x14001ec42`
- `RPCRT4!RpcServerUseProtseqW` at `0x14001eab1`
- `RPCRT4!RpcServerUseProtseqW` at `0x14001eab1`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x14001ebf9`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x14001ebf9`
- `RPCRT4!RpcBindingVectorFree` at `0x14001ec87`
- `RPCRT4!RpcBindingVectorFree` at `0x14001ec87`

## string_xrefs

- `0x14001ea17`: `MpService_InternalInitServiceRpcDebug`
- `0x14001ea7c`: `MpService_SkipUseEndpointMapper`

## pseudocode

```c
__int64 __fastcall CopyAcceleratorRpc::InitUnsafe(CopyAcceleratorRpc *this, int a2)
{
  int v4; // r12d
  int v5; // r13d
  RPC_STATUS v7; // eax
  RPC_STATUS v8; // eax
  RPC_STATUS v9; // eax
  _QWORD *v10; // rcx
  unsigned __int64 i; // r15
  _QWORD *v12; // rcx
  RPC_STATUS v13; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  struct _RTL_CRITICAL_SECTION *v16; // rsi
  int *v17; // rax
  bool v18; // zf
  unsigned int v19; // r15d
  int v20; // [rsp+C0h] [rbp-80h] BYREF
  int v21; // [rsp+C4h] [rbp-7Ch] BYREF
  unsigned int v22; // [rsp+C8h] [rbp-78h] BYREF
  int v23; // [rsp+CCh] [rbp-74h] BYREF
  int v24; // [rsp+D0h] [rbp-70h] BYREF
  int v25; // [rsp+D4h] [rbp-6Ch] BYREF
  int v26; // [rsp+D8h] [rbp-68h] BYREF
  int v27; // [rsp+DCh] [rbp-64h] BYREF
  int v28; // [rsp+E0h] [rbp-60h] BYREF
  int v29; // [rsp+E4h] [rbp-5Ch] BYREF
  int v30; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v31; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v32; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v33; // [rsp+100h] [rbp-40h] BYREF
  __int64 v34; // [rsp+108h] [rbp-38h] BYREF
  __int64 v35; // [rsp+110h] [rbp-30h] BYREF
  __int64 v36; // [rsp+118h] [rbp-28h] BYREF
  __int64 v37; // [rsp+120h] [rbp-20h] BYREF
  __int64 v38; // [rsp+128h] [rbp-18h] BYREF
  RPC_BINDING_VECTOR *BindingVector; // [rsp+130h] [rbp-10h] BYREF

  BindingVector = 0;
  v4 = 0;
  v5 = 0;
  if ( (unsigned int)MpLookupMiscConfigFlag(L"MpService_InternalInitServiceRpcDebug") )
    DebugBreak();
  dword_14003DB98 = a2;
  if ( _InterlockedExchange((volatile __int32 *)this + 8, 1) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids);
    return 0;
  }
  if ( !(unsigned int)MpLookupMiscConfigFlag(L"MpService_SkipUseEndpointMapper") )
  {
    v7 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0x4D2u, *((void **)this + 1));
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids,
          v7 | 0x80010000);
      goto LABEL_26;
    }
    v8 = RpcServerInqBindings(&BindingVector);
    if ( v8 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids,
        v8 | 0x80010000);
    v9 = RpcEpRegisterW(qword_140035250, BindingVector, 0, 0);
    if ( v9 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
LABEL_25:
        v4 = 1;
        goto LABEL_26;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_22:
        if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 )
          WPP_SF_(v10[2], 21, &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids);
        goto LABEL_25;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids,
        v9 | 0x80010000);
    }
    v10 = WPP_GLOBAL_Control;
    goto LABEL_22;
  }
LABEL_26:
  for ( i = 0; ; ++i )
  {
    v13 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0x4D2u, *(RPC_WSTR *)this, *((void **)this + 1));
    if ( !v13 )
    {
      v5 = 1;
      goto LABEL_35;
    }
    if ( v13 != 1740 )
      break;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids,
        *(_QWORD *)this);
      v12 = WPP_GLOBAL_Control;
    }
    if ( i > 0x14 )
    {
      if ( !v4 )
        goto LABEL_55;
LABEL_35:
      v14 = RpcServerRegisterIf3(
              qword_140035250,
              0,
              0,
              41,
              1234,
              -1,
              IMpCopyAcceleratorSecurityCallback,
              *((_QWORD *)this + 1));
      v15 = 0;
      if ( v14 )
      {
        v15 = v14 | 0x80010000;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids, v15);
      }
      goto LABEL_39;
    }
  }
  v12 = WPP_GLOBAL_Control;
LABEL_55:
  v19 = v13 != 0 ? v13 | 0x80010000 : 0;
  v15 = v19;
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
    WPP_SF_Sd(v12[2], 23, (unsigned int)&WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids, *(_QWORD *)this, v19);
LABEL_39:
  if ( BindingVector )
    RpcBindingVectorFree(&BindingVector);
  if ( (v15 & 0x80000000) != 0 )
  {
    MpCmdLogPrintf(L"Initializing RPC server failed, hr=%#lx\n", v15);
    _InterlockedExchange((volatile __int32 *)this + 8, 0);
  }
  v16 = g_pcsAsimovLock;
  if ( g_pcsAsimovLock )
  {
    CommonUtil::CMpCriticalSection::lock(g_pcsAsimovLock);
    if ( **(_DWORD **)&g_hMpAsimovProvider > 5u
      && (*(_QWORD *)(*(_QWORD *)&g_hMpAsimovProvider + 16LL) & 0x400000000000LL) != 0
      && (*(_QWORD *)(*(_QWORD *)&g_hMpAsimovProvider + 24LL) & 0x400000000000LL) == *(_QWORD *)(*(_QWORD *)&g_hMpAsimovProvider
                                                                                               + 24LL) )
    {
      v17 = &dword_140033A5C;
      v18 = *(_QWORD *)this == 0;
      v20 = v5;
      if ( !v18 )
        v17 = *(int **)this;
      v31 = (__int64)v17;
      v23 = *((_DWORD *)g_aAsimov + 18);
      v24 = *((_DWORD *)g_aAsimov + 17);
      v25 = *((_DWORD *)g_aAsimov + 16);
      v26 = *((unsigned __int8 *)g_aAsimov + 60);
      v27 = *((unsigned __int8 *)g_aAsimov + 59);
      v28 = *((unsigned __int8 *)g_aAsimov + 58);
      v29 = *((unsigned __int8 *)g_aAsimov + 57);
      v30 = *((unsigned __int8 *)g_aAsimov + 56);
      v32 = *((_QWORD *)g_aAsimov + 6);
      v33 = *((_QWORD *)g_aAsimov + 5);
      v34 = *((_QWORD *)g_aAsimov + 4);
      v35 = *((_QWORD *)g_aAsimov + 3);
      v36 = *((_QWORD *)g_aAsimov + 2);
      v37 = *((_QWORD *)g_aAsimov + 1);
      v21 = v4;
      v22 = v15;
      v38 = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        g_hMpAsimovProvider,
        (int)&byte_1400362F1,
        (__int64)&v38,
        (__int64)&v37,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v31,
        (__int64)&v21,
        (__int64)&v20);
    }
    CommonUtil::CMpCriticalSection::unlock(v16);
  }
  return v15;
}

```

## disassembly

```asm
0x14001e9dc  mov     [rsp-28h+arg_8], rbx
0x14001e9e1  mov     [rsp-28h+arg_10], rsi
0x14001e9e6  mov     [rsp-28h+arg_18], rdi
0x14001e9eb  push    rbp
0x14001e9ec  push    r12
0x14001e9ee  push    r13
0x14001e9f0  push    r14
0x14001e9f2  push    r15
0x14001e9f4  mov     rbp, rsp
0x14001e9f7  sub     rsp, 140h
0x14001e9fe  mov     rax, cs:__security_cookie
0x14001ea05  xor     rax, rsp
0x14001ea08  mov     [rbp+var_8], rax
0x14001ea0c  mov     rdi, rcx
0x14001ea0f  mov     [rbp+BindingVector], 0
0x14001ea17  lea     rcx, aMpserviceInter; "MpService_InternalInitServiceRpcDebug"
0x14001ea1e  mov     ebx, edx
0x14001ea20  xor     r12d, r12d
0x14001ea23  xor     r13d, r13d
0x14001ea26  call    MpLookupMiscConfigFlag
0x14001ea2b  test    eax, eax
0x14001ea2d  jz      short loc_14001EA35
0x14001ea2f  call    cs:__imp_DebugBreak
0x14001ea35  mov     eax, 1
0x14001ea3a  mov     cs:dword_14003DB98, ebx
0x14001ea40  xchg    eax, [rdi+20h]
0x14001ea43  test    eax, eax
0x14001ea45  jz      short loc_14001EA7C
0x14001ea47  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ea4e  lea     rsi, WPP_GLOBAL_Control
0x14001ea55  cmp     rcx, rsi
0x14001ea58  jz      short loc_14001EA75
0x14001ea5a  test    byte ptr [rcx+1Ch], 4
0x14001ea5e  jz      short loc_14001EA75
0x14001ea60  mov     rcx, [rcx+10h]
0x14001ea64  lea     r8, WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids
0x14001ea6b  mov     edx, 11h
0x14001ea70  call    WPP_SF_
0x14001ea75  xor     eax, eax
0x14001ea77  jmp     loc_14001EE5D
0x14001ea7c  lea     rcx, aMpserviceSkipu; "MpService_SkipUseEndpointMapper"
0x14001ea83  call    MpLookupMiscConfigFlag
0x14001ea88  lea     rsi, WPP_GLOBAL_Control
0x14001ea8f  mov     r15b, 2
0x14001ea92  lea     r14, WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids
0x14001ea99  test    eax, eax
0x14001ea9b  jnz     loc_14001EB9B
0x14001eaa1  mov     r8, [rdi+8]; SecurityDescriptor
0x14001eaa5  lea     rcx, aNcalrpc; "ncalrpc"
0x14001eaac  mov     edx, 4D2h; MaxCalls
0x14001eab1  call    cs:__imp_RpcServerUseProtseqW
0x14001eab7  test    eax, eax
0x14001eab9  jz      short loc_14001EAF4
0x14001eabb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eac2  cmp     rcx, rsi
0x14001eac5  jz      loc_14001EB9B
0x14001eacb  test    [rcx+1Ch], r15b
0x14001eacf  jz      loc_14001EB9B
0x14001ead5  mov     rcx, [rcx+10h]
0x14001ead9  mov     r9d, 80010000h
0x14001eadf  or      r9d, eax
0x14001eae2  mov     edx, 12h
0x14001eae7  mov     r8, r14
0x14001eaea  call    WPP_SF_d
0x14001eaef  jmp     loc_14001EB9B
0x14001eaf4  lea     rcx, [rbp+BindingVector]; BindingVector
0x14001eaf8  call    cs:__imp_RpcServerInqBindings
0x14001eafe  mov     ebx, 80010000h
0x14001eb03  test    eax, eax
0x14001eb05  jz      short loc_14001EB2F
0x14001eb07  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eb0e  cmp     rcx, rsi
0x14001eb11  jz      short loc_14001EB2F
0x14001eb13  test    [rcx+1Ch], r15b
0x14001eb17  jz      short loc_14001EB2F
0x14001eb19  mov     rcx, [rcx+10h]
0x14001eb1d  or      eax, ebx
0x14001eb1f  mov     r9d, eax
0x14001eb22  mov     edx, 13h
0x14001eb27  mov     r8, r14
0x14001eb2a  call    WPP_SF_d
0x14001eb2f  mov     rdx, [rbp+BindingVector]; BindingVector
0x14001eb33  lea     rcx, qword_140035250; IfSpec
0x14001eb3a  xor     r9d, r9d; Annotation
0x14001eb3d  xor     r8d, r8d; UuidVector
0x14001eb40  call    cs:__imp_RpcEpRegisterW
0x14001eb46  test    eax, eax
0x14001eb48  jz      short loc_14001EB72
0x14001eb4a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eb51  cmp     rcx, rsi
0x14001eb54  jz      short loc_14001EB95
0x14001eb56  test    [rcx+1Ch], r15b
0x14001eb5a  jz      short loc_14001EB79
0x14001eb5c  mov     rcx, [rcx+10h]
0x14001eb60  or      eax, ebx
0x14001eb62  mov     r9d, eax
0x14001eb65  mov     edx, 14h
0x14001eb6a  mov     r8, r14
0x14001eb6d  call    WPP_SF_d
0x14001eb72  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eb79  cmp     rcx, rsi
0x14001eb7c  jz      short loc_14001EB95
0x14001eb7e  test    [rcx+1Ch], r15b
0x14001eb82  jz      short loc_14001EB95
0x14001eb84  mov     rcx, [rcx+10h]
0x14001eb88  mov     edx, 15h
0x14001eb8d  mov     r8, r14
0x14001eb90  call    WPP_SF_
0x14001eb95  mov     r12d, 1
0x14001eb9b  xor     r15d, r15d
0x14001eb9e  jmp     short loc_14001EBE6
0x14001eba0  cmp     ebx, 6CCh
0x14001eba6  jnz     loc_14001EE95
0x14001ebac  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ebb3  cmp     rcx, rsi
0x14001ebb6  jz      short loc_14001EBD9
0x14001ebb8  test    byte ptr [rcx+1Ch], 2
0x14001ebbc  jz      short loc_14001EBD9
0x14001ebbe  mov     r9, [rdi]
0x14001ebc1  mov     edx, 16h
0x14001ebc6  mov     rcx, [rcx+10h]
0x14001ebca  mov     r8, r14
0x14001ebcd  call    WPP_SF_S
0x14001ebd2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ebd9  cmp     r15, 14h
0x14001ebdd  ja      loc_14001EE8A
0x14001ebe3  inc     r15
0x14001ebe6  mov     r9, [rdi+8]; SecurityDescriptor
0x14001ebea  lea     rcx, aNcalrpc; "ncalrpc"
0x14001ebf1  mov     r8, [rdi]; Endpoint
0x14001ebf4  mov     edx, 4D2h; MaxCalls
0x14001ebf9  call    cs:__imp_RpcServerUseProtseqEpW
0x14001ebff  mov     ebx, eax
0x14001ec01  test    eax, eax
0x14001ec03  jnz     short loc_14001EBA0
0x14001ec05  mov     r13d, 1
0x14001ec0b  mov     rax, [rdi+8]
0x14001ec0f  lea     rcx, qword_140035250
0x14001ec16  mov     [rsp+140h+var_108], rax
0x14001ec1b  mov     r9d, 29h ; ')'
0x14001ec21  lea     rax, IMpCopyAcceleratorSecurityCallback
0x14001ec28  xor     r8d, r8d
0x14001ec2b  mov     [rsp+140h+var_110], rax
0x14001ec30  xor     edx, edx
0x14001ec32  mov     dword ptr [rsp+140h+var_118], 0FFFFFFFFh
0x14001ec3a  mov     dword ptr [rsp+140h+var_120], 4D2h
0x14001ec42  call    cs:__imp_RpcServerRegisterIf3
0x14001ec48  xor     ebx, ebx
0x14001ec4a  test    eax, eax
0x14001ec4c  jz      short loc_14001EC7C
0x14001ec4e  mov     ebx, eax
0x14001ec50  or      ebx, 80010000h
0x14001ec56  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ec5d  cmp     rcx, rsi
0x14001ec60  jz      short loc_14001EC7C
0x14001ec62  test    byte ptr [rcx+1Ch], 1
0x14001ec66  jz      short loc_14001EC7C
0x14001ec68  mov     rcx, [rcx+10h]
0x14001ec6c  mov     edx, 18h
0x14001ec71  mov     r9d, ebx
0x14001ec74  mov     r8, r14
0x14001ec77  call    WPP_SF_d
0x14001ec7c  cmp     [rbp+BindingVector], 0
0x14001ec81  jz      short loc_14001EC8D
0x14001ec83  lea     rcx, [rbp+BindingVector]; BindingVector
0x14001ec87  call    cs:__imp_RpcBindingVectorFree
0x14001ec8d  test    ebx, ebx
0x14001ec8f  jns     short loc_14001ECA4
0x14001ec91  mov     edx, ebx
0x14001ec93  lea     rcx, aInitializingRp; "Initializing RPC server failed, hr=%#lx"...
0x14001ec9a  call    ?MpCmdLogPrintf@@YAXPEB_WZZ; MpCmdLogPrintf(wchar_t const *,...)
0x14001ec9f  xor     eax, eax
0x14001eca1  xchg    eax, [rdi+20h]
0x14001eca4  mov     rsi, cs:?g_pcsAsimovLock@@3PEAVCMpCriticalSection@CommonUtil@@EA; CommonUtil::CMpCriticalSection * g_pcsAsimovLock
0x14001ecab  test    rsi, rsi
0x14001ecae  jz      loc_14001EE5B
0x14001ecb4  mov     rcx, rsi; lpCriticalSection
0x14001ecb7  call    ?lock@CMpCriticalSection@CommonUtil@@QEBAXXZ; CommonUtil::CMpCriticalSection::lock(void)
0x14001ecbc  mov     r8, cs:g_hMpAsimovProvider
0x14001ecc3  cmp     dword ptr [r8], 5
0x14001ecc7  jbe     loc_14001EE53
0x14001eccd  mov     rcx, 400000000000h
0x14001ecd7  test    [r8+10h], rcx
0x14001ecdb  jz      loc_14001EE53
0x14001ece1  mov     rax, [r8+18h]
0x14001ece5  and     rax, rcx
0x14001ece8  cmp     rax, [r8+18h]
0x14001ecec  jnz     loc_14001EE53
0x14001ecf2  mov     rcx, cs:?g_aAsimov@@3PEAVCMpAsimov@@EA; CMpAsimov * g_aAsimov
0x14001ecf9  lea     rax, dword_140033A5C
0x14001ed00  cmp     qword ptr [rdi], 0
0x14001ed04  lea     rdx, byte_1400362F1; int
0x14001ed0b  mov     dword ptr [rbp+var_80], r13d
0x14001ed0f  cmovnz  rax, [rdi]
0x14001ed13  mov     [rbp+var_50], rax
0x14001ed17  mov     eax, [rcx+48h]
0x14001ed1a  mov     dword ptr [rbp+var_78+4], eax
0x14001ed1d  mov     eax, [rcx+44h]
0x14001ed20  mov     [rbp+var_70], eax
0x14001ed23  mov     eax, [rcx+40h]
0x14001ed26  mov     [rbp+var_6C], eax
0x14001ed29  movzx   eax, byte ptr [rcx+3Ch]
0x14001ed2d  mov     [rbp+var_68], eax
0x14001ed30  movzx   eax, byte ptr [rcx+3Bh]
0x14001ed34  mov     [rbp+var_64], eax
0x14001ed37  movzx   eax, byte ptr [rcx+3Ah]
0x14001ed3b  mov     [rbp+var_60], eax
0x14001ed3e  movzx   eax, byte ptr [rcx+39h]
0x14001ed42  mov     [rbp+var_5C], eax
0x14001ed45  movzx   eax, byte ptr [rcx+38h]
0x14001ed49  mov     [rbp+var_58], eax
0x14001ed4c  mov     rax, [rcx+30h]
0x14001ed50  mov     [rbp+var_48], rax
0x14001ed54  mov     rax, [rcx+28h]
0x14001ed58  mov     [rbp+var_40], rax
0x14001ed5c  mov     rax, [rcx+20h]
0x14001ed60  mov     [rbp+var_38], rax
0x14001ed64  mov     rax, [rcx+18h]
0x14001ed68  mov     [rbp+var_30], rax
0x14001ed6c  mov     rax, [rcx+10h]
0x14001ed70  mov     [rbp+var_28], rax
0x14001ed74  mov     rax, [rcx+8]
0x14001ed78  mov     rcx, r8; int
0x14001ed7b  mov     [rbp+var_20], rax
0x14001ed7f  lea     rax, [rbp+var_80]
0x14001ed83  mov     [rsp+140h+var_90], rax; __int64
0x14001ed8b  lea     rax, [rbp+var_80+4]
0x14001ed8f  mov     [rsp+140h+var_98], rax; __int64
0x14001ed97  lea     rax, [rbp+var_50]
0x14001ed9b  mov     [rsp+140h+var_A0], rax; __int64
0x14001eda3  lea     rax, [rbp+var_78]
0x14001eda7  mov     [rsp+140h+var_A8], rax; __int64
0x14001edaf  lea     rax, [rbp+var_78+4]
0x14001edb3  mov     [rsp+140h+var_B0], rax; __int64
0x14001edbb  lea     rax, [rbp+var_70]
0x14001edbf  mov     [rsp+140h+var_B8], rax; __int64
0x14001edc7  lea     rax, [rbp+var_6C]
0x14001edcb  mov     [rsp+140h+var_C0], rax; __int64
0x14001edd3  lea     rax, [rbp+var_68]
0x14001edd7  mov     [rsp+140h+var_C8], rax; __int64
0x14001eddc  lea     rax, [rbp+var_64]
0x14001ede0  mov     [rsp+140h+var_D0], rax; __int64
0x14001ede5  lea     rax, [rbp+var_60]
0x14001ede9  mov     [rsp+140h+var_D8], rax; __int64
0x14001edee  lea     rax, [rbp+var_5C]
0x14001edf2  mov     [rsp+140h+var_E0], rax; __int64
0x14001edf7  lea     rax, [rbp+var_58]
0x14001edfb  mov     [rsp+140h+var_E8], rax; __int64
0x14001ee00  lea     rax, [rbp+var_48]
0x14001ee04  mov     [rsp+140h+var_F0], rax; __int64
0x14001ee09  lea     rax, [rbp+var_40]
0x14001ee0d  mov     [rsp+140h+var_F8], rax; __int64
0x14001ee12  lea     rax, [rbp+var_38]
0x14001ee16  mov     [rsp+140h+var_100], rax; __int64
0x14001ee1b  lea     rax, [rbp+var_30]
0x14001ee1f  mov     [rsp+140h+var_108], rax; __int64
0x14001ee24  lea     rax, [rbp+var_28]
0x14001ee28  mov     [rsp+140h+var_110], rax; __int64
0x14001ee2d  lea     rax, [rbp+var_20]
0x14001ee31  mov     [rsp+140h+var_118], rax; __int64
0x14001ee36  lea     rax, [rbp+var_18]
0x14001ee3a  mov     [rsp+140h+var_120], rax; __int64
0x14001ee3f  mov     dword ptr [rbp+var_80+4], r12d
0x14001ee43  mov     dword ptr [rbp+var_78], ebx
0x14001ee46  mov     [rbp+var_18], 2000000h
0x14001ee4e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@_W@@U2@U2@U2@U2@U2@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U3@U3@U3@U3@U2@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@_W@@44444AEBU?$_tlgWrapperByVal@$03@@55555555455@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14001ee53  mov     rcx, rsi; lpCriticalSection
0x14001ee56  call    ?unlock@CMpCriticalSection@CommonUtil@@QEBAXXZ; CommonUtil::CMpCriticalSection::unlock(void)
0x14001ee5b  mov     eax, ebx
0x14001ee5d  mov     rcx, [rbp+var_8]
0x14001ee61  xor     rcx, rsp; StackCookie
0x14001ee64  call    __security_check_cookie
0x14001ee69  lea     r11, [rsp+140h+var_s0]
0x14001ee71  mov     rbx, [r11+38h]
0x14001ee75  mov     rsi, [r11+40h]
0x14001ee79  mov     rdi, [r11+48h]
0x14001ee7d  mov     rsp, r11
0x14001ee80  pop     r15
0x14001ee82  pop     r14
0x14001ee84  pop     r13
0x14001ee86  pop     r12
0x14001ee88  pop     rbp
0x14001ee89  retn
0x14001ee8a  test    r12d, r12d
0x14001ee8d  jnz     loc_14001EC0B
0x14001ee93  jmp     short loc_14001EE9C
0x14001ee95  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ee9c  mov     eax, ebx
0x14001ee9e  or      eax, 80010000h
0x14001eea3  neg     ebx
0x14001eea5  sbb     r15d, r15d
0x14001eea8  and     r15d, eax
0x14001eeab  mov     ebx, r15d
0x14001eeae  cmp     rcx, rsi
0x14001eeb1  jz      loc_14001EC7C
0x14001eeb7  test    byte ptr [rcx+1Ch], 1
0x14001eebb  jz      loc_14001EC7C
0x14001eec1  mov     r9, [rdi]
0x14001eec4  mov     edx, 17h
0x14001eec9  mov     rcx, [rcx+10h]
  ... truncated ...
```
