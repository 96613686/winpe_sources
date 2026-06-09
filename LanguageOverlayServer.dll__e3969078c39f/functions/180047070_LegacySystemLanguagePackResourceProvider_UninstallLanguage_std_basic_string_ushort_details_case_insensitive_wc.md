# LegacySystemLanguagePackResourceProvider::UninstallLanguage(std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> const &)

- ea: `0x180047070`
- end: `0x180047d37`
- name: `?UninstallLanguage@LegacySystemLanguagePackResourceProvider@@UEBAJAEBV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@Z`
- size: `3271`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180003a00`
- `0x180009084`
- `0x180014418`
- `0x180014ca0`
- `0x180014ed0`
- `0x180015a00`
- `0x180016f74`
- `0x1800263ac`
- `0x1800443f0`
- `0x180046668`
- `0x180047070`
- `0x180060df4`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800478e5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800478e5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180047104`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180047104`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800475e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047623`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047769`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004777f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004795e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047974`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047aa3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047ab9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047b9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047bb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047cd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047cec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800475e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047623`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047769`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004777f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004795e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047974`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047aa3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047ab9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047b9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047bb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047cd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047cec`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180047197`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180047197`

## string_xrefs

- `0x1800470aa`: `UninstallSystemLanguagePackActivity`
- `0x18004711b`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x1800471ae`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x18004723a`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x1800472c2`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x1800473da`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x1800474bb`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x180047602`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x18004774a`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x180047923`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x180047a68`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x180047215`: `Language Overlay Service`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall LegacySystemLanguagePackResourceProvider::UninstallLanguage(__int64 a1, const unsigned __int16 *a2)
{
  const unsigned __int16 *v3; // rdi
  HRESULT Instance; // eax
  unsigned int v5; // edi
  IUnknown *v6; // rcx
  HRESULT v7; // eax
  IUnknown *v8; // rcx
  int v9; // eax
  IUnknown *v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  IUnknown *v13; // rcx
  const char *v14; // r9
  __int64 result; // rax
  _QWORD *v16; // rcx
  __int64 v17; // rdi
  unsigned int (__fastcall *v18)(__int64, __int64, _QWORD **, int *, int *); // rsi
  int v19; // eax
  int v20; // edi
  __int64 v21; // rcx
  _QWORD *v22; // rcx
  __int64 v23; // rcx
  IUnknown *v24; // rcx
  int v25; // eax
  __int64 *v26; // rcx
  __int64 v27; // rcx
  _QWORD *v28; // rcx
  __int64 v29; // rcx
  IUnknown *v30; // rcx
  __int64 v31; // rax
  void *v32; // rcx
  void *v33; // rcx
  __int64 *v34; // rcx
  __int64 v35; // rcx
  _QWORD *v36; // rcx
  __int64 v37; // rcx
  IUnknown *v38; // rcx
  unsigned __int16 *v39; // rax
  int v40; // r8d
  int v41; // ecx
  __int64 v42; // rax
  int v43; // eax
  __int64 v44; // rdx
  void *v45; // rcx
  __int64 *v46; // rcx
  __int64 v47; // rcx
  _QWORD *v48; // rcx
  __int64 v49; // rcx
  IUnknown *v50; // rcx
  _QWORD *v51; // rax
  __int64 v52; // rcx
  const unsigned __int16 *v53; // rdx
  char **v54; // rcx
  int v55; // eax
  unsigned int v56; // ebx
  void *v57; // rcx
  __int64 *v58; // rcx
  __int64 v59; // rcx
  _QWORD *v60; // rcx
  __int64 v61; // rcx
  IUnknown *v62; // rcx
  int v63; // eax
  void *v64; // rcx
  __int64 *v65; // rcx
  __int64 v66; // rcx
  _QWORD *v67; // rcx
  __int64 v68; // rcx
  IUnknown *v69; // rcx
  void *v70; // rcx
  __int64 *v71; // rcx
  __int64 v72; // rcx
  _QWORD *v73; // rcx
  __int64 v74; // rcx
  IUnknown *v75; // rcx
  void *v76; // rcx
  __int64 *v77; // rcx
  __int64 v78; // rcx
  int ppv; // [rsp+20h] [rbp-228h]
  int ppva; // [rsp+20h] [rbp-228h]
  int *ppvb; // [rsp+20h] [rbp-228h]
  _QWORD v82[2]; // [rsp+40h] [rbp-208h] BYREF
  IUnknown *pProxy; // [rsp+50h] [rbp-1F8h] BYREF
  _QWORD *v84; // [rsp+58h] [rbp-1F0h] BYREF
  int v85[2]; // [rsp+60h] [rbp-1E8h] BYREF
  __int64 v86; // [rsp+68h] [rbp-1E0h] BYREF
  __int64 *v87; // [rsp+70h] [rbp-1D8h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-1D0h] BYREF
  LPVOID v89; // [rsp+80h] [rbp-1C8h] BYREF
  int v90; // [rsp+88h] [rbp-1C0h] BYREF
  int v91; // [rsp+8Ch] [rbp-1BCh] BYREF
  __int128 v92; // [rsp+90h] [rbp-1B8h] BYREF
  __int64 v93; // [rsp+A0h] [rbp-1A8h]
  char *v94[2]; // [rsp+A8h] [rbp-1A0h] BYREF
  __int64 v95; // [rsp+B8h] [rbp-190h]
  unsigned __int64 v96; // [rsp+C0h] [rbp-188h]
  _QWORD v97[42]; // [rsp+D0h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  if ( *((_QWORD *)a2 + 3) <= 7u )
    v3 = a2;
  else
    v3 = *(const unsigned __int16 **)a2;
  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(
    v97,
    "UninstallSystemLanguagePackActivity");
  v97[0] = &LanguageOverlayTraceProvider::UninstallSystemLanguagePackActivity::`vftable';
  try
  {
    LanguageOverlayTraceProvider::UninstallSystemLanguagePackActivity::StartActivity(
      (LanguageOverlayTraceProvider::UninstallSystemLanguagePackActivity *)v97,
      v3);
    pProxy = 0;
    Instance = CoCreateInstance(
                 &GUID_752073a1_23f2_4396_85f0_8fdb879ed0ed,
                 0,
                 0x15u,
                 &GUID_9c7e3cf3_4c97_4d36_bdeb_e3093c228c22,
                 (LPVOID *)&pProxy);
    v5 = Instance;
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16F,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
        (const char *)(unsigned int)Instance,
        ppv);
      v6 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v6->lpVtbl->Release)(v6);
      }
LABEL_22:
      v97[0] = &LanguageOverlayTraceProvider::UninstallSystemLanguagePackActivity::`vftable';
      wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v97);
      wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v97);
      return v5;
    }
    v7 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 3u, 3u, 0, 0);
    v5 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x178,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
        (const char *)(unsigned int)v7,
        ppva);
      v8 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v8->lpVtbl->Release)(v8);
      }
      goto LABEL_22;
    }
    ppvb = 0;
    v9 = ((__int64 (__fastcall *)(IUnknown *, __int64, const OLECHAR *))pProxy->lpVtbl[1].QueryInterface)(
           pProxy,
           48,
           L"Language Overlay Service");
    v5 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17B,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
        (const char *)(unsigned int)v9,
        0);
      v10 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v10->lpVtbl->Release)(v10);
      }
      goto LABEL_22;
    }
    v86 = 0;
    v11 = ((__int64 (__fastcall *)(IUnknown *, __int64, __int64 *))pProxy->lpVtbl[2].AddRef)(pProxy, 16, &v86);
    v5 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17E,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
        (const char *)(unsigned int)v11,
        0);
      v12 = v86;
      if ( v86 )
      {
        v86 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
      v13 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v13->lpVtbl->Release)(v13);
      }
      goto LABEL_22;
    }
    v16 = 0;
    v84 = 0;
    v91 = 0;
    while ( 1 )
    {
      v17 = v86;
      v18 = *(unsigned int (__fastcall **)(__int64, __int64, _QWORD **, int *, int *))(*(_QWORD *)v86 + 24LL);
      if ( v16 )
      {
        v84 = 0;
        (*(void (__fastcall **)(_QWORD *, _QWORD))(*v16 + 16LL))(v16, *v16);
      }
      if ( v18(v17, 1, &v84, &v91, ppvb) || !v91 )
        goto LABEL_139;
      *(_QWORD *)v85 = 0;
      ppvb = v85;
      v19 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, _QWORD *, _QWORD))pProxy->lpVtbl[2].QueryInterface)(
              pProxy,
              0,
              v84,
              0);
      v20 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x185,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
          (const char *)(unsigned int)v19,
          (int)v85);
        v21 = *(_QWORD *)v85;
        if ( *(_QWORD *)v85 )
        {
          *(_QWORD *)v85 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        }
        v22 = v84;
        if ( v84 )
        {
          v84 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v22 + 16LL))(v22);
        }
        v23 = v86;
        if ( v86 )
        {
          v86 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        }
        v24 = pProxy;
        if ( pProxy )
        {
          pProxy = 0;
          ((void (__fastcall *)(IUnknown *))v24->lpVtbl->Release)(v24);
        }
