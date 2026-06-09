# DumpTokenInfo

- ea: `0x180027d30`
- end: `0x180027fc3`
- name: `DumpTokenInfo`
- size: `659`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180027fcc`

## callees

- `0x180002214`
- `0x180003180`
- `0x18000dce4`
- `0x18000dd60`
- `0x1800110fc`
- `0x180027d30`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027dcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027dcd`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180027e65`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180027f15`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180027e65`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180027f15`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027d8b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027db3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027e30`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027d8b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027db3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027e30`

## string_xrefs

- `0x180027f47`: `Attempting to create remote handler process as %ls\%ls in session %d`
- `0x180027ede`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhutil.cpp`
- `0x180027f26`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhutil.cpp`

## pseudocode

```c
__int64 __fastcall DumpTokenInfo(HANDLE TokenHandle)
{
  PSID *v1; // rbx
  WCHAR *v3; // rsi
  WCHAR *v4; // rdi
  const char *v5; // r9
  __int64 v6; // rdx
  unsigned int LastError; // r14d
  __int64 v8; // rdx
  DWORD v9; // r9d
  int ReturnLength; // [rsp+20h] [rbp-50h]
  DWORD TokenInformationLength; // [rsp+50h] [rbp-20h] BYREF
  DWORD cchReferencedDomainName; // [rsp+54h] [rbp-1Ch] BYREF
  DWORD cchName; // [rsp+58h] [rbp-18h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+5Ch] [rbp-14h] BYREF
  int TokenInformation; // [rsp+60h] [rbp-10h] BYREF
  DWORD v17; // [rsp+64h] [rbp-Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v1 = 0;
  peUse = 0;
  TokenInformation = 0;
  TokenInformationLength = 0;
  v17 = 0;
  cchReferencedDomainName = 0;
  cchName = 0;
  v3 = 0;
  v4 = 0;
  if ( !GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, &TokenInformationLength) )
  {
    v6 = 33;
LABEL_24:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v6,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhutil.cpp",
                  v5);
    goto LABEL_26;
  }
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    LastError = -2145120257;
    v8 = 34;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhutil.cpp",
      (const char *)LastError,
      ReturnLength);
    goto LABEL_26;
  }
  if ( GetLastError() != 122 )
  {
    v6 = 35;
    goto LABEL_24;
  }
  v9 = TokenInformationLength;
  if ( TokenInformationLength )
  {
    v1 = (PSID *)SafeSusAllocArray(TokenInformationLength, 1u);
    LastError = v1 == 0 ? 0x8007000E : 0;
    if ( !v1 )
    {
      v8 = 36;
      goto LABEL_21;
    }
    v9 = TokenInformationLength;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, v1, v9, &v17) )
  {
    v6 = 37;
    goto LABEL_24;
  }
  if ( LookupAccountSidW(0, *v1, 0, &cchName, 0, &cchReferencedDomainName, &peUse) )
  {
    LastError = -2145120257;
    v8 = 46;
    goto LABEL_21;
  }
  if ( cchName )
  {
    v3 = (WCHAR *)SafeSusAllocArray(cchName, 2u);
    LastError = v3 == 0 ? 0x8007000E : 0;
    if ( !v3 )
    {
      v8 = 48;
      goto LABEL_21;
    }
  }
  if ( cchReferencedDomainName )
  {
    v4 = (WCHAR *)SafeSusAllocArray(cchReferencedDomainName, 2u);
    LastError = v4 == 0 ? 0x8007000E : 0;
    if ( !v4 )
    {
      v8 = 49;
      goto LABEL_21;
    }
  }
  if ( !LookupAccountSidW(0, *v1, v3, &cchName, v4, &cchReferencedDomainName, &peUse) )
  {
    v6 = 57;
    goto LABEL_24;
  }
  WUTrace(0, 0, 0x1000000, 4);
  LastError = 0;
LABEL_26:
  if ( v4 )
    SusFree(v4);
  if ( v3 )
    SusFree(v3);
  if ( v1 )
    SusFree(v1);
  return LastError;
}

```

## disassembly

