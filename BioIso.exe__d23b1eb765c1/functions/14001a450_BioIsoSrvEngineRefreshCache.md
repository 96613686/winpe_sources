# BioIsoSrvEngineRefreshCache

- ea: `0x14001a450`
- end: `0x14001a625`
- name: `BioIsoSrvEngineRefreshCache`
- size: `469`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000791c`
- `0x14000a2e4`
- `0x14000a31c`
- `0x14000a420`
- `0x140012974`
- `0x14001a450`
- `0x14001a62c`
- `0x14001bd40`
- `0x1400448c8`
- `0x140059830`
- `0x140085010`

## string_xrefs

- `0x14001a4ab`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14001a4ea`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14001a533`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14001a5d7`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14001a46e`: `EngineRefreshCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BioIsoSrvEngineRefreshCache(int *a1)
{
  int BiometricUnit; // eax
  int v4; // ebx
  __int64 v5; // rax
  __int64 (*v6)(void); // rax
  int v7; // [rsp+20h] [rbp-188h]
  std::_Ref_count_base *v8[2]; // [rsp+28h] [rbp-180h] BYREF
  _QWORD v9[42]; // [rsp+40h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v9,
    (__int64)"EngineRefreshCache");
  v9[0] = &BioIsoProvider::EngineRefreshCache::`vftable';
  BioIsoProvider::EngineRefreshCache::StartActivity((BioIsoProvider::EngineRefreshCache *)v9);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x541,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v7);
    BioIsoProvider::EngineRefreshCache::~EngineRefreshCache((BioIsoProvider::EngineRefreshCache *)v9);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle((unsigned __int64)a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x542,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v7);
    BioIsoProvider::EngineRefreshCache::~EngineRefreshCache((BioIsoProvider::EngineRefreshCache *)v9);
    return 2147942487LL;
  }
  *(_OWORD *)v8 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v8);
  v4 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x547,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v7);
    if ( v8[1] )
      std::_Ref_count_base::_Decref(v8[1]);
LABEL_20:
    BioIsoProvider::EngineRefreshCache::~EngineRefreshCache((BioIsoProvider::EngineRefreshCache *)v9);
    return (unsigned int)v4;
  }
  if ( *((_QWORD *)v8[0] + 3) == -32 || (v5 = *(_QWORD *)(*((_QWORD *)v8[0] + 3) + 64LL)) == 0 )
  {
    v4 = -2147467261;
    goto LABEL_18;
  }
  v6 = *(__int64 (**)(void))(v5 + 288);
  if ( !v6 )
  {
    v4 = -2147467263;
    goto LABEL_18;
  }
  v4 = v6();
  if ( v4 < 0 )
  {
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54A,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)v4,
      v7);
    if ( v8[1] )
      std::_Ref_count_base::_Decref(v8[1]);
    goto LABEL_20;
  }
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v9, 0);
  if ( v8[1] )
    std::_Ref_count_base::_Decref(v8[1]);
  BioIsoProvider::EngineRefreshCache::~EngineRefreshCache((BioIsoProvider::EngineRefreshCache *)v9);
  return 0;
}

```

## disassembly

