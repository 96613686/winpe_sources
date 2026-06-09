# BioIsoSrvPresenceMonitorGetChanges

- ea: `0x140055800`
- end: `0x140056771`
- name: `BioIsoSrvPresenceMonitorGetChanges`
- size: `3953`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x14000791c`
- `0x140007ed4`
- `0x14000a2e4`
- `0x14000a31c`
- `0x14000a420`
- `0x14000ad00`
- `0x14000ae0c`
- `0x140012974`
- `0x140013380`
- `0x14001bd40`
- `0x140040954`
- `0x140041168`
- `0x140041194`
- `0x140041968`
- `0x140041d78`
- `0x140045410`
- `0x140054088`
- `0x140055800`
- `0x1400597d4`
- `0x140059830`
- `0x14005cf30`
- `0x140061b30`
- `0x140085010`

## string_xrefs

- `0x140055941`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14005598d`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140055a4f`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140055b29`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140055bff`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140055ccf`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140055f1c`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14005615d`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400563a4`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140056726`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall BioIsoSrvPresenceMonitorGetChanges(
        int *a1,
        _QWORD *a2,
        void **a3,
        _DWORD *a4,
        void **a5,
        _DWORD *a6,
        void **a7,
        _DWORD *a8,
        void **a9,
        _DWORD *a10)
{
  int BiometricUnit; // eax
  unsigned int v15; // ebx
  int v16; // eax
  unsigned int v17; // ebx
  unsigned int *i; // rbx
  unsigned int *v19; // rsi
  int EnrollmentId; // eax
  unsigned int v21; // edi
  unsigned int v22; // edx
  char v23; // al
  int v24; // r8d
  int v25; // eax
  unsigned int v26; // edx
  __int64 v27; // r10
  _OWORD *j; // r8
  _OWORD *v29; // r9
  _OWORD *v30; // rax
  _OWORD *v31; // rcx
  __int64 v32; // rdx
  _OWORD *v33; // rdx
  _OWORD *v34; // rax
  __int64 v35; // rcx
  unsigned int v36; // edx
  __int64 v37; // r10
  _OWORD *k; // r8
  _OWORD *v39; // r9
  _OWORD *v40; // rax
  _OWORD *v41; // rcx
  __int64 v42; // rdx
  _OWORD *v43; // rdx
  _OWORD *v44; // rax
  __int64 v45; // rcx
  unsigned int v46; // edx
  __int64 v47; // r10
  _OWORD *m; // r8
  _OWORD *v49; // r9
  _OWORD *v50; // rax
  _OWORD *v51; // rcx
  __int64 v52; // rdx
  _OWORD *v53; // rdx
  _OWORD *v54; // rax
  __int64 v55; // rcx
  _OWORD *v56; // rdx
  _OWORD *v57; // r9
  unsigned int v58; // edx
  __int64 v59; // r10
  _OWORD *v60; // rax
  _OWORD *v61; // rcx
  __int64 v62; // r8
  _OWORD *v63; // r8
  _OWORD *v64; // rax
  __int64 v65; // rcx
  unsigned __int64 v66; // rcx
  unsigned __int64 v67; // rcx
  unsigned __int64 v68; // rcx
  unsigned __int64 v69; // rdx
  void *v70; // rcx
  unsigned int v71; // edx
  int v72; // [rsp+20h] [rbp-488h]
  int *v73; // [rsp+20h] [rbp-488h]
  void *v74; // [rsp+30h] [rbp-478h] BYREF
  void *v75; // [rsp+38h] [rbp-470h] BYREF
  void *v76; // [rsp+40h] [rbp-468h] BYREF
  void *v77; // [rsp+48h] [rbp-460h] BYREF
  void *v78; // [rsp+50h] [rbp-458h] BYREF
  int v79; // [rsp+58h] [rbp-450h] BYREF
  __int128 v80; // [rsp+60h] [rbp-448h] BYREF
  __int64 v81; // [rsp+70h] [rbp-438h]
  std::_Ref_count_base *v82[2]; // [rsp+78h] [rbp-430h] BYREF
  int v83[4]; // [rsp+88h] [rbp-420h] BYREF
  __int64 v84; // [rsp+98h] [rbp-410h]
  __int128 v85; // [rsp+A0h] [rbp-408h] BYREF
  __int64 v86; // [rsp+B0h] [rbp-3F8h]
  __int128 v87; // [rsp+B8h] [rbp-3F0h] BYREF
  __int64 v88; // [rsp+C8h] [rbp-3E0h]
  _DWORD *v89; // [rsp+D0h] [rbp-3D8h]
  _DWORD *v90; // [rsp+D8h] [rbp-3D0h]
  _QWORD *v91; // [rsp+E0h] [rbp-3C8h]
  __int128 v92; // [rsp+E8h] [rbp-3C0h] BYREF
  void **v93; // [rsp+F8h] [rbp-3B0h]
  void **v94; // [rsp+100h] [rbp-3A8h]
  char v95; // [rsp+108h] [rbp-3A0h]
  _DWORD *v96; // [rsp+110h] [rbp-398h]
  _DWORD *v97; // [rsp+118h] [rbp-390h]
  _BYTE v98[496]; // [rsp+120h] [rbp-388h] BYREF
  _QWORD v99[42]; // [rsp+310h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4A8h] [rbp+0h]

  v96 = a4;
  v91 = a2;
  v89 = a6;
  v90 = a8;
  v97 = a10;
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v99,
    (__int64)"PresenceMonitorGetChanges");
  v99[0] = &BioIsoProvider::PresenceMonitorGetChanges::`vftable';
  BioIsoProvider::PresenceMonitorGetChanges::StartActivity((BioIsoProvider::PresenceMonitorGetChanges *)v99);
  if ( !a1 || !v91 || !a3 || !a4 || !a5 || !v89 || !a7 || !v90 || !a9 || !a10 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x903,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v72);
    BioIsoProvider::PresenceMonitorGetChanges::~PresenceMonitorGetChanges((BioIsoProvider::PresenceMonitorGetChanges *)v99);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle((unsigned __int64)a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x905,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      v72);
    BioIsoProvider::PresenceMonitorGetChanges::~PresenceMonitorGetChanges((BioIsoProvider::PresenceMonitorGetChanges *)v99);
    return 2147942487LL;
  }
  *(_OWORD *)v82 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v82);
  v15 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x90B,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      v72);
    if ( v82[1] )
      std::_Ref_count_base::_Decref(v82[1]);
    BioIsoProvider::PresenceMonitorGetChanges::~PresenceMonitorGetChanges((BioIsoProvider::PresenceMonitorGetChanges *)v99);
    return v15;
  }
  v87 = 0;
  v88 = 0;
  v85 = 0;
  v86 = 0;
  v80 = 0;
  v81 = 0;
  *(_OWORD *)v83 = 0;
  v84 = 0;
  v73 = v83;
  v16 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int128 *, __int128 *))(**((_QWORD **)v82[0] + 5) + 16LL))(
          *((_QWORD *)v82[0] + 5),
          &v87,
          &v85,
          &v80);
  v17 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x916,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)v16,
      (int)v83);
    std::vector<_WINBIO_PRESENCE>::_Tidy(v83);
    std::vector<_WINBIO_PRESENCE>::_Tidy(&v80);
    std::vector<_WINBIO_PRESENCE>::_Tidy(&v85);
    std::vector<_WINBIO_PRESENCE>::_Tidy(&v87);
    if ( v82[1] )
      std::_Ref_count_base::_Decref(v82[1]);
    BioIsoProvider::PresenceMonitorGetChanges::~PresenceMonitorGetChanges((BioIsoProvider::PresenceMonitorGetChanges *)v99);
    return v17;
  }
  std::make_unique<KeyReleaseAuthzContext,,0>(&v74);
  v19 = (unsigned int *)*((_QWORD *)&v80 + 1);
  for ( i = (unsigned int *)v80; i != v19; i += 124 )
  {
    if ( (i[2] & 0x80000000) == 0 && i[4] == 3 )
    {
      v92 = 0;
      v93 = 0;
      EnrollmentId = GenerateEnrollmentId(*i, (__int64)(i + 4), (__int64)&v92);
      v21 = EnrollmentId;
      if ( EnrollmentId < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x922,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
          (const char *)(unsigned int)EnrollmentId,
          (int)v73);
        std::vector<unsigned char>::_Tidy((__int64)&v92);
        std::unique_ptr<KeyReleaseAuthzContext>::~unique_ptr<KeyReleaseAuthzContext>(
          (KeyReleaseAuthzContext **)&v74,
          v22);
        std::vector<_WINBIO_PRESENCE>::_Tidy(v83);
        std::vector<_WINBIO_PRESENCE>::_Tidy(&v80);
        std::vector<_WINBIO_PRESENCE>::_Tidy(&v85);
        std::vector<_WINBIO_PRESENCE>::_Tidy(&v87);
        if ( v82[1] )
          std::_Ref_count_base::_Decref(v82[1]);
        BioIsoProvider::PresenceMonitorGetChanges::~PresenceMonitorGetChanges((BioIsoProvider::PresenceMonitorGetChanges *)v99);
        return v21;
      }
      v23 = VsmUtils::Velocity::IsEnabled<wil::Feature<__WilFeatureTraits_Feature_AddLoggingForFaceAuthErrors>>();
      v24 = DWORD2(v92) - v92;
      if ( v23 )
      {
        v79 = KeyReleaseAuthzContext::Add((__int64)v74, v92, v24, 0);
        BioIsoProvider::AuthorizationForRecognizedPresence<long &>(&v79);
      }
      else
      {
        v25 = KeyReleaseAuthzContext::Add((__int64)v74, v92, v24, 0);
        if ( v25 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x92E,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
            (const char *)(unsigned int)v25,
            (int)v73);
      }
      std::vector<unsigned char>::_Tidy((__int64)&v92);
    }
  }
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  *(_QWORD *)&v92 = &v75;
  *((_QWORD *)&v92 + 1) = &v76;
  v93 = &v77;
  v94 = &v78;
  v95 = 1;
  if ( 0xEF7BDEF7BDEF7BDFuLL * ((__int64)(*((_QWORD *)&v87 + 1) - v87) >> 4) )
  {
    v75 = MIDL_user_allocate(16 * ((__int64)(*((_QWORD *)&v87 + 1) - v87) >> 4));
    if ( !v75 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x944,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
        (const char *)0x8007000ELL,
        (int)v73);
      MIDL_user_free(v75);
      MIDL_user_free(v76);
      MIDL_user_free(v77);
      MIDL_user_free(v78);
      std::unique_ptr<KeyReleaseAuthzContext>::~unique_ptr<KeyReleaseAuthzContext>((KeyReleaseAuthzContext **)&v74, v26);
      std::vector<_WINBIO_PRESENCE>::_Tidy(v83);
      std::vector<_WINBIO_PRESENCE>::_Tidy(&v80);
      std::vector<_WINBIO_PRESENCE>::_Tidy(&v85);
      std::vector<_WINBIO_PRESENCE>::_Tidy(&v87);
      if ( v82[1] )
        std::_Ref_count_base::_Decref(v82[1]);
LABEL_73:
      BioIsoProvider::PresenceMonitorGetChanges::~PresenceMonitorGetChanges((BioIsoProvider::PresenceMonitorGetChanges *)v99);
      return 2147942414LL;
    }
    v27 = 0;
    v29 = (_OWORD *)*((_QWORD *)&v87 + 1);
    for ( j = (_OWORD *)v87; j != v29; j += 31 )
    {
      v30 = j;
      v31 = v98;
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
      v33 = (char *)v75 + 496 * v27;
      v34 = v98;
      v35 = 3;
      do
      {
        *v33 = *v34;
        v33[1] = v34[1];
        v33[2] = v34[2];
        v33[3] = v34[3];
        v33[4] = v34[4];
        v33[5] = v34[5];
        v33[6] = v34[6];
        v33[7] = v34[7];
        v33 += 8;
        v34 += 8;
        --v35;
      }
      while ( v35 );
      *v33 = *v34;
      v33[1] = v34[1];
      v33[2] = v34[2];
      v33[3] = v34[3];
      v33[4] = v34[4];
      v33[5] = v34[5];
      v33[6] = v34[6];
      ++v27;
    }
  }
  if ( 0xEF7BDEF7BDEF7BDFuLL * ((__int64)(*((_QWORD *)&v85 + 1) - v85) >> 4) )
  {
    v76 = MIDL_user_allocate(16 * ((__int64)(*((_QWORD *)&v85 + 1) - v85) >> 4));
    if ( !v76 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x950,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
        (const char *)0x8007000ELL,
        (int)v73);
      MIDL_user_free(v75);
      MIDL_user_free(v76);
      MIDL_user_free(v77);
      MIDL_user_free(v78);
      std::unique_ptr<KeyReleaseAuthzContext>::~unique_ptr<KeyReleaseAuthzContext>((KeyReleaseAuthzContext **)&v74, v36);
      std::vector<_WINBIO_PRESENCE>::_Tidy(v83);
      std::vector<_WINBIO_PRESENCE>::_Tidy(&v80);
      std::vector<_WINBIO_PRESENCE>::_Tidy(&v85);
      std::vector<_WINBIO_PRESENCE>::_Tidy(&v87);
      if ( v82[1] )
        std::_Ref_count_base::_Decref(v82[1]);
      goto LABEL_73;
    }
    v37 = 0;
    v39 = (_OWORD *)*((_QWORD *)&v85 + 1);
    for ( k = (_OWORD *)v85; k != v39; k += 31 )
    {
      v40 = k;
      v41 = v98;
      v42 = 3;
      do
      {
        *v41 = *v40;
        v41[1] = v40[1];
        v41[2] = v40[2];
        v41[3] = v40[3];
        v41[4] = v40[4];
        v41[5] = v40[5];
        v41[6] = v40[6];
        v41[7] = v40[7];
        v41 += 8;
        v40 += 8;
        --v42;
      }
      while ( v42 );
      *v41 = *v40;
      v41[1] = v40[1];
      v41[2] = v40[2];
      v41[3] = v40[3];
      v41[4] = v40[4];
      v41[5] = v40[5];
      v41[6] = v40[6];
      v43 = (char *)v76 + 496 * v37;
      v44 = v98;
      v45 = 3;
      do
      {
        *v43 = *v44;
        v43[1] = v44[1];
        v43[2] = v44[2];
        v43[3] = v44[3];
        v43[4] = v44[4];
        v43[5] = v44[5];
        v43[6] = v44[6];
        v43[7] = v44[7];
        v43 += 8;
        v44 += 8;
        --v45;
      }
      while ( v45 );
      *v43 = *v44;
      v43[1] = v44[1];
      v43[2] = v44[2];
      v43[3] = v44[3];
      v43[4] = v44[4];
      v43[5] = v44[5];
      v43[6] = v44[6];
      ++v37;
    }
  }
  if ( 0xEF7BDEF7BDEF7BDFuLL * ((__int64)(*((_QWORD *)&v80 + 1) - v80) >> 4) )
  {
    v77 = MIDL_user_allocate(16 * ((__int64)(*((_QWORD *)&v80 + 1) - v80) >> 4));
    if ( !v77 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x95C,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
        (const char *)0x8007000ELL,
        (int)v73);
      MIDL_user_free(v75);
      MIDL_user_free(v76);
      MIDL_user_free(v77);
      MIDL_user_free(v78);
      std::unique_ptr<KeyReleaseAuthzContext>::~unique_ptr<KeyReleaseAuthzContext>((KeyReleaseAuthzContext **)&v74, v46);
      std::vector<_WINBIO_PRESENCE>::_Tidy(v83);
      std::vector<_WINBIO_PRESENCE>::_Tidy(&v80);
      std::vector<_WINBIO_PRESENCE>::_Tidy(&v85);
      std::vector<_WINBIO_PRESENCE>::_Tidy(&v87);
      if ( v82[1] )
        std::_Ref_count_base::_Decref(v82[1]);
      goto LABEL_73;
    }
    v47 = 0;
    v49 = (_OWORD *)*((_QWORD *)&v80 + 1);
    for ( m = (_OWORD *)v80; m != v49; m += 31 )
    {
      v50 = m;
      v51 = v98;
      v52 = 3;
      do
      {
        *v51 = *v50;
        v51[1] = v50[1];
        v51[2] = v50[2];
        v51[3] = v50[3];
        v51[4] = v50[4];
        v51[5] = v50[5];
        v51[6] = v50[6];
        v51[7] = v50[7];
        v51 += 8;
        v50 += 8;
        --v52;
      }
      while ( v52 );
      *v51 = *v50;
      v51[1] = v50[1];
      v51[2] = v50[2];
      v51[3] = v50[3];
      v51[4] = v50[4];
      v51[5] = v50[5];
      v51[6] = v50[6];
      v53 = (char *)v77 + 496 * v47;
      v54 = v98;
      v55 = 3;
      do
      {
        *v53 = *v54;
        v53[1] = v54[1];
        v53[2] = v54[2];
        v53[3] = v54[3];
        v53[4] = v54[4];
        v53[5] = v54[5];
        v53[6] = v54[6];
        v53[7] = v54[7];
        v53 += 8;
        v54 += 8;
        --v55;
      }
      while ( v55 );
      *v53 = *v54;
      v53[1] = v54[1];
      v53[2] = v54[2];
      v53[3] = v54[3];
      v53[4] = v54[4];
      v53[5] = v54[5];
      v53[6] = v54[6];
      ++v47;
    }
  }
  v56 = *(_OWORD **)&v83[2];
  v57 = *(_OWORD **)v83;
  if ( 0xEF7BDEF7BDEF7BDFuLL * ((__int64)(*(_QWORD *)&v83[2] - *(_QWORD *)v83) >> 4) )
  {
    v78 = MIDL_user_allocate(16 * ((__int64)(*(_QWORD *)&v83[2] - *(_QWORD *)v83) >> 4));
    if ( !v78 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x968,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
        (const char *)0x8007000ELL,
        (int)v73);
      MIDL_user_free(v75);
      MIDL_user_free(v76);
      MIDL_user_free(v77);
      MIDL_user_free(v78);
      std::unique_ptr<KeyReleaseAuthzContext>::~unique_ptr<KeyReleaseAuthzContext>((KeyReleaseAuthzContext **)&v74, v58);
      std::vector<_WINBIO_PRESENCE>::_Tidy(v83);
      std::vector<_WINBIO_PRESENCE>::_Tidy(&v80);
      std::vector<_WINBIO_PRESENCE>::_Tidy(&v85);
      std::vector<_WINBIO_PRESENCE>::_Tidy(&v87);
      if ( v82[1] )
        std::_Ref_count_base::_Decref(v82[1]);
      goto LABEL_73;
    }
    v59 = 0;
    v57 = *(_OWORD **)v83;
    v56 = *(_OWORD **)&v83[2];
    if ( *(_QWORD *)v83 != *(_QWORD *)&v83[2] )
    {
      do
      {
        v60 = v57;
        v61 = v98;
        v62 = 3;
        do
        {
          *v61 = *v60;
          v61[1] = v60[1];
          v61[2] = v60[2];
          v61[3] = v60[3];
          v61[4] = v60[4];
          v61[5] = v60[5];
          v61[6] = v60[6];
          v61[7] = v60[7];
          v61 += 8;
          v60 += 8;
          --v62;
        }
        while ( v62 );
        *v61 = *v60;
        v61[1] = v60[1];
        v61[2] = v60[2];
        v61[3] = v60[3];
        v61[4] = v60[4];
        v61[5] = v60[5];
        v61[6] = v60[6];
        v63 = (char *)v78 + 496 * v59;
        v64 = v98;
        v65 = 3;
        do
        {
          *v63 = *v64;
          v63[1] = v64[1];
          v63[2] = v64[2];
          v63[3] = v64[3];
          v63[4] = v64[4];
          v63[5] = v64[5];
          v63[6] = v64[6];
          v63[7] = v64[7];
          v63 += 8;
          v64 += 8;
          --v65;
        }
        while ( v65 );
        *v63 = *v64;
        v63[1] = v64[1];
        v63[2] = v64[2];
        v63[3] = v64[3];
        v63[4] = v64[4];
        v63[5] = v64[5];
        v63[6] = v64[6];
        ++v59;
        v57 += 31;
      }
      while ( v57 != v56 );
      v56 = *(_OWORD **)&v83[2];
      v57 = *(_OWORD **)v83;
    }
  }
  v66 = 0xEF7BDEF7BDEF7BDFuLL * ((__int64)(*((_QWORD *)&v87 + 1) - v87) >> 4);
  if ( v66 )
  {
    *a3 = v75;
  }
  else
  {
    *a3 = 0;
    LODWORD(v66) = 0;
  }
  *v96 = v66;
  v67 = 0xEF7BDEF7BDEF7BDFuLL * ((__int64)(*((_QWORD *)&v85 + 1) - v85) >> 4);
  if ( v67 )
  {
    *a5 = v76;
  }
  else
  {
    *a5 = 0;
    LODWORD(v67) = 0;
  }
  *v89 = v67;
  v68 = 0xEF7BDEF7BDEF7BDFuLL * ((__int64)(*((_QWORD *)&v80 + 1) - v80) >> 4);
  if ( v68 )
  {
    *a7 = v77;
  }
  else
  {
    *a7 = 0;
    LODWORD(v68) = 0;
  }
  *v90 = v68;
  v69 = 0xEF7BDEF7BDEF7BDFuLL * (v56 - v57);
  if ( v69 )
  {
    *a9 = v78;
  }
  else
  {
    *a9 = 0;
    LODWORD(v69) = 0;
  }
  *v97 = v69;
  v70 = v74;
  v74 = 0;
  *v91 = v70;
  HardwareManager::AddHandle(v70);
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v99, 0);
  std::unique_ptr<KeyReleaseAuthzContext>::~unique_ptr<KeyReleaseAuthzContext>((KeyReleaseAuthzContext **)&v74, v71);
  std::vector<_WINBIO_PRESENCE>::_Tidy(v83);
  std::vector<_WINBIO_PRESENCE>::_Tidy(&v80);
  std::vector<_WINBIO_PRESENCE>::_Tidy(&v85);
  std::vector<_WINBIO_PRESENCE>::_Tidy(&v87);
  if ( v82[1] )
    std::_Ref_count_base::_Decref(v82[1]);
  BioIsoProvider::PresenceMonitorGetChanges::~PresenceMonitorGetChanges((BioIsoProvider::PresenceMonitorGetChanges *)v99);
  return 0;
}

```

