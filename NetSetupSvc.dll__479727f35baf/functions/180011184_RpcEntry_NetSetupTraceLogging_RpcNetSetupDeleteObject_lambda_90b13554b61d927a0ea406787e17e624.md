# RpcEntry_NetSetupTraceLogging::RpcNetSetupDeleteObject__lambda_90b13554b61d927a0ea406787e17e624___

- ea: `0x180011184`
- end: `0x180011303`
- name: `RpcEntry_NetSetupTraceLogging::RpcNetSetupDeleteObject__lambda_90b13554b61d927a0ea406787e17e624___`
- size: `383`
- prototype: `BOOL __fastcall(NetSetup2::Exception ***this, unsigned int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update`

## callers

- `0x180010930`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x1800078d0`
- `0x180008854`
- `0x18000d8ec`
- `0x18001023c`
- `0x180011184`
- `0x180011e70`
- `0x1800120c0`
- `0x180012440`
- `0x180012cc8`
- `0x1800139fc`
- `0x180014658`
- `0x180014dd4`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001128c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001128c`

## string_xrefs

- `0x1800111cf`: `RpcNetSetupDeleteObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
BOOL __fastcall RpcEntry_NetSetupTraceLogging::RpcNetSetupDeleteObject__lambda_90b13554b61d927a0ea406787e17e624___(
        NetSetup2::Exception ***this,
        unsigned int *a2)
{
  const struct _GUID *Id; // rbx
  NetSetup2::Exception **v5; // rdx
  std::_Ref_count_base *v6; // rbx
  _BYTE v8[8]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v9; // [rsp+28h] [rbp-D8h]
  _BYTE pExceptionObject[208]; // [rsp+38h] [rbp-C8h] BYREF
  struct _GUID v11; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v12[42]; // [rsp+120h] [rbp+20h] BYREF

  StashPidInTls::StashPidInTls((StashPidInTls *)v8, (struct NETSETUP_RPC_CONTEXT *)this);
  Id = NETSETUP_RPC_CONTEXT::GetId((NETSETUP_RPC_CONTEXT *)this, &v11);
  wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v12,
    "RpcNetSetupDeleteObject");
  v12[0] = &NetSetupTraceLogging::RpcNetSetupDeleteObject::`vftable';
  NetSetupTraceLogging::RpcNetSetupDeleteObject::StartActivity((NetSetupTraceLogging::RpcNetSetupDeleteObject *)v12, Id);
  v9 = 0;
  v5 = this[1];
  if ( v5 )
  {
    lambda_90b13554b61d927a0ea406787e17e624_::operator()(a2, *v5);
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
    lambda_90b13554b61d927a0ea406787e17e624_::operator()(a2, **(NetSetup2::Exception ***)&v11.Data1);
    v6 = *(std::_Ref_count_base **)v11.Data4;
    if ( *(_QWORD *)v11.Data4
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)v11.Data4 + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(std::_Ref_count_base *))v6)(v6);
      std::_Ref_count_base::_Decwref(v6);
    }
  }
  wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v12);
  NetSetupTraceLogging::RpcNetSetupDeleteObject::~RpcNetSetupDeleteObject((NetSetupTraceLogging::RpcNetSetupDeleteObject *)v12);
  return TlsSetValue(*((_DWORD *)g_NetSetupService + 91), 0);
}

