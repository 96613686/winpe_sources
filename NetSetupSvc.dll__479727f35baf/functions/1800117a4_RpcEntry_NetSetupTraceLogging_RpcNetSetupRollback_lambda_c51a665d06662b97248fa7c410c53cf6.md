# RpcEntry_NetSetupTraceLogging::RpcNetSetupRollback__lambda_c51a665d06662b97248fa7c410c53cf6___

- ea: `0x1800117a4`
- end: `0x180011931`
- name: `RpcEntry_NetSetupTraceLogging::RpcNetSetupRollback__lambda_c51a665d06662b97248fa7c410c53cf6___`
- size: `397`
- prototype: `__int64 __fastcall(NETSETUP_RPC_CONTEXT *this)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update`

## callers

- `0x180010bb0`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x1800078d0`
- `0x180008854`
- `0x18000d8ec`
- `0x18001023c`
- `0x1800117a4`
- `0x180011e70`
- `0x1800120c0`
- `0x18001251c`
- `0x180013084`
- `0x1800139fc`
- `0x180014a40`
- `0x180014dd4`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800118b8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800118b8`

## string_xrefs

- `0x1800117f3`: `RpcNetSetupRollback`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
BOOL __fastcall RpcEntry_NetSetupTraceLogging::RpcNetSetupRollback__lambda_c51a665d06662b97248fa7c410c53cf6___(
        __int64 **this,
        __int64 a2)
{
  const struct _GUID *Id; // rbx
  __int64 v4; // r8
  __int64 *v5; // rdx
  __int64 v6; // r8
  std::_Ref_count_base *v7; // rbx
  _BYTE v9[24]; // [rsp+28h] [rbp-E0h] BYREF
  _BYTE pExceptionObject[208]; // [rsp+40h] [rbp-C8h] BYREF
  struct _GUID v11; // [rsp+110h] [rbp+8h] BYREF
  _QWORD v12[42]; // [rsp+128h] [rbp+20h] BYREF
  __int64 v13; // [rsp+2A0h] [rbp+198h] BYREF

  v13 = a2;
  StashPidInTls::StashPidInTls((StashPidInTls *)v9, (struct NETSETUP_RPC_CONTEXT *)this);
  Id = NETSETUP_RPC_CONTEXT::GetId((NETSETUP_RPC_CONTEXT *)this, &v11);
  wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v12,
    (__int64)"RpcNetSetupRollback");
  v12[0] = &NetSetupTraceLogging::RpcNetSetupRollback::`vftable';
  NetSetupTraceLogging::RpcNetSetupRollback::StartActivity((NetSetupTraceLogging::RpcNetSetupRollback *)v12, Id);
  *(_OWORD *)&v9[8] = 0;
  v5 = this[1];
  if ( v5 )
  {
    lambda_c51a665d06662b97248fa7c410c53cf6_::operator()((__int64)&v13, *v5, v4);
  }
  else
  {
    std::weak_ptr<NetSetupSvcTxHolder>::lock(this + 3, &v11);
    if ( !*(_QWORD *)&v11.Data1 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_d7c9c24d725337bc8e6af9dd6d1b553a_Traceguids);
      HResultException::HResultException((HResultException *)pExceptionObject, -2147018081);
      throw (HResultException *)pExceptionObject;
    }
    lambda_c51a665d06662b97248fa7c410c53cf6_::operator()((__int64)&v13, **(_QWORD **)&v11.Data1, v6);
    v7 = *(std::_Ref_count_base **)v11.Data4;
    if ( *(_QWORD *)v11.Data4
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)v11.Data4 + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(std::_Ref_count_base *))v7)(v7);
      std::_Ref_count_base::_Decwref(v7);
    }
  }
  wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v12);
  NetSetupTraceLogging::RpcNetSetupRollback::~RpcNetSetupRollback((NetSetupTraceLogging::RpcNetSetupRollback *)v12);
  return TlsSetValue(*((_DWORD *)g_NetSetupService + 91), 0);
}

```

## disassembly

