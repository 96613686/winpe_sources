# DownloadPackages(void *,IUpdateSession *,IUpdateCollection *,ulong,HSTRING__ *,ushort const *,IDownloadProgressChangedCallback *,IDownloadCompletedCallback *,HSTRING__ *,char const *,IUpdateDownloader * *,IDownloadJob * *)

- ea: `0x180073690`
- end: `0x180073ee1`
- name: `?DownloadPackages@@YAJPEAXPEAUIUpdateSession@@PEAUIUpdateCollection@@KPEAUHSTRING__@@PEBGPEAUIDownloadProgressChangedCallback@@PEAUIDownloadCompletedCallback@@3PEBDPEAPEAUIUpdateDownloader@@PEAPEAUIDownloadJob@@@Z`
- size: `2129`
- prototype: `__int64 __fastcall(void *, struct IUpdateSession *, struct IUpdateCollection *, unsigned int, HSTRING, const unsigned __int16 *, struct IDownloadProgressChangedCallback *, struct IDownloadCompletedCallback *, HSTRING, const char *, struct IUpdateDownloader **, BSTR bstrString)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f7914`

## callees

- `0x1800101f4`
- `0x1800127c8`
- `0x18001c844`
- `0x18003fe8c`
- `0x18006f8b4`
- `0x18007023c`
- `0x180071dcc`
- `0x180073690`
- `0x180078c60`
- `0x180079878`
- `0x180079a68`
- `0x18007a7cc`
- `0x180215010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180073cdb`
- `OLEAUT32!__imp_SysAllocString` at `0x180073cdb`
- `OLEAUT32!__imp_SysFreeString` at `0x180073b37`
- `OLEAUT32!__imp_SysFreeString` at `0x180073b37`
- `OLEAUT32!__imp_VariantInit` at `0x1800737f0`
- `OLEAUT32!__imp_VariantInit` at `0x180073949`
- `OLEAUT32!__imp_VariantInit` at `0x180073cbd`
- `OLEAUT32!__imp_VariantInit` at `0x1800737f0`
- `OLEAUT32!__imp_VariantInit` at `0x180073949`
- `OLEAUT32!__imp_VariantInit` at `0x180073cbd`
- `OLEAUT32!__imp_VariantClear` at `0x1800739b6`
- `OLEAUT32!__imp_VariantClear` at `0x180073d29`
- `OLEAUT32!__imp_VariantClear` at `0x1800739b6`
- `OLEAUT32!__imp_VariantClear` at `0x180073d29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180073c6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180073d33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180073c6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180073d33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180073cd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180073cd2`

## string_xrefs

