# BioIsoSrvEngineAcceptSampleData

- ea: `0x140019440`
- end: `0x1400196b9`
- name: `BioIsoSrvEngineAcceptSampleData`
- size: `633`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000791c`
- `0x14000a2e4`
- `0x14000a31c`
- `0x14000a420`
- `0x140012974`
- `0x140013078`
- `0x140019440`
- `0x1400196c0`
- `0x14001bd40`
- `0x1400439b0`
- `0x140059830`
- `0x140085010`

## string_xrefs

- `0x1400194a3`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400194e2`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14001952b`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140019587`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14001965a`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BioIsoSrvEngineAcceptSampleData(int *a1, char a2, int a3)
{
  int BiometricUnit; // eax
  int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 (__fastcall *v13)(__int64, _QWORD, _QWORD, __int64); // rax
  int v14; // [rsp+20h] [rbp-1B8h]
  std::_Ref_count_base *v15[2]; // [rsp+38h] [rbp-1A0h] BYREF
  __int64 v16; // [rsp+48h] [rbp-190h] BYREF
  std::_Ref_count_base *v17; // [rsp+50h] [rbp-188h]
  _QWORD v18[42]; // [rsp+60h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v18,
    (__int64)"EngineAcceptSampleData");
  v18[0] = &BioIsoProvider::EngineAcceptSampleData::`vftable';
  BioIsoProvider::EngineAcceptSampleData::StartActivity((BioIsoProvider::EngineAcceptSampleData *)v18);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34B,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v14);
    BioIsoProvider::EngineAcceptSampleData::~EngineAcceptSampleData((BioIsoProvider::EngineAcceptSampleData *)v18);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle((unsigned __int64)a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34C,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v14);
    BioIsoProvider::EngineAcceptSampleData::~EngineAcceptSampleData((BioIsoProvider::EngineAcceptSampleData *)v18);
    return 2147942487LL;
  }
  *(_OWORD *)v15 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v15);
  v8 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x351,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v14);
    if ( v15[1] )
      std::_Ref_count_base::_Decref(v15[1]);
LABEL_30:
    BioIsoProvider::EngineAcceptSampleData::~EngineAcceptSampleData((BioIsoProvider::EngineAcceptSampleData *)v18);
    return (unsigned int)v8;
  }
  BiometricUnit::PipelineObject(v15[0], &v16);
  if ( !v16 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x356,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v14);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    if ( v15[1] )
      std::_Ref_count_base::_Decref(v15[1]);
    BioIsoProvider::EngineAcceptSampleData::~EngineAcceptSampleData((BioIsoProvider::EngineAcceptSampleData *)v18);
    return 2147942487LL;
  }
  v11 = *(_QWORD *)(v9 + 24) + 32LL;
  if ( !v11 || (v12 = *(_QWORD *)(v11 + 32)) == 0 )
  {
    v8 = -2147467261;
    goto LABEL_26;
  }
  v13 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(v12 + 96);
  if ( !v13 )
  {
    v8 = -2147467263;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35E,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)v8,
      v14);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    if ( v15[1] )
      std::_Ref_count_base::_Decref(v15[1]);
    goto LABEL_30;
  }
  v14 = a3;
  LOBYTE(v10) = a2;
  v8 = v13(v11, *(_QWORD *)(v16 + 1240), *(_QWORD *)(v16 + 1248) - *(_QWORD *)(v16 + 1240), v10);
  if ( v8 < 0 )
    goto LABEL_26;
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v18, 0);
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  if ( v15[1] )
    std::_Ref_count_base::_Decref(v15[1]);
  BioIsoProvider::EngineAcceptSampleData::~EngineAcceptSampleData((BioIsoProvider::EngineAcceptSampleData *)v18);
  return 0;
}

