# BioIsoSrvEngineSetAccountPolicy

- ea: `0x14000c1b0`
- end: `0x14000c3fd`
- name: `BioIsoSrvEngineSetAccountPolicy`
- size: `589`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x14000791c`
- `0x14000a2e4`
- `0x14000a31c`
- `0x14000a420`
- `0x14000c1b0`
- `0x14000c404`
- `0x140012974`
- `0x14001bd40`
- `0x140044cb8`
- `0x140057b78`
- `0x140059830`
- `0x140085010`

## string_xrefs

- `0x14000c218`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000c257`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000c2a0`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000c2fa`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000c3a4`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BioIsoSrvEngineSetAccountPolicy(int *a1, const struct _WINBIO_ACCOUNT_POLICY *a2, unsigned int a3)
{
  unsigned __int64 v3; // rdi
  int BiometricUnit; // eax
  int v8; // ebx
  unsigned __int64 v9; // r14
  unsigned __int64 v10; // r8
  std::_Ref_count_base *v11; // rdi
  int v12; // eax
  __int64 v13; // rax
  __int64 (__fastcall *v14)(__int64, const struct _WINBIO_ACCOUNT_POLICY *, unsigned __int64); // rax
  int v15; // [rsp+20h] [rbp-198h]
  std::_Ref_count_base *v16[2]; // [rsp+28h] [rbp-190h] BYREF
  _QWORD v17[42]; // [rsp+40h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v3 = a3;
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v17,
    (__int64)"EngineSetAccountPolicy");
  v17[0] = &BioIsoProvider::EngineSetAccountPolicy::`vftable';
  BioIsoProvider::EngineSetAccountPolicy::StartActivity((BioIsoProvider::EngineSetAccountPolicy *)v17);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x597,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v15);
    BioIsoProvider::EngineSetAccountPolicy::~EngineSetAccountPolicy((BioIsoProvider::EngineSetAccountPolicy *)v17);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle((unsigned __int64)a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x598,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v15);
    BioIsoProvider::EngineSetAccountPolicy::~EngineSetAccountPolicy((BioIsoProvider::EngineSetAccountPolicy *)v17);
    return 2147942487LL;
  }
  *(_OWORD *)v16 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v16);
  v8 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x59D,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v15);
    if ( v16[1] )
      std::_Ref_count_base::_Decref(v16[1]);
LABEL_25:
    BioIsoProvider::EngineSetAccountPolicy::~EngineSetAccountPolicy((BioIsoProvider::EngineSetAccountPolicy *)v17);
    return (unsigned int)v8;
  }
  v9 = v3;
  v10 = v3;
  v11 = v16[0];
  v12 = BiometricUnit::SetAccountPolicy(v16[0], a2, v10);
  v8 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A0,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)v12,
      v15);
    if ( v16[1] )
      std::_Ref_count_base::_Decref(v16[1]);
    goto LABEL_25;
  }
  if ( *((_QWORD *)v11 + 3) == -32 || (v13 = *(_QWORD *)(*((_QWORD *)v11 + 3) + 64LL)) == 0 || !a2 )
  {
    v8 = -2147467261;
    goto LABEL_23;
  }
  v14 = *(__int64 (__fastcall **)(__int64, const struct _WINBIO_ACCOUNT_POLICY *, unsigned __int64))(v13 + 312);
  if ( !v14 )
  {
    v8 = -2147467263;
    goto LABEL_23;
  }
  v8 = v14(*((_QWORD *)v11 + 3) + 32LL, a2, v9);
  if ( v8 < 0 )
  {
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A3,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)v8,
      v15);
    if ( v16[1] )
      std::_Ref_count_base::_Decref(v16[1]);
    goto LABEL_25;
  }
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v17, 0);
  if ( v16[1] )
    std::_Ref_count_base::_Decref(v16[1]);
  BioIsoProvider::EngineSetAccountPolicy::~EngineSetAccountPolicy((BioIsoProvider::EngineSetAccountPolicy *)v17);
  return 0;
}