- `0x180073719`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x1800738d5`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180073922`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x1800739a3`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x1800739fe`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180073ac7`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180073b26`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180073d80`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180073e70`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180073706`: `pSession->CreateUpdateDownloader(&spDownloader)`
- `0x180073913`: `_SetWuUserTokenProperty(spInternalConfiguration.Get(), IUPDATE_INTERNALPROPERTY_DOWNLOAD_USERTOKEN, hUserToken)`
- `0x1800738bf`: `spDownloader->QueryInterface(IID_PPV_ARGS(&spInternalConfiguration))`
- `0x180073994`: `spInternalConfiguration->put_InternalConfigurationProperty(IUPDATE_INTERNALPROPERTY_DOWNLOAD_USERTOKEN, var)`
- `0x180073d6a`: `spDownloader->put_Updates(pPackages)`
- `0x180073e61`: `spDownloader->BeginDownload(pProgress, pCompleted, varNull, &spJob)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DownloadPackages(
        void *a1,
        struct IUpdateSession *a2,
        struct IUpdateCollection *a3,
        __int16 a4,
        HSTRING a5,
        unsigned __int16 *a6,
        struct IDownloadProgressChangedCallback *a7,
        struct IDownloadCompletedCallback *a8,
        HSTRING a9,
        const char *a10,
        struct IUpdateDownloader **a11,
        struct IUpdateInternalConfiguration *bstrString)
{
  struct IUpdateDownloader **v15; // r12
  struct IUpdateInternalConfiguration *v16; // r13
  HRESULT (__stdcall *CreateUpdateDownloader)(IUpdateSession *, IUpdateDownloader **); // rbx
  int v18; // eax
  int v19; // edi
  int v20; // esi
  struct IUpdateDownloader **v21; // rbx
  struct IUpdateDownloaderVtbl *lpVtbl; // rdi
  struct IUpdateDownloader **v23; // rdi
  struct IUpdateDownloaderVtbl *v24; // rbx
  int v25; // eax
  int v26; // eax
  int v27; // eax
  char v28; // al
  __int64 v29; // rdx
  OLECHAR *v30; // rbx
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  struct IUpdateDownloader **v36; // rdi
  struct IUpdateDownloaderVtbl *v37; // rbx
  int v38; // eax
  struct IUpdateDownloader **v39; // rax
  struct IUpdateInternalConfiguration *v40; // rax
  int v42; // [rsp+30h] [rbp-C1h]
  int v43; // [rsp+30h] [rbp-C1h]
  int v44; // [rsp+30h] [rbp-C1h]
  int v45; // [rsp+30h] [rbp-C1h]
  VARIANTARG pvarg; // [rsp+40h] [rbp-B1h] BYREF
  __int64 v47; // [rsp+58h] [rbp-99h]
  _QWORD v48[3]; // [rsp+60h] [rbp-91h] BYREF
  __int64 v49; // [rsp+78h] [rbp-79h]
  int v50; // [rsp+88h] [rbp-69h] BYREF
  bool v51; // [rsp+8Ch] [rbp-65h]
  int v52; // [rsp+90h] [rbp-61h]
  bool v53; // [rsp+94h] [rbp-5Dh]
  int v54; // [rsp+98h] [rbp-59h]
  char v55; // [rsp+9Ch] [rbp-55h]
  int v56; // [rsp+A0h] [rbp-51h]
  bool v57; // [rsp+A4h] [rbp-4Dh]
  int v58; // [rsp+A8h] [rbp-49h]
  bool v59; // [rsp+ACh] [rbp-45h]
  int v60; // [rsp+B0h] [rbp-41h]
  char v61; // [rsp+B4h] [rbp-3Dh]
  int v62; // [rsp+B8h] [rbp-39h]
  char v63; // [rsp+BCh] [rbp-35h]
  int v64; // [rsp+C0h] [rbp-31h]
  char v65; // [rsp+C4h] [rbp-2Dh]
  int v66; // [rsp+C8h] [rbp-29h]
  char v67; // [rsp+CCh] [rbp-25h]
  int v68; // [rsp+D0h] [rbp-21h]
  bool v69; // [rsp+D4h] [rbp-1Dh]
  int v70; // [rsp+D8h] [rbp-19h]
  char v71; // [rsp+DCh] [rbp-15h]

  v15 = a11;
  *a11 = 0;
  v16 = bstrString;
  *(_QWORD *)bstrString = 0;
  a11 = 0;
  CreateUpdateDownloader = a2->lpVtbl->CreateUpdateDownloader;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&a11);
  v18 = ((__int64 (__fastcall *)(struct IUpdateSession *, struct IUpdateDownloader ***))CreateUpdateDownloader)(
          a2,
          &a11);
  v19 = TraceHR(
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
          0x235u,
          "DownloadPackages",
          "pSession->CreateUpdateDownloader(&spDownloader)",
          v18,
          v42);
  if ( v19 < 0 )
    goto LABEL_61;
  if ( (a4 & 0x40) == 0 && (a4 & 0x4000) == 0 )
  {
    v20 = a4 & 0x10;
    if ( (a4 & 0x10) != 0 )
    {
      bstrString = 0;
      v21 = a11;
      lpVtbl = (*a11)->lpVtbl;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&bstrString);
      if ( ((int (__fastcall *)(struct IUpdateDownloader **, GUID *, struct IUpdateInternalConfiguration **))lpVtbl)(
             v21,
             &GUID_829a2abf_33f9_4e74_aa7a_395a1e77dc5d,
             &bstrString) >= 0 )
        (*(void (__fastcall **)(struct IUpdateInternalConfiguration *, __int64))(*(_QWORD *)bstrString + 144LL))(
          bstrString,
          0xFFFFFFFFLL);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&bstrString);
    }
    else
    {
      v20 = 0;
    }
