# WinStoreAuth::AuthenticationInternal::FetchStoreAccountIdFromRegistry(ushort const *,Windows::System::IUser *,HSTRING__ * *)

- ea: `0x18003ceb8`
- end: `0x18003d175`
- name: `?FetchStoreAccountIdFromRegistry@AuthenticationInternal@WinStoreAuth@@YAJPEBGPEAUIUser@System@Windows@@PEAPEAUHSTRING__@@@Z`
- size: `701`
- prototype: `__int64 __fastcall(WinStoreAuth::AuthenticationInternal *__hidden this, const unsigned __int16 *, struct Windows::System::IUser *, HSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003dcbc`

## callees

- `0x1800026b0`
- `0x180010b84`
- `0x180039a58`
- `0x18003ceb8`
- `0x18004215c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cf6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cfec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cf6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cfec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cf7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cfff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cf7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cfff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003cf51`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003cf51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003cf75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003cff7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d0fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d143`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003cf75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003cff7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d0fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d143`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003cfa9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d02b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003cfa9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d02b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003d080`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003d080`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d0b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d0e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d12e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d0b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d0e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d12e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d0ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d0ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WinStoreAuth::AuthenticationInternal::FetchStoreAccountIdFromRegistry(
        WinStoreAuth::AuthenticationInternal *this,
        const unsigned __int16 *a2,
        struct Windows::System::IUser *a3,
        HSTRING *a4)
{
  int v5; // eax
  int v6; // ebx
  unsigned __int64 v7; // rdi
  LSTATUS v8; // eax
  __int64 v9; // rdx
  LSTATUS v10; // eax
  LSTATUS ValueW; // eax
  HSTRING v12; // rax
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v20[8]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v21; // [rsp+60h] [rbp-A0h]
  __int64 v22; // [rsp+70h] [rbp-90h]
  WCHAR sourceString[512]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+3C8h]

  *(_QWORD *)a3 = 0;
  v20[0] = 0;
  v21 = 0;
  v22 = 0;
  v5 = ConstrainedImpersonateLoggedOnUser::Impersonate((ConstrainedImpersonateLoggedOnUser *)v20);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56B,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v5,
      bIgnoreCase);
    goto LABEL_27;
  }
  v7 = -1;
  if ( CompareStringOrdinal(L"PrimaryWebAccountId", -1, L"StoreAADAccountId", -1, 1) == 2 )
  {
    hKey = 0;
    v8 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\CurrentVersion\\Store", 0, 0x20019u, &hKey);
    v6 = v8;
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    if ( v6 < 0 )
    {
      v9 = 1392;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v6,
        bIgnoreCasea);
      goto LABEL_25;
    }
  }
  else
  {
    hKey = 0;
    v10 = RegOpenKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Store\\CurrentIdentity",
            0,
            0x20019u,
            &hKey);
    v6 = v10;
    if ( v10 > 0 )
      v6 = (unsigned __int16)v10 | 0x80070000;
    if ( v6 < 0 )
    {
      v9 = 1396;
      goto LABEL_8;
    }
  }
  pcbData = 1024;
  ValueW = RegGetValueW(hKey, 0, L"StoreAADAccountId", 2u, 0, sourceString, &pcbData);
  v6 = ValueW;
  if ( ValueW > 0 )
    v6 = (unsigned __int16)ValueW | 0x80070000;
  if ( v6 < 0 )
    goto LABEL_25;
  string = 0;
  do
    ++v7;
  while ( sourceString[v7] );
  if ( v7 > 0xFFFFFFFF )
  {
    v6 = -2147024362;
    goto LABEL_24;
  }
  WindowsDeleteString(0);
  string = 0;
  v6 = WindowsCreateString(sourceString, v7, &string);
  if ( v6 < 0 )
  {
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57C,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v6,
      bIgnoreCaseb);
    WindowsDeleteString(string);
    string = 0;
LABEL_25:
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_27;
  }
  v12 = string;
  string = 0;
  *(_QWORD *)a3 = v12;
  WindowsDeleteString(0);
  string = 0;
  if ( hKey )
    RegCloseKey(hKey);
  v6 = 0;
LABEL_27:
  ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser((ConstrainedImpersonateLoggedOnUser *)v20);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003ceb8  push    rbp
