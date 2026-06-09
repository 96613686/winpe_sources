# WinStoreAuth::AuthenticationInternal::ManagePropertiesFromTokenResponse(Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenResponse> const &,Windows::System::IUser *)

- ea: `0x1800401e0`
- end: `0x1800403f9`
- name: `?ManagePropertiesFromTokenResponse@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@PEAUIUser@System@Windows@@@Z`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800620e8`

## callees

- `0x18003dab0`
- `0x1800401e0`
- `0x180061c04`
- `0x180075e60`
- `0x1800a8170`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004028c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004028c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800403ac`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800403ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180040276`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180040276`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004038e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004038e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040300`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004035f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800403c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040300`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004035f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800403c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WinStoreAuth::AuthenticationInternal::ManagePropertiesFromTokenResponse(_QWORD *a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  __int64 *v3; // rcx
  __int64 *v5; // rbx
  __int64 v6; // rdi
  HRESULT v7; // eax
  int v8; // eax
  __int64 *v9; // rcx
  __int64 *v10; // rdi
  __int64 (__fastcall *v11)(__int64 *, HSTRING, HSTRING *); // rbx
  int v12; // eax
  __int64 *v13; // rcx
  const WCHAR *StringRawBuffer; // rax
  bool v15; // dl
  WinStoreAuth::AuthenticationInternal *v16; // rcx
  bool v17; // r8
  struct Windows::System::IUser *v18; // r9
  __int64 *v19; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-58h]
  _BYTE v21[8]; // [rsp+30h] [rbp-48h] BYREF
  __int64 *v22; // [rsp+38h] [rbp-40h] BYREF
  HSTRING v23; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-30h] BYREF
  HSTRING string; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  v22 = 0;
  v1 = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(*(_QWORD *)*a1 + 72LL))(*a1, &v22);
  v2 = v1;
  if ( v1 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x83A,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v1,
      bIgnoreCase);
    v3 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64 *))(*v3 + 16))(v3);
    }
    return v2;
  }
  v21[0] = 0;
  v5 = v22;
  v6 = *v22;
  string = 0;
  v7 = WindowsCreateStringReference(L"SkipForceAuthentication", 0x17u, &hstringHeader, &string);
  if ( v7 < 0 )
    RaiseException(v7, 1u, 0, 0);
  v8 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, _BYTE *))(v6 + 64))(v5, string, v21);
  v2 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x83D,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v8,
      bIgnoreCase);
    v9 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64 *))(*v9 + 16))(v9);
    }
    return v2;
  }
  if ( v21[0] )
  {
    v23 = 0;
    v10 = v22;
    v11 = *(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING *))(*v22 + 48);
    WindowsDeleteString(0);
    v23 = 0;
    string = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"SkipForceAuthentication",
      0x18u,
      0x17u);
    v12 = v11(v10, string, &v23);
    v2 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x842,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v12,
        bIgnoreCase);
      WindowsDeleteString(v23);
      v23 = 0;
      v13 = v22;
      if ( v22 )
      {
        v22 = 0;
        (*(void (__fastcall **)(__int64 *))(*v13 + 16))(v13);
      }
      return v2;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(v23, 0);
    if ( CompareStringOrdinal(StringRawBuffer, -1, L"true", -1, 1) == 2 )
      WinStoreAuth::AuthenticationInternal::SetPromptBeforePurchaseState(v16, v15, v17, v18);
    WindowsDeleteString(v23);
  }
  v19 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
  }
  return 0;
}