LABEL_12:
    v19 = SetIntentPFNConfigurationProperty<IUpdateDownloader>(&a11, a5);
    if ( v19 >= 0 )
    {
      if ( a1 )
      {
        bstrString = 0;
        v23 = a11;
        v24 = (*a11)->lpVtbl;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&bstrString);
        v25 = ((__int64 (__fastcall *)(struct IUpdateDownloader **, GUID *, struct IUpdateInternalConfiguration **))v24)(
                v23,
                &GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b,
                &bstrString);
        v19 = TraceHR(
                "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                0x25Cu,
                "DownloadPackages",
                "spDownloader->QueryInterface(IID_PPV_ARGS(&spInternalConfiguration))",
                v25,
                v43);
        if ( v19 >= 0 )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureTokensAreDuplicable>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnsureTokensAreDuplicable>::GetImpl'::`2'::impl) )
          {
            v26 = _SetWuUserTokenProperty(bstrString, 0x30006u, a1);
            v19 = TraceHR(
                    "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                    0x261u,
                    "DownloadPackages",
                    "_SetWuUserTokenProperty(spInternalConfiguration.Get(), IUPDATE_INTERNALPROPERTY_DOWNLOAD_USERTOKEN, hUserToken)",
                    v26,
                    v43);
          }
          else
          {
            *(_OWORD *)&pvarg.decVal.Lo32 = 0;
            v47 = 0;
            VariantInit((VARIANTARG *)&pvarg.decVal.8);
            pvarg.iVal = 19;
            *((_DWORD *)&pvarg.decVal + 4) = (_DWORD)a1;
            *(_OWORD *)&v48[1] = *(_OWORD *)&pvarg.decVal.Lo32;
            v49 = v47;
            v27 = (*(__int64 (__fastcall **)(struct IUpdateInternalConfiguration *, __int64, _QWORD *))(*(_QWORD *)bstrString + 32LL))(
                    bstrString,
                    196614,
                    &v48[1]);
            v19 = TraceHR(
                    "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                    0x269u,
                    "DownloadPackages",
                    "spInternalConfiguration->put_InternalConfigurationProperty(IUPDATE_INTERNALPROPERTY_DOWNLOAD_USERTOKEN, var)",
                    v27,
                    v43);
            VariantClear((VARIANTARG *)&pvarg.decVal.8);
          }
        }
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&bstrString);
      }
      else
      {
        LogSimpleMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
          0x270u,
          "DownloadPackages",
          -1,
          L"User wasnt logged in. Downloading as LocalSystem",
          0,
          0);
      }
    }
    goto LABEL_20;
  }
  bstrString = 0;
  if ( (int)Microsoft::WRL::ComPtr<IUpdateSearcher>::As<IUpdateInternalConfiguration>(&a11, &bstrString) >= 0 )
  {
    *(_OWORD *)&pvarg.decVal.Lo32 = 0;
    v47 = 0;
    VariantInit((VARIANTARG *)&pvarg.decVal.8);
    pvarg.iVal = 19;
    *((_DWORD *)&pvarg.decVal + 4) = ((a4 & 0x40) != 0) + 3;
    *(_OWORD *)&v48[1] = *(_OWORD *)&pvarg.decVal.Lo32;
    v49 = v47;
    v19 = (*(__int64 (__fastcall **)(struct IUpdateInternalConfiguration *, __int64, _QWORD *))(*(_QWORD *)bstrString
                                                                                              + 32LL))(
            bstrString,
            196613,
            &v48[1]);
  }
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&bstrString);
  v20 = a4 & 0x10;
  if ( v19 >= 0 )
    goto LABEL_12;
LABEL_20:
  if ( (a4 & 1) != 0 || v20 )
  {
    v28 = 0;
    if ( (a4 & 1) != 0 )
    {
LABEL_28:
      v29 = 3;
      goto LABEL_29;
    }
  }
  else
  {
    v28 = 1;
  }
  if ( (a4 & 8) != 0 && !v20 && (a4 & 0x4000) == 0 )
    goto LABEL_28;
  v29 = 4;
  if ( v28 )
    goto LABEL_28;
