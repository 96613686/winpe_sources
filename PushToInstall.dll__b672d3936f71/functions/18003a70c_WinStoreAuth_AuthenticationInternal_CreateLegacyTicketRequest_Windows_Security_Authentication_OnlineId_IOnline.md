# WinStoreAuth::AuthenticationInternal::CreateLegacyTicketRequest(Windows::Security::Authentication::OnlineId::IOnlineIdServiceTicketRequest * *)

- ea: `0x18003a70c`
- end: `0x18003a9a0`
- name: `?CreateLegacyTicketRequest@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUIOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Z`
- size: `660`
- prototype: `__int64 __fastcall(WinStoreAuth::AuthenticationInternal *__hidden this, struct Windows::Security::Authentication::OnlineId::IOnlineIdServiceTicketRequest **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800403c4`

## callees

- `0x1800026b0`
- `0x180010b84`
- `0x18002fbb4`
- `0x18003a70c`
- `0x180040e90`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003a74d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003a74d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a7d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a80b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a837`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a872`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a906`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a914`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a94c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a95a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a7d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a80b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a837`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a872`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a906`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a914`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a94c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a95a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003a787`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003a787`

## string_xrefs

- `0x18003a746`: `Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest`

## pseudocode

```c
__int64 __fastcall WinStoreAuth::AuthenticationInternal::CreateLegacyTicketRequest(
        WinStoreAuth::AuthenticationInternal *this,
        struct Windows::Security::Authentication::OnlineId::IOnlineIdServiceTicketRequest **a2)
{
  HRESULT v3; // eax
  int v4; // edx
  unsigned int v5; // r8d
  int ActivationFactory; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  int SlsValue; // eax
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  int v19; // [rsp+20h] [rbp-29h]
  __int64 v20; // [rsp+30h] [rbp-19h] BYREF
  HSTRING v21; // [rsp+38h] [rbp-11h] BYREF
  HSTRING v22; // [rsp+40h] [rbp-9h] BYREF
  __int64 v23; // [rsp+48h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp+7h] BYREF
  HSTRING string; // [rsp+68h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  *(_QWORD *)this = 0;
  v20 = 0;
  string = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest",
         0x45u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
    JUMPOUT(0x18003A99FLL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_bebb0a08_9e73_4077_9614_08614c0bc245, &v20);
  v7 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F1,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v19);
    v8 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return v7;
  }
  v21 = 0;
  WindowsDeleteString(0);
  v21 = 0;
  SlsValue = WinStoreAuth::GetSlsValue(0, &v21);
  v7 = SlsValue;
  if ( SlsValue < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F4,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)SlsValue,
      v19);
    WindowsDeleteString(v21);
    v21 = 0;
    v11 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    return v7;
  }
  v22 = 0;
  WindowsDeleteString(0);
  v22 = 0;
  v12 = WinStoreAuth::GetSlsValue(1, &v22);
  v7 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F7,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v12,
      v19);
    WindowsDeleteString(v22);
    v22 = 0;
    WindowsDeleteString(v21);
    v21 = 0;
    v13 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return v7;
  }
  v23 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, __int64 *))(*(_QWORD *)v20 + 48LL))(v20, v21, v22, &v23);
  v7 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7FD,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v14,
      v19);
    v15 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    WindowsDeleteString(v22);
    v22 = 0;
    WindowsDeleteString(v21);
    v21 = 0;
    v16 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return v7;
  }
  v17 = v23;
  v23 = 0;
  *(_QWORD *)this = v17;
  WindowsDeleteString(v22);
  v22 = 0;
  WindowsDeleteString(v21);
  v21 = 0;
  v18 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return 0;
}

```

## disassembly

