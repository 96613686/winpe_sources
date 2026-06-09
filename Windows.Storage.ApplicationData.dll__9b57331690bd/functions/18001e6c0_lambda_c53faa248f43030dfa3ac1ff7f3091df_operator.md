# _lambda_c53faa248f43030dfa3ac1ff7f3091df_::operator()

- ea: `0x18001e6c0`
- end: `0x18001e9ac`
- name: `_lambda_c53faa248f43030dfa3ac1ff7f3091df_::operator()`
- size: `748`
- prototype: `HRESULT __fastcall()`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017250`

## callees

- `0x180003820`
- `0x180007280`
- `0x180009778`
- `0x18001c71c`
- `0x18001e6c0`
- `0x180021efc`
- `0x180041620`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e7c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e7c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7b0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e71b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e827`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e71b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e827`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001e702`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001e80e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001e702`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001e80e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e848`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e89a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e917`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e848`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e89a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e917`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e7bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e7bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18001e837`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18001e837`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001e8db`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001e8db`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001e750`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001e750`

## string_xrefs

- `0x18001e930`: `Read %ws`
- `0x18001e877`: `BuildPropertyKeyByUserSid`

## pseudocode

```c
__int64 __fastcall lambda_c53faa248f43030dfa3ac1ff7f3091df_::operator()(__int64 a1)
{
  HRESULT ActivationFactory; // ebx
  Windows::ApplicationModel::Core::ICoreApplication *ptr; // rcx
  HSTRING *v5; // rsi
  HSTRING v6; // r14
  DWORD LastError; // ebx
  HSTRING v8; // r14
  PCWSTR StringRawBuffer; // rax
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *v10; // rbx
  const wchar_t *v11; // rax
  unsigned __int8 v12; // r8
  int v13; // eax
  PCWSTR v14; // rax
  __int64 *v15; // rax
  __int64 v16; // rdx
  Windows::ApplicationModel::Core::ICoreApplication *v17; // rcx
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplication> appObject; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-20h] BYREF
  void *retaddr; // [rsp+78h] [rbp+18h]

  appObject.ptr_ = 0;
  if ( WindowsCreateStringReference(
         RuntimeClass_Windows_ApplicationModel_Core_CoreApplication,
         0x2Du,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(string, &GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1, &appObject);
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0xC3u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatafactory.server.cpp",
      ActivationFactory,
      "GetActivationFactory");
    goto LABEL_5;
  }
  v5 = *(HSTRING **)(a1 + 8);
  v6 = *v5;
  if ( *v5 )
  {
    LastError = GetLastError();
    WindowsDeleteString(v6);
    SetLastError(LastError);
  }
  *v5 = 0;
  v8 = **(HSTRING **)a1;
  if ( !v8 )
  {
    ActivationFactory = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x12Cu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatafactory.server.cpp",
      -2147024809);
LABEL_16:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0xC7u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatafactory.server.cpp",
      ActivationFactory,
      "BuildPropertyKeyByUserSid");
    goto LABEL_24;
  }
  if ( WindowsCreateStringReference(L"Windows.Storage.ApplicationData", 0x1Fu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = WindowsConcatString(string, v8, v5);
  if ( ActivationFactory < 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(v8, 0);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x12Fu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatafactory.server.cpp",
      ActivationFactory,
      "WindowsConcatString %ws",
      StringRawBuffer);
    goto LABEL_16;
  }
  v10 = *(Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> **)(a1 + 16);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v10);
  v11 = WindowsGetStringRawBuffer(**(HSTRING **)(a1 + 8), 0);
  v13 = Windows::Internal::StaticLifetimeStore::Read<Windows::Storage::IApplicationData>(
          appObject.ptr_,
          v11,
          v12,
          (Windows::Storage::IApplicationData **)v10);
  ActivationFactory = v13;
  if ( v13 < 0 )
  {
    if ( v13 == -2147483637 )
    {
LABEL_5:
      ptr = appObject.ptr_;
      if ( appObject.ptr_ )
      {
        appObject.ptr_ = 0;
        ptr->Release(ptr);
      }
      return (unsigned int)ActivationFactory;
    }
    if ( v13 == -2147024882 )
    {
      v14 = WindowsGetStringRawBuffer(**(HSTRING **)(a1 + 8), 0);
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0xE4u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatafactory.server.cpp",
        ActivationFactory,
        "Read %ws",
        v14);
    }
    else
    {
      if ( v13 == -2147417842 )
      {
        ActivationFactory = -2147009196;
        RoOriginateError(2147958100LL, 0);
      }
      SqmInsertAppDataObjectError(ActivationFactory);
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0xE1u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatafactory.server.cpp",
        ActivationFactory,
        "Read");
    }
