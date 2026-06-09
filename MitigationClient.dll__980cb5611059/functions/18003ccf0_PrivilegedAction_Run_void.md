# PrivilegedAction::Run(void)

- ea: `0x18003ccf0`
- end: `0x18003d2fc`
- name: `?Run@PrivilegedAction@@UEAAXXZ`
- size: `1548`
- prototype: `void __fastcall(PrivilegedAction *__hidden this)`
- caller_count: `0`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000a6e0`
- `0x18000cebc`
- `0x18001055c`
- `0x18001208c`
- `0x180013b04`
- `0x180017c84`
- `0x180019ecc`
- `0x18001e164`
- `0x18001e1b4`
- `0x18002407c`
- `0x180024518`
- `0x18002bc50`
- `0x18002bd64`
- `0x18002c004`
- `0x18002c958`
- `0x18002db58`
- `0x180035f34`
- `0x18003b8bc`
- `0x18003c10c`
- `0x18003c970`
- `0x18003ca7c`
- `0x18003cab8`
- `0x18003ccf0`
- `0x18003d304`
- `0x18003dcf8`
- `0x18003e9ec`
- `0x18003eb00`
- `0x18003f458`
- `0x180042f54`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18003ce21`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18003ce52`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18003cec3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18003ce21`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18003ce52`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18003cec3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d2b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d2b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ce65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cf02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cf89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ce65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cf02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cf89`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003ce2e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003ce9c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003d2a8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003ce2e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003ce9c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003d2a8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003d019`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003d019`

## string_xrefs

- `0x18003cd79`: `PrivilegedActions.cab`
- `0x18003cdba`: `Actions.json`
- `0x18003cda3`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\privilegedaction.cpp`
- `0x18003cde4`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\privilegedaction.cpp`
- `0x18003ce40`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\privilegedaction.cpp`
- `0x18003ce85`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\privilegedaction.cpp`
- `0x18003ceb9`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\privilegedaction.cpp`
- `0x18003d1b9`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\privilegedactionsjsondescriptor.cpp`

## pseudocode

