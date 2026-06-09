# OnCreateProcessCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180006860`
- end: `0x18000786b`
- name: `?OnCreateProcessCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `4107`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005918`
- `0x180005990`
- `0x180006228`
- `0x180006860`
- `0x180007874`
- `0x18000c096`
- `0x18000c0e0`
- `0x18000d010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007779`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007779`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800068ae`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180007767`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800068ae`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180007767`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180007758`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180007758`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800069b8`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800069b8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800074fe`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800074fe`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180006899`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180006899`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800068c9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800068c9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000692d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180006b57`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000692d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180006b57`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180006a92`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180006a92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007615`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007683`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007615`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007683`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000690f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006a06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006a53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006b1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006c31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006cba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006d56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006de3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006e7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006f21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006fdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180007090`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000710b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800071ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180007267`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000731d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000741c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800074be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000758e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180007656`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000690f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006a06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006a53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006b1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006c31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006cba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006d56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006de3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006e7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006f21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006fdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180007090`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000710b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800071ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180007267`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000731d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000741c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800074be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000758e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180007656`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180007751`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180007751`

## string_xrefs

- `0x1800069ff`: `createProcess`
- `0x180006ddc`: `parentPath`
- `0x180007104`: `ntfsId`
- `0x1800071c7`: `safeOpenResults`
- `0x1800074b7`: `createProcFlags`
- `0x18000764f`: `onCreateProcess`
- `0x180006908`: `Windows.Internal.Security.SmartScreen.EventLogger`
- `0x180006a4c`: `Windows.Data.Json.JsonObject`
- `0x180006b14`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall OnCreateProcessCallback(PTP_CALLBACK_INSTANCE Instance, HSTRING Context, PTP_WORK Work)
{
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  int ActivationFactory; // eax
  int (__fastcall ***v9)(_QWORD, GUID *, IUnknown **); // rbx
  int (__fastcall **v10)(_QWORD, _QWORD, _QWORD); // rdi
  HRESULT v11; // eax
  int v12; // edx
  unsigned int v13; // r8d
  int v14; // eax
  HRESULT v15; // eax
  int v16; // edx
  unsigned int v17; // r8d
  int v18; // ebx
  HRESULT v19; // eax
  int v20; // edx
  unsigned int v21; // r8d
  HSTRING v22; // rbx
  int (__fastcall ***v23)(__int64, GUID *, __int64 *); // rcx
  int v24; // eax
  unsigned int v25; // r8d
  unsigned __int64 v26; // rbx
  int (__fastcall ***v27)(__int64, GUID *, __int64 *); // rdi
  int (__fastcall **v28)(__int64, GUID *, __int64 *); // r14
  const WCHAR *v29; // rcx
  unsigned __int64 v30; // rdx
  HRESULT v31; // eax
  int v32; // edx
  unsigned int v33; // r8d
  int v34; // eax
  __int64 *v35; // rdi
  int (__fastcall **v36)(_QWORD, _QWORD, _QWORD); // r14
  __int64 v37; // r15
  HRESULT v38; // eax
  int v39; // edx
  unsigned int v40; // r8d
  int v41; // eax
  int v42; // edx
  unsigned int v43; // r8d
  __int64 v44; // rcx
  int (__fastcall ***v45)(__int64, GUID *, __int64 *); // rdi
  int (__fastcall **v46)(__int64, GUID *, __int64 *); // r14
  const WCHAR *v47; // rcx
  HRESULT v48; // eax
  int v49; // edx
  unsigned int v50; // r8d
  int v51; // eax
  __int64 v52; // rbx
  __int64 (__fastcall *v53)(__int64, __int64 *); // rdi
  __int64 *v54; // rbx
  int (__fastcall **v55)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 v56; // r14
  HRESULT v57; // eax
  int v58; // edx
  unsigned int v59; // r8d
  int v60; // eax
  GUID *v61; // rdx
  int (__fastcall ***v62)(__int64, GUID *, __int64 *); // rbx
  int (__fastcall *v63)(__int64, GUID *, __int64 *); // rdi
  __int64 v64; // rcx
  __int64 *v65; // rbx
  int (__fastcall **v66)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 v67; // r14
  HRESULT v68; // eax
  int v69; // edx
  unsigned int v70; // r8d
  int v71; // eax
  int (__fastcall ***v72)(__int64, GUID *, __int64 *); // rbx
  int (__fastcall *v73)(__int64, GUID *, __int64 *); // rdi
  __int64 v74; // rcx
  __int64 *v75; // rbx
  int (__fastcall **v76)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 v77; // r14
  HRESULT v78; // eax
  int v79; // edx
  unsigned int v80; // r8d
  int v81; // eax
  __int64 v82; // rdx
  int (__fastcall ***v83)(__int64, GUID *, __int64 *); // rbx
  int (__fastcall *v84)(__int64, GUID *, __int64 *); // rdi
  __int64 v85; // rcx
  __int64 v86; // rax
  __int64 *v87; // rbx
  int (__fastcall **v88)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 v89; // r14
  HRESULT v90; // eax
  int v91; // edx
  unsigned int v92; // r8d
  int v93; // eax
  __int64 v94; // rdx
  int v95; // eax
  __int64 v96; // rbx
  __int64 (__fastcall *v97)(__int64, __int64 *); // rdi
  __int64 v98; // rcx
  __int64 *v99; // rbx
  int (__fastcall **v100)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 v101; // r14
  HRESULT v102; // eax
  int v103; // edx
  unsigned int v104; // r8d
  int v105; // eax
  __int64 *v106; // rbx
  int (__fastcall **v107)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 v108; // r14
  HRESULT v109; // eax
  int v110; // edx
  unsigned int v111; // r8d
  int v112; // eax
  __int64 v113; // rax
  __int64 v114; // rbx
  int (__fastcall ***v115)(__int64, GUID *, __int64 *); // rdi
  int (__fastcall *v116)(__int64, GUID *, __int64 *); // r14
  __int64 v117; // rcx
  __int64 *v118; // rdi
  int (__fastcall **v119)(_QWORD, _QWORD, _QWORD); // r14
  __int64 v120; // r15
  HRESULT v121; // eax
  int v122; // edx
  unsigned int v123; // r8d
  int v124; // eax
  GUID *v125; // rdx
  int (__fastcall ***v126)(__int64, GUID *, __int64 *); // rdi
  int (__fastcall *v127)(__int64, GUID *, __int64 *); // r14
  __int64 v128; // rcx
  __int64 *v129; // rbx
  int (__fastcall **v130)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 v131; // r14
  HRESULT v132; // eax
  int v133; // edx
  unsigned int v134; // r8d
  int v135; // eax
  int v136; // eax
  __int64 v137; // rbx
  __int64 (__fastcall *v138)(__int64, __int64 *); // rdi
  __int64 v139; // rcx
  __int64 *v140; // rbx
  int (__fastcall **v141)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 v142; // r14
  HRESULT v143; // eax
  int v144; // edx
  unsigned int v145; // r8d
  int v146; // eax
  __int64 v147; // rcx
  int (__fastcall ***v148)(__int64, GUID *, __int64 *); // rbx
  int (__fastcall *v149)(__int64, GUID *, __int64 *); // rdi
  __int64 *v150; // rax
  __int64 v151; // rax
  int v152; // eax
  __int64 v153; // rbx
  __int64 (__fastcall *v154)(__int64, __int64 *); // rdi
  __int64 *v155; // rbx
  int (__fastcall **v156)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 v157; // r14
  HRESULT v158; // eax
  int v159; // edx
  unsigned int v160; // r8d
  int v161; // eax
  int (__fastcall ***v162)(__int64, GUID *, __int64 *); // rbx
  int (__fastcall *v163)(__int64, GUID *, __int64 *); // rdi
  __int64 v164; // rcx
  __int64 *v165; // rbx
  int (__fastcall **v166)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 v167; // r14
  HRESULT v168; // eax
  int v169; // edx
  unsigned int v170; // r8d
  int v171; // eax
  int (__fastcall ***v172)(__int64, GUID *, __int64 *); // rbx
  int (__fastcall *v173)(__int64, GUID *, __int64 *); // rdi
  __int64 v174; // rcx
  __int64 v175; // rax
  int v176; // eax
  __int64 *v177; // rbx
  int (__fastcall **v178)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 v179; // r14
  HRESULT v180; // eax
  int v181; // edx
  unsigned int v182; // r8d
  int v183; // eax
  __int64 *v184; // rbx
  int (__fastcall *v185)(__int64 *, GUID *, __int64 *); // rdi
  __int64 v186; // rcx
  __int64 v187; // rdi
  int (__fastcall *v188)(__int64, HSTRING *); // rbx
  _QWORD *v189; // rbx
  __int64 v190; // rdi
  HSTRING v191; // r14
  HRESULT v192; // eax
  int v193; // edx
  unsigned int v194; // r8d
  __int64 v195; // rcx
  __int64 v196; // rcx
  int (__fastcall ***v197)(__int64, GUID *, __int64 *); // rcx
  __int64 *v198; // rcx
  _QWORD *v199; // rcx
  IUnknown *v200; // rcx
  int (__fastcall ***v201)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v202; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v203; // [rsp+48h] [rbp-B8h] BYREF
  int (__fastcall ***v204)(__int64, GUID *, __int64 *); // [rsp+50h] [rbp-B0h] BYREF
  int (__fastcall ***v205)(_QWORD, GUID *, IUnknown **); // [rsp+58h] [rbp-A8h] BYREF
  IUnknown *pProxy; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v207; // [rsp+68h] [rbp-98h] BYREF
  __int64 v208; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v209; // [rsp+78h] [rbp-88h] BYREF
  HSTRING v210[3]; // [rsp+80h] [rbp-80h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-68h] BYREF
  HSTRING string[2]; // [rsp+B0h] [rbp-50h] BYREF
  OLECHAR sz; // [rsp+C0h] [rbp-40h] BYREF
  char v214; // [rsp+C2h] [rbp-3Eh] BYREF
  __int16 v215; // [rsp+10Ah] [rbp+Ah]

  v210[1] = Context;
  v210[2] = (HSTRING)Work;
  if ( CoInitializeEx(0, 0) >= 0 )
  {
    if ( !SetThreadToken(0, *(HANDLE *)Context) )
    {
LABEL_145:
      CoUninitialize();
      if ( Work )
        CloseThreadpoolWork(Work);
      goto LABEL_147;
    }
    v205 = 0;
    string[0] = 0;
    v5 = WindowsCreateStringReference(
           L"Windows.Internal.Security.SmartScreen.EventLogger",
           0x31u,
           &hstringHeader,
           string);
    if ( v5 >= 0 )
    {
      ActivationFactory = RoGetActivationFactory(string[0], &GUID_16ae6386_0aa2_45fc_aab2_f2ee3a0f3188, &v205);
      string[0] = 0;
      if ( ActivationFactory < 0 )
      {
LABEL_142:
        v201 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v205;
        if ( v205 )
        {
          v205 = 0;
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v201)[2])(v201);
        }
        RevertToSelf();
        goto LABEL_145;
      }
      pProxy = 0;
      if ( (**v205)(v205, &GUID_00000000_0000_0000_c000_000000000046, &pProxy) < 0
        || CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0x20u) < 0 )
      {
LABEL_140:
        v200 = pProxy;
        if ( pProxy )
        {
          pProxy = 0;
          ((void (__fastcall *)(IUnknown *))v200->lpVtbl->Release)(v200);
        }
        goto LABEL_142;
      }
      v207 = 0;
      v9 = v205;
      v10 = (int (__fastcall **)(_QWORD, _QWORD, _QWORD))*v205;
      string[0] = 0;
      v11 = WindowsCreateStringReference(L"createProcess", 0xDu, &hstringHeader, string);
      if ( v11 < 0 )
        goto LABEL_151;
      v14 = ((int (__fastcall **)(_QWORD, HSTRING, _QWORD **))v10)[6](v9, string[0], &v207);
      string[0] = 0;
      if ( v14 < 0 )
      {
LABEL_138:
        v199 = v207;
        if ( v207 )
        {
          v207 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v199 + 16LL))(v199);
        }
        goto LABEL_140;
      }
      v203 = 0;
      string[0] = 0;
      v15 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, string);
      if ( v15 < 0 )
        goto LABEL_152;
      v203 = 0;
      v209 = 0;
      v18 = RoActivateInstance(string[0], &v209);
      if ( v18 >= 0 )
      {
        if ( !memcmp_0(&GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
        {
          v203 = v209;
        }
        else
        {
          v18 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64 **))*v209)(
                  v209,
                  &GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3,
                  &v203);
          (*(void (__fastcall **)(__int64 *))(*v209 + 16))(v209);
        }
      }
      string[0] = 0;
      if ( v18 < 0 )
        goto LABEL_136;
      v204 = 0;
      string[0] = 0;
      v19 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, string);
      if ( v19 < 0 )
        goto LABEL_153;
      v22 = string[0];
      v23 = v204;
      if ( v204 )
      {
        v204 = 0;
        ((void (__fastcall *)(int (__fastcall ***)(__int64, GUID *, __int64 *)))(*v23)[2])(v23);
      }
      v24 = RoGetActivationFactory(v22, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v204);
      string[0] = 0;
      if ( v24 < 0 )
        goto LABEL_134;
      v208 = 0;
      if ( (**v204)((__int64)v204, &GUID_1d9ecbe4_3fe8_4335_8392_93d8e36865f0, &v208) < 0 )
      {
LABEL_132:
        v196 = v208;
        if ( v208 )
        {
          v208 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v196 + 16LL))(v196);
        }
LABEL_134:
        v197 = v204;
        if ( v204 )
        {
          v204 = 0;
          ((void (__fastcall *)(int (__fastcall ***)(__int64, GUID *, __int64 *)))(*v197)[2])(v197);
        }
LABEL_136:
        v198 = v203;
        if ( v203 )
        {
          v203 = 0;
          (*(void (__fastcall **)(__int64 *))(*v198 + 16))(v198);
        }
        goto LABEL_138;
      }
      v209 = (__int64 *)&v204;
      v202 = 0;
      v26 = -1;
      if ( *((_QWORD *)Context + 3) )
      {
        v27 = v204;
        v28 = *v204;
        v29 = (const WCHAR *)(Context + 2);
        if ( *((_QWORD *)Context + 4) >= 8u )
          v29 = *(const WCHAR **)v29;
        string[0] = 0;
        v30 = -1;
        do
          ++v30;
        while ( v29[v30] );
        if ( v30 > 0xFFFFFFFF )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v30, v25);
          __debugbreak();
        }
        if ( (int)v30 + 1 < (unsigned int)v30 )
        {
LABEL_154:
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v30, v25);
          __debugbreak();
        }
        v31 = WindowsCreateStringReference(v29, v30, &hstringHeader, string);
        if ( v31 < 0 )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v31, v32, v33);
          __debugbreak();
        }
        v34 = v28[10]((__int64)v27, (GUID *)string[0], &v202);
        string[0] = 0;
      }
      else
      {
        v34 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v208 + 48LL))(v208, &v202);
      }
      if ( v34 < 0 )
        goto LABEL_130;
      v35 = v203;
      v36 = (int (__fastcall **)(_QWORD, _QWORD, _QWORD))*v203;
      v37 = v202;
      string[0] = 0;
      v38 = WindowsCreateStringReference(L"path", 4u, &hstringHeader, string);
      if ( v38 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v38, v39, v40);
        __debugbreak();
      }
      v41 = ((int (__fastcall **)(__int64 *, HSTRING, __int64))v36)[7](v35, string[0], v37);
      string[0] = 0;
      if ( v41 < 0 )
        goto LABEL_130;
      v44 = v202;
      if ( *((_QWORD *)Context + 7) )
      {
        v45 = v204;
        v46 = *v204;
        if ( v202 )
        {
          v202 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
        }
        v47 = (const WCHAR *)(Context + 10);
        if ( *((_QWORD *)Context + 8) >= 8u )
          v47 = *(const WCHAR **)v47;
        string[0] = 0;
        do
          ++v26;
        while ( v47[v26] );
        if ( v26 > 0xFFFFFFFF )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v42, v43);
          __debugbreak();
        }
        if ( (int)v26 + 1 < (unsigned int)v26 )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v42, v43);
          __debugbreak();
        }
        v48 = WindowsCreateStringReference(v47, v26, &hstringHeader, string);
        if ( v48 < 0 )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v48, v49, v50);
          __debugbreak();
        }
        v51 = v46[10]((__int64)v45, (GUID *)string[0], &v202);
        string[0] = 0;
      }
      else
      {
        v52 = v208;
        v53 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v208 + 48LL);
        if ( v202 )
        {
          v202 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
        }
        v51 = v53(v52, &v202);
      }
      if ( v51 < 0 )
        goto LABEL_130;
      v54 = v203;
      v55 = (int (__fastcall **)(_QWORD, _QWORD, _QWORD))*v203;
      v56 = v202;
      string[0] = 0;
      v57 = WindowsCreateStringReference(L"parentPath", 0xAu, &hstringHeader, string);
      if ( v57 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v57, v58, v59);
        __debugbreak();
      }
      v60 = ((int (__fastcall **)(__int64 *, HSTRING, __int64))v55)[7](v54, string[0], v56);
      string[0] = 0;
      if ( v60 < 0 )
        goto LABEL_130;
      v62 = v204;
      v63 = (*v204)[9];
      v64 = v202;
      if ( v202 )
      {
        v202 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
      }
      if ( v63((__int64)v62, v61, &v202) < 0 )
        goto LABEL_130;
      v65 = v203;
      v66 = (int (__fastcall **)(_QWORD, _QWORD, _QWORD))*v203;
      v67 = v202;
      string[0] = 0;
      v68 = WindowsCreateStringReference(L"statusCode", 0xAu, &hstringHeader, string);
      if ( v68 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v68, v69, v70);
        __debugbreak();
      }
      v71 = ((int (__fastcall **)(__int64 *, HSTRING, __int64))v66)[7](v65, string[0], v67);
      string[0] = 0;
      if ( v71 < 0 )
        goto LABEL_130;
      v72 = v204;
      v73 = (*v204)[9];
      v74 = v202;
      if ( v202 )
      {
        v202 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      }
      if ( v73((__int64)v72, (GUID *)*((unsigned int *)Context + 19), &v202) < 0 )
        goto LABEL_130;
      v75 = v203;
      v76 = (int (__fastcall **)(_QWORD, _QWORD, _QWORD))*v203;
      v77 = v202;
      string[0] = 0;
      v78 = WindowsCreateStringReference(L"bucket", 6u, &hstringHeader, string);
      if ( v78 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v78, v79, v80);
        __debugbreak();
      }
      v81 = ((int (__fastcall **)(__int64 *, HSTRING, __int64))v76)[7](v75, string[0], v77);
      string[0] = 0;
      if ( v81 < 0 )
        goto LABEL_130;
      v83 = v204;
      v84 = (*v204)[9];
      v85 = v202;
      if ( v202 )
      {
        v202 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
      }
      v86 = *((_QWORD *)Context + 10);
      if ( v86 < 0 )
        v82 = *((_QWORD *)Context + 10) & 1LL | ((unsigned __int64)v86 >> 1);
      if ( v84((__int64)v83, (GUID *)v82, &v202) < 0 )
        goto LABEL_130;
      v87 = v203;
      v88 = (int (__fastcall **)(_QWORD, _QWORD, _QWORD))*v203;
      v89 = v202;
      string[0] = 0;
      v90 = WindowsCreateStringReference(L"usn", 3u, &hstringHeader, string);
      if ( v90 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v90, v91, v92);
        __debugbreak();
      }
      v93 = ((int (__fastcall **)(__int64 *, HSTRING, __int64))v88)[7](v87, string[0], v89);
      string[0] = 0;
      if ( v93 < 0 )
        goto LABEL_130;
      v94 = *((unsigned int *)Context + 38);
      if ( (_DWORD)v94 )
      {
        v95 = lambda_698083c9b54468aeccfdadd8b0896794_::operator()_unsigned_long_unsigned_char___Microsoft::WRL::Details::ComPtrRef_Microsoft::WRL::ComPtr_Windows::Data::Json::IJsonValue_____(
                &v209,
                v94,
                Context + 22,
                &v202);
      }
      else
      {
        v96 = v208;
        v97 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v208 + 48LL);
        v98 = v202;
        if ( v202 )
        {
          v202 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
        }
        v95 = v97(v96, &v202);
      }
      if ( v95 < 0 )
        goto LABEL_130;
      v99 = v203;
      v100 = (int (__fastcall **)(_QWORD, _QWORD, _QWORD))*v203;
      v101 = v202;
      string[0] = 0;
      v102 = WindowsCreateStringReference(L"fileHash", 8u, &hstringHeader, string);
      if ( v102 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v102, v103, v104);
        __debugbreak();
      }
      v105 = ((int (__fastcall **)(__int64 *, HSTRING, __int64))v100)[7](v99, string[0], v101);
      string[0] = 0;
      if ( v105 < 0
        || (int)lambda_698083c9b54468aeccfdadd8b0896794_::operator()_unsigned_long_unsigned_char___Microsoft::WRL::Details::ComPtrRef_Microsoft::WRL::ComPtr_Windows::Data::Json::IJsonValue_____(
                  &v209,
                  *((_DWORD *)Context + 42) - (unsigned int)*((_QWORD *)Context + 20),
                  *((_QWORD *)Context + 20),
                  &v202) < 0 )
      {
        goto LABEL_130;
      }
      v106 = v203;
      v107 = (int (__fastcall **)(_QWORD, _QWORD, _QWORD))*v203;
      v108 = v202;
      string[0] = 0;
      v109 = WindowsCreateStringReference(L"ntfsId", 6u, &hstringHeader, string);
      if ( v109 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v109, v110, v111);
        __debugbreak();
      }
      v112 = ((int (__fastcall **)(__int64 *, HSTRING, __int64))v107)[7](v106, string[0], v108);
      string[0] = 0;
      if ( v112 < 0 )
        goto LABEL_130;
      v113 = *((_QWORD *)Context + 24);
      v114 = *((_QWORD *)Context + 23);
      if ( v114 == v113 )
      {
        v137 = v208;
        v138 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v208 + 48LL);
        v139 = v202;
        if ( v202 )
        {
          v202 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v139 + 16LL))(v139);
        }
        v136 = v138(v137, &v202);
      }
      else
      {
        if ( (unsigned __int64)(v113 - v114) >= 0x34 )
        {
          v115 = v204;
          v116 = (*v204)[9];
          v117 = v202;
          if ( v202 )
          {
            v202 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v117 + 16LL))(v117);
          }
          if ( v116((__int64)v115, (GUID *)*(unsigned int *)(v114 + 48), &v202) < 0 )
            goto LABEL_130;
          v118 = v203;
          v119 = (int (__fastcall **)(_QWORD, _QWORD, _QWORD))*v203;
          v120 = v202;
          string[0] = 0;
          v121 = WindowsCreateStringReference(L"safeOpenResults", 0xFu, &hstringHeader, string);
          if ( v121 < 0 )
          {
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v121, v122, v123);
            __debugbreak();
          }
          v124 = ((int (__fastcall **)(__int64 *, HSTRING, __int64))v119)[7](v118, string[0], v120);
          string[0] = 0;
          if ( v124 < 0 )
            goto LABEL_130;
          v126 = v204;
          v127 = (*v204)[8];
          v128 = v202;
          if ( v202 )
          {
            v202 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v128 + 16LL))(v128);
          }
          LOBYTE(v125) = *(_DWORD *)(v114 + 4) == 1;
          if ( v127((__int64)v126, v125, &v202) < 0 )
            goto LABEL_130;
          v129 = v203;
          v130 = (int (__fastcall **)(_QWORD, _QWORD, _QWORD))*v203;
          v131 = v202;
          string[0] = 0;
          v132 = WindowsCreateStringReference(L"markOfTheWeb", 0xCu, &hstringHeader, string);
          if ( v132 < 0 )
          {
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v132, v133, v134);
            __debugbreak();
          }
          v135 = ((int (__fastcall **)(__int64 *, HSTRING, __int64))v130)[7](v129, string[0], v131);
          string[0] = 0;
          if ( v135 < 0 )
            goto LABEL_130;
        }
        v136 = lambda_698083c9b54468aeccfdadd8b0896794_::operator()_unsigned_long_unsigned_char___Microsoft::WRL::Details::ComPtrRef_Microsoft::WRL::ComPtr_Windows::Data::Json::IJsonValue_____(
                 &v209,
                 *((_DWORD *)Context + 48) - (unsigned int)*((_QWORD *)Context + 23),
                 *((_QWORD *)Context + 23),
                 &v202);
      }
      if ( v136 < 0 )
        goto LABEL_130;
      v140 = v203;
      v141 = (int (__fastcall **)(_QWORD, _QWORD, _QWORD))*v203;
      v142 = v202;
      string[0] = 0;
      v143 = WindowsCreateStringReference(L"originClaim", 0xBu, &hstringHeader, string);
      if ( v143 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v143, v144, v145);
        __debugbreak();
      }
      v146 = ((int (__fastcall **)(__int64 *, HSTRING, __int64))v141)[7](v140, string[0], v142);
      string[0] = 0;
      if ( v146 < 0 )
        goto LABEL_130;
      v147 = v202;
      if ( *((_QWORD *)Context + 28) )
      {
        v148 = v204;
        v149 = (*v204)[10];
        if ( v202 )
        {
          v202 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v147 + 16LL))(v147);
        }
        v150 = (__int64 *)(Context + 52);
        if ( *((_QWORD *)Context + 29) >= 8u )
          v150 = (__int64 *)*v150;
        v209 = v150;
        v151 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v209);
        v152 = v149((__int64)v148, *(GUID **)(v151 + 24), &v202);
        string[0] = 0;
      }
      else
      {
        v153 = v208;
        v154 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v208 + 48LL);
        if ( v202 )
        {
          v202 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v147 + 16LL))(v147);
        }
        v152 = v154(v153, &v202);
      }
      if ( v152 < 0 )
        goto LABEL_130;
      v155 = v203;
      v156 = (int (__fastcall **)(_QWORD, _QWORD, _QWORD))*v203;
      v157 = v202;
      string[0] = 0;
      v158 = WindowsCreateStringReference(L"fqbn", 4u, &hstringHeader, string);
      if ( v158 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v158, v159, v160);
        __debugbreak();
      }
      v161 = ((int (__fastcall **)(__int64 *, HSTRING, __int64))v156)[7](v155, string[0], v157);
      string[0] = 0;
      if ( v161 < 0 )
        goto LABEL_130;
      v162 = v204;
      v163 = (*v204)[9];
      v164 = v202;
      if ( v202 )
      {
        v202 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v164 + 16LL))(v164);
      }
      if ( v163((__int64)v162, (GUID *)*((unsigned int *)Context + 60), &v202) < 0 )
        goto LABEL_130;
      v165 = v203;
      v166 = (int (__fastcall **)(_QWORD, _QWORD, _QWORD))*v203;
      v167 = v202;
      string[0] = 0;
      v168 = WindowsCreateStringReference(L"createProcFlags", 0xFu, &hstringHeader, string);
      if ( v168 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v168, v169, v170);
        __debugbreak();
      }
      v171 = ((int (__fastcall **)(__int64 *, HSTRING, __int64))v166)[7](v165, string[0], v167);
      string[0] = 0;
      if ( v171 < 0 )
        goto LABEL_130;
      StringFromGUID2((const GUID *const)(Context + 61), &sz, 39);
      v215 = 0;
      v172 = v204;
      v173 = (*v204)[10];
      v174 = v202;
      if ( v202 )
      {
        v202 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v174 + 16LL))(v174);
      }
      v209 = (__int64 *)&v214;
      v175 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v209);
      v176 = v173((__int64)v172, *(GUID **)(v175 + 24), &v202);
      string[0] = 0;
      if ( v176 < 0 )
        goto LABEL_130;
      v177 = v203;
      v178 = (int (__fastcall **)(_QWORD, _QWORD, _QWORD))*v203;
      v179 = v202;
      string[0] = 0;
      v180 = WindowsCreateStringReference(L"correlationId", 0xDu, &hstringHeader, string);
      if ( v180 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v180, v181, v182);
        JUMPOUT(0x18000786ALL);
      }
      v183 = ((int (__fastcall **)(__int64 *, HSTRING, __int64))v178)[7](v177, string[0], v179);
      string[0] = 0;
      if ( v183 < 0 )
        goto LABEL_130;
      v184 = v203;
      v185 = *(int (__fastcall **)(__int64 *, GUID *, __int64 *))*v203;
      v186 = v202;
      if ( v202 )
      {
        v202 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v186 + 16LL))(v186);
      }
      if ( v185(v184, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v202) < 0 )
      {
LABEL_130:
        v195 = v202;
        if ( v202 )
        {
          v202 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v195 + 16LL))(v195);
        }
        goto LABEL_132;
      }
      v210[0] = 0;
      v187 = v202;
      v188 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v202 + 56LL);
      WindowsDeleteString(0);
      v210[0] = 0;
      if ( v188(v187, v210) < 0 )
      {
LABEL_129:
        WindowsDeleteString(v210[0]);
        v210[0] = 0;
        goto LABEL_130;
      }
      v189 = v207;
      v190 = *v207;
      v191 = v210[0];
      string[0] = 0;
      v192 = WindowsCreateStringReference(L"onCreateProcess", 0xFu, &hstringHeader, string);
      if ( v192 >= 0 )
      {
        (*(void (__fastcall **)(_QWORD *, HSTRING, HSTRING, _QWORD))(v190 + 48))(v189, string[0], v191, 0);
        string[0] = 0;
        goto LABEL_129;
      }
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v192, v193, v194);
    }
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
LABEL_151:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v11, v12, v13);
LABEL_152:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v15, v16, v17);
LABEL_153:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v19, v20, v21);
    goto LABEL_154;
  }
  if ( Work )
    CloseThreadpoolWork(Work);
  if ( Context )
  {
LABEL_147:
    ON_CREATE_PROC_DATA::~ON_CREATE_PROC_DATA((ON_CREATE_PROC_DATA *)Context);
    operator delete(Context);
  }
}

```

