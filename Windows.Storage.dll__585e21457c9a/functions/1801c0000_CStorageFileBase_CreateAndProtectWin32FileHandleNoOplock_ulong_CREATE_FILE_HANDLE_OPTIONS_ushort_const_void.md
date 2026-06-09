# CStorageFileBase::CreateAndProtectWin32FileHandleNoOplock(ulong,CREATE_FILE_HANDLE_OPTIONS,ushort const *,void * *)

- ea: `0x1801c0000`
- end: `0x1801c0365`
- name: `?CreateAndProtectWin32FileHandleNoOplock@CStorageFileBase@@UEAAJKW4CREATE_FILE_HANDLE_OPTIONS@@PEBGPEAPEAX@Z`
- size: `869`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x18000d6cc`
- `0x18000ee68`
- `0x180010110`
- `0x180010220`
- `0x18001b390`
- `0x18002f650`
- `0x1800432f0`
- `0x180060a10`
- `0x1800c2f14`
- `0x1800c39dc`
- `0x18014d4e0`
- `0x1801c0000`
- `0x1801c036c`
- `0x1801dffa0`
- `0x180348990`
- `0x1803a4cb0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801c035a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801c035a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18064d977`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18064d977`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801c01de`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18064d911`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801c01de`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18064d911`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c0221`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c02e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c0221`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c02e2`
- `efswrt!EnterpriseDataProtect` at `0x18064d9a6`
- `efswrt!EnterpriseDataProtect` at `0x18064d9a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801c01b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18064d8ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18064d996`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801c01b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18064d8ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18064d996`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c0143`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c0249`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c02a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c02ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c0143`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c0249`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c02a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c02ed`

## string_xrefs

- `0x1801c00b9`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x1801c0233`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x1801c028d`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18064d936`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18064d9be`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x1801c0113`: `CreateAndProtectWin32FileHandleNoOplockAsync`
- `0x18064da20`: `This file cannot be protected. It may be compressed, read-only, cert-based EFS protected, etc.`
- `0x18064da3b`: `This file was already protected to an enterprise ID, but the protection has been revoked.`
- `0x18064da05`: `This file is already protected to an EDP identity; it cannot have a new one applied.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CStorageFileBase::CreateAndProtectWin32FileHandleNoOplock(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        _QWORD *a5)
{
  struct Windows::System::IUser *RawUser; // rax
  int v10; // eax
  __int64 v11; // r8
  unsigned int v12; // ebx
  __int64 v13; // rcx
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rbx
  int v16; // eax
  void *v17; // rbx
  unsigned int v18; // r14d
  DWORD v19; // r15d
  __int64 v20; // rsi
  const WCHAR *v21; // rax
  char *v22; // rax
  unsigned int LastError; // edi
  __int64 v24; // rcx
  __int64 v25; // rcx
  const WCHAR *StringRawBuffer; // rax
  HANDLE FileW; // rax
  const char *v28; // r9
  unsigned int v29; // r9d
  unsigned int v30; // r8d
  const WCHAR *v31; // rdx
  PCWSTR v32; // rax
  int v33; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  __int64 v36; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v37; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+70h] [rbp-90h]
  int v41[2]; // [rsp+78h] [rbp-88h] BYREF
  HSTRING string; // [rsp+80h] [rbp-80h] BYREF
  int v43; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v44[88]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v45[104]; // [rsp+E8h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  *a5 = 0;
  v37 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  RawUser = CStorageItem::GetRawUser((CStorageItem *)(a1 - 432));
  v38 = (a1 - 304) & -(__int64)(a1 != 432);
  *(_QWORD *)v41 = RawUser;
  v43 = 0;
  LODWORD(v36) = 2;
  v10 = Microsoft::WRL::Details::MakeAndInitialize<CapturedCallerContext,Windows::Internal::ICapturedCallerContext,enum Windows::Internal::MuaApiUserPolicy &,enum Windows::Internal::MuaApiUserPolicyFlags &,IUnknown * &,Windows::System::IUser * &>(
          (unsigned int)&v37,
          (unsigned int)&v36,
          (unsigned int)&v43,
          (unsigned int)&v38,
          (__int64)v41);
  v12 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3042,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v10,
      dwCreationDisposition);
    v13 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return v12;
  }
  LOBYTE(v11) = 1;
  WinRTStorageTelemetry::WatchCurrentThread(v44, "CreateAndProtectWin32FileHandleNoOplockAsync", v11);
  Microsoft::WRL::ComPtr<IStream>::operator=(v45, v37);
  string = 0;
  v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)(a1 - 416) + 96LL);
  WindowsDeleteString(0);
  string = 0;
  v16 = v15(a1 - 416, &string);
  v12 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3048,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v16,
      dwCreationDisposition);
    WindowsDeleteString(string);
    string = 0;
    StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)v44);
    v24 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    return v12;
  }
  v17 = 0;
  v36 = 0;
  if ( a4 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v38,
      a4,
      -1);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v36,
      v38);
    v17 = (void *)v36;
    if ( !v36 )
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x304E,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
        (const char *)0x8007000ELL,
        dwCreationDisposition);
      goto LABEL_14;
    }
  }
  v18 = a2 != 0 ? 0xFFFFFFFE : 0;
  v19 = a2 != 0 ? -1073741824 : 0x80000000;
  v20 = -1;
  v36 = -1;
  if ( v17 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    FileW = CreateFileW(StringRawBuffer, 0, 7u, 0, 3u, 0, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v36,
      FileW);
    v20 = v36;
    if ( v36 == -1 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x3075,
                    (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
                    v28);
LABEL_28:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v36);
      goto LABEL_10;
    }
    v43 = 0;
    v32 = WindowsGetStringRawBuffer(string, 0);
    v33 = EnterpriseDataProtect(v32, v17, &v43);
    LastError = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3078,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
        (const char *)(unsigned int)v33,
        dwCreationDispositiona);
      goto LABEL_28;
    }
    switch ( v43 )
    {
      case 3:
        goto LABEL_8;
      case 2:
        v40 = 0;
        v29 = 89;
        v30 = 90;
        v31 = L"This file was already protected to an enterprise ID, but the protection has been revoked.";
        break;
      case 4:
      case 5:
        goto LABEL_37;
      case 6:
        v40 = 0;
        v29 = 94;
        v30 = 95;
        v31 = L"This file cannot be protected. It may be compressed, read-only, cert-based EFS protected, etc.";
        break;
      case 7:
LABEL_37:
        v40 = 0;
        v29 = 84;
        v30 = 85;
        v31 = L"This file is already protected to an EDP identity; it cannot have a new one applied.";
        break;
      default:
        v40 = 0;
        v29 = 43;
        v30 = 44;
        v31 = L"Could not protect the file: Reason unknown.";
        break;
    }
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, v31, v30, v29);
    LastError = -2146893015;
    RoOriginateError(2148074281LL, v40);
    goto LABEL_28;
  }
LABEL_8:
  v21 = WindowsGetStringRawBuffer(string, 0);
  v22 = (char *)CreateFileW(v21, v19, v18 + 7, 0, 3u, a3 & 0x40000000, 0);
  v38 = (__int64)v22;
  if ( ((unsigned __int64)(v22 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = wil::details::GetLastErrorFailHr((wil::details *)(v22 + 1));
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v36);
    if ( !v17 )
    {
LABEL_14:
      WindowsDeleteString(string);
      string = 0;
      StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)v44);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
      return LastError;
    }
LABEL_10:
    CoTaskMemFree(v17);
    goto LABEL_14;
  }
  *a5 = v22;
  if ( (unsigned __int64)(v20 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v20);
  if ( v17 )
    CoTaskMemFree(v17);
  WindowsDeleteString(string);
  string = 0;
  StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)v44);
  v25 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  return 0;
}

```

