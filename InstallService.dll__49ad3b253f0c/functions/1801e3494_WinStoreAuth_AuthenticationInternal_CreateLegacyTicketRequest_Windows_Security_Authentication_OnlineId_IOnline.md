# WinStoreAuth::AuthenticationInternal::CreateLegacyTicketRequest(Windows::Security::Authentication::OnlineId::IOnlineIdServiceTicketRequest * *)

- ea: `0x1801e3494`
- end: `0x1801e3679`
- name: `?CreateLegacyTicketRequest@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUIOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Z`
- size: `485`
- prototype: `__int64 __fastcall(WinStoreAuth::AuthenticationInternal *__hidden this, struct Windows::Security::Authentication::OnlineId::IOnlineIdServiceTicketRequest **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1801e79a0`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x180010b74`
- `0x1800252e8`
- `0x1801e3494`
- `0x1801e8500`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e352d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e3565`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e3576`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e35b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e362f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e363d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e352d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e3565`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e3576`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e35b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e362f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e363d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801e34fe`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801e34fe`

## string_xrefs

- `0x1801e34d3`: `Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WinStoreAuth::AuthenticationInternal::CreateLegacyTicketRequest(
        WinStoreAuth::AuthenticationInternal *this,
        struct Windows::Security::Authentication::OnlineId::IOnlineIdServiceTicketRequest **a2)
{
  __int64 v3; // rbx
  int ActivationFactory; // eax
  unsigned int v5; // ebx
  int SlsValue; // eax
  int v7; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING, HSTRING, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rax
  int v13; // [rsp+20h] [rbp-60h]
  HSTRING string; // [rsp+30h] [rbp-50h] BYREF
  HSTRING v15; // [rsp+38h] [rbp-48h] BYREF
  __int64 v16; // [rsp+40h] [rbp-40h] BYREF
  __int64 v17; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  __int64 v19; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  *(_QWORD *)this = 0;
  v17 = 0;
  v19 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest",
    0x46u,
    0x45u);
  v3 = v19;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v17);
  ActivationFactory = RoGetActivationFactory(v3, &GUID_bebb0a08_9e73_4077_9614_08614c0bc245, &v17);
  v5 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    WindowsDeleteString(0);
    string = 0;
    SlsValue = WinStoreAuth::GetSlsValue(0, &string);
    v5 = SlsValue;
    if ( SlsValue >= 0 )
    {
      v15 = 0;
      WindowsDeleteString(0);
      v15 = 0;
      v7 = WinStoreAuth::GetSlsValue(1, &v15);
      v5 = v7;
      if ( v7 >= 0 )
      {
        v16 = 0;
        v8 = v17;
        v9 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, __int64 *))(*(_QWORD *)v17 + 48LL);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v16);
        v10 = v9(v8, string, v15, &v16);
        v5 = v10;
        if ( v10 >= 0 )
        {
          v11 = v16;
          v16 = 0;
          *(_QWORD *)this = v11;
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v16);
          WindowsDeleteString(v15);
          v15 = 0;
          WindowsDeleteString(string);
          v5 = 0;
          goto LABEL_12;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7FD,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v10,
          v13);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v16);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7F7,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v7,
          v13);
      }
      WindowsDeleteString(v15);
      v15 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7F4,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)SlsValue,
        v13);
    }
    WindowsDeleteString(string);
LABEL_12:
    string = 0;
    goto LABEL_13;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x7F1,
    (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
    (const char *)(unsigned int)ActivationFactory,
    v13);
LABEL_13:
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v17);
  return v5;
}