```

## disassembly

```asm
0x140019440  push    rbx
0x140019442  push    rsi
0x140019443  push    rdi
0x140019444  sub     rsp, 1C0h
0x14001944b  mov     rax, cs:__security_cookie
0x140019452  xor     rax, rsp
0x140019455  mov     [rsp+1D8h+var_28], rax
0x14001945d  mov     rsi, r8
0x140019460  mov     dil, dl
0x140019463  mov     rbx, rcx
0x140019466  lea     rdx, aEngineacceptsa; "EngineAcceptSampleData"
0x14001946d  lea     rcx, [rsp+1D8h+var_178]
0x140019472  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140019477  lea     rax, ??_7EngineAcceptSampleData@BioIsoProvider@@6B@; const BioIsoProvider::EngineAcceptSampleData::`vftable'
0x14001947e  mov     [rsp+1D8h+var_178], rax
0x140019483  lea     rcx, [rsp+1D8h+var_178]; this
0x140019488  call    ?StartActivity@EngineAcceptSampleData@BioIsoProvider@@QEAAXXZ; BioIsoProvider::EngineAcceptSampleData::StartActivity(void)
0x14001948d  nop
0x14001948e  test    rbx, rbx
0x140019491  jnz     short loc_1400194C6
0x140019493  mov     rcx, [rsp+1D8h]; this
0x14001949b  mov     ebx, 80004003h
0x1400194a0  mov     r9d, ebx; char *
0x1400194a3  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400194aa  mov     edx, 34Bh; void *
0x1400194af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400194b4  nop
0x1400194b5  lea     rcx, [rsp+1D8h+var_178]; this
0x1400194ba  call    ??1EngineAcceptSampleData@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineAcceptSampleData::~EngineAcceptSampleData(void)
0x1400194bf  mov     eax, ebx
0x1400194c1  jmp     loc_14001969D
0x1400194c6  mov     rcx, rbx; void *
0x1400194c9  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x1400194ce  test    al, al
0x1400194d0  jnz     short loc_140019505
0x1400194d2  mov     rcx, [rsp+1D8h]; this
0x1400194da  mov     ebx, 80070057h
0x1400194df  mov     r9d, ebx; char *
0x1400194e2  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400194e9  mov     edx, 34Ch; void *
0x1400194ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400194f3  nop
0x1400194f4  lea     rcx, [rsp+1D8h+var_178]; this
0x1400194f9  call    ??1EngineAcceptSampleData@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineAcceptSampleData::~EngineAcceptSampleData(void)
0x1400194fe  mov     eax, ebx
0x140019500  jmp     loc_14001969D
0x140019505  xorps   xmm0, xmm0
0x140019508  movdqu  xmmword ptr [rsp+1D8h+var_1A0], xmm0
0x14001950e  lea     rdx, [rsp+1D8h+var_1A0]
0x140019513  mov     ecx, [rbx]
0x140019515  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x14001951a  mov     ebx, eax
0x14001951c  test    eax, eax
0x14001951e  jns     short loc_14001955E
0x140019520  mov     rcx, [rsp+1D8h]; this
0x140019528  mov     r9d, eax; char *
0x14001952b  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140019532  mov     edx, 351h; void *
0x140019537  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001953c  nop
0x14001953d  mov     rcx, [rsp+1D8h+var_1A0+8]; this
0x140019542  test    rcx, rcx
0x140019545  jz      short loc_14001954D
0x140019547  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001954c  nop
0x14001954d  lea     rcx, [rsp+1D8h+var_178]; this
0x140019552  call    ??1EngineAcceptSampleData@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineAcceptSampleData::~EngineAcceptSampleData(void)
0x140019557  mov     eax, ebx
0x140019559  jmp     loc_14001969D
0x14001955e  lea     rdx, [rsp+1D8h+var_190]
0x140019563  mov     rcx, [rsp+1D8h+var_1A0]
0x140019568  call    ?PipelineObject@BiometricUnit@@QEBA?AV?$shared_ptr@VPipeline@@@std@@XZ; BiometricUnit::PipelineObject(void)
0x14001956d  mov     r8, [rsp+1D8h+var_190]
0x140019572  test    r8, r8
0x140019575  jnz     short loc_1400195C9
0x140019577  mov     rcx, [rsp+1D8h]; this
0x14001957f  mov     ebx, 80070057h
0x140019584  mov     r9d, ebx; char *
0x140019587  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14001958e  mov     edx, 356h; void *
0x140019593  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019598  mov     rcx, [rsp+1D8h+var_188]; this
0x14001959d  test    rcx, rcx
0x1400195a0  jz      short loc_1400195A8
0x1400195a2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400195a7  nop
0x1400195a8  mov     rcx, [rsp+1D8h+var_1A0+8]; this
0x1400195ad  test    rcx, rcx
0x1400195b0  jz      short loc_1400195B8
0x1400195b2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400195b7  nop
0x1400195b8  lea     rcx, [rsp+1D8h+var_178]; this
0x1400195bd  call    ??1EngineAcceptSampleData@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineAcceptSampleData::~EngineAcceptSampleData(void)
0x1400195c2  mov     eax, ebx
0x1400195c4  jmp     loc_14001969D
0x1400195c9  mov     rcx, [rcx+18h]
0x1400195cd  add     rcx, 20h ; ' '
0x1400195d1  jz      short loc_14001964A
0x1400195d3  mov     rax, [rcx+20h]
0x1400195d7  test    rax, rax
0x1400195da  jz      short loc_14001964A
0x1400195dc  mov     rax, [rax+60h]
0x1400195e0  test    rax, rax
0x1400195e3  jnz     short loc_1400195EC
0x1400195e5  mov     ebx, 80004001h
0x1400195ea  jmp     short loc_14001964F
0x1400195ec  mov     rdx, [r8+4D8h]
0x1400195f3  mov     r8, [r8+4E0h]
0x1400195fa  sub     r8, rdx
0x1400195fd  mov     qword ptr [rsp+1D8h+var_1B8], rsi
0x140019602  mov     r9b, dil
0x140019605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001960a  mov     ebx, eax
0x14001960c  test    eax, eax
0x14001960e  js      short loc_14001964F
0x140019610  xor     edx, edx
0x140019612  lea     rcx, [rsp+1D8h+var_178]
0x140019617  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14001961c  mov     rcx, [rsp+1D8h+var_188]; this
0x140019621  test    rcx, rcx
0x140019624  jz      short loc_14001962C
0x140019626  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001962b  nop
0x14001962c  mov     rcx, [rsp+1D8h+var_1A0+8]; this
0x140019631  test    rcx, rcx
0x140019634  jz      short loc_14001963C
0x140019636  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001963b  nop
0x14001963c  lea     rcx, [rsp+1D8h+var_178]; this
0x140019641  call    ??1EngineAcceptSampleData@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineAcceptSampleData::~EngineAcceptSampleData(void)
0x140019646  xor     eax, eax
0x140019648  jmp     short loc_14001969D
0x14001964a  mov     ebx, 80004003h
0x14001964f  mov     rcx, [rsp+1D8h]; this
0x140019657  mov     r9d, ebx; char *
0x14001965a  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140019661  mov     edx, 35Eh; void *
0x140019666  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001966b  mov     rcx, [rsp+1D8h+var_188]; this
0x140019670  test    rcx, rcx
0x140019673  jz      short loc_14001967B
0x140019675  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001967a  nop
0x14001967b  mov     rcx, [rsp+1D8h+var_1A0+8]; this
0x140019680  test    rcx, rcx
0x140019683  jz      short loc_14001968B
0x140019685  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001968a  nop
0x14001968b  lea     rcx, [rsp+1D8h+var_178]; this
0x140019690  call    ??1EngineAcceptSampleData@BioIsoProvider@@QEAA@XZ; BioIsoProvider::EngineAcceptSampleData::~EngineAcceptSampleData(void)
0x140019695  mov     eax, ebx
0x140019697  jmp     short loc_14001969D
0x140019699  mov     eax, [rsp+1D8h+var_1A8]
0x14001969d  mov     rcx, [rsp+1D8h+var_28]
0x1400196a5  xor     rcx, rsp; StackCookie
0x1400196a8  call    __security_check_cookie
0x1400196ad  add     rsp, 1C0h
0x1400196b4  pop     rdi
0x1400196b5  pop     rsi
0x1400196b6  pop     rbx
0x1400196b7  retn
```
