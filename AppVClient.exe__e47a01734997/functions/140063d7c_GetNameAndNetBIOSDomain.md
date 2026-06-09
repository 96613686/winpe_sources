# GetNameAndNetBIOSDomain

- ea: `0x140063d7c`
- end: `0x14006409b`
- name: `GetNameAndNetBIOSDomain`
- size: `799`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1400645ec`

## callees

- `0x140004280`
- `0x140006061`
- `0x140007404`
- `0x140018bec`
- `0x140019da0`
- `0x14001a08c`
- `0x140063d7c`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x140063dc3`
- `ADVAPI32!GetTokenInformation` at `0x140063dc3`
- `ADVAPI32!LookupAccountSidW` at `0x140063e51`
- `ADVAPI32!LookupAccountSidW` at `0x140063f07`
- `ADVAPI32!LookupAccountSidW` at `0x140063e51`
- `ADVAPI32!LookupAccountSidW` at `0x140063f07`
- `KERNEL32!GetLastError` at `0x140063e07`
- `KERNEL32!GetLastError` at `0x140063e5b`
- `KERNEL32!GetLastError` at `0x140063f44`
- `KERNEL32!GetLastError` at `0x140063e07`
- `KERNEL32!GetLastError` at `0x140063e5b`
- `KERNEL32!GetLastError` at `0x140063f44`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140063dda`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140063e74`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140063f1b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140064041`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140063dda`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140063e74`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140063f1b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140064041`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetNameAndNetBIOSDomain(void *a1, __int64 a2, __int64 a3)
{
  char *v5; // rax
  const char *v6; // rax
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rax
  __int64 v9; // rcx
  DWORD LastError; // eax
  __int64 v11; // rdi
  char *v12; // rax
  const char *v13; // rax
  __int64 v14; // r8
  char *v15; // rax
  const char *v16; // rax
  unsigned __int64 FileId; // rbx
  __int64 v18; // rdi
  LPWSTR v20; // r9
  unsigned __int64 v21; // rdi
  unsigned __int64 v22; // rdx
  char *v23; // rsi
  __int64 v24; // rbx
  __int64 v25; // r8
  LPWSTR v26; // r9
  char *v27; // rsi
  char *v28; // rax
  const char *v29; // rax
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-69h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-65h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-61h] BYREF
  DWORD ReturnLength; // [rsp+4Ch] [rbp-5Dh] BYREF
  LPWSTR ReferencedDomainName[3]; // [rsp+50h] [rbp-59h] BYREF
  LPWSTR Name[3]; // [rsp+68h] [rbp-41h] BYREF
  PSID TokenInformation[10]; // [rsp+80h] [rbp-29h] BYREF

  ReturnLength = 68;
  if ( !GetTokenInformation(a1, TokenUser, TokenInformation, 0x44u, &ReturnLength) )
  {
    v5 = strrchr("admin\\appman\\appv\\shared\\user\\userinfo.cpp", 92);
    if ( v5 )
      v6 = v5 + 1;
    else
      v6 = "admin\\appman\\appv\\shared\\user\\userinfo.cpp";
    v7 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v6) << 52;
    v8 = v7 | GetLastError();
    v9 = 0x1B2500000000LL;
    return v9 | v8;
  }
  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  if ( !LookupAccountSidW(0, TokenInformation[0], 0, &cchName, 0, &cchReferencedDomainName, &peUse) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError != 122 )
    {
      v12 = strrchr("admin\\appman\\appv\\shared\\user\\userinfo.cpp", 92);
      if ( v12 )
        v13 = v12 + 1;
      else
        v13 = "admin\\appman\\appv\\shared\\user\\userinfo.cpp";
      v8 = v11
         | (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v13) << 52);
      v9 = 0x1D2500000000LL;
      return v9 | v8;
    }
  }
  if ( !cchName || !cchReferencedDomainName )
  {
    v28 = strrchr("admin\\appman\\appv\\shared\\user\\userinfo.cpp", 92);
    if ( v28 )
      v29 = v28 + 1;
    else
      v29 = "admin\\appman\\appv\\shared\\user\\userinfo.cpp";
    v8 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v29) << 52;
    v9 = 0x1D25000004E9LL;
    return v9 | v8;
  }
  std::vector<wchar_t>::vector<wchar_t>(Name, cchName);
  std::vector<wchar_t>::vector<wchar_t>(ReferencedDomainName, cchReferencedDomainName);
  if ( LookupAccountSidW(
         0,
         TokenInformation[0],
         Name[0],
         &cchName,
         ReferencedDomainName[0],
         &cchReferencedDomainName,
         &peUse) )
  {
    v20 = Name[0];
    v21 = -1;
    v22 = -1;
    do
      ++v22;
    while ( Name[0][v22] );
    if ( v22 > *(_QWORD *)(a2 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
        (char **)a2,
        v22,
        v14,
        Name[0]);
    }
    else
    {
      if ( *(_QWORD *)(a2 + 24) <= 7u )
        v23 = (char *)a2;
      else
        v23 = *(char **)a2;
      *(_QWORD *)(a2 + 16) = v22;
      v24 = 2 * v22;
      memmove_0(v23, v20, 2 * v22);
      *(_WORD *)&v23[v24] = 0;
    }
    v26 = ReferencedDomainName[0];
    do
      ++v21;
    while ( ReferencedDomainName[0][v21] );
    if ( v21 > *(_QWORD *)(a3 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
        (char **)a3,
        v21,
        v25,
        ReferencedDomainName[0]);
    }
    else
    {
      if ( *(_QWORD *)(a3 + 24) <= 7u )
        v27 = (char *)a3;
      else
        v27 = *(char **)a3;
      *(_QWORD *)(a3 + 16) = v21;
      memmove_0(v27, v26, 2 * v21);
      *(_WORD *)&v27[2 * v21] = 0;
    }
    std::vector<wchar_t>::~vector<wchar_t>((char **)ReferencedDomainName);
    std::vector<wchar_t>::~vector<wchar_t>((char **)Name);
    return 0x8000000000LL;
  }
  else
  {
    v15 = strrchr("admin\\appman\\appv\\shared\\user\\userinfo.cpp", 92);
    if ( v15 )
      v16 = v15 + 1;
    else
      v16 = "admin\\appman\\appv\\shared\\user\\userinfo.cpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v16);
    v18 = (FileId << 52) | GetLastError() | 0x1E2500000000LL;
    std::vector<wchar_t>::~vector<wchar_t>((char **)ReferencedDomainName);
    std::vector<wchar_t>::~vector<wchar_t>((char **)Name);
    return v18;
  }
}

