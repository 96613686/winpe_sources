# AppActivation::ActivateExtensionWithRawExe(ActivateType,Windows::ApplicationModel::Activation::IActivatedEventArgs *,Windows::ApplicationModel::Core::IActivatableApplication * *)

- ea: `0x180042ca8`
- end: `0x180043574`
- name: `?ActivateExtensionWithRawExe@AppActivation@@AEAAJW4ActivateType@@PEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@PEAPEAUIActivatableApplication@Core@56@@Z`
- size: `2252`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800300c0`

## callees

- `0x18000b5c0`
- `0x18000cbc0`
- `0x180010514`
- `0x180011328`
- `0x180027ce8`
- `0x180042ca8`
- `0x18004357c`
- `0x1800435b0`
- `0x18004361c`
- `0x1800445ac`
- `0x18004498c`
- `0x180044a14`
- `0x18004d174`
- `0x18005697c`
- `0x18005ae90`
- `0x18005b33c`
- `0x18005ba40`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180042dac`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180042dac`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180042fec`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180042fec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042df9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042ede`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042f69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042fb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042df9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042ede`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042f69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042fb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042e34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042e49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800431ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043384`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042e34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042e49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800431ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043384`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180042d3b`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180042d3b`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
int __fastcall AppActivation::ActivateExtensionWithRawExe(
        __int64 a1,
        int a2,
        int (__fastcall ***a3)(_QWORD, GUID *, __int64 *),
        const char *a4)
{
  const char *v4; // rsi
  int v6; // r13d
  const unsigned __int16 **v8; // r12
  unsigned int v9; // eax
  unsigned __int16 *v11; // r14
  AppActivation *v12; // rcx
  int (__fastcall *v13)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rbx
  int v16; // eax
  int v17; // ebx
  __int64 v18; // r9
  __int64 v19; // rdx
  PCWSTR StringRawBuffer; // rsi
  PCWSTR v21; // rdi
  unsigned __int64 v22; // rbx
  _QWORD *unique; // rax
  const struct std::nothrow_t *v24; // rdx
  void *v25; // rcx
  __int64 v26; // rdx
  const struct std::nothrow_t *v27; // rdx
  unsigned __int64 v28; // rbx
  _QWORD *v29; // rax
  const struct std::nothrow_t *v30; // rdx
  void *v31; // rcx
  HRESULT v32; // eax
  SwitchToDesktopImpl **v33; // rax
  void *v34; // rcx
  HANDLE v35; // rsi
  __int64 (__fastcall *v36)(HANDLE, GUID *, HSTRING *); // rbx
  int v37; // eax
  LPVOID v38; // rbx
  __int64 (__fastcall *v39)(LPVOID, GUID *, UINT32 *); // rdi
  int v40; // eax
  int v41; // eax
  LPVOID v42; // rdi
  __int64 (__fastcall *v43)(LPVOID, _QWORD, PCWSTR, unsigned __int16 *); // rbx
  PCWSTR v44; // rax
  int v45; // eax
  int v46; // eax
  int IsBnoIsolationEnabled; // eax
  unsigned int v48; // r13d
  unsigned __int64 v49; // rbx
  unsigned __int64 v50; // rdi
  const unsigned __int16 *v51; // rsi
  const unsigned __int16 *v52; // rax
  unsigned int v53; // r9d
  unsigned int v54; // eax
  int v55; // eax
  const struct std::nothrow_t *v56; // rdx
  __int64 v57; // rdi
  __int64 (__fastcall *v58)(__int64, _QWORD, _QWORD, const unsigned __int16 *); // rbx
  int v59; // eax
  __int64 v60; // rdx
  unsigned int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *bIgnoreCasec; // [rsp+20h] [rbp-E0h]
  unsigned int bIgnoreCased; // [rsp+20h] [rbp-E0h]
  BOOL bIgnoreCasee[2]; // [rsp+20h] [rbp-E0h]
  HWND v67; // [rsp+40h] [rbp-C0h]
  void *v68; // [rsp+50h] [rbp-B0h]
  HSTRING string; // [rsp+80h] [rbp-80h] BYREF
  bool v70; // [rsp+88h] [rbp-78h] BYREF
  bool v71[7]; // [rsp+89h] [rbp-77h] BYREF
  __int64 v72; // [rsp+90h] [rbp-70h] BYREF
  LPVOID ppv; // [rsp+98h] [rbp-68h] BYREF
  UINT32 length[2]; // [rsp+A0h] [rbp-60h] BYREF
  UINT32 v75[2]; // [rsp+A8h] [rbp-58h] BYREF
  void *hThread; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD **hProcess; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v78; // [rsp+C0h] [rbp-40h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+C8h] [rbp-38h] BYREF
  const char *v80; // [rsp+D0h] [rbp-30h]
  struct _PROCESS_INFORMATION v81; // [rsp+D8h] [rbp-28h] BYREF
  struct _STARTUPINFOW v82; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+160h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v4 = a4;
  v80 = a4;
  v6 = a2;
  LODWORD(ppv) = a2;
  *(_QWORD *)a4 = 0;
  if ( a2 == 1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x31D,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      a4);
  if ( (unsigned __int64)(*(_QWORD *)(a1 + 256) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v8 = (const unsigned __int16 **)(a1 + 16);
    goto LABEL_77;
  }
  packageFamilyNameLength = 65;
  v9 = PackageFamilyNameFromFullName(*(PCWSTR *)(a1 + 32), &packageFamilyNameLength, packageFamilyName);
  if ( v9 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x325,
             (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
             (const char *)v9,
             bIgnoreCase);
  memset(&v81, 0, sizeof(v81));
  memset_0(&v82.cb + 1, 0, 0x64u);
  v82.cb = 104;
  v11 = 0;
  v78 = 0;
  v72 = 0;
  if ( CompareStringOrdinal(*(LPCWCH *)(a1 + 24), -1, L"Windows.Launch", -1, 1) == 2 )
  {
    v13 = **a3;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v72);
    if ( v13(a3, &GUID_fbc93e26_a14a_4b4f_82b0_33bed920af52, &v72) >= 0 )
    {
      string = 0;
      v14 = v72;
      v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v72 + 48LL);
      WindowsDeleteString(0);
      string = 0;
      v16 = v15(v14, &string);
      v17 = v16;
      if ( v16 < 0 )
      {
        v18 = (unsigned int)v16;
        v19 = 820;
LABEL_26:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
          (const char *)v18,
          bIgnoreCasea);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v72);
        return v17;
      }
      length[0] = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 136), length);
      v75[0] = 0;
      v21 = WindowsGetStringRawBuffer(string, v75);
      if ( v6 == 3 )
      {
        v22 = v75[0] + 1;
        unique = wil::make_unique_nothrow<unsigned short [0]>(&hThread, v22);
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(&v78, unique);
        v25 = hThread;
        hThread = 0;
        if ( v25 )
          operator delete(v25, v24);
        v11 = v78;
        if ( !v78 )
        {
          v19 = 834;
LABEL_25:
          v17 = -2147024882;
          v18 = 2147942414LL;
          goto LABEL_26;
        }
        v17 = StringCchPrintfW(v78, v22, L"%s", v21);
        if ( v17 < 0 )
        {
          v26 = 836;
LABEL_18:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v26,
            (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
            (const char *)(unsigned int)v17,
            bIgnoreCasea);
          WindowsDeleteString(string);
          string = 0;
          goto LABEL_19;
        }
      }
      else
      {
        v28 = v75[0] + 4 + length[0];
        v29 = wil::make_unique_nothrow<unsigned short [0]>(&hThread, v28);
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(&v78, v29);
        v31 = hThread;
        hThread = 0;
        if ( v31 )
          operator delete(v31, v30);
        v11 = v78;
        if ( !v78 )
        {
          v19 = 843;
          goto LABEL_25;
        }
        bIgnoreCasea = (int)v21;
        v17 = StringCchPrintfW(v78, v28, L"\"%s\" %s", StringRawBuffer);
        if ( v17 < 0 )
        {
          v26 = 845;
          goto LABEL_18;
        }
      }
      WindowsDeleteString(string);
    }
  }
  if ( v6 != 3 )
  {
    v70 = 0;
    v71[0] = 0;
    v8 = (const unsigned __int16 **)(a1 + 16);
    IsBnoIsolationEnabled = AppActivation::GetIsFullTrustUWPApplicationAndIsBnoIsolationEnabled(
                              v12,
                              *(const unsigned __int16 **)(a1 + 16),
                              *(const unsigned __int16 **)(a1 + 24),
                              &v70,
                              v71);
    v17 = IsBnoIsolationEnabled;
    if ( IsBnoIsolationEnabled >= 0 )
    {
      if ( v70 )
      {
        v48 = 4128;
        if ( v71[0] )
          v48 = 12320;
      }
      else
      {
        v48 = 4256;
      }
      v49 = *(_QWORD *)(a1 + 64);
      v50 = *(_QWORD *)(a1 + 80);
      v51 = *v8;
      v52 = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 136), 0);
      v54 = AicLaunchProcessWithIdentity(
              v52,
              v11,
              (unsigned int)&v81,
              v53,
              bIgnoreCasec,
              &v82,
              packageFamilyName,
              v51,
              v67,
              v48,
              v68,
              v50,
              (unsigned __int64 *)(a1 + 72),
              (struct _GUID *)(a1 + 48),
              v49,
              &v81);
      if ( v54 )
      {
        v17 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x38A,
                (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
                (const char *)v54,
                bIgnoreCased);
      }
      else
      {
        hThread = v81.hThread;
        hProcess = (_QWORD **)v81.hProcess;
        v55 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
        v17 = v55;
        if ( v55 >= 0 )
        {
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hThread);
          v6 = (int)ppv;
          goto LABEL_74;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x38D,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
          (const char *)(unsigned int)v55,
          bIgnoreCased);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hThread);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x371,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
        (const char *)(unsigned int)IsBnoIsolationEnabled,
        (int)bIgnoreCasec);
    }
