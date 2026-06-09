# CCVListUpdateManager::DownloadFile(void)

- ea: `0x18000fad8`
- end: `0x180010046`
- name: `?DownloadFile@CCVListUpdateManager@@QEAAJXZ`
- size: `1390`
- prototype: `__int64 __fastcall(CCVListUpdateManager *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000f880`

## callees

- `0x180001010`
- `0x180001358`
- `0x1800014ec`
- `0x18000159c`
- `0x1800017a0`
- `0x180002ce0`
- `0x180002d3c`
- `0x18000f094`
- `0x18000f800`
- `0x18000fad8`
- `0x18001004c`
- `0x18001029c`
- `0x18001061c`
- `0x1800106fc`
- `0x180014af0`
- `0x180014c9c`
- `0x18002b4e0`
- `0x18002d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000fc3b`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000fc3b`
- `iertutil!__imp_GetValue` at `0x18000fb4a`
- `iertutil!__imp_GetValue` at `0x18000fb77`
- `iertutil!__imp_GetValue` at `0x18000fb4a`
- `iertutil!__imp_GetValue` at `0x18000fb77`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18000fbe0`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18000fd4e`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18000fdc4`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18000fe54`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18000ffaf`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18000fbe0`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18000fd4e`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18000fdc4`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18000fe54`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18000ffaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff59`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000ff2e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000ff4b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000ff2e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000ff4b`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000fd0b`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000fd0b`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18000fbd2`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18000fd40`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18000fdb6`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18000fe46`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18000ffa0`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18000fbd2`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18000fd40`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18000fdb6`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18000fe46`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18000ffa0`
- `urlmon!__imp_CreateReadOnlyBrowserEmulationFilter` at `0x18000feae`
- `urlmon!__imp_CreateReadOnlyBrowserEmulationFilter` at `0x18000feae`
- `urlmon!__imp_GetIEBrowserModeFilterSpartanMediumILPath` at `0x18000fb97`
- `urlmon!__imp_GetIEBrowserModeFilterSpartanMediumILPath` at `0x18000fb97`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x18000fc59`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x18000fc59`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCVListUpdateManager::DownloadFile(CCVListUpdateManager *this)
{
  unsigned int IEBrowserModeFilterSpartanMediumILPath; // ebx
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  wchar_t *v6; // rax
  wchar_t *v7; // rbx
  unsigned int v8; // edx
  struct IBindStatusCallback *v9; // rbx
  unsigned int v10; // r8d
  CCVListUpdateManager *v11; // rcx
  CCVListUpdateManager *v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  BOOL v19; // edi
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rax
  void (*v25)(void); // rax
  DWORD FileAttributesW; // esi
  DWORD LastError; // edi
  __int64 v28; // rcx
  DWORD v29; // r14d
  unsigned int v30; // r8d
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  bool v35[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v36; // [rsp+64h] [rbp-9Ch] BYREF
  struct IE_GLOBAL_THREAD_STATE *CLSID; // [rsp+68h] [rbp-98h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v38; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v39; // [rsp+78h] [rbp-88h] BYREF
  __int64 v40; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *v41; // [rsp+88h] [rbp-78h] BYREF
  int v42; // [rsp+90h] [rbp-70h] BYREF
  int v43; // [rsp+94h] [rbp-6Ch] BYREF
  struct IBindStatusCallback *v44; // [rsp+98h] [rbp-68h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v45; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t Str[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  WCHAR v48[2088]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v42 = 0;
  v43 = 0;
  GetValue((__int64 *)SettingStore::IEVALUE_BrowserEmulation_CVListXMLVersionLow[0], 1, 1, &v42, 4, 0, 0);
  GetValue((__int64 *)SettingStore::IEVALUE_BrowserEmulation_CVListXMLVersionHigh[0], 1, 1, &v43, 4, 0, 0);
  Str[0] = 0;
  IEBrowserModeFilterSpartanMediumILPath = GetIEBrowserModeFilterSpartanMediumILPath(1, &pszSubkey, Str, 260);
  if ( (unsigned int)dword_18003F000 > 5 && (unsigned __int8)tlgKeywordOn((unsigned int)dword_18003F000, 0x10000000) )
  {
    v41 = Str;
    v36 = IEBrowserModeFilterSpartanMediumILPath;
    v35[0] = 1;
    v38 = GlobalThreadState();
    CLSID = (struct IE_GLOBAL_THREAD_STATE *)IEConfiguration_GetCLSID(268435459);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v3,
      (__int64)byte_18003551D,
      v4,
      v5,
      (__int64 *)&CLSID,
      (__int64 *)&v38,
      (__int64)v35,
      (__int64)&v36,
      (const WCHAR **)&v41);
  }
  if ( (IEBrowserModeFilterSpartanMediumILPath & 0x80000000) == 0 )
  {
    v6 = wcsrchr(Str, 0x5Cu);
    v7 = v6;
    if ( !v6 )
      return (unsigned int)-2147467259;
    *v6 = 0;
    SHCreateDirectoryExW(0, Str, 0);
    *v7 = 92;
    v48[0] = 0;
    GetCVListDownloadUrl(v48);
    if ( (int)CCVListTelemManager::AppendPing(v48, v8) < 0 )
    {
      v48[0] = 0;
      GetCVListDownloadUrl(v48);
    }
    v41 = 0;
    v9 = (struct IBindStatusCallback *)operator new(0x30u);
    v44 = v9;
    CBrokerDownloadBindStatusCallback::CBrokerDownloadBindStatusCallback(
      (CBrokerDownloadBindStatusCallback *)v9,
      *(_DWORD *)this);
    v9->lpVtbl = (struct IBindStatusCallbackVtbl *)&CCVListDownloadCallback::`vftable'{for `TUnknownSTBaseFRE<char>'};
    v9[2].lpVtbl = (struct IBindStatusCallbackVtbl *)&CCVListDownloadCallback::`vftable'{for `IBindStatusCallback'};
    v9[5].lpVtbl = (struct IBindStatusCallbackVtbl *)this;
    v41 = (wchar_t *)v9;
    IEBrowserModeFilterSpartanMediumILPath = DownloadToTempFile(v48, ExistingFileName, v10, v9 + 2);
    if ( IEBrowserModeFilterSpartanMediumILPath )
      goto LABEL_39;
    if ( !MoveFileExW(ExistingFileName, Str, 3u) )
    {
      if ( (int)GetLastError() > 0 )
        IEBrowserModeFilterSpartanMediumILPath = (unsigned __int16)GetLastError() | 0x80070000;
      else
        IEBrowserModeFilterSpartanMediumILPath = GetLastError();
      FileAttributesW = GetFileAttributesW(ExistingFileName);
      if ( FileAttributesW == -1 )
        LastError = GetLastError();
      else
        LastError = 0;
      v29 = GetFileAttributesW(Str);
      if ( v29 == -1 )
        GetLastError();
      if ( (unsigned int)dword_18003F000 > 5 && (unsigned __int8)tlgKeywordOn(v28, 0x10000000) )
      {
        v39 = v30;
        v36 = v29;
        LODWORD(v40) = LastError;
        LODWORD(CLSID) = FileAttributesW;
        LODWORD(v38) = IEBrowserModeFilterSpartanMediumILPath;
        v35[0] = 1;
        v45 = GlobalThreadState();
        v44 = (struct IBindStatusCallback *)IEConfiguration_GetCLSID(268435459);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v31,
          (__int64)byte_180035279,
          v32,
          v33,
          (__int64 *)&v44,
          (__int64 *)&v45,
          (__int64)v35,
          (__int64)&v38,
          (__int64)&CLSID,
          (__int64)&v40,
          (__int64)&v36,
          (__int64)&v39);
      }
      goto LABEL_39;
    }
    IEBrowserModeFilterSpartanMediumILPath = CCVListUpdateManager::ParseVersionAndUpdateRegistry(v11);
    if ( (unsigned int)dword_18003F000 > 5 && (unsigned __int8)tlgKeywordOn(v12, 0x10000000) )
    {
      v36 = IEBrowserModeFilterSpartanMediumILPath;
      v35[0] = 1;
      CLSID = GlobalThreadState();
      v40 = IEConfiguration_GetCLSID(268435459);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
        v13,
        (__int64)&byte_180035487,
        v14,
        v15,
        &v40,
        &CLSID,
        (__int64)v35,
        (__int64)&v36);
    }
    if ( !IEBrowserModeFilterSpartanMediumILPath )
    {
      IEBrowserModeFilterSpartanMediumILPath = CCVListUpdateManager::UpdateTimeRegistry(v12);
      if ( (unsigned int)dword_18003F000 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(v12, 0x10000000) )
        {
          v36 = IEBrowserModeFilterSpartanMediumILPath;
          v35[0] = 1;
          CLSID = GlobalThreadState();
          v40 = IEConfiguration_GetCLSID(268435459);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
            v16,
            (__int64)&dword_1800353FC,
            v17,
            v18,
            &v40,
            &CLSID,
            (__int64)v35,
            (__int64)&v36);
        }
      }
    }
    LOBYTE(v19) = 0;
    v35[0] = 0;
    if ( !IEBrowserModeFilterSpartanMediumILPath )
    {
      IEBrowserModeFilterSpartanMediumILPath = CCVListUpdateManager::UpdateDownloadUrlRegistry(v12, v35);
      v19 = v35[0];
      if ( (unsigned int)dword_18003F000 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(v20, 0x10000000) )
        {
          v36 = v19;
          v39 = IEBrowserModeFilterSpartanMediumILPath;
          v35[0] = 1;
          CLSID = GlobalThreadState();
          v40 = IEConfiguration_GetCLSID(268435459);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v21,
            (__int64)word_18003534A,
            v22,
            v23,
            &v40,
            (__int64 *)&CLSID,
            (__int64)v35,
            (__int64)&v39,
            (__int64)&v36);
        }
      }
    }
    v38 = 0;
    CreateReadOnlyBrowserEmulationFilter(4, &v38);
    if ( !v38 )
    {
LABEL_39:
      ATL::CComPtrBase<CBrokerDownloadBindStatusCallback>::~CComPtrBase<CBrokerDownloadBindStatusCallback>((__int64 *)&v41);
      return IEBrowserModeFilterSpartanMediumILPath;
    }
    v24 = *(_QWORD *)v38;
    if ( v19 )
    {
      v25 = *(void (**)(void))(v24 + 48);
    }
    else
    {
      if ( (*(int (**)(void))(v24 + 64))() < 0 )
      {
LABEL_27:
        (*(void (__fastcall **)(struct IE_GLOBAL_THREAD_STATE *))(*(_QWORD *)v38 + 16LL))(v38);
        goto LABEL_39;
      }
      v25 = *(void (**)(void))(*(_QWORD *)v38 + 56LL);
    }
    v25();
    goto LABEL_27;
  }
  return IEBrowserModeFilterSpartanMediumILPath;
}

