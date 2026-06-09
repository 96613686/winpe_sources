# SecUtil::AccountNameFromWellKnownType(WELL_KNOWN_SID_TYPE,wchar_t * *)

- ea: `0x14002adc4`
- end: `0x14002b09d`
- name: `?AccountNameFromWellKnownType@SecUtil@@YAJW4WELL_KNOWN_SID_TYPE@@PEAPEA_W@Z`
- size: `729`
- prototype: `__int64 __fastcall(SecUtil *this, unsigned __int16 **, wchar_t **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002753c`

## callees

- `0x1400034b0`
- `0x14000a684`
- `0x14001ba58`
- `0x14001e440`
- `0x14002ada0`
- `0x14002adc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002adff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ae7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002aee7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002afd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002adff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ae7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002aee7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002afd0`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14002adf5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14002ae70`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14002adf5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14002ae70`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x14002aedd`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x14002afc6`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x14002aedd`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x14002afc6`

## string_xrefs

- `0x14002ae2a`: `"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx"`
- `0x14002aea0`: `"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx"`
- `0x14002aff6`: `"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx"`
- `0x14002ae1e`: `[UtilSecurity] CreateWellKnownSid() failed with error 0x%08x.`
- `0x14002ae91`: `[UtilSecurity] CreateWellKnownSid() failed with error 0x%08x.`
- `0x14002af03`: `[UtilSecurity] LookupAccountSid() failed with error 0x%08x.`
- `0x14002afea`: `[UtilSecurity] LookupAccountSid() failed with error 0x%08x.`

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
    TPointer<char>::~TPointer<char>(v25);
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
  TPointer<char>::~TPointer<char>(v25);
  return 2147942414LL;
}

