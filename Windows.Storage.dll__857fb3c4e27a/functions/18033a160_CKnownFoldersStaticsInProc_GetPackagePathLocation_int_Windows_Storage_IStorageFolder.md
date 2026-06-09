# CKnownFoldersStaticsInProc::GetPackagePathLocation(int,Windows::Storage::IStorageFolder * *)

- ea: `0x18033a160`
- end: `0x18033a564`
- name: `?GetPackagePathLocation@CKnownFoldersStaticsInProc@@UEAAJHPEAPEAUIStorageFolder@Storage@Windows@@@Z`
- size: `1028`
- prototype: `__int64 __fastcall(CKnownFoldersStaticsInProc *__hidden this, int, struct Windows::Storage::IStorageFolder **)`
- caller_count: `0`
- callee_count: `19`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callees

- `0x18000d6cc`
- `0x18000e620`
- `0x18001b340`
- `0x18001b390`
- `0x180027d84`
- `0x18002ba4c`
- `0x1800432f0`
- `0x18007266c`
- `0x180139988`
- `0x18014be50`
- `0x1801dffa0`
- `0x1801e36d4`
- `0x18026c22c`
- `0x1802c03b8`
- `0x18033a160`
- `0x18033b5a8`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18033a216`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18033a216`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18033a421`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18033a421`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18033a40f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18033a40f`
- `KERNELBASE!GetStagedPackagePathByFullName2` at `0x18033a272`
- `KERNELBASE!GetStagedPackagePathByFullName2` at `0x18033a352`
- `KERNELBASE!GetStagedPackagePathByFullName2` at `0x18033a272`
- `KERNELBASE!GetStagedPackagePathByFullName2` at `0x18033a352`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033a2ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033a2fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033a333`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033a4af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033a4b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033a4ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033a4f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033a539`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033a2ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033a2fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033a333`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033a4af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033a4b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033a4ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033a4f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033a539`

## string_xrefs

- `0x18033a315`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18033a366`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18033a3d3`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18033a470`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18033a51b`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18033a1d4`: `GetPackagePathLocation`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CKnownFoldersStaticsInProc::GetPackagePathLocation(
        CKnownFoldersStaticsInProc *this,
        unsigned int a2,
        struct Windows::Storage::IStorageFolder **a3)
{
  HANDLE CurrentProcess; // rax
  unsigned __int16 **v6; // r8
  signed int PackageFullNameFromProcess; // ebx
  __int64 v8; // rdx
  int StagedPackagePathByFullName2; // eax
  WCHAR *v10; // rbx
  __int64 v11; // rdx
  unsigned int v12; // eax
  unsigned int v13; // edi
  int v14; // eax
  const WCHAR *FileNameW; // rax
  HRESULT v16; // eax
  __int64 v17; // rdx
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR pszPath; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h]
  unsigned int v24; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v25; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v27[48]; // [rsp+70h] [rbp-90h] BYREF
  int v28; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v29[40]; // [rsp+A4h] [rbp-5Ch] BYREF
  WCHAR v30[274]; // [rsp+CCh] [rbp-34h] BYREF
  _BYTE v31[528]; // [rsp+2F0h] [rbp+1F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+428h]

  if ( _InterlockedIncrement(&`CKnownFoldersStaticsInProc::GetPackagePathLocation'::`4'::__wil_apiCallCounter) == 1 )
  {
    pszPath = (LPCWSTR)&`CKnownFoldersStaticsInProc::GetPackagePathLocation'::`4'::__wil_apiCallCounter;
    pv = 0;
    v21 = (**((__int64 (__fastcall ***)(char *))this + 11))((char *)this + 88);
    wil::details::ApiTelemetryLogger::InitApiData<unsigned short const *,unsigned short const (&)[7],std::nullptr_t,long volatile *>(
      &v21,
      L"GetPackagePathLocation",
      &pv,
      &pszPath);
  }
  *a3 = 0;
  pszPath = 0;
  v25 = 0;
  *(_OWORD *)&hstringHeader.Reserved.Reserved1 = (unsigned __int64)&v25;
  hstringHeader.Reserved.Reserved2[16] = 1;
  CurrentProcess = GetCurrentProcess();
  PackageFullNameFromProcess = CallerIdentity::GetPackageFullNameFromProcess(
                                 CurrentProcess,
                                 &hstringHeader.Reserved.Reserved2[8],
                                 v6);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&hstringHeader);
  if ( PackageFullNameFromProcess < 0 )
  {
    v8 = 3970;
    goto LABEL_40;
  }
  memset_0(v31, 0, 0x208u);
  v24 = 260;
  StagedPackagePathByFullName2 = GetStagedPackagePathByFullName2(v25, a2, &v24, v31);
  PackageFullNameFromProcess = StagedPackagePathByFullName2;
  if ( StagedPackagePathByFullName2 )
  {
    if ( StagedPackagePathByFullName2 != 122 )
    {
      if ( StagedPackagePathByFullName2 > 0 )
        PackageFullNameFromProcess = (unsigned __int16)StagedPackagePathByFullName2 | 0x80070000;
      if ( PackageFullNameFromProcess >= 0 )
        goto LABEL_41;
      v8 = 3988;
LABEL_40:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
        (const char *)(unsigned int)PackageFullNameFromProcess,
        (int)pv);
LABEL_41:
      if ( v25 )
        CoTaskMemFree(v25);
      return (unsigned int)PackageFullNameFromProcess;
    }
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &pv,
      0,
      v24);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &pszPath,
      &pv);
    if ( pv )
      CoTaskMemFree(pv);
    v10 = (WCHAR *)pszPath;
    if ( !pszPath )
    {
      v11 = 3983;
      goto LABEL_15;
    }
    v12 = GetStagedPackagePathByFullName2(v25, a2, &v24, pszPath);
    if ( v12 )
    {
      v13 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xF90,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
              (const char *)v12,
              (unsigned int)pv);