```

## disassembly

```asm
0x180011184  mov     [rsp-8+arg_10], rbx
0x180011189  push    rbp
0x18001118a  push    rsi
0x18001118b  push    rdi
0x18001118c  lea     rbp, [rsp-180h]
0x180011194  sub     rsp, 280h
0x18001119b  mov     rax, cs:__security_cookie
0x1800111a2  xor     rax, rsp
0x1800111a5  mov     [rbp+190h+var_20], rax
0x1800111ac  mov     rdi, rdx
0x1800111af  mov     rsi, rcx
0x1800111b2  mov     rdx, rcx; struct NETSETUP_RPC_CONTEXT *
0x1800111b5  lea     rcx, [rsp+290h+var_270]; this
0x1800111ba  call    ??0StashPidInTls@@QEAA@PEAUNETSETUP_RPC_CONTEXT@@@Z; StashPidInTls::StashPidInTls(NETSETUP_RPC_CONTEXT *)
0x1800111bf  nop
0x1800111c0  lea     rdx, [rbp+190h+var_188]; retstr
0x1800111c4  mov     rcx, rsi; this
0x1800111c7  call    ?GetId@NETSETUP_RPC_CONTEXT@@QEAA?AU_GUID@@XZ; NETSETUP_RPC_CONTEXT::GetId(void)
0x1800111cc  mov     rbx, rax
0x1800111cf  lea     rdx, aRpcnetsetupdel; "RpcNetSetupDeleteObject"
0x1800111d6  lea     rcx, [rbp+190h+var_170]
0x1800111da  call    ??0?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800111df  lea     rax, ??_7RpcNetSetupDeleteObject@NetSetupTraceLogging@@6B@; const NetSetupTraceLogging::RpcNetSetupDeleteObject::`vftable'
0x1800111e6  mov     [rbp+190h+var_170], rax
0x1800111ea  mov     rdx, rbx; struct _GUID *
0x1800111ed  lea     rcx, [rbp+190h+var_170]; this
0x1800111f1  call    ?StartActivity@RpcNetSetupDeleteObject@NetSetupTraceLogging@@QEAAXAEBU_GUID@@@Z; NetSetupTraceLogging::RpcNetSetupDeleteObject::StartActivity(_GUID const &)
0x1800111f6  nop
0x1800111f7  xorps   xmm0, xmm0
0x1800111fa  movdqu  [rsp+290h+var_268], xmm0
0x180011200  mov     rdx, [rsi+8]
0x180011204  test    rdx, rdx
0x180011207  jz      short loc_180011216
0x180011209  mov     rdx, [rdx]
0x18001120c  mov     rcx, rdi
0x18001120f  call    _lambda_90b13554b61d927a0ea406787e17e624___operator__
0x180011214  jmp     short loc_180011269
0x180011216  lea     rcx, [rsi+18h]
0x18001121a  lea     rdx, [rbp+190h+var_188]
0x18001121e  call    ?lock@?$weak_ptr@UNetSetupSvcTxHolder@@@std@@QEBA?AV?$shared_ptr@UNetSetupSvcTxHolder@@@2@XZ; std::weak_ptr<NetSetupSvcTxHolder>::lock(void)
0x180011223  nop
0x180011224  mov     rdx, qword ptr [rbp+190h+var_188.Data1]
0x180011228  test    rdx, rdx
0x18001122b  jz      loc_1800112B4
0x180011231  mov     rdx, [rdx]
0x180011234  mov     rcx, rdi
0x180011237  call    _lambda_90b13554b61d927a0ea406787e17e624___operator__
0x18001123c  nop
0x18001123d  mov     rbx, qword ptr [rbp+190h+var_188.Data4]
0x180011241  test    rbx, rbx
0x180011244  jz      short loc_180011269
0x180011246  or      eax, 0FFFFFFFFh
0x180011249  lock xadd [rbx+8], eax
0x18001124e  cmp     eax, 1
0x180011251  jnz     short loc_180011269
0x180011253  mov     rax, [rbx]
0x180011256  mov     rcx, rbx
0x180011259  mov     rax, [rax]
0x18001125c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011261  mov     rcx, rbx; this
0x180011264  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180011269  lea     rcx, [rbp+190h+var_170]
0x18001126d  call    ?Stop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180011272  nop
0x180011273  lea     rcx, [rbp+190h+var_170]; this
0x180011277  call    ??1RpcNetSetupDeleteObject@NetSetupTraceLogging@@QEAA@XZ; NetSetupTraceLogging::RpcNetSetupDeleteObject::~RpcNetSetupDeleteObject(void)
0x18001127c  nop
0x18001127d  xor     edx, edx; lpTlsValue
0x18001127f  mov     rcx, cs:?g_NetSetupService@@3PEAVNetSetupService@@EA; NetSetupService * g_NetSetupService
0x180011286  mov     ecx, [rcx+16Ch]; dwTlsIndex
0x18001128c  call    cs:__imp_TlsSetValue
0x180011292  mov     rcx, [rbp+190h+var_20]
0x180011299  xor     rcx, rsp; StackCookie
0x18001129c  call    __security_check_cookie
0x1800112a1  mov     rbx, [rsp+290h+arg_10]
0x1800112a9  add     rsp, 280h
0x1800112b0  pop     rdi
0x1800112b1  pop     rsi
0x1800112b2  pop     rbp
0x1800112b3  retn
0x1800112b4  lea     rax, WPP_GLOBAL_Control
0x1800112bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800112c2  cmp     rcx, rax
0x1800112c5  jz      short loc_1800112E2
0x1800112c7  cmp     byte ptr [rcx+19h], 2
0x1800112cb  jb      short loc_1800112E2
0x1800112cd  mov     edx, 11h
0x1800112d2  lea     r8, WPP_d7c9c24d725337bc8e6af9dd6d1b553a_Traceguids
0x1800112d9  mov     rcx, [rcx+10h]
0x1800112dd  call    WPP_SF_
0x1800112e2  mov     edx, 80071A9Fh; int
0x1800112e7  lea     rcx, [rsp+290h+pExceptionObject]; this
0x1800112ec  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800112f1  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800112f8  lea     rcx, [rsp+290h+pExceptionObject]; pExceptionObject
0x1800112fd  call    _CxxThrowException_0
```
