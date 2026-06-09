# WinStoreAuth::AuthenticationInternal::CreateLegacyTicketRequest(Windows::Security::Authentication::OnlineId::IOnlineIdServiceTicketRequest * *)

- ea: `0x1800617c0`
- end: `0x1800619dd`
- name: `?CreateLegacyTicketRequest@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUIOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Z`
- size: `541`
- prototype: `__int64 __fastcall(WinStoreAuth::AuthenticationInternal *__hidden this, struct Windows::Security::Authentication::OnlineId::IOnlineIdServiceTicketRequest **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800126ec`

## callees

- `0x180004738`
- `0x180044dcc`
- `0x1800617c0`
- `0x1800619e4`
- `0x180061c04`
- `0x180075e60`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180061820`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180061820`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006180a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006180a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006185d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061895`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800618c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061958`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061966`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061996`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800619a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006185d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061895`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800618c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061958`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061966`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061996`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800619a4`

## string_xrefs

- `0x180061803`: `Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WinStoreAuth::AuthenticationInternal::CreateLegacyTicketRequest(
        WinStoreAuth::AuthenticationInternal *this,
        struct Windows::Security::Authentication::OnlineId::IOnlineIdServiceTicketRequest **a2)
{
  HRESULT v3; // eax
  int v4; // eax
  unsigned int v5; // ebx
  int SlsValue; // eax
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING, HSTRING, __int64 *); // rbx
  int v11; // eax
  __int64 v13; // rax
  int v14; // [rsp+20h] [rbp-60h]
  HSTRING v15; // [rsp+30h] [rbp-50h] BYREF
  HSTRING v16; // [rsp+38h] [rbp-48h] BYREF
  __int64 v17; // [rsp+40h] [rbp-40h] BYREF
  __int64 v18; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  *(_QWORD *)this = 0;
  v18 = 0;
  string = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest",
         0x45u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  v4 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::OnlineId::IOnlineIdServiceTicketRequestFactory>>(
         string,
         &v18);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F1,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v4,
      v14);
LABEL_14:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
    return v5;
  }
  WindowsDeleteString(0);
  v15 = 0;
  SlsValue = WinStoreAuth::GetSlsValue(0, &v15);
  v5 = SlsValue;
  if ( SlsValue < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F4,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)SlsValue,
      v14);
    WindowsDeleteString(v15);
    v15 = 0;
    v7 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return v5;
  }
  v16 = 0;
  WindowsDeleteString(0);
  v16 = 0;
  v8 = WinStoreAuth::GetSlsValue(1, &v16);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F7,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v8,
      v14);
LABEL_13:
    WindowsDeleteString(v16);
    v16 = 0;
    WindowsDeleteString(v15);
    v15 = 0;
    goto LABEL_14;
  }
  v17 = 0;
  v9 = v18;
  v10 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, __int64 *))(*(_QWORD *)v18 + 48LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
  v11 = v10(v9, v15, v16, &v17);
  v5 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7FD,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v11,
      v14);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
    goto LABEL_13;
  }
  v13 = v17;
  v17 = 0;
  *(_QWORD *)this = v13;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
  WindowsDeleteString(v16);
  v16 = 0;
  WindowsDeleteString(v15);
  v15 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
  return 0;
}