```asm
0x180027d30  mov     r11, rsp
0x180027d33  mov     [r11+10h], rbx
0x180027d37  mov     [r11+18h], rsi
0x180027d3b  mov     [r11+20h], rdi
0x180027d3f  push    rbp
0x180027d40  push    r14
0x180027d42  push    r15
0x180027d44  mov     rbp, rsp
0x180027d47  sub     rsp, 70h
0x180027d4b  mov     rax, cs:__security_cookie
0x180027d52  xor     rax, rsp
0x180027d55  mov     [rbp+var_8], rax
0x180027d59  xor     ebx, ebx
0x180027d5b  mov     [rbp+var_14], 0
0x180027d62  lea     rax, [rbp+TokenInformationLength]
0x180027d66  mov     [rbp+TokenInformation], ebx
0x180027d69  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180027d6d  mov     [rbp+TokenInformationLength], ebx
0x180027d70  mov     r15, rcx
0x180027d73  mov     [rbp+var_C], ebx
0x180027d76  lea     r9d, [rbx+4]; TokenInformationLength
0x180027d7a  mov     [rbp+var_1C], ebx
0x180027d7d  lea     edx, [rbx+0Ch]; TokenInformationClass
0x180027d80  mov     [rbp+cchName], ebx
0x180027d83  xor     esi, esi
0x180027d85  mov     [r11-68h], rax
0x180027d89  xor     edi, edi
0x180027d8b  call    cs:__imp_GetTokenInformation
0x180027d91  test    eax, eax
0x180027d93  jnz     short loc_180027D9D
0x180027d95  lea     edx, [rbx+21h]
0x180027d98  jmp     loc_180027F22
0x180027d9d  xor     r9d, r9d; TokenInformationLength
0x180027da0  lea     rax, [rbp+TokenInformationLength]
0x180027da4  xor     r8d, r8d; TokenInformation
0x180027da7  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180027dac  mov     rcx, r15; TokenHandle
0x180027daf  lea     edx, [r9+1]; TokenInformationClass
0x180027db3  call    cs:__imp_GetTokenInformation
0x180027db9  test    eax, eax
0x180027dbb  jz      short loc_180027DCD
0x180027dbd  mov     r14d, 80240FFFh
0x180027dc3  mov     edx, 22h ; '"'
0x180027dc8  jmp     loc_180027EDA
0x180027dcd  call    cs:__imp_GetLastError
0x180027dd3  cmp     eax, 7Ah ; 'z'
0x180027dd6  jz      short loc_180027DE2
0x180027dd8  mov     edx, 23h ; '#'
0x180027ddd  jmp     loc_180027F22
0x180027de2  mov     r9d, [rbp+TokenInformationLength]
0x180027de6  mov     ecx, r9d; unsigned __int64
0x180027de9  test    r9d, r9d
0x180027dec  jz      short loc_180027E1C
0x180027dee  mov     edx, 1; unsigned __int64
0x180027df3  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x180027df8  mov     rbx, rax
0x180027dfb  neg     rax
0x180027dfe  sbb     r14d, r14d
0x180027e01  not     r14d
0x180027e04  and     r14d, 8007000Eh
0x180027e0b  test    rbx, rbx
0x180027e0e  jnz     short loc_180027E18
0x180027e10  lea     edx, [rbx+24h]
0x180027e13  jmp     loc_180027EDA
0x180027e18  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180027e1c  lea     rax, [rbp+var_C]
0x180027e20  mov     r8, rbx; TokenInformation
0x180027e23  mov     edx, 1; TokenInformationClass
0x180027e28  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180027e2d  mov     rcx, r15; TokenHandle
0x180027e30  call    cs:__imp_GetTokenInformation
0x180027e36  test    eax, eax
0x180027e38  jnz     short loc_180027E42
0x180027e3a  lea     edx, [rax+25h]
0x180027e3d  jmp     loc_180027F22
0x180027e42  mov     rdx, [rbx]; Sid
0x180027e45  lea     rax, [rbp+var_14]
0x180027e49  mov     [rsp+70h+peUse], rax; peUse
0x180027e4e  lea     r9, [rbp+cchName]; cchName
0x180027e52  lea     rax, [rbp+var_1C]
0x180027e56  xor     r8d, r8d; Name
0x180027e59  mov     [rsp+70h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180027e5e  xor     ecx, ecx; lpSystemName
0x180027e60  mov     [rsp+70h+ReturnLength], rsi; int
0x180027e65  call    cs:__imp_LookupAccountSidW
0x180027e6b  test    eax, eax
0x180027e6d  jz      short loc_180027E7C
0x180027e6f  mov     r14d, 80240FFFh
0x180027e75  mov     edx, 2Eh ; '.'
0x180027e7a  jmp     short loc_180027EDA
0x180027e7c  mov     ecx, [rbp+cchName]; unsigned __int64
0x180027e7f  mov     r15d, 2
0x180027e85  test    rcx, rcx
0x180027e88  jz      short loc_180027EAF
0x180027e8a  mov     edx, r15d; unsigned __int64
0x180027e8d  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x180027e92  mov     rsi, rax
0x180027e95  neg     rax
0x180027e98  sbb     r14d, r14d
0x180027e9b  not     r14d
0x180027e9e  and     r14d, 8007000Eh
0x180027ea5  test    rsi, rsi
0x180027ea8  jnz     short loc_180027EAF
0x180027eaa  lea     edx, [rsi+30h]
0x180027ead  jmp     short loc_180027EDA
0x180027eaf  mov     ecx, [rbp+var_1C]; unsigned __int64
0x180027eb2  test    rcx, rcx
0x180027eb5  jz      short loc_180027EF2
0x180027eb7  mov     rdx, r15; unsigned __int64
0x180027eba  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x180027ebf  mov     rdi, rax
0x180027ec2  neg     rax
0x180027ec5  sbb     r14d, r14d
0x180027ec8  not     r14d
0x180027ecb  and     r14d, 8007000Eh
0x180027ed2  test    rdi, rdi
0x180027ed5  jnz     short loc_180027EF2
0x180027ed7  lea     edx, [rdi+31h]; void *
0x180027eda  mov     rcx, [rbp+18h]; this
0x180027ede  lea     r8, aCW1SSrcClientU_8; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180027ee5  mov     r9d, r14d; char *
0x180027ee8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027eed  jmp     loc_180027F73
0x180027ef2  mov     rdx, [rbx]; Sid
0x180027ef5  lea     rax, [rbp+var_14]
0x180027ef9  mov     [rsp+70h+peUse], rax; peUse
0x180027efe  lea     r9, [rbp+cchName]; cchName
0x180027f02  lea     rax, [rbp+var_1C]
0x180027f06  mov     r8, rsi; Name
0x180027f09  mov     [rsp+70h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180027f0e  xor     ecx, ecx; lpSystemName
0x180027f10  mov     [rsp+70h+ReturnLength], rdi; ReferencedDomainName
0x180027f15  call    cs:__imp_LookupAccountSidW
0x180027f1b  test    eax, eax
0x180027f1d  jnz     short loc_180027F37
0x180027f1f  lea     edx, [rax+39h]; void *
0x180027f22  mov     rcx, [rbp+18h]; this
0x180027f26  lea     r8, aCW1SSrcClientU_8; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180027f2d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027f32  mov     r14d, eax
0x180027f35  jmp     short loc_180027F73
0x180027f37  mov     eax, [rbp+TokenInformation]
0x180027f3a  xor     edx, edx
0x180027f3c  mov     [rsp+70h+var_30], eax
0x180027f40  xor     ecx, ecx
0x180027f42  mov     [rsp+70h+var_38], rsi
0x180027f47  lea     rax, aAttemptingToCr; "Attempting to create remote handler pro"...
0x180027f4e  mov     [rsp+70h+peUse], rdi
0x180027f53  mov     r8d, 1000000h
0x180027f59  mov     [rsp+70h+cchReferencedDomainName], rax
0x180027f5e  lea     r9d, [rdx+4]
0x180027f62  mov     [rsp+70h+ReturnLength], 0
0x180027f6b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180027f70  xor     r14d, r14d
0x180027f73  test    rdi, rdi
0x180027f76  jz      short loc_180027F80
0x180027f78  mov     rcx, rdi; lpMem
0x180027f7b  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180027f80  test    rsi, rsi
0x180027f83  jz      short loc_180027F8D
0x180027f85  mov     rcx, rsi; lpMem
0x180027f88  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180027f8d  test    rbx, rbx
0x180027f90  jz      short loc_180027F9A
0x180027f92  mov     rcx, rbx; lpMem
0x180027f95  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180027f9a  mov     eax, r14d
0x180027f9d  mov     rcx, [rbp+var_8]
0x180027fa1  xor     rcx, rsp; StackCookie
0x180027fa4  call    __security_check_cookie
0x180027fa9  lea     r11, [rsp+70h+var_s0]
0x180027fae  mov     rbx, [r11+28h]
0x180027fb2  mov     rsi, [r11+30h]
0x180027fb6  mov     rdi, [r11+38h]
0x180027fba  mov     rsp, r11
0x180027fbd  pop     r15
0x180027fbf  pop     r14
0x180027fc1  pop     rbp
0x180027fc2  retn
```
