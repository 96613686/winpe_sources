# CLogger::GetLogPath(void)

- ea: `0x1800382c0`
- end: `0x18003850f`
- name: `?GetLogPath@CLogger@@AEAA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@XZ`
- size: `591`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180037c84`

## callees

- `0x180002300`
- `0x180008a9c`
- `0x18000b9f0`
- `0x18000ee48`
- `0x1800122d8`
- `0x18002cdd4`
- `0x180038018`
- `0x1800382c0`
- `0x18003a060`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180038455`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180038455`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180038431`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180038431`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038364`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038364`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003830c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003830c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003831e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003831e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800383bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800383bd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003835e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800383a7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003835e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800383a7`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x18003849c`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x18003849c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18003841a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18003841a`

## pseudocode

```c
__int64 __fastcall CLogger::GetLogPath(__int64 a1, __int64 a2)
{
  signed int Error; // ebx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  PSID *v6; // rdi
  __int64 v7; // r8
  DWORD TokenInformationLength; // [rsp+40h] [rbp-C0h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName; // [rsp+54h] [rbp-ACh] BYREF
  int v13; // [rsp+58h] [rbp-A8h]
  __int64 v14; // [rsp+60h] [rbp-A0h]
  WCHAR pszPath[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[1024]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR ReferencedDomainName[1024]; // [rsp+A80h] [rbp+980h] BYREF

  v14 = a2;
  v13 = 0;
  Error = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    Error = ResultFromLastError();
    if ( Error < 0 )
      goto LABEL_19;
  }
  if ( !TokenHandle )
    goto LABEL_20;
  TokenInformationLength = 0;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  LastError = GetLastError();
  if ( LastError == 122 )
  {
    v6 = (PSID *)malloc(TokenInformationLength);
    if ( v6 )
      goto LABEL_9;
    Error = -2147024882;
  }
  else
  {
    if ( LastError > 0 )
      Error = (unsigned __int16)LastError | 0x80070000;
    else
      Error = LastError;
    v6 = 0;
    if ( Error >= 0 )
    {
LABEL_9:
      if ( !GetTokenInformation(TokenHandle, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
        Error = ResultFromLastError();
    }
  }
  CloseHandle(TokenHandle);
  if ( Error >= 0 )
  {
    if ( !v6 )
      goto LABEL_20;
    cchName = 1024;
    cchReferencedDomainName = 1024;
    TokenInformationLength = 0;
    if ( !LookupAccountSidW(
            0,
            *v6,
            Name,
            &cchName,
            ReferencedDomainName,
            &cchReferencedDomainName,
            (PSID_NAME_USE)&TokenInformationLength) )
      Error = ResultFromLastError();
LABEL_18:
    free(v6);
    if ( Error >= 0 )
      goto LABEL_20;
    goto LABEL_19;
  }
  if ( v6 )
    goto LABEL_18;
LABEL_19:
  StringCchCopyW(Name, 0x400u, L"Unknown");
LABEL_20:
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    a2,
    &byte_1800444C0);
  v13 = 1;
  if ( SHGetSpecialFolderPathW(0, pszPath, 35, 0) )
  {
    v7 = -1;
    do
      ++v7;
    while ( pszPath[v7] );
    ATL::CSimpleStringT<wchar_t,0>::SetString(a2, pszPath, v7);
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(a2, "\\MSSearch\\Logs\\");
    ATL::CSimpleStringT<wchar_t,0>::Append(a2, Name);
  }
  return a2;
}

```

## disassembly

