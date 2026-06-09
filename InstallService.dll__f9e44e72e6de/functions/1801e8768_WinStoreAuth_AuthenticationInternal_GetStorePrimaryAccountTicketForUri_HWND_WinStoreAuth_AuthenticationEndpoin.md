# WinStoreAuth::AuthenticationInternal::GetStorePrimaryAccountTicketForUri(HWND__ *,WinStoreAuth::AuthenticationEndpoint,WinStoreAuth::PromptType,bool,HSTRING__ *,Windows::System::IUser *,HSTRING__ * *,WinStoreAuth::AccountProviderType &,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult * *,bool)

- ea: `0x1801e8768`
- end: `0x1801e8b0b`
- name: `?GetStorePrimaryAccountTicketForUri@AuthenticationInternal@WinStoreAuth@@YAJPEAUHWND__@@W4AuthenticationEndpoint@2@W4PromptType@2@_NPEAUHSTRING__@@PEAUIUser@System@Windows@@PEAPEAU6@AEAW4AccountProviderType@2@PEAPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@9@3@Z`
- size: `931`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800c9f54`
- `0x1801ed094`

## callees

- `0x1800101f4`
- `0x180010b74`
- `0x180024fe0`
- `0x1801e27d8`
- `0x1801e2bf0`
- `0x1801e4db4`
- `0x1801e5270`
- `0x1801e8568`
- `0x1801e8768`
- `0x1801e90a0`
- `0x1801eaa04`
- `0x1801eabcc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e8824`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e8835`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e88b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e88d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e8944`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e894f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e8960`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e897c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e8987`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e8998`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e89bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e89d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e8a29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e8a3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e8aa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e8abd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e8acf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e8af2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e8824`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e8835`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e88b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e88d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e8944`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e894f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e8960`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e897c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e8987`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e8998`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e89bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e89d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e8a29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e8a3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e8aa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e8abd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e8acf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e8af2`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WinStoreAuth::AuthenticationInternal::GetStorePrimaryAccountTicketForUri(
        HSTRING a1,
        __int64 a2,
        bool *a3,
        char a4,
        __int64 a5,
        WinStoreAuth::AuthenticationInternal *a6,
        HSTRING a7,
        HSTRING a8,
        HSTRING a9,
        int a10)
{
  HSTRING v11; // r12
  HSTRING v12; // rsi
  WinStoreAuth::AuthenticationInternal *v13; // r14
  int IsStoreSignedOut; // eax
  struct Windows::Security::Credentials::IWebAccount **v15; // r8
  unsigned int v16; // ebx
  unsigned int v18; // edi
  int XToken; // eax
  WinStoreAuth::AuthenticationInternal *v20; // rcx
  HSTRING v21; // rbx
  HSTRING *v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rcx
  HSTRING v25; // r8
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  int v33; // eax
  __int64 v34; // r9
  __int64 v35; // rdx
  HSTRING v36; // rax
  int v37; // [rsp+20h] [rbp-28h]
  int v38; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]
  HSTRING string; // [rsp+90h] [rbp+48h] BYREF

  string = a1;
  v11 = a7;
  *(_QWORD *)a7 = 0;
  v12 = a8;
  *(_DWORD *)a8 = 0;
  *(_QWORD *)a9 = 0;
  LOBYTE(a10) = 0;
  v13 = a6;
  IsStoreSignedOut = WinStoreAuth::AuthenticationInternal::IsStoreSignedOut(
                       a6,
                       (struct Windows::System::IUser *)&a10,
                       a3);
  v16 = IsStoreSignedOut;
  if ( IsStoreSignedOut < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x125,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)IsStoreSignedOut,
      v37);
    return v16;
  }
  if ( (_BYTE)a10 )
  {
    v18 = -2147023579;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x126,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)0x80070525LL,
      v37);
    return v18;
  }
  string = 0;
  if ( !a4 )
  {
    a7 = 0;
    if ( (int)WinStoreAuth::AuthenticationInternal::FindCachedStorePrimaryAccount(
                v13,
                (struct Windows::System::IUser *)&a7,
                v15) >= 0
      && a7 )
    {
      WindowsDeleteString(0);
      a8 = 0;
      WindowsDeleteString(string);
      string = 0;
      v29 = WinStoreAuth::AuthenticationInternal::CaptureStorePrimaryAccountTicket(v27, v26, v28, v13);
      v18 = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x148,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v29,
          (int)&string);
LABEL_28:
        WindowsDeleteString(a8);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&a7);
        goto LABEL_29;
      }
LABEL_30:
      WindowsDeleteString(a8);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&a7);
      goto LABEL_31;
    }
    WindowsDeleteString(0);
    a8 = 0;
    WindowsDeleteString(string);
    string = 0;
    v33 = WinStoreAuth::AuthenticationInternal::CaptureGoldenAccountTicket(v31, v30, v32, v13);
    v18 = v33;
    if ( v33 >= 0 )
    {
      if ( *(_DWORD *)v12 == 1 )
        goto LABEL_30;
      *(_DWORD *)v12 = 0;
      v18 = -2147023579;
      v34 = 2147943717LL;
      v35 = 340;
    }
    else
    {
      v34 = (unsigned int)v33;
      v35 = 334;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)v34,
      (int)&string);
    goto LABEL_28;
  }
  a8 = 0;
  WindowsDeleteString(0);
  a8 = 0;
  WindowsDeleteString(string);
  string = 0;
  XToken = WinStoreAuth::AuthenticationInternal::GetXToken(0, 0, 0, 0, (__int64)v13, &string, &a8);
  v18 = XToken;
  if ( XToken < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12D,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)XToken,
      v38);
LABEL_15:
    WindowsDeleteString(a8);
    a8 = 0;
LABEL_29:
    WindowsDeleteString(string);
    return v18;
  }
  *(_DWORD *)v12 = 8;
  a7 = 0;
  v21 = 0;
  a9 = 0;
  a10 = 0;
  if ( !WinStoreAuth::AuthenticationInternal::IsPlatformXbox(v20) )
  {
    WindowsDeleteString(a7);
    a7 = 0;
    if ( (int)WinStoreAuth::AuthenticationInternal::FetchXboxLiveAccountId(&a7, v22) >= 0 )
    {
      WindowsDeleteString(0);
      a9 = 0;
      if ( (int)WinStoreAuth::AuthenticationInternal::GetStorePrimaryAccountId(v24, v23, v13, &a9) >= 0 && a10 == 1 )
      {
        v21 = a9;
        if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                             (Microsoft::WRL::Wrappers::Details *)a7,
                             a9,
                             v25) )
        {
          *(_DWORD *)v12 = 0;
          v18 = -2147023579;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x13E,
            (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
            (const char *)0x80070525LL,
            (int)&a10);
          WindowsDeleteString(v21);
          WindowsDeleteString(a7);
          a7 = 0;
          goto LABEL_15;
        }
      }
      else
      {
        v21 = a9;
      }
    }
  }
  WindowsDeleteString(v21);
  WindowsDeleteString(a7);
  a7 = 0;
  WindowsDeleteString(a8);
LABEL_31:
  v36 = string;
  if ( string )
  {
    string = 0;
    *(_QWORD *)v11 = v36;
  }
  WindowsDeleteString(0);
  return 0;
}

```

