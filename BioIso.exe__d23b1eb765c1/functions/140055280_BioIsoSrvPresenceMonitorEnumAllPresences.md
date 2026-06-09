# BioIsoSrvPresenceMonitorEnumAllPresences

- ea: `0x140055280`
- end: `0x1400557ec`
- name: `BioIsoSrvPresenceMonitorEnumAllPresences`
- size: `1388`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x14000791c`
- `0x140007ed4`
- `0x14000a2e4`
- `0x14000a31c`
- `0x14000a420`
- `0x14000acd4`
- `0x14000ad00`
- `0x14000ae0c`
- `0x14001bd40`
- `0x140040954`
- `0x140041168`
- `0x140041194`
- `0x140041648`
- `0x140041968`
- `0x140054088`
- `0x140055280`
- `0x1400597d4`
- `0x140059830`
- `0x14005cf30`
- `0x140061b30`
- `0x140085010`

## string_xrefs

- `0x1400552fd`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140055349`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400553bc`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140055467`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140055505`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140055579`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400557a3`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall BioIsoSrvPresenceMonitorEnumAllPresences(int *a1, _QWORD *a2, _QWORD *a3, _DWORD *a4)
{
  int BiometricUnit; // eax
  unsigned int v10; // ebx
  int v11; // eax
  unsigned int v12; // ebx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rcx
  unsigned int *i; // rbx
  unsigned int *v16; // rsi
  unsigned __int128 v17; // kr10_16
  int EnrollmentId; // eax
  unsigned int v19; // edi
  unsigned int v20; // edx
  char v21; // al
  int v22; // r8d
  int v23; // eax
  unsigned __int64 v24; // rax
  char *v25; // r9
  unsigned int v26; // edx
  __int64 v27; // r11
  _OWORD *v28; // rcx
  _OWORD *v29; // r8
  _OWORD *v30; // rax
  _OWORD *v31; // rdx
  __int64 v32; // r10
  char *v33; // rdx
  _OWORD *v34; // rax
  __int64 v35; // r10
  unsigned __int64 v36; // rcx
  void *v37; // rcx
  unsigned int v38; // edx
  int v39; // [rsp+20h] [rbp-3D8h] BYREF
  void *v40; // [rsp+28h] [rbp-3D0h] BYREF
  __int128 v41; // [rsp+30h] [rbp-3C8h] BYREF
  __int64 v42; // [rsp+40h] [rbp-3B8h]
  std::_Ref_count_base *v43[2]; // [rsp+48h] [rbp-3B0h] BYREF
  __int128 v44; // [rsp+58h] [rbp-3A0h] BYREF
  __int64 v45; // [rsp+68h] [rbp-390h]
  _BYTE v46[496]; // [rsp+70h] [rbp-388h] BYREF
  _BYTE v47[336]; // [rsp+260h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3F8h] [rbp+0h]

  BioIsoProvider::PresenceMonitorEnumAll::Start<>((BioIsoProvider::PresenceMonitorEnumAll *)v47);
  if ( !a1 || !a2 || !a3 || !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9CB,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v39);
    BioIsoProvider::PresenceMonitorEnumAll::~PresenceMonitorEnumAll((BioIsoProvider::PresenceMonitorEnumAll *)v47);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle((unsigned __int64)a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9CC,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v39);
    BioIsoProvider::PresenceMonitorEnumAll::~PresenceMonitorEnumAll((BioIsoProvider::PresenceMonitorEnumAll *)v47);
    return 2147942487LL;
  }
  *(_OWORD *)v43 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v43);
  v10 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9D2,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v39);
    if ( v43[1] )
      std::_Ref_count_base::_Decref(v43[1]);
    BioIsoProvider::PresenceMonitorEnumAll::~PresenceMonitorEnumAll((BioIsoProvider::PresenceMonitorEnumAll *)v47);
    return v10;
  }
  v41 = 0;
  v42 = 0;
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)v43[0] + 5) + 32LL))(
          *((_QWORD *)v43[0] + 5),
          &v41);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9D7,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)v11,
      v39);
    std::vector<_WINBIO_PRESENCE>::_Tidy(&v41);
    if ( v43[1] )
      std::_Ref_count_base::_Decref(v43[1]);
    BioIsoProvider::PresenceMonitorEnumAll::~PresenceMonitorEnumAll((BioIsoProvider::PresenceMonitorEnumAll *)v47);
    return v12;
  }
  std::make_unique<KeyReleaseAuthzContext,,0>(&v40);
  __SET_PAIR__(v13, v14, v41);
  v17 = v41;
  v16 = (unsigned int *)(v17 >> 64);
  for ( i = (unsigned int *)v17; i != v16; i += 124 )
  {
    if ( (i[2] & 0x80000000) == 0 && i[4] == 3 )
    {
      v44 = 0;
      v45 = 0;
      EnrollmentId = GenerateEnrollmentId(*i, (__int64)(i + 4), (__int64)&v44);
      v19 = EnrollmentId;
      if ( EnrollmentId < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9EA,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
          (const char *)(unsigned int)EnrollmentId,
          v39);
        std::vector<unsigned char>::_Tidy((__int64)&v44);
        std::unique_ptr<KeyReleaseAuthzContext>::~unique_ptr<KeyReleaseAuthzContext>(
          (KeyReleaseAuthzContext **)&v40,
          v20);
        std::vector<_WINBIO_PRESENCE>::_Tidy(&v41);
        if ( v43[1] )
          std::_Ref_count_base::_Decref(v43[1]);
        BioIsoProvider::PresenceMonitorEnumAll::~PresenceMonitorEnumAll((BioIsoProvider::PresenceMonitorEnumAll *)v47);
        return v19;
      }
      v21 = VsmUtils::Velocity::IsEnabled<wil::Feature<__WilFeatureTraits_Feature_AddLoggingForFaceAuthErrors>>();
      v22 = DWORD2(v44) - v44;
      if ( v21 )
      {
        v39 = KeyReleaseAuthzContext::Add((__int64)v40, v44, v22, 0);
        BioIsoProvider::AuthorizationForRecognizedPresence<long &>(&v39);
      }
      else
      {
        v23 = KeyReleaseAuthzContext::Add((__int64)v40, v44, v22, 0);
        if ( v23 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x9F6,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
            (const char *)(unsigned int)v23,
            v39);
      }
      std::vector<unsigned char>::_Tidy((__int64)&v44);
      v13 = *((_QWORD *)&v41 + 1);
      v14 = v41;
    }
  }
  v24 = 0xEF7BDEF7BDEF7BDFuLL * ((__int64)(v13 - v14) >> 4);
  if ( v24 )
  {
    v25 = (char *)MIDL_user_allocate(496 * v24);
    if ( !v25 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9FE,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
        (const char *)0x8007000ELL,
        v39);
      std::unique_ptr<KeyReleaseAuthzContext>::~unique_ptr<KeyReleaseAuthzContext>((KeyReleaseAuthzContext **)&v40, v26);
      std::vector<_WINBIO_PRESENCE>::_Tidy(&v41);
      if ( v43[1] )
        std::_Ref_count_base::_Decref(v43[1]);
      BioIsoProvider::PresenceMonitorEnumAll::~PresenceMonitorEnumAll((BioIsoProvider::PresenceMonitorEnumAll *)v47);
      return 2147942414LL;
    }
    v27 = 0;
    v28 = (_OWORD *)*((_QWORD *)&v41 + 1);
    v29 = (_OWORD *)v41;
    if ( (_QWORD)v41 != *((_QWORD *)&v41 + 1) )
    {
      do
      {
        v30 = v29;
        v31 = v46;
        v32 = 3;
        do
        {
          *v31 = *v30;
          v31[1] = v30[1];
          v31[2] = v30[2];
          v31[3] = v30[3];
          v31[4] = v30[4];
          v31[5] = v30[5];
          v31[6] = v30[6];
          v31[7] = v30[7];
          v31 += 8;
          v30 += 8;
          --v32;
        }
        while ( v32 );
        *v31 = *v30;
        v31[1] = v30[1];
        v31[2] = v30[2];
        v31[3] = v30[3];
        v31[4] = v30[4];
        v31[5] = v30[5];
        v31[6] = v30[6];
        v33 = &v25[496 * v27];
        v34 = v46;
        v35 = 3;
        do
        {
          *(_OWORD *)v33 = *v34;
          *((_OWORD *)v33 + 1) = v34[1];
          *((_OWORD *)v33 + 2) = v34[2];
          *((_OWORD *)v33 + 3) = v34[3];
          *((_OWORD *)v33 + 4) = v34[4];
          *((_OWORD *)v33 + 5) = v34[5];
          *((_OWORD *)v33 + 6) = v34[6];
          *((_OWORD *)v33 + 7) = v34[7];
          v33 += 128;
          v34 += 8;
          --v35;
        }
        while ( v35 );
        *(_OWORD *)v33 = *v34;
        *((_OWORD *)v33 + 1) = v34[1];
        *((_OWORD *)v33 + 2) = v34[2];
        *((_OWORD *)v33 + 3) = v34[3];
        *((_OWORD *)v33 + 4) = v34[4];
        *((_OWORD *)v33 + 5) = v34[5];
        *((_OWORD *)v33 + 6) = v34[6];
        ++v27;
        v29 += 31;
      }
      while ( v29 != v28 );
      v28 = (_OWORD *)*((_QWORD *)&v41 + 1);
      v29 = (_OWORD *)v41;
    }
    v36 = 0xEF7BDEF7BDEF7BDFuLL * (v28 - v29);
  }
  else
  {
    LODWORD(v36) = 0;
    v25 = 0;
  }
  *a3 = v25;
  *a4 = v36;
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v47, 0);
  v37 = v40;
  v40 = 0;
  *a2 = v37;
  HardwareManager::AddHandle(v37);
  std::unique_ptr<KeyReleaseAuthzContext>::~unique_ptr<KeyReleaseAuthzContext>((KeyReleaseAuthzContext **)&v40, v38);
  std::vector<_WINBIO_PRESENCE>::_Tidy(&v41);
  if ( v43[1] )
    std::_Ref_count_base::_Decref(v43[1]);
  BioIsoProvider::PresenceMonitorEnumAll::~PresenceMonitorEnumAll((BioIsoProvider::PresenceMonitorEnumAll *)v47);
  return 0;
}

```