```asm
0x1800117a4  mov     rax, rsp
0x1800117a7  mov     [rax+18h], rbx
0x1800117ab  mov     [rax+20h], rdi
0x1800117af  mov     [rax+10h], rdx
0x1800117b3  push    rbp
0x1800117b4  lea     rbp, [rax-188h]
0x1800117bb  sub     rsp, 280h
0x1800117c2  mov     rax, cs:__security_cookie
0x1800117c9  xor     rax, rsp
0x1800117cc  mov     [rbp+180h+var_10], rax
0x1800117d3  mov     rdi, rcx
0x1800117d6  mov     rdx, rcx; struct NETSETUP_RPC_CONTEXT *
0x1800117d9  lea     rcx, [rsp+280h+var_260]; this
0x1800117de  call    ??0StashPidInTls@@QEAA@PEAUNETSETUP_RPC_CONTEXT@@@Z; StashPidInTls::StashPidInTls(NETSETUP_RPC_CONTEXT *)
0x1800117e3  nop
0x1800117e4  lea     rdx, [rbp+180h+var_178]; retstr
0x1800117e8  mov     rcx, rdi; this
0x1800117eb  call    ?GetId@NETSETUP_RPC_CONTEXT@@QEAA?AU_GUID@@XZ; NETSETUP_RPC_CONTEXT::GetId(void)
0x1800117f0  mov     rbx, rax
0x1800117f3  lea     rdx, aRpcnetsetuprol; "RpcNetSetupRollback"
0x1800117fa  lea     rcx, [rbp+180h+var_160]
0x1800117fe  call    ??0?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180011803  lea     rax, ??_7RpcNetSetupRollback@NetSetupTraceLogging@@6B@; const NetSetupTraceLogging::RpcNetSetupRollback::`vftable'
0x18001180a  mov     [rbp+180h+var_160], rax
0x18001180e  mov     rdx, rbx; struct _GUID *
0x180011811  lea     rcx, [rbp+180h+var_160]; this
0x180011815  call    ?StartActivity@RpcNetSetupRollback@NetSetupTraceLogging@@QEAAXAEBU_GUID@@@Z; NetSetupTraceLogging::RpcNetSetupRollback::StartActivity(_GUID const &)
0x18001181a  nop
0x18001181b  xorps   xmm0, xmm0
0x18001181e  movdqu  [rsp+280h+var_260+8], xmm0
0x180011824  mov     rdx, [rdi+8]
0x180011828  test    rdx, rdx
0x18001182b  jz      short loc_18001183E
0x18001182d  mov     rdx, [rdx]
0x180011830  lea     rcx, [rbp+180h+arg_8]
0x180011837  call    _lambda_c51a665d06662b97248fa7c410c53cf6___operator__
0x18001183c  jmp     short loc_180011895
0x18001183e  lea     rcx, [rdi+18h]
0x180011842  lea     rdx, [rbp+180h+var_178]
0x180011846  call    ?lock@?$weak_ptr@UNetSetupSvcTxHolder@@@std@@QEBA?AV?$shared_ptr@UNetSetupSvcTxHolder@@@2@XZ; std::weak_ptr<NetSetupSvcTxHolder>::lock(void)
0x18001184b  nop
0x18001184c  mov     rdx, qword ptr [rbp+180h+var_178.Data1]
0x180011850  test    rdx, rdx
0x180011853  jz      loc_1800118E2
0x180011859  mov     rdx, [rdx]
0x18001185c  lea     rcx, [rbp+180h+arg_8]
0x180011863  call    _lambda_c51a665d06662b97248fa7c410c53cf6___operator__
0x180011868  nop
0x180011869  mov     rbx, qword ptr [rbp+180h+var_178.Data4]
0x18001186d  test    rbx, rbx
0x180011870  jz      short loc_180011895
0x180011872  or      eax, 0FFFFFFFFh
0x180011875  lock xadd [rbx+8], eax
0x18001187a  cmp     eax, 1
0x18001187d  jnz     short loc_180011895
0x18001187f  mov     rax, [rbx]
0x180011882  mov     rcx, rbx
0x180011885  mov     rax, [rax]
0x180011888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001188d  mov     rcx, rbx; this
0x180011890  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180011895  lea     rcx, [rbp+180h+var_160]
0x180011899  call    ?Stop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001189e  nop
0x18001189f  lea     rcx, [rbp+180h+var_160]; this
0x1800118a3  call    ??1RpcNetSetupRollback@NetSetupTraceLogging@@QEAA@XZ; NetSetupTraceLogging::RpcNetSetupRollback::~RpcNetSetupRollback(void)
0x1800118a8  nop
0x1800118a9  xor     edx, edx; lpTlsValue
0x1800118ab  mov     rcx, cs:?g_NetSetupService@@3PEAVNetSetupService@@EA; NetSetupService * g_NetSetupService
0x1800118b2  mov     ecx, [rcx+16Ch]; dwTlsIndex
0x1800118b8  call    cs:__imp_TlsSetValue
0x1800118be  mov     rcx, [rbp+180h+var_10]
0x1800118c5  xor     rcx, rsp; StackCookie
0x1800118c8  call    __security_check_cookie
0x1800118cd  lea     r11, [rsp+280h+var_s0]
0x1800118d5  mov     rbx, [r11+20h]
0x1800118d9  mov     rdi, [r11+28h]
0x1800118dd  mov     rsp, r11
0x1800118e0  pop     rbp
0x1800118e1  retn
0x1800118e2  lea     rax, WPP_GLOBAL_Control
0x1800118e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800118f0  cmp     rcx, rax
0x1800118f3  jz      short loc_180011910
0x1800118f5  cmp     byte ptr [rcx+19h], 2
0x1800118f9  jb      short loc_180011910
0x1800118fb  mov     edx, 11h
0x180011900  lea     r8, WPP_d7c9c24d725337bc8e6af9dd6d1b553a_Traceguids
0x180011907  mov     rcx, [rcx+10h]
0x18001190b  call    WPP_SF_
0x180011910  mov     edx, 80071A9Fh; int
0x180011915  lea     rcx, [rsp+280h+pExceptionObject]; this
0x18001191a  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18001191f  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180011926  lea     rcx, [rsp+280h+pExceptionObject]; pExceptionObject
0x18001192b  call    _CxxThrowException_0
```
