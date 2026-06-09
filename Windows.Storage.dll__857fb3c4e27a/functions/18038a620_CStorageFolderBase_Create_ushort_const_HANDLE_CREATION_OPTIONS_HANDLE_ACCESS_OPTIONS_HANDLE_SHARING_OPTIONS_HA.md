# CStorageFolderBase::Create(ushort const *,HANDLE_CREATION_OPTIONS,HANDLE_ACCESS_OPTIONS,HANDLE_SHARING_OPTIONS,HANDLE_OPTIONS,IOplockBreakingHandler *,void * *)

- ea: `0x18038a620`
- end: `0x18038aa95`
- name: `?Create@CStorageFolderBase@@UEAAJPEBGW4HANDLE_CREATION_OPTIONS@@W4HANDLE_ACCESS_OPTIONS@@W4HANDLE_SHARING_OPTIONS@@W4HANDLE_OPTIONS@@PEAUIOplockBreakingHandler@@PEAPEAX@Z`
- size: `1141`
- prototype: `__int64 __fastcall(CStorageFolderBase *__hidden this, const unsigned __int16 *, enum HANDLE_CREATION_OPTIONS, enum HANDLE_ACCESS_OPTIONS, enum HANDLE_SHARING_OPTIONS, enum HANDLE_OPTIONS, struct IOplockBreakingHandler *, void **)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000ee68`
- `0x180010110`
- `0x180010220`
- `0x180036710`
- `0x180037294`
- `0x1800432f0`
- `0x18005f240`
- `0x18005f6c0`
- `0x180060a10`
- `0x180068eec`
- `0x1800d13a0`
- `0x1801a8784`
- `0x1802239b0`
- `0x180226c10`
- `0x18038a620`
- `0x18038aa9c`
- `0x18038aabc`
- `0x1803a4cb0`
- `0x1803ef8e0`
- `0x180419680`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrW` at `0x18038a8ed`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrW` at `0x18038a8ed`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsPrefixW` at `0x18038a8c0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsPrefixW` at `0x18038a8c0`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x18038a7f2`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x18038a7f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038a87a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038a9c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038a9dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038aa0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038aa1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038aa3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038a87a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038a9c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038a9dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038aa0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038aa1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038aa3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18038a73e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18038a73e`

## string_xrefs

- `0x18038a6c7`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18038a709`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18038a76a`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18038a814`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18038a85e`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18038a91f`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18038a9ab`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18038a66e`: `Create`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CStorageFolderBase::Create(
        CStorageFolderBase *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        enum HANDLE_SHARING_OPTIONS a5,
        enum HANDLE_OPTIONS a6,
        struct IOplockBreakingHandler *a7,
        void **a8)
{
  __int64 v12; // rdx
  int LastError; // edi
  PCWSTR StringRawBuffer; // rax
  int v15; // eax
  __int64 v16; // rdx
  __int64 File2; // rax
  const char *v18; // r9
  void *v19; // rsi
  int v20; // eax
  void *v21; // rcx
  WCHAR *v22; // rbx
  bool v23; // di
  __int64 v24; // rdx
  CStorageFolderBase *v25; // rcx
  int IsExecutableKind; // eax
  __int64 v27; // r9
  CallerIdentity *v28; // rax
  unsigned __int16 **v29; // rdx
  int v30; // eax
  __int64 v31; // rax
  void *v32; // rdi
  __int64 v33; // rdx
  int v35; // [rsp+20h] [rbp-E0h]
  bool v36; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v37; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v38; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v39[3]; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v41; // [rsp+68h] [rbp-98h] BYREF
  char v42; // [rsp+70h] [rbp-90h]
  void **v43; // [rsp+78h] [rbp-88h]
  _BYTE v44[16]; // [rsp+80h] [rbp-80h] BYREF
  int v45[4]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v46; // [rsp+A0h] [rbp-60h]
  HSTRING string[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v48[192]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v43 = a8;
  WinRTStorageTelemetry::WatchCurrentThread(v48, "Create", 0);
  *a8 = 0;
  if ( (a4 & 0xFFECFE60) != 0 )
  {
    v12 = 11078;
LABEL_7:
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)0x80070057LL,
      v35);
    goto LABEL_54;
  }
  if ( (a5 & 0xFFFFFFF8) != 0 )
  {
    v12 = 11079;
    goto LABEL_7;
  }
  if ( (a6 & 0x3FFFFFF) != 0 )
  {
    v12 = 11080;
    goto LABEL_7;
  }
  string[0] = 0;
  LastError = (*(__int64 (__fastcall **)(char *, HSTRING *))(*((_QWORD *)this - 56) + 96LL))((char *)this - 448, string);
  if ( LastError < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B4B,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)LastError,
      v35);