```

## disassembly

```asm
0x14000c1b0  mov     [rsp+arg_18], rbx
0x14000c1b5  push    rsi
0x14000c1b6  push    rdi
0x14000c1b7  push    r14
0x14000c1b9  sub     rsp, 1A0h
0x14000c1c0  mov     rax, cs:__security_cookie
0x14000c1c7  xor     rax, rsp
0x14000c1ca  mov     [rsp+1B8h+var_28], rax
0x14000c1d2  mov     edi, r8d
0x14000c1d5  mov     rsi, rdx
0x14000c1d8  mov     rbx, rcx
0x14000c1db  lea     rdx, aEnginesetaccou; "EngineSetAccountPolicy"
0x14000c1e2  lea     rcx, [rsp+1B8h+var_178]
0x14000c1e7  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14000c1ec  lea     rax, ??_7EngineSetAccountPolicy@BioIsoProvider@@6B@; const BioIsoProvider::EngineSetAccountPolicy::`vftable'
0x14000c1f3  mov     [rsp+1B8h+var_178], rax
0x14000c1f8  lea     rcx, [rsp+1B8h+var_178]; this
0x14000c1fd  call    ?StartActivity@EngineSetAccountPolicy@BioIsoProvider@@QEAAXXZ; BioIsoProvider::EngineSetAccountPolicy::StartActivity(void)
0x14000c202  nop
0x14000c203  test    rbx, rbx
0x14000c206  jnz     short loc_14000C23B
0x14000c208  mov     rcx, [rsp+1B8h]; this
0x14000c210  mov     ebx, 80004003h
0x14000c215  mov     r9d, ebx; char *
0x14000c218  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000c21f  mov     edx, 597h; void *
0x14000c224  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c229  nop
0x14000c22a  lea     rcx, [rsp+1B8h+var_178]; this
0x14000c22f  call    ??1EngineSetAccountPolicy@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineSetAccountPolicy::~EngineSetAccountPolicy(void)
0x14000c234  mov     eax, ebx
0x14000c236  jmp     loc_14000C3D8
0x14000c23b  mov     rcx, rbx; void *
0x14000c23e  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x14000c243  test    al, al
0x14000c245  jnz     short loc_14000C27A
0x14000c247  mov     rcx, [rsp+1B8h]; this
0x14000c24f  mov     ebx, 80070057h
0x14000c254  mov     r9d, ebx; char *
0x14000c257  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000c25e  mov     edx, 598h; void *
0x14000c263  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c268  nop
0x14000c269  lea     rcx, [rsp+1B8h+var_178]; this
0x14000c26e  call    ??1EngineSetAccountPolicy@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineSetAccountPolicy::~EngineSetAccountPolicy(void)
0x14000c273  mov     eax, ebx
0x14000c275  jmp     loc_14000C3D8
0x14000c27a  xorps   xmm0, xmm0
0x14000c27d  movdqu  xmmword ptr [rsp+1B8h+var_190], xmm0
0x14000c283  lea     rdx, [rsp+1B8h+var_190]
0x14000c288  mov     ecx, [rbx]
0x14000c28a  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x14000c28f  mov     ebx, eax
0x14000c291  test    eax, eax
0x14000c293  jns     short loc_14000C2D3
0x14000c295  mov     rcx, [rsp+1B8h]; this
0x14000c29d  mov     r9d, eax; char *
0x14000c2a0  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000c2a7  mov     edx, 59Dh; void *
0x14000c2ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c2b1  nop
0x14000c2b2  mov     rcx, [rsp+1B8h+var_190+8]; this
0x14000c2b7  test    rcx, rcx
0x14000c2ba  jz      short loc_14000C2C2
0x14000c2bc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000c2c1  nop
0x14000c2c2  lea     rcx, [rsp+1B8h+var_178]; this
0x14000c2c7  call    ??1EngineSetAccountPolicy@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineSetAccountPolicy::~EngineSetAccountPolicy(void)
0x14000c2cc  mov     eax, ebx
0x14000c2ce  jmp     loc_14000C3D8
0x14000c2d3  mov     r14, rdi
0x14000c2d6  mov     r8, rdi; unsigned __int64
0x14000c2d9  mov     rdx, rsi; struct _WINBIO_ACCOUNT_POLICY *
0x14000c2dc  mov     rdi, [rsp+1B8h+var_190]
0x14000c2e1  mov     rcx, rdi; this
0x14000c2e4  call    ?SetAccountPolicy@BiometricUnit@@QEAAJPEBU_WINBIO_ACCOUNT_POLICY@@_K@Z; BiometricUnit::SetAccountPolicy(_WINBIO_ACCOUNT_POLICY const *,unsigned __int64)
0x14000c2e9  mov     ebx, eax
0x14000c2eb  test    eax, eax
0x14000c2ed  jns     short loc_14000C32D
0x14000c2ef  mov     rcx, [rsp+1B8h]; this
0x14000c2f7  mov     r9d, eax; char *
0x14000c2fa  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000c301  mov     edx, 5A0h; void *
0x14000c306  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c30b  nop
0x14000c30c  mov     rcx, [rsp+1B8h+var_190+8]; this
0x14000c311  test    rcx, rcx
0x14000c314  jz      short loc_14000C31C
0x14000c316  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000c31b  nop
0x14000c31c  lea     rcx, [rsp+1B8h+var_178]; this
0x14000c321  call    ??1EngineSetAccountPolicy@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineSetAccountPolicy::~EngineSetAccountPolicy(void)
0x14000c326  mov     eax, ebx
0x14000c328  jmp     loc_14000C3D8
0x14000c32d  mov     rcx, [rdi+18h]
0x14000c331  add     rcx, 20h ; ' '
0x14000c335  jz      short loc_14000C394
0x14000c337  mov     rax, [rcx+20h]
0x14000c33b  test    rax, rax
0x14000c33e  jz      short loc_14000C394
0x14000c340  test    rsi, rsi
0x14000c343  jz      short loc_14000C394
0x14000c345  mov     rax, [rax+138h]
0x14000c34c  test    rax, rax
0x14000c34f  jnz     short loc_14000C358
0x14000c351  mov     ebx, 80004001h
0x14000c356  jmp     short loc_14000C399
0x14000c358  mov     r8, r14
0x14000c35b  mov     rdx, rsi
0x14000c35e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c363  mov     ebx, eax
0x14000c365  test    eax, eax
0x14000c367  js      short loc_14000C399
0x14000c369  xor     edx, edx
0x14000c36b  lea     rcx, [rsp+1B8h+var_178]
0x14000c370  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14000c375  nop
0x14000c376  mov     rcx, [rsp+1B8h+var_190+8]; this
0x14000c37b  test    rcx, rcx
0x14000c37e  jz      short loc_14000C386
0x14000c380  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000c385  nop
0x14000c386  lea     rcx, [rsp+1B8h+var_178]; this
0x14000c38b  call    ??1EngineSetAccountPolicy@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineSetAccountPolicy::~EngineSetAccountPolicy(void)
0x14000c390  xor     eax, eax
0x14000c392  jmp     short loc_14000C3D8
0x14000c394  mov     ebx, 80004003h
0x14000c399  mov     rcx, [rsp+1B8h]; this
0x14000c3a1  mov     r9d, ebx; char *
0x14000c3a4  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000c3ab  mov     edx, 5A3h; void *
0x14000c3b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c3b5  nop
0x14000c3b6  mov     rcx, [rsp+1B8h+var_190+8]; this
0x14000c3bb  test    rcx, rcx
0x14000c3be  jz      short loc_14000C3C6
0x14000c3c0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000c3c5  nop
0x14000c3c6  lea     rcx, [rsp+1B8h+var_178]; this
0x14000c3cb  call    ??1EngineSetAccountPolicy@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineSetAccountPolicy::~EngineSetAccountPolicy(void)
0x14000c3d0  mov     eax, ebx
0x14000c3d2  jmp     short loc_14000C3D8
0x14000c3d4  mov     eax, [rsp+1B8h+var_198]
0x14000c3d8  mov     rcx, [rsp+1B8h+var_28]
0x14000c3e0  xor     rcx, rsp; StackCookie
0x14000c3e3  call    __security_check_cookie
0x14000c3e8  mov     rbx, [rsp+1B8h+arg_18]
0x14000c3f0  add     rsp, 1A0h
0x14000c3f7  pop     r14
0x14000c3f9  pop     rdi
0x14000c3fa  pop     rsi
0x14000c3fb  retn
```