```

## disassembly

```asm
0x1800401e0  push    rbp
0x1800401e2  push    rbx
0x1800401e3  push    rsi
0x1800401e4  push    rdi
0x1800401e5  mov     rbp, rsp
0x1800401e8  sub     rsp, 78h
0x1800401ec  mov     rax, cs:__security_cookie
0x1800401f3  xor     rax, rsp
0x1800401f6  mov     [rbp+var_10], rax
0x1800401fa  xor     esi, esi
0x1800401fc  mov     [rbp+var_40], rsi
0x180040200  mov     rcx, [rcx]
0x180040203  mov     rax, [rcx]
0x180040206  lea     rdx, [rbp+var_40]
0x18004020a  mov     rax, [rax+48h]
0x18004020e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040213  mov     ebx, eax
0x180040215  test    eax, eax
0x180040217  jns     short loc_180040253
0x180040219  mov     rcx, [rbp+20h]; this
0x18004021d  mov     r9d, eax; char *
0x180040220  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x180040227  mov     edx, 83Ah; void *
0x18004022c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040231  nop
0x180040232  mov     rcx, [rbp+var_40]
0x180040236  test    rcx, rcx
0x180040239  jz      short loc_18004024C
0x18004023b  mov     [rbp+var_40], rsi
0x18004023f  mov     rax, [rcx]
0x180040242  mov     rax, [rax+10h]
0x180040246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004024b  nop
0x18004024c  mov     eax, ebx
0x18004024e  jmp     loc_1800403E4
0x180040253  mov     [rbp+var_48], sil
0x180040257  mov     rbx, [rbp+var_40]
0x18004025b  mov     rdi, [rbx]
0x18004025e  mov     [rbp+string], rsi
0x180040262  lea     r9, [rbp+string]; string
0x180040266  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004026a  mov     edx, 17h; length
0x18004026f  lea     rcx, aSkipforceauthe; "SkipForceAuthentication"
0x180040276  call    cs:__imp_WindowsCreateStringReference
0x18004027c  test    eax, eax
0x18004027e  jns     short loc_180040293
0x180040280  xor     r9d, r9d; lpArguments
0x180040283  xor     r8d, r8d; nNumberOfArguments
0x180040286  lea     edx, [r9+1]; dwExceptionFlags
0x18004028a  mov     ecx, eax; dwExceptionCode
0x18004028c  call    cs:__imp_RaiseException
0x180040292  nop
0x180040293  lea     r8, [rbp+var_48]
0x180040297  mov     rdx, [rbp+string]
0x18004029b  mov     rcx, rbx
0x18004029e  mov     rax, [rdi+40h]
0x1800402a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800402a7  mov     ebx, eax
0x1800402a9  test    eax, eax
0x1800402ab  jns     short loc_1800402E5
0x1800402ad  mov     rcx, [rbp+20h]; this
0x1800402b1  mov     r9d, eax; char *
0x1800402b4  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800402bb  mov     edx, 83Dh; void *
0x1800402c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800402c5  nop
0x1800402c6  mov     rcx, [rbp+var_40]
0x1800402ca  test    rcx, rcx
0x1800402cd  jz      short loc_1800402E0
0x1800402cf  mov     [rbp+var_40], rsi
0x1800402d3  mov     rax, [rcx]
0x1800402d6  mov     rax, [rax+10h]
0x1800402da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800402df  nop
0x1800402e0  jmp     loc_18004024C
0x1800402e5  cmp     [rbp+var_48], sil
0x1800402e9  jz      loc_1800403C8
0x1800402ef  mov     [rbp+var_38], rsi
0x1800402f3  mov     rdi, [rbp+var_40]
0x1800402f7  mov     rax, [rdi]
0x1800402fa  mov     rbx, [rax+30h]
0x1800402fe  xor     ecx, ecx; string
0x180040300  call    cs:__imp_WindowsDeleteString
0x180040306  mov     [rbp+var_38], rsi
0x18004030a  mov     [rbp+string], rsi
0x18004030e  mov     r9d, 17h; unsigned int
0x180040314  lea     r8d, [r9+1]; unsigned int
0x180040318  lea     rdx, aSkipforceauthe; "SkipForceAuthentication"
0x18004031f  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180040323  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180040328  nop
0x180040329  lea     r8, [rbp+var_38]
0x18004032d  mov     rdx, [rbp+string]
0x180040331  mov     rcx, rdi
0x180040334  mov     rax, rbx
0x180040337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004033c  mov     ebx, eax
0x18004033e  test    eax, eax
0x180040340  jns     short loc_180040388
0x180040342  mov     rcx, [rbp+20h]; this
0x180040346  mov     r9d, eax; char *
0x180040349  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x180040350  mov     edx, 842h; void *
0x180040355  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004035a  nop
0x18004035b  mov     rcx, [rbp+var_38]; string
0x18004035f  call    cs:__imp_WindowsDeleteString
0x180040365  mov     [rbp+var_38], rsi
0x180040369  mov     rcx, [rbp+var_40]
0x18004036d  test    rcx, rcx
0x180040370  jz      short loc_180040383
0x180040372  mov     [rbp+var_40], rsi
0x180040376  mov     rax, [rcx]
0x180040379  mov     rax, [rax+10h]
0x18004037d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040382  nop
0x180040383  jmp     loc_18004024C
0x180040388  xor     edx, edx; length
0x18004038a  mov     rcx, [rbp+var_38]; string
0x18004038e  call    cs:__imp_WindowsGetStringRawBuffer
0x180040394  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18004039c  or      edx, 0FFFFFFFFh; cchCount1
0x18004039f  mov     r9d, edx; cchCount2
0x1800403a2  lea     r8, aTrue; "true"
0x1800403a9  mov     rcx, rax; lpString1
0x1800403ac  call    cs:__imp_CompareStringOrdinal
0x1800403b2  cmp     eax, 2
0x1800403b5  jnz     short loc_1800403BD
0x1800403b7  call    ?SetPromptBeforePurchaseState@AuthenticationInternal@WinStoreAuth@@YAX_N0PEAUIUser@System@Windows@@@Z; WinStoreAuth::AuthenticationInternal::SetPromptBeforePurchaseState(bool,bool,Windows::System::IUser *)
0x1800403bc  nop
0x1800403bd  mov     rcx, [rbp+var_38]; string
0x1800403c1  call    cs:__imp_WindowsDeleteString
0x1800403c7  nop
0x1800403c8  mov     rcx, [rbp+var_40]
0x1800403cc  test    rcx, rcx
0x1800403cf  jz      short loc_1800403E2
0x1800403d1  mov     [rbp+var_40], rsi
0x1800403d5  mov     rax, [rcx]
0x1800403d8  mov     rax, [rax+10h]
0x1800403dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800403e1  nop
0x1800403e2  xor     eax, eax
0x1800403e4  mov     rcx, [rbp+var_10]
0x1800403e8  xor     rcx, rsp; StackCookie
0x1800403eb  call    __security_check_cookie
0x1800403f0  add     rsp, 78h
0x1800403f4  pop     rdi
0x1800403f5  pop     rsi
0x1800403f6  pop     rbx
0x1800403f7  pop     rbp
0x1800403f8  retn
```
