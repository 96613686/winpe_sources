# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::CreateTemporaryFileHandlesForPreferredPdl(void)

- ea: `0x180042dc8`
- end: `0x18004303c`
- name: `?CreateTemporaryFileHandlesForPreferredPdl@PrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAAXXZ`
- size: `628`
- prototype: `void __fastcall(winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *this, __int64, int, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180042b5c`

## callees

- `0x180001614`
- `0x180001984`
- `0x1800097ec`
- `0x1800127a4`
- `0x1800129dc`
- `0x180012b10`
- `0x18001a7c0`
- `0x18002141c`
- `0x180021c14`
- `0x180023664`
- `0x180032528`
- `0x180042dc8`
- `0x180043758`
- `0x180044f90`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180042e8b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180042ee2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180042f39`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180042e8b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180042ee2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180042f39`

## string_xrefs

- `0x180042fdf`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportvirtualprintersession.cpp`
- `0x180042ff4`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportvirtualprintersession.cpp`
- `0x180043006`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportvirtualprintersession.cpp`
- `0x180043018`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportvirtualprintersession.cpp`
- `0x18004302a`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportvirtualprintersession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::CreateTemporaryFileHandlesForPreferredPdl(
        winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *this,
        __int64 a2,
        int a3,
        int a4)
{
  int CallerIntegrityLevel; // eax
  __int64 v6; // rax
  const WCHAR *v7; // rax
  HANDLE FileW; // rax
  const char *v9; // r9
  const WCHAR *v10; // rax
  HANDLE v11; // rax
  const char *v12; // r9
  const WCHAR *v13; // rax
  HANDLE v14; // rax
  const char *v15; // r9
  WCHAR *v16; // rax
  int v17; // eax
  int v18; // r8d
  int v19; // r9d
  int dwCreationDisposition; // [rsp+20h] [rbp-20h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  unsigned int v23; // [rsp+60h] [rbp+20h] BYREF
  char v24; // [rsp+68h] [rbp+28h] BYREF
  char v25; // [rsp+70h] [rbp+30h] BYREF
  const unsigned __int16 *v26; // [rsp+78h] [rbp+38h] BYREF

  if ( (unsigned int)dword_180083000 > 5 )
  {
    v23 = *((_DWORD *)this + 54);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180083000,
      (unsigned int)byte_180074BA3,
      a3,
      a4,
      (__int64)&v23);
  }
  PrintSupportSessionCommon::EnsureWorkflowTempFolder(this, &v25);
  v23 = 4096;
  CallerIntegrityLevel = GetCallerIntegrityLevel(&v23);
  if ( CallerIntegrityLevel < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EB,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportvirtualprintersession.cpp",
      (const char *)(unsigned int)CallerIntegrityLevel,
      dwCreationDisposition);
  v6 = winrt::impl::consume_Windows_Storage_IStorageItem<winrt::Windows::Storage::IStorageFile>::Path(&v25, &v26);
  winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::GetPreferredPdlTempFileName(
    this,
    &v24,
    v6);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v26);
  v7 = winrt::hstring::c_str((winrt::hstring *)&v24);
  FileW = CreateFileW(v7, 0xC0000000, 5u, 0, 1u, 0x4000100u, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 440,
    FileW);
  if ( *((_QWORD *)this + 55) == -1 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1F1,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportvirtualprintersession.cpp",
      v9);
  v10 = winrt::hstring::c_str((winrt::hstring *)&v24);
  v11 = CreateFileW(v10, 0x80000000, 7u, 0, 3u, 0x4000100u, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 448,
    v11);
  if ( *((_QWORD *)this + 56) == -1 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1F5,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportvirtualprintersession.cpp",
      v12);
  v13 = winrt::hstring::c_str((winrt::hstring *)&v24);
  v14 = CreateFileW(v13, 0x80000000, 7u, 0, 3u, 0x4000100u, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 456,
    v14);
  if ( *((_QWORD *)this + 57) == -1 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1F9,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportvirtualprintersession.cpp",
      v15);
  if ( v23 <= 0x1000 )
  {
    v16 = (WCHAR *)winrt::hstring::c_str((winrt::hstring *)&v24);
    v17 = ApplyLowSecurityLabel(v16);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1FE,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportvirtualprintersession.cpp",
        (const char *)(unsigned int)v17,
        dwCreationDispositiona);
  }
  if ( (unsigned int)dword_180083000 > 5 )
  {
    v23 = *((_DWORD *)this + 54);
    v26 = winrt::hstring::c_str((winrt::hstring *)&v24);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180083000,
      (unsigned int)word_180074C0A,
      v18,
      v19,
      (__int64)&v26,
      (__int64)&v23);
  }
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v24);
  winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow((winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow *)&v25);
}

