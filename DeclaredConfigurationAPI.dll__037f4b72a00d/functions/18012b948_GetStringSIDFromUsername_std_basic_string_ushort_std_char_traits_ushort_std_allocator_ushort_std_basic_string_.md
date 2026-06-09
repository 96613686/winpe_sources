# GetStringSIDFromUsername(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18012b948`
- end: `0x18012bb74`
- name: `?GetStringSIDFromUsername@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z`
- size: `556`
- prototype: `__int64 __fastcall(LPCWSTR lpAccountName)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18012b480`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180018ac0`
- `0x180019d38`
- `0x18012b948`
- `0x18012c77c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18012baea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18012bb03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18012baea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18012bb03`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18012ba18`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18012ba3e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18012ba18`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18012ba3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012ba07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012ba2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012badc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012baf5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012ba07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012ba2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012badc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012baf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b9c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012ba9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b9c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012ba9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18012bad1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18012bad1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18012ba95`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18012ba95`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18012b9bb`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18012ba76`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18012b9bb`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18012ba76`

## string_xrefs

- `0x18012b9ce`: `GetStringSIDFromUsername - ::LookupAccountName failed with error: %1!d!`
- `0x18012bb1b`: `GetStringSIDFromUsername - ::LookupAccountName failed with error: %1!d!`
- `0x18012b9eb`: `GetStringSIDFromUsername - Username does not map to a SID`
- `0x18012baa7`: `GetStringSIDFromUsername - ::ConvertSidToStringSid failed with error: 0x%1!x!`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetStringSIDFromUsername(WCHAR *lpAccountName, char **a2)
{
  const WCHAR *v4; // rdx
  DWORD LastError; // eax
  __int64 v6; // rdx
  WCHAR *v7; // rsi
  SIZE_T v8; // rbx
  HANDLE ProcessHeap; // rax
  void *v10; // r14
  SIZE_T v11; // rbx
  HANDLE v12; // rax
  const WCHAR *v13; // rdx
  DWORD v14; // eax
  __int64 v15; // r8
  HANDLE v16; // rax
  HANDLE v17; // rax
  int ReferencedDomainName; // [rsp+20h] [rbp-50h]
  DWORD cbSid; // [rsp+40h] [rbp-30h] BYREF
  DWORD cchReferencedDomainName; // [rsp+44h] [rbp-2Ch] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-28h] BYREF
  LPWSTR StringSid[2]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

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
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\utils.cpp",
      (const char *)0x8000FFFFLL,
      ReferencedDomainName);
    std::wstring::_Tidy_deallocate(lpAccountName);
    return 2147549183LL;
  }
  if ( !cbSid )
  {
    LogTelemetryError(L"GetStringSIDFromUsername - Username does not map to a SID");
    v6 = 783;
    goto LABEL_25;
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
    goto LABEL_25;
  }
  if ( !ConvertSidToStringSidW(v10, StringSid) )
  {
    v14 = GetLastError();
    LogTelemetryError(L"GetStringSIDFromUsername - ::ConvertSidToStringSid failed with error: 0x%1!x!", v14);
  }
  v15 = -1;
  do
    ++v15;
  while ( StringSid[0][v15] );
  std::wstring::_Assign<unsigned short>(a2, StringSid[0], (char *)v15);
  LocalFree(StringSid[0]);
  if ( v10 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v10);
  }
  if ( v7 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v7);
  }
  std::wstring::_Tidy_deallocate(lpAccountName);
  return 0;
}

```

## disassembly

