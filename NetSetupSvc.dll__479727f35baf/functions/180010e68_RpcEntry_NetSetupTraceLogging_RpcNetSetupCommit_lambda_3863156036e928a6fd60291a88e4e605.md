# RpcEntry_NetSetupTraceLogging::RpcNetSetupCommit__lambda_3863156036e928a6fd60291a88e4e605___

- ea: `0x180010e68`
- end: `0x180010ff5`
- name: `RpcEntry_NetSetupTraceLogging::RpcNetSetupCommit__lambda_3863156036e928a6fd60291a88e4e605___`
- size: `397`
- prototype: `BOOL __fastcall(__int64 **this, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180010854`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x1800078d0`
- `0x180008854`
- `0x18000d8ec`
- `0x18001023c`
- `0x180010e68`
- `0x180011e70`
- `0x1800120c0`
- `0x1800123e8`
- `0x180012a08`
- `0x1800139fc`
- `0x1800144c8`
- `0x180014dd4`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180010f7c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180010f7c`

## string_xrefs

- `0x180010eb7`: `RpcNetSetupCommit`

## pseudocode

```c
BOOL __fastcall RpcEntry_NetSetupTraceLogging::RpcNetSetupCommit__lambda_3863156036e928a6fd60291a88e4e605___(
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
    v12,
    "RpcNetSetupCommit");
  v12[0] = &NetSetupTraceLogging::RpcNetSetupCommit::`vftable';
  NetSetupTraceLogging::RpcNetSetupCommit::StartActivity((NetSetupTraceLogging::RpcNetSetupCommit *)v12, Id);
  *(_OWORD *)&v9[8] = 0;
  v5 = this[1];
  if ( v5 )
  {
    lambda_3863156036e928a6fd60291a88e4e605_::operator()((__int64)&v13, *v5, v4);
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
    lambda_3863156036e928a6fd60291a88e4e605_::operator()((__int64)&v13, **(_QWORD **)&v11.Data1, v6);
    v7 = *(std::_Ref_count_base **)v11.Data4;
    if ( *(_QWORD *)v11.Data4
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)v11.Data4 + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(std::_Ref_count_base *))v7)(v7);
      std::_Ref_count_base::_Decwref(v7);
    }
  }
  wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v12);
  NetSetupTraceLogging::RpcNetSetupCommit::~RpcNetSetupCommit((NetSetupTraceLogging::RpcNetSetupCommit *)v12);
  return TlsSetValue(*((_DWORD *)g_NetSetupService + 91), 0);
}