LABEL_19:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v72);
    if ( v11 )
      operator delete(v11, v27);
    return v17;
  }
  ppv = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
  v32 = CoCreateInstance(
          &GUID_168eb462_775f_42ae_9111_d714b2306c2e,
          0,
          1u,
          &GUID_f158268a_d5a5_45ce_99cf_00d6c3f3fc0a,
          &ppv);
  v17 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x354,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)(unsigned int)v32,
      bIgnoreCaseb);
LABEL_34:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
    goto LABEL_19;
  }
  *(_QWORD *)length = 0;
  string = 0;
  hProcess = 0;
  v33 = Microsoft::WRL::Details::Make<SwitchToDesktopImpl,>((SwitchToDesktopImpl **)&hThread);
  Microsoft::WRL::ComPtr<SwitchToDesktopImpl>::operator=(&hProcess, v33);
  v34 = hThread;
  if ( hThread )
  {
    hThread = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v34 + 16LL))(v34);
  }
  v35 = hProcess;
  if ( !hProcess )
  {
    v17 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35C,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)0x8007000ELL,
      bIgnoreCaseb);
LABEL_39:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&string);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(length);
    goto LABEL_34;
  }
  v36 = (__int64 (__fastcall *)(HANDLE, GUID *, HSTRING *))**hProcess;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&string);
  v37 = v36(v35, &GUID_00000000_0000_0000_c000_000000000046, &string);
  v17 = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35D,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)(unsigned int)v37,
      bIgnoreCaseb);
    if ( v35 )
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v35 + 16LL))(v35);
    goto LABEL_39;
  }
  *(_QWORD *)v75 = 0;
  v38 = ppv;
  v39 = **(__int64 (__fastcall ***)(LPVOID, GUID *, UINT32 *))ppv;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v75);
  v40 = v39(v38, &GUID_fc4801a3_2ba9_11cf_a229_00aa003d7352, v75);
  v17 = v40;
  if ( v40 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35F,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)(unsigned int)v40,
      bIgnoreCaseb);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v75);
    if ( v35 )
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v35 + 16LL))(v35);
    goto LABEL_39;
  }
  v41 = (*(__int64 (__fastcall **)(_QWORD, HSTRING))(**(_QWORD **)v75 + 24LL))(*(_QWORD *)v75, string);
  v17 = v41;
  if ( v41 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x360,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)(unsigned int)v41,
      bIgnoreCaseb);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v75);
    if ( v35 )
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v35 + 16LL))(v35);
    goto LABEL_39;
  }
  v42 = ppv;
  v43 = *(__int64 (__fastcall **)(LPVOID, _QWORD, PCWSTR, unsigned __int16 *))(*(_QWORD *)ppv + 32LL);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    length,
    0);
  v44 = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 136), 0);
  v8 = (const unsigned __int16 **)(a1 + 16);
  v45 = v43(v42, *(_QWORD *)(a1 + 16), v44, v11);
  v17 = v45;
  if ( v45 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x366,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)(unsigned int)v45,
      4928);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v75);
    if ( v35 )
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v35 + 16LL))(v35);
    goto LABEL_39;
  }
  v46 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, *(_QWORD *)length);
  v17 = v46;
  if ( v46 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x367,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)(unsigned int)v46,
      4928);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v75);
    if ( v35 )
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v35 + 16LL))(v35);
    goto LABEL_39;
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v75);
  if ( v35 )
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v35 + 16LL))(v35);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&string);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(length);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
LABEL_74:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v72);
  if ( v11 )
    operator delete(v11, v56);
  v4 = v80;
