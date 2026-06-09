# GetPackageRegistrationStatusForUserAndDefaultAccount

- ea: `0x18002aa30`
- end: `0x18002bc16`
- name: `GetPackageRegistrationStatusForUserAndDefaultAccount`
- size: `4582`
- prototype: `__int64 __fastcall(void *, __int64, int, int *, _DWORD *, const WCHAR *, int *, _QWORD *)`
- caller_count: `3`
- callee_count: `30`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002a9f0`
- `0x18002e9d0`
- `0x18007a0d0`

## callees

- `0x180001008`
- `0x180005410`
- `0x180006c5c`
- `0x180007320`
- `0x180008a1c`
- `0x18000b614`
- `0x18001ad98`
- `0x18001c720`
- `0x180020f74`
- `0x180021358`
- `0x180022490`
- `0x1800237b8`
- `0x1800242fc`
- `0x18002aa30`
- `0x18002f640`
- `0x180035a70`
- `0x180035d44`
- `0x180035d98`
- `0x180037868`
- `0x180051870`
- `0x180051c20`
- `0x180051c40`
- `0x180051c4c`
- `0x180051c70`
- `0x180054568`
- `0x18005ed70`
- `0x1800916e0`
- `0x1800a76d4`
- `0x1800c5af8`
- `0x1800e6010`

## import_xrefs

- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18002aaf4`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18002aaf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b048`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ad60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ad60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ad58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ad9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002adee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ae81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002aec4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ad58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ad9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002adee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ae81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002aec4`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18002ac6f`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18002ac6f`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18002ac54`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18002ac54`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002b996`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002b996`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002ac9e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002ac9e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002abaa`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002abaa`
- `AppXAllUserStore!GetPackageSetupPhase` at `0x18002b43b`
- `AppXAllUserStore!GetPackageSetupPhase` at `0x18002b43b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b60e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b60e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b6b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bb30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bb92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b6b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bb30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bb92`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002b03a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002b08d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002b03a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002b08d`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002ae20`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002af25`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002ae20`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002af25`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002ae97`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002ae97`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x18002b683`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x18002b683`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!GetPackageStatusForUserSid` at `0x18002baf8`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!GetPackageStatusForUserSid` at `0x18002baf8`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!GetEffectivePackageStatusForUserSid` at `0x18002b6d6`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!GetEffectivePackageStatusForUserSid` at `0x18002b6d6`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002ad2a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002ad2a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18002af56`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18002af56`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b2cc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b32c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b2cc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b32c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002af7a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002b345`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002b534`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002b5b4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002bb45`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002bbab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002af7a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002b345`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002b534`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002b5b4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002bb45`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002bbab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-2!SRCacheContext_IsEmpty` at `0x18002b25e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-2!SRCacheContext_IsEmpty` at `0x18002b25e`

## string_xrefs