## disassembly

```asm
0x1801c0000  mov     [rsp-8+arg_8], rbx
0x1801c0005  push    rbp
0x1801c0006  push    rsi
0x1801c0007  push    rdi
0x1801c0008  push    r12
0x1801c000a  push    r13
0x1801c000c  push    r14
0x1801c000e  push    r15
0x1801c0010  lea     rbp, [rsp-60h]
0x1801c0015  sub     rsp, 160h
0x1801c001c  mov     rax, cs:__security_cookie
0x1801c0023  xor     rax, rsp
0x1801c0026  mov     [rbp+90h+var_40], rax
0x1801c002a  mov     r14, r9
0x1801c002d  mov     r12d, r8d
0x1801c0030  mov     esi, edx
0x1801c0032  mov     rdi, rcx
0x1801c0035  mov     r13, [rbp+90h+arg_20]
0x1801c003c  xor     r15d, r15d
0x1801c003f  mov     [r13+0], r15
0x1801c0043  mov     [rsp+190h+var_148], r15
0x1801c0048  lea     rcx, [rsp+190h+var_148]
0x1801c004d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c0052  lea     rbx, [rdi-1B0h]
0x1801c0059  mov     rcx, rbx; this
0x1801c005c  call    ?GetRawUser@CStorageItem@@IEAAPEAUIUser@System@Windows@@XZ; CStorageItem::GetRawUser(void)
0x1801c0061  lea     rdx, [rdi-130h]
0x1801c0068  neg     rbx
0x1801c006b  sbb     rcx, rcx
0x1801c006e  and     rcx, rdx
0x1801c0071  mov     [rsp+190h+var_140], rcx
0x1801c0076  mov     qword ptr [rsp+190h+var_118], rax
0x1801c007b  mov     [rbp+90h+var_108], r15d
0x1801c007f  mov     dword ptr [rsp+190h+var_150], 2
0x1801c0087  lea     rax, [rsp+190h+var_118]
0x1801c008c  mov     qword ptr [rsp+190h+dwCreationDisposition], rax; int
0x1801c0091  lea     r9, [rsp+190h+var_140]
0x1801c0096  lea     r8, [rbp+90h+var_108]
0x1801c009a  lea     rdx, [rsp+190h+var_150]
0x1801c009f  lea     rcx, [rsp+190h+var_148]
0x1801c00a4  call    ??$MakeAndInitialize@VCapturedCallerContext@@UICapturedCallerContext@Internal@Windows@@AEAW4MuaApiUserPolicy@34@AEAW4MuaApiUserPolicyFlags@34@AEAPEAUIUnknown@@AEAPEAUIUser@System@4@@Details@WRL@Microsoft@@YAJPEAPEAUICapturedCallerContext@Internal@Windows@@AEAW4MuaApiUserPolicy@45@AEAW4MuaApiUserPolicyFlags@45@AEAPEAUIUnknown@@AEAPEAUIUser@System@5@@Z; Microsoft::WRL::Details::MakeAndInitialize<CapturedCallerContext,Windows::Internal::ICapturedCallerContext,Windows::Internal::MuaApiUserPolicy &,Windows::Internal::MuaApiUserPolicyFlags &,IUnknown * &,Windows::System::IUser * &>(Windows::Internal::ICapturedCallerContext * *,Windows::Internal::MuaApiUserPolicy &,Windows::Internal::MuaApiUserPolicyFlags &,IUnknown * &,Windows::System::IUser * &)
0x1801c00a9  mov     ebx, eax
0x1801c00ab  test    eax, eax
0x1801c00ad  jns     short loc_1801C0110
0x1801c00af  mov     rcx, [rbp+98h]; this
0x1801c00b6  mov     r9d, eax; char *
0x1801c00b9  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x1801c00c0  mov     edx, 3042h; void *
0x1801c00c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c00ca  nop
0x1801c00cb  mov     rcx, [rsp+190h+var_148]
0x1801c00d0  test    rcx, rcx
0x1801c00d3  jz      short loc_1801C00E7
0x1801c00d5  mov     [rsp+190h+var_148], r15
0x1801c00da  mov     rax, [rcx]
0x1801c00dd  mov     rax, [rax+10h]
0x1801c00e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c00e6  nop
0x1801c00e7  mov     eax, ebx
0x1801c00e9  mov     rcx, [rbp+90h+var_40]
0x1801c00ed  xor     rcx, rsp; StackCookie
0x1801c00f0  call    __security_check_cookie
0x1801c00f5  mov     rbx, [rsp+190h+arg_8]
0x1801c00fd  add     rsp, 160h
0x1801c0104  pop     r15
0x1801c0106  pop     r14
0x1801c0108  pop     r13
0x1801c010a  pop     r12
0x1801c010c  pop     rdi
0x1801c010d  pop     rsi
0x1801c010e  pop     rbp
0x1801c010f  retn
0x1801c0110  mov     r8b, 1
0x1801c0113  lea     rdx, aCreateandprote_0; "CreateAndProtectWin32FileHandleNoOplock"...
0x1801c011a  lea     rcx, [rbp+90h+var_100]
0x1801c011e  call    ?WatchCurrentThread@WinRTStorageTelemetry@@SA?AVActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@PEBD_N@Z; WinRTStorageTelemetry::WatchCurrentThread(char const *,bool)
0x1801c0123  nop
0x1801c0124  mov     rdx, [rsp+190h+var_148]
0x1801c0129  lea     rcx, [rbp+90h+var_A8]
0x1801c012d  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x1801c0132  mov     [rbp+90h+string], r15
0x1801c0136  mov     rax, [rdi-1A0h]
0x1801c013d  mov     rbx, [rax+60h]
0x1801c0141  xor     ecx, ecx; string
0x1801c0143  call    cs:__imp_WindowsDeleteString
0x1801c0149  mov     [rbp+90h+string], r15
0x1801c014d  lea     rdx, [rbp+90h+string]
0x1801c0151  lea     rcx, [rdi-1A0h]
0x1801c0158  mov     rax, rbx
0x1801c015b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c0160  mov     ebx, eax
0x1801c0162  xor     edi, edi
0x1801c0164  test    eax, eax
0x1801c0166  js      loc_1801C0229
0x1801c016c  mov     ebx, edi
0x1801c016e  mov     [rsp+190h+var_150], rbx
0x1801c0173  test    r14, r14
0x1801c0176  jnz     loc_1801C0324
0x1801c017c  mov     eax, esi
0x1801c017e  neg     eax
0x1801c0180  sbb     r14d, r14d
0x1801c0183  and     r14d, 0FFFFFFFEh
0x1801c0187  neg     esi
0x1801c0189  sbb     r15d, r15d
0x1801c018c  and     r15d, 40000000h
0x1801c0193  add     r15d, 80000000h
0x1801c019a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1801c019e  mov     [rsp+190h+var_150], rsi
0x1801c01a3  test    rbx, rbx
0x1801c01a6  jnz     loc_18064D8E8
0x1801c01ac  xor     edx, edx; length
0x1801c01ae  mov     rcx, [rbp+90h+string]; string
0x1801c01b2  call    cs:__imp_WindowsGetStringRawBuffer
0x1801c01b8  and     r12d, 40000000h
0x1801c01bf  mov     [rsp+190h+hTemplateFile], rdi; hTemplateFile
0x1801c01c4  mov     [rsp+190h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x1801c01c9  mov     [rsp+190h+dwCreationDisposition], 3; dwCreationDisposition
0x1801c01d1  xor     r9d, r9d; lpSecurityAttributes
0x1801c01d4  lea     r8d, [r14+7]; dwShareMode
0x1801c01d8  mov     edx, r15d; dwDesiredAccess
0x1801c01db  mov     rcx, rax; lpFileName
0x1801c01de  call    cs:__imp_CreateFileW
0x1801c01e4  mov     [rsp+190h+var_140], rax
0x1801c01e9  lea     rcx, [rax+1]; this
0x1801c01ed  test    rcx, 0FFFFFFFFFFFFFFFEh
0x1801c01f4  jnz     loc_1801C02CC
0x1801c01fa  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1801c01ff  mov     edi, eax
0x1801c0201  lea     rcx, [rsp+190h+var_140]
0x1801c0206  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801c020b  lea     rcx, [rsp+190h+var_150]
0x1801c0210  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801c0215  test    rbx, rbx
0x1801c0218  jz      loc_1801C029F
0x1801c021e  mov     rcx, rbx; pv
0x1801c0221  call    cs:__imp_CoTaskMemFree
0x1801c0227  jmp     short loc_1801C029F
0x1801c0229  mov     rcx, [rbp+98h]; this
0x1801c0230  mov     r9d, ebx; char *
0x1801c0233  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x1801c023a  mov     edx, 3048h; void *
0x1801c023f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c0244  nop
0x1801c0245  mov     rcx, [rbp+90h+string]; string
0x1801c0249  call    cs:__imp_WindowsDeleteString
0x1801c024f  mov     [rbp+90h+string], rdi
0x1801c0253  lea     rcx, [rbp+90h+var_100]; this
0x1801c0257  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x1801c025c  nop
0x1801c025d  mov     rcx, [rsp+190h+var_148]
0x1801c0262  test    rcx, rcx
0x1801c0265  jz      short loc_1801C0279
0x1801c0267  mov     [rsp+190h+var_148], rdi
0x1801c026c  mov     rax, [rcx]
0x1801c026f  mov     rax, [rax+10h]
0x1801c0273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c0278  nop
0x1801c0279  jmp     loc_1801C00E7
0x1801c027e  mov     rcx, [rbp+98h]; this
0x1801c0285  mov     edi, 8007000Eh
0x1801c028a  mov     r9d, edi; char *
0x1801c028d  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x1801c0294  mov     edx, 304Eh; void *
0x1801c0299  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c029e  nop
0x1801c029f  mov     rcx, [rbp+90h+string]; string
0x1801c02a3  call    cs:__imp_WindowsDeleteString
0x1801c02a9  mov     [rbp+90h+string], 0
0x1801c02b1  lea     rcx, [rbp+90h+var_100]; this
0x1801c02b5  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x1801c02ba  nop
0x1801c02bb  lea     rcx, [rsp+190h+var_148]
0x1801c02c0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c02c5  mov     eax, edi
0x1801c02c7  jmp     loc_1801C00E9
0x1801c02cc  mov     [r13+0], rax
0x1801c02d0  lea     rax, [rsi-1]
0x1801c02d4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801c02d8  jbe     short loc_1801C0357
0x1801c02da  test    rbx, rbx
0x1801c02dd  jz      short loc_1801C02E9
0x1801c02df  mov     rcx, rbx; pv
0x1801c02e2  call    cs:__imp_CoTaskMemFree
0x1801c02e8  nop
0x1801c02e9  mov     rcx, [rbp+90h+string]; string
0x1801c02ed  call    cs:__imp_WindowsDeleteString
0x1801c02f3  mov     [rbp+90h+string], rdi
0x1801c02f7  lea     rcx, [rbp+90h+var_100]; this
0x1801c02fb  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x1801c0300  nop
0x1801c0301  mov     rcx, [rsp+190h+var_148]
0x1801c0306  test    rcx, rcx
0x1801c0309  jz      short loc_1801C031D
0x1801c030b  mov     [rsp+190h+var_148], rdi
0x1801c0310  mov     rax, [rcx]
0x1801c0313  mov     rax, [rax+10h]
0x1801c0317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c031c  nop
0x1801c031d  xor     eax, eax
0x1801c031f  jmp     loc_1801C00E9
0x1801c0324  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801c0328  mov     rdx, r14
0x1801c032b  lea     rcx, [rsp+190h+var_140]
0x1801c0330  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1801c0335  mov     rdx, [rsp+190h+var_140]
0x1801c033a  lea     rcx, [rsp+190h+var_150]
0x1801c033f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1801c0344  mov     rbx, [rsp+190h+var_150]
0x1801c0349  test    rbx, rbx
0x1801c034c  jnz     loc_1801C017C
0x1801c0352  jmp     loc_1801C027E
0x1801c0357  mov     rcx, rsi; hObject
0x1801c035a  call    cs:__imp_CloseHandle
0x1801c0360  jmp     loc_1801C02DA
0x18064d8e8  xor     edx, edx; length
0x18064d8ea  mov     rcx, [rbp+90h+string]; string
0x18064d8ee  call    cs:__imp_WindowsGetStringRawBuffer
0x18064d8f4  mov     [rsp+190h+hTemplateFile], rdi; hTemplateFile
0x18064d8f9  mov     [rsp+190h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x18064d8fd  mov     [rsp+190h+dwCreationDisposition], 3; int
0x18064d905  xor     r9d, r9d; lpSecurityAttributes
0x18064d908  xor     edx, edx; dwDesiredAccess
0x18064d90a  lea     r8d, [r9+7]; dwShareMode
0x18064d90e  mov     rcx, rax; lpFileName
0x18064d911  call    cs:__imp_CreateFileW
0x18064d917  mov     rdx, rax
0x18064d91a  lea     rcx, [rsp+190h+var_150]
0x18064d91f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18064d924  mov     rsi, [rsp+190h+var_150]
0x18064d929  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18064d92d  jnz     short loc_18064D98D
0x18064d92f  mov     rcx, [rbp+98h]; this
0x18064d936  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18064d93d  mov     edx, 3075h; void *
0x18064d942  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18064d947  mov     edi, eax
0x18064d949  jmp     short loc_18064D97D
0x18064d94b  mov     [rsp+190h+var_120], rdx
0x18064d950  mov     r9d, 2Bh ; '+'; unsigned int
0x18064d956  lea     r8d, [r9+1]; unsigned int
0x18064d95a  lea     rdx, aCouldNotProtec; "Could not protect the file: Reason unkn"...
0x18064d961  lea     rcx, [rsp+190h+hstringHeader]; hstringHeader
0x18064d966  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18064d96b  mov     rdx, [rsp+190h+var_120]
0x18064d970  mov     edi, 80090329h
0x18064d975  mov     ecx, edi
0x18064d977  call    cs:__imp_RoOriginateError
0x18064d97d  lea     rcx, [rsp+190h+var_150]
0x18064d982  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18064d987  nop
0x18064d988  jmp     loc_1801C021E
0x18064d98d  mov     [rbp+90h+var_108], edi
0x18064d990  xor     edx, edx; length
0x18064d992  mov     rcx, [rbp+90h+string]; string
0x18064d996  call    cs:__imp_WindowsGetStringRawBuffer
0x18064d99c  lea     r8, [rbp+90h+var_108]
0x18064d9a0  mov     rdx, rbx
0x18064d9a3  mov     rcx, rax
0x18064d9a6  call    cs:__imp_EnterpriseDataProtect
0x18064d9ac  mov     edi, eax
0x18064d9ae  xor     edx, edx
0x18064d9b0  test    eax, eax
0x18064d9b2  jns     short loc_18064D9D1
0x18064d9b4  mov     rcx, [rbp+98h]; this
0x18064d9bb  mov     r9d, eax; char *
0x18064d9be  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18064d9c5  mov     edx, 3078h; void *
0x18064d9ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18064d9cf  jmp     short loc_18064D97D
0x18064d9d1  mov     ecx, [rbp+90h+var_108]
0x18064d9d4  cmp     ecx, 3
0x18064d9d7  jz      short loc_18064DA47
0x18064d9d9  sub     ecx, 2
0x18064d9dc  jz      short loc_18064DA2C
0x18064d9de  sub     ecx, 2
0x18064d9e1  jz      short loc_18064D9F6
0x18064d9e3  sub     ecx, 1
0x18064d9e6  jz      short loc_18064D9F6
0x18064d9e8  sub     ecx, 1
0x18064d9eb  jz      short loc_18064DA11
0x18064d9ed  cmp     ecx, 1
0x18064d9f0  jnz     loc_18064D94B
0x18064d9f6  mov     [rsp+190h+var_120], rdx
0x18064d9fb  mov     r9d, 54h ; 'T'
0x18064da01  lea     r8d, [r9+1]
0x18064da05  lea     rdx, aThisFileIsAlre; "This file is already protected to an ED"...
0x18064da0c  jmp     loc_18064D961
0x18064da11  mov     [rsp+190h+var_120], rdx
0x18064da16  mov     r9d, 5Eh ; '^'
0x18064da1c  lea     r8d, [r9+1]
0x18064da20  lea     rdx, aThisFileCannot; "This file cannot be protected. It may b"...
0x18064da27  jmp     loc_18064D961
0x18064da2c  mov     [rsp+190h+var_120], rdx
0x18064da31  mov     r9d, 59h ; 'Y'
0x18064da37  lea     r8d, [r9+1]
0x18064da3b  lea     rdx, aThisFileWasAlr; "This file was already protected to an e"...
0x18064da42  jmp     loc_18064D961
0x18064da47  xor     edi, edi
0x18064da49  jmp     loc_1801C01AC
```