```c
void __fastcall PrivilegedAction::Run(PrivilegedAction *this)
{
  LPCWSTR *v2; // rdi
  __int64 v3; // rdx
  const unsigned __int16 **v4; // rsi
  int v5; // eax
  LPCWSTR *v6; // rbx
  int v7; // eax
  __int64 DirectoryPath; // rax
  const char *v9; // r9
  const unsigned __int16 *StringRawBuffer; // rax
  int ContentFromFileAndVerifySha256Hash; // eax
  const char *v12; // r9
  unsigned __int8 **v13; // r12
  unsigned int v14; // eax
  unsigned int *v15; // r13
  int v16; // ebx
  struct MitigationContext *MitigationContext; // rax
  const unsigned __int16 *v18; // rax
  int v19; // eax
  int CabFile; // eax
  HANDLE FileW; // rax
  wil *v22; // rcx
  const char *v23; // r9
  void *v24; // rbx
  int v25; // eax
  int v26; // eax
  wil *v27; // rcx
  int v28; // eax
  int v29; // eax
  int v30; // ebx
  __int64 v31; // rcx
  int v32; // eax
  int v33; // ebx
  __int64 v34; // rsi
  __int64 (__fastcall *v35)(__int64, char *); // rbx
  int v36; // eax
  wil *v37; // rcx
  wil *v38; // rcx
  void *v39; // rdx
  unsigned int v40; // r8d
  const char *v41; // r9
  __int64 v42; // rax
  unsigned int v43; // eax
  __int64 v44; // rax
  __int64 v45; // rax
  unsigned int v46; // eax
  __int64 v47; // rax
  unsigned int v48; // eax
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  unsigned int v52; // eax
  __int64 v53; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-2B8h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-2B8h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-2B8h]
  int v57[4]; // [rsp+40h] [rbp-298h] BYREF
  IID rclsid; // [rsp+50h] [rbp-288h] BYREF
  __int64 v59; // [rsp+60h] [rbp-278h] BYREF
  unsigned __int16 *v60; // [rsp+68h] [rbp-270h] BYREF
  __int64 v61; // [rsp+70h] [rbp-268h]
  __int64 v62; // [rsp+78h] [rbp-260h]
  __int64 v63; // [rsp+80h] [rbp-258h] BYREF
  void *v64; // [rsp+88h] [rbp-250h] BYREF
  HANDLE v65; // [rsp+90h] [rbp-248h] BYREF
  const wil::ResultException *v66; // [rsp+98h] [rbp-240h] BYREF
  const wil::ResultException *v67; // [rsp+A0h] [rbp-238h] BYREF
  const wil::ResultException *v68; // [rsp+A8h] [rbp-230h] BYREF
  const wil::ResultException *v69[2]; // [rsp+B0h] [rbp-228h] BYREF
  char v70; // [rsp+C0h] [rbp-218h]
  _BYTE v71[424]; // [rsp+C8h] [rbp-210h] BYREF
  char *v72; // [rsp+270h] [rbp-68h] BYREF
  __int64 v73; // [rsp+278h] [rbp-60h] BYREF
  char v74; // [rsp+280h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  v2 = *(LPCWSTR **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                      &v65,
                      this);
  v69[1] = (const wil::ResultException *)v2;
  v70 = 1;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
    &v60,
    L"%s\\",
    *(_QWORD *)(*(_QWORD *)(v3 + 152) + 88LL));
  v4 = (const unsigned __int16 **)((char *)this + 72);
  v5 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         (char *)this + 72,
         L"%sCabDir\\%s",
         v60,
         L"PrivilegedActions.cab");
  try
  {
    if ( v5 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
        (const char *)(unsigned int)v5,
        dwCreationDisposition);
    v6 = (LPCWSTR *)((char *)this + 128);
    v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
           (char *)this + 128,
           L"%sCabDir\\%s",
           v60,
           L"Actions.json");
    if ( v7 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x54,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
        (const char *)(unsigned int)v7,
        dwCreationDisposition);
    DirectoryPath = FileUtils::GetDirectoryPath(&v72, *v4);
    std::wstring::operator=((char *)this + 96, DirectoryPath);
    std::wstring::_Tidy_deallocate(&v72);
    if ( PathFileExistsW(*v6) && !DeleteFileW(*v6) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x5C,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
        v9);
    if ( PathFileExistsW(*v4) )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 22), 0);
      ContentFromFileAndVerifySha256Hash = FileUtils::GetContentFromFileAndVerifySha256Hash(*v4, StringRawBuffer);
      if ( ContentFromFileAndVerifySha256Hash < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x63,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
          (const char *)(unsigned int)ContentFromFileAndVerifySha256Hash,
          dwCreationDisposition);
        if ( !DeleteFileW(*v4) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x65,
            (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
            v12);
      }
    }
    if ( !PathFileExistsW(*v4) )
    {
      v57[0] = 0;
      v13 = (unsigned __int8 **)((char *)this + 56);
      v72 = (char *)this + 56;
      v73 = 0;
      v74 = 1;
      v14 = (unsigned int)WindowsGetStringRawBuffer(*((HSTRING *)this + 21), 0);
      rclsid = *(IID *)&off_18005EE80;
      v15 = (unsigned int *)((char *)this + 64);
      v16 = FileUtils::DownloadContentFromURL(
              v14,
              (unsigned int)&rclsid,
              (unsigned int)&v73,
              (int)this + 64,
              (unsigned int)v57);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>>(&v72);
      rclsid = (IID)xmmword_180080698;
      MitigationContext = MitigationExecutionContext::GetMitigationContext(&rclsid);
      *((_DWORD *)MitigationContext + 45) = v57[0];
      if ( v16 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x73,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
          (const char *)(unsigned int)v16,
          dwCreationDispositiona);
      v18 = WindowsGetStringRawBuffer(*((HSTRING *)this + 22), 0);
      v19 = FileUtils::VerifyContentSha256Hash(*v13, *v15, v18);
      if ( v19 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x76,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
          (const char *)(unsigned int)v19,
          dwCreationDispositiona);
      CabFile = CabUtils::CreateCabFile(*v4, *v13, *v15);
      if ( CabFile < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x79,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
          (const char *)(unsigned int)CabFile,
          dwCreationDispositiona);
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v60);
    FileW = CreateFileW(*v4, 0x120089u, 1u, 0, 3u, 0x100u, 0);
  }
  catch ( const wil::ResultException *v69 )
  {
    v51 = MitigationException::MitigationException(v71, 3, v69[0]);
    wil::details::ReportFailure_CustomException<MitigationException>(
      retaddr,
      127,
      "onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
      v51);
  }
  catch ( ... )
  {
    v52 = wil::ResultFromCaughtException(v22);
    v53 = MitigationException::MitigationException(v71, 3, v52);
    wil::details::ReportFailure_CustomException<MitigationException>(
      retaddr,
      132,
      "onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
      v53);
  }
  try
  {
    v24 = FileW;
    v65 = FileW;
    if ( FileW == (HANDLE)-1LL )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x93,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
        v23);
    v25 = CabUtils::VerifyCabIntegrity(FileW);
    if ( v25 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x96,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
        (const char *)(unsigned int)v25,
        dwCreationDispositionb);
    v26 = CabUtils::VerifyCabAuthenticity(v24, *v4);
    v27 = retaddr;
    if ( v26 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x99,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
        (const char *)(unsigned int)v26,
        dwCreationDispositionb);
  }
  catch ( const wil::ResultException *v68 )
  {
    v50 = MitigationException::MitigationException(v71, 5, v68);
    wil::details::ReportFailure_CustomException<MitigationException>(
      retaddr,
      157,
      "onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
      v50);
  }
  catch ( ... )
  {
    v48 = wil::ResultFromCaughtException(v27);
    v49 = MitigationException::MitigationException(v71, 5, v48);
    wil::details::ReportFailure_CustomException<MitigationException>(
      retaddr,
      162,
      "onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
      v49);
  }
  try
  {
    v64 = (void *)-1LL;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v64,
      -1);
    v28 = PrivilegedAction::ExtractJsonFileFromCab(this, &v64);
    if ( v28 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xA9,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
        (const char *)(unsigned int)v28,
        dwCreationDispositionb);
    v60 = 0;
    v61 = 0;
    v62 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v60);
    v61 = -1;
    v62 = -1;
    v29 = MitigationAPICommon::ReadFileIntoString(v64, &v60);
    v30 = v29;
    if ( v29 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xED,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
        (const char *)(unsigned int)v29,
        dwCreationDispositionb);
    if ( v30 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xAD,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
        (const char *)(unsigned int)v30,
        dwCreationDispositionb);
    v63 = 0;
    *(_QWORD *)v57 = *((_QWORD *)this + 19);
    Microsoft::WRL::ComPtr<MitigationOneSettingsMetadata>::InternalAddRef(v57);
    *(_QWORD *)&rclsid.Data1 = v57;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
    v59 = *(_QWORD *)v57;
    Microsoft::WRL::ComPtr<MitigationOneSettingsMetadata>::InternalAddRef(&v59);
    v32 = PrivilegedActionsJsonDescriptor::s_CreateInstance(v31, &v63, v60, &v59);
    v33 = v32;
    if ( v32 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x32,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedactionsjsondescriptor.cpp",
        (const char *)(unsigned int)v32,
        dwCreationDispositionb);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v57);
    if ( v33 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xB1,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
        (const char *)(unsigned int)v33,
        dwCreationDispositionb);
    v34 = v63;
    v35 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v63 + 24LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 160);
    v36 = v35(v34, (char *)this + 160);
    if ( v36 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xB3,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
        (const char *)(unsigned int)v36,
        dwCreationDispositionb);
    if ( !*((_QWORD *)this + 20) )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xB4,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
        (const char *)0x80070057LL,
        dwCreationDispositionb);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v60);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v64);
  }
  catch ( const wil::ResultException *v67 )
  {
    v45 = MitigationException::MitigationException(v71, 6, v67);
    wil::details::ReportFailure_CustomException<MitigationException>(
      retaddr,
      184,
      "onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
      v45);
  }
  catch ( ... )
  {
    v46 = wil::ResultFromCaughtException(v37);
    v47 = MitigationException::MitigationException(v71, 6, v46);
    wil::details::ReportFailure_CustomException<MitigationException>(
      retaddr,
      189,
      "onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
      v47);
  }
  try
  {
    ActionRunner::RunServiceDrivenActions(*((struct IObjectArray **)this + 20));
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v65);
    if ( !DeleteFileW(v2[16]) && GetLastError() != 2 )
      wil::details::in1diag3::_Log_GetLastError(retaddr, v39, v40, v41);
  }
  catch ( MitigationException )
  {
    throw;
  }
  catch ( const wil::ResultException *v66 )
  {
    v42 = MitigationException::MitigationException(v71, 7, v66);
    wil::details::ReportFailure_CustomException<MitigationException>(
      retaddr,
      205,
      "onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
      v42);
  }
  catch ( ... )
  {
    v43 = wil::ResultFromCaughtException(v38);
    v44 = MitigationException::MitigationException(v71, 7, v43);
    wil::details::ReportFailure_CustomException<MitigationException>(
      retaddr,
      210,
      "onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
      v44);
  }
}

```