- `0x18002b275`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002b22a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18002b290`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18002b2b0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18002b109`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18002b14a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18002af8b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x18002b0a2`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18002b0c6`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18002b0e8`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18002bc04`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
__int64 __fastcall GetPackageRegistrationStatusForUserAndDefaultAccount(
        void *a1,
        __int64 a2,
        int a3,
        int *a4,
        _DWORD *a5,
        const WCHAR *a6,
        int *a7,
        _QWORD *a8)
{
  __int64 v8; // rbx
  void *v9; // r14
  int v11; // r8d
  int v12; // r13d
  int v13; // eax
  WINBOOL v14; // ecx
  int v15; // r8d
  int v16; // r9d
  _QWORD *v17; // rbx
  ULONGLONG *v18; // r9
  _DWORD *v19; // rcx
  int UserToken; // edi
  _QWORD *v21; // rsi
  __int64 v22; // r15
  void *v23; // r14
  DWORD LastError; // ebx
  int v25; // eax
  unsigned int v26; // ebx
  __int64 v27; // rcx
  PSID *v28; // rdi
  int v29; // eax
  __int64 v30; // rbx
  bool v31; // si
  int v32; // eax
  __int64 v33; // rax
  __int64 v34; // rcx
  int v35; // eax
  _QWORD *v36; // rbx
  int v37; // esi
  int v38; // eax
  __int64 v39; // rcx
  bool v40; // bl
  int v41; // eax
  int v42; // eax
  __int64 v43; // rdx
  int IsEmpty; // eax
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  char v48; // r13
  char *v49; // rbx
  char v50; // r15
  int v51; // eax
  int PackageSetupPhase; // eax
  __int64 v53; // rdx
  PSID v54; // rdx
  int v55; // eax
  __int64 v56; // rcx
  LPCWCH v57; // rax
  __int64 v58; // rcx
  LPCWCH v59; // r12
  __int64 v60; // rsi
  char *v61; // rax
  int *v62; // rsi
  unsigned int EffectivePackageStatusForUser; // eax
  __int64 v64; // rdx
  _DWORD *v65; // rax
  int v66; // r8d
  int v67; // r9d
  _DWORD *v68; // rax
  int v69; // r8d
  int v70; // r9d
  _DWORD *v71; // rax
  int v72; // r8d
  int v73; // r9d
  int *v74; // r12
  int v75; // eax
  int *v76; // r14
  int v77; // eax
  int v78; // eax
  WCHAR *v79; // r13
  int v80; // eax
  int v81; // eax
  __int64 v82; // rcx
  __int64 v83; // rsi
  _DWORD *v84; // rax
  int v85; // r8d
  int v86; // r9d
  unsigned int PackageStatusForUserSid; // eax
  __int64 v88; // rcx
  char v89; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v90[7]; // [rsp+31h] [rbp-CFh] BYREF
  __int64 v91; // [rsp+38h] [rbp-C8h] BYREF
  WINBOOL fPending; // [rsp+40h] [rbp-C0h] BYREF
  char v93; // [rsp+44h] [rbp-BCh] BYREF
  bool v94; // [rsp+45h] [rbp-BBh]
  char v95[2]; // [rsp+46h] [rbp-BAh] BYREF
  LPVOID Context; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v97; // [rsp+50h] [rbp-B0h] BYREF
  int v98; // [rsp+58h] [rbp-A8h] BYREF
  int v99; // [rsp+5Ch] [rbp-A4h]
  __int64 v100; // [rsp+60h] [rbp-A0h] BYREF
  void *v101; // [rsp+68h] [rbp-98h] BYREF
  int *v102; // [rsp+70h] [rbp-90h] BYREF
  __int64 v103; // [rsp+78h] [rbp-88h] BYREF
  int *v104; // [rsp+80h] [rbp-80h]
  LPCWCH v105; // [rsp+88h] [rbp-78h] BYREF
  LPCWCH lpString1[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v107; // [rsp+A0h] [rbp-60h]
  __int64 v108; // [rsp+A8h] [rbp-58h]
  __int64 v109; // [rsp+B0h] [rbp-50h]
  __int64 v110; // [rsp+B8h] [rbp-48h]
  __int64 v111; // [rsp+C0h] [rbp-40h]
  __int64 v112; // [rsp+C8h] [rbp-38h]
  __int128 v113; // [rsp+D0h] [rbp-30h]
  int v114; // [rsp+E0h] [rbp-20h]
  __int64 v115; // [rsp+E8h] [rbp-18h]
  __int64 v116; // [rsp+F0h] [rbp-10h]
  __int64 v117; // [rsp+100h] [rbp+0h]
  _QWORD *v118; // [rsp+108h] [rbp+8h]
  GUID ProviderId; // [rsp+110h] [rbp+10h] BYREF
  __int64 v120; // [rsp+120h] [rbp+20h]
  __int64 v121; // [rsp+130h] [rbp+30h] BYREF
  __int128 v122; // [rsp+138h] [rbp+38h]
  __int128 v123; // [rsp+148h] [rbp+48h]
  __int128 v124; // [rsp+158h] [rbp+58h]
  __int128 v125; // [rsp+168h] [rbp+68h]
  int v126; // [rsp+178h] [rbp+78h]
  __int64 v127; // [rsp+180h] [rbp+80h]
  __int64 v128; // [rsp+190h] [rbp+90h] BYREF
  __int128 v129; // [rsp+198h] [rbp+98h]
  __int128 v130; // [rsp+1A8h] [rbp+A8h]
  __int128 v131; // [rsp+1B8h] [rbp+B8h]
  __int128 v132; // [rsp+1C8h] [rbp+C8h]
  int v133; // [rsp+1D8h] [rbp+D8h]
  __int64 v134; // [rsp+1E0h] [rbp+E0h]
  void *retaddr; // [rsp+238h] [rbp+138h]

  v8 = a2;
  v9 = a1;
  v117 = a2;
  v101 = a1;
  v105 = a6;
  v118 = a8;
  v104 = a4;
  v99 = a3;
  v102 = a7;
  if ( !a4 )
  {
    sub_180008A1C(retaddr, 2692, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", 2147942487LL);
    return 2147942487LL;
  }
  *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *(_DWORD *)a6 = 0;
  if ( a7 )
    *a7 = 0;
  if ( (unsigned __int8)RtlIsMultiUsersInSessionSku() )
  {
    fPending = 0;
    v97 = 0;
    v13 = sub_1800A76D4((unsigned int)off_1801025A0, (unsigned int)&v97, v11, (unsigned int)L"SharedAppsEnabled");
    v12 = 0;
    v14 = 0;
    if ( v13 >= 0 )
      v14 = fPending;
    LOBYTE(v12) = v14 != 0;
    LODWORD(v100) = v12;
  }
  else
  {
    v12 = 0;
    LODWORD(v100) = 0;
  }
  v126 = 0;
  v93 = 0;
  v121 = 0;
  v127 = 0;
  v122 = 0;
  v94 = 1;
  v123 = 0;
  v97 = 0;
  v124 = 0;
  Context = 0;
  v125 = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&InitOnce, 0, &fPending, &Context) && fPending )
  {
    qword_180153340 = 0;
    Context = &qword_180153338;
    qword_180153338 = (__int64)off_1800E7DA8;
    byte_180153348 = 0;
    dword_18015334C = 0;
    CallbackContext = &qword_180152078;
    atexit(sub_18002DD70);
    v17 = CallbackContext;
    qword_180153340 = (__int64)CallbackContext;
    byte_180153348 = 1;
    ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
    if ( *((_QWORD *)CallbackContext + 4) )
      __fastfail(5u);
    v18 = (ULONGLONG *)((char *)CallbackContext + 32);
    *((_QWORD *)CallbackContext + 5) = 0;
    v17[6] = 0;
    if ( !EventRegister(&ProviderId, (PENABLECALLBACK)EnableCallback, v17, v18) )
      EventSetInformation(v17[4], 2, v17[1], *(unsigned __int16 *)v17[1]);
    dword_18015334C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180153338 + 8))(&qword_180153338);
    InitOnceComplete(&InitOnce, 0, &qword_180153338);
    v8 = v117;
  }
  v19 = (_DWORD *)*((_QWORD *)Context + 1);
  if ( *v19 > 5u )
  {
    Context = v9;
    sub_180020F74((_DWORD)v19, (unsigned int)&dword_18013E49C, v15, v16, (__int64)&Context);
  }
  if ( v8 )
  {
    if ( !(unsigned __int8)sub_180054568() )
    {
      sub_180008A1C(retaddr, 2716, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", 2147500033LL);
      return 2147500033LL;
    }
    Context = 0;
    *(_QWORD *)&ProviderId.Data1 = &Context;
    *(_QWORD *)ProviderId.Data4 = 0;
    LOBYTE(v120) = 1;
    UserToken = UMgrQueryUserToken(v8, ProviderId.Data4);
    if ( (_BYTE)v120 )
    {
      v21 = *(_QWORD **)&ProviderId.Data1;
      v22 = *(_QWORD *)ProviderId.Data4;
      v23 = **(void ***)&ProviderId.Data1;
      if ( (unsigned __int64)(**(_QWORD **)&ProviderId.Data1 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        LastError = GetLastError();
        CloseHandle(v23);
        SetLastError(LastError);
      }
      v9 = v101;
      *v21 = v22;
    }
    if ( UserToken < 0 )
    {
      sub_180008A1C(
        retaddr,
        2719,
        "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
        (unsigned int)UserToken);
      if ( (char *)Context - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(Context);
      return (unsigned int)UserToken;
    }
    v25 = sub_1800237B8(&v97, Context);
    v26 = v25;
    if ( v25 < 0 )
    {
      sub_180008A1C(retaddr, 2721, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v25);
      if ( (char *)Context - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(Context);
      v27 = v97;
      if ( v97 )
        goto LABEL_38;
      return v26;
    }
    v28 = (PSID *)v97;
    if ( v12 )
      v94 = IsWellKnownSid(*(PSID *)v97, WinLocalAccountAndAdministratorSid|WinCreatorGroupSid);
    v97 = 0;
    v29 = sub_1800237B8(&v97, 0);
    v26 = v29;
    if ( v29 < 0 )
    {
      sub_180008A1C(retaddr, 2728, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v29);
      if ( v97 )
        j__o_free(v97);
      if ( (char *)Context - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(Context);
LABEL_115:
      if ( v28 )
        j__o_free(v28);
      return v26;
    }
    v30 = v97;
    v31 = EqualSid(*v28, *(PSID *)v97);
    v89 = v31;
    if ( v30 )
      j__o_free(v30);
    if ( (char *)Context - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(Context);
  }
  else
  {
    v32 = sub_1800237B8(&v97, 0);
    v26 = v32;
    if ( v32 < 0 )
    {
      sub_180008A1C(retaddr, 2737, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v32);
      v27 = v97;
      if ( v97 )
      {
LABEL_38:
        j__o_free(v27);
        return v26;
      }
      return v26;
    }
    v28 = (PSID *)v97;
    if ( v12 )
      v94 = IsWellKnownSid(*(PSID *)v97, WinLocalAccountAndAdministratorSid|WinCreatorGroupSid);
    v31 = 1;
    v89 = 1;
  }
  v91 = 0;
  *(_QWORD *)&ProviderId.Data1 = &v91;
  *(_QWORD *)ProviderId.Data4 = 0;
  LOBYTE(v120) = 1;
  v26 = SRCacheManager_Open(0, ProviderId.Data4);
  if ( (_BYTE)v120 )
  {
    v33 = **(_QWORD **)&ProviderId.Data1;
    **(_QWORD **)&ProviderId.Data1 = *(_QWORD *)ProviderId.Data4;
    if ( v33 )
      SRCacheManager_Close(v33);
  }
  if ( (v26 & 0x80000000) != 0 )
  {
    sub_180008A1C(
      retaddr,
      165,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      v26);
    sub_180008A1C(retaddr, 2746, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", v26);
    v34 = v91;
    v91 = 0;
    goto LABEL_113;
  }
  v103 = 0;
  v35 = sub_180007320(&v91, v9, &v103);
  v26 = v35;
  if ( v35 < 0 )
  {
    sub_180008A1C(retaddr, 2748, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v35);
    v34 = v91;
    v91 = 0;
    goto LABEL_113;
  }
  if ( v31 )
  {
    fPending = 0;
    if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, 0, 0, (PDWORD)&fPending) || GetLastError() != 122 )
    {
      v37 = sub_180035D44(retaddr, 279, "onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h");
    }
    else
    {
      v36 = (_QWORD *)sub_180051C4C((unsigned int)fPending, &qword_18010CB78);
      if ( !v36 )
      {
        v37 = -2147024882;
        sub_180008A1C(retaddr, 281, "onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h", 2147942414LL);
LABEL_72:
        sub_180008A1C(
          retaddr,
          351,
          "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
          (unsigned int)v37);
LABEL_75:
        sub_180008A1C(retaddr, 2752, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v37);
        v39 = v91;
        v91 = 0;
LABEL_199:
        if ( v39 )
          SRCacheManager_Close(v39);
        if ( v28 )
          j__o_free(v28);
        return (unsigned int)v37;
      }
      if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, v36, fPending, (PDWORD)&fPending) )
        goto LABEL_73;
      v37 = sub_180035D44(retaddr, 282, "onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h");
      j__o_free(v36);
    }
    v36 = 0;
    if ( v37 < 0 )
      goto LABEL_72;
LABEL_73:
    v38 = sub_180005410(&v91, *v36, 0, &v121, &v93);
    v37 = v38;
    if ( v38 < 0 )
    {
      sub_180008A1C(
        retaddr,
        352,
        "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
        (unsigned int)v38);
      j__o_free(v36);
      goto LABEL_75;
    }
    j__o_free(v36);
    goto LABEL_77;
  }
  v41 = sub_180005410(&v91, *v28, 1, &v121, &v93);
  v26 = v41;
  if ( v41 < 0 )
  {
    sub_180008A1C(retaddr, 2756, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v41);
    v34 = v91;
    v91 = 0;
    goto LABEL_113;
  }
LABEL_77:
  if ( v12 )
    goto LABEL_98;
  if ( !v103 )
  {
    v40 = 0;
    goto LABEL_92;
  }
  *(_QWORD *)&ProviderId.Data1 = 0;
  *(_DWORD *)ProviderId.Data4 = 0;
  v120 = 0;
  v42 = sub_18001C720(&ProviderId, &v91);
  v26 = v42;
  if ( v42 < 0 )
  {
    sub_180008A1C(
      retaddr,
      2079,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (unsigned int)v42);
    v43 = 2055;
LABEL_87:
    sub_180008A1C(
      retaddr,
      v43,
      "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      v26);
    v45 = *(_QWORD *)&ProviderId.Data1;
    *(_QWORD *)&ProviderId.Data1 = 0;
    if ( v45 )
      SRCacheContext_Close(v45);
    sub_180008A1C(retaddr, 2450, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", v26);
    sub_180008A1C(retaddr, 2766, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", v26);
    v34 = v91;
    v91 = 0;
    goto LABEL_113;
  }
  v40 = 0;
  if ( *(_QWORD *)&ProviderId.Data1 )
  {
    fPending = 0;
    IsEmpty = SRCacheContext_IsEmpty(*(_QWORD *)&ProviderId.Data1, &fPending);
    v26 = IsEmpty;
    if ( IsEmpty < 0 )
    {
      sub_180008A1C(
        retaddr,
        696,
        "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (unsigned int)IsEmpty);
      sub_180008A1C(
        retaddr,
        1996,
        "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
        v26);
      v43 = 2061;
      goto LABEL_87;
    }
    v46 = *(_QWORD *)&ProviderId.Data1;
    v40 = fPending == 0;
    *(_QWORD *)&ProviderId.Data1 = 0;
    if ( v46 )
      SRCacheContext_Close(v46);
  }
LABEL_92:
  if ( !v40 )
  {
    v47 = v91;
    v91 = 0;
    if ( v47 )
      SRCacheManager_Close(v47);
    if ( v28 )
      j__o_free(v28);
    return 2147958001LL;
  }
LABEL_98:
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v95[0] = 0;
  v90[0] = 0;
  if ( !v93 )
    goto LABEL_135;
  v107 = 0;
  *(_OWORD *)lpString1 = 0;
  v108 = 0;
  v109 = 0;
  v110 = 0;
  v111 = 0;
  v112 = 0;
  v113 = 0;
  v114 = 0;
  v115 = 0;
  v116 = 0;
  v51 = sub_18002F640(
          (unsigned int)&v91,
          v103,
          (unsigned int)&v121,
          (unsigned int)lpString1,
          (__int64)v90,
          (__int64)v95);
  v37 = v51;
  if ( v51 < 0 )
  {
    sub_180008A1C(retaddr, 2783, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v51);
    sub_180006C5C(lpString1);
    v39 = v91;
    v91 = 0;
    goto LABEL_199;
  }
  v50 = v90[0];
  v48 = v95[0];
  if ( v90[0] )
  {
    v57 = lpString1[1];
    if ( !lpString1[1] )
      sub_18005ED70(retaddr, 3977, "onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h");
    v58 = 0x7FFFFFFF;
    v59 = lpString1[1];
    do
    {
      if ( !*v57 )
        break;
      ++v57;
      --v58;
    }
    while ( v58 );
    v60 = 2 * (v57 - lpString1[1]);
    v61 = (char *)CoTaskMemAlloc(v60 + 2);
    v49 = v61;
    if ( !v61 )
    {
      v37 = -2147024882;
      v53 = 2832;
      goto LABEL_108;
    }
    sub_1800242FC(v61, v60 + 2, v59, v60);
    *(_WORD *)&v49[v60] = 0;
LABEL_134:
    sub_180006C5C(lpString1);
    if ( v50 )
    {
      v62 = v104;
LABEL_138:
      v98 = 0;
      if ( v50 )
      {
        if ( v89 )
        {
          EffectivePackageStatusForUser = GetEffectivePackageStatusForUser(0, v49, &v98);
          if ( EffectivePackageStatusForUser )
          {
            v64 = 2848;
LABEL_142:
            v37 = sub_180035D98(
                    retaddr,
                    v64,
                    "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
                    EffectivePackageStatusForUser);
            goto LABEL_143;
          }
        }
        else
        {
          EffectivePackageStatusForUser = GetEffectivePackageStatusForUserSid(v127, v49, &v98);
          if ( EffectivePackageStatusForUser )
          {
            v64 = 2852;
            goto LABEL_142;
          }
        }
        v65 = (_DWORD *)sub_180021358();
        if ( *v65 > 5u )
        {
          LODWORD(Context) = v98;
          v101 = v49;
          sub_180022490((_DWORD)v65, (unsigned int)&byte_18013E437, v66, v67, (__int64)&v101, (__int64)&Context);
        }
        if ( (v98 & 0x489920) != 0 )
        {
          *v62 = 1;
          v68 = (_DWORD *)sub_180021358();
          if ( *v68 > 5u )
          {
            LODWORD(Context) = v98;
            v101 = v49;
            sub_180022490((_DWORD)v68, (unsigned int)&byte_18013E38F, v69, v70, (__int64)&v101, (__int64)&Context);
          }
        }
        else
        {
          sub_18001AD98(qword_180153E60);
          if ( !v48 )
            goto LABEL_157;
          *v62 = 1;
        }
        sub_18001AD98(qword_180153E60);
        if ( v48 )
        {
          v71 = (_DWORD *)sub_180021358();
          if ( *v71 > 5u )
          {
            v101 = v49;
            sub_180020F74((_DWORD)v71, (unsigned int)byte_18013E3D3, v72, v73, (__int64)&v101);
          }
        }
      }
LABEL_157:
      if ( !(_DWORD)v100 || v94 )
        goto LABEL_207;
      v74 = v102;
      if ( !v50 && !v102 )
        goto LABEL_210;
      v102 = 0;
      v75 = sub_1800916E0(&v102);
      v37 = v75;
      if ( v75 < 0 )
      {
        sub_180008A1C(retaddr, 2897, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v75);
LABEL_196:
        if ( v49 )
          CoTaskMemFree(v49);
        v39 = v91;
        v91 = 0;
        goto LABEL_199;
      }
      v76 = v102;
      v128 = 0;
      v134 = 0;
      v133 = 0;
      v89 = 0;
      v129 = 0;
      v130 = 0;
      v131 = 0;
      v132 = 0;
      v77 = sub_180005410(&v91, v102, 1, &v128, &v89);
      v37 = v77;
      if ( v77 < 0 )
      {
        sub_180008A1C(retaddr, 2901, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v77);
        goto LABEL_196;
      }
      if ( !v89 )
      {
        if ( v74 )
          *v74 = v99;
LABEL_207:
        if ( v50 && v118 )
        {
          *v118 = v49;
LABEL_212:
          v88 = v91;
          v91 = 0;
          if ( v88 )
            SRCacheManager_Close(v88);
          if ( v28 )
            j__o_free(v28);
          return 0;
        }
LABEL_210:
        if ( v49 )
          CoTaskMemFree(v49);
        goto LABEL_212;
      }
      v107 = 0;
      *(_OWORD *)lpString1 = 0;
      v108 = 0;
      v109 = 0;
      v110 = 0;
      v111 = 0;
      v112 = 0;
      v113 = 0;
      v114 = 0;
      v115 = 0;
      v116 = 0;
      v89 = 0;
      v90[0] = 0;
      v78 = sub_18002F640(
              (unsigned int)&v91,
              v103,
              (unsigned int)&v128,
              (unsigned int)lpString1,
              (__int64)&v89,
              (__int64)v90);
      v37 = v78;
      if ( v78 < 0 )
      {
        sub_180008A1C(retaddr, 2914, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v78);
LABEL_195:
        sub_180006C5C(lpString1);
        goto LABEL_196;
      }
      if ( !v89 )
      {
        if ( v74 )
          *v74 = v99;
        goto LABEL_206;
      }
      if ( v50 && CompareStringOrdinal(lpString1[1], -1, (LPCWCH)v49, -1, 1) != 2 )
      {
        v79 = (WCHAR *)v105;
        if ( v105 )
        {
          v97 = 0;
          v80 = sub_1800C5AF8((LPCWCH)v49);
          v37 = v80;
          if ( v80 < 0 )
          {
            sub_180008A1C(
              retaddr,
              2930,
              "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
              (unsigned int)v80);
LABEL_178:
            if ( v97 )
              j_j__o_free(v97);
            sub_180006C5C(lpString1);
LABEL_143:
            if ( v49 )
            {
              CoTaskMemFree(v49);
              v39 = v91;
              v91 = 0;
              goto LABEL_199;
            }
            goto LABEL_109;
          }
          v100 = 0;
          v81 = sub_1800C5AF8(lpString1[1]);
          v37 = v81;
          if ( v81 < 0 )
          {
            sub_180008A1C(
              retaddr,
              2933,
              "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
              (unsigned int)v81);
            if ( v100 )
              j_j__o_free(v100);
            goto LABEL_178;
          }
          v82 = v100;
          v83 = v97;
          if ( *(_QWORD *)(v97 + 8) > *(_QWORD *)(v100 + 8) )
            *(_DWORD *)v79 = 1;
          if ( v82 )
            j_j__o_free(v82);
          if ( v83 )
            j_j__o_free(v83);
        }
        *v104 = 1;
        v84 = (_DWORD *)sub_180021358();
        if ( *v84 > 5u )
        {
          v105 = lpString1[1];
          v101 = v49;
          sub_180001008((_DWORD)v84, (unsigned int)&dword_18013E33C, v85, v86, (__int64)&v101, (__int64)&v105);
        }
      }
      if ( v74 )
      {
        LODWORD(v100) = 0;
        PackageStatusForUserSid = GetPackageStatusForUserSid(v76, lpString1[1], &v100);
        if ( PackageStatusForUserSid )
        {
          v37 = sub_180035D98(
                  retaddr,
                  2954,
                  "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
                  PackageStatusForUserSid);
          goto LABEL_195;
        }
        if ( (v100 & 0x481820) != 0 )
          *v74 = 1;
      }
LABEL_206:
      sub_180006C5C(lpString1);
      goto LABEL_207;
    }
LABEL_135:
    v62 = v104;
    *v104 = v99;
    goto LABEL_138;
  }
  fPending = 0;
  PackageSetupPhase = GetPackageSetupPhase(v9, &fPending);
  if ( PackageSetupPhase >= 0 )
  {
    if ( (fPending & 0x400) != 0 )
    {
LABEL_127:
      v99 = 1;
      goto LABEL_134;
    }
  }
  else
  {
    sub_18000B614(
      retaddr,
      2791,
      "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
      (unsigned int)PackageSetupPhase);
  }
  sub_18001AD98(qword_180153E60);
  if ( v48 )
    goto LABEL_127;
  LODWORD(Context) = 0;
  v37 = HasPackageFamilyBeenRegisteredForUser(v9, v117, &Context);
  if ( v37 < 0 )
  {
    v53 = 2799;
LABEL_108:
    sub_180008A1C(retaddr, v53, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v37);
    sub_180006C5C(lpString1);
LABEL_109:
    v39 = v91;
    v91 = 0;
    goto LABEL_199;
  }
  if ( !(_DWORD)Context )
    goto LABEL_134;
  v54 = *v28;
  v90[0] = 0;
  v55 = sub_180037868(v9, v54, v90);
  v26 = v55;
  if ( v55 < 0 )
  {
    sub_180008A1C(retaddr, 2809, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v55);
    sub_180006C5C(lpString1);
    v34 = v91;
    v91 = 0;
LABEL_113:
    if ( v34 )
      SRCacheManager_Close(v34);
    goto LABEL_115;
  }
  if ( v90[0] )
  {
    if ( a5 )
      *a5 = 1;
    *v104 = 1;
    sub_180006C5C(lpString1);
    goto LABEL_212;
  }
  sub_180008A1C(retaddr, 2824, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", 2150040148LL);
  sub_180006C5C(lpString1);
  v56 = v91;
  v91 = 0;
  if ( v56 )
    SRCacheManager_Close(v56);
  if ( v28 )
    j__o_free(v28);
  return 2150040148LL;
}

```

## disassembly

```asm
0x18002aa30  push    rbp
0x18002aa32  push    rbx
0x18002aa33  push    r12
0x18002aa35  push    r14
0x18002aa37  lea     rbp, [rsp-118h]
0x18002aa3f  sub     rsp, 218h
0x18002aa46  mov     rax, cs:__security_cookie
0x18002aa4d  xor     rax, rsp
0x18002aa50  mov     [rbp+130h+var_40], rax
0x18002aa57  mov     rax, [rbp+130h+arg_30]
0x18002aa5e  mov     rbx, rdx
0x18002aa61  mov     r12, [rbp+130h+arg_20]
0x18002aa68  mov     r14, rcx
0x18002aa6b  mov     [rbp+130h+var_130], rdx
0x18002aa6f  mov     rdx, [rbp+130h+arg_38]
0x18002aa76  mov     [rsp+230h+var_1C8], rcx
0x18002aa7b  mov     rcx, [rbp+130h+arg_28]
0x18002aa82  mov     [rbp+130h+var_1A8], rcx
0x18002aa86  mov     [rbp+130h+var_128], rdx
0x18002aa8a  mov     [rbp+130h+var_1B0], r9
0x18002aa8e  mov     [rsp+230h+var_1D4], r8d
0x18002aa93  mov     [rsp+230h+var_1C0], rax
0x18002aa98  test    r9, r9
0x18002aa9b  jnz     short loc_18002AAC5
0x18002aa9d  mov     rcx, [rbp+138h]
0x18002aaa4  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18002aaab  mov     r9d, 80070057h
0x18002aab1  mov     edx, 0A84h
0x18002aab6  call    sub_180008A1C
0x18002aabb  mov     eax, 80070057h
0x18002aac0  jmp     loc_18002BBE0
0x18002aac5  mov     [rsp+230h+var_30], r15
0x18002aacd  xor     r15d, r15d
0x18002aad0  mov     [r9], r15d
0x18002aad3  test    r12, r12
0x18002aad6  jz      short loc_18002AADC
0x18002aad8  mov     [r12], r15d
0x18002aadc  test    rcx, rcx
0x18002aadf  jz      short loc_18002AAE4
0x18002aae1  mov     [rcx], r15d
0x18002aae4  test    rax, rax
0x18002aae7  jz      short loc_18002AAEC
0x18002aae9  mov     [rax], r15d
0x18002aaec  mov     [rsp+230h+var_28], r13
0x18002aaf4  call    cs:RtlIsMultiUsersInSessionSku
0x18002aafa  test    al, al
0x18002aafc  jnz     short loc_18002AB08
0x18002aafe  mov     r13d, r15d
0x18002ab01  mov     dword ptr [rsp+230h+var_1D0], r15d
0x18002ab06  jmp     short loc_18002AB4C
0x18002ab08  lea     rax, [rsp+230h+fPending]
0x18002ab0d  mov     [rsp+230h+fPending], r15d
0x18002ab12  lea     r9, aSharedappsenab; "SharedAppsEnabled"
0x18002ab19  mov     [rsp+230h+var_208], rax
0x18002ab1e  lea     rdx, [rsp+230h+var_1E0]
0x18002ab23  mov     [rsp+230h+var_1E0], r15
0x18002ab28  lea     rcx, off_1801025A0; "AppxRoot"
0x18002ab2f  call    sub_1800A76D4
0x18002ab34  test    eax, eax
0x18002ab36  mov     r13d, r15d
0x18002ab39  mov     ecx, r15d
0x18002ab3c  cmovns  ecx, [rsp+230h+fPending]
0x18002ab41  test    ecx, ecx
0x18002ab43  setnz   r13b
0x18002ab47  mov     dword ptr [rsp+230h+var_1D0], r13d
0x18002ab4c  xorps   xmm0, xmm0
0x18002ab4f  mov     [rsp+230h+arg_10], rsi
0x18002ab57  xor     eax, eax
0x18002ab59  mov     [rsp+230h+var_20], rdi
0x18002ab61  lea     r9, [rsp+230h+Context]; lpContext
0x18002ab66  mov     [rbp+130h+var_B8], eax
0x18002ab69  lea     r8, [rsp+230h+fPending]; fPending
0x18002ab6e  mov     [rsp+230h+var_1EC], al
0x18002ab72  xor     edx, edx; dwFlags
0x18002ab74  mov     [rbp+130h+var_100], r15
0x18002ab78  lea     rcx, InitOnce; lpInitOnce
0x18002ab7f  mov     [rbp+130h+var_B0], r15
0x18002ab86  movups  [rbp+130h+var_F8], xmm0
0x18002ab8a  mov     [rsp+230h+var_1EB], 1
0x18002ab8f  movups  [rbp+130h+var_E8], xmm0
0x18002ab93  mov     [rsp+230h+var_1E0], r15
0x18002ab98  movups  [rbp+130h+var_D8], xmm0
0x18002ab9c  mov     [rsp+230h+Context], r15
0x18002aba1  movups  [rbp+130h+var_C8], xmm0
0x18002aba5  mov     [rsp+230h+fPending], r15d
0x18002abaa  call    cs:InitOnceBeginInitialize
0x18002abb0  test    eax, eax
0x18002abb2  jz      loc_18002ACA8
0x18002abb8  cmp     [rsp+230h+fPending], r15d
0x18002abbd  jz      loc_18002ACA8
0x18002abc3  lea     rsi, qword_180153338
0x18002abca  mov     cs:qword_180153340, r15
0x18002abd1  lea     rax, off_1800E7DA8
0x18002abd8  mov     [rsp+230h+Context], rsi
0x18002abdd  mov     cs:qword_180153338, rax
0x18002abe4  mov     cs:byte_180153348, r15b
0x18002abeb  mov     cs:dword_18015334C, r15d
0x18002abf2  lea     rax, qword_180152078
0x18002abf9  lea     rcx, sub_18002DD70; void (__cdecl *)()
0x18002ac00  mov     cs:CallbackContext, rax
0x18002ac07  call    atexit
0x18002ac0c  mov     rbx, cs:CallbackContext
0x18002ac13  mov     cs:qword_180153340, rbx
0x18002ac1a  mov     cs:byte_180153348, 1
0x18002ac21  mov     rax, [rbx+8]
0x18002ac25  movups  xmm0, xmmword ptr [rax-10h]
0x18002ac29  movups  xmmword ptr [rbp+130h+ProviderId.Data1], xmm0
0x18002ac2d  cmp     [rbx+20h], r15
0x18002ac31  jz      short loc_18002AC3A
0x18002ac33  mov     ecx, 5
0x18002ac38  int     29h; Win8: RtlFailFast(ecx)
0x18002ac3a  lea     r9, [rbx+20h]; RegHandle
0x18002ac3e  mov     [rbx+28h], r15
0x18002ac42  mov     r8, rbx; CallbackContext
0x18002ac45  mov     [rbx+30h], r15
0x18002ac49  lea     rdx, EnableCallback; EnableCallback
0x18002ac50  lea     rcx, [rbp+130h+ProviderId]; ProviderId
0x18002ac54  call    cs:EventRegister
0x18002ac5a  test    eax, eax
0x18002ac5c  jnz     short loc_18002AC75
0x18002ac5e  mov     r8, [rbx+8]
0x18002ac62  mov     edx, 2
0x18002ac67  mov     rcx, [rbx+20h]
0x18002ac6b  movzx   r9d, word ptr [r8]
0x18002ac6f  call    cs:EventSetInformation
0x18002ac75  mov     rax, cs:qword_180153338
0x18002ac7c  mov     rcx, rsi
0x18002ac7f  mov     cs:dword_18015334C, 1
0x18002ac89  mov     rax, [rax+8]
0x18002ac8d  call    j__guard_dispatch_icall
0x18002ac92  mov     r8, rsi; lpContext
0x18002ac95  lea     rcx, InitOnce; lpInitOnce
0x18002ac9c  xor     edx, edx; dwFlags
0x18002ac9e  call    cs:InitOnceComplete
0x18002aca4  mov     rbx, [rbp+130h+var_130]
0x18002aca8  mov     rax, [rsp+230h+Context]
0x18002acad  mov     rcx, [rax+8]
0x18002acb1  mov     eax, [rcx]
0x18002acb3  cmp     eax, 5
0x18002acb6  jbe     short loc_18002ACD3
0x18002acb8  lea     rax, [rsp+230h+Context]
0x18002acbd  mov     [rsp+230h+Context], r14
0x18002acc2  lea     rdx, dword_18013E49C
0x18002acc9  mov     [rsp+230h+ReturnLength], rax
0x18002acce  call    sub_180020F74
0x18002acd3  test    rbx, rbx
0x18002acd6  jz      loc_18002AECC
0x18002acdc  call    sub_180054568
0x18002ace1  test    al, al
0x18002ace3  jnz     short loc_18002AD0D
0x18002ace5  mov     rcx, [rbp+138h]
0x18002acec  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18002acf3  mov     r9d, 80004001h
0x18002acf9  mov     edx, 0A9Ch
0x18002acfe  call    sub_180008A1C
0x18002ad03  mov     eax, 80004001h
0x18002ad08  jmp     loc_18002BBC0
0x18002ad0d  lea     rax, [rsp+230h+Context]
0x18002ad12  mov     [rsp+230h+Context], r15
0x18002ad17  lea     rdx, [rbp+130h+ProviderId.Data4]
0x18002ad1b  mov     qword ptr [rbp+130h+ProviderId.Data1], rax
0x18002ad1f  mov     rcx, rbx
0x18002ad22  mov     qword ptr [rbp+130h+ProviderId.Data4], r15
0x18002ad26  mov     byte ptr [rbp+130h+var_110], 1
0x18002ad2a  call    cs:UMgrQueryUserToken
0x18002ad30  mov     edi, eax
0x18002ad32  cmp     byte ptr [rbp+130h+var_110], r15b
0x18002ad36  jz      short loc_18002AD71
0x18002ad38  mov     rsi, qword ptr [rbp+130h+ProviderId.Data1]
0x18002ad3c  mov     r15, qword ptr [rbp+130h+ProviderId.Data4]
0x18002ad40  mov     r14, [rsi]
0x18002ad43  lea     rcx, [r14-1]
0x18002ad47  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002ad4b  ja      short loc_18002AD66
0x18002ad4d  call    cs:GetLastError
0x18002ad53  mov     rcx, r14; hObject
0x18002ad56  mov     ebx, eax
0x18002ad58  call    cs:CloseHandle
0x18002ad5e  mov     ecx, ebx; dwErrCode
0x18002ad60  call    cs:SetLastError
0x18002ad66  mov     r14, [rsp+230h+var_1C8]
0x18002ad6b  mov     [rsi], r15
0x18002ad6e  xor     r15d, r15d
0x18002ad71  test    edi, edi
0x18002ad73  jns     short loc_18002ADAC
0x18002ad75  mov     rcx, [rbp+138h]
0x18002ad7c  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18002ad83  mov     r9d, edi
0x18002ad86  mov     edx, 0A9Fh
0x18002ad8b  call    sub_180008A1C
0x18002ad90  mov     rcx, [rsp+230h+Context]; hObject
0x18002ad95  lea     rax, [rcx-1]
0x18002ad99  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ad9d  ja      short loc_18002ADA5
0x18002ad9f  call    cs:CloseHandle
0x18002ada5  mov     eax, edi
0x18002ada7  jmp     loc_18002BBC0
0x18002adac  mov     rdx, [rsp+230h+Context]
0x18002adb1  lea     rcx, [rsp+230h+var_1E0]
0x18002adb6  call    sub_1800237B8
0x18002adbb  mov     ebx, eax
0x18002adbd  test    eax, eax
0x18002adbf  jns     short loc_18002AE0E
0x18002adc1  mov     rcx, [rbp+138h]
0x18002adc8  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18002adcf  mov     r9d, eax
0x18002add2  mov     edx, 0AA1h
0x18002add7  call    sub_180008A1C
0x18002addc  mov     rax, [rsp+230h+Context]
0x18002ade1  lea     rcx, [rax-1]
0x18002ade5  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002ade9  ja      short loc_18002ADF4
0x18002adeb  mov     rcx, rax; hObject
0x18002adee  call    cs:CloseHandle
0x18002adf4  mov     rcx, [rsp+230h+var_1E0]
0x18002adf9  test    rcx, rcx
0x18002adfc  jz      loc_18002B547
0x18002ae02  call    j__o_free
0x18002ae07  mov     eax, ebx
0x18002ae09  jmp     loc_18002BBC0
0x18002ae0e  mov     rdi, [rsp+230h+var_1E0]
0x18002ae13  test    r13d, r13d
0x18002ae16  jz      short loc_18002AE2D
0x18002ae18  mov     rcx, [rdi]; pSid
0x18002ae1b  mov     edx, 6Eh ; 'n'; WellKnownSidType
0x18002ae20  call    cs:IsWellKnownSid
0x18002ae26  test    eax, eax
0x18002ae28  setnz   [rsp+230h+var_1EB]
0x18002ae2d  xor     edx, edx
0x18002ae2f  mov     [rsp+230h+var_1E0], r15
0x18002ae34  lea     rcx, [rsp+230h+var_1E0]
0x18002ae39  call    sub_1800237B8
0x18002ae3e  mov     ebx, eax
0x18002ae40  test    eax, eax
0x18002ae42  jns     short loc_18002AE8C
0x18002ae44  mov     rcx, [rbp+138h]
0x18002ae4b  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18002ae52  mov     r9d, eax
0x18002ae55  mov     edx, 0AA8h
0x18002ae5a  call    sub_180008A1C
0x18002ae5f  mov     rcx, [rsp+230h+var_1E0]
0x18002ae64  test    rcx, rcx
0x18002ae67  jz      short loc_18002AE6E
0x18002ae69  call    j__o_free
0x18002ae6e  mov     rcx, [rsp+230h+Context]; hObject
0x18002ae73  lea     rax, [rcx-1]
0x18002ae77  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ae7b  ja      loc_18002B53A
0x18002ae81  call    cs:CloseHandle
0x18002ae87  jmp     loc_18002B53A
0x18002ae8c  mov     rbx, [rsp+230h+var_1E0]
0x18002ae91  mov     rcx, [rdi]; pSid1
0x18002ae94  mov     rdx, [rbx]; pSid2
0x18002ae97  call    cs:EqualSid
0x18002ae9d  test    eax, eax
0x18002ae9f  setnz   sil
0x18002aea3  mov     [rsp+230h+var_200], sil
0x18002aea8  test    rbx, rbx
0x18002aeab  jz      short loc_18002AEB5
0x18002aead  mov     rcx, rbx
0x18002aeb0  call    j__o_free
0x18002aeb5  mov     rcx, [rsp+230h+Context]; hObject
0x18002aeba  lea     rax, [rcx-1]
0x18002aebe  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002aec2  ja      short loc_18002AF3A
0x18002aec4  call    cs:CloseHandle
0x18002aeca  jmp     short loc_18002AF3A
0x18002aecc  xor     edx, edx
0x18002aece  lea     rcx, [rsp+230h+var_1E0]
0x18002aed3  call    sub_1800237B8
0x18002aed8  mov     ebx, eax
0x18002aeda  test    eax, eax
0x18002aedc  jns     short loc_18002AF13
0x18002aede  mov     rcx, [rbp+138h]
0x18002aee5  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18002aeec  mov     r9d, eax
0x18002aeef  mov     edx, 0AB1h
0x18002aef4  call    sub_180008A1C
0x18002aef9  mov     rcx, [rsp+230h+var_1E0]
0x18002aefe  test    rcx, rcx
0x18002af01  jz      loc_18002B547
0x18002af07  call    j__o_free
0x18002af0c  mov     eax, ebx
0x18002af0e  jmp     loc_18002BBC0
0x18002af13  mov     rdi, [rsp+230h+var_1E0]
0x18002af18  test    r13d, r13d
0x18002af1b  jz      short loc_18002AF32
0x18002af1d  mov     rcx, [rdi]; pSid
0x18002af20  mov     edx, 6Eh ; 'n'; WellKnownSidType
0x18002af25  call    cs:IsWellKnownSid
0x18002af2b  test    eax, eax
0x18002af2d  setnz   [rsp+230h+var_1EB]
0x18002af32  mov     sil, 1
0x18002af35  mov     [rsp+230h+var_200], sil
0x18002af3a  lea     rax, [rsp+230h+var_1F8]
0x18002af3f  mov     [rsp+230h+var_1F8], r15
0x18002af44  lea     rdx, [rbp+130h+ProviderId.Data4]
0x18002af48  mov     qword ptr [rbp+130h+ProviderId.Data1], rax
0x18002af4c  xor     ecx, ecx
0x18002af4e  mov     qword ptr [rbp+130h+ProviderId.Data4], r15
  ... truncated ...
```
