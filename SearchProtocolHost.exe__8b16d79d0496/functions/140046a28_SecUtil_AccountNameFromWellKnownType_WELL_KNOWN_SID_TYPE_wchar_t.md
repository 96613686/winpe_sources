# SecUtil::AccountNameFromWellKnownType(WELL_KNOWN_SID_TYPE,wchar_t * *)

- ea: `0x140046a28`
- end: `0x140046d01`
- name: `?AccountNameFromWellKnownType@SecUtil@@YAJW4WELL_KNOWN_SID_TYPE@@PEAPEA_W@Z`
- size: `729`
- prototype: `__int64 __fastcall(SecUtil *__hidden this, enum WELL_KNOWN_SID_TYPE, wchar_t **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003a8e8`

## callees

- `0x140005924`
- `0x14000ea6c`
- `0x14000eb54`
- `0x140015958`
- `0x140029a8c`
- `0x140046a28`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140046a59`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140046ad4`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140046a59`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140046ad4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046a63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046ade`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046b4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046c34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046a63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046ade`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046b4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046c34`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x140046b41`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x140046c2a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x140046b41`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x140046c2a`

## string_xrefs

- `0x140046a8e`: `"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx"`
- `0x140046b04`: `"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx"`
- `0x140046c5a`: `"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx"`
- `0x140046a82`: `[UtilSecurity] CreateWellKnownSid() failed with error 0x%08x.`
- `0x140046af5`: `[UtilSecurity] CreateWellKnownSid() failed with error 0x%08x.`
- `0x140046b67`: `[UtilSecurity] LookupAccountSid() failed with error 0x%08x.`
- `0x140046c4e`: `[UtilSecurity] LookupAccountSid() failed with error 0x%08x.`

## pseudocode

```c
__int64 __fastcall SecUtil::AccountNameFromWellKnownType(SecUtil *this, unsigned __int16 **a2, wchar_t **a3)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  void *v7; // rax
  void *v8; // rbx
  signed int v9; // eax
  const char *v10; // r8
  __int64 v11; // rdx
  unsigned __int64 v12; // rax
  WCHAR *v13; // r14
  unsigned __int64 v14; // rax
  WCHAR *ReferencedDomainName; // rsi
  unsigned __int64 v16; // r12
  unsigned __int64 v17; // rax
  unsigned __int16 *v18; // rax
  unsigned __int16 *v19; // rdi
  signed int v20; // eax
  enum _SID_NAME_USE peUse; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int16 *v22; // [rsp+48h] [rbp-28h] BYREF
  WCHAR *v23; // [rsp+50h] [rbp-20h] BYREF
  WCHAR *v24; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v25[2]; // [rsp+60h] [rbp-10h] BYREF
  DWORD cchReferencedDomainName; // [rsp+B0h] [rbp+40h] BYREF
  DWORD cchName; // [rsp+C0h] [rbp+50h] BYREF
  DWORD cbSid; // [rsp+C8h] [rbp+58h] BYREF

  cchReferencedDomainName = (unsigned int)this;
  cbSid = 0;
  if ( !CreateWellKnownSid(WinAuthenticatedUserSid, 0, 0, &cbSid) )
  {
    LastError = GetLastError();
    if ( LastError != 122 )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      else
        v5 = LastError;
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\secutil\\\\secutil.cxx\"",
        (const wchar_t *)0x637,
        (unsigned int)L"[UtilSecurity] CreateWellKnownSid() failed with error 0x%08x.",
        (const wchar_t *)(unsigned int)LastError);
      return v5;
    }
  }
  v7 = operator new[](cbSid, (const struct std::nothrow_t *)&std::nothrow);
  v25[0] = v7;
  v8 = v7;
  if ( !v7 )
  {
    v5 = -2147024882;
LABEL_39:
    TPointer<unsigned char>::~TPointer<unsigned char>(v25);
    return v5;
  }
  if ( !CreateWellKnownSid(WinAuthenticatedUserSid, 0, v7, &cbSid) )
  {
    v9 = GetLastError();
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    else
      v5 = v9;
    v10 = L"[UtilSecurity] CreateWellKnownSid() failed with error 0x%08x.";
    v11 = 1609;
LABEL_15:
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\secutil\\\\secutil.cxx\"",
      (const wchar_t *)v11,
      (unsigned int)v10,
      (const wchar_t *)(unsigned int)v9);
    goto LABEL_39;
  }
  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  if ( !LookupAccountSidW(0, v8, 0, &cchName, 0, &cchReferencedDomainName, &peUse) )
  {
    v9 = GetLastError();
    if ( v9 != 122 )
    {
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
      else
        v5 = v9;
      v10 = L"[UtilSecurity] LookupAccountSid() failed with error 0x%08x.";
      v11 = 1624;
      goto LABEL_15;
    }
  }
  v12 = 2LL * (cchName + 1);
  if ( !is_mul_ok(cchName + 1, 2u) )
    v12 = -1;
  v13 = (WCHAR *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
  v24 = v13;
  v14 = 2LL * (cchReferencedDomainName + 1);
  if ( !is_mul_ok(cchReferencedDomainName + 1, 2u) )
    v14 = -1;
  ReferencedDomainName = (WCHAR *)operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
  v23 = ReferencedDomainName;
  v16 = cchReferencedDomainName + 2 + cchName;
  v17 = 2 * v16;
  if ( !is_mul_ok(v16, 2u) )
    v17 = -1;
  v18 = (unsigned __int16 *)operator new[](v17, (const struct std::nothrow_t *)&std::nothrow);
  v22 = v18;
  v19 = v18;
  if ( v13 && ReferencedDomainName && v18 )
  {
    if ( LookupAccountSidW(0, v8, v13, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
    {
      v5 = StringCchPrintfW(v19, v16, L"%lS\\%lS", ReferencedDomainName, v13);
      if ( (v5 & 0x80000000) == 0 )
      {
        v22 = 0;
        *a2 = v19;
        goto LABEL_38;
      }
    }
    else
    {
      v20 = GetLastError();
      if ( v20 > 0 )
        v5 = (unsigned __int16)v20 | 0x80070000;
      else
        v5 = v20;
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\secutil\\\\secutil.cxx\"",
        (const wchar_t *)0x66D,
        (unsigned int)L"[UtilSecurity] LookupAccountSid() failed with error 0x%08x.",
        (const wchar_t *)(unsigned int)v20);
    }
    *a2 = 0;
LABEL_38:
    TPointer<wchar_t>::~TPointer<wchar_t>(&v22);
    TPointer<wchar_t>::~TPointer<wchar_t>(&v23);
    TPointer<wchar_t>::~TPointer<wchar_t>(&v24);
    goto LABEL_39;
  }
  *a2 = 0;
  TPointer<wchar_t>::~TPointer<wchar_t>(&v22);
  TPointer<wchar_t>::~TPointer<wchar_t>(&v23);
  TPointer<wchar_t>::~TPointer<wchar_t>(&v24);
  TPointer<unsigned char>::~TPointer<unsigned char>(v25);
  return 2147942414LL;
}

```

## disassembly

```asm
0x140046a28  mov     [rsp-38h+arg_8], rbx
0x140046a2d  mov     [rsp-38h+arg_0], ecx
0x140046a31  push    rbp
0x140046a32  push    rsi
0x140046a33  push    rdi
0x140046a34  push    r12
0x140046a36  push    r13
0x140046a38  push    r14
0x140046a3a  push    r15
0x140046a3c  mov     rbp, rsp
0x140046a3f  sub     rsp, 70h
0x140046a43  xor     edi, edi
0x140046a45  lea     r9, [rbp+cbSid]; cbSid
0x140046a49  mov     r15, rdx
0x140046a4c  mov     [rbp+cbSid], edi
0x140046a4f  xor     r8d, r8d; pSid
0x140046a52  xor     edx, edx; DomainSid
0x140046a54  lea     esi, [rdi+11h]
0x140046a57  mov     ecx, esi; WellKnownSidType
0x140046a59  call    cs:__imp_CreateWellKnownSid
0x140046a5f  test    eax, eax
0x140046a61  jnz     short loc_140046AA1
0x140046a63  call    cs:__imp_GetLastError
0x140046a69  cmp     eax, 7Ah ; 'z'
0x140046a6c  jz      short loc_140046AA1
0x140046a6e  test    eax, eax
0x140046a70  jg      short loc_140046A76
0x140046a72  mov     ebx, eax
0x140046a74  jmp     short loc_140046A7F
0x140046a76  movzx   ebx, ax
0x140046a79  or      ebx, 80070000h
0x140046a7f  mov     r9d, eax; wchar_t *
0x140046a82  lea     r8, aUtilsecurityCr; "[UtilSecurity] CreateWellKnownSid() fai"...
0x140046a89  mov     edx, 637h; wchar_t *
0x140046a8e  lea     rcx, aOnecoreuapBase_11; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x140046a95  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x140046a9a  mov     eax, ebx
0x140046a9c  jmp     loc_140046CE9
0x140046aa1  mov     ecx, [rbp+cbSid]; unsigned __int64
0x140046aa4  lea     r12, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140046aab  mov     rdx, r12; struct std::nothrow_t *
0x140046aae  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140046ab3  mov     [rbp+var_10], rax
0x140046ab7  mov     rbx, rax
0x140046aba  test    rax, rax
0x140046abd  jnz     short loc_140046AC9
0x140046abf  mov     ebx, 8007000Eh
0x140046ac4  jmp     loc_140046CA6
0x140046ac9  lea     r9, [rbp+cbSid]; cbSid
0x140046acd  mov     r8, rbx; pSid
0x140046ad0  xor     edx, edx; DomainSid
0x140046ad2  mov     ecx, esi; WellKnownSidType
0x140046ad4  call    cs:__imp_CreateWellKnownSid
0x140046ada  test    eax, eax
0x140046adc  jnz     short loc_140046B15
0x140046ade  call    cs:__imp_GetLastError
0x140046ae4  test    eax, eax
0x140046ae6  jg      short loc_140046AEC
0x140046ae8  mov     ebx, eax
0x140046aea  jmp     short loc_140046AF5
0x140046aec  movzx   ebx, ax
0x140046aef  or      ebx, 80070000h
0x140046af5  lea     r8, aUtilsecurityCr; "[UtilSecurity] CreateWellKnownSid() fai"...
0x140046afc  mov     edx, 649h; wchar_t *
0x140046b01  mov     r9d, eax; wchar_t *
0x140046b04  lea     rcx, aOnecoreuapBase_11; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x140046b0b  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x140046b10  jmp     loc_140046CA6
0x140046b15  lea     rax, [rbp+var_30]
0x140046b19  mov     [rbp+cchName], edi
0x140046b1c  mov     [rsp+70h+peUse], rax; peUse
0x140046b21  lea     r9, [rbp+cchName]; cchName
0x140046b25  lea     rax, [rbp+arg_0]
0x140046b29  mov     [rbp+arg_0], edi
0x140046b2c  mov     [rsp+70h+cchReferencedDomainName], rax; cchReferencedDomainName
0x140046b31  xor     r8d, r8d; Name
0x140046b34  mov     rdx, rbx; Sid
0x140046b37  mov     [rsp+70h+ReferencedDomainName], rdi; ReferencedDomainName
0x140046b3c  xor     ecx, ecx; lpSystemName
0x140046b3e  mov     [rbp+var_30], edi
0x140046b41  call    cs:__imp_LookupAccountSidW
0x140046b47  test    eax, eax
0x140046b49  jnz     short loc_140046B75
0x140046b4b  call    cs:__imp_GetLastError
0x140046b51  cmp     eax, 7Ah ; 'z'
0x140046b54  jz      short loc_140046B75
0x140046b56  test    eax, eax
0x140046b58  jg      short loc_140046B5E
0x140046b5a  mov     ebx, eax
0x140046b5c  jmp     short loc_140046B67
0x140046b5e  movzx   ebx, ax
0x140046b61  or      ebx, 80070000h
0x140046b67  lea     r8, aUtilsecurityLo; "[UtilSecurity] LookupAccountSid() faile"...
0x140046b6e  mov     edx, 658h
0x140046b73  jmp     short loc_140046B01
0x140046b75  mov     ecx, [rbp+cchName]
0x140046b78  mov     edi, 2
0x140046b7d  inc     ecx
0x140046b7f  mov     eax, edi
0x140046b81  mul     rcx
0x140046b84  lea     r13, [rdi-3]
0x140046b88  mov     rdx, r12; struct std::nothrow_t *
0x140046b8b  cmovb   rax, r13
0x140046b8f  mov     rcx, rax; unsigned __int64
0x140046b92  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140046b97  mov     ecx, [rbp+arg_0]
0x140046b9a  mov     r14, rax
0x140046b9d  mov     [rbp+var_18], rax
0x140046ba1  inc     ecx
0x140046ba3  mov     eax, edi
0x140046ba5  mul     rcx
0x140046ba8  mov     rdx, r12; struct std::nothrow_t *
0x140046bab  cmovb   rax, r13
0x140046baf  mov     rcx, rax; unsigned __int64
0x140046bb2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140046bb7  mov     ecx, [rbp+arg_0]
0x140046bba  mov     rsi, rax
0x140046bbd  mov     r12d, [rbp+cchName]
0x140046bc1  add     ecx, edi
0x140046bc3  mov     [rbp+var_20], rax
0x140046bc7  add     r12d, ecx
0x140046bca  mov     eax, edi
0x140046bcc  mul     r12
0x140046bcf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140046bd6  cmovb   rax, r13
0x140046bda  mov     rcx, rax; unsigned __int64
0x140046bdd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140046be2  xor     r13d, r13d
0x140046be5  mov     [rbp+var_28], rax
0x140046be9  mov     rdi, rax
0x140046bec  test    r14, r14
0x140046bef  jz      loc_140046CBD
0x140046bf5  test    rsi, rsi
0x140046bf8  jz      loc_140046CBD
0x140046bfe  test    rax, rax
0x140046c01  jz      loc_140046CBD
0x140046c07  lea     rax, [rbp+var_30]
0x140046c0b  mov     r8, r14; Name
0x140046c0e  mov     [rsp+70h+peUse], rax; peUse
0x140046c13  lea     r9, [rbp+cchName]; cchName
0x140046c17  lea     rax, [rbp+arg_0]
0x140046c1b  mov     rdx, rbx; Sid
0x140046c1e  mov     [rsp+70h+cchReferencedDomainName], rax; cchReferencedDomainName
0x140046c23  xor     ecx, ecx; lpSystemName
0x140046c25  mov     [rsp+70h+ReferencedDomainName], rsi; ReferencedDomainName
0x140046c2a  call    cs:__imp_LookupAccountSidW
0x140046c30  test    eax, eax
0x140046c32  jnz     short loc_140046C68
0x140046c34  call    cs:__imp_GetLastError
0x140046c3a  test    eax, eax
0x140046c3c  jg      short loc_140046C42
0x140046c3e  mov     ebx, eax
0x140046c40  jmp     short loc_140046C4B
0x140046c42  movzx   ebx, ax
0x140046c45  or      ebx, 80070000h
0x140046c4b  mov     r9d, eax; wchar_t *
0x140046c4e  lea     r8, aUtilsecurityLo; "[UtilSecurity] LookupAccountSid() faile"...
0x140046c55  mov     edx, 66Dh; wchar_t *
0x140046c5a  lea     rcx, aOnecoreuapBase_11; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x140046c61  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x140046c66  jmp     short loc_140046C88
0x140046c68  mov     r9, rsi
0x140046c6b  mov     [rsp+70h+ReferencedDomainName], r14
0x140046c70  lea     r8, aLsLs; "%lS\\%lS"
0x140046c77  mov     rdx, r12; unsigned __int64
0x140046c7a  mov     rcx, rdi; unsigned __int16 *
0x140046c7d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140046c82  mov     ebx, eax
0x140046c84  test    eax, eax
0x140046c86  jns     short loc_140046CB4
0x140046c88  mov     [r15], r13
0x140046c8b  lea     rcx, [rbp+var_28]
0x140046c8f  call    ??1?$TPointer@_W@@QEAA@XZ; TPointer<wchar_t>::~TPointer<wchar_t>(void)
0x140046c94  lea     rcx, [rbp+var_20]
0x140046c98  call    ??1?$TPointer@_W@@QEAA@XZ; TPointer<wchar_t>::~TPointer<wchar_t>(void)
0x140046c9d  lea     rcx, [rbp+var_18]
0x140046ca1  call    ??1?$TPointer@_W@@QEAA@XZ; TPointer<wchar_t>::~TPointer<wchar_t>(void)
0x140046ca6  lea     rcx, [rbp+var_10]
0x140046caa  call    ??1?$TPointer@E@@QEAA@XZ; TPointer<uchar>::~TPointer<uchar>(void)
0x140046caf  jmp     loc_140046A9A
0x140046cb4  mov     [rbp+var_28], r13
0x140046cb8  mov     [r15], rdi
0x140046cbb  jmp     short loc_140046C8B
0x140046cbd  lea     rcx, [rbp+var_28]
0x140046cc1  mov     [r15], r13
0x140046cc4  call    ??1?$TPointer@_W@@QEAA@XZ; TPointer<wchar_t>::~TPointer<wchar_t>(void)
0x140046cc9  lea     rcx, [rbp+var_20]
0x140046ccd  call    ??1?$TPointer@_W@@QEAA@XZ; TPointer<wchar_t>::~TPointer<wchar_t>(void)
0x140046cd2  lea     rcx, [rbp+var_18]
0x140046cd6  call    ??1?$TPointer@_W@@QEAA@XZ; TPointer<wchar_t>::~TPointer<wchar_t>(void)
0x140046cdb  lea     rcx, [rbp+var_10]
0x140046cdf  call    ??1?$TPointer@E@@QEAA@XZ; TPointer<uchar>::~TPointer<uchar>(void)
0x140046ce4  mov     eax, 8007000Eh
0x140046ce9  mov     rbx, [rsp+70h+arg_8]
0x140046cf1  add     rsp, 70h
0x140046cf5  pop     r15
0x140046cf7  pop     r14
0x140046cf9  pop     r13
0x140046cfb  pop     r12
0x140046cfd  pop     rdi
0x140046cfe  pop     rsi
0x140046cff  pop     rbp
0x140046d00  retn
```