```asm
0x18003a70c  push    rbp
0x18003a70e  push    rbx
0x18003a70f  push    rsi
0x18003a710  push    rdi
0x18003a711  lea     rbp, [rsp-3Fh]
0x18003a716  sub     rsp, 88h
0x18003a71d  mov     rax, cs:__security_cookie
0x18003a724  xor     rax, rsp
0x18003a727  mov     [rbp+57h+var_30], rax
0x18003a72b  mov     rdi, rcx
0x18003a72e  xor     esi, esi
0x18003a730  mov     [rcx], rsi
0x18003a733  mov     [rbp+57h+var_70], rsi
0x18003a737  mov     [rbp+57h+string], rsi
0x18003a73b  lea     r9, [rbp+57h+string]; string
0x18003a73f  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18003a743  lea     edx, [rsi+45h]; length
0x18003a746  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdServiceTicketRequest@@3QBGB; "Windows.Security.Authentication.OnlineI"...
0x18003a74d  call    cs:__imp_WindowsCreateStringReference
0x18003a753  test    eax, eax
0x18003a755  js      loc_18003A998
0x18003a75b  mov     rbx, [rbp+57h+string]
0x18003a75f  mov     rcx, [rbp+57h+var_70]
0x18003a763  test    rcx, rcx
0x18003a766  jz      short loc_18003A779
0x18003a768  mov     [rbp+57h+var_70], rsi
0x18003a76c  mov     rax, [rcx]
0x18003a76f  mov     rax, [rax+10h]
0x18003a773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a778  nop
0x18003a779  lea     r8, [rbp+57h+var_70]
0x18003a77d  lea     rdx, _GUID_bebb0a08_9e73_4077_9614_08614c0bc245
0x18003a784  mov     rcx, rbx
0x18003a787  call    cs:__imp_RoGetActivationFactory
0x18003a78d  mov     ebx, eax
0x18003a78f  test    eax, eax
0x18003a791  jns     short loc_18003A7CD
0x18003a793  mov     rcx, [rbp+5Fh]; this
0x18003a797  mov     r9d, eax; char *
0x18003a79a  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003a7a1  mov     edx, 7F1h; void *
0x18003a7a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a7ab  nop
0x18003a7ac  mov     rcx, [rbp+57h+var_70]
0x18003a7b0  test    rcx, rcx
0x18003a7b3  jz      short loc_18003A7C6
0x18003a7b5  mov     [rbp+57h+var_70], rsi
0x18003a7b9  mov     rax, [rcx]
0x18003a7bc  mov     rax, [rax+10h]
0x18003a7c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a7c5  nop
0x18003a7c6  mov     eax, ebx
0x18003a7c8  jmp     loc_18003A980
0x18003a7cd  mov     [rbp+57h+var_68], rsi
0x18003a7d1  xor     ecx, ecx; string
0x18003a7d3  call    cs:__imp_WindowsDeleteString
0x18003a7d9  mov     [rbp+57h+var_68], rsi
0x18003a7dd  lea     rdx, [rbp+57h+var_68]
0x18003a7e1  xor     ecx, ecx
0x18003a7e3  call    ?GetSlsValue@WinStoreAuth@@YAJW4SlsIndex@1@PEAPEAUHSTRING__@@@Z; WinStoreAuth::GetSlsValue(WinStoreAuth::SlsIndex,HSTRING__ * *)
0x18003a7e8  mov     ebx, eax
0x18003a7ea  test    eax, eax
0x18003a7ec  jns     short loc_18003A831
0x18003a7ee  mov     rcx, [rbp+5Fh]; this
0x18003a7f2  mov     r9d, eax; char *
0x18003a7f5  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003a7fc  mov     edx, 7F4h; void *
0x18003a801  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a806  nop
0x18003a807  mov     rcx, [rbp+57h+var_68]; string
0x18003a80b  call    cs:__imp_WindowsDeleteString
0x18003a811  mov     [rbp+57h+var_68], rsi
0x18003a815  mov     rcx, [rbp+57h+var_70]
0x18003a819  test    rcx, rcx
0x18003a81c  jz      short loc_18003A82F
0x18003a81e  mov     [rbp+57h+var_70], rsi
0x18003a822  mov     rax, [rcx]
0x18003a825  mov     rax, [rax+10h]
0x18003a829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a82e  nop
0x18003a82f  jmp     short loc_18003A7C6
0x18003a831  mov     [rbp+57h+var_60], rsi
0x18003a835  xor     ecx, ecx; string
0x18003a837  call    cs:__imp_WindowsDeleteString
0x18003a83d  mov     [rbp+57h+var_60], rsi
0x18003a841  lea     rdx, [rbp+57h+var_60]
0x18003a845  mov     ecx, 1
0x18003a84a  call    ?GetSlsValue@WinStoreAuth@@YAJW4SlsIndex@1@PEAPEAUHSTRING__@@@Z; WinStoreAuth::GetSlsValue(WinStoreAuth::SlsIndex,HSTRING__ * *)
0x18003a84f  mov     ebx, eax
0x18003a851  test    eax, eax
0x18003a853  jns     short loc_18003A8A9
0x18003a855  mov     rcx, [rbp+5Fh]; this
0x18003a859  mov     r9d, eax; char *
0x18003a85c  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003a863  mov     edx, 7F7h; void *
0x18003a868  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a86d  nop
0x18003a86e  mov     rcx, [rbp+57h+var_60]; string
0x18003a872  call    cs:__imp_WindowsDeleteString
0x18003a878  mov     [rbp+57h+var_60], rsi
0x18003a87c  mov     rcx, [rbp+57h+var_68]; string
0x18003a880  call    cs:__imp_WindowsDeleteString
0x18003a886  mov     [rbp+57h+var_68], rsi
0x18003a88a  mov     rcx, [rbp+57h+var_70]
0x18003a88e  test    rcx, rcx
0x18003a891  jz      short loc_18003A8A4
0x18003a893  mov     [rbp+57h+var_70], rsi
0x18003a897  mov     rax, [rcx]
0x18003a89a  mov     rax, [rax+10h]
0x18003a89e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a8a3  nop
0x18003a8a4  jmp     loc_18003A7C6
0x18003a8a9  mov     [rbp+57h+var_58], rsi
0x18003a8ad  mov     rcx, [rbp+57h+var_70]
0x18003a8b1  mov     rax, [rcx]
0x18003a8b4  lea     r9, [rbp+57h+var_58]
0x18003a8b8  mov     r8, [rbp+57h+var_60]
0x18003a8bc  mov     rdx, [rbp+57h+var_68]
0x18003a8c0  mov     rax, [rax+30h]
0x18003a8c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a8c9  mov     ebx, eax
0x18003a8cb  test    eax, eax
0x18003a8cd  jns     short loc_18003A93D
0x18003a8cf  mov     rcx, [rbp+5Fh]; this
0x18003a8d3  mov     r9d, eax; char *
0x18003a8d6  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003a8dd  mov     edx, 7FDh; void *
0x18003a8e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a8e7  nop
0x18003a8e8  mov     rcx, [rbp+57h+var_58]
0x18003a8ec  test    rcx, rcx
0x18003a8ef  jz      short loc_18003A902
0x18003a8f1  mov     [rbp+57h+var_58], rsi
0x18003a8f5  mov     rax, [rcx]
0x18003a8f8  mov     rax, [rax+10h]
0x18003a8fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a901  nop
0x18003a902  mov     rcx, [rbp+57h+var_60]; string
0x18003a906  call    cs:__imp_WindowsDeleteString
0x18003a90c  mov     [rbp+57h+var_60], rsi
0x18003a910  mov     rcx, [rbp+57h+var_68]; string
0x18003a914  call    cs:__imp_WindowsDeleteString
0x18003a91a  mov     [rbp+57h+var_68], rsi
0x18003a91e  mov     rcx, [rbp+57h+var_70]
0x18003a922  test    rcx, rcx
0x18003a925  jz      short loc_18003A938
0x18003a927  mov     [rbp+57h+var_70], rsi
0x18003a92b  mov     rax, [rcx]
0x18003a92e  mov     rax, [rax+10h]
0x18003a932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a937  nop
0x18003a938  jmp     loc_18003A7C6
0x18003a93d  mov     rax, [rbp+57h+var_58]
0x18003a941  mov     [rbp+57h+var_58], rsi
0x18003a945  mov     [rdi], rax
0x18003a948  mov     rcx, [rbp+57h+var_60]; string
0x18003a94c  call    cs:__imp_WindowsDeleteString
0x18003a952  mov     [rbp+57h+var_60], rsi
0x18003a956  mov     rcx, [rbp+57h+var_68]; string
0x18003a95a  call    cs:__imp_WindowsDeleteString
0x18003a960  mov     [rbp+57h+var_68], rsi
0x18003a964  mov     rcx, [rbp+57h+var_70]
0x18003a968  test    rcx, rcx
0x18003a96b  jz      short loc_18003A97E
0x18003a96d  mov     [rbp+57h+var_70], rsi
0x18003a971  mov     rax, [rcx]
0x18003a974  mov     rax, [rax+10h]
0x18003a978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a97d  nop
0x18003a97e  xor     eax, eax
0x18003a980  mov     rcx, [rbp+57h+var_30]
0x18003a984  xor     rcx, rsp; StackCookie
0x18003a987  call    __security_check_cookie
0x18003a98c  add     rsp, 88h
0x18003a993  pop     rdi
0x18003a994  pop     rsi
0x18003a995  pop     rbx
0x18003a996  pop     rbp
0x18003a997  retn
0x18003a998  mov     ecx, eax; this
0x18003a99a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