```

## disassembly

```asm
0x140063d7c  mov     [rsp-8+arg_18], rbx
0x140063d81  push    rbp
0x140063d82  push    rsi
0x140063d83  push    rdi
0x140063d84  push    r14
0x140063d86  push    r15
0x140063d88  lea     rbp, [rsp-37h]
0x140063d8d  sub     rsp, 0E0h
0x140063d94  mov     rax, cs:__security_cookie
0x140063d9b  xor     rax, rsp
0x140063d9e  mov     [rbp+57h+var_30], rax
0x140063da2  mov     r14, r8
0x140063da5  mov     rbx, rdx
0x140063da8  mov     r9d, 44h ; 'D'; TokenInformationLength
0x140063dae  mov     [rbp+57h+var_B4], r9d
0x140063db2  lea     rax, [rbp+57h+var_B4]
0x140063db6  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x140063dbb  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x140063dbf  lea     edx, [r9-43h]; TokenInformationClass
0x140063dc3  call    cs:__imp_GetTokenInformation
0x140063dc9  xor     r15d, r15d
0x140063dcc  test    eax, eax
0x140063dce  jnz     short loc_140063E21
0x140063dd0  lea     edx, [rax+5Ch]; Ch
0x140063dd3  lea     rcx, aAdminAppmanApp_9; "admin\\appman\\appv\\shared\\user\\user"...
0x140063dda  call    cs:__imp_strrchr
0x140063de0  test    rax, rax
0x140063de3  jz      short loc_140063DEA
0x140063de5  inc     rax
0x140063de8  jmp     short loc_140063DF1
0x140063dea  lea     rax, aAdminAppmanApp_9; "admin\\appman\\appv\\shared\\user\\user"...
0x140063df1  mov     rdx, rax; char *
0x140063df4  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140063dfb  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140063e00  mov     rbx, rax
0x140063e03  shl     rbx, 34h
0x140063e07  call    cs:__imp_GetLastError
0x140063e0d  mov     eax, eax
0x140063e0f  or      rax, rbx
0x140063e12  mov     rcx, 1B2500000000h
0x140063e1c  jmp     loc_140064075
0x140063e21  mov     [rbp+57h+cchName], r15d
0x140063e25  mov     [rbp+57h+var_C0], r15d
0x140063e29  mov     [rbp+57h+var_B8], r15d
0x140063e2d  lea     rax, [rbp+57h+var_B8]
0x140063e31  mov     [rsp+100h+peUse], rax; peUse
0x140063e36  lea     rax, [rbp+57h+var_C0]
0x140063e3a  mov     [rsp+100h+cchReferencedDomainName], rax; cchReferencedDomainName
0x140063e3f  mov     [rsp+100h+ReturnLength], r15; ReferencedDomainName
0x140063e44  lea     r9, [rbp+57h+cchName]; cchName
0x140063e48  xor     r8d, r8d; Name
0x140063e4b  mov     rdx, [rbp+57h+TokenInformation]; Sid
0x140063e4f  xor     ecx, ecx; lpSystemName
0x140063e51  call    cs:__imp_LookupAccountSidW
0x140063e57  test    eax, eax
0x140063e59  jnz     short loc_140063EB0
0x140063e5b  call    cs:__imp_GetLastError
0x140063e61  mov     edi, eax
0x140063e63  cmp     eax, 7Ah ; 'z'
0x140063e66  jz      short loc_140063EB0
0x140063e68  mov     edx, 5Ch ; '\'; Ch
0x140063e6d  lea     rcx, aAdminAppmanApp_9; "admin\\appman\\appv\\shared\\user\\user"...
0x140063e74  call    cs:__imp_strrchr
0x140063e7a  test    rax, rax
0x140063e7d  jz      short loc_140063E84
0x140063e7f  inc     rax
0x140063e82  jmp     short loc_140063E8B
0x140063e84  lea     rax, aAdminAppmanApp_9; "admin\\appman\\appv\\shared\\user\\user"...
0x140063e8b  mov     rdx, rax; char *
0x140063e8e  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140063e95  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140063e9a  shl     rax, 34h
0x140063e9e  or      rax, rdi
0x140063ea1  mov     rcx, 1D2500000000h
0x140063eab  jmp     loc_140064075
0x140063eb0  mov     eax, [rbp+57h+cchName]
0x140063eb3  test    eax, eax
0x140063eb5  jz      loc_140064035
0x140063ebb  cmp     [rbp+57h+var_C0], r15d
0x140063ebf  jz      loc_140064035
0x140063ec5  mov     edx, eax
0x140063ec7  lea     rcx, [rbp+57h+Name]
0x140063ecb  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x140063ed0  nop
0x140063ed1  mov     edx, [rbp+57h+var_C0]
0x140063ed4  lea     rcx, [rbp+57h+ReferencedDomainName]
0x140063ed8  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x140063edd  nop
0x140063ede  mov     rax, [rbp+57h+ReferencedDomainName]
0x140063ee2  lea     rcx, [rbp+57h+var_B8]
0x140063ee6  mov     [rsp+100h+peUse], rcx; peUse
0x140063eeb  lea     rcx, [rbp+57h+var_C0]
0x140063eef  mov     [rsp+100h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x140063ef4  mov     [rsp+100h+ReturnLength], rax; ReferencedDomainName
0x140063ef9  lea     r9, [rbp+57h+cchName]; cchName
0x140063efd  mov     r8, [rbp+57h+Name]; Name
0x140063f01  mov     rdx, [rbp+57h+TokenInformation]; Sid
0x140063f05  xor     ecx, ecx; lpSystemName
0x140063f07  call    cs:__imp_LookupAccountSidW
0x140063f0d  test    eax, eax
0x140063f0f  jnz     short loc_140063F7B
0x140063f11  lea     edx, [rax+5Ch]; Ch
0x140063f14  lea     rcx, aAdminAppmanApp_9; "admin\\appman\\appv\\shared\\user\\user"...
0x140063f1b  call    cs:__imp_strrchr
0x140063f21  test    rax, rax
0x140063f24  jz      short loc_140063F2B
0x140063f26  inc     rax
0x140063f29  jmp     short loc_140063F32
0x140063f2b  lea     rax, aAdminAppmanApp_9; "admin\\appman\\appv\\shared\\user\\user"...
0x140063f32  mov     rdx, rax; char *
0x140063f35  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140063f3c  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140063f41  mov     rbx, rax
0x140063f44  call    cs:__imp_GetLastError
0x140063f4a  mov     edi, eax
0x140063f4c  shl     rbx, 34h
0x140063f50  or      rdi, rbx
0x140063f53  mov     rax, 1E2500000000h
0x140063f5d  or      rdi, rax
0x140063f60  lea     rcx, [rbp+57h+ReferencedDomainName]
0x140063f64  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x140063f69  nop
0x140063f6a  lea     rcx, [rbp+57h+Name]
0x140063f6e  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x140063f73  mov     rax, rdi
0x140063f76  jmp     loc_140064078
0x140063f7b  mov     r9, [rbp+57h+Name]
0x140063f7f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140063f83  mov     rdx, rdi
0x140063f86  inc     rdx
0x140063f89  cmp     [r9+rdx*2], r15w
0x140063f8e  jnz     short loc_140063F86
0x140063f90  cmp     rdx, [rbx+18h]
0x140063f94  ja      short loc_140063FC2
0x140063f96  cmp     qword ptr [rbx+18h], 7
0x140063f9b  jbe     short loc_140063FA2
0x140063f9d  mov     rsi, [rbx]
0x140063fa0  jmp     short loc_140063FA5
0x140063fa2  mov     rsi, rbx
0x140063fa5  mov     [rbx+10h], rdx
0x140063fa9  lea     rbx, [rdx+rdx]
0x140063fad  mov     r8, rbx; Size
0x140063fb0  mov     rdx, r9; Src
0x140063fb3  mov     rcx, rsi; void *
0x140063fb6  call    memmove_0
0x140063fbb  mov     [rbx+rsi], r15w
0x140063fc0  jmp     short loc_140063FCA
0x140063fc2  mov     rcx, rbx
0x140063fc5  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x140063fca  mov     r9, [rbp+57h+ReferencedDomainName]
0x140063fce  inc     rdi
0x140063fd1  cmp     [r9+rdi*2], r15w
0x140063fd6  jnz     short loc_140063FCE
0x140063fd8  cmp     rdi, [r14+18h]
0x140063fdc  ja      short loc_14006400A
0x140063fde  cmp     qword ptr [r14+18h], 7
0x140063fe3  jbe     short loc_140063FEA
0x140063fe5  mov     rsi, [r14]
0x140063fe8  jmp     short loc_140063FED
0x140063fea  mov     rsi, r14
0x140063fed  mov     [r14+10h], rdi
0x140063ff1  lea     rbx, [rdi+rdi]
0x140063ff5  mov     r8, rbx; Size
0x140063ff8  mov     rdx, r9; Src
0x140063ffb  mov     rcx, rsi; void *
0x140063ffe  call    memmove_0
0x140064003  mov     [rbx+rsi], r15w
0x140064008  jmp     short loc_140064016
0x14006400a  mov     rdx, rdi
0x14006400d  mov     rcx, r14
0x140064010  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x140064015  nop
0x140064016  lea     rcx, [rbp+57h+ReferencedDomainName]
0x14006401a  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x14006401f  nop
0x140064020  lea     rcx, [rbp+57h+Name]
0x140064024  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x140064029  mov     rax, 8000000000h
0x140064033  jmp     short loc_140064078
0x140064035  mov     edx, 5Ch ; '\'; Ch
0x14006403a  lea     rcx, aAdminAppmanApp_9; "admin\\appman\\appv\\shared\\user\\user"...
0x140064041  call    cs:__imp_strrchr
0x140064047  test    rax, rax
0x14006404a  jz      short loc_140064051
0x14006404c  inc     rax
0x14006404f  jmp     short loc_140064058
0x140064051  lea     rax, aAdminAppmanApp_9; "admin\\appman\\appv\\shared\\user\\user"...
0x140064058  mov     rdx, rax; char *
0x14006405b  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140064062  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140064067  shl     rax, 34h
0x14006406b  mov     rcx, 1D25000004E9h
0x140064075  or      rax, rcx
0x140064078  mov     rcx, [rbp+57h+var_30]
0x14006407c  xor     rcx, rsp; StackCookie
0x14006407f  call    __security_check_cookie
0x140064084  mov     rbx, [rsp+100h+arg_18]
0x14006408c  add     rsp, 0E0h
0x140064093  pop     r15
0x140064095  pop     r14
0x140064097  pop     rdi
0x140064098  pop     rsi
0x140064099  pop     rbp
0x14006409a  retn
```