LABEL_24:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&appObject);
    return (unsigned int)ActivationFactory;
  }
  v15 = *(__int64 **)(a1 + 16);
  v16 = *v15;
  *v15 = 0;
  ***(_QWORD ***)(a1 + 24) = v16;
  v17 = appObject.ptr_;
  if ( appObject.ptr_ )
  {
    appObject.ptr_ = 0;
    v17->Release(v17);
  }
  return 0;
}

```

## disassembly

```asm
0x18001e6c0  mov     [rsp-18h+arg_8], rbx
0x18001e6c5  mov     [rsp-18h+arg_10], rsi
0x18001e6ca  push    rbp
0x18001e6cb  push    rdi
0x18001e6cc  push    r14
0x18001e6ce  mov     rbp, rsp
0x18001e6d1  sub     rsp, 60h
0x18001e6d5  mov     rax, cs:__security_cookie
0x18001e6dc  xor     rax, rsp
0x18001e6df  mov     [rbp+var_8], rax
0x18001e6e3  mov     rdi, this
0x18001e6e6  mov     [rbp+appObject.ptr_], 0
0x18001e6ee  lea     this, ?RuntimeClass_Windows_ApplicationModel_Core_CoreApplication@@3QBGB; sourceString
0x18001e6f5  mov     edx, 2Dh ; '-'; length
0x18001e6fa  lea     r9, [rbp+string]; string
0x18001e6fe  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001e702  call    cs:__imp_WindowsCreateStringReference
0x18001e708  test    eax, eax
0x18001e70a  jns     short loc_18001E721
0x18001e70c  xor     r9d, r9d; lpArguments
0x18001e70f  xor     r8d, r8d; nNumberOfArguments
0x18001e712  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001e717  lea     edx, [r9+1]; dwExceptionFlags
0x18001e71b  call    cs:__imp_RaiseException
0x18001e721  mov     this, [rbp+appObject.ptr_]
0x18001e725  mov     rbx, [rbp+string]
0x18001e729  test    this, this
0x18001e72c  jz      short loc_18001E742
0x18001e72e  mov     [rbp+appObject.ptr_], 0
0x18001e736  mov     rax, [this]
0x18001e739  mov     rax, [rax+10h]
0x18001e73d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e742  lea     r8, [rbp+appObject]
0x18001e746  mov     this, rbx
0x18001e749  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x18001e750  call    cs:__imp_RoGetActivationFactory
0x18001e756  mov     ebx, eax
0x18001e758  test    eax, eax
0x18001e75a  jns     short loc_18001E7A4
0x18001e75c  mov     this, [rbp+18h]; callerReturnAddress
0x18001e760  lea     rax, aGetactivationf_0; "GetActivationFactory"
0x18001e767  mov     r9d, ebx; hr
0x18001e76a  mov     [rsp+60h+formatString], rax; formatString
0x18001e76f  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\statemanage"...
0x18001e776  mov     edx, 0C3h; lineNumber
0x18001e77b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001e780  mov     this, [rbp+appObject.ptr_]
0x18001e784  test    this, this
0x18001e787  jz      short loc_18001E79D
0x18001e789  mov     [rbp+appObject.ptr_], 0
0x18001e791  mov     rax, [this]
0x18001e794  mov     rax, [rax+10h]
0x18001e798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e79d  mov     eax, ebx
0x18001e79f  jmp     loc_18001E98B
0x18001e7a4  mov     rsi, [rdi+8]
0x18001e7a8  mov     r14, [rsi]
0x18001e7ab  test    r14, r14
0x18001e7ae  jz      short loc_18001E7C9
0x18001e7b0  call    cs:__imp_GetLastError
0x18001e7b6  mov     this, r14; string
0x18001e7b9  mov     ebx, eax
0x18001e7bb  call    cs:__imp_WindowsDeleteString
0x18001e7c1  mov     ecx, ebx; dwErrCode
0x18001e7c3  call    cs:__imp_SetLastError
0x18001e7c9  mov     qword ptr [rsi], 0
0x18001e7d0  mov     rax, [rdi]
0x18001e7d3  mov     r14, [rax]
0x18001e7d6  test    r14, r14
0x18001e7d9  jnz     short loc_18001E7FA
0x18001e7db  mov     this, [rbp+18h]; callerReturnAddress
0x18001e7df  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\statemanage"...
0x18001e7e6  mov     ebx, 80070057h
0x18001e7eb  mov     edx, 12Ch; lineNumber
0x18001e7f0  mov     r9d, ebx; hr
0x18001e7f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e7f8  jmp     short loc_18001E877
0x18001e7fa  lea     r9, [rbp+string]; string
0x18001e7fe  mov     edx, 1Fh; length
0x18001e803  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001e807  lea     this, ?RuntimeClass_Windows_Storage_ApplicationData@@3QBGB; "Windows.Storage.ApplicationData"
0x18001e80e  call    cs:__imp_WindowsCreateStringReference
0x18001e814  test    eax, eax
0x18001e816  jns     short loc_18001E82D
0x18001e818  xor     r9d, r9d; lpArguments
0x18001e81b  xor     r8d, r8d; nNumberOfArguments
0x18001e81e  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001e823  lea     edx, [r9+1]; dwExceptionFlags
0x18001e827  call    cs:__imp_RaiseException
0x18001e82d  mov     this, [rbp+string]; string1
0x18001e831  mov     r8, rsi; newString
0x18001e834  mov     rdx, r14; string2
0x18001e837  call    cs:__imp_WindowsConcatString
0x18001e83d  mov     ebx, eax
0x18001e83f  test    eax, eax
0x18001e841  jns     short loc_18001E885
0x18001e843  xor     edx, edx; length
0x18001e845  mov     this, r14; string
0x18001e848  call    cs:__imp_WindowsGetStringRawBuffer
0x18001e84e  mov     this, [rbp+18h]; callerReturnAddress
0x18001e852  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\statemanage"...
0x18001e859  mov     [rsp+60h+var_38], rax
0x18001e85e  mov     r9d, ebx; hr
0x18001e861  lea     rax, aWindowsconcats_0; "WindowsConcatString %ws"
0x18001e868  mov     edx, 12Fh; lineNumber
0x18001e86d  mov     [rsp+60h+formatString], rax; formatString
0x18001e872  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001e877  lea     rax, aBuildpropertyk; "BuildPropertyKeyByUserSid"
0x18001e87e  mov     edx, 0C7h
0x18001e883  jmp     short loc_18001E8F4
0x18001e885  mov     rbx, [rdi+10h]
0x18001e889  mov     this, rbx; this
0x18001e88c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001e891  mov     this, [rdi+8]
0x18001e895  xor     edx, edx; length
0x18001e897  mov     this, [this]; string
0x18001e89a  call    cs:__imp_WindowsGetStringRawBuffer
0x18001e8a0  mov     this, [rbp+appObject.ptr_]; coreApp
0x18001e8a4  mov     r9, rbx; coreApp
0x18001e8a7  mov     rdx, rax; propName
0x18001e8aa  call    ??$Read@UIApplicationData@Storage@Windows@@@StaticLifetimeStore@Internal@Windows@@SAJPEAUICoreApplication@Core@ApplicationModel@2@PEBGEPEAPEAUIApplicationData@Storage@2@@Z; Windows::Internal::StaticLifetimeStore::Read<Windows::Storage::IApplicationData>(Windows::ApplicationModel::Core::ICoreApplication *,ushort const *,uchar,Windows::Storage::IApplicationData * *)
0x18001e8af  mov     ebx, eax
0x18001e8b1  test    eax, eax
0x18001e8b3  jns     loc_18001E954
0x18001e8b9  cmp     eax, 8000000Bh
0x18001e8be  jz      loc_18001E780
0x18001e8c4  cmp     eax, 8007000Eh
0x18001e8c9  jz      short loc_18001E90E
0x18001e8cb  cmp     eax, 8001010Eh
0x18001e8d0  jnz     short loc_18001E8E1
0x18001e8d2  mov     ebx, 80073D54h
0x18001e8d7  xor     edx, edx
0x18001e8d9  mov     ecx, ebx
0x18001e8db  call    cs:__imp_RoOriginateError
0x18001e8e1  mov     ecx, ebx; hr
0x18001e8e3  call    ?SqmInsertAppDataObjectError@@YAXJ@Z; SqmInsertAppDataObjectError(long)
0x18001e8e8  lea     rax, aRead; "Read"
0x18001e8ef  mov     edx, 0E1h; lineNumber
0x18001e8f4  mov     this, [rbp+18h]; callerReturnAddress
0x18001e8f8  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\statemanage"...
0x18001e8ff  mov     r9d, ebx; hr
0x18001e902  mov     [rsp+60h+formatString], rax; formatString
0x18001e907  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001e90c  jmp     short loc_18001E946
0x18001e90e  mov     this, [rdi+8]
0x18001e912  xor     edx, edx; length
0x18001e914  mov     this, [this]; string
0x18001e917  call    cs:__imp_WindowsGetStringRawBuffer
0x18001e91d  mov     this, [rbp+18h]; callerReturnAddress
0x18001e921  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\statemanage"...
0x18001e928  mov     [rsp+60h+var_38], rax
0x18001e92d  mov     r9d, ebx; hr
0x18001e930  lea     rax, aReadWs; "Read %ws"
0x18001e937  mov     edx, 0E4h; lineNumber
0x18001e93c  mov     [rsp+60h+formatString], rax; formatString
0x18001e941  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001e946  lea     this, [rbp+appObject]; this
0x18001e94a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001e94f  jmp     loc_18001E79D
0x18001e954  mov     rax, [rdi+10h]
0x18001e958  mov     rdx, [rax]
0x18001e95b  mov     qword ptr [rax], 0
0x18001e962  mov     rax, [rdi+18h]
0x18001e966  mov     this, [rax]
0x18001e969  mov     [this], rdx
0x18001e96c  mov     this, [rbp+appObject.ptr_]
0x18001e970  test    this, this
0x18001e973  jz      short loc_18001E989
0x18001e975  mov     [rbp+appObject.ptr_], 0
0x18001e97d  mov     rax, [this]
0x18001e980  mov     rax, [rax+10h]
0x18001e984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e989  xor     eax, eax
0x18001e98b  mov     this, [rbp+var_8]
0x18001e98f  xor     this, rsp; StackCookie
0x18001e992  call    __security_check_cookie
0x18001e997  lea     r11, [rsp+60h+var_s0]
0x18001e99c  mov     rbx, [r11+28h]
0x18001e9a0  mov     rsi, [r11+30h]
0x18001e9a4  mov     rsp, r11
0x18001e9a7  pop     r14
0x18001e9a9  pop     rdi
0x18001e9aa  pop     rbp
0x18001e9ab  retn
```