LABEL_77:
  if ( ((v6 - 2) & 0xFFFFFFFD) == 0 )
  {
    string = 0;
    v57 = AppActivation::s_activatableApplicationStore;
    v58 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, const unsigned __int16 *))(*(_QWORD *)AppActivation::s_activatableApplicationStore
                                                                                      + 32LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&string);
    *(_QWORD *)bIgnoreCasee = *(_QWORD *)(a1 + 72);
    v59 = v58(v57, *(_QWORD *)(a1 + 256), *(_QWORD *)(a1 + 80), *v8);
    v17 = v59;
    if ( v59 < 0 )
    {
      v60 = 916;
LABEL_82:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v60,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
        (const char *)(unsigned int)v59,
        bIgnoreCasee[0]);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&string);
      return v17;
    }
    v59 = (**(__int64 (__fastcall ***)(HSTRING, GUID *, const char *))string)(
            string,
            &GUID_92696c00_7578_48e1_ac1a_2ca909e2c8cf,
            v4);
    v17 = v59;
    if ( v59 < 0 )
    {
      v60 = 917;
      goto LABEL_82;
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&string);
  }
  return 0;
}

```

## disassembly

```asm
0x180042ca8  mov     [rsp-8+arg_8], rbx
0x180042cad  push    rbp
0x180042cae  push    rsi
0x180042caf  push    rdi
0x180042cb0  push    r12
0x180042cb2  push    r13
0x180042cb4  push    r14
0x180042cb6  push    r15
0x180042cb8  lea     rbp, [rsp-100h]
0x180042cc0  sub     rsp, 200h
0x180042cc7  mov     rax, cs:__security_cookie
0x180042cce  xor     rax, rsp
0x180042cd1  mov     [rbp+130h+var_40], rax
0x180042cd8  mov     rsi, r9
0x180042cdb  mov     [rbp+130h+var_160], r9
0x180042cdf  mov     rdi, r8
0x180042ce2  mov     r13d, edx
0x180042ce5  mov     dword ptr [rbp+130h+ppv], edx
0x180042ce8  mov     r15, rcx
0x180042ceb  xor     r12d, r12d
0x180042cee  mov     [r9], r12
0x180042cf1  mov     rcx, [rbp+138h]; this
0x180042cf8  cmp     edx, 1
0x180042cfb  jnz     short loc_180042D0F
0x180042cfd  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180042d04  mov     edx, 31Dh; void *
0x180042d09  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180042d0f  mov     rax, [r15+100h]
0x180042d16  dec     rax
0x180042d19  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180042d1d  ja      short loc_180042D28
0x180042d1f  lea     r12, [r15+10h]
0x180042d23  jmp     loc_180043487
0x180042d28  mov     [rbp+130h+packageFamilyNameLength], 41h ; 'A'
0x180042d2f  lea     r8, [rbp+130h+packageFamilyName]; packageFamilyName
0x180042d33  lea     rdx, [rbp+130h+packageFamilyNameLength]; packageFamilyNameLength
0x180042d37  mov     rcx, [r15+20h]; packageFullName
0x180042d3b  call    cs:__imp_PackageFamilyNameFromFullName
0x180042d41  test    eax, eax
0x180042d43  jz      short loc_180042D65
0x180042d45  mov     rcx, [rbp+138h]; this
0x180042d4c  mov     r9d, eax; char *
0x180042d4f  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180042d56  mov     edx, 325h; void *
0x180042d5b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180042d60  jmp     loc_18004354A
0x180042d65  xorps   xmm0, xmm0
0x180042d68  xor     eax, eax
0x180042d6a  movups  xmmword ptr [rbp+130h+var_158.hProcess], xmm0
0x180042d6e  mov     qword ptr [rbp+130h+var_158.dwProcessId], rax
0x180042d72  xor     edx, edx; Val
0x180042d74  lea     r8d, [rax+64h]; Size
0x180042d78  lea     rcx, [rbp+130h+var_140+4]; void *
0x180042d7c  call    memset_0
0x180042d81  mov     [rbp+130h+var_140.cb], 68h ; 'h'
0x180042d88  mov     r14, r12
0x180042d8b  mov     [rbp+130h+var_170], r12
0x180042d8f  mov     [rbp+130h+var_1A0], r12
0x180042d93  mov     [rsp+230h+bIgnoreCase], 1; int
0x180042d9b  or      edx, 0FFFFFFFFh; cchCount1
0x180042d9e  mov     r9d, edx; cchCount2
0x180042da1  lea     r8, String2; "Windows.Launch"
0x180042da8  mov     rcx, [r15+18h]; lpString1
0x180042dac  call    cs:__imp_CompareStringOrdinal
0x180042db2  cmp     eax, 2
0x180042db5  jnz     loc_180042FB8
0x180042dbb  mov     rax, [rdi]
0x180042dbe  mov     rbx, [rax]
0x180042dc1  lea     rcx, [rbp+130h+var_1A0]
0x180042dc5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180042dca  lea     r8, [rbp+130h+var_1A0]
0x180042dce  lea     rdx, _GUID_fbc93e26_a14a_4b4f_82b0_33bed920af52
0x180042dd5  mov     rcx, rdi
0x180042dd8  mov     rax, rbx
0x180042ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042de0  test    eax, eax
0x180042de2  js      loc_180042FB8
0x180042de8  mov     [rbp+130h+string], r12
0x180042dec  mov     rdi, [rbp+130h+var_1A0]
0x180042df0  mov     rax, [rdi]
0x180042df3  mov     rbx, [rax+30h]
0x180042df7  xor     ecx, ecx; string
0x180042df9  call    cs:__imp_WindowsDeleteString
0x180042dff  mov     [rbp+130h+string], r12
0x180042e03  lea     rdx, [rbp+130h+string]
0x180042e07  mov     rcx, rdi
0x180042e0a  mov     rax, rbx
0x180042e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e12  mov     ebx, eax
0x180042e14  test    eax, eax
0x180042e16  jns     short loc_180042E25
0x180042e18  mov     r9d, eax
0x180042e1b  mov     edx, 334h
0x180042e20  jmp     loc_180042F51
0x180042e25  mov     [rbp+130h+length], r12d
0x180042e29  lea     rdx, [rbp+130h+length]; length
0x180042e2d  mov     rcx, [r15+88h]; string
0x180042e34  call    cs:__imp_WindowsGetStringRawBuffer
0x180042e3a  mov     rsi, rax
0x180042e3d  mov     [rbp+130h+var_188], r12d
0x180042e41  lea     rdx, [rbp+130h+var_188]; length
0x180042e45  mov     rcx, [rbp+130h+string]; string
0x180042e49  call    cs:__imp_WindowsGetStringRawBuffer
0x180042e4f  mov     rdi, rax
0x180042e52  cmp     r13d, 3
0x180042e56  jnz     loc_180042F05
0x180042e5c  mov     ecx, [rbp+130h+var_188]
0x180042e5f  inc     ecx
0x180042e61  mov     ebx, ecx
0x180042e63  mov     edx, ecx
0x180042e65  lea     rcx, [rbp+130h+var_180]
0x180042e69  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180042e6e  mov     rdx, rax
0x180042e71  lea     rcx, [rbp+130h+var_170]
0x180042e75  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180042e7a  mov     rcx, [rbp+130h+var_180]; void *
0x180042e7e  mov     [rbp+130h+var_180], r12
0x180042e82  test    rcx, rcx
0x180042e85  jz      short loc_180042E8C
0x180042e87  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180042e8c  mov     r14, [rbp+130h+var_170]
0x180042e90  test    r14, r14
0x180042e93  jnz     short loc_180042E9F
0x180042e95  mov     edx, 342h
0x180042e9a  jmp     loc_180042F49
0x180042e9f  mov     r9, rdi
0x180042ea2  lea     r8, aS; "%s"
0x180042ea9  mov     rdx, rbx; unsigned __int64
0x180042eac  mov     rcx, r14; unsigned __int16 *
0x180042eaf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180042eb4  mov     ebx, eax
0x180042eb6  test    eax, eax
0x180042eb8  jns     loc_180042FAE
0x180042ebe  mov     edx, 344h; void *
0x180042ec3  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180042eca  mov     r9d, ebx; char *
0x180042ecd  mov     rcx, [rbp+138h]; this
0x180042ed4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042ed9  nop
0x180042eda  mov     rcx, [rbp+130h+string]; string
0x180042ede  call    cs:__imp_WindowsDeleteString
0x180042ee4  mov     [rbp+130h+string], r12
0x180042ee8  lea     rcx, [rbp+130h+var_1A0]
0x180042eec  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180042ef1  nop
0x180042ef2  test    r14, r14
0x180042ef5  jz      loc_180042F7D
0x180042efb  mov     rcx, r14; void *
0x180042efe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180042f03  jmp     short loc_180042F7D
0x180042f05  mov     ecx, [rbp+130h+length]
0x180042f08  mov     eax, [rbp+130h+var_188]
0x180042f0b  add     eax, 4
0x180042f0e  add     ecx, eax
0x180042f10  mov     ebx, ecx
0x180042f12  mov     edx, ecx
0x180042f14  lea     rcx, [rbp+130h+var_180]
0x180042f18  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180042f1d  mov     rdx, rax
0x180042f20  lea     rcx, [rbp+130h+var_170]
0x180042f24  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180042f29  mov     rcx, [rbp+130h+var_180]; void *
0x180042f2d  mov     [rbp+130h+var_180], r12
0x180042f31  test    rcx, rcx
0x180042f34  jz      short loc_180042F3B
0x180042f36  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180042f3b  mov     r14, [rbp+130h+var_170]
0x180042f3f  test    r14, r14
0x180042f42  jnz     short loc_180042F84
0x180042f44  mov     edx, 34Bh; void *
0x180042f49  mov     ebx, 8007000Eh
0x180042f4e  mov     r9d, ebx; char *
0x180042f51  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180042f58  mov     rcx, [rbp+138h]; this
0x180042f5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042f64  nop
0x180042f65  mov     rcx, [rbp+130h+string]; string
0x180042f69  call    cs:__imp_WindowsDeleteString
0x180042f6f  mov     [rbp+130h+string], r12
0x180042f73  lea     rcx, [rbp+130h+var_1A0]
0x180042f77  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180042f7c  nop
0x180042f7d  mov     eax, ebx
0x180042f7f  jmp     loc_18004354A
0x180042f84  mov     qword ptr [rsp+230h+bIgnoreCase], rdi
0x180042f89  mov     r9, rsi
0x180042f8c  lea     r8, aSS; "\"%s\" %s"
0x180042f93  mov     rdx, rbx; unsigned __int64
0x180042f96  mov     rcx, r14; unsigned __int16 *
0x180042f99  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180042f9e  mov     ebx, eax
0x180042fa0  test    eax, eax
0x180042fa2  jns     short loc_180042FAE
0x180042fa4  mov     edx, 34Dh
0x180042fa9  jmp     loc_180042EC3
0x180042fae  mov     rcx, [rbp+130h+string]; string
0x180042fb2  call    cs:__imp_WindowsDeleteString
0x180042fb8  cmp     r13d, 3
0x180042fbc  jnz     loc_180043302
0x180042fc2  mov     [rbp+130h+ppv], r12
0x180042fc6  lea     rcx, [rbp+130h+ppv]
0x180042fca  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180042fcf  lea     rax, [rbp+130h+ppv]
0x180042fd3  mov     qword ptr [rsp+230h+bIgnoreCase], rax; int
0x180042fd8  lea     r9, _GUID_f158268a_d5a5_45ce_99cf_00d6c3f3fc0a; riid
0x180042fdf  xor     edx, edx; pUnkOuter
0x180042fe1  lea     r8d, [r13-2]; dwClsContext
0x180042fe5  lea     rcx, _GUID_168eb462_775f_42ae_9111_d714b2306c2e; rclsid
0x180042fec  call    cs:__imp_CoCreateInstance
0x180042ff2  mov     ebx, eax
0x180042ff4  test    eax, eax
0x180042ff6  jns     short loc_180043022
0x180042ff8  mov     rcx, [rbp+138h]; this
0x180042fff  mov     r9d, eax; char *
0x180043002  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180043009  mov     edx, 354h; void *
0x18004300e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043013  nop
0x180043014  lea     rcx, [rbp+130h+ppv]
0x180043018  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004301d  jmp     loc_180042EE8
0x180043022  mov     qword ptr [rbp+130h+length], r12
0x180043026  mov     [rbp+130h+string], r12
0x18004302a  mov     [rbp+130h+var_178], r12
0x18004302e  lea     rcx, [rbp+130h+var_180]
0x180043032  call    ??$Make@VSwitchToDesktopImpl@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VSwitchToDesktopImpl@@@12@XZ; Microsoft::WRL::Details::Make<SwitchToDesktopImpl,>(void)
0x180043037  mov     rdx, rax
0x18004303a  lea     rcx, [rbp+130h+var_178]
0x18004303e  call    ??4?$ComPtr@VSwitchToDesktopImpl@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<SwitchToDesktopImpl>::operator=(Microsoft::WRL::ComPtr<SwitchToDesktopImpl> &&)
0x180043043  nop
0x180043044  mov     rcx, [rbp+130h+var_180]
0x180043048  test    rcx, rcx
0x18004304b  jz      short loc_18004305E
0x18004304d  mov     [rbp+130h+var_180], r12
0x180043051  mov     rax, [rcx]
0x180043054  mov     rax, [rax+10h]
0x180043058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004305d  nop
0x18004305e  mov     rsi, [rbp+130h+var_178]
0x180043062  test    rsi, rsi
0x180043065  jnz     short loc_1800430A0
0x180043067  mov     rcx, [rbp+138h]; this
0x18004306e  mov     ebx, 8007000Eh
0x180043073  mov     r9d, ebx; char *
0x180043076  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18004307d  mov     edx, 35Ch; void *
0x180043082  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043087  nop
0x180043088  lea     rcx, [rbp+130h+string]
0x18004308c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180043091  nop
0x180043092  lea     rcx, [rbp+130h+length]
0x180043096  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004309b  jmp     loc_180043014
0x1800430a0  mov     rax, [rsi]
0x1800430a3  mov     rbx, [rax]
0x1800430a6  lea     rcx, [rbp+130h+string]
0x1800430aa  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800430af  lea     r8, [rbp+130h+string]
0x1800430b3  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800430ba  mov     rcx, rsi
0x1800430bd  mov     rax, rbx
0x1800430c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800430c5  mov     ebx, eax
0x1800430c7  test    eax, eax
0x1800430c9  jns     short loc_1800430FE
0x1800430cb  mov     rcx, [rbp+138h]; this
0x1800430d2  mov     r9d, eax; char *
0x1800430d5  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800430dc  mov     edx, 35Dh; void *
0x1800430e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800430e6  nop
0x1800430e7  test    rsi, rsi
0x1800430ea  jz      short loc_1800430FC
0x1800430ec  mov     rax, [rsi]
0x1800430ef  mov     rcx, rsi
0x1800430f2  mov     rax, [rax+10h]
0x1800430f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800430fb  nop
0x1800430fc  jmp     short loc_180043088
0x1800430fe  mov     qword ptr [rbp+130h+var_188], r12
0x180043102  mov     rbx, [rbp+130h+ppv]
0x180043106  mov     rax, [rbx]
0x180043109  mov     rdi, [rax]
0x18004310c  lea     rcx, [rbp+130h+var_188]
0x180043110  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180043115  lea     r8, [rbp+130h+var_188]
0x180043119  lea     rdx, _GUID_fc4801a3_2ba9_11cf_a229_00aa003d7352
0x180043120  mov     rcx, rbx
0x180043123  mov     rax, rdi
0x180043126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004312b  mov     ebx, eax
0x18004312d  test    eax, eax
0x18004312f  jns     short loc_180043171
0x180043131  mov     rcx, [rbp+138h]; this
0x180043138  mov     r9d, eax; char *
0x18004313b  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180043142  mov     edx, 35Fh; void *
0x180043147  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004314c  nop
  ... truncated ...
```
