# RpcEntry_NetSetupTraceLogging::RpcNetSetupCreateObject__lambda_6a9f15c514d8e5738f8c67966b26e6ed___

- ea: `0x180010ffc`
- end: `0x18001117b`
- name: `RpcEntry_NetSetupTraceLogging::RpcNetSetupCreateObject__lambda_6a9f15c514d8e5738f8c67966b26e6ed___`
- size: `383`
- prototype: `BOOL __fastcall(NetSetup2::Exception ***this, unsigned int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update`

## callers

- `0x180010a50`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x1800078d0`
- `0x180008854`
- `0x18000d8ec`
- `0x18001023c`
- `0x180010ffc`
- `0x180011e70`
- `0x1800120c0`
- `0x180012414`
- `0x180012abc`
- `0x1800139fc`
- `0x180014590`
- `0x180014dd4`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180011104`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180011104`

## string_xrefs

- `0x180011047`: `RpcNetSetupCreateObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
BOOL __fastcall RpcEntry_NetSetupTraceLogging::RpcNetSetupCreateObject__lambda_6a9f15c514d8e5738f8c67966b26e6ed___(
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
    "RpcNetSetupCreateObject");
  v12[0] = &NetSetupTraceLogging::RpcNetSetupCreateObject::`vftable';
  NetSetupTraceLogging::RpcNetSetupCreateObject::StartActivity((NetSetupTraceLogging::RpcNetSetupCreateObject *)v12, Id);
  v9 = 0;
  v5 = this[1];
  if ( v5 )
  {
    lambda_6a9f15c514d8e5738f8c67966b26e6ed_::operator()(a2, *v5);
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
    lambda_6a9f15c514d8e5738f8c67966b26e6ed_::operator()(a2, **(NetSetup2::Exception ***)&v11.Data1);
    v6 = *(std::_Ref_count_base **)v11.Data4;
    if ( *(_QWORD *)v11.Data4
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)v11.Data4 + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(std::_Ref_count_base *))v6)(v6);
      std::_Ref_count_base::_Decwref(v6);
    }
  }
  wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v12);
  NetSetupTraceLogging::RpcNetSetupCreateObject::~RpcNetSetupCreateObject((NetSetupTraceLogging::RpcNetSetupCreateObject *)v12);
  return TlsSetValue(*((_DWORD *)g_NetSetupService + 91), 0);
}

```

## disassembly

