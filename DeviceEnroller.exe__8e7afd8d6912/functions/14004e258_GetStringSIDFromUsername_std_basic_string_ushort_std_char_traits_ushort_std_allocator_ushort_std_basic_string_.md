# GetStringSIDFromUsername(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x14004e258`
- end: `0x14004e4b5`
- name: `?GetStringSIDFromUsername@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z`
- size: `605`
- prototype: `__int64 __fastcall(LPCWSTR lpAccountName)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004dcbc`

## callees

- `0x1400042f0`
- `0x140005c81`
- `0x1400095b4`
- `0x14001e838`
- `0x14001ed14`
- `0x14004e258`
- `0x14004f4d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14004e42c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14004e445`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14004e42c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14004e445`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14004e32a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14004e34e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14004e32a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14004e34e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004e315`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004e33f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004e41e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004e437`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004e315`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004e33f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004e41e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004e437`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e2cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e3af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e2cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e3af`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x14004e2c9`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x14004e386`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x14004e2c9`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x14004e386`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004e413`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004e413`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14004e3a5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14004e3a5`

## string_xrefs

- `0x14004e2f9`: `GetStringSIDFromUsername - Username does not map to a SID`
- `0x14004e3b7`: `GetStringSIDFromUsername - ::ConvertSidToStringSid failed with error: 0x%1!x!`
- `0x14004e2dc`: `GetStringSIDFromUsername - ::LookupAccountName failed with error: %1!d!`
- `0x14004e45d`: `GetStringSIDFromUsername - ::LookupAccountName failed with error: %1!d!`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetStringSIDFromUsername(WCHAR *lpAccountName, char **a2)
{
  const WCHAR *v4; // rdx
  DWORD LastError; // eax
  __int64 v6; // rdx
  WCHAR *v7; // r12
  SIZE_T v8; // rbx
  HANDLE ProcessHeap; // rax
  void *v10; // r15
  SIZE_T v11; // rbx
  HANDLE v12; // rax
  const WCHAR *v13; // rdx
  __int64 v14; // r8
  DWORD v15; // eax
  LPWSTR v16; // r9
  unsigned __int64 v17; // rdx
  char *v18; // r14
  __int64 v19; // rbx
  HANDLE v20; // rax
  HANDLE v21; // rax
  int ReferencedDomainName; // [rsp+20h] [rbp-50h]
  DWORD cbSid; // [rsp+40h] [rbp-30h] BYREF
  DWORD cchReferencedDomainName; // [rsp+44h] [rbp-2Ch] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-28h] BYREF
  LPWSTR StringSid[2]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  StringSid[1] = lpAccountName;
  peUse = 0;
  cchReferencedDomainName = 0;
  cbSid = 0;
  StringSid[0] = 0;
  if ( *((_QWORD *)lpAccountName + 3) <= 7u )
    v4 = lpAccountName;
  else
    v4 = *(const WCHAR **)lpAccountName;
  LookupAccountNameW(0, v4, 0, &cbSid, 0, &cchReferencedDomainName, &peUse);
  LastError = GetLastError();
  if ( LastError != 122 )
  {
    LogTelemetryError(L"GetStringSIDFromUsername - ::LookupAccountName failed with error: %1!d!", LastError);
    v6 = 778;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\utils.cpp",
      (const char *)0x8000FFFFLL,
      ReferencedDomainName);
    std::wstring::~wstring((char **)lpAccountName);
    return 2147549183LL;
  }
  if ( !cbSid )
  {
    LogTelemetryError(L"GetStringSIDFromUsername - Username does not map to a SID");
    v6 = 783;
    goto LABEL_31;
  }
  v7 = 0;
  v8 = cbSid;
  ProcessHeap = GetProcessHeap();
  v10 = HeapAlloc(ProcessHeap, 8u, v8);
  if ( cchReferencedDomainName )
  {
    v11 = 2LL * cchReferencedDomainName;
    v12 = GetProcessHeap();
    v7 = (WCHAR *)HeapAlloc(v12, 8u, v11);
  }
  if ( *((_QWORD *)lpAccountName + 3) <= 7u )
    v13 = lpAccountName;
  else
    v13 = *(const WCHAR **)lpAccountName;
  if ( !LookupAccountNameW(0, v13, v10, &cbSid, v7, &cchReferencedDomainName, &peUse) || !cbSid )
  {
    LogTelemetryError(L"GetStringSIDFromUsername - ::LookupAccountName failed with error: %1!d!", 122);
    v6 = 797;
    goto LABEL_31;
  }
  if ( !ConvertSidToStringSidW(v10, StringSid) )
  {
    v15 = GetLastError();
    LogTelemetryError(L"GetStringSIDFromUsername - ::ConvertSidToStringSid failed with error: 0x%1!x!", v15);
  }
  v16 = StringSid[0];
  v17 = -1;
  do
    ++v17;
  while ( StringSid[0][v17] );
  if ( v17 > (unsigned __int64)a2[3] )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      a2,
      v17,
      v14,
      StringSid[0]);
  }
  else
  {
    if ( (unsigned __int64)a2[3] <= 7 )
      v18 = (char *)a2;
    else
      v18 = *a2;
    a2[2] = (char *)v17;
    v19 = 2 * v17;
    memmove_0(v18, v16, 2 * v17);
    *(_WORD *)&v18[v19] = 0;
  }
  LocalFree(StringSid[0]);
  if ( v10 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v10);
  }
  if ( v7 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v7);
  }
  std::wstring::~wstring((char **)lpAccountName);
  return 0;
}

```