## disassembly

```asm
0x180006860  push    rbp
0x180006862  push    rbx
0x180006863  push    rsi
0x180006864  push    rdi
0x180006865  push    r12
0x180006867  push    r13
0x180006869  push    r14
0x18000686b  push    r15
0x18000686d  lea     rbp, [rsp-28h]
0x180006872  sub     rsp, 128h
0x180006879  mov     rax, cs:__security_cookie
0x180006880  xor     rax, rsp
0x180006883  mov     [rbp+60h+var_48], rax
0x180006887  mov     rsi, r8
0x18000688a  mov     r12, rdx
0x18000688d  mov     [rbp+60h+var_D8], rdx
0x180006891  mov     [rbp+60h+var_D0], r8
0x180006895  xor     edx, edx; dwCoInit
0x180006897  xor     ecx, ecx; pvReserved
0x180006899  call    cs:__imp_CoInitializeEx
0x18000689f  xor     r13d, r13d
0x1800068a2  test    eax, eax
0x1800068a4  jns     short loc_1800068C3
0x1800068a6  test    rsi, rsi
0x1800068a9  jz      short loc_1800068B5
0x1800068ab  mov     rcx, rsi; pwk
0x1800068ae  call    cs:__imp_CloseThreadpoolWork
0x1800068b4  nop
0x1800068b5  test    r12, r12
0x1800068b8  jz      loc_18000777F
0x1800068be  jmp     loc_18000776E
0x1800068c3  mov     rdx, [r12]; Token
0x1800068c7  xor     ecx, ecx; Thread
0x1800068c9  call    cs:__imp_SetThreadToken
0x1800068cf  test    eax, eax
0x1800068d1  jz      loc_180007758
0x1800068d7  mov     [rsp+160h+var_108], r13
0x1800068dc  mov     rcx, [rsp+160h+var_108]
0x1800068e1  test    rcx, rcx
0x1800068e4  jz      short loc_1800068F7
0x1800068e6  mov     [rsp+160h+var_108], r13
0x1800068eb  mov     rax, [rcx]
0x1800068ee  mov     rax, [rax+10h]
0x1800068f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068f7  mov     [rbp+60h+string], r13
0x1800068fb  lea     r9, [rbp+60h+string]; string
0x1800068ff  lea     r8, [rbp+60h+hstringHeader]; hstringHeader
0x180006903  mov     edx, 31h ; '1'; length
0x180006908  lea     rcx, ?RuntimeClass_Windows_Internal_Security_SmartScreen_EventLogger@@3QBGB; "Windows.Internal.Security.SmartScreen.E"...
0x18000690f  call    cs:__imp_WindowsCreateStringReference
0x180006915  test    eax, eax
0x180006917  js      loc_1800077A7
0x18000691d  lea     r8, [rsp+160h+var_108]
0x180006922  lea     rdx, _GUID_16ae6386_0aa2_45fc_aab2_f2ee3a0f3188
0x180006929  mov     rcx, [rbp+60h+string]
0x18000692d  call    cs:__imp_RoGetActivationFactory
0x180006933  nop
0x180006934  mov     [rbp+60h+string], r13
0x180006938  test    eax, eax
0x18000693a  js      loc_180007735
0x180006940  mov     [rsp+160h+pProxy], r13
0x180006945  mov     rbx, [rsp+160h+var_108]
0x18000694a  mov     rax, [rbx]
0x18000694d  mov     rdi, [rax]
0x180006950  mov     rcx, [rsp+160h+pProxy]
0x180006955  test    rcx, rcx
0x180006958  jz      short loc_18000696B
0x18000695a  mov     [rsp+160h+pProxy], r13
0x18000695f  mov     rdx, [rcx]
0x180006962  mov     rax, [rdx+10h]
0x180006966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000696b  lea     r8, [rsp+160h+pProxy]
0x180006970  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180006977  mov     rcx, rbx
0x18000697a  mov     rax, rdi
0x18000697d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006982  test    eax, eax
0x180006984  js      loc_180007719
0x18000698a  mov     [rsp+160h+dwCapabilities], 20h ; ' '; dwCapabilities
0x180006992  mov     [rsp+160h+pAuthInfo], r13; pAuthInfo
0x180006997  mov     [rsp+160h+dwImpLevel], 3; dwImpLevel
0x18000699f  mov     [rsp+160h+dwAuthnLevel], r13d; dwAuthnLevel
0x1800069a4  xor     r9d, r9d; pServerPrincName
0x1800069a7  mov     r15d, 0FFFFFFFFh
0x1800069ad  mov     r8d, r15d; dwAuthzSvc
0x1800069b0  mov     edx, r15d; dwAuthnSvc
0x1800069b3  mov     rcx, [rsp+160h+pProxy]; pProxy
0x1800069b8  call    cs:__imp_CoSetProxyBlanket
0x1800069be  test    eax, eax
0x1800069c0  js      loc_180007719
0x1800069c6  mov     [rsp+160h+var_F8], r13
0x1800069cb  mov     rbx, [rsp+160h+var_108]
0x1800069d0  mov     rdi, [rbx]
0x1800069d3  mov     rcx, [rsp+160h+var_F8]
0x1800069d8  test    rcx, rcx
0x1800069db  jz      short loc_1800069EE
0x1800069dd  mov     [rsp+160h+var_F8], r13
0x1800069e2  mov     rax, [rcx]
0x1800069e5  mov     rax, [rax+10h]
0x1800069e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069ee  mov     [rbp+60h+string], r13
0x1800069f2  lea     r9, [rbp+60h+string]; string
0x1800069f6  lea     r8, [rbp+60h+hstringHeader]; hstringHeader
0x1800069fa  mov     edx, 0Dh; length
0x1800069ff  lea     rcx, sourceString; "createProcess"
0x180006a06  call    cs:__imp_WindowsCreateStringReference
0x180006a0c  test    eax, eax
0x180006a0e  js      loc_1800077AF
0x180006a14  lea     r8, [rsp+160h+var_F8]
0x180006a19  mov     rdx, [rbp+60h+string]
0x180006a1d  mov     rcx, rbx
0x180006a20  mov     rax, [rdi+30h]
0x180006a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a29  nop
0x180006a2a  mov     [rbp+60h+string], r13
0x180006a2e  test    eax, eax
0x180006a30  js      loc_1800076FD
0x180006a36  mov     [rsp+160h+var_118], r13
0x180006a3b  mov     [rbp+60h+string], r13
0x180006a3f  lea     r9, [rbp+60h+string]; string
0x180006a43  lea     r8, [rbp+60h+hstringHeader]; hstringHeader
0x180006a47  mov     edx, 1Ch; length
0x180006a4c  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180006a53  call    cs:__imp_WindowsCreateStringReference
0x180006a59  test    eax, eax
0x180006a5b  js      loc_1800077B7
0x180006a61  mov     rbx, [rbp+60h+string]
0x180006a65  mov     rcx, [rsp+160h+var_118]
0x180006a6a  test    rcx, rcx
0x180006a6d  jz      short loc_180006A80
0x180006a6f  mov     [rsp+160h+var_118], r13
0x180006a74  mov     rax, [rcx]
0x180006a77  mov     rax, [rax+10h]
0x180006a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a80  mov     [rsp+160h+var_118], r13
0x180006a85  mov     [rsp+160h+var_E8], r13
0x180006a8a  lea     rdx, [rsp+160h+var_E8]
0x180006a8f  mov     rcx, rbx
0x180006a92  call    cs:__imp_RoActivateInstance
0x180006a98  mov     ebx, eax
0x180006a9a  test    eax, eax
0x180006a9c  js      short loc_180006AF2
0x180006a9e  mov     r8d, 10h; Size
0x180006aa4  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180006aab  lea     rcx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3; Buf1
0x180006ab2  call    memcmp_0
0x180006ab7  mov     rcx, [rsp+160h+var_E8]
0x180006abc  test    eax, eax
0x180006abe  jnz     short loc_180006AC7
0x180006ac0  mov     [rsp+160h+var_118], rcx
0x180006ac5  jmp     short loc_180006AF2
0x180006ac7  mov     rax, [rcx]
0x180006aca  lea     r8, [rsp+160h+var_118]
0x180006acf  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x180006ad6  mov     rax, [rax]
0x180006ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ade  mov     ebx, eax
0x180006ae0  mov     rcx, [rsp+160h+var_E8]
0x180006ae5  mov     rax, [rcx]
0x180006ae8  mov     rax, [rax+10h]
0x180006aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006af1  nop
0x180006af2  mov     [rbp+60h+string], r13
0x180006af6  test    ebx, ebx
0x180006af8  js      loc_1800076E1
0x180006afe  mov     [rsp+160h+var_110], r13
0x180006b03  mov     [rbp+60h+string], r13
0x180006b07  lea     r9, [rbp+60h+string]; string
0x180006b0b  lea     r8, [rbp+60h+hstringHeader]; hstringHeader
0x180006b0f  mov     edx, 1Bh; length
0x180006b14  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180006b1b  call    cs:__imp_WindowsCreateStringReference
0x180006b21  test    eax, eax
0x180006b23  js      loc_1800077BF
0x180006b29  mov     rbx, [rbp+60h+string]
0x180006b2d  mov     rcx, [rsp+160h+var_110]
0x180006b32  test    rcx, rcx
0x180006b35  jz      short loc_180006B48
0x180006b37  mov     [rsp+160h+var_110], r13
0x180006b3c  mov     rax, [rcx]
0x180006b3f  mov     rax, [rax+10h]
0x180006b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b48  lea     r8, [rsp+160h+var_110]
0x180006b4d  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x180006b54  mov     rcx, rbx
0x180006b57  call    cs:__imp_RoGetActivationFactory
0x180006b5d  nop
0x180006b5e  mov     [rbp+60h+string], r13
0x180006b62  test    eax, eax
0x180006b64  js      loc_1800076C5
0x180006b6a  mov     [rsp+160h+var_F0], r13
0x180006b6f  mov     rbx, [rsp+160h+var_110]
0x180006b74  mov     rax, [rbx]
0x180006b77  mov     rdi, [rax]
0x180006b7a  mov     rcx, [rsp+160h+var_F0]
0x180006b7f  test    rcx, rcx
0x180006b82  jz      short loc_180006B95
0x180006b84  mov     [rsp+160h+var_F0], r13
0x180006b89  mov     rdx, [rcx]
0x180006b8c  mov     rax, [rdx+10h]
0x180006b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b95  lea     r8, [rsp+160h+var_F0]
0x180006b9a  lea     rdx, _GUID_1d9ecbe4_3fe8_4335_8392_93d8e36865f0
0x180006ba1  mov     rcx, rbx
0x180006ba4  mov     rax, rdi
0x180006ba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bac  test    eax, eax
0x180006bae  js      loc_1800076A9
0x180006bb4  lea     rax, [rsp+160h+var_110]
0x180006bb9  mov     [rsp+160h+var_E8], rax
0x180006bbe  mov     [rsp+160h+var_120], r13
0x180006bc3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006bc7  mov     rcx, [rsp+160h+var_120]
0x180006bcc  cmp     [r12+18h], r13
0x180006bd1  jz      loc_180006C5B
0x180006bd7  mov     rdi, [rsp+160h+var_110]
0x180006bdc  mov     r14, [rdi]
0x180006bdf  test    rcx, rcx
0x180006be2  jz      short loc_180006BF5
0x180006be4  mov     [rsp+160h+var_120], r13
0x180006be9  mov     rax, [rcx]
0x180006bec  mov     rax, [rax+10h]
0x180006bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bf5  lea     rcx, [r12+8]
0x180006bfa  cmp     qword ptr [rcx+18h], 8
0x180006bff  jb      short loc_180006C04
0x180006c01  mov     rcx, [rcx]; sourceString
0x180006c04  mov     [rbp+60h+string], r13
0x180006c08  mov     rdx, rbx
0x180006c0b  inc     rdx; int
0x180006c0e  cmp     [rcx+rdx*2], r13w
0x180006c13  jnz     short loc_180006C0B
0x180006c15  cmp     rdx, r15
0x180006c18  ja      loc_1800077DA
0x180006c1e  lea     eax, [rdx+1]
0x180006c21  cmp     eax, edx
0x180006c23  jb      loc_1800077C7
0x180006c29  lea     r9, [rbp+60h+string]; string
0x180006c2d  lea     r8, [rbp+60h+hstringHeader]; hstringHeader
0x180006c31  call    cs:__imp_WindowsCreateStringReference
0x180006c37  test    eax, eax
0x180006c39  js      loc_1800077D2
0x180006c3f  lea     r8, [rsp+160h+var_120]
0x180006c44  mov     rdx, [rbp+60h+string]
0x180006c48  mov     rcx, rdi
0x180006c4b  mov     rax, [r14+50h]
0x180006c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c54  nop
0x180006c55  mov     [rbp+60h+string], r13
0x180006c59  jmp     short loc_180006C8D
0x180006c5b  mov     rdi, [rsp+160h+var_F0]
0x180006c60  mov     rax, [rdi]
0x180006c63  mov     r14, [rax+30h]
0x180006c67  test    rcx, rcx
0x180006c6a  jz      short loc_180006C7D
0x180006c6c  mov     [rsp+160h+var_120], r13
0x180006c71  mov     rdx, [rcx]
0x180006c74  mov     rax, [rdx+10h]
0x180006c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c7d  lea     rdx, [rsp+160h+var_120]
0x180006c82  mov     rcx, rdi
0x180006c85  mov     rax, r14
0x180006c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c8d  test    eax, eax
0x180006c8f  js      loc_18000768D
0x180006c95  mov     rdi, [rsp+160h+var_118]
0x180006c9a  mov     r14, [rdi]
0x180006c9d  mov     r15, [rsp+160h+var_120]
0x180006ca2  mov     [rbp+60h+string], r13
0x180006ca6  lea     r9, [rbp+60h+string]; string
0x180006caa  lea     r8, [rbp+60h+hstringHeader]; hstringHeader
0x180006cae  mov     edx, 4; length
0x180006cb3  lea     rcx, aPath; "path"
0x180006cba  call    cs:__imp_WindowsCreateStringReference
0x180006cc0  test    eax, eax
0x180006cc2  js      loc_1800077E5
0x180006cc8  mov     r8, r15
0x180006ccb  mov     rdx, [rbp+60h+string]
0x180006ccf  mov     rcx, rdi
0x180006cd2  mov     rax, [r14+38h]
0x180006cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cdb  nop
0x180006cdc  mov     [rbp+60h+string], r13
0x180006ce0  test    eax, eax
0x180006ce2  js      loc_18000768D
0x180006ce8  mov     rcx, [rsp+160h+var_120]
0x180006ced  cmp     [r12+38h], r13
0x180006cf2  jz      loc_180006D80
0x180006cf8  mov     rdi, [rsp+160h+var_110]
0x180006cfd  mov     r14, [rdi]
0x180006d00  test    rcx, rcx
0x180006d03  jz      short loc_180006D16
0x180006d05  mov     [rsp+160h+var_120], r13
0x180006d0a  mov     rax, [rcx]
0x180006d0d  mov     rax, [rax+10h]
0x180006d11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d16  lea     rcx, [r12+28h]
0x180006d1b  cmp     qword ptr [rcx+18h], 8
0x180006d20  jb      short loc_180006D25
0x180006d22  mov     rcx, [rcx]; sourceString
  ... truncated ...
```