LABEL_30:
      if ( v25 )
        CoTaskMemFree(v25);
      CoTaskMemFree(v10);
      return v13;
    }
  }
  else
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &pv,
      v31,
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &pszPath,
      &pv);
    if ( pv )
      CoTaskMemFree(pv);
    v10 = (WCHAR *)pszPath;
    if ( !pszPath )
    {
      v11 = 3978;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
        (const char *)0x8007000ELL,
        (int)pv);
      if ( v25 )
        CoTaskMemFree(v25);
      return (unsigned int)-2147024882;
    }
  }
  v26 = 0;
  pv = 0;
  v23 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.Package",
    0x29u,
    0x28u);
  v14 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(
          v23,
          &v26);
  v13 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF9A,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v14,
      (int)pv);
LABEL_29:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
    goto LABEL_30;
  }
  CInProcStorageItemResult<Windows::Storage::IStorageFolder>::CInProcStorageItemResult<Windows::Storage::IStorageFolder>(v27);
  memset_0(v29, 0, 0x24Cu);
  v28 = 16;
  FileNameW = PathFindFileNameW(v10);
  v16 = PathCchAppend(v30, 0x104u, FileNameW);
  v13 = v16;
  if ( v16 < 0 )
  {
    v17 = 3999;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v16,
      (int)pv);
    CInProcStorageItemResult<Windows::Storage::IStorageItem>::~CInProcStorageItemResult<Windows::Storage::IStorageItem>(v27);
    goto LABEL_29;
  }
  v16 = CInProcStorageItemResult<Windows::Storage::IStorageFolder>::_Initialize(v27, v10, &v28, 0);
  v13 = v16;
  if ( v16 < 0 )
  {
    v17 = 4000;
    goto LABEL_28;
  }
  v16 = CInProcStorageItemResult<Windows::Storage::IStorageFolder>::Get(v27, a3);
  v13 = v16;
  if ( v16 < 0 )
  {
    v17 = 4001;
    goto LABEL_28;
  }
  CInProcStorageItemResult<Windows::Storage::IStorageItem>::~CInProcStorageItemResult<Windows::Storage::IStorageItem>(v27);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
  if ( v25 )
    CoTaskMemFree(v25);
  CoTaskMemFree(v10);
  return 0;
}