## disassembly

```asm
0x140055800  push    rbx
0x140055802  push    rsi
0x140055803  push    rdi
0x140055804  push    r12
0x140055806  push    r13
0x140055808  push    r14
0x14005580a  push    r15
0x14005580c  sub     rsp, 470h
0x140055813  mov     rax, cs:__security_cookie
0x14005581a  xor     rax, rsp
0x14005581d  mov     [rsp+4A8h+var_48], rax
0x140055825  mov     rsi, r9
0x140055828  mov     [rsp+4A8h+var_398], r9
0x140055830  mov     r15, r8
0x140055833  mov     [rsp+4A8h+var_3C8], rdx
0x14005583b  mov     rbx, rcx
0x14005583e  mov     r12, [rsp+4A8h+arg_20]
0x140055846  mov     rax, [rsp+4A8h+arg_28]
0x14005584e  mov     [rsp+4A8h+var_3D8], rax
0x140055856  mov     r13, [rsp+4A8h+arg_30]
0x14005585e  mov     rax, [rsp+4A8h+arg_38]
0x140055866  mov     [rsp+4A8h+var_3D0], rax
0x14005586e  mov     r14, [rsp+4A8h+arg_40]
0x140055876  mov     rdi, [rsp+4A8h+arg_48]
0x14005587e  mov     [rsp+4A8h+var_390], rdi
0x140055886  lea     rdx, aPresencemonito_3; "PresenceMonitorGetChanges"
0x14005588d  lea     rcx, [rsp+4A8h+var_198]
0x140055895  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14005589a  lea     rax, ??_7PresenceMonitorGetChanges@BioIsoProvider@@6B@; const BioIsoProvider::PresenceMonitorGetChanges::`vftable'
0x1400558a1  mov     [rsp+4A8h+var_198], rax
0x1400558a9  lea     rcx, [rsp+4A8h+var_198]; this
0x1400558b1  call    ?StartActivity@PresenceMonitorGetChanges@BioIsoProvider@@QEAAXXZ; BioIsoProvider::PresenceMonitorGetChanges::StartActivity(void)
0x1400558b6  nop
0x1400558b7  test    rbx, rbx
0x1400558ba  jz      loc_140056716
0x1400558c0  cmp     [rsp+4A8h+var_3C8], 0
0x1400558c9  jz      loc_140056716
0x1400558cf  test    r15, r15
0x1400558d2  jz      loc_140056716
0x1400558d8  test    rsi, rsi
0x1400558db  jz      loc_140056716
0x1400558e1  test    r12, r12
0x1400558e4  jz      loc_140056716
0x1400558ea  cmp     [rsp+4A8h+var_3D8], 0
0x1400558f3  jz      loc_140056716
0x1400558f9  test    r13, r13
0x1400558fc  jz      loc_140056716
0x140055902  cmp     [rsp+4A8h+var_3D0], 0
0x14005590b  jz      loc_140056716
0x140055911  test    r14, r14
0x140055914  jz      loc_140056716
0x14005591a  test    rdi, rdi
0x14005591d  jz      loc_140056716
0x140055923  mov     rcx, rbx; void *
0x140055926  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x14005592b  xor     edi, edi
0x14005592d  test    al, al
0x14005592f  jnz     short loc_140055967
0x140055931  mov     rcx, [rsp+4A8h]; this
0x140055939  mov     ebx, 80070057h
0x14005593e  mov     r9d, ebx; char *
0x140055941  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140055948  mov     edx, 905h; void *
0x14005594d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140055952  nop
0x140055953  lea     rcx, [rsp+4A8h+var_198]; this
0x14005595b  call    ??1PresenceMonitorGetChanges@BioIsoProvider@@QEAA@XZ; BioIsoProvider::PresenceMonitorGetChanges::~PresenceMonitorGetChanges(void)
0x140055960  mov     eax, ebx
0x140055962  jmp     loc_14005674D
0x140055967  xorps   xmm0, xmm0
0x14005596a  movdqu  xmmword ptr [rsp+4A8h+var_430], xmm0
0x140055970  lea     rdx, [rsp+4A8h+var_430]
0x140055975  mov     ecx, [rbx]
0x140055977  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x14005597c  mov     ebx, eax
0x14005597e  test    eax, eax
0x140055980  jns     short loc_1400559C6
0x140055982  mov     rcx, [rsp+4A8h]; this
0x14005598a  mov     r9d, eax; char *
0x14005598d  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140055994  mov     edx, 90Bh; void *
0x140055999  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005599e  nop
0x14005599f  mov     rcx, [rsp+4A8h+var_430+8]; this
0x1400559a7  test    rcx, rcx
0x1400559aa  jz      short loc_1400559B2
0x1400559ac  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400559b1  nop
0x1400559b2  lea     rcx, [rsp+4A8h+var_198]; this
0x1400559ba  call    ??1PresenceMonitorGetChanges@BioIsoProvider@@QEAA@XZ; BioIsoProvider::PresenceMonitorGetChanges::~PresenceMonitorGetChanges(void)
0x1400559bf  mov     eax, ebx
0x1400559c1  jmp     loc_14005674D
0x1400559c6  xorps   xmm0, xmm0
0x1400559c9  movdqu  [rsp+4A8h+var_3F0], xmm0
0x1400559d2  mov     [rsp+4A8h+var_3E0], rdi
0x1400559da  movdqu  [rsp+4A8h+var_408], xmm0
0x1400559e3  mov     [rsp+4A8h+var_3F8], rdi
0x1400559eb  movdqu  [rsp+4A8h+var_448], xmm0
0x1400559f1  mov     [rsp+4A8h+var_438], rdi
0x1400559f6  movdqu  xmmword ptr [rsp+4A8h+var_420], xmm0
0x1400559ff  mov     [rsp+4A8h+var_410], rdi
0x140055a07  mov     rax, [rsp+4A8h+var_430]
0x140055a0c  mov     rcx, [rax+28h]
0x140055a10  mov     rax, [rcx]
0x140055a13  lea     rdx, [rsp+4A8h+var_420]
0x140055a1b  mov     qword ptr [rsp+4A8h+var_488], rdx; int
0x140055a20  lea     r9, [rsp+4A8h+var_448]
0x140055a25  lea     r8, [rsp+4A8h+var_408]
0x140055a2d  lea     rdx, [rsp+4A8h+var_3F0]
0x140055a35  mov     rax, [rax+10h]
0x140055a39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055a3e  mov     ebx, eax
0x140055a40  test    eax, eax
0x140055a42  jns     short loc_140055ABD
0x140055a44  mov     rcx, [rsp+4A8h]; this
0x140055a4c  mov     r9d, eax; char *
0x140055a4f  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140055a56  mov     edx, 916h; void *
0x140055a5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140055a60  nop
0x140055a61  lea     rcx, [rsp+4A8h+var_420]
0x140055a69  call    ?_Tidy@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@AEAAXXZ; std::vector<_WINBIO_PRESENCE>::_Tidy(void)
0x140055a6e  nop
0x140055a6f  lea     rcx, [rsp+4A8h+var_448]
0x140055a74  call    ?_Tidy@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@AEAAXXZ; std::vector<_WINBIO_PRESENCE>::_Tidy(void)
0x140055a79  nop
0x140055a7a  lea     rcx, [rsp+4A8h+var_408]
0x140055a82  call    ?_Tidy@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@AEAAXXZ; std::vector<_WINBIO_PRESENCE>::_Tidy(void)
0x140055a87  nop
0x140055a88  lea     rcx, [rsp+4A8h+var_3F0]
0x140055a90  call    ?_Tidy@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@AEAAXXZ; std::vector<_WINBIO_PRESENCE>::_Tidy(void)
0x140055a95  nop
0x140055a96  mov     rcx, [rsp+4A8h+var_430+8]; this
0x140055a9e  test    rcx, rcx
0x140055aa1  jz      short loc_140055AA9
0x140055aa3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140055aa8  nop
0x140055aa9  lea     rcx, [rsp+4A8h+var_198]; this
0x140055ab1  call    ??1PresenceMonitorGetChanges@BioIsoProvider@@QEAA@XZ; BioIsoProvider::PresenceMonitorGetChanges::~PresenceMonitorGetChanges(void)
0x140055ab6  mov     eax, ebx
0x140055ab8  jmp     loc_14005674D
0x140055abd  lea     rcx, [rsp+4A8h+var_478]
0x140055ac2  call    ??$make_unique@VKeyReleaseAuthzContext@@$$V$0A@@std@@YA?AV?$unique_ptr@VKeyReleaseAuthzContext@@U?$default_delete@VKeyReleaseAuthzContext@@@std@@@0@XZ; std::make_unique<KeyReleaseAuthzContext,,0>(void)
0x140055ac7  nop
0x140055ac8  mov     rbx, qword ptr [rsp+4A8h+var_448]
0x140055acd  mov     rsi, qword ptr [rsp+4A8h+var_448+8]
0x140055ad2  cmp     rbx, rsi
0x140055ad5  jz      loc_140055C2A
0x140055adb  cmp     [rbx+8], edi
0x140055ade  jl      loc_140055C1E
0x140055ae4  lea     rdx, [rbx+10h]
0x140055ae8  cmp     dword ptr [rdx], 3
0x140055aeb  jnz     loc_140055C1E
0x140055af1  xorps   xmm0, xmm0
0x140055af4  movdqu  [rsp+4A8h+var_3C0], xmm0
0x140055afd  mov     [rsp+4A8h+var_3B0], rdi
0x140055b05  lea     r8, [rsp+4A8h+var_3C0]
0x140055b0d  mov     ecx, [rbx]
0x140055b0f  call    ?GenerateEnrollmentId@@YAJIPEBU_WINBIO_IDENTITY@@PEAV?$vector@EV?$allocator@E@std@@@std@@@Z; GenerateEnrollmentId(uint,_WINBIO_IDENTITY const *,std::vector<uchar> *)
0x140055b14  mov     edi, eax
0x140055b16  test    eax, eax
0x140055b18  jns     loc_140055BB0
0x140055b1e  mov     rcx, [rsp+4A8h]; this
0x140055b26  mov     r9d, eax; char *
0x140055b29  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140055b30  mov     edx, 922h; void *
0x140055b35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140055b3a  nop
0x140055b3b  lea     rcx, [rsp+4A8h+var_3C0]
0x140055b43  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140055b48  nop
0x140055b49  lea     rcx, [rsp+4A8h+var_478]
0x140055b4e  call    ??1?$unique_ptr@VKeyReleaseAuthzContext@@U?$default_delete@VKeyReleaseAuthzContext@@@std@@@std@@QEAA@XZ; std::unique_ptr<KeyReleaseAuthzContext>::~unique_ptr<KeyReleaseAuthzContext>(void)
0x140055b53  nop
0x140055b54  lea     rcx, [rsp+4A8h+var_420]
0x140055b5c  call    ?_Tidy@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@AEAAXXZ; std::vector<_WINBIO_PRESENCE>::_Tidy(void)
0x140055b61  nop
0x140055b62  lea     rcx, [rsp+4A8h+var_448]
0x140055b67  call    ?_Tidy@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@AEAAXXZ; std::vector<_WINBIO_PRESENCE>::_Tidy(void)
0x140055b6c  nop
0x140055b6d  lea     rcx, [rsp+4A8h+var_408]
0x140055b75  call    ?_Tidy@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@AEAAXXZ; std::vector<_WINBIO_PRESENCE>::_Tidy(void)
0x140055b7a  nop
0x140055b7b  lea     rcx, [rsp+4A8h+var_3F0]
0x140055b83  call    ?_Tidy@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@AEAAXXZ; std::vector<_WINBIO_PRESENCE>::_Tidy(void)
0x140055b88  nop
0x140055b89  mov     rcx, [rsp+4A8h+var_430+8]; this
0x140055b91  test    rcx, rcx
0x140055b94  jz      short loc_140055B9C
0x140055b96  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140055b9b  nop
0x140055b9c  lea     rcx, [rsp+4A8h+var_198]; this
0x140055ba4  call    ??1PresenceMonitorGetChanges@BioIsoProvider@@QEAA@XZ; BioIsoProvider::PresenceMonitorGetChanges::~PresenceMonitorGetChanges(void)
0x140055ba9  mov     eax, edi
0x140055bab  jmp     loc_14005674D
0x140055bb0  call    ??$IsEnabled@V?$Feature@U__WilFeatureTraits_Feature_AddLoggingForFaceAuthErrors@@@wil@@@Velocity@VsmUtils@@SA_NXZ; VsmUtils::Velocity::IsEnabled<wil::Feature<__WilFeatureTraits_Feature_AddLoggingForFaceAuthErrors>>(void)
0x140055bb5  xor     edi, edi
0x140055bb7  mov     r8, qword ptr [rsp+4A8h+var_3C0+8]
0x140055bbf  mov     rdx, qword ptr [rsp+4A8h+var_3C0]
0x140055bc7  xor     r9d, r9d
0x140055bca  mov     rcx, [rsp+4A8h+var_478]
0x140055bcf  sub     r8, rdx
0x140055bd2  test    al, al
0x140055bd4  jz      short loc_140055BEB
0x140055bd6  call    ?Add@KeyReleaseAuthzContext@@QEAAJPEBE_KPEAV?$vector@EV?$allocator@E@std@@@std@@@Z; KeyReleaseAuthzContext::Add(uchar const *,unsigned __int64,std::vector<uchar> *)
0x140055bdb  mov     [rsp+4A8h+var_450], eax
0x140055bdf  lea     rcx, [rsp+4A8h+var_450]
0x140055be4  call    ??$AuthorizationForRecognizedPresence@AEAJ@BioIsoProvider@@SAXAEAJ@Z; BioIsoProvider::AuthorizationForRecognizedPresence<long &>(long &)
0x140055be9  jmp     short loc_140055C11
0x140055beb  call    ?Add@KeyReleaseAuthzContext@@QEAAJPEBE_KPEAV?$vector@EV?$allocator@E@std@@@std@@@Z; KeyReleaseAuthzContext::Add(uchar const *,unsigned __int64,std::vector<uchar> *)
0x140055bf0  mov     rcx, [rsp+4A8h]; this
0x140055bf8  test    eax, eax
0x140055bfa  jns     short loc_140055C11
0x140055bfc  mov     r9d, eax; char *
0x140055bff  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140055c06  mov     edx, 92Eh; void *
0x140055c0b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140055c10  nop
0x140055c11  lea     rcx, [rsp+4A8h+var_3C0]
0x140055c19  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140055c1e  add     rbx, 1F0h
0x140055c25  jmp     loc_140055AD2
0x140055c2a  mov     [rsp+4A8h+var_470], rdi
0x140055c2f  mov     [rsp+4A8h+var_468], rdi
0x140055c34  mov     [rsp+4A8h+var_460], rdi
0x140055c39  mov     [rsp+4A8h+var_458], rdi
0x140055c3e  lea     rax, [rsp+4A8h+var_470]
0x140055c43  mov     qword ptr [rsp+4A8h+var_3C0], rax
0x140055c4b  lea     rax, [rsp+4A8h+var_468]
0x140055c50  mov     qword ptr [rsp+4A8h+var_3C0+8], rax
0x140055c58  lea     rax, [rsp+4A8h+var_460]
0x140055c5d  mov     [rsp+4A8h+var_3B0], rax
0x140055c65  lea     rax, [rsp+4A8h+var_458]
0x140055c6a  mov     [rsp+4A8h+var_3A8], rax
0x140055c72  mov     [rsp+4A8h+var_3A0], 1
0x140055c7a  mov     rax, qword ptr [rsp+4A8h+var_3F0+8]
0x140055c82  sub     rax, qword ptr [rsp+4A8h+var_3F0]
0x140055c8a  sar     rax, 4
0x140055c8e  mov     rsi, 0EF7BDEF7BDEF7BDFh
0x140055c98  imul    rax, rsi
0x140055c9c  test    rax, rax
0x140055c9f  jz      loc_140055ECC
0x140055ca5  imul    rcx, rax, 1F0h; size
0x140055cac  call    MIDL_user_allocate
0x140055cb1  mov     [rsp+4A8h+var_470], rax
0x140055cb6  test    rax, rax
0x140055cb9  jnz     loc_140055D71
0x140055cbf  mov     rcx, [rsp+4A8h]; this
0x140055cc7  mov     ebx, 8007000Eh
0x140055ccc  mov     r9d, ebx; char *
0x140055ccf  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140055cd6  mov     edx, 944h; void *
0x140055cdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140055ce0  nop
0x140055ce1  mov     rcx, [rsp+4A8h+var_470]; void *
0x140055ce6  call    MIDL_user_free
0x140055ceb  mov     rcx, [rsp+4A8h+var_468]; void *
0x140055cf0  call    MIDL_user_free
0x140055cf5  mov     rcx, [rsp+4A8h+var_460]; void *
0x140055cfa  call    MIDL_user_free
0x140055cff  mov     rcx, [rsp+4A8h+var_458]; void *
0x140055d04  call    MIDL_user_free
0x140055d09  nop
0x140055d0a  lea     rcx, [rsp+4A8h+var_478]
0x140055d0f  call    ??1?$unique_ptr@VKeyReleaseAuthzContext@@U?$default_delete@VKeyReleaseAuthzContext@@@std@@@std@@QEAA@XZ; std::unique_ptr<KeyReleaseAuthzContext>::~unique_ptr<KeyReleaseAuthzContext>(void)
0x140055d14  nop
0x140055d15  lea     rcx, [rsp+4A8h+var_420]
0x140055d1d  call    ?_Tidy@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@AEAAXXZ; std::vector<_WINBIO_PRESENCE>::_Tidy(void)
0x140055d22  nop
0x140055d23  lea     rcx, [rsp+4A8h+var_448]
0x140055d28  call    ?_Tidy@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@AEAAXXZ; std::vector<_WINBIO_PRESENCE>::_Tidy(void)
0x140055d2d  nop
0x140055d2e  lea     rcx, [rsp+4A8h+var_408]
0x140055d36  call    ?_Tidy@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@AEAAXXZ; std::vector<_WINBIO_PRESENCE>::_Tidy(void)
0x140055d3b  nop
0x140055d3c  lea     rcx, [rsp+4A8h+var_3F0]
0x140055d44  call    ?_Tidy@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@AEAAXXZ; std::vector<_WINBIO_PRESENCE>::_Tidy(void)
0x140055d49  nop
0x140055d4a  mov     rcx, [rsp+4A8h+var_430+8]; this
0x140055d52  test    rcx, rcx
0x140055d55  jz      short loc_140055D5D
0x140055d57  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140055d5c  nop
0x140055d5d  lea     rcx, [rsp+4A8h+var_198]; this
0x140055d65  call    ??1PresenceMonitorGetChanges@BioIsoProvider@@QEAA@XZ; BioIsoProvider::PresenceMonitorGetChanges::~PresenceMonitorGetChanges(void)
0x140055d6a  mov     eax, ebx
0x140055d6c  jmp     loc_14005674D
0x140055d71  mov     r10, rdi
0x140055d74  mov     r8, qword ptr [rsp+4A8h+var_3F0]
0x140055d7c  mov     r9, qword ptr [rsp+4A8h+var_3F0+8]
0x140055d84  mov     ebx, 80h
0x140055d89  jmp     loc_140055EC1
0x140055d8e  mov     rax, r8
0x140055d91  lea     rcx, [rsp+4A8h+var_388]
0x140055d99  mov     edx, 3
0x140055d9e  movups  xmm0, xmmword ptr [rax]
0x140055da1  movups  xmmword ptr [rcx], xmm0
0x140055da4  movups  xmm1, xmmword ptr [rax+10h]
0x140055da8  movups  xmmword ptr [rcx+10h], xmm1
0x140055dac  movups  xmm0, xmmword ptr [rax+20h]
  ... truncated ...
```