LABEL_29:
  if ( v20 )
    v29 = 4;
  ((void (__fastcall *)(struct IUpdateDownloader **, __int64))(*a11)[12].lpVtbl)(a11, v29);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureTokensAreDuplicable>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnsureTokensAreDuplicable>::GetImpl'::`2'::impl) )
  {
    if ( v19 < 0 )
      goto LABEL_61;
    v19 = -2147024882;
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, a6);
    v30 = (OLECHAR *)bstrString;
    if ( bstrString )
    {
      v31 = ((__int64 (__fastcall *)(struct IUpdateDownloader **, struct IUpdateInternalConfiguration *))(*a11)[8].lpVtbl)(
              a11,
              bstrString);
      v19 = TraceHR(
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
              0x28Cu,
              "DownloadPackages",
              "spDownloader->put_ClientApplicationID(sbstrClientApplicationId)",
              v31,
              v43);
    }
  }
  else
  {
    v19 = -2147024882;
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, a6);
    v30 = (OLECHAR *)bstrString;
    if ( bstrString )
    {
      v32 = ((__int64 (__fastcall *)(struct IUpdateDownloader **, struct IUpdateInternalConfiguration *))(*a11)[8].lpVtbl)(
              a11,
              bstrString);
      v19 = TraceHR(
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
              0x297u,
              "DownloadPackages",
              "spDownloader->put_ClientApplicationID(sbstrClientApplicationId)",
              v32,
              v43);
    }
  }
  SysFreeString(v30);
  if ( v19 < 0 )
    goto LABEL_61;
  v50 = 196611;
  v51 = v20 != 0;
  v52 = 196619;
  v53 = (a4 & 0x20) != 0;
  v54 = 196618;
  v55 = a4 & 1;
  v56 = 196617;
  v57 = (a4 & 1) == 0;
  v58 = 196623;
  v59 = (a4 & 0x400) != 0;
  v60 = 196610;
  if ( v20 || (a4 & 0x20) != 0 )
  {
    v61 = 1;
    v62 = 196620;
    if ( v20 )
      goto LABEL_46;
  }
  else
  {
    v61 = 0;
    v62 = 196620;
  }
  if ( (a4 & 1) != 0 && !(unsigned int)IsDeviceXbox() )
  {
    v63 = 1;
    v64 = 196612;
    goto LABEL_48;
  }
LABEL_46:
  v63 = 0;
  v64 = 196612;
  if ( !v20 && (a4 & 1) != 0 )
  {
LABEL_48:
    v33 = IsDeviceXbox();
    v65 = 1;
    if ( v33 )
      goto LABEL_50;
  }
  v65 = 0;
LABEL_50:
  v66 = 196615;
  v67 = 0;
  v68 = 196624;
  v69 = (a4 & 0x2000) != 0;
  v70 = 196609;
  v71 = 0;
  v19 = SetInternalConfigurationFlags(a11, &v50, 11, a10);
  if ( v19 >= 0 )
  {
    bstrString = 0;
    v19 = Microsoft::WRL::ComPtr<IUpdateSearcher>::As<IUpdateInternalConfiguration>(&a11, &bstrString);
    if ( v19 >= 0 )
    {
      WindowsDeleteString(0);
      v19 = DetermineWUVolumePath(a9);
      WindowsDeleteString(0);
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&bstrString);
    if ( v19 >= 0 )
    {
      v34 = ((__int64 (__fastcall *)(struct IUpdateDownloader **, struct IUpdateCollection *))(*a11)[14].lpVtbl)(
              a11,
              a3);
      v19 = TraceHR(
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
              0x2E1u,
              "DownloadPackages",
              "spDownloader->put_Updates(pPackages)",
              v34,
              v43);
      if ( v19 >= 0 )
      {
        if ( (a4 & 8) != 0 )
        {
          LogSimpleMessage(
            3u,
            "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
            0x2E6u,
            "DownloadPackages",
            -1,
            L"Downloading with IsForced = TRUE",
            0,
            0);
          v35 = ((__int64 (__fastcall *)(struct IUpdateDownloader **, __int64))(*a11)[10].lpVtbl)(a11, 0xFFFFFFFFLL);
          v19 = TraceHR(
                  "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                  0x2E7u,
                  "DownloadPackages",
                  "spDownloader->put_IsForced(VARIANT_TRUE)",
                  v35,
                  v45);
        }
        if ( v19 >= 0 )
        {
          bstrString = 0;
          v36 = a11;
          v37 = (*a11)[15].lpVtbl;
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&bstrString);
          *(_OWORD *)&v48[1] = 0;
          v49 = 0;
          v38 = ((__int64 (__fastcall *)(struct IUpdateDownloader **, struct IDownloadProgressChangedCallback *, struct IDownloadCompletedCallback *, _QWORD *, struct IUpdateInternalConfiguration **))v37)(
                  v36,
                  a7,
                  a8,
                  &v48[1],
                  &bstrString);
          v19 = TraceHR(
                  "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                  0x2EEu,
                  "DownloadPackages",
                  "spDownloader->BeginDownload(pProgress, pCompleted, varNull, &spJob)",
                  v38,
                  v44);
          if ( v19 >= 0 )
          {
            v39 = a11;
            a11 = 0;
            *v15 = (struct IUpdateDownloader *)v39;
            v40 = bstrString;
            bstrString = 0;
            *(_QWORD *)v16 = v40;
          }
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&bstrString);
        }
      }
    }
  }