```

## disassembly

```asm
0x1800617c0  mov     [rsp-18h+arg_8], rbx
0x1800617c5  mov     [rsp-18h+arg_10], rsi
0x1800617ca  push    rbp
0x1800617cb  push    rdi
0x1800617cc  push    r14
0x1800617ce  mov     rbp, rsp
0x1800617d1  sub     rsp, 80h
0x1800617d8  mov     rax, cs:__security_cookie
0x1800617df  xor     rax, rsp
0x1800617e2  mov     [rbp+var_10], rax
0x1800617e6  mov     rsi, rcx
0x1800617e9  xor     r14d, r14d
0x1800617ec  mov     [rcx], r14
0x1800617ef  mov     [rbp+var_38], r14
0x1800617f3  mov     [rbp+string], r14
0x1800617f7  lea     r9, [rbp+string]; string
0x1800617fb  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800617ff  lea     edx, [r14+45h]; length
0x180061803  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdServiceTicketRequest@@3QBGB; "Windows.Security.Authentication.OnlineI"...
0x18006180a  call    cs:__imp_WindowsCreateStringReference
0x180061810  test    eax, eax
0x180061812  jns     short loc_180061827
0x180061814  xor     r9d, r9d; lpArguments
0x180061817  xor     r8d, r8d; nNumberOfArguments
0x18006181a  lea     edx, [r14+1]; dwExceptionFlags
0x18006181e  mov     ecx, eax; dwExceptionCode
0x180061820  call    cs:__imp_RaiseException
0x180061826  int     3; Trap to Debugger
0x180061827  lea     rdx, [rbp+var_38]
0x18006182b  mov     rcx, [rbp+string]
0x18006182f  call    ??$GetActivationFactory@V?$ComPtr@UIOnlineIdServiceTicketRequestFactory@OnlineId@Authentication@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIOnlineIdServiceTicketRequestFactory@OnlineId@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::OnlineId::IOnlineIdServiceTicketRequestFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::OnlineId::IOnlineIdServiceTicketRequestFactory>>)
0x180061834  mov     ebx, eax
0x180061836  test    eax, eax
0x180061838  jns     short loc_180061857
0x18006183a  mov     rcx, [rbp+18h]; this
0x18006183e  mov     r9d, eax; char *
0x180061841  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x180061848  mov     edx, 7F1h; void *
0x18006184d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061852  jmp     loc_180061970
0x180061857  mov     [rbp+var_50], r14
0x18006185b  xor     ecx, ecx; string
0x18006185d  call    cs:__imp_WindowsDeleteString
0x180061863  mov     [rbp+var_50], r14
0x180061867  lea     rdx, [rbp+var_50]
0x18006186b  xor     ecx, ecx
0x18006186d  call    ?GetSlsValue@WinStoreAuth@@YAJW4SlsIndex@1@PEAPEAUHSTRING__@@@Z; WinStoreAuth::GetSlsValue(WinStoreAuth::SlsIndex,HSTRING__ * *)
0x180061872  mov     ebx, eax
0x180061874  test    eax, eax
0x180061876  jns     short loc_1800618BE
0x180061878  mov     rcx, [rbp+18h]; this
0x18006187c  mov     r9d, eax; char *
0x18006187f  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x180061886  mov     edx, 7F4h; void *
0x18006188b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061890  nop
0x180061891  mov     rcx, [rbp+var_50]; string
0x180061895  call    cs:__imp_WindowsDeleteString
0x18006189b  mov     [rbp+var_50], r14
0x18006189f  mov     rcx, [rbp+var_38]
0x1800618a3  test    rcx, rcx
0x1800618a6  jz      short loc_1800618B9
0x1800618a8  mov     [rbp+var_38], r14
0x1800618ac  mov     rax, [rcx]
0x1800618af  mov     rax, [rax+10h]
0x1800618b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800618b8  nop
0x1800618b9  jmp     loc_180061979
0x1800618be  mov     [rbp+var_48], r14
0x1800618c2  xor     ecx, ecx; string
0x1800618c4  call    cs:__imp_WindowsDeleteString
0x1800618ca  mov     [rbp+var_48], r14
0x1800618ce  lea     rdx, [rbp+var_48]
0x1800618d2  mov     ecx, 1
0x1800618d7  call    ?GetSlsValue@WinStoreAuth@@YAJW4SlsIndex@1@PEAPEAUHSTRING__@@@Z; WinStoreAuth::GetSlsValue(WinStoreAuth::SlsIndex,HSTRING__ * *)
0x1800618dc  mov     ebx, eax
0x1800618de  test    eax, eax
0x1800618e0  jns     short loc_1800618FC
0x1800618e2  mov     rcx, [rbp+18h]; this
0x1800618e6  mov     r9d, eax; char *
0x1800618e9  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800618f0  mov     edx, 7F7h; void *
0x1800618f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800618fa  jmp     short loc_180061954
0x1800618fc  mov     [rbp+var_40], r14
0x180061900  mov     rdi, [rbp+var_38]
0x180061904  mov     rax, [rdi]
0x180061907  mov     rbx, [rax+30h]
0x18006190b  lea     rcx, [rbp+var_40]
0x18006190f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180061914  lea     r9, [rbp+var_40]
0x180061918  mov     r8, [rbp+var_48]
0x18006191c  mov     rdx, [rbp+var_50]
0x180061920  mov     rcx, rdi
0x180061923  mov     rax, rbx
0x180061926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006192b  mov     ebx, eax
0x18006192d  test    eax, eax
0x18006192f  jns     short loc_18006197D
0x180061931  mov     rcx, [rbp+18h]; this
0x180061935  mov     r9d, eax; char *
0x180061938  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18006193f  mov     edx, 7FDh; void *
0x180061944  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061949  nop
0x18006194a  lea     rcx, [rbp+var_40]
0x18006194e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180061953  nop
0x180061954  mov     rcx, [rbp+var_48]; string
0x180061958  call    cs:__imp_WindowsDeleteString
0x18006195e  mov     [rbp+var_48], r14
0x180061962  mov     rcx, [rbp+var_50]; string
0x180061966  call    cs:__imp_WindowsDeleteString
0x18006196c  mov     [rbp+var_50], r14
0x180061970  lea     rcx, [rbp+var_38]
0x180061974  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180061979  mov     eax, ebx
0x18006197b  jmp     short loc_1800619B9
0x18006197d  mov     rax, [rbp+var_40]
0x180061981  mov     [rbp+var_40], r14
0x180061985  mov     [rsi], rax
0x180061988  lea     rcx, [rbp+var_40]
0x18006198c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180061991  nop
0x180061992  mov     rcx, [rbp+var_48]; string
0x180061996  call    cs:__imp_WindowsDeleteString
0x18006199c  mov     [rbp+var_48], r14
0x1800619a0  mov     rcx, [rbp+var_50]; string
0x1800619a4  call    cs:__imp_WindowsDeleteString
0x1800619aa  mov     [rbp+var_50], r14
0x1800619ae  lea     rcx, [rbp+var_38]
0x1800619b2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800619b7  xor     eax, eax
0x1800619b9  mov     rcx, [rbp+var_10]
0x1800619bd  xor     rcx, rsp; StackCookie
0x1800619c0  call    __security_check_cookie
0x1800619c5  lea     r11, [rsp+80h+var_s0]
0x1800619cd  mov     rbx, [r11+28h]
0x1800619d1  mov     rsi, [r11+30h]
0x1800619d5  mov     rsp, r11
0x1800619d8  pop     r14
0x1800619da  pop     rdi
0x1800619db  pop     rbp
0x1800619dc  retn
```
