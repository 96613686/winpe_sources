# OrchestratorDBManager::UpdateRequestDocVersion(_GUID,OrchestratorDCInfo,StateMachineTypeTag)

- ea: `0x18010bab4`
- end: `0x18010bf09`
- name: `?UpdateRequestDocVersion@OrchestratorDBManager@@QEAAJU_GUID@@UOrchestratorDCInfo@@W4StateMachineTypeTag@@@Z`
- size: `1109`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180082930`
- `0x1801196e0`

## callees

- `0x18000b9e0`
- `0x18000c8f4`
- `0x18000e310`
- `0x18000e32c`
- `0x1800117dc`
- `0x180011fe0`
- `0x180012dc4`
- `0x180018cc4`
- `0x18001d0b0`
- `0x18004d1ac`
- `0x180056bcc`
- `0x180058b3c`
- `0x18009a2e4`
- `0x1800a04fc`
- `0x180109070`
- `0x18010a054`
- `0x18010a628`
- `0x18010abd8`
- `0x18010b6a0`
- `0x18010b724`
- `0x18010bab4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010bd7e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010bda8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010bdd2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010bdff`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010bd7e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010bda8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010bdd2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010bdff`

## string_xrefs

- `0x18010bb19`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\database\src\dbmanager.cpp`
- `0x18010bb59`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\database\src\dbmanager.cpp`
- `0x18010bbab`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\database\src\dbmanager.cpp`
- `0x18010bc26`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\database\src\dbmanager.cpp`
- `0x18010bd4b`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\database\src\dbmanager.cpp`
- `0x18010beab`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\database\src\dbmanager.cpp`
- `0x18010bd3c`: `Doc for enrollmentId %ws, user context %ws docid %ws, docVersion %ws is being processed, can't be updated`
- `0x18010bcd6`: `UpdateRequestDocVersion failed because request state is DMOrchestratorState::OrchestratorStarted`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OrchestratorDBManager::UpdateRequestDocVersion(__int64 a1, __int128 *a2, _QWORD *a3, int a4)
{
  int Request; // edi
  int v7; // eax
  int v8; // eax
  OrchestratorDBManager *v9; // rcx
  _QWORD *v10; // r8
  _QWORD *v11; // rcx
  _QWORD *v12; // rax
  char **v13; // r9
  int v14; // ecx
  _QWORD *v15; // r9
  _QWORD *v16; // r8
  _QWORD *v17; // rdx
  const char *v18; // rax
  _QWORD *v19; // rdx
  char **v20; // rcx
  _QWORD *v21; // rdx
  _QWORD *v22; // rcx
  _QWORD *v23; // rdx
  _QWORD *v24; // rcx
  _QWORD *v25; // rdx
  _QWORD *v26; // rcx
  OrchestratorDBManager *v27; // rcx
  OrchestratorDBManager *v28; // rcx
  const unsigned __int16 *v29; // r8
  const unsigned __int16 *v30; // rax
  OrchestratorDBManager *v31; // rcx
  const unsigned __int16 *v32; // r8
  int v34; // [rsp+20h] [rbp-E0h]
  enum DCLifecycleNotificationType *v35; // [rsp+28h] [rbp-D8h]
  enum DCLifecycleNotificationType *v36; // [rsp+28h] [rbp-D8h]
  unsigned int v37; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v38; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v39; // [rsp+60h] [rbp-A0h] BYREF
  int v40; // [rsp+68h] [rbp-98h] BYREF
  __int128 v41; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v42; // [rsp+80h] [rbp-80h]
  char *v43[3]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v44; // [rsp+A8h] [rbp-58h]
  _QWORD v45[3]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v46; // [rsp+C8h] [rbp-38h]
  _QWORD v47[3]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int64 v48; // [rsp+E8h] [rbp-18h]
  _QWORD v49[3]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v50; // [rsp+108h] [rbp+8h]
  _QWORD v51[4]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v52[40]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v53[264]; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+2B8h]

  v42 = a3;
  v41 = *a2;
  Request = GUIDToStringWithoutBracket(&v41, v52);
  if ( Request >= 0 )
  {
    v38 = 0;
    v7 = _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
           &v38,
           L"Global\\DCOrchestratorMutex");
    Request = v7;
    if ( v7 >= 0 )
    {
      v37 = 0;
      _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
        &v38,
        &v41,
        &v37,
        30000);
      v8 = CheckLockStatusAndLogError(v37);
      Request = v8;
      if ( v8 >= 0 )
      {
        v40 = 0;
        OrchestratorDCInfo::OrchestratorDCInfo((OrchestratorDCInfo *)v43);
        v37 = 0;
        Request = OrchestratorDBManager::GetRequest(
                    v9,
                    v52,
                    (struct OrchestratorDCInfo *)v43,
                    (enum StateMachineTypeTag *)&v40,
                    (enum DMOrchestratorState *)&v37,
                    (enum DCLifecycleNotificationType *)&v39);
        if ( Request >= 0 )
        {
          if ( v37 == 2 )
          {
            memset_0(v53, 0, 0x104u);
            v10 = v49;
            if ( v50 > 7 )
              v10 = (_QWORD *)v49[0];
            v11 = v47;
            if ( v48 > 7 )
              v11 = (_QWORD *)v47[0];
            v12 = v45;
            if ( v46 > 7 )
              v12 = (_QWORD *)v45[0];
            v13 = v43;
            if ( v44 > 7 )
              v13 = (char **)v43[0];
            Request = -2100297720;
            if ( StringCchPrintfW(
                   v53,
                   0x104u,
                   L"enrollmentId: %s, context:%s, docId:%s, docVersion:%s",
                   v13,
                   v12,
                   v11,
                   v10) >= 0
              && byte_180189FC1 < 0 )
            {
              McTemplateU0zzd_EventWriteTransfer(
                v14,
                (unsigned int)OrchestratorGenericFailure,
                (unsigned int)L"UpdateRequestDocVersion failed because request state is DMOrchestratorState::OrchestratorStarted",
                (unsigned int)v53,
                8);
            }
            v15 = v49;
            if ( v50 > 7 )
              v15 = (_QWORD *)v49[0];
            v16 = v47;
            if ( v48 > 7 )
              v16 = (_QWORD *)v47[0];
            v17 = v45;
            if ( v46 > 7 )
              v17 = (_QWORD *)v45[0];
            v18 = (const char *)v43;
            if ( v44 > 7 )
              v18 = v43[0];
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x512,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\database\\src\\dbmanager.cpp",
              (const char *)0x82D00008LL,
              (int)"Doc for enrollmentId %ws, user context %ws docid %ws, docVersion %ws is being processed, can't be updated",
              v18,
              v17,
              v16,
              v15);
          }
          else
          {
            if ( a3[3] <= 7u )
              v19 = a3;
            else
              v19 = (_QWORD *)*a3;
            v20 = v43;
            if ( v44 > 7 )
              v20 = (char **)v43[0];
            if ( (unsigned int)_o__wcsicmp(v20, v19) )
              goto LABEL_58;
            v21 = a3 + 4;
            if ( a3[7] > 7u )
              v21 = (_QWORD *)*v21;
            v22 = v45;
            if ( v46 > 7 )
              v22 = (_QWORD *)v45[0];
            if ( (unsigned int)_o__wcsicmp(v22, v21) )
              goto LABEL_58;
            v23 = a3 + 8;
            if ( a3[11] > 7u )
              v23 = (_QWORD *)*v23;
            v24 = v47;
            if ( v48 > 7 )
              v24 = (_QWORD *)v47[0];
            if ( (unsigned int)_o__wcsicmp(v24, v23) )
              goto LABEL_58;
            v25 = a3 + 16;
            if ( a3[19] > 7u )
              v25 = (_QWORD *)*v25;
            v26 = v51;
            if ( v51[3] > 7u )
              v26 = (_QWORD *)v51[0];
            if ( (unsigned int)_o__wcsicmp(v26, v25) || a4 != v40 )
            {
LABEL_58:
              Request = -2147467259;
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x51A,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\database\\src\\dbmanager.cpp",
                (const char *)0x80004005LL,
                (int)"existing doc mismatch with request",
                (const char *)v36);
            }
            else
            {
              v39 = 0;
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
                &v39,
                0);
              Request = OrchestratorDBManager::GetDMOrchestratorKey(v27, &v39, v52, 0);
              if ( Request >= 0 )
              {
                v30 = (const unsigned __int16 *)(a3 + 12);
                if ( a3[15] > 7u )
                  v30 = *(const unsigned __int16 **)v30;
                Request = OrchestratorDBManager::SetRegistryString(v28, v39, v29, L"DocVersion", v30, (bool)v36);
                if ( Request >= 0 )
                  Request = OrchestratorDBManager::SetRegistryDWORD(v31, v39, v32, L"State", 1u);
              }
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v39);
            }
          }
        }
        else
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x506,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\database\\src\\dbmanager.cpp",
            (const char *)(unsigned int)Request,
            (int)"can't find the request for id: %ws",
            (const char *)v52);
        }
        OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)v43);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4FF,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\database\\src\\dbmanager.cpp",
          (const char *)(unsigned int)v8,
          v34);
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v41);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4FB,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\database\\src\\dbmanager.cpp",
        (const char *)(unsigned int)v7,
        v34);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v38);
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x4F7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\database\\src\\dbmanager.cpp",
      (const char *)(unsigned int)Request,
      (int)"failed to convert GUID to string with no bracket",
      (const char *)v35);
  }
  OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)a3);
  return (unsigned int)Request;
}