LABEL_61:
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&a11);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180073690  mov     rax, rsp
0x180073693  mov     [rax+8], rbx
0x180073697  mov     [rax+18h], r8
0x18007369b  push    rbp
0x18007369c  push    rsi
0x18007369d  push    rdi
0x18007369e  push    r12
0x1800736a0  push    r13
0x1800736a2  push    r14
0x1800736a4  push    r15
0x1800736a6  lea     rbp, [rax-3Fh]
0x1800736aa  sub     rsp, 0F0h
0x1800736b1  movaps  xmmword ptr [rax-48h], xmm6
0x1800736b5  mov     r14d, r9d
0x1800736b8  mov     rdi, rdx
0x1800736bb  mov     r15, rcx
0x1800736be  xor     esi, esi
0x1800736c0  mov     r12, [rbp+37h+arg_50]
0x1800736c7  mov     [r12], rsi
0x1800736cb  mov     r13, [rbp+37h+bstrString]
0x1800736d2  mov     [r13+0], rsi
0x1800736d6  mov     [rbp+37h+arg_50], rsi
0x1800736dd  mov     rax, [rdx]
0x1800736e0  mov     rbx, [rax+68h]
0x1800736e4  lea     rcx, [rbp+37h+arg_50]
0x1800736eb  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800736f0  lea     rdx, [rbp+37h+arg_50]
0x1800736f7  mov     rcx, rdi
0x1800736fa  mov     rax, rbx
0x1800736fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073702  mov     [rsp+120h+var_100], eax; int
0x180073706  lea     r9, aPsessionCreate; "pSession->CreateUpdateDownloader(&spDow"...
0x18007370d  lea     r8, aDownloadpackag; "DownloadPackages"
0x180073714  mov     edx, 235h; unsigned int
0x180073719  lea     rcx, aOnecoreuapEndu_18; "onecoreuap\\enduser\\winstore\\installs"...
0x180073720  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x180073725  mov     edi, eax
0x180073727  test    eax, eax
0x180073729  js      loc_180073EB3
0x18007372f  mov     ebx, r14d
0x180073732  and     ebx, 40h
0x180073735  jnz     loc_1800737BE
0x18007373b  bt      r14d, 0Eh
0x180073740  jb      short loc_1800737BE
0x180073742  mov     esi, r14d
0x180073745  and     esi, 10h
0x180073748  jz      short loc_1800737B7
0x18007374a  mov     [rbp+37h+bstrString], 0
0x180073755  mov     rbx, [rbp+37h+arg_50]
0x18007375c  mov     rax, [rbx]
0x18007375f  mov     rdi, [rax]
0x180073762  lea     rcx, [rbp+37h+bstrString]
0x180073769  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007376e  lea     r8, [rbp+37h+bstrString]
0x180073775  lea     rdx, _GUID_829a2abf_33f9_4e74_aa7a_395a1e77dc5d
0x18007377c  mov     rcx, rbx
0x18007377f  mov     rax, rdi
0x180073782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073787  nop
0x180073788  test    eax, eax
0x18007378a  js      short loc_1800737A6
0x18007378c  mov     rcx, [rbp+37h+bstrString]
0x180073793  mov     rax, [rcx]
0x180073796  or      edx, 0FFFFFFFFh
0x180073799  mov     rax, [rax+90h]
0x1800737a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800737a5  nop
0x1800737a6  lea     rcx, [rbp+37h+bstrString]
0x1800737ad  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800737b2  jmp     loc_18007385B
0x1800737b7  xor     esi, esi
0x1800737b9  jmp     loc_18007385B
0x1800737be  mov     [rbp+37h+bstrString], rsi
0x1800737c5  lea     rdx, [rbp+37h+bstrString]
0x1800737cc  lea     rcx, [rbp+37h+arg_50]
0x1800737d3  call    ??$As@UIUpdateInternalConfiguration@@@?$ComPtr@UIUpdateSearcher@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUpdateInternalConfiguration@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IUpdateSearcher>::As<IUpdateInternalConfiguration>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IUpdateInternalConfiguration>>)
0x1800737d8  test    eax, eax
0x1800737da  js      short loc_180073841
0x1800737dc  xorps   xmm0, xmm0
0x1800737df  xor     eax, eax
0x1800737e1  movups  xmmword ptr [rsp+120h+pvarg+8], xmm0
0x1800737e6  mov     [rsp+120h+var_D0], rax
0x1800737eb  lea     rcx, [rsp+120h+pvarg+8]; pvarg
0x1800737f0  call    cs:__imp_VariantInit
0x1800737f6  mov     eax, 13h
0x1800737fb  mov     word ptr [rsp+120h+pvarg+8], ax
0x180073800  neg     ebx
0x180073802  sbb     eax, eax
0x180073804  neg     eax
0x180073806  add     eax, 3
0x180073809  mov     dword ptr [rsp+120h+pvarg+10h], eax
0x18007380d  mov     rcx, [rbp+37h+bstrString]
0x180073814  movups  xmm0, xmmword ptr [rsp+120h+pvarg+8]
0x180073819  movaps  xmmword ptr [rsp+120h+var_C8+8], xmm0
0x18007381e  movsd   xmm1, [rsp+120h+var_D0]
0x180073824  movsd   [rbp+37h+var_B0], xmm1
0x180073829  mov     rax, [rcx]
0x18007382c  lea     r8, [rsp+120h+var_C8+8]
0x180073831  mov     edx, 30005h
0x180073836  mov     rax, [rax+20h]
0x18007383a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007383f  mov     edi, eax
0x180073841  lea     rcx, [rbp+37h+bstrString]
0x180073848  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007384d  mov     esi, r14d
0x180073850  and     esi, 10h
0x180073853  test    edi, edi
0x180073855  js      loc_180073A0F
0x18007385b  mov     rdx, [rbp+37h+arg_20]
0x18007385f  lea     rcx, [rbp+37h+arg_50]
0x180073866  call    ??$SetIntentPFNConfigurationProperty@UIUpdateDownloader@@@@YAJAEAV?$ComPtr@UIUpdateDownloader@@@WRL@Microsoft@@PEAUHSTRING__@@@Z; SetIntentPFNConfigurationProperty<IUpdateDownloader>(Microsoft::WRL::ComPtr<IUpdateDownloader> &,HSTRING__ *)
0x18007386b  mov     edi, eax
0x18007386d  test    eax, eax
0x18007386f  js      loc_180073A0F
0x180073875  test    r15, r15
0x180073878  jz      loc_1800739CB
0x18007387e  mov     [rbp+37h+bstrString], 0
0x180073889  mov     rdi, [rbp+37h+arg_50]
0x180073890  mov     rax, [rdi]
0x180073893  mov     rbx, [rax]
0x180073896  lea     rcx, [rbp+37h+bstrString]
0x18007389d  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800738a2  lea     r8, [rbp+37h+bstrString]
0x1800738a9  lea     rdx, _GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b
0x1800738b0  mov     rcx, rdi
0x1800738b3  mov     rax, rbx
0x1800738b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800738bb  mov     [rsp+120h+var_100], eax; int
0x1800738bf  lea     r9, aSpdownloaderQu; "spDownloader->QueryInterface(IID_PPV_AR"...
0x1800738c6  lea     rbx, aDownloadpackag; "DownloadPackages"
0x1800738cd  mov     r8, rbx; char *
0x1800738d0  mov     edx, 25Ch; unsigned int
0x1800738d5  lea     rcx, aOnecoreuapEndu_18; "onecoreuap\\enduser\\winstore\\installs"...
0x1800738dc  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x1800738e1  mov     edi, eax
0x1800738e3  test    eax, eax
0x1800738e5  js      loc_1800739BD
0x1800738eb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnsureTokensAreDuplicable@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnsureTokensAreDuplicable@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureTokensAreDuplicable> `wil::Feature<__WilFeatureTraits_Feature_EnsureTokensAreDuplicable>::GetImpl(void)'::`2'::impl
0x1800738f2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnsureTokensAreDuplicable@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureTokensAreDuplicable>::__private_IsEnabled(void)
0x1800738f7  test    al, al
0x1800738f9  jz      short loc_180073935
0x1800738fb  mov     r8, r15; void *
0x1800738fe  mov     edx, 30006h; unsigned int
0x180073903  mov     rcx, [rbp+37h+bstrString]; struct IUpdateInternalConfiguration *
0x18007390a  call    ?_SetWuUserTokenProperty@@YAJPEAUIUpdateInternalConfiguration@@KPEAX@Z; _SetWuUserTokenProperty(IUpdateInternalConfiguration *,ulong,void *)
0x18007390f  mov     [rsp+120h+var_100], eax; int
0x180073913  lea     r9, aSetwuusertoken; "_SetWuUserTokenProperty(spInternalConfi"...
0x18007391a  mov     r8, rbx; char *
0x18007391d  mov     edx, 261h; unsigned int
0x180073922  lea     rcx, aOnecoreuapEndu_18; "onecoreuap\\enduser\\winstore\\installs"...
0x180073929  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x18007392e  mov     edi, eax
0x180073930  jmp     loc_1800739BD
0x180073935  xorps   xmm0, xmm0
0x180073938  xor     eax, eax
0x18007393a  movups  xmmword ptr [rsp+120h+pvarg+8], xmm0
0x18007393f  mov     [rsp+120h+var_D0], rax
0x180073944  lea     rcx, [rsp+120h+pvarg+8]; pvarg
0x180073949  call    cs:__imp_VariantInit
0x18007394f  mov     eax, 13h
0x180073954  mov     word ptr [rsp+120h+pvarg+8], ax
0x180073959  mov     dword ptr [rsp+120h+pvarg+10h], r15d
0x18007395e  mov     rcx, [rbp+37h+bstrString]
0x180073965  movups  xmm0, xmmword ptr [rsp+120h+pvarg+8]
0x18007396a  movaps  xmmword ptr [rsp+120h+var_C8+8], xmm0
0x18007396f  movsd   xmm1, [rsp+120h+var_D0]
0x180073975  movsd   [rbp+37h+var_B0], xmm1
0x18007397a  mov     rax, [rcx]
0x18007397d  lea     r8, [rsp+120h+var_C8+8]
0x180073982  mov     edx, 30006h
0x180073987  mov     rax, [rax+20h]
0x18007398b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073990  mov     [rsp+120h+var_100], eax; int
0x180073994  lea     r9, aSpinternalconf_0; "spInternalConfiguration->put_InternalCo"...
0x18007399b  mov     r8, rbx; char *
0x18007399e  mov     edx, 269h; unsigned int
0x1800739a3  lea     rcx, aOnecoreuapEndu_18; "onecoreuap\\enduser\\winstore\\installs"...
0x1800739aa  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x1800739af  mov     edi, eax
0x1800739b1  lea     rcx, [rsp+120h+pvarg+8]; pvarg
0x1800739b6  call    cs:__imp_VariantClear
0x1800739bc  nop
0x1800739bd  lea     rcx, [rbp+37h+bstrString]
0x1800739c4  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800739c9  jmp     short loc_180073A0F
0x1800739cb  mov     qword ptr [rsp+120h+pvarg], 0; unsigned __int16 *
0x1800739d4  mov     [rsp+120h+var_F0], 0; char *
0x1800739dd  lea     rax, aUserWasntLogge_0; "User wasnt logged in. Downloading as Lo"...
0x1800739e4  mov     [rsp+120h+var_F8], rax; int
0x1800739e9  mov     [rsp+120h+var_100], 0FFFFFFFFh; int
0x1800739f1  lea     r9, aDownloadpackag; "DownloadPackages"
0x1800739f8  mov     r8d, 270h; unsigned int
0x1800739fe  lea     rdx, aOnecoreuapEndu_18; "onecoreuap\\enduser\\winstore\\installs"...
0x180073a05  mov     ecx, 3; unsigned int
0x180073a0a  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x180073a0f  mov     r15d, r14d
0x180073a12  mov     ecx, 4
0x180073a17  and     r15d, 1
0x180073a1b  jnz     short loc_180073A25
0x180073a1d  test    esi, esi
0x180073a1f  jnz     short loc_180073A25
0x180073a21  mov     al, 1
0x180073a23  jmp     short loc_180073A2C
0x180073a25  xor     al, al
0x180073a27  test    r15d, r15d
0x180073a2a  jnz     short loc_180073A43
0x180073a2c  test    r14b, 8
0x180073a30  jz      short loc_180073A3D
0x180073a32  test    esi, esi
0x180073a34  jnz     short loc_180073A3D
0x180073a36  bt      r14d, 0Eh
0x180073a3b  jnb     short loc_180073A43
0x180073a3d  mov     edx, ecx
0x180073a3f  test    al, al
0x180073a41  jz      short loc_180073A48
0x180073a43  mov     edx, 3
0x180073a48  test    esi, esi
0x180073a4a  cmovnz  edx, ecx
0x180073a4d  mov     rcx, [rbp+37h+arg_50]
0x180073a54  mov     rax, [rcx]
0x180073a57  mov     rax, [rax+60h]
0x180073a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073a60  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnsureTokensAreDuplicable@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnsureTokensAreDuplicable@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureTokensAreDuplicable> `wil::Feature<__WilFeatureTraits_Feature_EnsureTokensAreDuplicable>::GetImpl(void)'::`2'::impl
0x180073a67  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnsureTokensAreDuplicable@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureTokensAreDuplicable>::__private_IsEnabled(void)
0x180073a6c  test    al, al
0x180073a6e  jz      short loc_180073AD7
0x180073a70  test    edi, edi
0x180073a72  js      loc_180073EB3
0x180073a78  mov     edi, 8007000Eh
0x180073a7d  mov     rdx, [rbp+37h+arg_28]; unsigned __int16 *
0x180073a81  lea     rcx, [rbp+37h+bstrString]; this
0x180073a88  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180073a8d  nop
0x180073a8e  mov     rbx, [rbp+37h+bstrString]
0x180073a95  test    rbx, rbx
0x180073a98  jz      short loc_180073AD5
0x180073a9a  mov     rcx, [rbp+37h+arg_50]
0x180073aa1  mov     rax, [rcx]
0x180073aa4  mov     rdx, rbx
0x180073aa7  mov     rax, [rax+40h]
0x180073aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073ab0  mov     [rsp+120h+var_100], eax; int
0x180073ab4  lea     r9, aSpdownloaderPu; "spDownloader->put_ClientApplicationID(s"...
0x180073abb  lea     r8, aDownloadpackag; "DownloadPackages"
0x180073ac2  mov     edx, 28Ch; unsigned int
0x180073ac7  lea     rcx, aOnecoreuapEndu_18; "onecoreuap\\enduser\\winstore\\installs"...
0x180073ace  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x180073ad3  mov     edi, eax
0x180073ad5  jmp     short loc_180073B34
0x180073ad7  mov     edi, 8007000Eh
0x180073adc  mov     rdx, [rbp+37h+arg_28]; unsigned __int16 *
0x180073ae0  lea     rcx, [rbp+37h+bstrString]; this
0x180073ae7  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180073aec  nop
0x180073aed  mov     rbx, [rbp+37h+bstrString]
0x180073af4  test    rbx, rbx
0x180073af7  jz      short loc_180073B34
0x180073af9  mov     rcx, [rbp+37h+arg_50]
0x180073b00  mov     rax, [rcx]
0x180073b03  mov     rdx, rbx
0x180073b06  mov     rax, [rax+40h]
0x180073b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073b0f  mov     [rsp+120h+var_100], eax; int
0x180073b13  lea     r9, aSpdownloaderPu; "spDownloader->put_ClientApplicationID(s"...
0x180073b1a  lea     r8, aDownloadpackag; "DownloadPackages"
0x180073b21  mov     edx, 297h; unsigned int
0x180073b26  lea     rcx, aOnecoreuapEndu_18; "onecoreuap\\enduser\\winstore\\installs"...
0x180073b2d  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x180073b32  mov     edi, eax
0x180073b34  mov     rcx, rbx; bstrString
0x180073b37  call    cs:__imp_SysFreeString
0x180073b3d  xor     ebx, ebx
0x180073b3f  test    edi, edi
0x180073b41  js      loc_180073EB3
0x180073b47  mov     [rbp+37h+var_A0], 30003h
0x180073b4e  test    esi, esi
0x180073b50  setnz   [rbp+37h+var_9C]
0x180073b54  mov     [rbp+37h+var_98], 3000Bh
0x180073b5b  mov     ecx, r14d
0x180073b5e  and     ecx, 20h
0x180073b61  setnz   [rbp+37h+var_94]
0x180073b65  mov     [rbp+37h+var_90], 3000Ah
0x180073b6c  mov     al, r14b
0x180073b6f  and     al, 1
0x180073b71  mov     [rbp+37h+var_8C], al
0x180073b74  mov     [rbp+37h+var_88], 30009h
0x180073b7b  test    r15d, r15d
0x180073b7e  setz    [rbp+37h+var_84]
0x180073b82  mov     [rbp+37h+var_80], 3000Fh
0x180073b89  mov     eax, r14d
0x180073b8c  shr     eax, 0Ah
0x180073b8f  and     al, 1
0x180073b91  mov     [rbp+37h+var_7C], al
0x180073b94  mov     [rbp+37h+var_78], 30002h
0x180073b9b  test    esi, esi
0x180073b9d  jnz     short loc_180073BAF
0x180073b9f  test    ecx, ecx
0x180073ba1  jnz     short loc_180073BAF
0x180073ba3  mov     [rbp+37h+var_74], bl
0x180073ba6  mov     [rbp+37h+var_70], 3000Ch
  ... truncated ...
```