```

## disassembly

```asm
0x14002adc4  mov     [rsp-38h+arg_8], rbx
0x14002adc9  mov     [rsp-38h+arg_0], ecx
0x14002adcd  push    rbp
0x14002adce  push    rsi
0x14002adcf  push    rdi
0x14002add0  push    r12
0x14002add2  push    r13
0x14002add4  push    r14
0x14002add6  push    r15
0x14002add8  mov     rbp, rsp
0x14002addb  sub     rsp, 70h
0x14002addf  xor     edi, edi
0x14002ade1  lea     r9, [rbp+cbSid]; cbSid
0x14002ade5  mov     r15, rdx
0x14002ade8  mov     [rbp+cbSid], edi
0x14002adeb  xor     r8d, r8d; pSid
0x14002adee  xor     edx, edx; DomainSid
0x14002adf0  lea     esi, [rdi+11h]
0x14002adf3  mov     ecx, esi; WellKnownSidType
0x14002adf5  call    cs:__imp_CreateWellKnownSid
0x14002adfb  test    eax, eax
0x14002adfd  jnz     short loc_14002AE3D
0x14002adff  call    cs:__imp_GetLastError
0x14002ae05  cmp     eax, 7Ah ; 'z'
0x14002ae08  jz      short loc_14002AE3D
0x14002ae0a  test    eax, eax
0x14002ae0c  jg      short loc_14002AE12
0x14002ae0e  mov     ebx, eax
0x14002ae10  jmp     short loc_14002AE1B
0x14002ae12  movzx   ebx, ax
0x14002ae15  or      ebx, 80070000h
0x14002ae1b  mov     r9d, eax; wchar_t *
0x14002ae1e  lea     r8, aUtilsecurityCr; "[UtilSecurity] CreateWellKnownSid() fai"...
0x14002ae25  mov     edx, 637h; wchar_t *
0x14002ae2a  lea     rcx, aOnecoreuapBase_8; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x14002ae31  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x14002ae36  mov     eax, ebx
0x14002ae38  jmp     loc_14002B085
0x14002ae3d  mov     ecx, [rbp+cbSid]; unsigned __int64
0x14002ae40  lea     r12, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14002ae47  mov     rdx, r12; struct std::nothrow_t *
0x14002ae4a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14002ae4f  mov     [rbp+var_10], rax
0x14002ae53  mov     rbx, rax
0x14002ae56  test    rax, rax
0x14002ae59  jnz     short loc_14002AE65
0x14002ae5b  mov     ebx, 8007000Eh
0x14002ae60  jmp     loc_14002B042
0x14002ae65  lea     r9, [rbp+cbSid]; cbSid
0x14002ae69  mov     r8, rbx; pSid
0x14002ae6c  xor     edx, edx; DomainSid
0x14002ae6e  mov     ecx, esi; WellKnownSidType
0x14002ae70  call    cs:__imp_CreateWellKnownSid
0x14002ae76  test    eax, eax
0x14002ae78  jnz     short loc_14002AEB1
0x14002ae7a  call    cs:__imp_GetLastError
0x14002ae80  test    eax, eax
0x14002ae82  jg      short loc_14002AE88
0x14002ae84  mov     ebx, eax
0x14002ae86  jmp     short loc_14002AE91
0x14002ae88  movzx   ebx, ax
0x14002ae8b  or      ebx, 80070000h
0x14002ae91  lea     r8, aUtilsecurityCr; "[UtilSecurity] CreateWellKnownSid() fai"...
0x14002ae98  mov     edx, 649h; wchar_t *
0x14002ae9d  mov     r9d, eax; wchar_t *
0x14002aea0  lea     rcx, aOnecoreuapBase_8; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x14002aea7  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x14002aeac  jmp     loc_14002B042
0x14002aeb1  lea     rax, [rbp+var_30]
0x14002aeb5  mov     [rbp+cchName], edi
0x14002aeb8  mov     [rsp+70h+peUse], rax; peUse
0x14002aebd  lea     r9, [rbp+cchName]; cchName
0x14002aec1  lea     rax, [rbp+arg_0]
0x14002aec5  mov     [rbp+arg_0], edi
0x14002aec8  mov     [rsp+70h+cchReferencedDomainName], rax; cchReferencedDomainName
0x14002aecd  xor     r8d, r8d; Name
0x14002aed0  mov     rdx, rbx; Sid
0x14002aed3  mov     [rsp+70h+ReferencedDomainName], rdi; ReferencedDomainName
0x14002aed8  xor     ecx, ecx; lpSystemName
0x14002aeda  mov     [rbp+var_30], edi
0x14002aedd  call    cs:__imp_LookupAccountSidW
0x14002aee3  test    eax, eax
0x14002aee5  jnz     short loc_14002AF11
0x14002aee7  call    cs:__imp_GetLastError
0x14002aeed  cmp     eax, 7Ah ; 'z'
0x14002aef0  jz      short loc_14002AF11
0x14002aef2  test    eax, eax
0x14002aef4  jg      short loc_14002AEFA
0x14002aef6  mov     ebx, eax
0x14002aef8  jmp     short loc_14002AF03
0x14002aefa  movzx   ebx, ax
0x14002aefd  or      ebx, 80070000h
0x14002af03  lea     r8, aUtilsecurityLo; "[UtilSecurity] LookupAccountSid() faile"...
0x14002af0a  mov     edx, 658h
0x14002af0f  jmp     short loc_14002AE9D
0x14002af11  mov     ecx, [rbp+cchName]
0x14002af14  mov     edi, 2
0x14002af19  inc     ecx
0x14002af1b  mov     eax, edi
0x14002af1d  mul     rcx
0x14002af20  lea     r13, [rdi-3]
0x14002af24  mov     rdx, r12; struct std::nothrow_t *
0x14002af27  cmovb   rax, r13
0x14002af2b  mov     rcx, rax; unsigned __int64
0x14002af2e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14002af33  mov     ecx, [rbp+arg_0]
0x14002af36  mov     r14, rax
0x14002af39  mov     [rbp+var_18], rax
0x14002af3d  inc     ecx
0x14002af3f  mov     eax, edi
0x14002af41  mul     rcx
0x14002af44  mov     rdx, r12; struct std::nothrow_t *
0x14002af47  cmovb   rax, r13
0x14002af4b  mov     rcx, rax; unsigned __int64
0x14002af4e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14002af53  mov     ecx, [rbp+arg_0]
0x14002af56  mov     rsi, rax
0x14002af59  mov     r12d, [rbp+cchName]
0x14002af5d  add     ecx, edi
0x14002af5f  mov     [rbp+var_20], rax
0x14002af63  add     r12d, ecx
0x14002af66  mov     eax, edi
0x14002af68  mul     r12
0x14002af6b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002af72  cmovb   rax, r13
0x14002af76  mov     rcx, rax; unsigned __int64
0x14002af79  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14002af7e  xor     r13d, r13d
0x14002af81  mov     [rbp+var_28], rax
0x14002af85  mov     rdi, rax
0x14002af88  test    r14, r14
0x14002af8b  jz      loc_14002B059
0x14002af91  test    rsi, rsi
0x14002af94  jz      loc_14002B059
0x14002af9a  test    rax, rax
0x14002af9d  jz      loc_14002B059
0x14002afa3  lea     rax, [rbp+var_30]
0x14002afa7  mov     r8, r14; Name
0x14002afaa  mov     [rsp+70h+peUse], rax; peUse
0x14002afaf  lea     r9, [rbp+cchName]; cchName
0x14002afb3  lea     rax, [rbp+arg_0]
0x14002afb7  mov     rdx, rbx; Sid
0x14002afba  mov     [rsp+70h+cchReferencedDomainName], rax; cchReferencedDomainName
0x14002afbf  xor     ecx, ecx; lpSystemName
0x14002afc1  mov     [rsp+70h+ReferencedDomainName], rsi; ReferencedDomainName
0x14002afc6  call    cs:__imp_LookupAccountSidW
0x14002afcc  test    eax, eax
0x14002afce  jnz     short loc_14002B004
0x14002afd0  call    cs:__imp_GetLastError
0x14002afd6  test    eax, eax
0x14002afd8  jg      short loc_14002AFDE
0x14002afda  mov     ebx, eax
0x14002afdc  jmp     short loc_14002AFE7
0x14002afde  movzx   ebx, ax
0x14002afe1  or      ebx, 80070000h
0x14002afe7  mov     r9d, eax; wchar_t *
0x14002afea  lea     r8, aUtilsecurityLo; "[UtilSecurity] LookupAccountSid() faile"...
0x14002aff1  mov     edx, 66Dh; wchar_t *
0x14002aff6  lea     rcx, aOnecoreuapBase_8; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x14002affd  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x14002b002  jmp     short loc_14002B024
0x14002b004  mov     r9, rsi
0x14002b007  mov     [rsp+70h+ReferencedDomainName], r14
0x14002b00c  lea     r8, aLsLs; "%lS\\%lS"
0x14002b013  mov     rdx, r12; unsigned __int64
0x14002b016  mov     rcx, rdi; unsigned __int16 *
0x14002b019  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002b01e  mov     ebx, eax
0x14002b020  test    eax, eax
0x14002b022  jns     short loc_14002B050
0x14002b024  mov     [r15], r13
0x14002b027  lea     rcx, [rbp+var_28]
0x14002b02b  call    ??1?$TPointer@_W@@QEAA@XZ; TPointer<wchar_t>::~TPointer<wchar_t>(void)
0x14002b030  lea     rcx, [rbp+var_20]
0x14002b034  call    ??1?$TPointer@_W@@QEAA@XZ; TPointer<wchar_t>::~TPointer<wchar_t>(void)
0x14002b039  lea     rcx, [rbp+var_18]
0x14002b03d  call    ??1?$TPointer@_W@@QEAA@XZ; TPointer<wchar_t>::~TPointer<wchar_t>(void)
0x14002b042  lea     rcx, [rbp+var_10]
0x14002b046  call    ??1?$TPointer@D@@QEAA@XZ; TPointer<char>::~TPointer<char>(void)
0x14002b04b  jmp     loc_14002AE36
0x14002b050  mov     [rbp+var_28], r13
0x14002b054  mov     [r15], rdi
0x14002b057  jmp     short loc_14002B027
0x14002b059  lea     rcx, [rbp+var_28]
0x14002b05d  mov     [r15], r13
0x14002b060  call    ??1?$TPointer@_W@@QEAA@XZ; TPointer<wchar_t>::~TPointer<wchar_t>(void)
0x14002b065  lea     rcx, [rbp+var_20]
0x14002b069  call    ??1?$TPointer@_W@@QEAA@XZ; TPointer<wchar_t>::~TPointer<wchar_t>(void)
0x14002b06e  lea     rcx, [rbp+var_18]
0x14002b072  call    ??1?$TPointer@_W@@QEAA@XZ; TPointer<wchar_t>::~TPointer<wchar_t>(void)
0x14002b077  lea     rcx, [rbp+var_10]
0x14002b07b  call    ??1?$TPointer@D@@QEAA@XZ; TPointer<char>::~TPointer<char>(void)
0x14002b080  mov     eax, 8007000Eh
0x14002b085  mov     rbx, [rsp+70h+arg_8]
0x14002b08d  add     rsp, 70h
0x14002b091  pop     r15
0x14002b093  pop     r14
0x14002b095  pop     r13
0x14002b097  pop     r12
0x14002b099  pop     rdi
0x14002b09a  pop     rsi
0x14002b09b  pop     rbp
0x14002b09c  retn
```