```

## disassembly

```asm
0x18010bab4  mov     [rsp-8+arg_0], rbx
0x18010bab9  push    rbp
0x18010baba  push    rsi
0x18010babb  push    rdi
0x18010babc  lea     rbp, [rsp-2A0h]
0x18010bac4  sub     rsp, 3A0h
0x18010bacb  mov     rax, cs:__security_cookie
0x18010bad2  xor     rax, rsp
0x18010bad5  mov     [rbp+2B0h+var_20], rax
0x18010badc  mov     esi, r9d
0x18010badf  mov     rbx, r8
0x18010bae2  mov     [rbp+2B0h+var_330], rbx
0x18010bae6  movaps  xmm0, xmmword ptr [rdx]
0x18010bae9  movdqa  [rsp+3B0h+var_340], xmm0
0x18010baef  lea     rdx, [rbp+2B0h+var_280]
0x18010baf3  lea     rcx, [rsp+3B0h+var_340]
0x18010baf8  call    GUIDToStringWithoutBracket
0x18010bafd  mov     edi, eax
0x18010baff  test    eax, eax
0x18010bb01  jns     short loc_18010BB2F
0x18010bb03  mov     rcx, [rbp+2B8h]; this
0x18010bb0a  lea     rax, aFailedToConver_1; "failed to convert GUID to string with n"...
0x18010bb11  mov     [rsp+3B0h+var_390], rax; int
0x18010bb16  mov     r9d, edi; char *
0x18010bb19  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18010bb20  mov     edx, 4F7h; void *
0x18010bb25  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18010bb2a  jmp     loc_18010BEDD
0x18010bb2f  mov     [rsp+3B0h+var_358], 0
0x18010bb38  lea     rdx, aGlobalDcorches; "Global\\DCOrchestratorMutex"
0x18010bb3f  lea     rcx, [rsp+3B0h+var_358]
0x18010bb44  call    ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18010bb49  mov     edi, eax
0x18010bb4b  test    eax, eax
0x18010bb4d  jns     short loc_18010BB6F
0x18010bb4f  mov     rcx, [rbp+2B8h]; this
0x18010bb56  mov     r9d, eax; char *
0x18010bb59  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18010bb60  mov     edx, 4FBh; void *
0x18010bb65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010bb6a  jmp     loc_18010BED2
0x18010bb6f  mov     [rsp+3B0h+var_360], 0
0x18010bb77  mov     r9d, 7530h
0x18010bb7d  lea     r8, [rsp+3B0h+var_360]
0x18010bb82  lea     rdx, [rsp+3B0h+var_340]
0x18010bb87  lea     rcx, [rsp+3B0h+var_358]
0x18010bb8c  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18010bb91  nop
0x18010bb92  mov     ecx, [rsp+3B0h+var_360]
0x18010bb96  call    CheckLockStatusAndLogError
0x18010bb9b  mov     edi, eax
0x18010bb9d  test    eax, eax
0x18010bb9f  jns     short loc_18010BBC1
0x18010bba1  mov     rcx, [rbp+2B8h]; this
0x18010bba8  mov     r9d, eax; char *
0x18010bbab  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18010bbb2  mov     edx, 4FFh; void *
0x18010bbb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010bbbc  jmp     loc_18010BEC7
0x18010bbc1  mov     [rsp+3B0h+var_348], 0
0x18010bbc9  lea     rcx, [rbp+2B0h+var_320]; this
0x18010bbcd  call    ??0OrchestratorDCInfo@@QEAA@XZ; OrchestratorDCInfo::OrchestratorDCInfo(void)
0x18010bbd2  nop
0x18010bbd3  mov     [rsp+3B0h+var_360], 0
0x18010bbdb  lea     rax, [rsp+3B0h+var_350]
0x18010bbe0  mov     [rsp+3B0h+var_388], rax; char *
0x18010bbe5  lea     rax, [rsp+3B0h+var_360]
0x18010bbea  mov     [rsp+3B0h+var_390], rax; enum DMOrchestratorState *
0x18010bbef  lea     r9, [rsp+3B0h+var_348]; enum StateMachineTypeTag *
0x18010bbf4  lea     r8, [rbp+2B0h+var_320]; struct OrchestratorDCInfo *
0x18010bbf8  lea     rdx, [rbp+2B0h+var_280]; unsigned __int16 *
0x18010bbfc  call    ?GetRequest@OrchestratorDBManager@@QEAAJPEBGPEAUOrchestratorDCInfo@@PEAW4StateMachineTypeTag@@PEAW4DMOrchestratorState@@PEAW4DCLifecycleNotificationType@@@Z; OrchestratorDBManager::GetRequest(ushort const *,OrchestratorDCInfo *,StateMachineTypeTag *,DMOrchestratorState *,DCLifecycleNotificationType *)
0x18010bc01  mov     edi, eax
0x18010bc03  test    eax, eax
0x18010bc05  jns     short loc_18010BC3C
0x18010bc07  mov     rcx, [rbp+2B8h]; this
0x18010bc0e  lea     rax, [rbp+2B0h+var_280]
0x18010bc12  mov     [rsp+3B0h+var_388], rax; char *
0x18010bc17  lea     rax, aCanTFindTheReq; "can't find the request for id: %ws"
0x18010bc1e  mov     [rsp+3B0h+var_390], rax; int
0x18010bc23  mov     r9d, edi; char *
0x18010bc26  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18010bc2d  mov     edx, 506h; void *
0x18010bc32  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18010bc37  jmp     loc_18010BEBD
0x18010bc3c  cmp     [rsp+3B0h+var_360], 2
0x18010bc41  jnz     loc_18010BD61
0x18010bc47  mov     edi, 104h
0x18010bc4c  mov     r8d, edi; Size
0x18010bc4f  xor     edx, edx; Val
0x18010bc51  lea     rcx, [rbp+2B0h+var_230]; void *
0x18010bc58  call    memset_0
0x18010bc5d  lea     r8, [rbp+2B0h+var_2C0]
0x18010bc61  cmp     [rbp+2B0h+var_2A8], 7
0x18010bc66  cmova   r8, [rbp+2B0h+var_2C0]
0x18010bc6b  lea     rcx, [rbp+2B0h+var_2E0]
0x18010bc6f  cmp     [rbp+2B0h+var_2C8], 7
0x18010bc74  cmova   rcx, [rbp+2B0h+var_2E0]
0x18010bc79  lea     rax, [rbp+2B0h+var_300]
0x18010bc7d  cmp     [rbp+2B0h+var_2E8], 7
0x18010bc82  cmova   rax, [rbp+2B0h+var_300]
0x18010bc87  lea     r9, [rbp+2B0h+var_320]
0x18010bc8b  cmp     [rbp+2B0h+var_308], 7
0x18010bc90  cmova   r9, [rbp+2B0h+var_320]
0x18010bc95  mov     [rsp+3B0h+var_380], r8
0x18010bc9a  mov     [rsp+3B0h+var_388], rcx
0x18010bc9f  mov     [rsp+3B0h+var_390], rax
0x18010bca4  lea     r8, aEnrollmentidSC; "enrollmentId: %s, context:%s, docId:%s,"...
0x18010bcab  mov     edx, edi; unsigned __int64
0x18010bcad  lea     rcx, [rbp+2B0h+var_230]; unsigned __int16 *
0x18010bcb4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18010bcb9  mov     edi, 82D00008h
0x18010bcbe  test    eax, eax
0x18010bcc0  js      short loc_18010BCE9
0x18010bcc2  cmp     cs:byte_180189FC1, 0
0x18010bcc9  jge     short loc_18010BCE9
0x18010bccb  mov     dword ptr [rsp+3B0h+var_390], edi
0x18010bccf  lea     r9, [rbp+2B0h+var_230]
0x18010bcd6  lea     r8, aUpdaterequestd; "UpdateRequestDocVersion failed because "...
0x18010bcdd  lea     rdx, OrchestratorGenericFailure
0x18010bce4  call    McTemplateU0zzd_EventWriteTransfer
0x18010bce9  lea     r9, [rbp+2B0h+var_2C0]
0x18010bced  cmp     [rbp+2B0h+var_2A8], 7
0x18010bcf2  cmova   r9, [rbp+2B0h+var_2C0]
0x18010bcf7  lea     r8, [rbp+2B0h+var_2E0]
0x18010bcfb  cmp     [rbp+2B0h+var_2C8], 7
0x18010bd00  cmova   r8, [rbp+2B0h+var_2E0]
0x18010bd05  lea     rdx, [rbp+2B0h+var_300]
0x18010bd09  cmp     [rbp+2B0h+var_2E8], 7
0x18010bd0e  cmova   rdx, [rbp+2B0h+var_300]
0x18010bd13  lea     rax, [rbp+2B0h+var_320]
0x18010bd17  cmp     [rbp+2B0h+var_308], 7
0x18010bd1c  cmova   rax, [rbp+2B0h+var_320]
0x18010bd21  mov     rcx, [rbp+2B8h]; this
0x18010bd28  mov     [rsp+3B0h+var_370], r9
0x18010bd2d  mov     [rsp+3B0h+var_378], r8
0x18010bd32  mov     [rsp+3B0h+var_380], rdx
0x18010bd37  mov     [rsp+3B0h+var_388], rax; char *
0x18010bd3c  lea     rax, aDocForEnrollme; "Doc for enrollmentId %ws, user context "...
0x18010bd43  mov     [rsp+3B0h+var_390], rax; int
0x18010bd48  mov     r9d, edi; char *
0x18010bd4b  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18010bd52  mov     edx, 512h; void *
0x18010bd57  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18010bd5c  jmp     loc_18010BEBD
0x18010bd61  cmp     qword ptr [rbx+18h], 7
0x18010bd66  jbe     short loc_18010BD6D
0x18010bd68  mov     rdx, [rbx]
0x18010bd6b  jmp     short loc_18010BD70
0x18010bd6d  mov     rdx, rbx
0x18010bd70  lea     rcx, [rbp+2B0h+var_320]
0x18010bd74  cmp     [rbp+2B0h+var_308], 7
0x18010bd79  cmova   rcx, [rbp+2B0h+var_320]
0x18010bd7e  call    cs:__imp__o__wcsicmp
0x18010bd84  test    eax, eax
0x18010bd86  jnz     loc_18010BE90
0x18010bd8c  lea     rdx, [rbx+20h]
0x18010bd90  cmp     qword ptr [rdx+18h], 7
0x18010bd95  jbe     short loc_18010BD9A
0x18010bd97  mov     rdx, [rdx]
0x18010bd9a  lea     rcx, [rbp+2B0h+var_300]
0x18010bd9e  cmp     [rbp+2B0h+var_2E8], 7
0x18010bda3  cmova   rcx, [rbp+2B0h+var_300]
0x18010bda8  call    cs:__imp__o__wcsicmp
0x18010bdae  test    eax, eax
0x18010bdb0  jnz     loc_18010BE90
0x18010bdb6  lea     rdx, [rbx+40h]
0x18010bdba  cmp     qword ptr [rdx+18h], 7
0x18010bdbf  jbe     short loc_18010BDC4
0x18010bdc1  mov     rdx, [rdx]
0x18010bdc4  lea     rcx, [rbp+2B0h+var_2E0]
0x18010bdc8  cmp     [rbp+2B0h+var_2C8], 7
0x18010bdcd  cmova   rcx, [rbp+2B0h+var_2E0]
0x18010bdd2  call    cs:__imp__o__wcsicmp
0x18010bdd8  test    eax, eax
0x18010bdda  jnz     loc_18010BE90
0x18010bde0  lea     rdx, [rbx+80h]
0x18010bde7  cmp     qword ptr [rdx+18h], 7
0x18010bdec  jbe     short loc_18010BDF1
0x18010bdee  mov     rdx, [rdx]
0x18010bdf1  lea     rcx, [rbp+2B0h+var_2A0]
0x18010bdf5  cmp     [rbp+2B0h+var_288], 7
0x18010bdfa  cmova   rcx, [rbp+2B0h+var_2A0]
0x18010bdff  call    cs:__imp__o__wcsicmp
0x18010be05  test    eax, eax
0x18010be07  jnz     loc_18010BE90
0x18010be0d  cmp     esi, [rsp+3B0h+var_348]
0x18010be11  jnz     short loc_18010BE90
0x18010be13  mov     [rsp+3B0h+var_350], 0
0x18010be1c  xor     edx, edx
0x18010be1e  lea     rcx, [rsp+3B0h+var_350]
0x18010be23  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18010be28  xor     r9d, r9d; int
0x18010be2b  lea     r8, [rbp+2B0h+var_280]; unsigned __int16 *
0x18010be2f  lea     rdx, [rsp+3B0h+var_350]; HKEY *
0x18010be34  call    ?GetDMOrchestratorKey@OrchestratorDBManager@@QEAAJPEAPEAUHKEY__@@PEBGH@Z; OrchestratorDBManager::GetDMOrchestratorKey(HKEY__ * *,ushort const *,int)
0x18010be39  mov     edi, eax
0x18010be3b  test    eax, eax
0x18010be3d  js      short loc_18010BE84
0x18010be3f  lea     rax, [rbx+60h]
0x18010be43  cmp     qword ptr [rax+18h], 7
0x18010be48  jbe     short loc_18010BE4D
0x18010be4a  mov     rax, [rax]
0x18010be4d  mov     [rsp+3B0h+var_390], rax; unsigned __int16 *
0x18010be52  lea     r9, aDocversion; "DocVersion"
0x18010be59  mov     rdx, [rsp+3B0h+var_350]; HKEY
0x18010be5e  call    ?SetRegistryString@OrchestratorDBManager@@AEAAJPEAUHKEY__@@PEBG11_N@Z; OrchestratorDBManager::SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x18010be63  mov     edi, eax
0x18010be65  test    eax, eax
0x18010be67  js      short loc_18010BE84
0x18010be69  mov     dword ptr [rsp+3B0h+var_390], 1; unsigned int
0x18010be71  lea     r9, aState; "State"
0x18010be78  mov     rdx, [rsp+3B0h+var_350]; HKEY
0x18010be7d  call    ?SetRegistryDWORD@OrchestratorDBManager@@AEAAJPEAUHKEY__@@PEBG1K@Z; OrchestratorDBManager::SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18010be82  mov     edi, eax
0x18010be84  lea     rcx, [rsp+3B0h+var_350]
0x18010be89  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010be8e  jmp     short loc_18010BEBD
0x18010be90  mov     rcx, [rbp+2B8h]; this
0x18010be97  lea     rax, aExistingDocMis; "existing doc mismatch with request"
0x18010be9e  mov     [rsp+3B0h+var_390], rax; int
0x18010bea3  mov     edi, 80004005h
0x18010bea8  mov     r9d, edi; char *
0x18010beab  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18010beb2  mov     edx, 51Ah; void *
0x18010beb7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18010bebc  nop
0x18010bebd  lea     rcx, [rbp+2B0h+var_320]; this
0x18010bec1  call    ??1OrchestratorDCInfo@@QEAA@XZ; OrchestratorDCInfo::~OrchestratorDCInfo(void)
0x18010bec6  nop
0x18010bec7  lea     rcx, [rsp+3B0h+var_340]
0x18010becc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18010bed1  nop
0x18010bed2  lea     rcx, [rsp+3B0h+var_358]
0x18010bed7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18010bedc  nop
0x18010bedd  mov     rcx, rbx; this
0x18010bee0  call    ??1OrchestratorDCInfo@@QEAA@XZ; OrchestratorDCInfo::~OrchestratorDCInfo(void)
0x18010bee5  mov     eax, edi
0x18010bee7  mov     rcx, [rbp+2B0h+var_20]
0x18010beee  xor     rcx, rsp; StackCookie
0x18010bef1  call    __security_check_cookie
0x18010bef6  mov     rbx, [rsp+3B0h+arg_0]
0x18010befe  add     rsp, 3A0h
0x18010bf05  pop     rdi
0x18010bf06  pop     rsi
0x18010bf07  pop     rbp
0x18010bf08  retn
```
