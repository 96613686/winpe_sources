# GetStringSIDFromUsername(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x140016a88`
- end: `0x140016c98`
- name: `?GetStringSIDFromUsername@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z`
- size: `528`
- prototype: `__int64 __fastcall(WCHAR *lpAccountName, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140015b7c`

## callees

- `0x140006480`
- `0x140006604`
- `0x1400068c8`
- `0x14000740c`
- `0x140016a88`
- `0x14001a8d0`

## import_xrefs

- `ADVAPI32!LookupAccountNameW` at `0x140016b03`
- `ADVAPI32!LookupAccountNameW` at `0x140016bb4`
- `ADVAPI32!LookupAccountNameW` at `0x140016b03`
- `ADVAPI32!LookupAccountNameW` at `0x140016bb4`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140016bcd`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140016bcd`
- `KERNEL32!LocalFree` at `0x140016c06`
- `KERNEL32!LocalFree` at `0x140016c06`
- `KERNEL32!HeapFree` at `0x140016c37`
- `KERNEL32!HeapFree` at `0x140016c50`
- `KERNEL32!HeapFree` at `0x140016c37`
- `KERNEL32!HeapFree` at `0x140016c50`
- `KERNEL32!GetLastError` at `0x140016b09`
- `KERNEL32!GetLastError` at `0x140016bd7`
- `KERNEL32!GetLastError` at `0x140016b09`
- `KERNEL32!GetLastError` at `0x140016bd7`
- `KERNEL32!GetProcessHeap` at `0x140016b47`
- `KERNEL32!GetProcessHeap` at `0x140016b6c`
- `KERNEL32!GetProcessHeap` at `0x140016c29`
- `KERNEL32!GetProcessHeap` at `0x140016c42`
- `KERNEL32!GetProcessHeap` at `0x140016b47`
- `KERNEL32!GetProcessHeap` at `0x140016b6c`
- `KERNEL32!GetProcessHeap` at `0x140016c29`
- `KERNEL32!GetProcessHeap` at `0x140016c42`
- `KERNEL32!HeapAlloc` at `0x140016b57`
- `KERNEL32!HeapAlloc` at `0x140016b7c`
- `KERNEL32!HeapAlloc` at `0x140016b57`
- `KERNEL32!HeapAlloc` at `0x140016b7c`

## string_xrefs

- `0x140016b16`: `GetStringSIDFromUsername - ::LookupAccountName failed with error: %1!d!`
- `0x140016c13`: `GetStringSIDFromUsername - ::LookupAccountName failed with error: %1!d!`
- `0x140016b33`: `GetStringSIDFromUsername() - Username does not map to a SID`
- `0x140016bdf`: `GetStringSIDFromUsername - ::ConvertSidToStringSid failed with error: 0x%1!x!`
- `0x140016c5c`: `GetStringSIDFromUsername() failed hr=0x%1!x!`

## pseudocode