## disassembly

```asm
0x14004e258  mov     [rsp-38h+arg_10], rbx
0x14004e25d  push    rbp
0x14004e25e  push    rsi
0x14004e25f  push    rdi
0x14004e260  push    r12
0x14004e262  push    r13
0x14004e264  push    r14
0x14004e266  push    r15
0x14004e268  mov     rbp, rsp
0x14004e26b  sub     rsp, 70h
0x14004e26f  mov     rax, cs:__security_cookie
0x14004e276  xor     rax, rsp
0x14004e279  mov     [rbp+var_10], rax
0x14004e27d  mov     rsi, rdx
0x14004e280  mov     rdi, rcx
0x14004e283  mov     [rbp+var_18], rcx
0x14004e287  xor     r13d, r13d
0x14004e28a  mov     [rbp+var_28], r13d
0x14004e28e  mov     [rbp+var_2C], r13d
0x14004e292  mov     [rbp+cbSid], r13d
0x14004e296  mov     [rbp+StringSid], r13
0x14004e29a  cmp     qword ptr [rcx+18h], 7
0x14004e29f  jbe     short loc_14004E2A6
0x14004e2a1  mov     rdx, [rcx]
0x14004e2a4  jmp     short loc_14004E2A9
0x14004e2a6  mov     rdx, rdi; lpAccountName
0x14004e2a9  lea     rax, [rbp+var_28]
0x14004e2ad  mov     [rsp+70h+peUse], rax; peUse
0x14004e2b2  lea     rax, [rbp+var_2C]
0x14004e2b6  mov     [rsp+70h+cchReferencedDomainName], rax; cchReferencedDomainName
0x14004e2bb  mov     [rsp+70h+ReferencedDomainName], r13; ReferencedDomainName
0x14004e2c0  lea     r9, [rbp+cbSid]; cbSid
0x14004e2c4  xor     r8d, r8d; Sid
0x14004e2c7  xor     ecx, ecx; lpSystemName
0x14004e2c9  call    cs:__imp_LookupAccountNameW
0x14004e2cf  call    cs:__imp_GetLastError
0x14004e2d5  cmp     eax, 7Ah ; 'z'
0x14004e2d8  jz      short loc_14004E2F2
0x14004e2da  mov     edx, eax
0x14004e2dc  lea     rcx, aGetstringsidfr; "GetStringSIDFromUsername - ::LookupAcco"...
0x14004e2e3  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14004e2e8  mov     edx, 30Ah
0x14004e2ed  jmp     loc_14004E46E
0x14004e2f2  mov     eax, [rbp+cbSid]
0x14004e2f5  test    eax, eax
0x14004e2f7  jnz     short loc_14004E30F
0x14004e2f9  lea     rcx, aGetstringsidfr_1; "GetStringSIDFromUsername - Username doe"...
0x14004e300  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14004e305  mov     edx, 30Fh
0x14004e30a  jmp     loc_14004E46E
0x14004e30f  mov     r12, r13
0x14004e312  mov     rbx, rax
0x14004e315  call    cs:__imp_GetProcessHeap
0x14004e31b  mov     r8, rbx; dwBytes
0x14004e31e  mov     r14d, 8
0x14004e324  mov     edx, r14d; dwFlags
0x14004e327  mov     rcx, rax; hHeap
0x14004e32a  call    cs:__imp_HeapAlloc
0x14004e330  mov     r15, rax
0x14004e333  mov     eax, [rbp+var_2C]
0x14004e336  test    eax, eax
0x14004e338  jz      short loc_14004E357
0x14004e33a  mov     ebx, eax
0x14004e33c  add     rbx, rbx
0x14004e33f  call    cs:__imp_GetProcessHeap
0x14004e345  mov     r8, rbx; dwBytes
0x14004e348  mov     edx, r14d; dwFlags
0x14004e34b  mov     rcx, rax; hHeap
0x14004e34e  call    cs:__imp_HeapAlloc
0x14004e354  mov     r12, rax
0x14004e357  cmp     qword ptr [rdi+18h], 7
0x14004e35c  jbe     short loc_14004E363
0x14004e35e  mov     rdx, [rdi]
0x14004e361  jmp     short loc_14004E366
0x14004e363  mov     rdx, rdi; lpAccountName
0x14004e366  lea     rax, [rbp+var_28]
0x14004e36a  mov     [rsp+70h+peUse], rax; peUse
0x14004e36f  lea     rax, [rbp+var_2C]
0x14004e373  mov     [rsp+70h+cchReferencedDomainName], rax; cchReferencedDomainName
0x14004e378  mov     [rsp+70h+ReferencedDomainName], r12; int
0x14004e37d  lea     r9, [rbp+cbSid]; cbSid
0x14004e381  mov     r8, r15; Sid
0x14004e384  xor     ecx, ecx; lpSystemName
0x14004e386  call    cs:__imp_LookupAccountNameW
0x14004e38c  test    eax, eax
0x14004e38e  jz      loc_14004E458
0x14004e394  cmp     [rbp+cbSid], r13d
0x14004e398  jz      loc_14004E458
0x14004e39e  lea     rdx, [rbp+StringSid]; StringSid
0x14004e3a2  mov     rcx, r15; Sid
0x14004e3a5  call    cs:__imp_ConvertSidToStringSidW
0x14004e3ab  test    eax, eax
0x14004e3ad  jnz     short loc_14004E3C3
0x14004e3af  call    cs:__imp_GetLastError
0x14004e3b5  mov     edx, eax
0x14004e3b7  lea     rcx, aGetstringsidfr_0; "GetStringSIDFromUsername - ::ConvertSid"...
0x14004e3be  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14004e3c3  mov     r9, [rbp+StringSid]
0x14004e3c7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14004e3cb  inc     rdx
0x14004e3ce  cmp     [r9+rdx*2], r13w
0x14004e3d3  jnz     short loc_14004E3CB
0x14004e3d5  cmp     rdx, [rsi+18h]
0x14004e3d9  ja      short loc_14004E407
0x14004e3db  cmp     qword ptr [rsi+18h], 7
0x14004e3e0  jbe     short loc_14004E3E7
0x14004e3e2  mov     r14, [rsi]
0x14004e3e5  jmp     short loc_14004E3EA
0x14004e3e7  mov     r14, rsi
0x14004e3ea  mov     [rsi+10h], rdx
0x14004e3ee  lea     rbx, [rdx+rdx]
0x14004e3f2  mov     r8, rbx; Size
0x14004e3f5  mov     rdx, r9; Src
0x14004e3f8  mov     rcx, r14; void *
0x14004e3fb  call    memmove_0
0x14004e400  mov     [rbx+r14], r13w
0x14004e405  jmp     short loc_14004E40F
0x14004e407  mov     rcx, rsi
0x14004e40a  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x14004e40f  mov     rcx, [rbp+StringSid]; hMem
0x14004e413  call    cs:__imp_LocalFree
0x14004e419  test    r15, r15
0x14004e41c  jz      short loc_14004E432
0x14004e41e  call    cs:__imp_GetProcessHeap
0x14004e424  mov     rcx, rax; hHeap
0x14004e427  mov     r8, r15; lpMem
0x14004e42a  xor     edx, edx; dwFlags
0x14004e42c  call    cs:__imp_HeapFree
0x14004e432  test    r12, r12
0x14004e435  jz      short loc_14004E44C
0x14004e437  call    cs:__imp_GetProcessHeap
0x14004e43d  mov     rcx, rax; hHeap
0x14004e440  mov     r8, r12; lpMem
0x14004e443  xor     edx, edx; dwFlags
0x14004e445  call    cs:__imp_HeapFree
0x14004e44b  nop
0x14004e44c  mov     rcx, rdi
0x14004e44f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004e454  xor     eax, eax
0x14004e456  jmp     short loc_14004E491
0x14004e458  mov     edx, 7Ah ; 'z'
0x14004e45d  lea     rcx, aGetstringsidfr; "GetStringSIDFromUsername - ::LookupAcco"...
0x14004e464  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14004e469  mov     edx, 31Dh; void *
0x14004e46e  mov     ebx, 8000FFFFh
0x14004e473  mov     r9d, ebx; char *
0x14004e476  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x14004e47d  mov     rcx, [rbp+38h]; this
0x14004e481  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004e486  nop
0x14004e487  mov     rcx, rdi
0x14004e48a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004e48f  mov     eax, ebx
0x14004e491  mov     rcx, [rbp+var_10]
0x14004e495  xor     rcx, rsp; StackCookie
0x14004e498  call    __security_check_cookie
0x14004e49d  mov     rbx, [rsp+70h+arg_10]
0x14004e4a5  add     rsp, 70h
0x14004e4a9  pop     r15
0x14004e4ab  pop     r14
0x14004e4ad  pop     r13
0x14004e4af  pop     r12
0x14004e4b1  pop     rdi
0x14004e4b2  pop     rsi
0x14004e4b3  pop     rbp
0x14004e4b4  retn
```