```

## disassembly

```asm
0x180042dc8  push    rbp
0x180042dca  push    rbx
0x180042dcb  push    rdi
0x180042dcc  mov     rbp, rsp
0x180042dcf  sub     rsp, 40h
0x180042dd3  mov     rdi, rcx
0x180042dd6  mov     eax, cs:dword_180083000
0x180042ddc  cmp     eax, 5
0x180042ddf  jbe     short loc_180042E06
0x180042de1  mov     eax, [rcx+0D8h]
0x180042de7  mov     [rbp+arg_0], eax
0x180042dea  lea     rax, [rbp+arg_0]
0x180042dee  mov     qword ptr [rsp+40h+dwCreationDisposition], rax; int
0x180042df3  lea     rdx, byte_180074BA3
0x180042dfa  lea     rcx, dword_180083000
0x180042e01  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180042e06  lea     rdx, [rbp+arg_10]
0x180042e0a  call    ?EnsureWorkflowTempFolder@PrintSupportSessionCommon@@IEAA?AUStorageFolder@Storage@Windows@winrt@@XZ; PrintSupportSessionCommon::EnsureWorkflowTempFolder(void)
0x180042e0f  nop
0x180042e10  mov     [rbp+arg_0], 1000h
0x180042e17  lea     rcx, [rbp+arg_0]; unsigned int *
0x180042e1b  call    ?GetCallerIntegrityLevel@@YAJAEAK@Z; GetCallerIntegrityLevel(ulong &)
0x180042e20  mov     rcx, [rbp+18h]; this
0x180042e24  test    eax, eax
0x180042e26  js      loc_180042FF1
0x180042e2c  lea     rdx, [rbp+arg_18]
0x180042e30  lea     rcx, [rbp+arg_10]
0x180042e34  call    ?Path@?$consume_Windows_Storage_IStorageItem@UIStorageFile@Storage@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Storage_IStorageItem<winrt::Windows::Storage::IStorageFile>::Path(void)
0x180042e39  nop
0x180042e3a  mov     r8, rax
0x180042e3d  lea     rdx, [rbp+arg_8]
0x180042e41  mov     rcx, rdi
0x180042e44  call    ?GetPreferredPdlTempFileName@PrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAA?AUhstring@8@AEBU98@@Z; winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::GetPreferredPdlTempFileName(winrt::hstring const &)
0x180042e49  nop
0x180042e4a  lea     rcx, [rbp+arg_18]
0x180042e4e  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180042e53  lea     rbx, [rdi+1B8h]
0x180042e5a  lea     rcx, [rbp+arg_8]; this
0x180042e5e  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180042e63  mov     rcx, rax; lpFileName
0x180042e66  mov     [rsp+40h+hTemplateFile], 0; hTemplateFile
0x180042e6f  mov     [rsp+40h+dwFlagsAndAttributes], 4000100h; dwFlagsAndAttributes
0x180042e77  mov     [rsp+40h+dwCreationDisposition], 1; dwCreationDisposition
0x180042e7f  xor     r9d, r9d; lpSecurityAttributes
0x180042e82  mov     edx, 0C0000000h; dwDesiredAccess
0x180042e87  lea     r8d, [r9+5]; dwShareMode
0x180042e8b  call    cs:__imp_CreateFileW
0x180042e91  mov     rdx, rax
0x180042e94  mov     rcx, rbx
0x180042e97  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180042e9c  mov     rcx, [rbp+18h]; this
0x180042ea0  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180042ea4  jz      loc_180043006
0x180042eaa  lea     rbx, [rdi+1C0h]
0x180042eb1  lea     rcx, [rbp+arg_8]; this
0x180042eb5  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180042eba  mov     rcx, rax; lpFileName
0x180042ebd  mov     [rsp+40h+hTemplateFile], 0; hTemplateFile
0x180042ec6  mov     [rsp+40h+dwFlagsAndAttributes], 4000100h; dwFlagsAndAttributes
0x180042ece  mov     [rsp+40h+dwCreationDisposition], 3; dwCreationDisposition
0x180042ed6  xor     r9d, r9d; lpSecurityAttributes
0x180042ed9  mov     edx, 80000000h; dwDesiredAccess
0x180042ede  lea     r8d, [r9+7]; dwShareMode
0x180042ee2  call    cs:__imp_CreateFileW
0x180042ee8  mov     rdx, rax
0x180042eeb  mov     rcx, rbx
0x180042eee  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180042ef3  mov     rcx, [rbp+18h]; this
0x180042ef7  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180042efb  jz      loc_180043018
0x180042f01  lea     rbx, [rdi+1C8h]
0x180042f08  lea     rcx, [rbp+arg_8]; this
0x180042f0c  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180042f11  mov     rcx, rax; lpFileName
0x180042f14  mov     [rsp+40h+hTemplateFile], 0; hTemplateFile
0x180042f1d  mov     [rsp+40h+dwFlagsAndAttributes], 4000100h; dwFlagsAndAttributes
0x180042f25  mov     [rsp+40h+dwCreationDisposition], 3; int
0x180042f2d  xor     r9d, r9d; lpSecurityAttributes
0x180042f30  mov     edx, 80000000h; dwDesiredAccess
0x180042f35  lea     r8d, [r9+7]; dwShareMode
0x180042f39  call    cs:__imp_CreateFileW
0x180042f3f  mov     rdx, rax
0x180042f42  mov     rcx, rbx
0x180042f45  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180042f4a  mov     rcx, [rbp+18h]; this
0x180042f4e  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180042f52  jz      loc_18004302A
0x180042f58  cmp     [rbp+arg_0], 1000h
0x180042f5f  ja      short loc_180042F7A
0x180042f61  lea     rcx, [rbp+arg_8]; this
0x180042f65  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180042f6a  mov     rcx, rax; pObjectName
0x180042f6d  call    ?ApplyLowSecurityLabel@@YAJPEBG@Z; ApplyLowSecurityLabel(ushort const *)
0x180042f72  mov     rcx, [rbp+18h]; this
0x180042f76  test    eax, eax
0x180042f78  js      short loc_180042FDC
0x180042f7a  mov     eax, cs:dword_180083000
0x180042f80  cmp     eax, 5
0x180042f83  jbe     short loc_180042FC1
0x180042f85  mov     eax, [rdi+0D8h]
0x180042f8b  mov     [rbp+arg_0], eax
0x180042f8e  lea     rcx, [rbp+arg_8]; this
0x180042f92  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180042f97  mov     [rbp+arg_18], rax
0x180042f9b  lea     rax, [rbp+arg_0]
0x180042f9f  mov     qword ptr [rsp+40h+dwFlagsAndAttributes], rax
0x180042fa4  lea     rax, [rbp+arg_18]
0x180042fa8  mov     qword ptr [rsp+40h+dwCreationDisposition], rax
0x180042fad  lea     rdx, word_180074C0A
0x180042fb4  lea     rcx, dword_180083000
0x180042fbb  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180042fc0  nop
0x180042fc1  lea     rcx, [rbp+arg_8]
0x180042fc5  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180042fca  nop
0x180042fcb  lea     rcx, [rbp+arg_10]; this
0x180042fcf  call    ??1IWindow@WindowManagement@ApplicationModel@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow(void)
0x180042fd4  add     rsp, 40h
0x180042fd8  pop     rdi
0x180042fd9  pop     rbx
0x180042fda  pop     rbp
0x180042fdb  retn
0x180042fdc  mov     r9d, eax; char *
0x180042fdf  lea     r8, aOnecoreuapPrin_20; "onecoreuap\\printscan\\print\\workflow"...
0x180042fe6  mov     edx, 1FEh; void *
0x180042feb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180042ff1  mov     r9d, eax; char *
0x180042ff4  lea     r8, aOnecoreuapPrin_20; "onecoreuap\\printscan\\print\\workflow"...
0x180042ffb  mov     edx, 1EBh; void *
0x180043000  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180043006  lea     r8, aOnecoreuapPrin_20; "onecoreuap\\printscan\\print\\workflow"...
0x18004300d  mov     edx, 1F1h; void *
0x180043012  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180043018  lea     r8, aOnecoreuapPrin_20; "onecoreuap\\printscan\\print\\workflow"...
0x18004301f  mov     edx, 1F5h; void *
0x180043024  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18004302a  lea     r8, aOnecoreuapPrin_20; "onecoreuap\\printscan\\print\\workflow"...
0x180043031  mov     edx, 1F9h; void *
0x180043036  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