```c
__int64 __fastcall GetStringSIDFromUsername(WCHAR *lpAccountName, _QWORD *a2)
{
  const WCHAR *v4; // rdx
  DWORD LastError; // eax
  int v6; // ebx
  WCHAR *ReferencedDomainName; // r14
  SIZE_T v8; // rbx
  HANDLE ProcessHeap; // rax
  void *v10; // rsi
  SIZE_T v11; // rbx
  HANDLE v12; // rax
  const WCHAR *v13; // rdx
  DWORD v14; // eax
  __int64 v15; // rax
  unsigned __int64 v16; // rcx
  HANDLE v17; // rax
  HANDLE v18; // rax
  DWORD cbSid; // [rsp+40h] [rbp-30h] BYREF
  DWORD cchReferencedDomainName; // [rsp+44h] [rbp-2Ch] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-28h] BYREF
  LPWSTR StringSid[2]; // [rsp+50h] [rbp-20h] BYREF

  StringSid[1] = lpAccountName;
  peUse = 0;
  cchReferencedDomainName = 0;
  cbSid = 0;
  StringSid[0] = 0;
  if ( *((_QWORD *)lpAccountName + 3) < 8u )
    v4 = lpAccountName;
  else
    v4 = *(const WCHAR **)lpAccountName;
  LookupAccountNameW(0, v4, 0, &cbSid, 0, &cchReferencedDomainName, &peUse);
  LastError = GetLastError();
  if ( LastError != 122 )
  {
    LogError(L"GetStringSIDFromUsername - ::LookupAccountName failed with error: %1!d!", LastError);
LABEL_6:
    v6 = -2147418113;
LABEL_25:
    LogError(L"GetStringSIDFromUsername() failed hr=0x%1!x!", (unsigned int)v6);
    goto LABEL_26;
  }
  if ( !cbSid )
  {
    LogError(L"GetStringSIDFromUsername() - Username does not map to a SID");
    goto LABEL_6;
  }
  ReferencedDomainName = 0;
  v8 = cbSid;
  ProcessHeap = GetProcessHeap();
  v10 = HeapAlloc(ProcessHeap, 8u, v8);
  if ( cchReferencedDomainName )
  {
    v11 = 2LL * cchReferencedDomainName;
    v12 = GetProcessHeap();
    ReferencedDomainName = (WCHAR *)HeapAlloc(v12, 8u, v11);
  }
  if ( *((_QWORD *)lpAccountName + 3) < 8u )
    v13 = lpAccountName;
  else
    v13 = *(const WCHAR **)lpAccountName;
  if ( LookupAccountNameW(0, v13, v10, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) && cbSid )
  {
    v6 = 0;
    if ( !ConvertSidToStringSidW(v10, StringSid) )
    {
      v14 = GetLastError();
      LogError(L"GetStringSIDFromUsername - ::ConvertSidToStringSid failed with error: 0x%1!x!", v14);
    }
    v15 = std::char_traits<unsigned short>::length(StringSid[0]);
    std::wstring::assign(a2, v16, v15);
    LocalFree(StringSid[0]);
  }
  else
  {
    LogError(L"GetStringSIDFromUsername - ::LookupAccountName failed with error: %1!d!", 122);
    v6 = -2147418113;
  }
  if ( v10 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v10);
  }
  if ( ReferencedDomainName )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, ReferencedDomainName);
  }
  if ( v6 < 0 )
    goto LABEL_25;
LABEL_26:
  std::wstring::_Tidy(lpAccountName, 1, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140016a88  mov     [rsp-28h+arg_10], rbx
0x140016a8d  push    rbp
0x140016a8e  push    rsi
0x140016a8f  push    rdi
0x140016a90  push    r14
0x140016a92  push    r15
0x140016a94  mov     rbp, rsp
0x140016a97  sub     rsp, 70h
0x140016a9b  mov     rax, cs:__security_cookie
0x140016aa2  xor     rax, rsp
0x140016aa5  mov     [rbp+var_10], rax
0x140016aa9  mov     r15, rdx
0x140016aac  mov     rdi, rcx
0x140016aaf  mov     [rbp+var_18], rcx
0x140016ab3  mov     [rbp+var_28], 0
0x140016aba  mov     [rbp+var_2C], 0
0x140016ac1  mov     [rbp+cbSid], 0
0x140016ac8  mov     [rbp+StringSid], 0
0x140016ad0  cmp     qword ptr [rcx+18h], 8
0x140016ad5  jb      short loc_140016ADC
0x140016ad7  mov     rdx, [rcx]
0x140016ada  jmp     short loc_140016ADF
0x140016adc  mov     rdx, rdi; lpAccountName
0x140016adf  lea     rax, [rbp+var_28]
0x140016ae3  mov     [rsp+70h+peUse], rax; peUse
0x140016ae8  lea     rax, [rbp+var_2C]
0x140016aec  mov     [rsp+70h+cchReferencedDomainName], rax; cchReferencedDomainName
0x140016af1  mov     [rsp+70h+ReferencedDomainName], 0; ReferencedDomainName
0x140016afa  lea     r9, [rbp+cbSid]; cbSid
0x140016afe  xor     r8d, r8d; Sid
0x140016b01  xor     ecx, ecx; lpSystemName
0x140016b03  call    cs:__imp_LookupAccountNameW
0x140016b09  call    cs:__imp_GetLastError
0x140016b0f  cmp     eax, 7Ah ; 'z'
0x140016b12  jz      short loc_140016B2C
0x140016b14  mov     edx, eax
0x140016b16  lea     rcx, aGetstringsidfr; "GetStringSIDFromUsername - ::LookupAcco"...
0x140016b1d  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140016b22  mov     ebx, 8000FFFFh
0x140016b27  jmp     loc_140016C5A
0x140016b2c  mov     eax, [rbp+cbSid]
0x140016b2f  test    eax, eax
0x140016b31  jnz     short loc_140016B41
0x140016b33  lea     rcx, aGetstringsidfr_1; "GetStringSIDFromUsername() - Username d"...
0x140016b3a  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140016b3f  jmp     short loc_140016B22
0x140016b41  xor     r14d, r14d
0x140016b44  mov     rbx, rax
0x140016b47  call    cs:__imp_GetProcessHeap
0x140016b4d  mov     r8, rbx; dwBytes
0x140016b50  lea     edx, [r14+8]; dwFlags
0x140016b54  mov     rcx, rax; hHeap
0x140016b57  call    cs:__imp_HeapAlloc
0x140016b5d  mov     rsi, rax
0x140016b60  mov     eax, [rbp+var_2C]
0x140016b63  test    eax, eax
0x140016b65  jz      short loc_140016B85
0x140016b67  mov     ebx, eax
0x140016b69  add     rbx, rbx
0x140016b6c  call    cs:__imp_GetProcessHeap
0x140016b72  mov     r8, rbx; dwBytes
0x140016b75  lea     edx, [r14+8]; dwFlags
0x140016b79  mov     rcx, rax; hHeap
0x140016b7c  call    cs:__imp_HeapAlloc
0x140016b82  mov     r14, rax
0x140016b85  cmp     qword ptr [rdi+18h], 8
0x140016b8a  jb      short loc_140016B91
0x140016b8c  mov     rdx, [rdi]
0x140016b8f  jmp     short loc_140016B94
0x140016b91  mov     rdx, rdi; lpAccountName
0x140016b94  lea     rax, [rbp+var_28]
0x140016b98  mov     [rsp+70h+peUse], rax; peUse
0x140016b9d  lea     rax, [rbp+var_2C]
0x140016ba1  mov     [rsp+70h+cchReferencedDomainName], rax; cchReferencedDomainName
0x140016ba6  mov     [rsp+70h+ReferencedDomainName], r14; ReferencedDomainName
0x140016bab  lea     r9, [rbp+cbSid]; cbSid
0x140016baf  mov     r8, rsi; Sid
0x140016bb2  xor     ecx, ecx; lpSystemName
0x140016bb4  call    cs:__imp_LookupAccountNameW
0x140016bba  test    eax, eax
0x140016bbc  jz      short loc_140016C0E
0x140016bbe  cmp     [rbp+cbSid], 0
0x140016bc2  jz      short loc_140016C0E
0x140016bc4  xor     ebx, ebx
0x140016bc6  lea     rdx, [rbp+StringSid]; StringSid
0x140016bca  mov     rcx, rsi; Sid
0x140016bcd  call    cs:__imp_ConvertSidToStringSidW
0x140016bd3  test    eax, eax
0x140016bd5  jnz     short loc_140016BEB
0x140016bd7  call    cs:__imp_GetLastError
0x140016bdd  mov     edx, eax
0x140016bdf  lea     rcx, aGetstringsidfr_0; "GetStringSIDFromUsername - ::ConvertSid"...
0x140016be6  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140016beb  mov     rcx, [rbp+StringSid]
0x140016bef  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x140016bf4  mov     r8, rax
0x140016bf7  mov     rdx, rcx
0x140016bfa  mov     rcx, r15
0x140016bfd  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x140016c02  mov     rcx, [rbp+StringSid]; hMem
0x140016c06  call    cs:__imp_LocalFree
0x140016c0c  jmp     short loc_140016C24
0x140016c0e  mov     edx, 7Ah ; 'z'
0x140016c13  lea     rcx, aGetstringsidfr; "GetStringSIDFromUsername - ::LookupAcco"...
0x140016c1a  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140016c1f  mov     ebx, 8000FFFFh
0x140016c24  test    rsi, rsi
0x140016c27  jz      short loc_140016C3D
0x140016c29  call    cs:__imp_GetProcessHeap
0x140016c2f  mov     rcx, rax; hHeap
0x140016c32  mov     r8, rsi; lpMem
0x140016c35  xor     edx, edx; dwFlags
0x140016c37  call    cs:__imp_HeapFree
0x140016c3d  test    r14, r14
0x140016c40  jz      short loc_140016C56
0x140016c42  call    cs:__imp_GetProcessHeap
0x140016c48  mov     rcx, rax; hHeap
0x140016c4b  mov     r8, r14; lpMem
0x140016c4e  xor     edx, edx; dwFlags
0x140016c50  call    cs:__imp_HeapFree
0x140016c56  test    ebx, ebx
0x140016c58  jns     short loc_140016C69
0x140016c5a  mov     edx, ebx
0x140016c5c  lea     rcx, aGetstringsidfr_2; "GetStringSIDFromUsername() failed hr=0x"...
0x140016c63  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140016c68  nop
0x140016c69  xor     r8d, r8d
0x140016c6c  mov     dl, 1
0x140016c6e  mov     rcx, rdi
0x140016c71  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140016c76  mov     eax, ebx
0x140016c78  mov     rcx, [rbp+var_10]
0x140016c7c  xor     rcx, rsp; StackCookie
0x140016c7f  call    __security_check_cookie
0x140016c84  mov     rbx, [rsp+70h+arg_10]
0x140016c8c  add     rsp, 70h
0x140016c90  pop     r15
0x140016c92  pop     r14
0x140016c94  pop     rdi
0x140016c95  pop     rsi
0x140016c96  pop     rbp
0x140016c97  retn
```