## disassembly

```asm
0x1801e8768  mov     [rsp-40h+string], rcx
0x1801e876d  push    rbp
0x1801e876e  push    rbx
0x1801e876f  push    rsi
0x1801e8770  push    rdi
0x1801e8771  push    r12
0x1801e8773  push    r13
0x1801e8775  push    r14
0x1801e8777  push    r15
0x1801e8779  mov     rbp, rsp
0x1801e877c  sub     rsp, 48h
0x1801e8780  mov     r15b, r9b
0x1801e8783  xor     r13d, r13d
0x1801e8786  mov     r12, [rbp+arg_30]
0x1801e878a  mov     [r12], r13
0x1801e878e  mov     rsi, [rbp+arg_38]
0x1801e8795  mov     [rsi], r13d
0x1801e8798  mov     rdi, [rbp+arg_40]
0x1801e879f  mov     [rdi], r13
0x1801e87a2  mov     byte ptr [rbp+arg_48], r13b
0x1801e87a9  lea     rdx, [rbp+arg_48]; struct Windows::System::IUser *
0x1801e87b0  mov     r14, [rbp+arg_28]
0x1801e87b4  mov     rcx, r14; this
0x1801e87b7  call    ?IsStoreSignedOut@AuthenticationInternal@WinStoreAuth@@YAJPEAUIUser@System@Windows@@PEA_N@Z; WinStoreAuth::AuthenticationInternal::IsStoreSignedOut(Windows::System::IUser *,bool *)
0x1801e87bc  mov     ebx, eax
0x1801e87be  test    eax, eax
0x1801e87c0  jns     short loc_1801E87E1
0x1801e87c2  mov     rcx, [rbp+40h]; this
0x1801e87c6  mov     r9d, eax; char *
0x1801e87c9  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e87d0  mov     edx, 125h; void *
0x1801e87d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e87da  mov     eax, ebx
0x1801e87dc  jmp     loc_1801E8AFA
0x1801e87e1  cmp     byte ptr [rbp+arg_48], r13b
0x1801e87e8  jz      short loc_1801E880E
0x1801e87ea  mov     rcx, [rbp+40h]; this
0x1801e87ee  mov     edi, 80070525h
0x1801e87f3  mov     r9d, edi; char *
0x1801e87f6  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e87fd  mov     edx, 126h; void *
0x1801e8802  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e8807  mov     eax, edi
0x1801e8809  jmp     loc_1801E8AFA
0x1801e880e  mov     [rbp+string], r13
0x1801e8812  test    r15b, r15b
0x1801e8815  jz      loc_1801E89A3
0x1801e881b  mov     [rbp+arg_38], r13
0x1801e8822  xor     ecx, ecx; string
0x1801e8824  call    cs:__imp_WindowsDeleteString
0x1801e882a  mov     [rbp+arg_38], r13
0x1801e8831  mov     rcx, [rbp+string]; string
0x1801e8835  call    cs:__imp_WindowsDeleteString
0x1801e883b  mov     [rbp+string], r13
0x1801e883f  lea     rax, [rbp+arg_38]
0x1801e8846  mov     [rsp+48h+var_18], rax
0x1801e884b  lea     rax, [rbp+string]
0x1801e884f  mov     [rsp+48h+var_20], rax
0x1801e8854  mov     qword ptr [rsp+48h+var_28], r14; int
0x1801e8859  xor     r9d, r9d
0x1801e885c  xor     r8d, r8d
0x1801e885f  xor     edx, edx
0x1801e8861  xor     ecx, ecx
0x1801e8863  call    ?GetXToken@AuthenticationInternal@WinStoreAuth@@YAJPEAUHWND__@@W4PromptType@2@PEAUHSTRING__@@2PEAUIUser@System@Windows@@PEAPEAU5@4@Z; WinStoreAuth::AuthenticationInternal::GetXToken(HWND__ *,WinStoreAuth::PromptType,HSTRING__ *,HSTRING__ *,Windows::System::IUser *,HSTRING__ * *,HSTRING__ * *)
0x1801e8868  mov     edi, eax
0x1801e886a  test    eax, eax
0x1801e886c  jns     short loc_1801E888B
0x1801e886e  mov     rcx, [rbp+40h]; this
0x1801e8872  mov     r9d, eax; char *
0x1801e8875  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e887c  mov     edx, 12Dh; void *
0x1801e8881  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e8886  jmp     loc_1801E8959
0x1801e888b  mov     dword ptr [rsi], 8
0x1801e8891  mov     [rbp+arg_30], r13
0x1801e8895  mov     rbx, r13
0x1801e8898  mov     [rbp+arg_40], rbx
0x1801e889f  mov     [rbp+arg_48], r13d
0x1801e88a6  call    ?IsPlatformXbox@AuthenticationInternal@WinStoreAuth@@YA_NXZ; WinStoreAuth::AuthenticationInternal::IsPlatformXbox(void)
0x1801e88ab  test    al, al
0x1801e88ad  jnz     loc_1801E8979
0x1801e88b3  mov     rcx, [rbp+arg_30]; string
0x1801e88b7  call    cs:__imp_WindowsDeleteString
0x1801e88bd  mov     [rbp+arg_30], r13
0x1801e88c1  lea     rcx, [rbp+arg_30]; string
0x1801e88c5  call    ?FetchXboxLiveAccountId@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUHSTRING__@@@Z; WinStoreAuth::AuthenticationInternal::FetchXboxLiveAccountId(HSTRING__ * *)
0x1801e88ca  test    eax, eax
0x1801e88cc  js      loc_1801E8979
0x1801e88d2  xor     ecx, ecx; string
0x1801e88d4  call    cs:__imp_WindowsDeleteString
0x1801e88da  mov     [rbp+arg_40], r13
0x1801e88e1  lea     rax, [rbp+arg_48]
0x1801e88e8  mov     qword ptr [rsp+48h+var_28], rax; int
0x1801e88ed  lea     r9, [rbp+arg_40]
0x1801e88f4  mov     r8, r14
0x1801e88f7  call    ?GetStorePrimaryAccountId@AuthenticationInternal@WinStoreAuth@@YAJPEAUHWND__@@W4PromptType@2@PEAUIUser@System@Windows@@PEAPEAUHSTRING__@@AEAW4AccountProviderType@2@@Z; WinStoreAuth::AuthenticationInternal::GetStorePrimaryAccountId(HWND__ *,WinStoreAuth::PromptType,Windows::System::IUser *,HSTRING__ * *,WinStoreAuth::AccountProviderType &)
0x1801e88fc  test    eax, eax
0x1801e88fe  js      short loc_1801E8972
0x1801e8900  cmp     [rbp+arg_48], 1
0x1801e8907  jnz     short loc_1801E8972
0x1801e8909  mov     rbx, [rbp+arg_40]
0x1801e8910  mov     rdx, rbx; HSTRING
0x1801e8913  mov     rcx, [rbp+arg_30]; this
0x1801e8917  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1801e891c  test    eax, eax
0x1801e891e  jz      short loc_1801E8979
0x1801e8920  mov     [rsi], r13d
0x1801e8923  mov     rcx, [rbp+40h]; this
0x1801e8927  mov     edi, 80070525h
0x1801e892c  mov     r9d, edi; char *
0x1801e892f  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e8936  mov     edx, 13Eh; void *
0x1801e893b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e8940  nop
0x1801e8941  mov     rcx, rbx; string
0x1801e8944  call    cs:__imp_WindowsDeleteString
0x1801e894a  nop
0x1801e894b  mov     rcx, [rbp+arg_30]; string
0x1801e894f  call    cs:__imp_WindowsDeleteString
0x1801e8955  mov     [rbp+arg_30], r13
0x1801e8959  mov     rcx, [rbp+arg_38]; string
0x1801e8960  call    cs:__imp_WindowsDeleteString
0x1801e8966  mov     [rbp+arg_38], r13
0x1801e896d  jmp     loc_1801E8AB9
0x1801e8972  mov     rbx, [rbp+arg_40]
0x1801e8979  mov     rcx, rbx; string
0x1801e897c  call    cs:__imp_WindowsDeleteString
0x1801e8982  nop
0x1801e8983  mov     rcx, [rbp+arg_30]; string
0x1801e8987  call    cs:__imp_WindowsDeleteString
0x1801e898d  mov     [rbp+arg_30], r13
0x1801e8991  mov     rcx, [rbp+arg_38]; string
0x1801e8998  call    cs:__imp_WindowsDeleteString
0x1801e899e  jmp     loc_1801E8ADF
0x1801e89a3  mov     [rbp+arg_30], r13
0x1801e89a7  lea     rdx, [rbp+arg_30]; struct Windows::System::IUser *
0x1801e89ab  mov     rcx, r14; this
0x1801e89ae  call    ?FindCachedStorePrimaryAccount@AuthenticationInternal@WinStoreAuth@@YAJPEAUIUser@System@Windows@@PEAPEAUIWebAccount@Credentials@Security@5@@Z; WinStoreAuth::AuthenticationInternal::FindCachedStorePrimaryAccount(Windows::System::IUser *,Windows::Security::Credentials::IWebAccount * *)
0x1801e89b3  test    eax, eax
0x1801e89b5  js      short loc_1801E8A27
0x1801e89b7  cmp     [rbp+arg_30], r13
0x1801e89bb  jz      short loc_1801E8A27
0x1801e89bd  xor     ecx, ecx; string
0x1801e89bf  call    cs:__imp_WindowsDeleteString
0x1801e89c5  mov     [rbp+arg_38], r13
0x1801e89cc  mov     rcx, [rbp+string]; string
0x1801e89d0  call    cs:__imp_WindowsDeleteString
0x1801e89d6  mov     [rbp+string], r13
0x1801e89da  mov     [rsp+48h+var_10], rdi
0x1801e89df  mov     [rsp+48h+var_18], rsi
0x1801e89e4  lea     rax, [rbp+arg_38]
0x1801e89eb  mov     [rsp+48h+var_20], rax
0x1801e89f0  lea     rax, [rbp+string]
0x1801e89f4  mov     qword ptr [rsp+48h+var_28], rax; int
0x1801e89f9  mov     r9, r14
0x1801e89fc  call    ?CaptureStorePrimaryAccountTicket@AuthenticationInternal@WinStoreAuth@@YAJPEAUHWND__@@W4AuthenticationEndpoint@2@W4PromptType@2@PEAUIUser@System@Windows@@PEAPEAUHSTRING__@@4AEAW4AccountProviderType@2@PEAPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@8@@Z; WinStoreAuth::AuthenticationInternal::CaptureStorePrimaryAccountTicket(HWND__ *,WinStoreAuth::AuthenticationEndpoint,WinStoreAuth::PromptType,Windows::System::IUser *,HSTRING__ * *,HSTRING__ * *,WinStoreAuth::AccountProviderType &,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult * *)
0x1801e8a01  mov     edi, eax
0x1801e8a03  test    eax, eax
0x1801e8a05  jns     short loc_1801E8A22
0x1801e8a07  mov     rcx, [rbp+40h]; this
0x1801e8a0b  mov     r9d, eax; char *
0x1801e8a0e  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e8a15  mov     edx, 148h; void *
0x1801e8a1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e8a1f  nop
0x1801e8a20  jmp     short loc_1801E8AA1
0x1801e8a22  jmp     loc_1801E8AC8
0x1801e8a27  xor     ecx, ecx; string
0x1801e8a29  call    cs:__imp_WindowsDeleteString
0x1801e8a2f  mov     [rbp+arg_38], r13
0x1801e8a36  mov     rcx, [rbp+string]; string
0x1801e8a3a  call    cs:__imp_WindowsDeleteString
0x1801e8a40  mov     [rbp+string], r13
0x1801e8a44  mov     [rsp+48h+var_10], rdi
0x1801e8a49  mov     [rsp+48h+var_18], rsi
0x1801e8a4e  lea     rax, [rbp+arg_38]
0x1801e8a55  mov     [rsp+48h+var_20], rax
0x1801e8a5a  lea     rax, [rbp+string]
0x1801e8a5e  mov     qword ptr [rsp+48h+var_28], rax; int
0x1801e8a63  mov     r9, r14
0x1801e8a66  call    ?CaptureGoldenAccountTicket@AuthenticationInternal@WinStoreAuth@@YAJPEAUHWND__@@W4AuthenticationEndpoint@2@W4PromptType@2@PEAUIUser@System@Windows@@PEAPEAUHSTRING__@@4AEAW4AccountProviderType@2@PEAPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@8@@Z; WinStoreAuth::AuthenticationInternal::CaptureGoldenAccountTicket(HWND__ *,WinStoreAuth::AuthenticationEndpoint,WinStoreAuth::PromptType,Windows::System::IUser *,HSTRING__ * *,HSTRING__ * *,WinStoreAuth::AccountProviderType &,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult * *)
0x1801e8a6b  mov     edi, eax
0x1801e8a6d  test    eax, eax
0x1801e8a6f  jns     short loc_1801E8A7B
0x1801e8a71  mov     r9d, eax
0x1801e8a74  mov     edx, 14Eh
0x1801e8a79  jmp     short loc_1801E8A90
0x1801e8a7b  cmp     dword ptr [rsi], 1
0x1801e8a7e  jz      short loc_1801E8AC8
0x1801e8a80  mov     [rsi], r13d
0x1801e8a83  mov     edi, 80070525h
0x1801e8a88  mov     r9d, edi; char *
0x1801e8a8b  mov     edx, 154h; void *
0x1801e8a90  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e8a97  mov     rcx, [rbp+40h]; this
0x1801e8a9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e8aa0  nop
0x1801e8aa1  mov     rcx, [rbp+arg_38]; string
0x1801e8aa8  call    cs:__imp_WindowsDeleteString
0x1801e8aae  nop
0x1801e8aaf  lea     rcx, [rbp+arg_30]
0x1801e8ab3  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e8ab8  nop
0x1801e8ab9  mov     rcx, [rbp+string]; string
0x1801e8abd  call    cs:__imp_WindowsDeleteString
0x1801e8ac3  jmp     loc_1801E8807
0x1801e8ac8  mov     rcx, [rbp+arg_38]; string
0x1801e8acf  call    cs:__imp_WindowsDeleteString
0x1801e8ad5  nop
0x1801e8ad6  lea     rcx, [rbp+arg_30]
0x1801e8ada  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e8adf  mov     rax, [rbp+string]
0x1801e8ae3  test    rax, rax
0x1801e8ae6  jz      short loc_1801E8AF0
0x1801e8ae8  mov     [rbp+string], r13
0x1801e8aec  mov     [r12], rax
0x1801e8af0  xor     ecx, ecx; string
0x1801e8af2  call    cs:__imp_WindowsDeleteString
0x1801e8af8  xor     eax, eax
0x1801e8afa  add     rsp, 48h
0x1801e8afe  pop     r15
0x1801e8b00  pop     r14
0x1801e8b02  pop     r13
0x1801e8b04  pop     r12
0x1801e8b06  pop     rdi
0x1801e8b07  pop     rsi
0x1801e8b08  pop     rbx
0x1801e8b09  pop     rbp
0x1801e8b0a  retn
```