```asm
0x1800382c0  mov     [rsp-8+arg_0], rbx
0x1800382c5  mov     [rsp-8+arg_10], rsi
0x1800382ca  push    rbp
0x1800382cb  push    rdi
0x1800382cc  push    r14
0x1800382ce  lea     rbp, [rsp-1190h]
0x1800382d6  mov     eax, 1290h
0x1800382db  call    _alloca_probe
0x1800382e0  sub     rsp, rax
0x1800382e3  mov     rax, cs:__security_cookie
0x1800382ea  xor     rax, rsp
0x1800382ed  mov     [rbp+11A0h+var_20], rax
0x1800382f4  mov     rsi, rdx
0x1800382f7  mov     [rsp+12A0h+var_1240], rdx
0x1800382fc  xor     r14d, r14d
0x1800382ff  mov     [rsp+12A0h+var_1248], r14d
0x180038304  mov     ebx, r14d
0x180038307  mov     [rsp+12A0h+TokenHandle], r14
0x18003830c  call    cs:__imp_GetCurrentProcess
0x180038312  mov     rcx, rax; ProcessHandle
0x180038315  lea     r8, [rsp+12A0h+TokenHandle]; TokenHandle
0x18003831a  lea     edx, [r14+8]; DesiredAccess
0x18003831e  call    cs:__imp_OpenProcessToken
0x180038324  test    eax, eax
0x180038326  jnz     short loc_180038337
0x180038328  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18003832d  mov     ebx, eax
0x18003832f  test    eax, eax
0x180038331  js      loc_18003845F
0x180038337  mov     rcx, [rsp+12A0h+TokenHandle]; TokenHandle
0x18003833c  test    rcx, rcx
0x18003833f  jz      loc_180038477
0x180038345  mov     [rsp+12A0h+TokenInformationLength], r14d
0x18003834a  lea     rax, [rsp+12A0h+TokenInformationLength]
0x18003834f  mov     [rsp+12A0h+ReturnLength], rax; ReturnLength
0x180038354  xor     r9d, r9d; TokenInformationLength
0x180038357  xor     r8d, r8d; TokenInformation
0x18003835a  lea     edx, [r9+1]; TokenInformationClass
0x18003835e  call    cs:__imp_GetTokenInformation
0x180038364  call    cs:__imp_GetLastError
0x18003836a  cmp     eax, 7Ah ; 'z'
0x18003836d  jz      loc_18003842D
0x180038373  test    eax, eax
0x180038375  jg      short loc_18003837B
0x180038377  mov     ebx, eax
0x180038379  jmp     short loc_180038384
0x18003837b  movzx   ebx, ax
0x18003837e  or      ebx, 80070000h
0x180038384  mov     rdi, r14
0x180038387  test    ebx, ebx
0x180038389  js      short loc_1800383B8
0x18003838b  lea     rax, [rsp+12A0h+TokenInformationLength]
0x180038390  mov     [rsp+12A0h+ReturnLength], rax; ReturnLength
0x180038395  mov     r9d, [rsp+12A0h+TokenInformationLength]; TokenInformationLength
0x18003839a  mov     r8, rdi; TokenInformation
0x18003839d  mov     edx, 1; TokenInformationClass
0x1800383a2  mov     rcx, [rsp+12A0h+TokenHandle]; TokenHandle
0x1800383a7  call    cs:__imp_GetTokenInformation
0x1800383ad  test    eax, eax
0x1800383af  jnz     short loc_1800383B8
0x1800383b1  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800383b6  mov     ebx, eax
0x1800383b8  mov     rcx, [rsp+12A0h+TokenHandle]; hObject
0x1800383bd  call    cs:__imp_CloseHandle
0x1800383c3  test    ebx, ebx
0x1800383c5  js      loc_18003844D
0x1800383cb  test    rdi, rdi
0x1800383ce  jz      loc_180038477
0x1800383d4  mov     [rsp+12A0h+cchName], 400h
0x1800383dc  mov     [rsp+12A0h+var_1250], 400h
0x1800383e4  mov     [rsp+12A0h+TokenInformationLength], r14d
0x1800383e9  lea     rax, [rsp+12A0h+TokenInformationLength]
0x1800383ee  mov     [rsp+12A0h+peUse], rax; peUse
0x1800383f3  lea     rax, [rsp+12A0h+var_1250]
0x1800383f8  mov     [rsp+12A0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800383fd  lea     rax, [rbp+11A0h+ReferencedDomainName]
0x180038404  mov     [rsp+12A0h+ReturnLength], rax; ReferencedDomainName
0x180038409  lea     r9, [rsp+12A0h+cchName]; cchName
0x18003840e  lea     r8, [rbp+11A0h+Name]; Name
0x180038415  mov     rdx, [rdi]; Sid
0x180038418  xor     ecx, ecx; lpSystemName
0x18003841a  call    cs:__imp_LookupAccountSidW
0x180038420  test    eax, eax
0x180038422  jnz     short loc_180038452
0x180038424  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180038429  mov     ebx, eax
0x18003842b  jmp     short loc_180038452
0x18003842d  mov     ecx, [rsp+12A0h+TokenInformationLength]; Size
0x180038431  call    cs:__imp_malloc
0x180038437  mov     rdi, rax
0x18003843a  test    rax, rax
0x18003843d  jnz     loc_18003838B
0x180038443  mov     ebx, 8007000Eh
0x180038448  jmp     loc_1800383B8
0x18003844d  test    rdi, rdi
0x180038450  jz      short loc_18003845F
0x180038452  mov     rcx, rdi; Block
0x180038455  call    cs:__imp_free
0x18003845b  test    ebx, ebx
0x18003845d  jns     short loc_180038477
0x18003845f  lea     r8, aUnknown; "Unknown"
0x180038466  mov     edx, 400h; unsigned __int64
0x18003846b  lea     rcx, [rbp+11A0h+Name]; wchar_t *
0x180038472  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180038477  lea     rdx, byte_1800444C0
0x18003847e  mov     rcx, rsi
0x180038481  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(char const *)
0x180038486  mov     [rsp+12A0h+var_1248], 1
0x18003848e  xor     r9d, r9d; fCreate
0x180038491  lea     r8d, [r9+23h]; csidl
0x180038495  lea     rdx, [rsp+12A0h+pszPath]; pszPath
0x18003849a  xor     ecx, ecx; hwnd
0x18003849c  call    cs:__imp_SHGetSpecialFolderPathW
0x1800384a2  test    eax, eax
0x1800384a4  jz      short loc_1800384E4
0x1800384a6  lea     rax, [rsp+12A0h+pszPath]
0x1800384ab  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800384af  inc     r8
0x1800384b2  cmp     [rax+r8*2], r14w
0x1800384b7  jnz     short loc_1800384AF
0x1800384b9  lea     rdx, [rsp+12A0h+pszPath]
0x1800384be  mov     rcx, rsi
0x1800384c1  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x1800384c6  lea     rdx, aMssearchLogs; "\\MSSearch\\Logs\\"
0x1800384cd  mov     rcx, rsi
0x1800384d0  call    ??Y?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(char const *)
0x1800384d5  lea     rdx, [rbp+11A0h+Name]
0x1800384dc  mov     rcx, rsi
0x1800384df  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_W@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *)
0x1800384e4  mov     rax, rsi
0x1800384e7  mov     rcx, [rbp+11A0h+var_20]
0x1800384ee  xor     rcx, rsp; StackCookie
0x1800384f1  call    __security_check_cookie
0x1800384f6  lea     r11, [rsp+12A0h+var_10]
0x1800384fe  mov     rbx, [r11+20h]
0x180038502  mov     rsi, [r11+30h]
0x180038506  mov     rsp, r11
0x180038509  pop     r14
0x18003850b  pop     rdi
0x18003850c  pop     rbp
0x18003850d  retn
```