LABEL_10:
    Windows::Internal::String::~String((Windows::Internal::String *)string);
    goto LABEL_54;
  }
  memset(v39, 0, sizeof(v39));
  StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
  v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
          v39,
          StringRawBuffer,
          -1);
  LastError = v15;
  if ( v15 < 0 )
  {
    v16 = 11086;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v15,
      v35);
LABEL_14:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v39);
    goto LABEL_10;
  }
  v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(v39, L"\\");
  LastError = v15;
  if ( v15 < 0 )
  {
    v16 = 11087;
    goto LABEL_13;
  }
  v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(v39, a2);
  LastError = v15;
  if ( v15 < 0 )
  {
    v16 = 11088;
    goto LABEL_13;
  }
  v45[0] = 32;
  v45[1] = 128;
  v45[2] = a6;
  v45[3] = 0;
  v46 = 0;
  File2 = CreateFile2(v39[0], a4, (unsigned int)a5, a3);
  v19 = (void *)File2;
  v37 = File2;
  if ( ((File2 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2B5D,
                  (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
                  v18);
LABEL_21:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v37);
    goto LABEL_14;
  }
  pv = 0;
  v20 = wil::GetFinalPathNameByHandleW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
          File2,
          &pv,
          2);
  LastError = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B60,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v20,
      (int)v45);
    v21 = pv;
    if ( !pv )
      goto LABEL_21;
LABEL_24:
    CoTaskMemFree(v21);
    goto LABEL_21;
  }
  CStorageItem::AcquireLock((char *)this - 464, &v38);
  v22 = (WCHAR *)pv;
  v23 = (*((_QWORD *)this - 25)
      || (int)CStorageItem::SetFinalPathNameMember((CStorageFolderBase *)((char *)this - 464)) >= 0)
     && PathIsPrefixW(*((LPCWSTR *)this - 25), v22);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v38);
  if ( !v23 )
  {
    v24 = 11106;
LABEL_40:
    LastError = -2147024891;
    v27 = 2147942405LL;
    goto LABEL_35;
  }
  if ( StrStrW(v22, L":") )
  {
    v24 = 11107;
    goto LABEL_40;
  }
  v36 = 0;
  IsExecutableKind = CStorageFolderBase::ExtensionIsExecutableKind(v25, v22, &v36);
  LastError = IsExecutableKind;
  if ( IsExecutableKind < 0 )
  {
    v27 = (unsigned int)IsExecutableKind;
    v24 = 11110;
LABEL_35:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)v27,
      (int)v45);
LABEL_36:
    if ( !v22 )
      goto LABEL_21;
    v21 = v22;
    goto LABEL_24;
  }
  if ( !v36 )
  {
    v24 = 11111;
    goto LABEL_40;
  }
  if ( (a4 & 0x116) != 0 )
  {
    v41 = 0;
    v42 = 0;
    v28 = (CallerIdentity *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v41);
    CallerIdentity::GetCallingProcessPackageFamilyName(v28, v29);
    v38 = 0;
    v30 = wil::GetFinalPathNameByHandleW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
            v19,
            &v38,
            1);
    LastError = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B72,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
        (const char *)(unsigned int)v30,
        (int)v45);
      if ( v38 )
        CoTaskMemFree(v38);
      if ( v41 )
        CoTaskMemFree(v41);
      goto LABEL_36;
    }
    v31 = _lambda_9f1649e5d329bbae3177f8ca9d8c65fe_::_lambda_9f1649e5d329bbae3177f8ca9d8c65fe_(v44, &v41);
    v32 = v38;
    ModifyZoneIdentifierOnPath<_lambda_9f1649e5d329bbae3177f8ca9d8c65fe_>(v38, v33, v31);
    if ( v32 )
      CoTaskMemFree(v32);
    if ( v41 )
      CoTaskMemFree(v41);
  }
  v37 = -1;
  *v43 = v19;
  if ( v22 )
    CoTaskMemFree(v22);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v37);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v39);
  Windows::Internal::String::~String((Windows::Internal::String *)string);
  LastError = 0;