```asm
0x180010ffc  mov     [rsp-8+arg_10], rbx
0x180011001  push    rbp
0x180011002  push    rsi
0x180011003  push    rdi
0x180011004  lea     rbp, [rsp-180h]
0x18001100c  sub     rsp, 280h
0x180011013  mov     rax, cs:__security_cookie
0x18001101a  xor     rax, rsp
0x18001101d  mov     [rbp+190h+var_20], rax
0x180011024  mov     rdi, rdx
0x180011027  mov     rsi, rcx
0x18001102a  mov     rdx, rcx; struct NETSETUP_RPC_CONTEXT *
0x18001102d  lea     rcx, [rsp+290h+var_270]; this
0x180011032  call    ??0StashPidInTls@@QEAA@PEAUNETSETUP_RPC_CONTEXT@@@Z; StashPidInTls::StashPidInTls(NETSETUP_RPC_CONTEXT *)
0x180011037  nop
0x180011038  lea     rdx, [rbp+190h+var_188]; retstr
0x18001103c  mov     rcx, rsi; this
0x18001103f  call    ?GetId@NETSETUP_RPC_CONTEXT@@QEAA?AU_GUID@@XZ; NETSETUP_RPC_CONTEXT::GetId(void)
0x180011044  mov     rbx, rax
0x180011047  lea     rdx, aRpcnetsetupcre; "RpcNetSetupCreateObject"
0x18001104e  lea     rcx, [rbp+190h+var_170]
0x180011052  call    ??0?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180011057  lea     rax, ??_7RpcNetSetupCreateObject@NetSetupTraceLogging@@6B@; const NetSetupTraceLogging::RpcNetSetupCreateObject::`vftable'
0x18001105e  mov     [rbp+190h+var_170], rax
0x180011062  mov     rdx, rbx; struct _GUID *
0x180011065  lea     rcx, [rbp+190h+var_170]; this
0x180011069  call    ?StartActivity@RpcNetSetupCreateObject@NetSetupTraceLogging@@QEAAXAEBU_GUID@@@Z; NetSetupTraceLogging::RpcNetSetupCreateObject::StartActivity(_GUID const &)
0x18001106e  nop
0x18001106f  xorps   xmm0, xmm0
0x180011072  movdqu  [rsp+290h+var_268], xmm0
0x180011078  mov     rdx, [rsi+8]
0x18001107c  test    rdx, rdx
0x18001107f  jz      short loc_18001108E
0x180011081  mov     rdx, [rdx]
0x180011084  mov     rcx, rdi
0x180011087  call    _lambda_6a9f15c514d8e5738f8c67966b26e6ed___operator__
0x18001108c  jmp     short loc_1800110E1
0x18001108e  lea     rcx, [rsi+18h]
0x180011092  lea     rdx, [rbp+190h+var_188]
0x180011096  call    ?lock@?$weak_ptr@UNetSetupSvcTxHolder@@@std@@QEBA?AV?$shared_ptr@UNetSetupSvcTxHolder@@@2@XZ; std::weak_ptr<NetSetupSvcTxHolder>::lock(void)
0x18001109b  nop
0x18001109c  mov     rdx, qword ptr [rbp+190h+var_188.Data1]
0x1800110a0  test    rdx, rdx
0x1800110a3  jz      loc_18001112C
0x1800110a9  mov     rdx, [rdx]
0x1800110ac  mov     rcx, rdi
0x1800110af  call    _lambda_6a9f15c514d8e5738f8c67966b26e6ed___operator__
0x1800110b4  nop
0x1800110b5  mov     rbx, qword ptr [rbp+190h+var_188.Data4]
0x1800110b9  test    rbx, rbx
0x1800110bc  jz      short loc_1800110E1
0x1800110be  or      eax, 0FFFFFFFFh
0x1800110c1  lock xadd [rbx+8], eax
0x1800110c6  cmp     eax, 1
0x1800110c9  jnz     short loc_1800110E1
0x1800110cb  mov     rax, [rbx]
0x1800110ce  mov     rcx, rbx
0x1800110d1  mov     rax, [rax]
0x1800110d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110d9  mov     rcx, rbx; this
0x1800110dc  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800110e1  lea     rcx, [rbp+190h+var_170]
0x1800110e5  call    ?Stop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800110ea  nop
0x1800110eb  lea     rcx, [rbp+190h+var_170]; this
0x1800110ef  call    ??1RpcNetSetupCreateObject@NetSetupTraceLogging@@QEAA@XZ; NetSetupTraceLogging::RpcNetSetupCreateObject::~RpcNetSetupCreateObject(void)
0x1800110f4  nop
0x1800110f5  xor     edx, edx; lpTlsValue
0x1800110f7  mov     rcx, cs:?g_NetSetupService@@3PEAVNetSetupService@@EA; NetSetupService * g_NetSetupService
0x1800110fe  mov     ecx, [rcx+16Ch]; dwTlsIndex
0x180011104  call    cs:__imp_TlsSetValue
0x18001110a  mov     rcx, [rbp+190h+var_20]
0x180011111  xor     rcx, rsp; StackCookie
0x180011114  call    __security_check_cookie
0x180011119  mov     rbx, [rsp+290h+arg_10]
0x180011121  add     rsp, 280h
0x180011128  pop     rdi
0x180011129  pop     rsi
0x18001112a  pop     rbp
0x18001112b  retn
0x18001112c  lea     rax, WPP_GLOBAL_Control
0x180011133  mov     rcx, cs:WPP_GLOBAL_Control
0x18001113a  cmp     rcx, rax
0x18001113d  jz      short loc_18001115A
0x18001113f  cmp     byte ptr [rcx+19h], 2
0x180011143  jb      short loc_18001115A
0x180011145  mov     edx, 11h
0x18001114a  lea     r8, WPP_d7c9c24d725337bc8e6af9dd6d1b553a_Traceguids
0x180011151  mov     rcx, [rcx+10h]
0x180011155  call    WPP_SF_
0x18001115a  mov     edx, 80071A9Fh; int
0x18001115f  lea     rcx, [rsp+290h+pExceptionObject]; this
0x180011164  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180011169  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180011170  lea     rcx, [rsp+290h+pExceptionObject]; pExceptionObject
0x180011175  call    _CxxThrowException_0
```