LABEL_86:
        v97[0] = &LanguageOverlayTraceProvider::UninstallSystemLanguagePackActivity::`vftable';
        wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v97);
        wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v97);
        return (unsigned int)v20;
      }
      v87 = 0;
      v25 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 **))v85)(
              *(_QWORD *)v85,
              &GUID_75207393_23f2_4396_85f0_8fdb879ed0ed,
              &v87);
      v20 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x187,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
          (const char *)(unsigned int)v25,
          (int)v85);
        v26 = v87;
        if ( v87 )
        {
          v87 = 0;
          (*(void (__fastcall **)(__int64 *))(*v26 + 16))(v26);
        }
        v27 = *(_QWORD *)v85;
        if ( *(_QWORD *)v85 )
        {
          *(_QWORD *)v85 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        }
        v28 = v84;
        if ( v84 )
        {
          v84 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
        }
        v29 = v86;
        if ( v86 )
        {
          v86 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        }
        v30 = pProxy;
        if ( pProxy )
        {
          pProxy = 0;
          ((void (__fastcall *)(IUnknown *))v30->lpVtbl->Release)(v30);
        }
        goto LABEL_86;
      }
      pv = 0;
      v31 = *v87;
      *(_QWORD *)&v92 = &pv;
      *((_QWORD *)&v92 + 1) = 0;
      LOBYTE(v93) = 1;
      v20 = (*(__int64 (__fastcall **)(__int64 *, __int64, char *))(v31 + 32))(v87, 8, (char *)&v92 + 8);
      if ( (_BYTE)v93 )
      {
        v32 = *(void **)v92;
        *(_QWORD *)v92 = *((_QWORD *)&v92 + 1);
        if ( v32 )
          CoTaskMemFree(v32);
      }
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18A,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
          (const char *)(unsigned int)v20,
          (int)v85);
        v33 = pv;
        pv = 0;
        if ( v33 )
          CoTaskMemFree(v33);
        v34 = v87;
        if ( v87 )
        {
          v87 = 0;
          (*(void (__fastcall **)(__int64 *))(*v34 + 16))(v34);
        }
        v35 = *(_QWORD *)v85;
        if ( *(_QWORD *)v85 )
        {
          *(_QWORD *)v85 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        }
        v36 = v84;
        if ( v84 )
        {
          v84 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v36 + 16LL))(v36);
        }
        v37 = v86;
        if ( v86 )
        {
          v86 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        }
        v38 = pProxy;
        if ( pProxy )
        {
          pProxy = 0;
          ((void (__fastcall *)(IUnknown *))v38->lpVtbl->Release)(v38);
        }
        goto LABEL_86;
      }
      v39 = (unsigned __int16 *)pv;
      do
      {
        v40 = *(unsigned __int16 *)((char *)v39 + (char *)L"Language Pack" - (_BYTE *)pv);
        v41 = *v39 - v40;
        if ( v41 )
          break;
        ++v39;
      }
      while ( v40 );
      if ( !v41 )
      {
        v89 = 0;
        v42 = *v84;
        v89 = 0;
        v43 = (*(__int64 (__fastcall **)(_QWORD *, LPVOID *))(v42 + 64))(v84, &v89);
        v20 = v43;
        if ( v43 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x18E,
            (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
            (const char *)(unsigned int)v43,
            (int)v85);
          if ( v89 )
            CoTaskMemFree(v89);
          v45 = pv;
          pv = 0;
          if ( v45 )
            CoTaskMemFree(v45);
          v46 = v87;
          if ( v87 )
          {
            v87 = 0;
            (*(void (__fastcall **)(__int64 *))(*v46 + 16))(v46);
          }
          v47 = *(_QWORD *)v85;
          if ( *(_QWORD *)v85 )
          {
            *(_QWORD *)v85 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
          }
          v48 = v84;
          if ( v84 )
          {
            v84 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
          }
          v49 = v86;
          if ( v86 )
          {
            v86 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
          }
          v50 = pProxy;
          if ( pProxy )
          {
            pProxy = 0;
            ((void (__fastcall *)(IUnknown *))v50->lpVtbl->Release)(v50);
          }
          goto LABEL_86;
        }
        v92 = 0;
        v93 = 0;
        _SplitIdentityStringToAttributes<std::back_insert_iterator<std::vector<std::wstring>>>(v89, v44, &v92);
        v51 = (_QWORD *)(v92 + 96);
        if ( *(_QWORD *)(v92 + 120) > 7u )
          v51 = (_QWORD *)*v51;
        v82[0] = v51;
        v52 = -1;
        do
          ++v52;
        while ( *((_WORD *)v51 + v52) );
        v82[1] = v52;
        bcp47::ConvertToMuiForm(v94, v82);
        if ( *((_QWORD *)a2 + 3) <= 7u )
          v53 = a2;
        else
          v53 = *(const unsigned __int16 **)a2;
        v54 = v94;
        if ( v96 > 7 )
          v54 = (char **)v94[0];
        if ( v95 == *((_QWORD *)a2 + 2) && (!v95 || !(unsigned int)_o__wcsnicmp(v54, v53)) )
        {
          v55 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(*v87 + 88))(v87, 21, 0);
          v56 = v55;
          if ( v55 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x199,
              (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
              (const char *)(unsigned int)v55,
              (int)v85);
            std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v94);
            std::vector<std::wstring>::_Tidy(&v92);
            if ( v89 )
              CoTaskMemFree(v89);
            v57 = pv;
            pv = 0;
            if ( v57 )
              CoTaskMemFree(v57);
            v58 = v87;
            if ( v87 )
            {
              v87 = 0;
              (*(void (__fastcall **)(__int64 *))(*v58 + 16))(v58);
            }
            v59 = *(_QWORD *)v85;
            if ( *(_QWORD *)v85 )
            {
              *(_QWORD *)v85 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
            }
            v60 = v84;
            if ( v84 )
            {
              v84 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v60 + 16LL))(v60);
            }
            v61 = v86;
            if ( v86 )
            {
              v86 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
            }
            v62 = pProxy;
            if ( pProxy )
            {
              pProxy = 0;
              ((void (__fastcall *)(IUnknown *))v62->lpVtbl->Release)(v62);
            }
            goto LABEL_114;
          }
          v90 = 0;
          v63 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, int *))pProxy->lpVtbl[4].Release)(pProxy, 0, &v90);
          v56 = v63;
          if ( v63 >= 0 )
          {
            std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v94);
            std::vector<std::wstring>::_Tidy(&v92);
            if ( v89 )
              CoTaskMemFree(v89);
            v70 = pv;
            pv = 0;
            if ( v70 )
              CoTaskMemFree(v70);
            v71 = v87;
            if ( v87 )
            {
              v87 = 0;
              (*(void (__fastcall **)(__int64 *))(*v71 + 16))(v71);
            }
            v72 = *(_QWORD *)v85;
            if ( *(_QWORD *)v85 )
            {
              *(_QWORD *)v85 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
            }
LABEL_139:
            wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(
              v97,
              0);
            v73 = v84;
            if ( v84 )
            {
              v84 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v73 + 16LL))(v73);
            }
            v74 = v86;
            if ( v86 )
            {
              v86 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
            }
            v75 = pProxy;
            if ( pProxy )
            {
              pProxy = 0;
              ((void (__fastcall *)(IUnknown *))v75->lpVtbl->Release)(v75);
            }
            v97[0] = &LanguageOverlayTraceProvider::UninstallSystemLanguagePackActivity::`vftable';
            wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v97);
            wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v97);
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x19C,
              (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
              (const char *)(unsigned int)v63,
              (int)v85);
            std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v94);
            std::vector<std::wstring>::_Tidy(&v92);
            if ( v89 )
              CoTaskMemFree(v89);
            v64 = pv;
            pv = 0;
            if ( v64 )
              CoTaskMemFree(v64);
            v65 = v87;
            if ( v87 )
            {
              v87 = 0;
              (*(void (__fastcall **)(__int64 *))(*v65 + 16))(v65);
            }
            v66 = *(_QWORD *)v85;
            if ( *(_QWORD *)v85 )
            {
              *(_QWORD *)v85 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
            }
            v67 = v84;
            if ( v84 )
            {
              v84 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v67 + 16LL))(v67);
            }
            v68 = v86;
            if ( v86 )
            {
              v86 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
            }
            v69 = pProxy;
            if ( pProxy )
            {
              pProxy = 0;
              ((void (__fastcall *)(IUnknown *))v69->lpVtbl->Release)(v69);
            }
