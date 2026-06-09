# BfeLookupAccountSid

- ea: `0x18003a4d8`
- end: `0x18003a612`
- name: `BfeLookupAccountSid`
- size: `314`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003a2e8`
- `0x18003a434`

## callees

- `0x18000e000`
- `0x18001236c`
- `0x180018b74`
- `0x180022190`
- `0x18003a4d8`
- `0x18003a618`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a5be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a5a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a5be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a5a2`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18003a555`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18008a594`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18003a555`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18008a594`

## string_xrefs

- `0x18003a5d8`: `LookupAccountSidW`
- `0x18008a5ab`: `LookupAccountSidW`
- `0x18003a601`: `BfeLookupAccountSid`

## pseudocode

```c
__int64 __fastcall BfeLookupAccountSid(PSID Sid, _QWORD *a2)
{
  WCHAR *v2; // rdi
  WCHAR *v3; // rsi
  __int64 v6; // rax
  __int64 v7; // rbx
  DWORD LastError; // eax
  __int64 v10; // rcx
  __int64 v11; // rax
  DWORD v12; // eax
  __int64 v13; // rcx
  LPWSTR v14; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR v15; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-BCh] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR ReferencedDomainName[64]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[64]; // [rsp+D0h] [rbp-30h] BYREF

  *a2 = 0;
  cchName = 64;
  v2 = Name;
  cchReferencedDomainName = 64;
  v3 = ReferencedDomainName;
  v14 = Name;
  v15 = ReferencedDomainName;
  peUse = 0;
  if ( LookupAccountSidLocalW(Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
    goto LABEL_2;
  LastError = GetLastError();
  if ( LastError != 122 && LastError )
  {
    v7 = WfpReportSysErrorAsWinError(v10, "LookupAccountSidW", LastError);
    goto LABEL_8;
  }
  v7 = WfpMemAllocArray(cchName, 2, 0, &v14);
  if ( !v7 )
  {
    v11 = WfpMemAllocArray(cchReferencedDomainName, 2, 0, &v15);
    v3 = v15;
    v7 = v11;
    v2 = v14;
    if ( v11 )
    {
LABEL_4:
      if ( v3 != ReferencedDomainName )
        WfpMemFree(&v15);
      goto LABEL_6;
    }
    if ( !LookupAccountSidLocalW(Sid, v14, &cchName, v15, &cchReferencedDomainName, &peUse) )
    {
      v12 = GetLastError();
      v6 = WfpReportSysErrorAsWinError(v13, "LookupAccountSidW", v12);
      goto LABEL_3;
    }
LABEL_2:
    v6 = BfeStringBuild(a2, v3, L"\\", v2, 0);
LABEL_3:
    v7 = v6;
    goto LABEL_4;
  }
  v2 = v14;
LABEL_6:
  if ( v2 != Name )
    WfpMemFree(&v14);
LABEL_8:
  if ( v7 )
    WfpReportError(v7, "BfeLookupAccountSid");
  return v7;
}

```

## disassembly