## disassembly

```asm
0x18003ccf0  mov     rax, rsp
0x18003ccf3  mov     [rax+10h], rbx
0x18003ccf7  mov     [rax+18h], rsi
0x18003ccfb  push    rdi
0x18003ccfc  push    r12
0x18003ccfe  push    r13
0x18003cd00  push    r14
0x18003cd02  push    r15
0x18003cd04  sub     rsp, 2B0h
0x18003cd0b  movaps  xmmword ptr [rax-38h], xmm6
0x18003cd0f  mov     rax, cs:__security_cookie
0x18003cd16  xor     rax, rsp
0x18003cd19  mov     [rsp+2D8h+var_48], rax
0x18003cd21  mov     r15, rcx
0x18003cd24  mov     rdx, rcx
0x18003cd27  lea     rcx, [rsp+2D8h+var_248]
0x18003cd2f  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18003cd34  mov     rdi, [rax]
0x18003cd37  mov     [rsp+2D8h+var_220], rdi
0x18003cd3f  mov     [rsp+2D8h+var_218], 1
0x18003cd47  xor     r13d, r13d
0x18003cd4a  mov     [rsp+2D8h+var_270], r13
0x18003cd4f  mov     [rsp+2D8h+var_268], r13
0x18003cd54  mov     [rsp+2D8h+var_260], r13
0x18003cd59  mov     r8, [rdx+98h]
0x18003cd60  mov     r8, [r8+58h]
0x18003cd64  lea     rdx, aS_0; "%s\\"
0x18003cd6b  lea     rcx, [rsp+2D8h+var_270]
0x18003cd70  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18003cd75  lea     rsi, [r15+48h]
0x18003cd79  lea     r9, WideCharStr; "PrivilegedActions.cab"
0x18003cd80  mov     r8, [rsp+2D8h+var_270]
0x18003cd85  lea     rdx, aScabdirS; "%sCabDir\\%s"
0x18003cd8c  mov     rcx, rsi
0x18003cd8f  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18003cd94  mov     rcx, [rsp+2D8h]; this
0x18003cd9c  test    eax, eax
0x18003cd9e  jns     short loc_18003CDB3
0x18003cda0  mov     r9d, eax; char *
0x18003cda3  lea     r8, aOnecoreBaseDia_12; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003cdaa  lea     edx, [r13+53h]; void *
0x18003cdae  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003cdb3  lea     rbx, [r15+80h]
0x18003cdba  lea     r9, aActionsJson; "Actions.json"
0x18003cdc1  mov     r8, [rsp+2D8h+var_270]
0x18003cdc6  lea     rdx, aScabdirS; "%sCabDir\\%s"
0x18003cdcd  mov     rcx, rbx
0x18003cdd0  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18003cdd5  mov     rcx, [rsp+2D8h]; this
0x18003cddd  test    eax, eax
0x18003cddf  jns     short loc_18003CDF5
0x18003cde1  mov     r9d, eax; char *
0x18003cde4  lea     r8, aOnecoreBaseDia_12; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003cdeb  mov     edx, 54h ; 'T'; void *
0x18003cdf0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003cdf5  mov     rdx, [rsi]
0x18003cdf8  lea     rcx, [rsp+2D8h+var_68]
0x18003ce00  call    ?GetDirectoryPath@FileUtils@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; FileUtils::GetDirectoryPath(ushort const *)
0x18003ce05  lea     rcx, [r15+60h]
0x18003ce09  mov     rdx, rax
0x18003ce0c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003ce11  lea     rcx, [rsp+2D8h+var_68]
0x18003ce19  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ce1e  mov     rcx, [rbx]; pszPath
0x18003ce21  call    cs:__imp_PathFileExistsW
0x18003ce27  test    eax, eax
0x18003ce29  jz      short loc_18003CE4F
0x18003ce2b  mov     rcx, [rbx]; lpFileName
0x18003ce2e  call    cs:__imp_DeleteFileW
0x18003ce34  mov     rcx, [rsp+2D8h]; this
0x18003ce3c  test    eax, eax
0x18003ce3e  jnz     short loc_18003CE4F
0x18003ce40  lea     r8, aOnecoreBaseDia_12; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003ce47  lea     edx, [rax+5Ch]; void *
0x18003ce4a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003ce4f  mov     rcx, [rsi]; pszPath
0x18003ce52  call    cs:__imp_PathFileExistsW
0x18003ce58  test    eax, eax
0x18003ce5a  jz      short loc_18003CEB9
0x18003ce5c  xor     edx, edx; length
0x18003ce5e  mov     rcx, [r15+0B0h]; string
0x18003ce65  call    cs:__imp_WindowsGetStringRawBuffer
0x18003ce6b  mov     rdx, rax; unsigned __int16 *
0x18003ce6e  mov     rcx, [rsi]; unsigned __int16 *
0x18003ce71  call    ?GetContentFromFileAndVerifySha256Hash@FileUtils@@SAJPEBGQEBG@Z; FileUtils::GetContentFromFileAndVerifySha256Hash(ushort const *,ushort const * const)
0x18003ce76  mov     rcx, [rsp+2D8h]; this
0x18003ce7e  test    eax, eax
0x18003ce80  jns     short loc_18003CEB9
0x18003ce82  mov     r9d, eax; char *
0x18003ce85  lea     r14, aOnecoreBaseDia_12; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003ce8c  mov     r8, r14; unsigned int
0x18003ce8f  mov     edx, 63h ; 'c'; void *
0x18003ce94  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003ce99  mov     rcx, [rsi]; lpFileName
0x18003ce9c  call    cs:__imp_DeleteFileW
0x18003cea2  mov     rcx, [rsp+2D8h]; this
0x18003ceaa  test    eax, eax
0x18003ceac  jnz     short loc_18003CEC0
0x18003ceae  mov     r8, r14; unsigned int
0x18003ceb1  lea     edx, [rax+65h]; void *
0x18003ceb4  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003ceb9  lea     r14, aOnecoreBaseDia_12; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003cec0  mov     rcx, [rsi]; pszPath
0x18003cec3  call    cs:__imp_PathFileExistsW
0x18003cec9  test    eax, eax
0x18003cecb  jnz     loc_18003CFEA
0x18003ced1  mov     [rsp+2D8h+var_298], r13d
0x18003ced6  lea     r12, [r15+38h]
0x18003ceda  mov     [rsp+2D8h+var_68], r12
0x18003cee2  mov     [rsp+2D8h+var_60], r13
0x18003ceea  mov     [rsp+2D8h+var_58], 1
0x18003cef2  movups  xmm6, xmmword ptr cs:off_18005EE80; "ca9d613c-a9a4-46e9-a010-8054ace6ee02"
0x18003cef9  xor     edx, edx; length
0x18003cefb  mov     rcx, [r15+0A8h]; string
0x18003cf02  call    cs:__imp_WindowsGetStringRawBuffer
0x18003cf08  movdqu  xmmword ptr [rsp+2D8h+rclsid.Data1], xmm6
0x18003cf0e  lea     r13, [r15+40h]
0x18003cf12  lea     rcx, [rsp+2D8h+var_298]
0x18003cf17  mov     qword ptr [rsp+2D8h+dwCreationDisposition], rcx; int
0x18003cf1c  mov     r9, r13
0x18003cf1f  lea     r8, [rsp+2D8h+var_60]
0x18003cf27  lea     rdx, [rsp+2D8h+rclsid]
0x18003cf2c  mov     rcx, rax
0x18003cf2f  call    ?DownloadContentFromURL@FileUtils@@SAJPEBGV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEAPEAEPEAKAEAH@Z; FileUtils::DownloadContentFromURL(ushort const *,std::basic_string_view<ushort>,uchar * *,ulong *,int &)
0x18003cf34  mov     ebx, eax
0x18003cf36  lea     rcx, [rsp+2D8h+var_68]
0x18003cf3e  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>>::~out_param_t<wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>>(void)
0x18003cf43  movups  xmm0, cs:xmmword_180080698
0x18003cf4a  movdqu  xmmword ptr [rsp+2D8h+rclsid.Data1], xmm0
0x18003cf50  lea     rcx, [rsp+2D8h+rclsid]; rclsid
0x18003cf55  call    ?GetMitigationContext@MitigationExecutionContext@@SAAEAVMitigationContext@@U_GUID@@@Z; MitigationExecutionContext::GetMitigationContext(_GUID)
0x18003cf5a  mov     ecx, [rsp+2D8h+var_298]
0x18003cf5e  mov     [rax+0B4h], ecx
0x18003cf64  mov     rcx, [rsp+2D8h]; this
0x18003cf6c  test    ebx, ebx
0x18003cf6e  jns     short loc_18003CF80
0x18003cf70  mov     r9d, ebx; char *
0x18003cf73  mov     r8, r14; unsigned int
0x18003cf76  mov     edx, 73h ; 's'; void *
0x18003cf7b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003cf80  xor     edx, edx; length
0x18003cf82  mov     rcx, [r15+0B0h]; string
0x18003cf89  call    cs:__imp_WindowsGetStringRawBuffer
0x18003cf8f  mov     r8, rax; unsigned __int16 *
0x18003cf92  mov     edx, [r13+0]; unsigned int
0x18003cf96  mov     rcx, [r12]; unsigned __int8 *
0x18003cf9a  call    ?VerifyContentSha256Hash@FileUtils@@SAJPEAEKQEBG@Z; FileUtils::VerifyContentSha256Hash(uchar *,ulong,ushort const * const)
0x18003cf9f  mov     rcx, [rsp+2D8h]; this
0x18003cfa7  test    eax, eax
0x18003cfa9  jns     short loc_18003CFBB
0x18003cfab  mov     r9d, eax; char *
0x18003cfae  mov     r8, r14; unsigned int
0x18003cfb1  mov     edx, 76h ; 'v'; void *
0x18003cfb6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003cfbb  mov     r8d, [r13+0]; nNumberOfBytesToWrite
0x18003cfbf  mov     rdx, [r12]; lpBuffer
0x18003cfc3  mov     rcx, [rsi]; lpFileName
0x18003cfc6  call    ?CreateCabFile@CabUtils@@SAJPEBGPEAEK@Z; CabUtils::CreateCabFile(ushort const *,uchar *,ulong)
0x18003cfcb  mov     rcx, [rsp+2D8h]; this
0x18003cfd3  xor     r13d, r13d
0x18003cfd6  test    eax, eax
0x18003cfd8  jns     short loc_18003CFEA
0x18003cfda  mov     r9d, eax; char *
0x18003cfdd  mov     r8, r14; unsigned int
0x18003cfe0  lea     edx, [r13+79h]; void *
0x18003cfe4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003cfea  lea     rcx, [rsp+2D8h+var_270]
0x18003cfef  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003cff4  nop
0x18003cff5  mov     [rsp+2D8h+hTemplateFile], r13; hTemplateFile
0x18003cffa  mov     [rsp+2D8h+dwFlagsAndAttributes], 100h; dwFlagsAndAttributes
0x18003d002  mov     [rsp+2D8h+dwCreationDisposition], 3; int
0x18003d00a  xor     r9d, r9d; lpSecurityAttributes
0x18003d00d  mov     edx, 120089h; dwDesiredAccess
0x18003d012  lea     r8d, [r9+1]; dwShareMode
0x18003d016  mov     rcx, [rsi]; lpFileName
0x18003d019  call    cs:__imp_CreateFileW
0x18003d01f  mov     rbx, rax
0x18003d022  mov     [rsp+2D8h+var_248], rax
0x18003d02a  mov     rcx, [rsp+2D8h]; this
0x18003d032  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003d036  cmp     rax, r12
0x18003d039  jnz     short loc_18003D048
0x18003d03b  mov     r8, r14; unsigned int
0x18003d03e  mov     edx, 93h; void *
0x18003d043  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003d048  mov     rcx, rbx; hFile
0x18003d04b  call    ?VerifyCabIntegrity@CabUtils@@SAJPEAX@Z; CabUtils::VerifyCabIntegrity(void *)
0x18003d050  mov     rcx, [rsp+2D8h]; this
0x18003d058  test    eax, eax
0x18003d05a  jns     short loc_18003D06C
0x18003d05c  mov     r9d, eax; char *
0x18003d05f  mov     r8, r14; unsigned int
0x18003d062  mov     edx, 96h; void *
0x18003d067  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003d06c  mov     rdx, [rsi]; unsigned __int16 *
0x18003d06f  mov     rcx, rbx; void *
0x18003d072  call    ?VerifyCabAuthenticity@CabUtils@@SAJPEAXPEBG@Z; CabUtils::VerifyCabAuthenticity(void *,ushort const *)
0x18003d077  mov     rcx, [rsp+2D8h]; this
0x18003d07f  test    eax, eax
0x18003d081  jns     short loc_18003D094
0x18003d083  mov     r9d, eax; char *
0x18003d086  mov     r8, r14; unsigned int
0x18003d089  mov     edx, 99h; void *
0x18003d08e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003d094  mov     [rsp+2D8h+var_250], r12
0x18003d09c  mov     rdx, r12
0x18003d09f  lea     rcx, [rsp+2D8h+var_250]
0x18003d0a7  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003d0ac  lea     rdx, [rsp+2D8h+var_250]; void **
0x18003d0b4  mov     rcx, r15; this
0x18003d0b7  call    ?ExtractJsonFileFromCab@PrivilegedAction@@AEAAJPEAPEAX@Z; PrivilegedAction::ExtractJsonFileFromCab(void * *)
0x18003d0bc  mov     rcx, [rsp+2D8h]; this
0x18003d0c4  test    eax, eax
0x18003d0c6  jns     short loc_18003D0D8
0x18003d0c8  mov     r9d, eax; char *
0x18003d0cb  mov     r8, r14; unsigned int
0x18003d0ce  mov     edx, 0A9h; void *
0x18003d0d3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003d0d8  mov     [rsp+2D8h+var_270], r13
0x18003d0dd  mov     [rsp+2D8h+var_268], r13
0x18003d0e2  mov     [rsp+2D8h+var_260], r13
0x18003d0e7  lea     rcx, [rsp+2D8h+var_270]
0x18003d0ec  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003d0f1  mov     [rsp+2D8h+var_268], r12
0x18003d0f6  mov     [rsp+2D8h+var_260], r12
0x18003d0fb  lea     rdx, [rsp+2D8h+var_270]; unsigned __int16 **
0x18003d100  mov     rcx, [rsp+2D8h+var_250]; void *
0x18003d108  call    ?ReadFileIntoString@MitigationAPICommon@@SAJPEAXPEAPEAG@Z; MitigationAPICommon::ReadFileIntoString(void *,ushort * *)
0x18003d10d  mov     ebx, eax
0x18003d10f  test    eax, eax
0x18003d111  jns     short loc_18003D12B
0x18003d113  mov     rcx, [rsp+2D8h]; this
0x18003d11b  mov     r9d, eax; char *
0x18003d11e  mov     r8, r14; unsigned int
0x18003d121  mov     edx, 0EDh; void *
0x18003d126  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d12b  mov     rcx, [rsp+2D8h]; this
0x18003d133  test    ebx, ebx
0x18003d135  jns     short loc_18003D147
0x18003d137  mov     r9d, ebx; char *
0x18003d13a  mov     r8, r14; unsigned int
0x18003d13d  mov     edx, 0ADh; void *
0x18003d142  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003d147  mov     [rsp+2D8h+var_258], r13
0x18003d14f  mov     rax, [r15+98h]
0x18003d156  mov     qword ptr [rsp+2D8h+var_298], rax
0x18003d15b  lea     rcx, [rsp+2D8h+var_298]
0x18003d160  call    ?InternalAddRef@?$ComPtr@VMitigationOneSettingsMetadata@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MitigationOneSettingsMetadata>::InternalAddRef(void)
0x18003d165  lea     rax, [rsp+2D8h+var_298]
0x18003d16a  mov     qword ptr [rsp+2D8h+rclsid.Data1], rax
0x18003d16f  lea     rcx, [rsp+2D8h+var_258]
0x18003d177  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003d17c  nop
0x18003d17d  mov     rax, qword ptr [rsp+2D8h+var_298]
0x18003d182  mov     [rsp+2D8h+var_278], rax
0x18003d187  lea     rcx, [rsp+2D8h+var_278]
0x18003d18c  call    ?InternalAddRef@?$ComPtr@VMitigationOneSettingsMetadata@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MitigationOneSettingsMetadata>::InternalAddRef(void)
0x18003d191  lea     r9, [rsp+2D8h+var_278]
0x18003d196  mov     r8, [rsp+2D8h+var_270]
0x18003d19b  lea     rdx, [rsp+2D8h+var_258]
0x18003d1a3  call    ?s_CreateInstance@PrivilegedActionsJsonDescriptor@@SAJAEBU_GUID@@PEAPEAXPEBGV?$ComPtr@VActionContext@@@WRL@Microsoft@@@Z; PrivilegedActionsJsonDescriptor::s_CreateInstance(_GUID const &,void * *,ushort const *,Microsoft::WRL::ComPtr<ActionContext>)
0x18003d1a8  mov     ebx, eax
0x18003d1aa  test    eax, eax
0x18003d1ac  jns     short loc_18003D1CB
0x18003d1ae  mov     rcx, [rsp+2D8h]; this
0x18003d1b6  mov     r9d, eax; char *
0x18003d1b9  lea     r8, aOnecoreBaseDia_16; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003d1c0  mov     edx, 32h ; '2'; void *
0x18003d1c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d1ca  nop
0x18003d1cb  lea     rcx, [rsp+2D8h+var_298]
0x18003d1d0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003d1d5  mov     rcx, [rsp+2D8h]; this
0x18003d1dd  test    ebx, ebx
0x18003d1df  jns     short loc_18003D1F1
0x18003d1e1  mov     r9d, ebx; char *
0x18003d1e4  mov     r8, r14; unsigned int
0x18003d1e7  mov     edx, 0B1h; void *
0x18003d1ec  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003d1f1  mov     rsi, [rsp+2D8h+var_258]
0x18003d1f9  mov     rax, [rsi]
0x18003d1fc  mov     rbx, [rax+18h]
0x18003d200  lea     rcx, [r15+0A0h]
0x18003d207  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003d20c  lea     rdx, [r15+0A0h]
0x18003d213  mov     rcx, rsi
0x18003d216  mov     rax, rbx
0x18003d219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d21e  mov     rcx, [rsp+2D8h]; this
0x18003d226  test    eax, eax
0x18003d228  jns     short loc_18003D23A
0x18003d22a  mov     r9d, eax; char *
0x18003d22d  mov     r8, r14; unsigned int
0x18003d230  mov     edx, 0B3h; void *
0x18003d235  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003d23a  mov     rcx, [rsp+2D8h]; this
0x18003d242  cmp     [r15+0A0h], r13
0x18003d249  jnz     short loc_18003D25F
0x18003d24b  mov     r9d, 80070057h; char *
  ... truncated ...
```