## disassembly

```asm
0x140055280  push    rbx
0x140055282  push    rsi
0x140055283  push    rdi
0x140055284  push    r12
0x140055286  push    r14
0x140055288  push    r15
0x14005528a  sub     rsp, 3C8h
0x140055291  mov     rax, cs:__security_cookie
0x140055298  xor     rax, rsp
0x14005529b  mov     [rsp+3F8h+var_48], rax
0x1400552a3  mov     r14, r9
0x1400552a6  mov     r12, r8
0x1400552a9  mov     r15, rdx
0x1400552ac  mov     rbx, rcx
0x1400552af  lea     rcx, [rsp+3F8h+var_198]; this
0x1400552b7  call    ??$Start@$$V@PresenceMonitorEnumAll@BioIsoProvider@@SA?AV01@XZ; BioIsoProvider::PresenceMonitorEnumAll::Start<>(void)
0x1400552bc  nop
0x1400552bd  test    rbx, rbx
0x1400552c0  jz      loc_140055793
0x1400552c6  test    r15, r15
0x1400552c9  jz      loc_140055793
0x1400552cf  test    r12, r12
0x1400552d2  jz      loc_140055793
0x1400552d8  test    r14, r14
0x1400552db  jz      loc_140055793
0x1400552e1  mov     rcx, rbx; void *
0x1400552e4  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x1400552e9  test    al, al
0x1400552eb  jnz     short loc_140055323
0x1400552ed  mov     rcx, [rsp+3F8h]; this
0x1400552f5  mov     ebx, 80070057h
0x1400552fa  mov     r9d, ebx; char *
0x1400552fd  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140055304  mov     edx, 9CCh; void *
0x140055309  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005530e  nop
0x14005530f  lea     rcx, [rsp+3F8h+var_198]; this
0x140055317  call    ??1PresenceMonitorEnumAll@BioIsoProvider@@QEAA@XZ; BioIsoProvider::PresenceMonitorEnumAll::~PresenceMonitorEnumAll(void)
0x14005531c  mov     eax, ebx
0x14005531e  jmp     loc_1400557CA
0x140055323  xorps   xmm0, xmm0
0x140055326  movdqu  xmmword ptr [rsp+3F8h+var_3B0], xmm0
0x14005532c  lea     rdx, [rsp+3F8h+var_3B0]
0x140055331  mov     ecx, [rbx]
0x140055333  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x140055338  mov     ebx, eax
0x14005533a  test    eax, eax
0x14005533c  jns     short loc_14005537F
0x14005533e  mov     rcx, [rsp+3F8h]; this
0x140055346  mov     r9d, eax; char *
0x140055349  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140055350  mov     edx, 9D2h; void *
0x140055355  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005535a  nop
0x14005535b  mov     rcx, [rsp+3F8h+var_3B0+8]; this
0x140055360  test    rcx, rcx
0x140055363  jz      short loc_14005536B
0x140055365  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14005536a  nop
0x14005536b  lea     rcx, [rsp+3F8h+var_198]; this
0x140055373  call    ??1PresenceMonitorEnumAll@BioIsoProvider@@QEAA@XZ; BioIsoProvider::PresenceMonitorEnumAll::~PresenceMonitorEnumAll(void)
0x140055378  mov     eax, ebx
0x14005537a  jmp     loc_1400557CA
0x14005537f  xorps   xmm0, xmm0
0x140055382  movdqu  [rsp+3F8h+var_3C8], xmm0
0x140055388  mov     [rsp+3F8h+var_3B8], 0
0x140055391  mov     rax, [rsp+3F8h+var_3B0]
0x140055396  mov     rcx, [rax+28h]
0x14005539a  mov     rax, [rcx]
0x14005539d  lea     rdx, [rsp+3F8h+var_3C8]
0x1400553a2  mov     rax, [rax+20h]
0x1400553a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400553ab  mov     ebx, eax
0x1400553ad  test    eax, eax
0x1400553af  jns     short loc_1400553FD
0x1400553b1  mov     rcx, [rsp+3F8h]; this
0x1400553b9  mov     r9d, eax; char *
0x1400553bc  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400553c3  mov     edx, 9D7h; void *
0x1400553c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400553cd  nop
0x1400553ce  lea     rcx, [rsp+3F8h+var_3C8]
0x1400553d3  call    ?_Tidy@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@AEAAXXZ; std::vector<_WINBIO_PRESENCE>::_Tidy(void)
0x1400553d8  nop
0x1400553d9  mov     rcx, [rsp+3F8h+var_3B0+8]; this
0x1400553de  test    rcx, rcx
0x1400553e1  jz      short loc_1400553E9
0x1400553e3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400553e8  nop
0x1400553e9  lea     rcx, [rsp+3F8h+var_198]; this
0x1400553f1  call    ??1PresenceMonitorEnumAll@BioIsoProvider@@QEAA@XZ; BioIsoProvider::PresenceMonitorEnumAll::~PresenceMonitorEnumAll(void)
0x1400553f6  mov     eax, ebx
0x1400553f8  jmp     loc_1400557CA
0x1400553fd  lea     rcx, [rsp+3F8h+var_3D0]
0x140055402  call    ??$make_unique@VKeyReleaseAuthzContext@@$$V$0A@@std@@YA?AV?$unique_ptr@VKeyReleaseAuthzContext@@U?$default_delete@VKeyReleaseAuthzContext@@@std@@@0@XZ; std::make_unique<KeyReleaseAuthzContext,,0>(void)
0x140055407  nop
0x140055408  mov     rcx, qword ptr [rsp+3F8h+var_3C8]
0x14005540d  mov     rbx, rcx
0x140055410  mov     rax, qword ptr [rsp+3F8h+var_3C8+8]
0x140055415  mov     rsi, rax
0x140055418  cmp     rbx, rsi
0x14005541b  jz      loc_140055537
0x140055421  cmp     dword ptr [rbx+8], 0
0x140055425  jl      loc_14005552B
0x14005542b  lea     rdx, [rbx+10h]
0x14005542f  cmp     dword ptr [rdx], 3
0x140055432  jnz     loc_14005552B
0x140055438  xorps   xmm0, xmm0
0x14005543b  movdqu  [rsp+3F8h+var_3A0], xmm0
0x140055441  mov     [rsp+3F8h+var_390], 0
0x14005544a  lea     r8, [rsp+3F8h+var_3A0]
0x14005544f  mov     ecx, [rbx]
0x140055451  call    ?GenerateEnrollmentId@@YAJIPEBU_WINBIO_IDENTITY@@PEAV?$vector@EV?$allocator@E@std@@@std@@@Z; GenerateEnrollmentId(uint,_WINBIO_IDENTITY const *,std::vector<uchar> *)
0x140055456  mov     edi, eax
0x140055458  test    eax, eax
0x14005545a  jns     short loc_1400554BE
0x14005545c  mov     rcx, [rsp+3F8h]; this
0x140055464  mov     r9d, eax; char *
0x140055467  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14005546e  mov     edx, 9EAh; void *
0x140055473  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140055478  nop
0x140055479  lea     rcx, [rsp+3F8h+var_3A0]
0x14005547e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140055483  nop
0x140055484  lea     rcx, [rsp+3F8h+var_3D0]
0x140055489  call    ??1?$unique_ptr@VKeyReleaseAuthzContext@@U?$default_delete@VKeyReleaseAuthzContext@@@std@@@std@@QEAA@XZ; std::unique_ptr<KeyReleaseAuthzContext>::~unique_ptr<KeyReleaseAuthzContext>(void)
0x14005548e  nop
0x14005548f  lea     rcx, [rsp+3F8h+var_3C8]
0x140055494  call    ?_Tidy@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@AEAAXXZ; std::vector<_WINBIO_PRESENCE>::_Tidy(void)
0x140055499  nop
0x14005549a  mov     rcx, [rsp+3F8h+var_3B0+8]; this
0x14005549f  test    rcx, rcx
0x1400554a2  jz      short loc_1400554AA
0x1400554a4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400554a9  nop
0x1400554aa  lea     rcx, [rsp+3F8h+var_198]; this
0x1400554b2  call    ??1PresenceMonitorEnumAll@BioIsoProvider@@QEAA@XZ; BioIsoProvider::PresenceMonitorEnumAll::~PresenceMonitorEnumAll(void)
0x1400554b7  mov     eax, edi
0x1400554b9  jmp     loc_1400557CA
0x1400554be  call    ??$IsEnabled@V?$Feature@U__WilFeatureTraits_Feature_AddLoggingForFaceAuthErrors@@@wil@@@Velocity@VsmUtils@@SA_NXZ; VsmUtils::Velocity::IsEnabled<wil::Feature<__WilFeatureTraits_Feature_AddLoggingForFaceAuthErrors>>(void)
0x1400554c3  mov     r8, qword ptr [rsp+3F8h+var_3A0+8]
0x1400554c8  mov     rdx, qword ptr [rsp+3F8h+var_3A0]
0x1400554cd  xor     r9d, r9d
0x1400554d0  mov     rcx, [rsp+3F8h+var_3D0]
0x1400554d5  sub     r8, rdx
0x1400554d8  test    al, al
0x1400554da  jz      short loc_1400554F1
0x1400554dc  call    ?Add@KeyReleaseAuthzContext@@QEAAJPEBE_KPEAV?$vector@EV?$allocator@E@std@@@std@@@Z; KeyReleaseAuthzContext::Add(uchar const *,unsigned __int64,std::vector<uchar> *)
0x1400554e1  mov     [rsp+3F8h+var_3D8], eax
0x1400554e5  lea     rcx, [rsp+3F8h+var_3D8]
0x1400554ea  call    ??$AuthorizationForRecognizedPresence@AEAJ@BioIsoProvider@@SAXAEAJ@Z; BioIsoProvider::AuthorizationForRecognizedPresence<long &>(long &)
0x1400554ef  jmp     short loc_140055517
0x1400554f1  call    ?Add@KeyReleaseAuthzContext@@QEAAJPEBE_KPEAV?$vector@EV?$allocator@E@std@@@std@@@Z; KeyReleaseAuthzContext::Add(uchar const *,unsigned __int64,std::vector<uchar> *)
0x1400554f6  mov     rcx, [rsp+3F8h]; this
0x1400554fe  test    eax, eax
0x140055500  jns     short loc_140055517
0x140055502  mov     r9d, eax; char *
0x140055505  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14005550c  mov     edx, 9F6h; void *
0x140055511  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140055516  nop
0x140055517  lea     rcx, [rsp+3F8h+var_3A0]
0x14005551c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140055521  mov     rax, qword ptr [rsp+3F8h+var_3C8+8]
0x140055526  mov     rcx, qword ptr [rsp+3F8h+var_3C8]
0x14005552b  add     rbx, 1F0h
0x140055532  jmp     loc_140055418
0x140055537  sub     rax, rcx
0x14005553a  sar     rax, 4
0x14005553e  mov     rdi, 0EF7BDEF7BDEF7BDFh
0x140055548  imul    rax, rdi
0x14005554c  test    rax, rax
0x14005554f  jz      loc_14005572A
0x140055555  imul    rcx, rax, 1F0h; size
0x14005555c  call    MIDL_user_allocate
0x140055561  mov     r9, rax
0x140055564  test    rax, rax
0x140055567  jnz     short loc_1400555C5
0x140055569  mov     rcx, [rsp+3F8h]; this
0x140055571  mov     ebx, 8007000Eh
0x140055576  mov     r9d, ebx; char *
0x140055579  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140055580  mov     edx, 9FEh; void *
0x140055585  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005558a  nop
0x14005558b  lea     rcx, [rsp+3F8h+var_3D0]
0x140055590  call    ??1?$unique_ptr@VKeyReleaseAuthzContext@@U?$default_delete@VKeyReleaseAuthzContext@@@std@@@std@@QEAA@XZ; std::unique_ptr<KeyReleaseAuthzContext>::~unique_ptr<KeyReleaseAuthzContext>(void)
0x140055595  nop
0x140055596  lea     rcx, [rsp+3F8h+var_3C8]
0x14005559b  call    ?_Tidy@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@AEAAXXZ; std::vector<_WINBIO_PRESENCE>::_Tidy(void)
0x1400555a0  nop
0x1400555a1  mov     rcx, [rsp+3F8h+var_3B0+8]; this
0x1400555a6  test    rcx, rcx
0x1400555a9  jz      short loc_1400555B1
0x1400555ab  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400555b0  nop
0x1400555b1  lea     rcx, [rsp+3F8h+var_198]; this
0x1400555b9  call    ??1PresenceMonitorEnumAll@BioIsoProvider@@QEAA@XZ; BioIsoProvider::PresenceMonitorEnumAll::~PresenceMonitorEnumAll(void)
0x1400555be  mov     eax, ebx
0x1400555c0  jmp     loc_1400557CA
0x1400555c5  xor     r11d, r11d
0x1400555c8  mov     r8, qword ptr [rsp+3F8h+var_3C8]
0x1400555cd  mov     rcx, qword ptr [rsp+3F8h+var_3C8+8]
0x1400555d2  cmp     r8, rcx
0x1400555d5  jz      loc_14005571D
0x1400555db  mov     ebx, 80h
0x1400555e0  lea     esi, [rbx-7Dh]
0x1400555e3  mov     rax, r8
0x1400555e6  lea     rdx, [rsp+3F8h+var_388]
0x1400555eb  mov     r10, rsi
0x1400555ee  movups  xmm0, xmmword ptr [rax]
0x1400555f1  movups  xmmword ptr [rdx], xmm0
0x1400555f4  movups  xmm1, xmmword ptr [rax+10h]
0x1400555f8  movups  xmmword ptr [rdx+10h], xmm1
0x1400555fc  movups  xmm0, xmmword ptr [rax+20h]
0x140055600  movups  xmmword ptr [rdx+20h], xmm0
0x140055604  movups  xmm1, xmmword ptr [rax+30h]
0x140055608  movups  xmmword ptr [rdx+30h], xmm1
0x14005560c  movups  xmm0, xmmword ptr [rax+40h]
0x140055610  movups  xmmword ptr [rdx+40h], xmm0
0x140055614  movups  xmm1, xmmword ptr [rax+50h]
0x140055618  movups  xmmword ptr [rdx+50h], xmm1
0x14005561c  movups  xmm0, xmmword ptr [rax+60h]
0x140055620  movups  xmmword ptr [rdx+60h], xmm0
0x140055624  movups  xmm1, xmmword ptr [rax+70h]
0x140055628  movups  xmmword ptr [rdx+70h], xmm1
0x14005562c  add     rdx, rbx
0x14005562f  add     rax, rbx
0x140055632  sub     r10, 1
0x140055636  jnz     short loc_1400555EE
0x140055638  movups  xmm0, xmmword ptr [rax]
0x14005563b  movups  xmmword ptr [rdx], xmm0
0x14005563e  movups  xmm1, xmmword ptr [rax+10h]
0x140055642  movups  xmmword ptr [rdx+10h], xmm1
0x140055646  movups  xmm0, xmmword ptr [rax+20h]
0x14005564a  movups  xmmword ptr [rdx+20h], xmm0
0x14005564e  movups  xmm1, xmmword ptr [rax+30h]
0x140055652  movups  xmmword ptr [rdx+30h], xmm1
0x140055656  movups  xmm0, xmmword ptr [rax+40h]
0x14005565a  movups  xmmword ptr [rdx+40h], xmm0
0x14005565e  movups  xmm1, xmmword ptr [rax+50h]
0x140055662  movups  xmmword ptr [rdx+50h], xmm1
0x140055666  movups  xmm0, xmmword ptr [rax+60h]
0x14005566a  movups  xmmword ptr [rdx+60h], xmm0
0x14005566e  imul    rdx, r11, 1F0h
0x140055675  add     rdx, r9
0x140055678  lea     rax, [rsp+3F8h+var_388]
0x14005567d  mov     r10, rsi
0x140055680  movups  xmm0, xmmword ptr [rax]
0x140055683  movups  xmmword ptr [rdx], xmm0
0x140055686  movups  xmm1, xmmword ptr [rax+10h]
0x14005568a  movups  xmmword ptr [rdx+10h], xmm1
0x14005568e  movups  xmm0, xmmword ptr [rax+20h]
0x140055692  movups  xmmword ptr [rdx+20h], xmm0
0x140055696  movups  xmm1, xmmword ptr [rax+30h]
0x14005569a  movups  xmmword ptr [rdx+30h], xmm1
0x14005569e  movups  xmm0, xmmword ptr [rax+40h]
0x1400556a2  movups  xmmword ptr [rdx+40h], xmm0
0x1400556a6  movups  xmm1, xmmword ptr [rax+50h]
0x1400556aa  movups  xmmword ptr [rdx+50h], xmm1
0x1400556ae  movups  xmm0, xmmword ptr [rax+60h]
0x1400556b2  movups  xmmword ptr [rdx+60h], xmm0
0x1400556b6  movups  xmm1, xmmword ptr [rax+70h]
0x1400556ba  movups  xmmword ptr [rdx+70h], xmm1
0x1400556be  add     rdx, rbx
0x1400556c1  add     rax, rbx
0x1400556c4  sub     r10, 1
0x1400556c8  jnz     short loc_140055680
0x1400556ca  movups  xmm0, xmmword ptr [rax]
0x1400556cd  movups  xmmword ptr [rdx], xmm0
0x1400556d0  movups  xmm1, xmmword ptr [rax+10h]
0x1400556d4  movups  xmmword ptr [rdx+10h], xmm1
0x1400556d8  movups  xmm0, xmmword ptr [rax+20h]
0x1400556dc  movups  xmmword ptr [rdx+20h], xmm0
0x1400556e0  movups  xmm1, xmmword ptr [rax+30h]
0x1400556e4  movups  xmmword ptr [rdx+30h], xmm1
0x1400556e8  movups  xmm0, xmmword ptr [rax+40h]
0x1400556ec  movups  xmmword ptr [rdx+40h], xmm0
0x1400556f0  movups  xmm1, xmmword ptr [rax+50h]
0x1400556f4  movups  xmmword ptr [rdx+50h], xmm1
0x1400556f8  movups  xmm0, xmmword ptr [rax+60h]
0x1400556fc  movups  xmmword ptr [rdx+60h], xmm0
0x140055700  inc     r11
0x140055703  add     r8, 1F0h
0x14005570a  cmp     r8, rcx
0x14005570d  jnz     loc_1400555E3
0x140055713  mov     rcx, qword ptr [rsp+3F8h+var_3C8+8]
0x140055718  mov     r8, qword ptr [rsp+3F8h+var_3C8]
0x14005571d  sub     rcx, r8
0x140055720  sar     rcx, 4
0x140055724  imul    rcx, rdi
0x140055728  jmp     short loc_14005572F
0x14005572a  xor     ecx, ecx
0x14005572c  xor     r9d, r9d
0x14005572f  mov     [r12], r9
0x140055733  mov     [r14], ecx
0x140055736  xor     edx, edx
0x140055738  lea     rcx, [rsp+3F8h+var_198]
0x140055740  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
  ... truncated ...
```