```

## disassembly

```asm
0x18000fad8  push    rbp
0x18000fada  push    rbx
0x18000fadb  push    rsi
0x18000fadc  push    rdi
0x18000fadd  push    r12
0x18000fadf  push    r13
0x18000fae1  push    r14
0x18000fae3  lea     rbp, [rsp-1430h]
0x18000faeb  mov     eax, 1530h
0x18000faf0  call    _alloca_probe
0x18000faf5  sub     rsp, rax
0x18000faf8  mov     rax, cs:__security_cookie
0x18000faff  xor     rax, rsp
0x18000fb02  mov     [rbp+1460h+var_40], rax
0x18000fb09  mov     rdi, rcx
0x18000fb0c  mov     [rbp+1460h+var_14D0], 0
0x18000fb13  mov     [rbp+1460h+var_14CC], 0
0x18000fb1a  mov     [rsp+1560h+var_1530], 0
0x18000fb23  mov     [rsp+1560h+var_1538], 0
0x18000fb2c  mov     ebx, 4
0x18000fb31  mov     dword ptr [rsp+1560h+var_1540], ebx
0x18000fb35  lea     r9, [rbp+1460h+var_14D0]
0x18000fb39  lea     r13d, [rbx-3]
0x18000fb3d  mov     r8d, r13d
0x18000fb40  mov     edx, r13d
0x18000fb43  mov     rcx, cs:?IEVALUE_BrowserEmulation_CVListXMLVersionLow@SettingStore@@3U?$VALUEID@K@1@B; SettingStore::VALUEID<ulong> const SettingStore::IEVALUE_BrowserEmulation_CVListXMLVersionLow
0x18000fb4a  call    cs:__imp_GetValue
0x18000fb50  mov     [rsp+1560h+var_1530], 0
0x18000fb59  mov     [rsp+1560h+var_1538], 0
0x18000fb62  mov     dword ptr [rsp+1560h+var_1540], ebx
0x18000fb66  lea     r9, [rbp+1460h+var_14CC]
0x18000fb6a  mov     r8d, r13d
0x18000fb6d  mov     edx, r13d
0x18000fb70  mov     rcx, cs:?IEVALUE_BrowserEmulation_CVListXMLVersionHigh@SettingStore@@3U?$VALUEID@K@1@B; SettingStore::VALUEID<ulong> const SettingStore::IEVALUE_BrowserEmulation_CVListXMLVersionHigh
0x18000fb77  call    cs:__imp_GetValue
0x18000fb7d  xor     eax, eax
0x18000fb7f  mov     [rbp+1460h+Str], ax
0x18000fb83  mov     r9d, 104h
0x18000fb89  lea     r8, [rbp+1460h+Str]
0x18000fb8d  lea     rdx, pszSubkey
0x18000fb94  mov     ecx, r13d
0x18000fb97  call    cs:__imp_GetIEBrowserModeFilterSpartanMediumILPath
0x18000fb9d  mov     ebx, eax
0x18000fb9f  mov     ecx, cs:dword_18003F000
0x18000fba5  mov     r12d, 10000000h
0x18000fbab  lea     r14d, [r12+3]
0x18000fbb0  cmp     ecx, 5
0x18000fbb3  jbe     short loc_18000FC28
0x18000fbb5  mov     edx, r12d
0x18000fbb8  call    _tlgKeywordOn
0x18000fbbd  test    al, al
0x18000fbbf  jz      short loc_18000FC28
0x18000fbc1  lea     rax, [rbp+1460h+Str]
0x18000fbc5  mov     [rbp+1460h+var_14D8], rax
0x18000fbc9  mov     [rsp+1560h+var_14FC], ebx
0x18000fbcd  mov     [rsp+1560h+var_1500], r13b
0x18000fbd2  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18000fbd8  mov     [rsp+1560h+var_14F0], rax
0x18000fbdd  mov     ecx, r14d
0x18000fbe0  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18000fbe6  mov     [rsp+1560h+var_14F8], rax
0x18000fbeb  lea     rax, [rbp+1460h+var_14D8]
0x18000fbef  mov     [rsp+1560h+var_1520], rax
0x18000fbf4  lea     rax, [rsp+1560h+var_14FC]
0x18000fbf9  mov     [rsp+1560h+var_1528], rax
0x18000fbfe  lea     rax, [rsp+1560h+var_1500]
0x18000fc03  mov     [rsp+1560h+var_1530], rax
0x18000fc08  lea     rax, [rsp+1560h+var_14F0]
0x18000fc0d  mov     [rsp+1560h+var_1538], rax
0x18000fc12  lea     rax, [rsp+1560h+var_14F8]
0x18000fc17  mov     [rsp+1560h+var_1540], rax
0x18000fc1c  lea     rdx, byte_18003551D
0x18000fc23  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18000fc28  test    ebx, ebx
0x18000fc2a  js      loc_180010023
0x18000fc30  mov     esi, 5Ch ; '\'
0x18000fc35  mov     edx, esi; Ch
0x18000fc37  lea     rcx, [rbp+1460h+Str]; Str
0x18000fc3b  call    cs:__imp_wcsrchr
0x18000fc41  mov     rbx, rax
0x18000fc44  test    rax, rax
0x18000fc47  jz      loc_18001001E
0x18000fc4d  xor     ecx, ecx; hwnd
0x18000fc4f  mov     [rax], cx
0x18000fc52  xor     r8d, r8d; psa
0x18000fc55  lea     rdx, [rbp+1460h+Str]; pszPath
0x18000fc59  call    cs:__imp_SHCreateDirectoryExW
0x18000fc5f  mov     [rbx], si
0x18000fc62  xor     eax, eax
0x18000fc64  mov     [rbp+1460h+var_1090], ax
0x18000fc6b  lea     rcx, [rbp+1460h+var_1090]
0x18000fc72  call    GetCVListDownloadUrl
0x18000fc77  lea     rcx, [rbp+1460h+var_1090]; unsigned __int16 *
0x18000fc7e  call    ?AppendPing@CCVListTelemManager@@SAJPEAGK@Z; CCVListTelemManager::AppendPing(ushort *,ulong)
0x18000fc83  test    eax, eax
0x18000fc85  jns     short loc_18000FC9C
0x18000fc87  xor     eax, eax
0x18000fc89  mov     [rbp+1460h+var_1090], ax
0x18000fc90  lea     rcx, [rbp+1460h+var_1090]
0x18000fc97  call    GetCVListDownloadUrl
0x18000fc9c  mov     [rbp+1460h+var_14D8], 0
0x18000fca4  mov     ecx, 30h ; '0'; Size
0x18000fca9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fcae  mov     rbx, rax
0x18000fcb1  mov     [rbp+1460h+var_14C8], rax
0x18000fcb5  mov     edx, [rdi]; unsigned int
0x18000fcb7  mov     rcx, rax; this
0x18000fcba  call    ??0CBrokerDownloadBindStatusCallback@@QEAA@K@Z; CBrokerDownloadBindStatusCallback::CBrokerDownloadBindStatusCallback(ulong)
0x18000fcbf  lea     rax, ??_7CCVListDownloadCallback@@6B?$TUnknownSTBaseFRE@D@@@; const CCVListDownloadCallback::`vftable'{for `TUnknownSTBaseFRE<char>'}
0x18000fcc6  mov     [rbx], rax
0x18000fcc9  lea     r9, [rbx+10h]; struct IBindStatusCallback *
0x18000fccd  lea     rax, ??_7CCVListDownloadCallback@@6BIBindStatusCallback@@@; const CCVListDownloadCallback::`vftable'{for `IBindStatusCallback'}
0x18000fcd4  mov     [r9], rax
0x18000fcd7  mov     [rbx+28h], rdi
0x18000fcdb  mov     [rbp+1460h+var_14D8], rbx
0x18000fcdf  lea     rdx, [rbp+1460h+ExistingFileName]; unsigned __int16 *
0x18000fce6  lea     rcx, [rbp+1460h+var_1090]; LPCWSTR
0x18000fced  call    ?DownloadToTempFile@@YAJPEBGPEAGKPEAUIBindStatusCallback@@@Z; DownloadToTempFile(ushort const *,ushort *,ulong,IBindStatusCallback *)
0x18000fcf2  mov     ebx, eax
0x18000fcf4  test    eax, eax
0x18000fcf6  jnz     loc_180010013
0x18000fcfc  lea     r8d, [rax+3]; dwFlags
0x18000fd00  lea     rdx, [rbp+1460h+Str]; lpNewFileName
0x18000fd04  lea     rcx, [rbp+1460h+ExistingFileName]; lpExistingFileName
0x18000fd0b  call    cs:__imp_MoveFileExW
0x18000fd11  test    eax, eax
0x18000fd13  jz      loc_18000FF04
0x18000fd19  call    ?ParseVersionAndUpdateRegistry@CCVListUpdateManager@@AEAAJXZ; CCVListUpdateManager::ParseVersionAndUpdateRegistry(void)
0x18000fd1e  mov     ebx, eax
0x18000fd20  mov     eax, cs:dword_18003F000
0x18000fd26  cmp     eax, 5
0x18000fd29  jbe     short loc_18000FD8B
0x18000fd2b  mov     rdx, r12
0x18000fd2e  call    _tlgKeywordOn
0x18000fd33  test    al, al
0x18000fd35  jz      short loc_18000FD8B
0x18000fd37  mov     [rsp+1560h+var_14FC], ebx
0x18000fd3b  mov     [rsp+1560h+var_1500], r13b
0x18000fd40  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18000fd46  mov     [rsp+1560h+var_14F8], rax
0x18000fd4b  mov     ecx, r14d
0x18000fd4e  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18000fd54  mov     [rbp+1460h+var_14E0], rax
0x18000fd58  lea     rax, [rsp+1560h+var_14FC]
0x18000fd5d  mov     [rsp+1560h+var_1528], rax
0x18000fd62  lea     rax, [rsp+1560h+var_1500]
0x18000fd67  mov     [rsp+1560h+var_1530], rax
0x18000fd6c  lea     rax, [rsp+1560h+var_14F8]
0x18000fd71  mov     [rsp+1560h+var_1538], rax
0x18000fd76  lea     rax, [rbp+1460h+var_14E0]
0x18000fd7a  mov     [rsp+1560h+var_1540], rax
0x18000fd7f  lea     rdx, byte_180035487
0x18000fd86  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x18000fd8b  test    ebx, ebx
0x18000fd8d  jnz     short loc_18000FE01
0x18000fd8f  call    ?UpdateTimeRegistry@CCVListUpdateManager@@AEAAJXZ; CCVListUpdateManager::UpdateTimeRegistry(void)
0x18000fd94  mov     ebx, eax
0x18000fd96  mov     eax, cs:dword_18003F000
0x18000fd9c  cmp     eax, 5
0x18000fd9f  jbe     short loc_18000FE01
0x18000fda1  mov     rdx, r12
0x18000fda4  call    _tlgKeywordOn
0x18000fda9  test    al, al
0x18000fdab  jz      short loc_18000FE01
0x18000fdad  mov     [rsp+1560h+var_14FC], ebx
0x18000fdb1  mov     [rsp+1560h+var_1500], r13b
0x18000fdb6  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18000fdbc  mov     [rsp+1560h+var_14F8], rax
0x18000fdc1  mov     ecx, r14d
0x18000fdc4  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18000fdca  mov     [rbp+1460h+var_14E0], rax
0x18000fdce  lea     rax, [rsp+1560h+var_14FC]
0x18000fdd3  mov     [rsp+1560h+var_1528], rax
0x18000fdd8  lea     rax, [rsp+1560h+var_1500]
0x18000fddd  mov     [rsp+1560h+var_1530], rax
0x18000fde2  lea     rax, [rsp+1560h+var_14F8]
0x18000fde7  mov     [rsp+1560h+var_1538], rax
0x18000fdec  lea     rax, [rbp+1460h+var_14E0]
0x18000fdf0  mov     [rsp+1560h+var_1540], rax
0x18000fdf5  lea     rdx, dword_1800353FC
0x18000fdfc  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x18000fe01  xor     dil, dil
0x18000fe04  mov     [rsp+1560h+var_1500], dil
0x18000fe09  test    ebx, ebx
0x18000fe0b  jnz     loc_18000FE9B
0x18000fe11  lea     rdx, [rsp+1560h+var_1500]; bool *
0x18000fe16  call    ?UpdateDownloadUrlRegistry@CCVListUpdateManager@@AEAAJAEA_N@Z; CCVListUpdateManager::UpdateDownloadUrlRegistry(bool &)
0x18000fe1b  mov     ebx, eax
0x18000fe1d  mov     eax, cs:dword_18003F000
0x18000fe23  movzx   edi, [rsp+1560h+var_1500]
0x18000fe28  cmp     eax, 5
0x18000fe2b  jbe     short loc_18000FE9B
0x18000fe2d  mov     rdx, r12
0x18000fe30  call    _tlgKeywordOn
0x18000fe35  test    al, al
0x18000fe37  jz      short loc_18000FE9B
0x18000fe39  mov     [rsp+1560h+var_14FC], edi
0x18000fe3d  mov     [rsp+1560h+var_14E8], ebx
0x18000fe41  mov     [rsp+1560h+var_1500], r13b
0x18000fe46  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18000fe4c  mov     [rsp+1560h+var_14F8], rax
0x18000fe51  mov     ecx, r14d
0x18000fe54  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18000fe5a  mov     [rbp+1460h+var_14E0], rax
0x18000fe5e  lea     rax, [rsp+1560h+var_14FC]
0x18000fe63  mov     [rsp+1560h+var_1520], rax
0x18000fe68  lea     rax, [rsp+1560h+var_14E8]
0x18000fe6d  mov     [rsp+1560h+var_1528], rax
0x18000fe72  lea     rax, [rsp+1560h+var_1500]
0x18000fe77  mov     [rsp+1560h+var_1530], rax
0x18000fe7c  lea     rax, [rsp+1560h+var_14F8]
0x18000fe81  mov     [rsp+1560h+var_1538], rax
0x18000fe86  lea     rax, [rbp+1460h+var_14E0]
0x18000fe8a  mov     [rsp+1560h+var_1540], rax
0x18000fe8f  lea     rdx, word_18003534A
0x18000fe96  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000fe9b  mov     [rsp+1560h+var_14F0], 0
0x18000fea4  lea     rdx, [rsp+1560h+var_14F0]
0x18000fea9  mov     ecx, 4
0x18000feae  call    cs:__imp_CreateReadOnlyBrowserEmulationFilter
0x18000feb4  mov     rcx, [rsp+1560h+var_14F0]
0x18000feb9  test    rcx, rcx
0x18000febc  jz      loc_180010013
0x18000fec2  mov     rax, [rcx]
0x18000fec5  test    dil, dil
0x18000fec8  jz      short loc_18000FED0
0x18000feca  mov     rax, [rax+30h]
0x18000fece  jmp     short loc_18000FEE9
0x18000fed0  mov     rax, [rax+40h]
0x18000fed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fed9  test    eax, eax
0x18000fedb  js      short loc_18000FEEE
0x18000fedd  mov     rcx, [rsp+1560h+var_14F0]
0x18000fee2  mov     rax, [rcx]
0x18000fee5  mov     rax, [rax+38h]
0x18000fee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000feee  mov     rcx, [rsp+1560h+var_14F0]
0x18000fef3  mov     rax, [rcx]
0x18000fef6  mov     rax, [rax+10h]
0x18000fefa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000feff  jmp     loc_180010013
0x18000ff04  call    cs:__imp_GetLastError
0x18000ff0a  test    eax, eax
0x18000ff0c  jg      short loc_18000FF18
0x18000ff0e  call    cs:__imp_GetLastError
0x18000ff14  mov     ebx, eax
0x18000ff16  jmp     short loc_18000FF27
0x18000ff18  call    cs:__imp_GetLastError
0x18000ff1e  movzx   ebx, ax
0x18000ff21  or      ebx, 80070000h
0x18000ff27  lea     rcx, [rbp+1460h+ExistingFileName]; lpFileName
0x18000ff2e  call    cs:__imp_GetFileAttributesW
0x18000ff34  mov     esi, eax
0x18000ff36  cmp     eax, 0FFFFFFFFh
0x18000ff39  jnz     short loc_18000FF45
0x18000ff3b  call    cs:__imp_GetLastError
0x18000ff41  mov     edi, eax
0x18000ff43  jmp     short loc_18000FF47
0x18000ff45  xor     edi, edi
0x18000ff47  lea     rcx, [rbp+1460h+Str]; lpFileName
0x18000ff4b  call    cs:__imp_GetFileAttributesW
0x18000ff51  mov     r14d, eax
0x18000ff54  cmp     eax, 0FFFFFFFFh
0x18000ff57  jnz     short loc_18000FF64
0x18000ff59  call    cs:__imp_GetLastError
0x18000ff5f  mov     r8d, eax
0x18000ff62  jmp     short loc_18000FF67
0x18000ff64  xor     r8d, r8d
0x18000ff67  mov     eax, cs:dword_18003F000
0x18000ff6d  cmp     eax, 5
0x18000ff70  jbe     loc_180010013
0x18000ff76  mov     rdx, r12
0x18000ff79  call    _tlgKeywordOn
0x18000ff7e  test    al, al
0x18000ff80  jz      loc_180010013
0x18000ff86  mov     [rsp+1560h+var_14E8], r8d
0x18000ff8b  mov     [rsp+1560h+var_14FC], r14d
0x18000ff90  mov     dword ptr [rbp+1460h+var_14E0], edi
0x18000ff93  mov     dword ptr [rsp+1560h+var_14F8], esi
0x18000ff97  mov     dword ptr [rsp+1560h+var_14F0], ebx
0x18000ff9b  mov     [rsp+1560h+var_1500], r13b
0x18000ffa0  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18000ffa6  mov     [rbp+1460h+var_14C0], rax
0x18000ffaa  mov     ecx, 10000003h
0x18000ffaf  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18000ffb5  mov     [rbp+1460h+var_14C8], rax
0x18000ffb9  lea     rax, [rsp+1560h+var_14E8]
0x18000ffbe  mov     [rsp+1560h+var_1508], rax
0x18000ffc3  lea     rax, [rsp+1560h+var_14FC]
0x18000ffc8  mov     [rsp+1560h+var_1510], rax
0x18000ffcd  lea     rax, [rbp+1460h+var_14E0]
0x18000ffd1  mov     [rsp+1560h+var_1518], rax
0x18000ffd6  lea     rax, [rsp+1560h+var_14F8]
0x18000ffdb  mov     [rsp+1560h+var_1520], rax
0x18000ffe0  lea     rax, [rsp+1560h+var_14F0]
0x18000ffe5  mov     [rsp+1560h+var_1528], rax
0x18000ffea  lea     rax, [rsp+1560h+var_1500]
0x18000ffef  mov     [rsp+1560h+var_1530], rax
0x18000fff4  lea     rax, [rbp+1460h+var_14C0]
0x18000fff8  mov     [rsp+1560h+var_1538], rax
  ... truncated ...
```
