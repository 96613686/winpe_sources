# BfeLookupAccountSid

- ea: `0x18002922c`
- end: `0x180029376`
- name: `BfeLookupAccountSid`
- size: `330`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029174`
- `0x180029a54`

## callees

- `0x18000e7e0`
- `0x180012d8c`
- `0x1800197d0`
- `0x180024880`
- `0x180027584`
- `0x18002922c`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c1e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c1e0`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800292a9`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18008c1cc`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800292a9`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18008c1cc`

## string_xrefs

- `0x180029339`: `LookupAccountSidW`
- `0x18008c1ef`: `LookupAccountSidW`
- `0x180029362`: `BfeLookupAccountSid`

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
0x18002922c  mov     [rsp-8+arg_10], rbx
0x180029231  push    rbp
0x180029232  push    rsi
0x180029233  push    rdi
0x180029234  push    r14
0x180029236  push    r15
0x180029238  lea     rbp, [rsp-60h]
0x18002923d  sub     rsp, 160h
0x180029244  mov     rax, cs:__security_cookie
0x18002924b  xor     rax, rsp
0x18002924e  mov     [rbp+80h+var_30], rax
0x180029252  mov     eax, 40h ; '@'
0x180029257  mov     qword ptr [rdx], 0
0x18002925e  mov     [rsp+180h+cchName], eax
0x180029262  lea     rdi, [rbp+80h+Name]
0x180029266  mov     [rsp+180h+var_140], eax
0x18002926a  lea     rsi, [rsp+180h+ReferencedDomainName]
0x18002926f  lea     rax, [rsp+180h+var_138]
0x180029274  mov     [rsp+180h+var_150], rdi
0x180029279  mov     [rsp+180h+peUse], rax; peUse
0x18002927e  lea     r9, [rsp+180h+ReferencedDomainName]; ReferencedDomainName
0x180029283  lea     rax, [rsp+180h+var_140]
0x180029288  mov     [rsp+180h+var_148], rsi
0x18002928d  mov     r14, rdx
0x180029290  mov     [rsp+180h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180029295  lea     r8, [rsp+180h+cchName]; cchName
0x18002929a  mov     [rsp+180h+var_138], 0
0x1800292a2  lea     rdx, [rbp+80h+Name]; Name
0x1800292a6  mov     r15, rcx
0x1800292a9  call    cs:__imp_LookupAccountSidLocalW
0x1800292b0  nop     dword ptr [rax+rax+00h]
0x1800292b5  test    eax, eax
0x1800292b7  jz      short loc_180029319
0x1800292b9  mov     r9, rdi
0x1800292bc  mov     [rsp+180h+cchReferencedDomainName], 0
0x1800292c5  lea     r8, asc_1800B6FC0; "\\"
0x1800292cc  mov     rdx, rsi
0x1800292cf  mov     rcx, r14
0x1800292d2  call    BfeStringBuild
0x1800292d7  mov     rbx, rax
0x1800292da  lea     rax, [rsp+180h+ReferencedDomainName]
0x1800292df  cmp     rsi, rax
0x1800292e2  jnz     short loc_18002934A
0x1800292e4  lea     rax, [rbp+80h+Name]
0x1800292e8  cmp     rdi, rax
0x1800292eb  jnz     short loc_180029356
0x1800292ed  test    rbx, rbx
0x1800292f0  jnz     short loc_180029362
0x1800292f2  mov     rax, rbx
0x1800292f5  mov     rcx, [rbp+80h+var_30]
0x1800292f9  xor     rcx, rsp; StackCookie
0x1800292fc  call    __security_check_cookie
0x180029301  mov     rbx, [rsp+180h+arg_10]
0x180029309  add     rsp, 160h
0x180029310  pop     r15
0x180029312  pop     r14
0x180029314  pop     rdi
0x180029315  pop     rsi
0x180029316  pop     rbp
0x180029317  retn
0x180029319  call    cs:__imp_GetLastError
0x180029320  nop     dword ptr [rax+rax+00h]
0x180029325  cmp     eax, 7Ah ; 'z'
0x180029328  jz      loc_18008C15E
0x18002932e  test    eax, eax
0x180029330  jz      loc_18008C15E
0x180029336  mov     r8d, eax
0x180029339  lea     rdx, aLookupaccounts_0; "LookupAccountSidW"
0x180029340  call    WfpReportSysErrorAsWinError
0x180029345  mov     rbx, rax
0x180029348  jmp     short loc_1800292ED
0x18002934a  lea     rcx, [rsp+180h+var_148]
0x18002934f  call    WfpMemFree
0x180029354  jmp     short loc_1800292E4
0x180029356  lea     rcx, [rsp+180h+var_150]
0x18002935b  call    WfpMemFree
0x180029360  jmp     short loc_1800292ED
0x180029362  lea     rdx, aBfelookupaccou_0; "BfeLookupAccountSid"
0x180029369  mov     rcx, rbx
0x18002936c  call    WfpReportError
0x180029371  jmp     loc_1800292F2
0x18008c15e  mov     ecx, [rsp+180h+cchName]
0x18008c162  lea     r9, [rsp+180h+var_150]
0x18008c167  xor     r8d, r8d
0x18008c16a  lea     edi, [r8+2]
0x18008c16e  mov     edx, edi
0x18008c170  call    WfpMemAllocArray
0x18008c175  mov     rbx, rax
0x18008c178  test    rax, rax
0x18008c17b  jnz     loc_18008C201
0x18008c181  mov     ecx, [rsp+180h+var_140]
0x18008c185  lea     r9, [rsp+180h+var_148]
0x18008c18a  xor     r8d, r8d
0x18008c18d  mov     edx, edi
0x18008c18f  call    WfpMemAllocArray
0x18008c194  mov     rsi, [rsp+180h+var_148]
0x18008c199  mov     rbx, rax
0x18008c19c  mov     rdi, [rsp+180h+var_150]
0x18008c1a1  test    rax, rax
0x18008c1a4  jnz     loc_1800292DA
0x18008c1aa  lea     rax, [rsp+180h+var_138]
0x18008c1af  mov     r9, rsi; ReferencedDomainName
0x18008c1b2  mov     [rsp+180h+peUse], rax; peUse
0x18008c1b7  lea     r8, [rsp+180h+cchName]; cchName
0x18008c1bc  lea     rax, [rsp+180h+var_140]
0x18008c1c1  mov     rdx, rdi; Name
0x18008c1c4  mov     rcx, r15; Sid
0x18008c1c7  mov     [rsp+180h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18008c1cc  call    cs:__imp_LookupAccountSidLocalW
0x18008c1d3  nop     dword ptr [rax+rax+00h]
0x18008c1d8  test    eax, eax
0x18008c1da  jnz     loc_1800292B9
0x18008c1e0  call    cs:__imp_GetLastError
0x18008c1e7  nop     dword ptr [rax+rax+00h]
0x18008c1ec  mov     r8d, eax
0x18008c1ef  lea     rdx, aLookupaccounts_0; "LookupAccountSidW"
0x18008c1f6  call    WfpReportSysErrorAsWinError
0x18008c1fb  nop
0x18008c1fc  jmp     loc_1800292D7
0x18008c201  mov     rdi, [rsp+180h+var_150]
0x18008c206  jmp     loc_1800292E4
```