```asm
0x18003a4d8  mov     [rsp-8+arg_10], rbx
0x18003a4dd  push    rbp
0x18003a4de  push    rsi
0x18003a4df  push    rdi
0x18003a4e0  push    r14
0x18003a4e2  push    r15
0x18003a4e4  lea     rbp, [rsp-60h]
0x18003a4e9  sub     rsp, 160h
0x18003a4f0  mov     rax, cs:__security_cookie
0x18003a4f7  xor     rax, rsp
0x18003a4fa  mov     [rbp+80h+var_30], rax
0x18003a4fe  mov     eax, 40h ; '@'
0x18003a503  mov     qword ptr [rdx], 0
0x18003a50a  mov     [rsp+180h+cchName], eax
0x18003a50e  lea     rdi, [rbp+80h+Name]
0x18003a512  mov     [rsp+180h+var_140], eax
0x18003a516  lea     rsi, [rsp+180h+ReferencedDomainName]
0x18003a51b  lea     rax, [rsp+180h+var_138]
0x18003a520  mov     [rsp+180h+var_150], rdi
0x18003a525  mov     [rsp+180h+peUse], rax; peUse
0x18003a52a  lea     r9, [rsp+180h+ReferencedDomainName]; ReferencedDomainName
0x18003a52f  lea     rax, [rsp+180h+var_140]
0x18003a534  mov     [rsp+180h+var_148], rsi
0x18003a539  mov     r14, rdx
0x18003a53c  mov     [rsp+180h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18003a541  lea     r8, [rsp+180h+cchName]; cchName
0x18003a546  mov     [rsp+180h+var_138], 0
0x18003a54e  lea     rdx, [rbp+80h+Name]; Name
0x18003a552  mov     r15, rcx
0x18003a555  call    cs:__imp_LookupAccountSidLocalW
0x18003a55b  test    eax, eax
0x18003a55d  jz      short loc_18003A5BE
0x18003a55f  mov     r9, rdi
0x18003a562  mov     [rsp+180h+cchReferencedDomainName], 0
0x18003a56b  lea     r8, asc_1800BD160; "\\"
0x18003a572  mov     rdx, rsi
0x18003a575  mov     rcx, r14
0x18003a578  call    BfeStringBuild
0x18003a57d  mov     rbx, rax
0x18003a580  lea     rax, [rsp+180h+ReferencedDomainName]
0x18003a585  cmp     rsi, rax
0x18003a588  jnz     short loc_18003A5E9
0x18003a58a  lea     rax, [rbp+80h+Name]
0x18003a58e  cmp     rdi, rax
0x18003a591  jnz     short loc_18003A5F5
0x18003a593  test    rbx, rbx
0x18003a596  jnz     short loc_18003A601
0x18003a598  mov     rax, rbx
0x18003a59b  mov     rcx, [rbp+80h+var_30]
0x18003a59f  xor     rcx, rsp; StackCookie
0x18003a5a2  call    __security_check_cookie
0x18003a5a7  mov     rbx, [rsp+180h+arg_10]
0x18003a5af  add     rsp, 160h
0x18003a5b6  pop     r15
0x18003a5b8  pop     r14
0x18003a5ba  pop     rdi
0x18003a5bb  pop     rsi
0x18003a5bc  pop     rbp
0x18003a5bd  retn
0x18003a5be  call    cs:__imp_GetLastError
0x18003a5c4  cmp     eax, 7Ah ; 'z'
0x18003a5c7  jz      loc_18008A52A
0x18003a5cd  test    eax, eax
0x18003a5cf  jz      loc_18008A52A
0x18003a5d5  mov     r8d, eax
0x18003a5d8  lea     rdx, aLookupaccounts_0; "LookupAccountSidW"
0x18003a5df  call    WfpReportSysErrorAsWinError
0x18003a5e4  mov     rbx, rax
0x18003a5e7  jmp     short loc_18003A593
0x18003a5e9  lea     rcx, [rsp+180h+var_148]
0x18003a5ee  call    WfpMemFree
0x18003a5f3  jmp     short loc_18003A58A
0x18003a5f5  lea     rcx, [rsp+180h+var_150]
0x18003a5fa  call    WfpMemFree
0x18003a5ff  jmp     short loc_18003A593
0x18003a601  lea     rdx, aBfelookupaccou_0; "BfeLookupAccountSid"
0x18003a608  mov     rcx, rbx
0x18003a60b  call    WfpReportError
0x18003a610  jmp     short loc_18003A598
0x18008a52a  mov     ecx, [rsp+180h+cchName]
0x18008a52e  lea     r9, [rsp+180h+var_150]
0x18008a533  xor     r8d, r8d
0x18008a536  lea     edi, [r8+2]
0x18008a53a  mov     edx, edi
0x18008a53c  call    WfpMemAllocArray
0x18008a541  mov     rbx, rax
0x18008a544  test    rax, rax
0x18008a547  jnz     short loc_18008A5BD
0x18008a549  mov     ecx, [rsp+180h+var_140]
0x18008a54d  lea     r9, [rsp+180h+var_148]
0x18008a552  xor     r8d, r8d
0x18008a555  mov     edx, edi
0x18008a557  call    WfpMemAllocArray
0x18008a55c  mov     rsi, [rsp+180h+var_148]
0x18008a561  mov     rbx, rax
0x18008a564  mov     rdi, [rsp+180h+var_150]
0x18008a569  test    rax, rax
0x18008a56c  jnz     loc_18003A580
0x18008a572  lea     rax, [rsp+180h+var_138]
0x18008a577  mov     r9, rsi; ReferencedDomainName
0x18008a57a  mov     [rsp+180h+peUse], rax; peUse
0x18008a57f  lea     r8, [rsp+180h+cchName]; cchName
0x18008a584  lea     rax, [rsp+180h+var_140]
0x18008a589  mov     rdx, rdi; Name
0x18008a58c  mov     rcx, r15; Sid
0x18008a58f  mov     [rsp+180h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18008a594  call    cs:__imp_LookupAccountSidLocalW
0x18008a59a  test    eax, eax
0x18008a59c  jnz     loc_18003A55F
0x18008a5a2  call    cs:__imp_GetLastError
0x18008a5a8  mov     r8d, eax
0x18008a5ab  lea     rdx, aLookupaccounts_0; "LookupAccountSidW"
0x18008a5b2  call    WfpReportSysErrorAsWinError
0x18008a5b7  nop
0x18008a5b8  jmp     loc_18003A57D
0x18008a5bd  mov     rdi, [rsp+180h+var_150]
0x18008a5c2  jmp     loc_18003A58A
```