0x18003ceba  push    rbx
0x18003cebb  push    rsi
0x18003cebc  push    rdi
0x18003cebd  push    r14
0x18003cebf  push    r15
0x18003cec1  lea     rbp, [rsp-398h]
0x18003cec9  sub     rsp, 498h
0x18003ced0  mov     rax, cs:__security_cookie
0x18003ced7  xor     rax, rsp
0x18003ceda  mov     [rbp+3C0h+var_40], rax
0x18003cee1  mov     r14, r8
0x18003cee4  xor     r15d, r15d
0x18003cee7  mov     [r8], r15
0x18003ceea  mov     [rsp+4C0h+var_468], r15b
0x18003ceef  xorps   xmm0, xmm0
0x18003cef2  movdqu  [rsp+4C0h+var_460], xmm0
0x18003cef8  mov     [rsp+4C0h+var_450], r15
0x18003cefd  lea     rcx, [rsp+4C0h+var_468]; this
0x18003cf02  call    ?Impersonate@ConstrainedImpersonateLoggedOnUser@@QEAAJXZ; ConstrainedImpersonateLoggedOnUser::Impersonate(void)
0x18003cf07  mov     ebx, eax
0x18003cf09  test    eax, eax
0x18003cf0b  jns     short loc_18003CF2D
0x18003cf0d  mov     rcx, [rbp+3C8h]; this
0x18003cf14  mov     r9d, eax; char *
0x18003cf17  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003cf1e  mov     edx, 56Bh; void *
0x18003cf23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cf28  jmp     loc_18003D14A
0x18003cf2d  mov     [rsp+4C0h+hKey], r15
0x18003cf32  mov     [rsp+4C0h+bIgnoreCase], 1; bIgnoreCase
0x18003cf3a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003cf3e  mov     r9d, edi; cchCount2
0x18003cf41  lea     r8, aStoreaadaccoun; "StoreAADAccountId"
0x18003cf48  mov     edx, edi; cchCount1
0x18003cf4a  lea     rcx, String1; "PrimaryWebAccountId"
0x18003cf51  call    cs:__imp_CompareStringOrdinal
0x18003cf57  mov     rsi, [rsp+4C0h+hKey]
0x18003cf5c  cmp     eax, 2
0x18003cf5f  jnz     loc_18003CFE7
0x18003cf65  test    rsi, rsi
0x18003cf68  jz      short loc_18003CF83
0x18003cf6a  call    cs:__imp_GetLastError
0x18003cf70  mov     ebx, eax
0x18003cf72  mov     rcx, rsi; hKey
0x18003cf75  call    cs:__imp_RegCloseKey
0x18003cf7b  mov     ecx, ebx; dwErrCode
0x18003cf7d  call    cs:__imp_SetLastError
0x18003cf83  mov     [rsp+4C0h+hKey], r15
0x18003cf88  lea     rax, [rsp+4C0h+hKey]
0x18003cf8d  mov     qword ptr [rsp+4C0h+bIgnoreCase], rax; int
0x18003cf92  mov     r9d, 20019h; samDesired
0x18003cf98  xor     r8d, r8d; ulOptions
0x18003cf9b  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003cfa2  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18003cfa9  call    cs:__imp_RegOpenKeyExW
0x18003cfaf  mov     ebx, eax
0x18003cfb1  mov     esi, 80070000h
0x18003cfb6  test    eax, eax
0x18003cfb8  jle     short loc_18003CFBF
0x18003cfba  movzx   ebx, ax
0x18003cfbd  or      ebx, esi
0x18003cfbf  test    ebx, ebx
0x18003cfc1  jns     loc_18003D04C
0x18003cfc7  mov     edx, 570h; void *
0x18003cfcc  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003cfd3  mov     r9d, ebx; char *
0x18003cfd6  mov     rcx, [rbp+3C8h]; this
0x18003cfdd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cfe2  jmp     loc_18003D139
0x18003cfe7  test    rsi, rsi
0x18003cfea  jz      short loc_18003D005
0x18003cfec  call    cs:__imp_GetLastError
0x18003cff2  mov     ebx, eax
0x18003cff4  mov     rcx, rsi; hKey
0x18003cff7  call    cs:__imp_RegCloseKey
0x18003cffd  mov     ecx, ebx; dwErrCode
0x18003cfff  call    cs:__imp_SetLastError
0x18003d005  mov     [rsp+4C0h+hKey], r15
0x18003d00a  lea     rax, [rsp+4C0h+hKey]
0x18003d00f  mov     qword ptr [rsp+4C0h+bIgnoreCase], rax; phkResult
0x18003d014  mov     r9d, 20019h; samDesired
0x18003d01a  xor     r8d, r8d; ulOptions
0x18003d01d  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003d024  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18003d02b  call    cs:__imp_RegOpenKeyExW
0x18003d031  mov     ebx, eax
0x18003d033  mov     esi, 80070000h
0x18003d038  test    eax, eax
0x18003d03a  jle     short loc_18003D041
0x18003d03c  movzx   ebx, ax
0x18003d03f  or      ebx, esi
0x18003d041  test    ebx, ebx
0x18003d043  jns     short loc_18003D04C
0x18003d045  mov     edx, 574h
0x18003d04a  jmp     short loc_18003CFCC
0x18003d04c  mov     [rsp+4C0h+var_470], 400h
0x18003d054  lea     rax, [rsp+4C0h+var_470]
0x18003d059  mov     [rsp+4C0h+pcbData], rax; pcbData
0x18003d05e  lea     rax, [rbp+3C0h+sourceString]
0x18003d062  mov     [rsp+4C0h+pvData], rax; pvData
0x18003d067  mov     qword ptr [rsp+4C0h+bIgnoreCase], r15; int
0x18003d06c  mov     r9d, 2; dwFlags
0x18003d072  lea     r8, aStoreaadaccoun; "StoreAADAccountId"
0x18003d079  xor     edx, edx; lpSubKey
0x18003d07b  mov     rcx, [rsp+4C0h+hKey]; hkey
0x18003d080  call    cs:__imp_RegGetValueW
0x18003d086  mov     ebx, eax
0x18003d088  test    eax, eax
0x18003d08a  jle     short loc_18003D091
0x18003d08c  movzx   ebx, ax
0x18003d08f  or      ebx, esi
0x18003d091  test    ebx, ebx
0x18003d093  js      loc_18003D139
0x18003d099  mov     [rsp+4C0h+string], r15
0x18003d09e  lea     rax, [rbp+3C0h+sourceString]
0x18003d0a2  inc     rdi
0x18003d0a5  cmp     [rax+rdi*2], r15w
0x18003d0aa  jnz     short loc_18003D0A2
0x18003d0ac  mov     eax, 0FFFFFFFFh
0x18003d0b1  cmp     rdi, rax
0x18003d0b4  ja      short loc_18003D109
0x18003d0b6  xor     ecx, ecx; string
0x18003d0b8  call    cs:__imp_WindowsDeleteString
0x18003d0be  mov     [rsp+4C0h+string], r15
0x18003d0c3  mov     edx, edi; length
0x18003d0c5  lea     r8, [rsp+4C0h+string]; string
0x18003d0ca  lea     rcx, [rbp+3C0h+sourceString]; sourceString
0x18003d0ce  call    cs:__imp_WindowsCreateString
0x18003d0d4  mov     ebx, eax
0x18003d0d6  test    eax, eax
0x18003d0d8  js      short loc_18003D10E
0x18003d0da  mov     rax, [rsp+4C0h+string]
0x18003d0df  mov     [rsp+4C0h+string], r15
0x18003d0e4  mov     [r14], rax
0x18003d0e7  xor     ecx, ecx; string
0x18003d0e9  call    cs:__imp_WindowsDeleteString
0x18003d0ef  mov     [rsp+4C0h+string], r15
0x18003d0f4  mov     rcx, [rsp+4C0h+hKey]; hKey
0x18003d0f9  test    rcx, rcx
0x18003d0fc  jz      short loc_18003D104
0x18003d0fe  call    cs:__imp_RegCloseKey
0x18003d104  mov     ebx, r15d
0x18003d107  jmp     short loc_18003D14A
0x18003d109  mov     ebx, 80070216h
0x18003d10e  mov     rcx, [rbp+3C8h]; this
0x18003d115  mov     r9d, ebx; char *
0x18003d118  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003d11f  mov     edx, 57Ch; void *
0x18003d124  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d129  mov     rcx, [rsp+4C0h+string]; string
0x18003d12e  call    cs:__imp_WindowsDeleteString
0x18003d134  mov     [rsp+4C0h+string], r15
0x18003d139  mov     rcx, [rsp+4C0h+hKey]; hKey
0x18003d13e  test    rcx, rcx
0x18003d141  jz      short loc_18003D14A
0x18003d143  call    cs:__imp_RegCloseKey
0x18003d149  nop
0x18003d14a  lea     rcx, [rsp+4C0h+var_468]; this
0x18003d14f  call    ??1ConstrainedImpersonateLoggedOnUser@@QEAA@XZ; ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(void)
0x18003d154  mov     eax, ebx
0x18003d156  mov     rcx, [rbp+3C0h+var_40]
0x18003d15d  xor     rcx, rsp; StackCookie
0x18003d160  call    __security_check_cookie
0x18003d165  add     rsp, 498h
0x18003d16c  pop     r15
0x18003d16e  pop     r14
0x18003d170  pop     rdi
0x18003d171  pop     rsi
0x18003d172  pop     rbx
0x18003d173  pop     rbp
0x18003d174  retn
```
