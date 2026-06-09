# Windows::Storage::StateABIHelpers::EnsureFolderAccessible(Microsoft::WRL::ComPtr<Windows::Storage::IStorageFolder>,Windows::System::IUser *)

- ea: `0x18001d43c`
- end: `0x18001d7d1`
- name: `?EnsureFolderAccessible@StateABIHelpers@Storage@Windows@@YAJV?$ComPtr@UIStorageFolder@Storage@Windows@@@WRL@Microsoft@@PEAUIUser@System@3@@Z`
- size: `917`
- prototype: `HRESULT __fastcall(Microsoft::WRL::ComPtr<Windows::Storage::IStorageFolder> storageFolder, Windows::System::IUser *userParam)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180036c9c`
- `0x18003e5f4`

## callees

- `0x180001008`
- `0x180001144`
- `0x180001d64`
- `0x180003820`
- `0x1800093d0`
- `0x180009778`
- `0x180018fb8`
- `0x18001d3cc`
- `0x18001d43c`
- `0x18001fc18`
- `0x1800207c0`
- `0x180029440`
- `0x180029bfc`
- `0x180040ccc`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d529`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d567`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d5b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d60e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d649`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d69b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d6fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d78a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d7a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d529`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d567`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d5b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d60e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d649`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d69b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d6fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d78a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d7a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d4c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d514`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d71c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d4c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d514`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d71c`

## string_xrefs

- `0x18001d49e`: `onecoreuap\base\appmodel\statemanager\winrt\lib\stateabicommonhelpers.cpp`
- `0x18001d4ff`: `onecoreuap\base\appmodel\statemanager\winrt\lib\stateabicommonhelpers.cpp`
- `0x18001d551`: `onecoreuap\base\appmodel\statemanager\winrt\lib\stateabicommonhelpers.cpp`
- `0x18001d4f0`: `get_Path`
- `0x18001d57c`: `Path %ws`
- `0x18001d653`: `Path %ws`
- `0x18001d750`: `Path %ws`
- `0x18001d6c9`: `EnsureFolderAccessible`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::EnsureFolderAccessible(
        Microsoft::WRL::ComPtr<Windows::Storage::IStorageFolder> storageFolder,
        Windows::System::IUser *userParam)
{
  Windows::Storage::IStorageFolder_vtbl *v2; // rdi
  __int64 (__fastcall *v5)(Windows::Storage::IStorageFolder_vtbl *, GUID *, Microsoft::WRL::ComPtr<Windows::Storage::IStorageItem> *); // rbx
  HRESULT v6; // ebx
  Windows::Storage::IStorageItem *ptr; // rdi
  HRESULT (__fastcall *get_Path)(Windows::Storage::IStorageItem *, HSTRING__ **); // rbx
  Windows::System::IUser *StringRawBuffer; // rax
  const wchar_t *v10; // rcx
  HRESULT v11; // eax
  PCWSTR v12; // rax
  const _tlgProvider_t *v13; // rcx
  const wchar_t *v14; // rax
  const _tlgProvider_t *v15; // rcx
  const _GUID *v16; // r8
  const _GUID *v17; // r9
  HRESULT fixed; // eax
  Windows::System::IUser *v19; // rax
  const wchar_t *v20; // rcx
  PCWSTR v21; // rax
  const _tlgProvider_t *v22; // rcx
  PCWSTR v23; // rax
  const _tlgProvider_t *v24; // rcx
  const _GUID *v25; // r8
  const _GUID *v26; // r9
  HRESULT v27; // eax
  Windows::System::IUser *v28; // rax
  const wchar_t *v29; // rcx
  const wchar_t *v31; // rax
  PCWSTR v32; // rax
  Microsoft::WRL::ComPtr<Windows::Storage::IStorageItem> spStorageItem; // [rsp+30h] [rbp-10h] BYREF
  _tlgWrapperByVal<8> pEventMetadata; // [rsp+38h] [rbp-8h] BYREF
  void *retaddr; // [rsp+68h] [rbp+28h]
  _tlgWrapSz<unsigned short> v36; // [rsp+80h] [rbp+40h] BYREF
  Microsoft::WRL::Wrappers::HString path; // [rsp+88h] [rbp+48h] BYREF

  v2 = storageFolder.ptr_->__vftable;
  spStorageItem.ptr_ = 0;
  v5 = *(__int64 (__fastcall **)(Windows::Storage::IStorageFolder_vtbl *, GUID *, Microsoft::WRL::ComPtr<Windows::Storage::IStorageItem> *))v2->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&spStorageItem);
  v6 = v5(v2, &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30, &spStorageItem);
  if ( v6 >= 0 )
  {
    ptr = spStorageItem.ptr_;
    path.hstr_ = 0;
    get_Path = spStorageItem.ptr_->get_Path;
    WindowsDeleteString(0);
    path.hstr_ = 0;
    v6 = get_Path(ptr, &path.hstr_);
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x1ECu,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabicommonhelpers.cpp",
        v6,
        "get_Path");
LABEL_5:
      WindowsDeleteString(path.hstr_);
LABEL_23:
      path.hstr_ = 0;
      goto LABEL_24;
    }
    StringRawBuffer = (Windows::System::IUser *)WindowsGetStringRawBuffer(path.hstr_, 0);
    v11 = lambda_6481a59ea0aa371205527dd2ce870ff9_::operator()(v10, StringRawBuffer, (bool *)userParam);
    v6 = v11;
    if ( v11 == -2147024713 )
      goto LABEL_22;
    if ( v11 == -2147024891 )
    {
      v12 = WindowsGetStringRawBuffer(path.hstr_, 0);
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        0x20Eu,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabicommonhelpers.cpp",
        -2147024891,
        "Path %ws",
        v12);
      if ( Tlgg_hStateManagerTraceProviderProv.LevelPlus1 > 5 && tlgKeywordOn(v13, 0x400000000000uLL) )
      {
        v14 = WindowsGetStringRawBuffer(path.hstr_, 0);
        pEventMetadata.Value = 0x1000000;
        v36.Psz = v14;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          v15,
          &tlgEvent_1._tlgChannel,
          v16,
          v17,
          &pEventMetadata,
          &v36);
      }
      fixed = Windows::Storage::StateABIHelpers::FixStateLocationsAccess(userParam);
      if ( fixed < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          0x216u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabicommonhelpers.cpp",
          fixed);
LABEL_16:
        v21 = WindowsGetStringRawBuffer(path.hstr_, 0);
        wil::details::in1diag3::Log_Win32Msg(
          retaddr,
          0x229u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabicommonhelpers.cpp",
          2u,
          "Path %ws",
          v21);
        if ( Tlgg_hStateManagerTraceProviderProv.LevelPlus1 > 5 && tlgKeywordOn(v22, 0x400000000000uLL) )
        {
          v23 = WindowsGetStringRawBuffer(path.hstr_, 0);
          LODWORD(v36.Psz) = v6;
          pEventMetadata.Value = (const unsigned __int64)v23;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
            v24,
            &tlgEvent_0._tlgChannel,
            v25,
            v26,
            (const _tlgWrapperByVal<4> *)&v36,
            (const _tlgWrapSz<unsigned short> *)&pEventMetadata);
        }
        v27 = Windows::Storage::StateABIHelpers::RepairStateLocations(L"EnsureFolderAccessible", -2147024894, userParam);
        if ( v27 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            0x232u,
            "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabicommonhelpers.cpp",
            v27);
          goto LABEL_25;
        }
        v28 = (Windows::System::IUser *)WindowsGetStringRawBuffer(path.hstr_, 0);
        v6 = lambda_6481a59ea0aa371205527dd2ce870ff9_::operator()(v29, v28, (bool *)userParam);
        if ( v6 != -2147024713 )
          goto LABEL_25;
LABEL_22:
        WindowsDeleteString(path.hstr_);
        v6 = 0;
        goto LABEL_23;
      }
      v19 = (Windows::System::IUser *)WindowsGetStringRawBuffer(path.hstr_, 0);
      v6 = lambda_6481a59ea0aa371205527dd2ce870ff9_::operator()(v20, v19, (bool *)userParam);
      if ( v6 == -2147024713 )
        goto LABEL_22;
    }
    if ( v6 < 0 && v6 != -2147024891 )
    {
LABEL_25:
      if ( v6 >= 0 )
        v6 = -2147024894;
      else
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          0x23Cu,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabicommonhelpers.cpp",
          v6);
      v31 = WindowsGetStringRawBuffer(path.hstr_, 0);
      Windows::Storage::StateABIHelpers::Logging::LogFolderPathAccessCheckFailure(v31, v6);
      v32 = WindowsGetStringRawBuffer(path.hstr_, 0);
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x244u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabicommonhelpers.cpp",
        v6,
        "Path %ws",
        v32);
      goto LABEL_5;
    }
    goto LABEL_16;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    0x1E9u,
    "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabicommonhelpers.cpp",
    v6,
    "As");
LABEL_24:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&spStorageItem);
  Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Storage::IApplicationDataContainer> *)storageFolder.ptr_);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001d43c  mov     [rsp-28h+arg_8], rbx
0x18001d441  push    rbp
0x18001d442  push    rsi
0x18001d443  push    rdi
0x18001d444  push    r12
0x18001d446  push    r14
0x18001d448  mov     rbp, rsp
0x18001d44b  sub     rsp, 40h
0x18001d44f  mov     rdi, [storageFolder]
0x18001d452  mov     r14, storageFolder
0x18001d455  mov     [rbp+spStorageItem.ptr_], 0
0x18001d45d  lea     storageFolder, [rbp+spStorageItem]; this
0x18001d461  mov     rsi, userParam
0x18001d464  mov     rax, [rdi]
0x18001d467  mov     rbx, [rax]
0x18001d46a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d46f  lea     r8, [rbp+spStorageItem]
0x18001d473  mov     storageFolder, rdi
0x18001d476  lea     userParam, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x18001d47d  mov     rax, rbx
0x18001d480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d485  mov     ebx, eax
0x18001d487  test    eax, eax
0x18001d489  jns     short loc_18001D4B4
0x18001d48b  mov     storageFolder, [rbp+28h]; callerReturnAddress
0x18001d48f  lea     rax, aAs; "As"
0x18001d496  mov     r9d, ebx; hr
0x18001d499  mov     [rsp+40h+formatString], rax; formatString
0x18001d49e  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\statemanage"...
0x18001d4a5  mov     edx, 1E9h; lineNumber
0x18001d4aa  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001d4af  jmp     loc_18001D72C
0x18001d4b4  mov     rdi, [rbp+spStorageItem.ptr_]
0x18001d4b8  xor     ecx, ecx; string
0x18001d4ba  mov     [rbp+path.hstr_], 0
0x18001d4c2  mov     rax, [rdi]
0x18001d4c5  mov     rbx, [rax+60h]
0x18001d4c9  call    cs:__imp_WindowsDeleteString
0x18001d4cf  lea     userParam, [rbp+path]
0x18001d4d3  mov     [rbp+path.hstr_], 0
0x18001d4db  mov     storageFolder, rdi
0x18001d4de  mov     rax, rbx
0x18001d4e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4e6  mov     ebx, eax
0x18001d4e8  test    eax, eax
0x18001d4ea  jns     short loc_18001D51F
0x18001d4ec  mov     storageFolder, [rbp+28h]; callerReturnAddress
0x18001d4f0  lea     rax, aGetPath; "get_Path"
0x18001d4f7  mov     r9d, ebx; hr
0x18001d4fa  mov     [rsp+40h+formatString], rax; formatString
0x18001d4ff  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\statemanage"...
0x18001d506  mov     edx, 1ECh; lineNumber
0x18001d50b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001d510  mov     storageFolder, [rbp+path.hstr_]; string
0x18001d514  call    cs:__imp_WindowsDeleteString
0x18001d51a  jmp     loc_18001D724
0x18001d51f  mov     storageFolder, [rbp+path.hstr_]; string
0x18001d523  xor     edx, edx; length
0x18001d525  mov     [rbp+fileExists], 0
0x18001d529  call    cs:__imp_WindowsGetStringRawBuffer
0x18001d52f  lea     r9, [rbp+fileExists]
0x18001d533  mov     r8, rsi; fileExists
0x18001d536  mov     userParam, rax; user
0x18001d539  call    _lambda_6481a59ea0aa371205527dd2ce870ff9___operator__
0x18001d53e  mov     ebx, eax
0x18001d540  cmp     eax, 800700B7h
0x18001d545  jz      loc_18001D718
0x18001d54b  mov     r12d, 80070005h
0x18001d551  lea     rdi, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\statemanage"...
0x18001d558  cmp     eax, r12d
0x18001d55b  jnz     loc_18001D630
0x18001d561  mov     storageFolder, [rbp+path.hstr_]; string
0x18001d565  xor     edx, edx; length
0x18001d567  call    cs:__imp_WindowsGetStringRawBuffer
0x18001d56d  mov     storageFolder, [rbp+28h]; callerReturnAddress
0x18001d571  mov     r9d, r12d; hr
0x18001d574  mov     [rsp+40h+var_18], rax
0x18001d579  mov     r8, rdi; fileName
0x18001d57c  lea     rax, aPathWs; "Path %ws"
0x18001d583  mov     edx, 20Eh; lineNumber
0x18001d588  mov     [rsp+40h+formatString], rax; formatString
0x18001d58d  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001d592  mov     eax, cs:_Tlgg_hStateManagerTraceProviderProv.LevelPlus1
0x18001d598  cmp     eax, 5
0x18001d59b  jbe     short loc_18001D5E6
0x18001d59d  mov     userParam, 400000000000h; hProvider
0x18001d5a7  call    _tlgKeywordOn
0x18001d5ac  test    al, al
0x18001d5ae  jz      short loc_18001D5E6
0x18001d5b0  mov     storageFolder, [rbp+path.hstr_]; __annotation("_TlgWrite:|532|g_hStateManagerTraceProvider|"AppDataPathAccessDenied"=|"PartA_PrivTags"=|"Path"=Path")
0x18001d5b4  xor     edx, edx; length
0x18001d5b6  call    cs:__imp_WindowsGetStringRawBuffer
0x18001d5bc  lea     userParam, _tlgEvent_1._tlgChannel; <wrappedArgs_0>
0x18001d5c3  mov     [rbp+pEventMetadata.Value], 1000000h
0x18001d5cb  mov     [rbp+arg_10.Psz], rax
0x18001d5cf  lea     rax, [rbp+arg_10]
0x18001d5d3  mov     [rsp+40h+var_18], rax; <writerArgs_0>
0x18001d5d8  lea     rax, [rbp+pEventMetadata]
0x18001d5dc  mov     [rsp+40h+formatString], rax; pEventMetadata
0x18001d5e1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18001d5e6  mov     storageFolder, rsi; userParam
0x18001d5e9  call    ?FixStateLocationsAccess@StateABIHelpers@Storage@Windows@@YAJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::FixStateLocationsAccess(Windows::System::IUser *)
0x18001d5ee  test    eax, eax
0x18001d5f0  jns     short loc_18001D608
0x18001d5f2  mov     storageFolder, [rbp+28h]; callerReturnAddress
0x18001d5f6  mov     r9d, eax; hr
0x18001d5f9  mov     r8, rdi; fileName
0x18001d5fc  mov     edx, 216h; lineNumber
0x18001d601  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d606  jmp     short loc_18001D643
0x18001d608  mov     storageFolder, [rbp+path.hstr_]; string
0x18001d60c  xor     edx, edx; length
0x18001d60e  call    cs:__imp_WindowsGetStringRawBuffer
0x18001d614  lea     r9, [rbp+fileExists]
0x18001d618  mov     r8, rsi; fileExists
0x18001d61b  mov     userParam, rax; user
0x18001d61e  call    _lambda_6481a59ea0aa371205527dd2ce870ff9___operator__
0x18001d623  mov     ebx, eax
0x18001d625  cmp     eax, 800700B7h
0x18001d62a  jz      loc_18001D718
0x18001d630  test    ebx, ebx
0x18001d632  js      short loc_18001D63A
0x18001d634  cmp     [rbp+fileExists], 0
0x18001d638  jz      short loc_18001D643
0x18001d63a  cmp     ebx, r12d
0x18001d63d  jnz     loc_18001D750
0x18001d643  mov     storageFolder, [rbp+path.hstr_]; string
0x18001d647  xor     edx, edx; length
0x18001d649  call    cs:__imp_WindowsGetStringRawBuffer
0x18001d64f  mov     storageFolder, [rbp+28h]; callerReturnAddress
0x18001d653  lea     r12, aPathWs; "Path %ws"
0x18001d65a  mov     [rsp+40h+var_18], rax
0x18001d65f  mov     r9d, 2; err
0x18001d665  mov     r8, rdi; fileName
0x18001d668  mov     [rsp+40h+formatString], r12; formatString
0x18001d66d  mov     edx, 229h; lineNumber
0x18001d672  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18001d677  mov     eax, cs:_Tlgg_hStateManagerTraceProviderProv.LevelPlus1
0x18001d67d  cmp     eax, 5
0x18001d680  jbe     short loc_18001D6C6
0x18001d682  mov     userParam, 400000000000h; hProvider
0x18001d68c  call    _tlgKeywordOn
0x18001d691  test    al, al
0x18001d693  jz      short loc_18001D6C6
0x18001d695  mov     storageFolder, [rbp+path.hstr_]; __annotation("_TlgWrite:|559|g_hStateManagerTraceProvider|"AppDataPathNotFound"=|"hrFileExists"=|"Path"=Path")
0x18001d699  xor     edx, edx; length
0x18001d69b  call    cs:__imp_WindowsGetStringRawBuffer
0x18001d6a1  lea     userParam, _tlgEvent_0._tlgChannel; <wrappedArgs_0>
0x18001d6a8  mov     dword ptr [rbp+arg_10.Psz], ebx
0x18001d6ab  mov     [rbp+pEventMetadata.Value], rax
0x18001d6af  lea     rax, [rbp+pEventMetadata]
0x18001d6b3  mov     [rsp+40h+var_18], rax; <writerArgs_0>
0x18001d6b8  lea     rax, [rbp+arg_10]
0x18001d6bc  mov     [rsp+40h+formatString], rax; pEventMetadata
0x18001d6c1  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18001d6c6  mov     r8, rsi; userParam
0x18001d6c9  lea     storageFolder, aEnsurefolderac_0; "EnsureFolderAccessible"
0x18001d6d0  mov     edx, 80070002h; inputHr
0x18001d6d5  call    ?RepairStateLocations@StateABIHelpers@Storage@Windows@@YAJPEBGJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::RepairStateLocations(ushort const *,long,Windows::System::IUser *)
0x18001d6da  test    eax, eax
0x18001d6dc  jns     short loc_18001D6F4
0x18001d6de  mov     storageFolder, [rbp+28h]; callerReturnAddress
0x18001d6e2  mov     r9d, eax; hr
0x18001d6e5  mov     r8, rdi; fileName
0x18001d6e8  mov     edx, 232h; lineNumber
0x18001d6ed  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d6f2  jmp     short loc_18001D757
0x18001d6f4  mov     storageFolder, [rbp+path.hstr_]; string
0x18001d6f8  xor     edx, edx; length
0x18001d6fa  call    cs:__imp_WindowsGetStringRawBuffer
0x18001d700  lea     r9, [rbp+fileExists]
0x18001d704  mov     r8, rsi; fileExists
0x18001d707  mov     userParam, rax; user
0x18001d70a  call    _lambda_6481a59ea0aa371205527dd2ce870ff9___operator__
0x18001d70f  mov     ebx, eax
0x18001d711  cmp     eax, 800700B7h
0x18001d716  jnz     short loc_18001D757
0x18001d718  mov     storageFolder, [rbp+path.hstr_]; string
0x18001d71c  call    cs:__imp_WindowsDeleteString
0x18001d722  xor     ebx, ebx
0x18001d724  mov     [rbp+path.hstr_], 0
0x18001d72c  lea     storageFolder, [rbp+spStorageItem]; this
0x18001d730  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d735  mov     storageFolder, r14; this
0x18001d738  call    ?InternalRelease@?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>::InternalRelease(void)
0x18001d73d  mov     eax, ebx
0x18001d73f  mov     rbx, [rsp+40h+arg_8]
0x18001d744  add     rsp, 40h
0x18001d748  pop     r14
0x18001d74a  pop     r12
0x18001d74c  pop     rdi
0x18001d74d  pop     rsi
0x18001d74e  pop     rbp
0x18001d74f  retn
0x18001d750  lea     r12, aPathWs; "Path %ws"
0x18001d757  test    ebx, ebx
0x18001d759  jns     short loc_18001D771
0x18001d75b  mov     storageFolder, [rbp+28h]; callerReturnAddress
0x18001d75f  mov     r9d, ebx; hr
0x18001d762  mov     r8, rdi; fileName
0x18001d765  mov     edx, 23Ch; lineNumber
0x18001d76a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d76f  jmp     short loc_18001D784
0x18001d771  mov     al, [rbp+fileExists]
0x18001d774  neg     al
0x18001d776  sbb     ebx, ebx
0x18001d778  and     ebx, 0B5h
0x18001d77e  add     ebx, 80070002h
0x18001d784  mov     storageFolder, [rbp+path.hstr_]; string
0x18001d788  xor     edx, edx; length
0x18001d78a  call    cs:__imp_WindowsGetStringRawBuffer
0x18001d790  mov     storageFolder, rax; folderPath
0x18001d793  mov     edx, ebx; errorCode
0x18001d795  call    ?LogFolderPathAccessCheckFailure@Logging@StateABIHelpers@Storage@Windows@@SAJPEBGJ@Z; Windows::Storage::StateABIHelpers::Logging::LogFolderPathAccessCheckFailure(ushort const *,long)
0x18001d79a  test    ebx, ebx
0x18001d79c  jns     loc_18001D718
0x18001d7a2  mov     storageFolder, [rbp+path.hstr_]; string
0x18001d7a6  xor     edx, edx; length
0x18001d7a8  call    cs:__imp_WindowsGetStringRawBuffer
0x18001d7ae  mov     storageFolder, [rbp+28h]; callerReturnAddress
0x18001d7b2  mov     r9d, ebx; hr
0x18001d7b5  mov     [rsp+40h+var_18], rax
0x18001d7ba  mov     r8, rdi; fileName
0x18001d7bd  mov     edx, 244h; lineNumber
0x18001d7c2  mov     [rsp+40h+formatString], r12; formatString
0x18001d7c7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001d7cc  jmp     loc_18001D510
```
