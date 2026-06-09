# WinStoreAuth::AuthenticationInternal::ManagePropertiesFromTokenResponse(Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenResponse> const &,Windows::System::IUser *)

- ea: `0x180042768`
- end: `0x180042986`
- name: `?ManagePropertiesFromTokenResponse@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@PEAUIUser@System@Windows@@@Z`
- size: `542`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18003c52c`

## callees

- `0x1800026b0`
- `0x180010b84`
- `0x18002fbb4`
- `0x180042768`
- `0x180043ddc`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180042929`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180042929`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004290b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004290b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800427fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180042897`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800427fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180042897`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042875`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800428dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004293e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042875`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800428dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004293e`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WinStoreAuth::AuthenticationInternal::ManagePropertiesFromTokenResponse(_QWORD *a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  _QWORD *v3; // rcx
  _QWORD *v5; // rbx
  __int64 v6; // rdi
  HRESULT v7; // eax
  int v8; // edx
  unsigned int v9; // r8d
  int v10; // eax
  _QWORD *v11; // rcx
  _QWORD *v12; // rbx
  __int64 v13; // rdi
  HRESULT v14; // eax
  int v15; // edx
  unsigned int v16; // r8d
  int v17; // eax
  _QWORD *v18; // rcx
  const WCHAR *StringRawBuffer; // rax
  __int64 v20; // rdx
  WinStoreAuth::AuthenticationInternal *v21; // rcx
  __int64 v22; // r8
  struct Windows::System::IUser *v23; // r9
  _QWORD *v24; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-58h]
  _BYTE v26[8]; // [rsp+30h] [rbp-48h] BYREF
  _QWORD *v27; // [rsp+38h] [rbp-40h] BYREF
  HSTRING v28; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-30h] BYREF
  HSTRING string; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  v27 = 0;
  v1 = (*(__int64 (__fastcall **)(_QWORD, _QWORD **))(*(_QWORD *)*a1 + 72LL))(*a1, &v27);
  v2 = v1;
  if ( v1 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x83A,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v1,
      bIgnoreCase);
    v3 = v27;
    if ( v27 )
    {
      v27 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v3 + 16LL))(v3);
    }
    return v2;
  }
  v26[0] = 0;
  v5 = v27;
  v6 = *v27;
  string = 0;
  v7 = WindowsCreateStringReference(L"SkipForceAuthentication", 0x17u, &hstringHeader, &string);
  if ( v7 < 0 )
    goto LABEL_23;
  v10 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, _BYTE *))(v6 + 64))(v5, string, v26);
  v2 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x83D,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v10,
      bIgnoreCase);
    v11 = v27;
    if ( v27 )
    {
      v27 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v11 + 16LL))(v11);
    }
    return v2;
  }
  if ( v26[0] )
  {
    v28 = 0;
    v12 = v27;
    v13 = *v27;
    WindowsDeleteString(0);
    v28 = 0;
    string = 0;
    v14 = WindowsCreateStringReference(L"SkipForceAuthentication", 0x17u, &hstringHeader, &string);
    if ( v14 >= 0 )
    {
      v17 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, HSTRING *))(v13 + 48))(v12, string, &v28);
      v2 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x842,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v17,
          bIgnoreCase);
        WindowsDeleteString(v28);
        v28 = 0;
        v18 = v27;
        if ( v27 )
        {
          v27 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
        }
        return v2;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(v28, 0);
      if ( CompareStringOrdinal(StringRawBuffer, -1, L"true", -1, 1) == 2 )
        WinStoreAuth::AuthenticationInternal::SetPromptBeforePurchaseState(v21, v20, v22, v23);
      WindowsDeleteString(v28);
      goto LABEL_19;
    }
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v14, v15, v16);
LABEL_23:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7, v8, v9);
    JUMPOUT(0x180042985LL);
  }
LABEL_19:
  v24 = v27;
  if ( v27 )
  {
    v27 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v24 + 16LL))(v24);
  }
  return 0;
}