```asm
0x18012b948  mov     [rsp-28h+arg_10], rbx
0x18012b94d  mov     [rsp-28h+arg_18], rsi
0x18012b952  push    rbp
0x18012b953  push    rdi
0x18012b954  push    r12
0x18012b956  push    r14
0x18012b958  push    r15
0x18012b95a  mov     rbp, rsp
0x18012b95d  sub     rsp, 70h
0x18012b961  mov     rax, cs:__security_cookie
0x18012b968  xor     rax, rsp
0x18012b96b  mov     [rbp+var_10], rax
0x18012b96f  mov     r15, rdx
0x18012b972  mov     rdi, rcx
0x18012b975  mov     [rbp+var_18], rcx
0x18012b979  xor     r12d, r12d
0x18012b97c  mov     [rbp+var_28], r12d
0x18012b980  mov     [rbp+var_2C], r12d
0x18012b984  mov     [rbp+cbSid], r12d
0x18012b988  mov     [rbp+StringSid], r12
0x18012b98c  cmp     qword ptr [rcx+18h], 7
0x18012b991  jbe     short loc_18012B998
0x18012b993  mov     rdx, [rcx]
0x18012b996  jmp     short loc_18012B99B
0x18012b998  mov     rdx, rdi; lpAccountName
0x18012b99b  lea     rax, [rbp+var_28]
0x18012b99f  mov     [rsp+70h+peUse], rax; peUse
0x18012b9a4  lea     rax, [rbp+var_2C]
0x18012b9a8  mov     [rsp+70h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18012b9ad  mov     [rsp+70h+ReferencedDomainName], r12; ReferencedDomainName
0x18012b9b2  lea     r9, [rbp+cbSid]; cbSid
0x18012b9b6  xor     r8d, r8d; Sid
0x18012b9b9  xor     ecx, ecx; lpSystemName
0x18012b9bb  call    cs:__imp_LookupAccountNameW
0x18012b9c1  call    cs:__imp_GetLastError
0x18012b9c7  cmp     eax, 7Ah ; 'z'
0x18012b9ca  jz      short loc_18012B9E4
0x18012b9cc  mov     edx, eax
0x18012b9ce  lea     rcx, aGetstringsidfr; "GetStringSIDFromUsername - ::LookupAcco"...
0x18012b9d5  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x18012b9da  mov     edx, 30Ah
0x18012b9df  jmp     loc_18012BB2C
0x18012b9e4  mov     eax, [rbp+cbSid]
0x18012b9e7  test    eax, eax
0x18012b9e9  jnz     short loc_18012BA01
0x18012b9eb  lea     rcx, aGetstringsidfr_1; "GetStringSIDFromUsername - Username doe"...
0x18012b9f2  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x18012b9f7  mov     edx, 30Fh
0x18012b9fc  jmp     loc_18012BB2C
0x18012ba01  mov     rsi, r12
0x18012ba04  mov     rbx, rax
0x18012ba07  call    cs:__imp_GetProcessHeap
0x18012ba0d  mov     r8, rbx; dwBytes
0x18012ba10  mov     edx, 8; dwFlags
0x18012ba15  mov     rcx, rax; hHeap
0x18012ba18  call    cs:__imp_HeapAlloc
0x18012ba1e  mov     r14, rax
0x18012ba21  mov     eax, [rbp+var_2C]
0x18012ba24  test    eax, eax
0x18012ba26  jz      short loc_18012BA47
0x18012ba28  mov     ebx, eax
0x18012ba2a  add     rbx, rbx
0x18012ba2d  call    cs:__imp_GetProcessHeap
0x18012ba33  mov     r8, rbx; dwBytes
0x18012ba36  mov     edx, 8; dwFlags
0x18012ba3b  mov     rcx, rax; hHeap
0x18012ba3e  call    cs:__imp_HeapAlloc
0x18012ba44  mov     rsi, rax
0x18012ba47  cmp     qword ptr [rdi+18h], 7
0x18012ba4c  jbe     short loc_18012BA53
0x18012ba4e  mov     rdx, [rdi]
0x18012ba51  jmp     short loc_18012BA56
0x18012ba53  mov     rdx, rdi; lpAccountName
0x18012ba56  lea     rax, [rbp+var_28]
0x18012ba5a  mov     [rsp+70h+peUse], rax; peUse
0x18012ba5f  lea     rax, [rbp+var_2C]
0x18012ba63  mov     [rsp+70h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18012ba68  mov     [rsp+70h+ReferencedDomainName], rsi; int
0x18012ba6d  lea     r9, [rbp+cbSid]; cbSid
0x18012ba71  mov     r8, r14; Sid
0x18012ba74  xor     ecx, ecx; lpSystemName
0x18012ba76  call    cs:__imp_LookupAccountNameW
0x18012ba7c  test    eax, eax
0x18012ba7e  jz      loc_18012BB16
0x18012ba84  cmp     [rbp+cbSid], r12d
0x18012ba88  jz      loc_18012BB16
0x18012ba8e  lea     rdx, [rbp+StringSid]; StringSid
0x18012ba92  mov     rcx, r14; Sid
0x18012ba95  call    cs:__imp_ConvertSidToStringSidW
0x18012ba9b  test    eax, eax
0x18012ba9d  jnz     short loc_18012BAB3
0x18012ba9f  call    cs:__imp_GetLastError
0x18012baa5  mov     edx, eax
0x18012baa7  lea     rcx, aGetstringsidfr_0; "GetStringSIDFromUsername - ::ConvertSid"...
0x18012baae  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x18012bab3  mov     rdx, [rbp+StringSid]
0x18012bab7  or      r8, 0FFFFFFFFFFFFFFFFh
0x18012babb  inc     r8
0x18012babe  cmp     [rdx+r8*2], r12w
0x18012bac3  jnz     short loc_18012BABB
0x18012bac5  mov     rcx, r15
0x18012bac8  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18012bacd  mov     rcx, [rbp+StringSid]; hMem
0x18012bad1  call    cs:__imp_LocalFree
0x18012bad7  test    r14, r14
0x18012bada  jz      short loc_18012BAF0
0x18012badc  call    cs:__imp_GetProcessHeap
0x18012bae2  mov     rcx, rax; hHeap
0x18012bae5  mov     r8, r14; lpMem
0x18012bae8  xor     edx, edx; dwFlags
0x18012baea  call    cs:__imp_HeapFree
0x18012baf0  test    rsi, rsi
0x18012baf3  jz      short loc_18012BB0A
0x18012baf5  call    cs:__imp_GetProcessHeap
0x18012bafb  mov     rcx, rax; hHeap
0x18012bafe  mov     r8, rsi; lpMem
0x18012bb01  xor     edx, edx; dwFlags
0x18012bb03  call    cs:__imp_HeapFree
0x18012bb09  nop
0x18012bb0a  mov     rcx, rdi
0x18012bb0d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012bb12  xor     eax, eax
0x18012bb14  jmp     short loc_18012BB4F
0x18012bb16  mov     edx, 7Ah ; 'z'
0x18012bb1b  lea     rcx, aGetstringsidfr; "GetStringSIDFromUsername - ::LookupAcco"...
0x18012bb22  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x18012bb27  mov     edx, 31Dh; void *
0x18012bb2c  mov     ebx, 8000FFFFh
0x18012bb31  mov     r9d, ebx; char *
0x18012bb34  lea     r8, aOnecoreuapAdmi_35; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x18012bb3b  mov     rcx, [rbp+28h]; this
0x18012bb3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012bb44  nop
0x18012bb45  mov     rcx, rdi
0x18012bb48  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012bb4d  mov     eax, ebx
0x18012bb4f  mov     rcx, [rbp+var_10]
0x18012bb53  xor     rcx, rsp; StackCookie
0x18012bb56  call    __security_check_cookie
0x18012bb5b  lea     r11, [rsp+70h+var_s0]
0x18012bb60  mov     rbx, [r11+40h]
0x18012bb64  mov     rsi, [r11+48h]
0x18012bb68  mov     rsp, r11
0x18012bb6b  pop     r15
0x18012bb6d  pop     r14
0x18012bb6f  pop     r12
0x18012bb71  pop     rdi
0x18012bb72  pop     rbp
0x18012bb73  retn
```