```

## disassembly

```asm
0x18033a160  mov     [rsp-8+arg_18], rbx
0x18033a165  push    rbp
0x18033a166  push    rsi
0x18033a167  push    rdi
0x18033a168  lea     rbp, [rsp-410h]
0x18033a170  sub     rsp, 510h
0x18033a177  mov     rax, cs:__security_cookie
0x18033a17e  xor     rax, rsp
0x18033a181  mov     [rbp+420h+var_20], rax
0x18033a188  mov     rsi, r8
0x18033a18b  mov     edi, edx
0x18033a18d  mov     eax, 1
0x18033a192  lock xadd cs:?__wil_apiCallCounter@?3??GetPackagePathLocation@CKnownFoldersStaticsInProc@@UEAAJHPEAPEAUIStorageFolder@Storage@Windows@@@Z@4JC, eax; long volatile `CKnownFoldersStaticsInProc::GetPackagePathLocation(int,Windows::Storage::IStorageFolder * *)'::`4'::__wil_apiCallCounter
0x18033a19a  inc     eax
0x18033a19c  cmp     eax, 1
0x18033a19f  jnz     short loc_18033A1E5
0x18033a1a1  lea     rax, ?__wil_apiCallCounter@?3??GetPackagePathLocation@CKnownFoldersStaticsInProc@@UEAAJHPEAPEAUIStorageFolder@Storage@Windows@@@Z@4JC; long volatile `CKnownFoldersStaticsInProc::GetPackagePathLocation(int,Windows::Storage::IStorageFolder * *)'::`4'::__wil_apiCallCounter
0x18033a1a8  mov     [rsp+520h+pszPath], rax
0x18033a1ad  mov     [rsp+520h+pv], 0; int
0x18033a1b6  add     rcx, 58h ; 'X'
0x18033a1ba  mov     rax, [rcx]
0x18033a1bd  mov     rax, [rax]
0x18033a1c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033a1c5  mov     [rsp+520h+var_4F0], rax
0x18033a1ca  lea     r9, [rsp+520h+pszPath]
0x18033a1cf  lea     r8, [rsp+520h+pv]
0x18033a1d4  lea     rdx, aGetpackagepath; "GetPackagePathLocation"
0x18033a1db  lea     rcx, [rsp+520h+var_4F0]
0x18033a1e0  call    ??$InitApiData@PEBGAEAY06$$CBG$$TPECJ@ApiTelemetryLogger@details@wil@@SAX$$QEAPEBGAEAY06$$CBG$$QEA$$T$$QEAPECJ@Z
0x18033a1e5  mov     qword ptr [rsi], 0
0x18033a1ec  mov     [rsp+520h+pszPath], 0
0x18033a1f5  mov     [rsp+520h+var_4C0], 0
0x18033a1fe  lea     rax, [rsp+520h+var_4C0]
0x18033a203  mov     qword ptr [rsp+520h+hstringHeader.Reserved], rax
0x18033a208  mov     qword ptr [rsp+520h+hstringHeader.Reserved+8], 0
0x18033a211  mov     byte ptr [rsp+520h+hstringHeader.Reserved+10h], 1
0x18033a216  call    cs:__imp_GetCurrentProcess
0x18033a21c  lea     rdx, [rsp+520h+hstringHeader.Reserved+8]; void *
0x18033a221  mov     rcx, rax; hProcess
0x18033a224  call    ?GetPackageFullNameFromProcess@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetPackageFullNameFromProcess(void *,ushort * *)
0x18033a229  mov     ebx, eax
0x18033a22b  lea     rcx, [rsp+520h+hstringHeader]
0x18033a230  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18033a235  test    ebx, ebx
0x18033a237  jns     short loc_18033A243
0x18033a239  mov     edx, 0F82h
0x18033a23e  jmp     loc_18033A518
0x18033a243  xor     edx, edx; Val
0x18033a245  mov     r8d, 208h; Size
0x18033a24b  lea     rcx, [rbp+420h+var_230]; void *
0x18033a252  call    memset_0
0x18033a257  mov     [rsp+520h+var_4C8], 104h
0x18033a25f  lea     r9, [rbp+420h+var_230]
0x18033a266  lea     r8, [rsp+520h+var_4C8]
0x18033a26b  mov     edx, edi
0x18033a26d  mov     rcx, [rsp+520h+var_4C0]
0x18033a272  call    cs:__imp_GetStagedPackagePathByFullName2
0x18033a278  mov     ebx, eax
0x18033a27a  test    eax, eax
0x18033a27c  jnz     short loc_18033A2C7
0x18033a27e  or      r8, 0FFFFFFFFFFFFFFFFh
0x18033a282  lea     rdx, [rbp+420h+var_230]
0x18033a289  lea     rcx, [rsp+520h+pv]
0x18033a28e  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18033a293  lea     rdx, [rsp+520h+pv]
0x18033a298  lea     rcx, [rsp+520h+pszPath]
0x18033a29d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18033a2a2  mov     rcx, [rsp+520h+pv]; pv
0x18033a2a7  test    rcx, rcx
0x18033a2aa  jz      short loc_18033A2B2
0x18033a2ac  call    cs:__imp_CoTaskMemFree
0x18033a2b2  mov     rbx, [rsp+520h+pszPath]
0x18033a2b7  test    rbx, rbx
0x18033a2ba  jnz     loc_18033A37E
0x18033a2c0  mov     edx, 0F8Ah
0x18033a2c5  jmp     short loc_18033A30F
0x18033a2c7  cmp     eax, 7Ah ; 'z'
0x18033a2ca  jnz     loc_18033A502
0x18033a2d0  mov     r8d, [rsp+520h+var_4C8]
0x18033a2d5  xor     edx, edx
0x18033a2d7  lea     rcx, [rsp+520h+pv]
0x18033a2dc  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18033a2e1  lea     rdx, [rsp+520h+pv]
0x18033a2e6  lea     rcx, [rsp+520h+pszPath]
0x18033a2eb  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18033a2f0  mov     rcx, [rsp+520h+pv]; pv
0x18033a2f5  test    rcx, rcx
0x18033a2f8  jz      short loc_18033A300
0x18033a2fa  call    cs:__imp_CoTaskMemFree
0x18033a300  mov     rbx, [rsp+520h+pszPath]
0x18033a305  test    rbx, rbx
0x18033a308  jnz     short loc_18033A343
0x18033a30a  mov     edx, 0F8Fh; void *
0x18033a30f  mov     r9d, 8007000Eh; char *
0x18033a315  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18033a31c  mov     rcx, [rbp+428h]; this
0x18033a323  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033a328  nop
0x18033a329  mov     rcx, [rsp+520h+var_4C0]; pv
0x18033a32e  test    rcx, rcx
0x18033a331  jz      short loc_18033A339
0x18033a333  call    cs:__imp_CoTaskMemFree
0x18033a339  mov     ebx, 8007000Eh
0x18033a33e  jmp     loc_18033A540
0x18033a343  mov     r9, rbx
0x18033a346  lea     r8, [rsp+520h+var_4C8]
0x18033a34b  mov     edx, edi
0x18033a34d  mov     rcx, [rsp+520h+var_4C0]
0x18033a352  call    cs:__imp_GetStagedPackagePathByFullName2
0x18033a358  test    eax, eax
0x18033a35a  jz      short loc_18033A37E
0x18033a35c  mov     rcx, [rbp+428h]; this
0x18033a363  mov     r9d, eax; char *
0x18033a366  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18033a36d  mov     edx, 0F90h; void *
0x18033a372  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18033a377  mov     edi, eax
0x18033a379  jmp     loc_18033A4A5
0x18033a37e  mov     [rsp+520h+var_4B8], 0
0x18033a387  mov     [rsp+520h+pv], 0; int
0x18033a390  mov     [rsp+520h+var_4D0], 0
0x18033a399  mov     r9d, 28h ; '('; unsigned int
0x18033a39f  lea     r8d, [r9+1]; unsigned int
0x18033a3a3  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18033a3aa  lea     rcx, [rsp+520h+hstringHeader]; hstringHeader
0x18033a3af  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18033a3b4  lea     rdx, [rsp+520h+var_4B8]
0x18033a3b9  mov     rcx, [rsp+520h+var_4D0]
0x18033a3be  call    ??$GetActivationFactory@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>)
0x18033a3c3  mov     edi, eax
0x18033a3c5  test    eax, eax
0x18033a3c7  jns     short loc_18033A3E9
0x18033a3c9  mov     rcx, [rbp+428h]; this
0x18033a3d0  mov     r9d, eax; char *
0x18033a3d3  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18033a3da  mov     edx, 0F9Ah; void *
0x18033a3df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033a3e4  jmp     loc_18033A48F
0x18033a3e9  lea     rcx, [rsp+520h+var_4B0]
0x18033a3ee  call    ??0?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@QEAA@XZ; CInProcStorageItemResult<Windows::Storage::IStorageFolder>::CInProcStorageItemResult<Windows::Storage::IStorageFolder>(void)
0x18033a3f3  nop
0x18033a3f4  xor     edx, edx; Val
0x18033a3f6  mov     r8d, 24Ch; Size
0x18033a3fc  lea     rcx, [rbp+420h+var_47C]; void *
0x18033a400  call    memset_0
0x18033a405  mov     [rbp+420h+var_480], 10h
0x18033a40c  mov     rcx, rbx; pszPath
0x18033a40f  call    cs:__imp_PathFindFileNameW
0x18033a415  mov     r8, rax; pszMore
0x18033a418  mov     edx, 104h; cchPath
0x18033a41d  lea     rcx, [rbp+420h+var_454]; pszPath
0x18033a421  call    cs:__imp_PathCchAppend
0x18033a427  mov     edi, eax
0x18033a429  test    eax, eax
0x18033a42b  jns     short loc_18033A434
0x18033a42d  mov     edx, 0F9Fh
0x18033a432  jmp     short loc_18033A46D
0x18033a434  xor     r9d, r9d
0x18033a437  lea     r8, [rbp+420h+var_480]
0x18033a43b  mov     rdx, rbx
0x18033a43e  lea     rcx, [rsp+520h+var_4B0]
0x18033a443  call    ?_Initialize@?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@AEAAJPEBGPEBU_WIN32_FIND_DATAW@@PEAUIUser@System@Windows@@@Z; CInProcStorageItemResult<Windows::Storage::IStorageFolder>::_Initialize(ushort const *,_WIN32_FIND_DATAW const *,Windows::System::IUser *)
0x18033a448  mov     edi, eax
0x18033a44a  test    eax, eax
0x18033a44c  jns     short loc_18033A455
0x18033a44e  mov     edx, 0FA0h
0x18033a453  jmp     short loc_18033A46D
0x18033a455  mov     rdx, rsi
0x18033a458  lea     rcx, [rsp+520h+var_4B0]
0x18033a45d  call    ?Get@?$CInProcStorageItemResult@UIStorageFolder@Storage@Windows@@@@QEAAJPEAPEAUIStorageFolder@Storage@Windows@@@Z; CInProcStorageItemResult<Windows::Storage::IStorageFolder>::Get(Windows::Storage::IStorageFolder * *)
0x18033a462  mov     edi, eax
0x18033a464  test    eax, eax
0x18033a466  jns     short loc_18033A4C3
0x18033a468  mov     edx, 0FA1h; void *
0x18033a46d  mov     r9d, eax; char *
0x18033a470  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18033a477  mov     rcx, [rbp+428h]; this
0x18033a47e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033a483  nop
0x18033a484  lea     rcx, [rsp+520h+var_4B0]
0x18033a489  call    ??1?$CInProcStorageItemResult@UIStorageItem@Storage@Windows@@@@QEAA@XZ; CInProcStorageItemResult<Windows::Storage::IStorageItem>::~CInProcStorageItemResult<Windows::Storage::IStorageItem>(void)
0x18033a48e  nop
0x18033a48f  lea     rcx, [rsp+520h+pv]
0x18033a494  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18033a499  nop
0x18033a49a  lea     rcx, [rsp+520h+var_4B8]
0x18033a49f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18033a4a4  nop
0x18033a4a5  mov     rcx, [rsp+520h+var_4C0]; pv
0x18033a4aa  test    rcx, rcx
0x18033a4ad  jz      short loc_18033A4B6
0x18033a4af  call    cs:__imp_CoTaskMemFree
0x18033a4b5  nop
0x18033a4b6  mov     rcx, rbx; pv
0x18033a4b9  call    cs:__imp_CoTaskMemFree
0x18033a4bf  mov     eax, edi
0x18033a4c1  jmp     short loc_18033A542
0x18033a4c3  lea     rcx, [rsp+520h+var_4B0]
0x18033a4c8  call    ??1?$CInProcStorageItemResult@UIStorageItem@Storage@Windows@@@@QEAA@XZ; CInProcStorageItemResult<Windows::Storage::IStorageItem>::~CInProcStorageItemResult<Windows::Storage::IStorageItem>(void)
0x18033a4cd  nop
0x18033a4ce  lea     rcx, [rsp+520h+pv]
0x18033a4d3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18033a4d8  nop
0x18033a4d9  lea     rcx, [rsp+520h+var_4B8]
0x18033a4de  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18033a4e3  nop
0x18033a4e4  mov     rcx, [rsp+520h+var_4C0]; pv
0x18033a4e9  test    rcx, rcx
0x18033a4ec  jz      short loc_18033A4F5
0x18033a4ee  call    cs:__imp_CoTaskMemFree
0x18033a4f4  nop
0x18033a4f5  mov     rcx, rbx; pv
0x18033a4f8  call    cs:__imp_CoTaskMemFree
0x18033a4fe  xor     eax, eax
0x18033a500  jmp     short loc_18033A542
0x18033a502  test    eax, eax
0x18033a504  jle     short loc_18033A50F
0x18033a506  movzx   ebx, ax
0x18033a509  or      ebx, 80070000h
0x18033a50f  test    ebx, ebx
0x18033a511  jns     short loc_18033A52F
0x18033a513  mov     edx, 0F94h; void *
0x18033a518  mov     r9d, ebx; char *
0x18033a51b  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18033a522  mov     rcx, [rbp+428h]; this
0x18033a529  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033a52e  nop
0x18033a52f  mov     rcx, [rsp+520h+var_4C0]; pv
0x18033a534  test    rcx, rcx
0x18033a537  jz      short loc_18033A540
0x18033a539  call    cs:__imp_CoTaskMemFree
0x18033a53f  nop
0x18033a540  mov     eax, ebx
0x18033a542  mov     rcx, [rbp+420h+var_20]
0x18033a549  xor     rcx, rsp; StackCookie
0x18033a54c  call    __security_check_cookie
0x18033a551  mov     rbx, [rsp+520h+arg_18]
0x18033a559  add     rsp, 510h
0x18033a560  pop     rdi
0x18033a561  pop     rsi
0x18033a562  pop     rbp
0x18033a563  retn
```