LABEL_114:
            v97[0] = &LanguageOverlayTraceProvider::UninstallSystemLanguagePackActivity::`vftable';
            wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v97);
            wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v97);
            return v56;
          }
        }
        std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v94);
        std::vector<std::wstring>::_Tidy(&v92);
        if ( v89 )
          CoTaskMemFree(v89);
      }
      v76 = pv;
      pv = 0;
      if ( v76 )
        CoTaskMemFree(v76);
      v77 = v87;
      if ( v87 )
      {
        v87 = 0;
        (*(void (__fastcall **)(__int64 *))(*v77 + 16))(v77);
      }
      v78 = *(_QWORD *)v85;
      if ( *(_QWORD *)v85 )
      {
        *(_QWORD *)v85 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
      }
      v16 = v84;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1A5,
                           (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemla"
                                         "nguageresourcesprovider.cpp",
                           v14);
  }
  return result;
}

```

## disassembly

```asm
0x180047070  mov     [rsp+arg_0], rbx
0x180047075  mov     [rsp+arg_10], rsi
0x18004707a  push    rdi
0x18004707b  push    r14
0x18004707d  push    r15
0x18004707f  sub     rsp, 230h
0x180047086  mov     rax, cs:__security_cookie
0x18004708d  xor     rax, rsp
0x180047090  mov     [rsp+248h+var_28], rax
0x180047098  mov     rbx, rdx
0x18004709b  cmp     qword ptr [rdx+18h], 7
0x1800470a0  jbe     short loc_1800470A7
0x1800470a2  mov     rdi, [rdx]
0x1800470a5  jmp     short loc_1800470AA
0x1800470a7  mov     rdi, rbx
0x1800470aa  lea     rdx, aUninstallsyste; "UninstallSystemLanguagePackActivity"
0x1800470b1  lea     rcx, [rsp+248h+var_178]
0x1800470b9  call    ??0?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800470be  lea     r15, ??_7UninstallSystemLanguagePackActivity@LanguageOverlayTraceProvider@@6B@; const LanguageOverlayTraceProvider::UninstallSystemLanguagePackActivity::`vftable'
0x1800470c5  mov     [rsp+248h+var_178], r15
0x1800470cd  mov     rdx, rdi; unsigned __int16 *
0x1800470d0  lea     rcx, [rsp+248h+var_178]; this
0x1800470d8  call    ?StartActivity@UninstallSystemLanguagePackActivity@LanguageOverlayTraceProvider@@QEAAXPEBG@Z; LanguageOverlayTraceProvider::UninstallSystemLanguagePackActivity::StartActivity(ushort const *)
0x1800470dd  nop
0x1800470de  xor     r14d, r14d
0x1800470e1  mov     [rsp+248h+pProxy], r14
0x1800470e6  lea     rax, [rsp+248h+pProxy]
0x1800470eb  mov     [rsp+248h+ppv], rax; int
0x1800470f0  lea     r9, _GUID_9c7e3cf3_4c97_4d36_bdeb_e3093c228c22; riid
0x1800470f7  xor     edx, edx; pUnkOuter
0x1800470f9  lea     r8d, [r14+15h]; dwClsContext
0x1800470fd  lea     rcx, _GUID_752073a1_23f2_4396_85f0_8fdb879ed0ed; rclsid
0x180047104  call    cs:__imp_CoCreateInstance
0x18004710a  mov     edi, eax
0x18004710c  test    eax, eax
0x18004710e  jns     short loc_180047172
0x180047110  mov     rcx, [rsp+248h]; this
0x180047118  mov     r9d, eax; char *
0x18004711b  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x180047122  mov     edx, 16Fh; void *
0x180047127  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004712c  nop
0x18004712d  mov     rcx, [rsp+248h+pProxy]
0x180047132  test    rcx, rcx
0x180047135  jz      short loc_180047149
0x180047137  mov     [rsp+248h+pProxy], r14
0x18004713c  mov     rax, [rcx]
0x18004713f  mov     rax, [rax+10h]
0x180047143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047148  nop
0x180047149  mov     [rsp+248h+var_178], r15
0x180047151  lea     rcx, [rsp+248h+var_178]
0x180047159  call    ?Destroy@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18004715e  lea     rcx, [rsp+248h+var_178]
0x180047166  call    ??1?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18004716b  mov     eax, edi
0x18004716d  jmp     loc_180047C84
0x180047172  mov     [rsp+248h+dwCapabilities], r14d; dwCapabilities
0x180047177  mov     [rsp+248h+pAuthInfo], r14; pAuthInfo
0x18004717c  mov     eax, 3
0x180047181  mov     [rsp+248h+dwImpLevel], eax; dwImpLevel
0x180047185  mov     dword ptr [rsp+248h+ppv], eax; int
0x180047189  xor     r9d, r9d; pServerPrincName
0x18004718c  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18004718f  mov     r8d, edx; dwAuthzSvc
0x180047192  mov     rcx, [rsp+248h+pProxy]; pProxy
0x180047197  call    cs:__imp_CoSetProxyBlanket
0x18004719d  mov     edi, eax
0x18004719f  test    eax, eax
0x1800471a1  jns     short loc_180047205
0x1800471a3  mov     rcx, [rsp+248h]; this
0x1800471ab  mov     r9d, eax; char *
0x1800471ae  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x1800471b5  mov     edx, 178h; void *
0x1800471ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800471bf  nop
0x1800471c0  mov     rcx, [rsp+248h+pProxy]
0x1800471c5  test    rcx, rcx
0x1800471c8  jz      short loc_1800471DC
0x1800471ca  mov     [rsp+248h+pProxy], r14
0x1800471cf  mov     rax, [rcx]
0x1800471d2  mov     rax, [rax+10h]
0x1800471d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800471db  nop
0x1800471dc  mov     [rsp+248h+var_178], r15
0x1800471e4  lea     rcx, [rsp+248h+var_178]
0x1800471ec  call    ?Destroy@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800471f1  lea     rcx, [rsp+248h+var_178]
0x1800471f9  call    ??1?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800471fe  mov     eax, edi
0x180047200  jmp     loc_180047C84
0x180047205  mov     rcx, [rsp+248h+pProxy]
0x18004720a  mov     rax, [rcx]
0x18004720d  mov     [rsp+248h+ppv], r14; int
0x180047212  xor     r9d, r9d
0x180047215  lea     r8, sourceString; "Language Overlay Service"
0x18004721c  lea     edx, [r9+30h]
0x180047220  mov     rax, [rax+18h]
0x180047224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047229  mov     edi, eax
0x18004722b  test    eax, eax
0x18004722d  jns     short loc_180047291
0x18004722f  mov     rcx, [rsp+248h]; this
0x180047237  mov     r9d, eax; char *
0x18004723a  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x180047241  mov     edx, 17Bh; void *
0x180047246  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004724b  nop
0x18004724c  mov     rcx, [rsp+248h+pProxy]
0x180047251  test    rcx, rcx
0x180047254  jz      short loc_180047268
0x180047256  mov     [rsp+248h+pProxy], r14
0x18004725b  mov     rax, [rcx]
0x18004725e  mov     rax, [rax+10h]
0x180047262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047267  nop
0x180047268  mov     [rsp+248h+var_178], r15
0x180047270  lea     rcx, [rsp+248h+var_178]
0x180047278  call    ?Destroy@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18004727d  lea     rcx, [rsp+248h+var_178]
0x180047285  call    ??1?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18004728a  mov     eax, edi
0x18004728c  jmp     loc_180047C84
0x180047291  mov     [rsp+248h+var_1E0], r14
0x180047296  mov     rcx, [rsp+248h+pProxy]
0x18004729b  mov     rax, [rcx]
0x18004729e  lea     r8, [rsp+248h+var_1E0]
0x1800472a3  mov     edx, 10h
0x1800472a8  mov     rax, [rax+38h]
0x1800472ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800472b1  mov     edi, eax
0x1800472b3  test    eax, eax
0x1800472b5  jns     short loc_180047335
0x1800472b7  mov     rcx, [rsp+248h]; this
0x1800472bf  mov     r9d, eax; char *
0x1800472c2  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x1800472c9  mov     edx, 17Eh; void *
0x1800472ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800472d3  nop
0x1800472d4  mov     rcx, [rsp+248h+var_1E0]
0x1800472d9  test    rcx, rcx
0x1800472dc  jz      short loc_1800472F0
0x1800472de  mov     [rsp+248h+var_1E0], r14
0x1800472e3  mov     rax, [rcx]
0x1800472e6  mov     rax, [rax+10h]
0x1800472ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800472ef  nop
0x1800472f0  mov     rcx, [rsp+248h+pProxy]
0x1800472f5  test    rcx, rcx
0x1800472f8  jz      short loc_18004730C
0x1800472fa  mov     [rsp+248h+pProxy], r14
0x1800472ff  mov     rax, [rcx]
0x180047302  mov     rax, [rax+10h]
0x180047306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004730b  nop
0x18004730c  mov     [rsp+248h+var_178], r15
0x180047314  lea     rcx, [rsp+248h+var_178]
0x18004731c  call    ?Destroy@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180047321  lea     rcx, [rsp+248h+var_178]
0x180047329  call    ??1?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18004732e  mov     eax, edi
0x180047330  jmp     loc_180047C84
0x180047335  mov     rcx, r14
0x180047338  mov     [rsp+248h+var_1F0], rcx
0x18004733d  mov     [rsp+248h+var_1BC], r14d
0x180047345  mov     rdi, [rsp+248h+var_1E0]
0x18004734a  mov     rax, [rdi]
0x18004734d  mov     rsi, [rax+18h]
0x180047351  test    rcx, rcx
0x180047354  jz      short loc_180047368
0x180047356  mov     [rsp+248h+var_1F0], r14
0x18004735b  mov     rdx, [rcx]
0x18004735e  mov     rax, [rdx+10h]
0x180047362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047367  nop
0x180047368  lea     r9, [rsp+248h+var_1BC]
0x180047370  lea     r8, [rsp+248h+var_1F0]
0x180047375  mov     edx, 1
0x18004737a  mov     rcx, rdi
0x18004737d  mov     rax, rsi
0x180047380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047385  test    eax, eax
0x180047387  jnz     loc_180047BF3
0x18004738d  cmp     [rsp+248h+var_1BC], r14d
0x180047395  jbe     loc_180047BF3
0x18004739b  mov     qword ptr [rsp+248h+var_1E8], r14
0x1800473a0  mov     rcx, [rsp+248h+pProxy]
0x1800473a5  mov     rax, [rcx]
0x1800473a8  lea     rdx, [rsp+248h+var_1E8]
0x1800473ad  mov     [rsp+248h+ppv], rdx; int
0x1800473b2  xor     r9d, r9d
0x1800473b5  mov     r8, [rsp+248h+var_1F0]
0x1800473ba  xor     edx, edx
0x1800473bc  mov     rax, [rax+30h]
0x1800473c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800473c5  mov     edi, eax
0x1800473c7  test    eax, eax
0x1800473c9  jns     loc_180047485
0x1800473cf  mov     rcx, [rsp+248h]; this
0x1800473d7  mov     r9d, eax; char *
0x1800473da  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x1800473e1  mov     edx, 185h; void *
0x1800473e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800473eb  nop
0x1800473ec  mov     rcx, qword ptr [rsp+248h+var_1E8]
0x1800473f1  test    rcx, rcx
0x1800473f4  jz      short loc_180047408
0x1800473f6  mov     qword ptr [rsp+248h+var_1E8], r14
0x1800473fb  mov     rax, [rcx]
0x1800473fe  mov     rax, [rax+10h]
0x180047402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047407  nop
0x180047408  mov     rcx, [rsp+248h+var_1F0]
0x18004740d  test    rcx, rcx
0x180047410  jz      short loc_180047424
0x180047412  mov     [rsp+248h+var_1F0], r14
0x180047417  mov     rax, [rcx]
0x18004741a  mov     rax, [rax+10h]
0x18004741e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047423  nop
0x180047424  mov     rcx, [rsp+248h+var_1E0]
0x180047429  test    rcx, rcx
0x18004742c  jz      short loc_180047440
0x18004742e  mov     [rsp+248h+var_1E0], r14
0x180047433  mov     rax, [rcx]
0x180047436  mov     rax, [rax+10h]
0x18004743a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004743f  nop
0x180047440  mov     rcx, [rsp+248h+pProxy]
0x180047445  test    rcx, rcx
0x180047448  jz      short loc_18004745C
0x18004744a  mov     [rsp+248h+pProxy], r14
0x18004744f  mov     rax, [rcx]
0x180047452  mov     rax, [rax+10h]
0x180047456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004745b  nop
0x18004745c  mov     [rsp+248h+var_178], r15
0x180047464  lea     rcx, [rsp+248h+var_178]
0x18004746c  call    ?Destroy@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180047471  lea     rcx, [rsp+248h+var_178]
0x180047479  call    ??1?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18004747e  mov     eax, edi
0x180047480  jmp     loc_180047C84
0x180047485  mov     [rsp+248h+var_1D8], r14
0x18004748a  mov     rcx, qword ptr [rsp+248h+var_1E8]
0x18004748f  mov     rax, [rcx]
0x180047492  lea     r8, [rsp+248h+var_1D8]
0x180047497  lea     rdx, _GUID_75207393_23f2_4396_85f0_8fdb879ed0ed
0x18004749e  mov     rax, [rax]
0x1800474a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800474a6  mov     edi, eax
0x1800474a8  test    eax, eax
0x1800474aa  jns     loc_180047582
0x1800474b0  mov     rcx, [rsp+248h]; this
0x1800474b8  mov     r9d, eax; char *
0x1800474bb  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x1800474c2  mov     edx, 187h; void *
0x1800474c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800474cc  nop
0x1800474cd  mov     rcx, [rsp+248h+var_1D8]
0x1800474d2  test    rcx, rcx
0x1800474d5  jz      short loc_1800474E9
0x1800474d7  mov     [rsp+248h+var_1D8], r14
0x1800474dc  mov     rax, [rcx]
0x1800474df  mov     rax, [rax+10h]
0x1800474e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800474e8  nop
0x1800474e9  mov     rcx, qword ptr [rsp+248h+var_1E8]
0x1800474ee  test    rcx, rcx
0x1800474f1  jz      short loc_180047505
0x1800474f3  mov     qword ptr [rsp+248h+var_1E8], r14
0x1800474f8  mov     rax, [rcx]
0x1800474fb  mov     rax, [rax+10h]
0x1800474ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047504  nop
0x180047505  mov     rcx, [rsp+248h+var_1F0]
0x18004750a  test    rcx, rcx
0x18004750d  jz      short loc_180047521
0x18004750f  mov     [rsp+248h+var_1F0], r14
0x180047514  mov     rax, [rcx]
0x180047517  mov     rax, [rax+10h]
0x18004751b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047520  nop
0x180047521  mov     rcx, [rsp+248h+var_1E0]
0x180047526  test    rcx, rcx
0x180047529  jz      short loc_18004753D
0x18004752b  mov     [rsp+248h+var_1E0], r14
0x180047530  mov     rax, [rcx]
0x180047533  mov     rax, [rax+10h]
0x180047537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004753c  nop
0x18004753d  mov     rcx, [rsp+248h+pProxy]
0x180047542  test    rcx, rcx
0x180047545  jz      short loc_180047559
0x180047547  mov     [rsp+248h+pProxy], r14
0x18004754c  mov     rax, [rcx]
0x18004754f  mov     rax, [rax+10h]
0x180047553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047558  nop
0x180047559  mov     [rsp+248h+var_178], r15
  ... truncated ...
```