```

## disassembly

```asm
0x180042768  push    rbp
0x18004276a  push    rbx
0x18004276b  push    rsi
0x18004276c  push    rdi
0x18004276d  mov     rbp, rsp
0x180042770  sub     rsp, 78h
0x180042774  mov     rax, cs:__security_cookie
0x18004277b  xor     rax, rsp
0x18004277e  mov     [rbp+var_10], rax
0x180042782  xor     esi, esi
0x180042784  mov     [rbp+var_40], rsi
0x180042788  mov     rcx, [rcx]
0x18004278b  mov     rax, [rcx]
0x18004278e  lea     rdx, [rbp+var_40]
0x180042792  mov     rax, [rax+48h]
0x180042796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004279b  mov     ebx, eax
0x18004279d  test    eax, eax
0x18004279f  jns     short loc_1800427DB
0x1800427a1  mov     rcx, [rbp+20h]; this
0x1800427a5  mov     r9d, eax; char *
0x1800427a8  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800427af  mov     edx, 83Ah; void *
0x1800427b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800427b9  nop
0x1800427ba  mov     rcx, [rbp+var_40]
0x1800427be  test    rcx, rcx
0x1800427c1  jz      short loc_1800427D4
0x1800427c3  mov     [rbp+var_40], rsi
0x1800427c7  mov     rax, [rcx]
0x1800427ca  mov     rax, [rax+10h]
0x1800427ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800427d3  nop
0x1800427d4  mov     eax, ebx
0x1800427d6  jmp     loc_180042961
0x1800427db  mov     [rbp+var_48], sil
0x1800427df  mov     rbx, [rbp+var_40]
0x1800427e3  mov     rdi, [rbx]
0x1800427e6  mov     [rbp+string], rsi
0x1800427ea  lea     r9, [rbp+string]; string
0x1800427ee  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800427f2  mov     edx, 17h; length
0x1800427f7  lea     rcx, aSkipforceauthe; "SkipForceAuthentication"
0x1800427fe  call    cs:__imp_WindowsCreateStringReference
0x180042804  test    eax, eax
0x180042806  js      loc_18004297E
0x18004280c  lea     r8, [rbp+var_48]
0x180042810  mov     rdx, [rbp+string]
0x180042814  mov     rcx, rbx
0x180042817  mov     rax, [rdi+40h]
0x18004281b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042820  mov     ebx, eax
0x180042822  test    eax, eax
0x180042824  jns     short loc_18004285E
0x180042826  mov     rcx, [rbp+20h]; this
0x18004282a  mov     r9d, eax; char *
0x18004282d  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x180042834  mov     edx, 83Dh; void *
0x180042839  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004283e  nop
0x18004283f  mov     rcx, [rbp+var_40]
0x180042843  test    rcx, rcx
0x180042846  jz      short loc_180042859
0x180042848  mov     [rbp+var_40], rsi
0x18004284c  mov     rax, [rcx]
0x18004284f  mov     rax, [rax+10h]
0x180042853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042858  nop
0x180042859  jmp     loc_1800427D4
0x18004285e  cmp     [rbp+var_48], sil
0x180042862  jz      loc_180042945
0x180042868  mov     [rbp+var_38], rsi
0x18004286c  mov     rbx, [rbp+var_40]
0x180042870  mov     rdi, [rbx]
0x180042873  xor     ecx, ecx; string
0x180042875  call    cs:__imp_WindowsDeleteString
0x18004287b  mov     [rbp+var_38], rsi
0x18004287f  mov     [rbp+string], rsi
0x180042883  lea     r9, [rbp+string]; string
0x180042887  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004288b  mov     edx, 17h; length
0x180042890  lea     rcx, aSkipforceauthe; "SkipForceAuthentication"
0x180042897  call    cs:__imp_WindowsCreateStringReference
0x18004289d  test    eax, eax
0x18004289f  js      loc_180042976
0x1800428a5  lea     r8, [rbp+var_38]
0x1800428a9  mov     rdx, [rbp+string]
0x1800428ad  mov     rcx, rbx
0x1800428b0  mov     rax, [rdi+30h]
0x1800428b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800428b9  mov     ebx, eax
0x1800428bb  test    eax, eax
0x1800428bd  jns     short loc_180042905
0x1800428bf  mov     rcx, [rbp+20h]; this
0x1800428c3  mov     r9d, eax; char *
0x1800428c6  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800428cd  mov     edx, 842h; void *
0x1800428d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800428d7  nop
0x1800428d8  mov     rcx, [rbp+var_38]; string
0x1800428dc  call    cs:__imp_WindowsDeleteString
0x1800428e2  mov     [rbp+var_38], rsi
0x1800428e6  mov     rcx, [rbp+var_40]
0x1800428ea  test    rcx, rcx
0x1800428ed  jz      short loc_180042900
0x1800428ef  mov     [rbp+var_40], rsi
0x1800428f3  mov     rax, [rcx]
0x1800428f6  mov     rax, [rax+10h]
0x1800428fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800428ff  nop
0x180042900  jmp     loc_1800427D4
0x180042905  xor     edx, edx; length
0x180042907  mov     rcx, [rbp+var_38]; string
0x18004290b  call    cs:__imp_WindowsGetStringRawBuffer
0x180042911  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x180042919  or      edx, 0FFFFFFFFh; cchCount1
0x18004291c  mov     r9d, edx; cchCount2
0x18004291f  lea     r8, aTrue; "true"
0x180042926  mov     rcx, rax; lpString1
0x180042929  call    cs:__imp_CompareStringOrdinal
0x18004292f  cmp     eax, 2
0x180042932  jnz     short loc_18004293A
0x180042934  call    ?SetPromptBeforePurchaseState@AuthenticationInternal@WinStoreAuth@@YAX_N0PEAUIUser@System@Windows@@@Z; WinStoreAuth::AuthenticationInternal::SetPromptBeforePurchaseState(bool,bool,Windows::System::IUser *)
0x180042939  nop
0x18004293a  mov     rcx, [rbp+var_38]; string
0x18004293e  call    cs:__imp_WindowsDeleteString
0x180042944  nop
0x180042945  mov     rcx, [rbp+var_40]
0x180042949  test    rcx, rcx
0x18004294c  jz      short loc_18004295F
0x18004294e  mov     [rbp+var_40], rsi
0x180042952  mov     rax, [rcx]
0x180042955  mov     rax, [rax+10h]
0x180042959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004295e  nop
0x18004295f  xor     eax, eax
0x180042961  mov     rcx, [rbp+var_10]
0x180042965  xor     rcx, rsp; StackCookie
0x180042968  call    __security_check_cookie
0x18004296d  add     rsp, 78h
0x180042971  pop     rdi
0x180042972  pop     rsi
0x180042973  pop     rbx
0x180042974  pop     rbp
0x180042975  retn
0x180042976  mov     ecx, eax; this
0x180042978  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004297d  nop
0x18004297e  mov     ecx, eax; this
0x180042980  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