```

## disassembly

```asm
0x180010e68  mov     rax, rsp
0x180010e6b  mov     [rax+18h], rbx
0x180010e6f  mov     [rax+20h], rdi
0x180010e73  mov     [rax+10h], rdx
0x180010e77  push    rbp
0x180010e78  lea     rbp, [rax-188h]
0x180010e7f  sub     rsp, 280h
0x180010e86  mov     rax, cs:__security_cookie
0x180010e8d  xor     rax, rsp
0x180010e90  mov     [rbp+180h+var_10], rax
0x180010e97  mov     rdi, rcx
0x180010e9a  mov     rdx, rcx; struct NETSETUP_RPC_CONTEXT *
0x180010e9d  lea     rcx, [rsp+280h+var_260]; this
0x180010ea2  call    ??0StashPidInTls@@QEAA@PEAUNETSETUP_RPC_CONTEXT@@@Z; StashPidInTls::StashPidInTls(NETSETUP_RPC_CONTEXT *)
0x180010ea7  nop
0x180010ea8  lea     rdx, [rbp+180h+var_178]; retstr
0x180010eac  mov     rcx, rdi; this
0x180010eaf  call    ?GetId@NETSETUP_RPC_CONTEXT@@QEAA?AU_GUID@@XZ; NETSETUP_RPC_CONTEXT::GetId(void)
0x180010eb4  mov     rbx, rax
0x180010eb7  lea     rdx, aRpcnetsetupcom; "RpcNetSetupCommit"
0x180010ebe  lea     rcx, [rbp+180h+var_160]
0x180010ec2  call    ??0?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180010ec7  lea     rax, ??_7RpcNetSetupCommit@NetSetupTraceLogging@@6B@; const NetSetupTraceLogging::RpcNetSetupCommit::`vftable'
0x180010ece  mov     [rbp+180h+var_160], rax
0x180010ed2  mov     rdx, rbx; struct _GUID *
0x180010ed5  lea     rcx, [rbp+180h+var_160]; this
0x180010ed9  call    ?StartActivity@RpcNetSetupCommit@NetSetupTraceLogging@@QEAAXAEBU_GUID@@@Z; NetSetupTraceLogging::RpcNetSetupCommit::StartActivity(_GUID const &)
0x180010ede  nop
0x180010edf  xorps   xmm0, xmm0
0x180010ee2  movdqu  [rsp+280h+var_260+8], xmm0
0x180010ee8  mov     rdx, [rdi+8]
0x180010eec  test    rdx, rdx
0x180010eef  jz      short loc_180010F02
0x180010ef1  mov     rdx, [rdx]
0x180010ef4  lea     rcx, [rbp+180h+arg_8]
0x180010efb  call    _lambda_3863156036e928a6fd60291a88e4e605___operator__
0x180010f00  jmp     short loc_180010F59
0x180010f02  lea     rcx, [rdi+18h]
0x180010f06  lea     rdx, [rbp+180h+var_178]
0x180010f0a  call    ?lock@?$weak_ptr@UNetSetupSvcTxHolder@@@std@@QEBA?AV?$shared_ptr@UNetSetupSvcTxHolder@@@2@XZ; std::weak_ptr<NetSetupSvcTxHolder>::lock(void)
0x180010f0f  nop
0x180010f10  mov     rdx, qword ptr [rbp+180h+var_178.Data1]
0x180010f14  test    rdx, rdx
0x180010f17  jz      loc_180010FA6
0x180010f1d  mov     rdx, [rdx]
0x180010f20  lea     rcx, [rbp+180h+arg_8]
0x180010f27  call    _lambda_3863156036e928a6fd60291a88e4e605___operator__
0x180010f2c  nop
0x180010f2d  mov     rbx, qword ptr [rbp+180h+var_178.Data4]
0x180010f31  test    rbx, rbx
0x180010f34  jz      short loc_180010F59
0x180010f36  or      eax, 0FFFFFFFFh
0x180010f39  lock xadd [rbx+8], eax
0x180010f3e  cmp     eax, 1
0x180010f41  jnz     short loc_180010F59
0x180010f43  mov     rax, [rbx]
0x180010f46  mov     rcx, rbx
0x180010f49  mov     rax, [rax]
0x180010f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f51  mov     rcx, rbx; this
0x180010f54  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180010f59  lea     rcx, [rbp+180h+var_160]
0x180010f5d  call    ?Stop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180010f62  nop
0x180010f63  lea     rcx, [rbp+180h+var_160]; this
0x180010f67  call    ??1RpcNetSetupCommit@NetSetupTraceLogging@@QEAA@XZ; NetSetupTraceLogging::RpcNetSetupCommit::~RpcNetSetupCommit(void)
0x180010f6c  nop
0x180010f6d  xor     edx, edx; lpTlsValue
0x180010f6f  mov     rcx, cs:?g_NetSetupService@@3PEAVNetSetupService@@EA; NetSetupService * g_NetSetupService
0x180010f76  mov     ecx, [rcx+16Ch]; dwTlsIndex
0x180010f7c  call    cs:__imp_TlsSetValue
0x180010f82  mov     rcx, [rbp+180h+var_10]
0x180010f89  xor     rcx, rsp; StackCookie
0x180010f8c  call    __security_check_cookie
0x180010f91  lea     r11, [rsp+280h+var_s0]
0x180010f99  mov     rbx, [r11+20h]
0x180010f9d  mov     rdi, [r11+28h]
0x180010fa1  mov     rsp, r11
0x180010fa4  pop     rbp
0x180010fa5  retn
0x180010fa6  lea     rax, WPP_GLOBAL_Control
0x180010fad  mov     rcx, cs:WPP_GLOBAL_Control
0x180010fb4  cmp     rcx, rax
0x180010fb7  jz      short loc_180010FD4
0x180010fb9  cmp     byte ptr [rcx+19h], 2
0x180010fbd  jb      short loc_180010FD4
0x180010fbf  mov     edx, 11h
0x180010fc4  lea     r8, WPP_d7c9c24d725337bc8e6af9dd6d1b553a_Traceguids
0x180010fcb  mov     rcx, [rcx+10h]
0x180010fcf  call    WPP_SF_
0x180010fd4  mov     edx, 80071A9Fh; int
0x180010fd9  lea     rcx, [rsp+280h+pExceptionObject]; this
0x180010fde  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180010fe3  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180010fea  lea     rcx, [rsp+280h+pExceptionObject]; pExceptionObject
0x180010fef  call    _CxxThrowException_0
```