LABEL_54:
  StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)v48);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18038a620  push    rbp
0x18038a622  push    rbx
0x18038a623  push    rsi
0x18038a624  push    rdi
0x18038a625  push    r12
0x18038a627  push    r13
0x18038a629  push    r14
0x18038a62b  push    r15
0x18038a62d  lea     rbp, [rsp-98h]
0x18038a635  sub     rsp, 198h
0x18038a63c  mov     rax, cs:__security_cookie
0x18038a643  xor     rax, rsp
0x18038a646  mov     [rbp+0D0h+var_50], rax
0x18038a64d  mov     r15d, r9d
0x18038a650  mov     r13d, r8d
0x18038a653  mov     r12, rdx
0x18038a656  mov     r14, rcx
0x18038a659  mov     esi, [rbp+0D0h+arg_20]
0x18038a65f  mov     rbx, [rbp+0D0h+arg_38]
0x18038a666  mov     [rsp+1D0h+var_158], rbx
0x18038a66b  xor     r8d, r8d
0x18038a66e  lea     rdx, aCreate_0; "Create"
0x18038a675  lea     rcx, [rbp+0D0h+var_110]
0x18038a679  call    ?WatchCurrentThread@WinRTStorageTelemetry@@SA?AVActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@PEBD_N@Z; WinRTStorageTelemetry::WatchCurrentThread(char const *,bool)
0x18038a67e  nop
0x18038a67f  mov     qword ptr [rbx], 0
0x18038a686  test    r15d, 0FFECFE60h
0x18038a68d  jz      short loc_18038A696
0x18038a68f  mov     edx, 2B46h
0x18038a694  jmp     short loc_18038A6B8
0x18038a696  test    esi, 0FFFFFFF8h
0x18038a69c  jz      short loc_18038A6A5
0x18038a69e  mov     edx, 2B47h
0x18038a6a3  jmp     short loc_18038A6B8
0x18038a6a5  mov     ebx, [rbp+0D0h+arg_28]
0x18038a6ab  test    ebx, 3FFFFFFh
0x18038a6b1  jz      short loc_18038A6D8
0x18038a6b3  mov     edx, 2B48h; void *
0x18038a6b8  mov     edi, 80070057h
0x18038a6bd  mov     rcx, [rbp+0D8h]; this
0x18038a6c4  mov     r9d, edi; char *
0x18038a6c7  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18038a6ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18038a6d3  jmp     loc_18038AA67
0x18038a6d8  mov     [rbp+0D0h+string], 0
0x18038a6e0  lea     rcx, [r14-1C0h]
0x18038a6e7  mov     rax, [rcx]
0x18038a6ea  lea     rdx, [rbp+0D0h+string]
0x18038a6ee  mov     rax, [rax+60h]
0x18038a6f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038a6f7  mov     edi, eax
0x18038a6f9  xor     eax, eax
0x18038a6fb  test    edi, edi
0x18038a6fd  jns     short loc_18038A729
0x18038a6ff  mov     rcx, [rbp+0D8h]; this
0x18038a706  mov     r9d, edi; char *
0x18038a709  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18038a710  mov     edx, 2B4Bh; void *
0x18038a715  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18038a71a  nop
0x18038a71b  lea     rcx, [rbp+0D0h+string]; this
0x18038a71f  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18038a724  jmp     loc_18038AA67
0x18038a729  mov     [rsp+1D0h+var_188], rax
0x18038a72e  mov     [rsp+1D0h+var_180], rax
0x18038a733  mov     [rsp+1D0h+var_178], rax
0x18038a738  xor     edx, edx; length
0x18038a73a  mov     rcx, [rbp+0D0h+string]; string
0x18038a73e  call    cs:__imp_WindowsGetStringRawBuffer
0x18038a744  or      r8, 0FFFFFFFFFFFFFFFFh
0x18038a748  mov     rdx, rax
0x18038a74b  lea     rcx, [rsp+1D0h+var_188]
0x18038a750  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18038a755  mov     edi, eax
0x18038a757  test    eax, eax
0x18038a759  jns     short loc_18038A783
0x18038a75b  mov     edx, 2B4Eh; void *
0x18038a760  mov     rcx, [rbp+0D8h]; this
0x18038a767  mov     r9d, eax; char *
0x18038a76a  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18038a771  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18038a776  nop
0x18038a777  lea     rcx, [rsp+1D0h+var_188]; void *
0x18038a77c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18038a781  jmp     short loc_18038A71B
0x18038a783  lea     rdx, pszSrc; "\\"
0x18038a78a  lea     rcx, [rsp+1D0h+var_188]
0x18038a78f  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x18038a794  mov     edi, eax
0x18038a796  test    eax, eax
0x18038a798  jns     short loc_18038A7A1
0x18038a79a  mov     edx, 2B4Fh
0x18038a79f  jmp     short loc_18038A760
0x18038a7a1  mov     rdx, r12
0x18038a7a4  lea     rcx, [rsp+1D0h+var_188]
0x18038a7a9  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x18038a7ae  mov     edi, eax
0x18038a7b0  xor     r12d, r12d
0x18038a7b3  test    eax, eax
0x18038a7b5  jns     short loc_18038A7BE
0x18038a7b7  mov     edx, 2B50h
0x18038a7bc  jmp     short loc_18038A760
0x18038a7be  mov     [rbp+0D0h+var_140], 20h ; ' '
0x18038a7c5  mov     [rbp+0D0h+var_13C], 80h
0x18038a7cc  mov     [rbp+0D0h+var_138], ebx
0x18038a7cf  mov     [rbp+0D0h+var_134], r12d
0x18038a7d3  xorps   xmm0, xmm0
0x18038a7d6  movdqu  [rbp+0D0h+var_130], xmm0
0x18038a7db  lea     rax, [rbp+0D0h+var_140]
0x18038a7df  mov     qword ptr [rsp+1D0h+var_1B0], rax; int
0x18038a7e4  mov     r9d, r13d
0x18038a7e7  mov     r8d, esi
0x18038a7ea  mov     edx, r15d
0x18038a7ed  mov     rcx, [rsp+1D0h+var_188]
0x18038a7f2  call    cs:__imp_CreateFile2
0x18038a7f8  mov     rsi, rax
0x18038a7fb  mov     [rsp+1D0h+var_198], rax
0x18038a800  lea     rcx, [rax+1]
0x18038a804  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18038a80b  jnz     short loc_18038A836
0x18038a80d  mov     rcx, [rbp+0D8h]; this
0x18038a814  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18038a81b  mov     edx, 2B5Dh; void *
0x18038a820  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18038a825  mov     edi, eax
0x18038a827  lea     rcx, [rsp+1D0h+var_198]
0x18038a82c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18038a831  jmp     loc_18038A777
0x18038a836  mov     [rsp+1D0h+pv], r12
0x18038a83b  mov     r8d, 2
0x18038a841  lea     rdx, [rsp+1D0h+pv]
0x18038a846  mov     rcx, rsi
0x18038a849  call    ??$GetFinalPathNameByHandleW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@W4VolumePrefix@0@W4PathOptions@0@@Z; wil::GetFinalPathNameByHandleW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::VolumePrefix,wil::PathOptions)
0x18038a84e  mov     edi, eax
0x18038a850  test    eax, eax
0x18038a852  jns     short loc_18038A882
0x18038a854  mov     rcx, [rbp+0D8h]; this
0x18038a85b  mov     r9d, eax; char *
0x18038a85e  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18038a865  mov     edx, 2B60h; void *
0x18038a86a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18038a86f  nop
0x18038a870  mov     rcx, [rsp+1D0h+pv]; pv
0x18038a875  test    rcx, rcx
0x18038a878  jz      short loc_18038A827
0x18038a87a  call    cs:__imp_CoTaskMemFree
0x18038a880  jmp     short loc_18038A827
0x18038a882  lea     rdi, [r14-1D0h]
0x18038a889  lea     rdx, [rsp+1D0h+var_190]
0x18038a88e  mov     rcx, rdi
0x18038a891  call    ?AcquireLock@CStorageItem@@IEAA?AVSyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@XZ; CStorageItem::AcquireLock(void)
0x18038a896  nop
0x18038a897  mov     rbx, [rsp+1D0h+pv]
0x18038a89c  cmp     [r14-0C8h], r12
0x18038a8a3  jnz     short loc_18038A8B6
0x18038a8a5  mov     rcx, rdi; this
0x18038a8a8  call    ?SetFinalPathNameMember@CStorageItem@@QEAAJXZ; CStorageItem::SetFinalPathNameMember(void)
0x18038a8ad  test    eax, eax
0x18038a8af  jns     short loc_18038A8B6
0x18038a8b1  mov     dil, r12b
0x18038a8b4  jmp     short loc_18038A8CD
0x18038a8b6  mov     rdx, rbx; pszPath
0x18038a8b9  mov     rcx, [r14-0C8h]; pszPrefix
0x18038a8c0  call    cs:__imp_PathIsPrefixW
0x18038a8c6  nop
0x18038a8c7  test    eax, eax
0x18038a8c9  setnz   dil
0x18038a8cd  lea     rcx, [rsp+1D0h+var_190]; this
0x18038a8d2  call    ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
0x18038a8d7  test    dil, dil
0x18038a8da  jnz     short loc_18038A8E3
0x18038a8dc  mov     edx, 2B62h
0x18038a8e1  jmp     short loc_18038A950
0x18038a8e3  lea     rdx, asc_18070F4D0; ":"
0x18038a8ea  mov     rcx, rbx; pszFirst
0x18038a8ed  call    cs:__imp_StrStrW
0x18038a8f3  test    rax, rax
0x18038a8f6  jz      short loc_18038A8FF
0x18038a8f8  mov     edx, 2B63h
0x18038a8fd  jmp     short loc_18038A950
0x18038a8ff  mov     [rsp+1D0h+var_1A0], r12b
0x18038a904  lea     r8, [rsp+1D0h+var_1A0]; bool *
0x18038a909  mov     rdx, rbx; unsigned __int16 *
0x18038a90c  call    ?ExtensionIsExecutableKind@CStorageFolderBase@@IEAAJPEBGPEA_N@Z; CStorageFolderBase::ExtensionIsExecutableKind(ushort const *,bool *)
0x18038a911  mov     edi, eax
0x18038a913  test    eax, eax
0x18038a915  jns     short loc_18038A944
0x18038a917  mov     r9d, eax; char *
0x18038a91a  mov     edx, 2B66h; void *
0x18038a91f  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18038a926  mov     rcx, [rbp+0D8h]; this
0x18038a92d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18038a932  nop
0x18038a933  test    rbx, rbx
0x18038a936  jz      loc_18038A827
0x18038a93c  mov     rcx, rbx
0x18038a93f  jmp     loc_18038A87A
0x18038a944  cmp     [rsp+1D0h+var_1A0], r12b
0x18038a949  jnz     short loc_18038A95A
0x18038a94b  mov     edx, 2B67h
0x18038a950  mov     edi, 80070005h
0x18038a955  mov     r9d, edi
0x18038a958  jmp     short loc_18038A91F
0x18038a95a  test    r15d, 116h
0x18038a961  jz      loc_18038AA25
0x18038a967  mov     [rsp+1D0h+var_168], r12
0x18038a96c  mov     [rsp+1D0h+var_160], r12b
0x18038a971  lea     rcx, [rsp+1D0h+var_168]
0x18038a976  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18038a97b  mov     rcx, rax; this
0x18038a97e  call    ?GetCallingProcessPackageFamilyName@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessPackageFamilyName(ushort * *)
0x18038a983  mov     [rsp+1D0h+var_190], r12
0x18038a988  mov     r8d, 1
0x18038a98e  lea     rdx, [rsp+1D0h+var_190]
0x18038a993  mov     rcx, rsi
0x18038a996  call    ??$GetFinalPathNameByHandleW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@W4VolumePrefix@0@W4PathOptions@0@@Z; wil::GetFinalPathNameByHandleW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::VolumePrefix,wil::PathOptions)
0x18038a99b  mov     edi, eax
0x18038a99d  test    eax, eax
0x18038a99f  jns     short loc_18038A9E7
0x18038a9a1  mov     rcx, [rbp+0D8h]; this
0x18038a9a8  mov     r9d, eax; char *
0x18038a9ab  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18038a9b2  mov     edx, 2B72h; void *
0x18038a9b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18038a9bc  nop
0x18038a9bd  mov     rcx, [rsp+1D0h+var_190]; pv
0x18038a9c2  test    rcx, rcx
0x18038a9c5  jz      short loc_18038A9CE
0x18038a9c7  call    cs:__imp_CoTaskMemFree
0x18038a9cd  nop
0x18038a9ce  mov     rcx, [rsp+1D0h+var_168]; pv
0x18038a9d3  test    rcx, rcx
0x18038a9d6  jz      loc_18038A933
0x18038a9dc  call    cs:__imp_CoTaskMemFree
0x18038a9e2  jmp     loc_18038A933
0x18038a9e7  lea     rdx, [rsp+1D0h+var_168]
0x18038a9ec  lea     rcx, [rbp+0D0h+var_150]
0x18038a9f0  call    ??0_lambda_9f1649e5d329bbae3177f8ca9d8c65fe_@@QEAA@AEBV?$MoveOnCopy@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Internal@Windows@@@Z; _lambda_9f1649e5d329bbae3177f8ca9d8c65fe_::_lambda_9f1649e5d329bbae3177f8ca9d8c65fe_(Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> const &)
0x18038a9f5  mov     r8, rax
0x18038a9f8  mov     rdi, [rsp+1D0h+var_190]
0x18038a9fd  mov     rcx, rdi
0x18038aa00  call    ??$ModifyZoneIdentifierOnPath@V_lambda_9f1649e5d329bbae3177f8ca9d8c65fe_@@@@YAJPEBGW4SET_ZONE_ID_FLAGS@@V_lambda_9f1649e5d329bbae3177f8ca9d8c65fe_@@@Z; ModifyZoneIdentifierOnPath<_lambda_9f1649e5d329bbae3177f8ca9d8c65fe_>(ushort const *,SET_ZONE_ID_FLAGS,_lambda_9f1649e5d329bbae3177f8ca9d8c65fe_)
0x18038aa05  nop
0x18038aa06  test    rdi, rdi
0x18038aa09  jz      short loc_18038AA15
0x18038aa0b  mov     rcx, rdi; pv
0x18038aa0e  call    cs:__imp_CoTaskMemFree
0x18038aa14  nop
0x18038aa15  mov     rcx, [rsp+1D0h+var_168]; pv
0x18038aa1a  test    rcx, rcx
0x18038aa1d  jz      short loc_18038AA25
0x18038aa1f  call    cs:__imp_CoTaskMemFree
0x18038aa25  mov     [rsp+1D0h+var_198], 0FFFFFFFFFFFFFFFFh
0x18038aa2e  mov     rax, [rsp+1D0h+var_158]
0x18038aa33  mov     [rax], rsi
0x18038aa36  test    rbx, rbx
0x18038aa39  jz      short loc_18038AA45
0x18038aa3b  mov     rcx, rbx; pv
0x18038aa3e  call    cs:__imp_CoTaskMemFree
0x18038aa44  nop
0x18038aa45  lea     rcx, [rsp+1D0h+var_198]
0x18038aa4a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18038aa4f  nop
0x18038aa50  lea     rcx, [rsp+1D0h+var_188]; void *
0x18038aa55  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18038aa5a  nop
0x18038aa5b  lea     rcx, [rbp+0D0h+string]; this
0x18038aa5f  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18038aa64  mov     edi, r12d
0x18038aa67  lea     rcx, [rbp+0D0h+var_110]; this
0x18038aa6b  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x18038aa70  mov     eax, edi
0x18038aa72  mov     rcx, [rbp+0D0h+var_50]
0x18038aa79  xor     rcx, rsp; StackCookie
0x18038aa7c  call    __security_check_cookie
0x18038aa81  add     rsp, 198h
0x18038aa88  pop     r15
0x18038aa8a  pop     r14
0x18038aa8c  pop     r13
0x18038aa8e  pop     r12
0x18038aa90  pop     rdi
0x18038aa91  pop     rsi
0x18038aa92  pop     rbx
0x18038aa93  pop     rbp
0x18038aa94  retn
```