```

## disassembly

```asm
0x1801e3494  mov     [rsp-18h+arg_8], rbx
0x1801e3499  mov     [rsp-18h+arg_10], rsi
0x1801e349e  push    rbp
0x1801e349f  push    rdi
0x1801e34a0  push    r14
0x1801e34a2  mov     rbp, rsp
0x1801e34a5  sub     rsp, 80h
0x1801e34ac  mov     rax, cs:__security_cookie
0x1801e34b3  xor     rax, rsp
0x1801e34b6  mov     [rbp+var_10], rax
0x1801e34ba  mov     rsi, rcx
0x1801e34bd  xor     r14d, r14d
0x1801e34c0  mov     [rcx], r14
0x1801e34c3  mov     [rbp+var_38], r14
0x1801e34c7  mov     [rbp+var_18], r14
0x1801e34cb  lea     r9d, [r14+45h]; unsigned int
0x1801e34cf  lea     r8d, [r14+46h]; unsigned int
0x1801e34d3  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdServiceTicketRequest@@3QBGB; "Windows.Security.Authentication.OnlineI"...
0x1801e34da  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1801e34de  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801e34e3  mov     rbx, [rbp+var_18]
0x1801e34e7  lea     rcx, [rbp+var_38]
0x1801e34eb  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e34f0  lea     r8, [rbp+var_38]
0x1801e34f4  lea     rdx, _GUID_bebb0a08_9e73_4077_9614_08614c0bc245
0x1801e34fb  mov     rcx, rbx
0x1801e34fe  call    cs:__imp_RoGetActivationFactory
0x1801e3504  mov     ebx, eax
0x1801e3506  test    eax, eax
0x1801e3508  jns     short loc_1801E3527
0x1801e350a  mov     rcx, [rbp+18h]; this
0x1801e350e  mov     r9d, eax; char *
0x1801e3511  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e3518  mov     edx, 7F1h; void *
0x1801e351d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e3522  jmp     loc_1801E364A
0x1801e3527  mov     [rbp+string], r14
0x1801e352b  xor     ecx, ecx; string
0x1801e352d  call    cs:__imp_WindowsDeleteString
0x1801e3533  mov     [rbp+string], r14
0x1801e3537  lea     rdx, [rbp+string]
0x1801e353b  xor     ecx, ecx
0x1801e353d  call    ?GetSlsValue@WinStoreAuth@@YAJW4SlsIndex@1@PEAPEAUHSTRING__@@@Z; WinStoreAuth::GetSlsValue(WinStoreAuth::SlsIndex,HSTRING__ * *)
0x1801e3542  mov     ebx, eax
0x1801e3544  test    eax, eax
0x1801e3546  jns     short loc_1801E3570
0x1801e3548  mov     rcx, [rbp+18h]; this
0x1801e354c  mov     r9d, eax; char *
0x1801e354f  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e3556  mov     edx, 7F4h; void *
0x1801e355b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e3560  nop
0x1801e3561  mov     rcx, [rbp+string]; string
0x1801e3565  call    cs:__imp_WindowsDeleteString
0x1801e356b  jmp     loc_1801E3646
0x1801e3570  mov     [rbp+var_48], r14
0x1801e3574  xor     ecx, ecx; string
0x1801e3576  call    cs:__imp_WindowsDeleteString
0x1801e357c  mov     [rbp+var_48], r14
0x1801e3580  lea     rdx, [rbp+var_48]
0x1801e3584  mov     ecx, 1
0x1801e3589  call    ?GetSlsValue@WinStoreAuth@@YAJW4SlsIndex@1@PEAPEAUHSTRING__@@@Z; WinStoreAuth::GetSlsValue(WinStoreAuth::SlsIndex,HSTRING__ * *)
0x1801e358e  mov     ebx, eax
0x1801e3590  test    eax, eax
0x1801e3592  jns     short loc_1801E35BD
0x1801e3594  mov     rcx, [rbp+18h]; this
0x1801e3598  mov     r9d, eax; char *
0x1801e359b  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e35a2  mov     edx, 7F7h; void *
0x1801e35a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e35ac  nop
0x1801e35ad  mov     rcx, [rbp+var_48]; string
0x1801e35b1  call    cs:__imp_WindowsDeleteString
0x1801e35b7  mov     [rbp+var_48], r14
0x1801e35bb  jmp     short loc_1801E3561
0x1801e35bd  mov     [rbp+var_40], r14
0x1801e35c1  mov     rdi, [rbp+var_38]
0x1801e35c5  mov     rax, [rdi]
0x1801e35c8  mov     rbx, [rax+30h]
0x1801e35cc  lea     rcx, [rbp+var_40]
0x1801e35d0  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e35d5  lea     r9, [rbp+var_40]
0x1801e35d9  mov     r8, [rbp+var_48]
0x1801e35dd  mov     rdx, [rbp+string]
0x1801e35e1  mov     rcx, rdi
0x1801e35e4  mov     rax, rbx
0x1801e35e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e35ec  mov     ebx, eax
0x1801e35ee  test    eax, eax
0x1801e35f0  jns     short loc_1801E3616
0x1801e35f2  mov     rcx, [rbp+18h]; this
0x1801e35f6  mov     r9d, eax; char *
0x1801e35f9  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e3600  mov     edx, 7FDh; void *
0x1801e3605  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e360a  nop
0x1801e360b  lea     rcx, [rbp+var_40]
0x1801e360f  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e3614  jmp     short loc_1801E35AD
0x1801e3616  mov     rax, [rbp+var_40]
0x1801e361a  mov     [rbp+var_40], r14
0x1801e361e  mov     [rsi], rax
0x1801e3621  lea     rcx, [rbp+var_40]
0x1801e3625  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e362a  nop
0x1801e362b  mov     rcx, [rbp+var_48]; string
0x1801e362f  call    cs:__imp_WindowsDeleteString
0x1801e3635  mov     [rbp+var_48], r14
0x1801e3639  mov     rcx, [rbp+string]; string
0x1801e363d  call    cs:__imp_WindowsDeleteString
0x1801e3643  mov     ebx, r14d
0x1801e3646  mov     [rbp+string], r14
0x1801e364a  lea     rcx, [rbp+var_38]
0x1801e364e  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e3653  mov     eax, ebx
0x1801e3655  mov     rcx, [rbp+var_10]
0x1801e3659  xor     rcx, rsp; StackCookie
0x1801e365c  call    __security_check_cookie
0x1801e3661  lea     r11, [rsp+80h+var_s0]
0x1801e3669  mov     rbx, [r11+28h]
0x1801e366d  mov     rsi, [r11+30h]
0x1801e3671  mov     rsp, r11
0x1801e3674  pop     r14
0x1801e3676  pop     rdi
0x1801e3677  pop     rbp
0x1801e3678  retn
```