```asm
0x14001a450  push    rbx
0x14001a452  sub     rsp, 1A0h
0x14001a459  mov     rax, cs:__security_cookie
0x14001a460  xor     rax, rsp
0x14001a463  mov     [rsp+1A8h+var_18], rax
0x14001a46b  mov     rbx, rcx
0x14001a46e  lea     rdx, aEnginerefreshc; "EngineRefreshCache"
0x14001a475  lea     rcx, [rsp+1A8h+var_168]
0x14001a47a  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14001a47f  lea     rax, ??_7EngineRefreshCache@BioIsoProvider@@6B@; const BioIsoProvider::EngineRefreshCache::`vftable'
0x14001a486  mov     [rsp+1A8h+var_168], rax
0x14001a48b  lea     rcx, [rsp+1A8h+var_168]; this
0x14001a490  call    ?StartActivity@EngineRefreshCache@BioIsoProvider@@QEAAXXZ; BioIsoProvider::EngineRefreshCache::StartActivity(void)
0x14001a495  nop
0x14001a496  test    rbx, rbx
0x14001a499  jnz     short loc_14001A4CE
0x14001a49b  mov     rcx, [rsp+1A8h]; this
0x14001a4a3  mov     ebx, 80004003h
0x14001a4a8  mov     r9d, ebx; char *
0x14001a4ab  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14001a4b2  mov     edx, 541h; void *
0x14001a4b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a4bc  nop
0x14001a4bd  lea     rcx, [rsp+1A8h+var_168]; this
0x14001a4c2  call    ??1EngineRefreshCache@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineRefreshCache::~EngineRefreshCache(void)
0x14001a4c7  mov     eax, ebx
0x14001a4c9  jmp     loc_14001A60B
0x14001a4ce  mov     rcx, rbx; void *
0x14001a4d1  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x14001a4d6  test    al, al
0x14001a4d8  jnz     short loc_14001A50D
0x14001a4da  mov     rcx, [rsp+1A8h]; this
0x14001a4e2  mov     ebx, 80070057h
0x14001a4e7  mov     r9d, ebx; char *
0x14001a4ea  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14001a4f1  mov     edx, 542h; void *
0x14001a4f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a4fb  nop
0x14001a4fc  lea     rcx, [rsp+1A8h+var_168]; this
0x14001a501  call    ??1EngineRefreshCache@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineRefreshCache::~EngineRefreshCache(void)
0x14001a506  mov     eax, ebx
0x14001a508  jmp     loc_14001A60B
0x14001a50d  xorps   xmm0, xmm0
0x14001a510  movdqu  xmmword ptr [rsp+1A8h+var_180], xmm0
0x14001a516  lea     rdx, [rsp+1A8h+var_180]
0x14001a51b  mov     ecx, [rbx]
0x14001a51d  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x14001a522  mov     ebx, eax
0x14001a524  test    eax, eax
0x14001a526  jns     short loc_14001A566
0x14001a528  mov     rcx, [rsp+1A8h]; this
0x14001a530  mov     r9d, eax; char *
0x14001a533  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14001a53a  mov     edx, 547h; void *
0x14001a53f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a544  nop
0x14001a545  mov     rcx, [rsp+1A8h+var_180+8]; this
0x14001a54a  test    rcx, rcx
0x14001a54d  jz      short loc_14001A555
0x14001a54f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001a554  nop
0x14001a555  lea     rcx, [rsp+1A8h+var_168]; this
0x14001a55a  call    ??1EngineRefreshCache@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineRefreshCache::~EngineRefreshCache(void)
0x14001a55f  mov     eax, ebx
0x14001a561  jmp     loc_14001A60B
0x14001a566  mov     rax, [rsp+1A8h+var_180]
0x14001a56b  mov     rcx, [rax+18h]
0x14001a56f  add     rcx, 20h ; ' '
0x14001a573  jz      short loc_14001A5C7
0x14001a575  mov     rax, [rcx+20h]
0x14001a579  test    rax, rax
0x14001a57c  jz      short loc_14001A5C7
0x14001a57e  mov     rax, [rax+120h]
0x14001a585  test    rax, rax
0x14001a588  jnz     short loc_14001A591
0x14001a58a  mov     ebx, 80004001h
0x14001a58f  jmp     short loc_14001A5CC
0x14001a591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a596  mov     ebx, eax
0x14001a598  test    eax, eax
0x14001a59a  js      short loc_14001A5CC
0x14001a59c  xor     edx, edx
0x14001a59e  lea     rcx, [rsp+1A8h+var_168]
0x14001a5a3  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14001a5a8  nop
0x14001a5a9  mov     rcx, [rsp+1A8h+var_180+8]; this
0x14001a5ae  test    rcx, rcx
0x14001a5b1  jz      short loc_14001A5B9
0x14001a5b3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001a5b8  nop
0x14001a5b9  lea     rcx, [rsp+1A8h+var_168]; this
0x14001a5be  call    ??1EngineRefreshCache@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineRefreshCache::~EngineRefreshCache(void)
0x14001a5c3  xor     eax, eax
0x14001a5c5  jmp     short loc_14001A60B
0x14001a5c7  mov     ebx, 80004003h
0x14001a5cc  mov     rcx, [rsp+1A8h]; this
0x14001a5d4  mov     r9d, ebx; char *
0x14001a5d7  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14001a5de  mov     edx, 54Ah; void *
0x14001a5e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a5e8  nop
0x14001a5e9  mov     rcx, [rsp+1A8h+var_180+8]; this
0x14001a5ee  test    rcx, rcx
0x14001a5f1  jz      short loc_14001A5F9
0x14001a5f3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001a5f8  nop
0x14001a5f9  lea     rcx, [rsp+1A8h+var_168]; this
0x14001a5fe  call    ??1EngineRefreshCache@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineRefreshCache::~EngineRefreshCache(void)
0x14001a603  mov     eax, ebx
0x14001a605  jmp     short loc_14001A60B
0x14001a607  mov     eax, [rsp+1A8h+var_188]
0x14001a60b  mov     rcx, [rsp+1A8h+var_18]
0x14001a613  xor     rcx, rsp; StackCookie
0x14001a616  call    __security_check_cookie
0x14001a61b  add     rsp, 1A0h
0x14001a622  pop     rbx
0x14001a623  retn
```
