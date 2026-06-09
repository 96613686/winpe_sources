# CreateWmsSid(WmsSid *,_SID *,unsigned __int64)

- ea: `0x140066310`
- end: `0x140066890`
- name: `?CreateWmsSid@@YAJPEAUWmsSid@@PEAU_SID@@_K@Z`
- size: `1408`
- prototype: `__int64 __fastcall(struct WmsSid *, struct _SID *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400657e8`
- `0x140065c64`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140066310`
- `0x1400673ac`
- `0x14006b010`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!LookupAccountNameW` at `0x140066710`
- `ADVAPI32!LookupAccountNameW` at `0x140066710`
- `ADVAPI32!CreateWellKnownSid` at `0x1400667a2`
- `ADVAPI32!CreateWellKnownSid` at `0x1400667a2`
- `ADVAPI32!OpenProcessToken` at `0x1400663a7`
- `ADVAPI32!OpenProcessToken` at `0x1400663a7`
- `ADVAPI32!CopySid` at `0x140066523`
- `ADVAPI32!CopySid` at `0x1400665d3`
- `ADVAPI32!CopySid` at `0x140066523`
- `ADVAPI32!CopySid` at `0x1400665d3`
- `KERNEL32!CloseHandle` at `0x14006684c`
- `KERNEL32!CloseHandle` at `0x14006684c`
- `KERNEL32!LocalFree` at `0x140066855`
- `KERNEL32!LocalFree` at `0x14006685e`
- `KERNEL32!LocalFree` at `0x140066855`
- `KERNEL32!LocalFree` at `0x14006685e`
- `KERNEL32!GetLastError` at `0x1400663b5`
- `KERNEL32!GetLastError` at `0x140066531`
- `KERNEL32!GetLastError` at `0x1400665e1`
- `KERNEL32!GetLastError` at `0x14006671e`
- `KERNEL32!GetLastError` at `0x1400667b0`
- `KERNEL32!GetLastError` at `0x1400663b5`
- `KERNEL32!GetLastError` at `0x140066531`
- `KERNEL32!GetLastError` at `0x1400665e1`
- `KERNEL32!GetLastError` at `0x14006671e`
- `KERNEL32!GetLastError` at `0x1400667b0`
- `KERNEL32!IsDebuggerPresent` at `0x14006640c`
- `KERNEL32!IsDebuggerPresent` at `0x1400664c5`
- `KERNEL32!IsDebuggerPresent` at `0x140066588`
- `KERNEL32!IsDebuggerPresent` at `0x140066638`
- `KERNEL32!IsDebuggerPresent` at `0x1400666a7`
- `KERNEL32!IsDebuggerPresent` at `0x140066775`
- `KERNEL32!IsDebuggerPresent` at `0x140066807`
- `KERNEL32!IsDebuggerPresent` at `0x14006640c`
- `KERNEL32!IsDebuggerPresent` at `0x1400664c5`
- `KERNEL32!IsDebuggerPresent` at `0x140066588`
- `KERNEL32!IsDebuggerPresent` at `0x140066638`
- `KERNEL32!IsDebuggerPresent` at `0x1400666a7`
- `KERNEL32!IsDebuggerPresent` at `0x140066775`
- `KERNEL32!IsDebuggerPresent` at `0x140066807`
- `KERNEL32!GetCurrentProcess` at `0x140066394`
- `KERNEL32!GetCurrentProcess` at `0x140066394`

## string_xrefs

- `0x1400663df`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x1400664ad`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x14006655b`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x14006660b`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x14006667f`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140066748`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x1400667da`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x1400663d8`: `CreateWmsSid`
- `0x14006649b`: `CreateWmsSid`
- `0x140066554`: `CreateWmsSid`
- `0x140066604`: `CreateWmsSid`
- `0x140066672`: `CreateWmsSid`
- `0x140066741`: `CreateWmsSid`
- `0x1400667d3`: `CreateWmsSid`

## pseudocode

```c
__int64 __fastcall CreateWmsSid(struct WmsSid *a1, struct _SID *a2)
{
  unsigned __int64 v4; // r8
  WELL_KNOWN_SID_TYPE v5; // eax
  void *v6; // r9
  void *v7; // r12
  void *v8; // r13
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // r8
  int v14; // eax
  signed int v15; // eax
  int TokenInformationWithLocalAlloc; // eax
  signed int v17; // eax
  int LocalGroupSid; // eax
  signed int v19; // eax
  signed int v20; // eax
  const unsigned __int16 *cchReferencedDomainName; // [rsp+28h] [rbp-D8h]
  PSID_NAME_USE peUse; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *peUsea; // [rsp+30h] [rbp-D0h]
  int v25; // [rsp+38h] [rbp-C8h]
  __int64 cbSid; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+48h] [rbp-B8h] BYREF
  void *v28; // [rsp+50h] [rbp-B0h] BYREF
  void *v29; // [rsp+58h] [rbp-A8h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+70h] [rbp-90h] BYREF

  memset_0(ReferencedDomainName, 0, 0x208u);
  v5 = *(_DWORD *)a1;
  v6 = 0;
  v7 = 0;
  LODWORD(v27) = 260;
  v8 = 0;
  TokenHandle = 0;
  v29 = 0;
  v28 = 0;
  cbSid = 68;
  if ( (unsigned int)(v5 - 3) <= 1 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( v11 >= 0 )
        v11 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        0x34Eu,
        L"CreateWmsSid",
        L"CBRAEx",
        L"fSuccess",
        v11);
      if ( IsDebuggerPresent() )
      {
        v12 = 846;
LABEL_9:
        v25 = v11;
        peUsea = L"fSuccess";
LABEL_10:
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          v12,
          L"CreateWmsSid",
          L"CBRAEx",
          peUsea,
          v25,
          cbSid,
          v27);
        goto LABEL_62;
      }
      v13 = 846;
      goto LABEL_60;
    }
    v6 = TokenHandle;
  }
  v11 = 0;
  switch ( *(_DWORD *)a1 )
  {
    case 0:
      if ( CreateWellKnownSid(*((WELL_KNOWN_SID_TYPE *)a1 + 1), 0, a2, (DWORD *)&cbSid) )
        goto LABEL_62;
      v20 = GetLastError();
      v11 = v20;
      if ( v20 > 0 )
        v11 = (unsigned __int16)v20 | 0x80070000;
      if ( v11 >= 0 )
        v11 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        0x355u,
        L"CreateWmsSid",
        L"CBRAEx",
        L"fSuccess",
        v11);
      if ( IsDebuggerPresent() )
      {
        v12 = 853;
        goto LABEL_9;
      }
      v13 = 853;
      goto LABEL_60;
    case 1:
      if ( LookupAccountNameW(
             0,
             *((LPCWSTR *)a1 + 1),
             a2,
             (LPDWORD)&cbSid,
             ReferencedDomainName,
             (LPDWORD)&v27,
             (PSID_NAME_USE)&cbSid + 1) )
      {
        goto LABEL_62;
      }
      v19 = GetLastError();
      v11 = v19;
      if ( v19 > 0 )
        v11 = (unsigned __int16)v19 | 0x80070000;
      if ( v11 >= 0 )
        v11 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        0x35Bu,
        L"CreateWmsSid",
        L"CBRAEx",
        L"fSuccess",
        v11);
      if ( IsDebuggerPresent() )
      {
        v12 = 859;
        goto LABEL_9;
      }
      v13 = 859;
      goto LABEL_60;
    case 2:
      LocalGroupSid = CUserManagement::s_GetLocalGroupSid(*((const unsigned __int16 **)a1 + 1), a2, v4);
      v11 = LocalGroupSid;
      if ( LocalGroupSid < 0 )
      {
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          0x360u,
          L"CreateWmsSid",
          L"CHRA",
          L"hr",
          LocalGroupSid);
        if ( IsDebuggerPresent() )
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
            864,
            L"CreateWmsSid",
            L"CHRA",
            L"hr",
            v11,
            cbSid,
            v27);
        else
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
            864,
            L"CreateWmsSid",
            L"CHRA",
            L"hr",
            v11);
      }
      goto LABEL_62;
    case 3:
      TokenInformationWithLocalAlloc = GetTokenInformationWithLocalAlloc(v6, TokenUser, &v29);
      v7 = v29;
      v11 = TokenInformationWithLocalAlloc;
      if ( TokenInformationWithLocalAlloc < 0 || CopySid(0x44u, a2, *(PSID *)v29) )
        goto LABEL_62;
      v17 = GetLastError();
      v11 = v17;
      if ( v17 > 0 )
        v11 = (unsigned __int16)v17 | 0x80070000;
      if ( v11 >= 0 )
        v11 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        0x36Au,
        L"CreateWmsSid",
        L"CBRAEx",
        L"fSuccess",
        v11);
      if ( IsDebuggerPresent() )
      {
        v12 = 874;
        goto LABEL_9;
      }
      v13 = 874;
LABEL_60:
      LODWORD(peUse) = v11;
      cchReferencedDomainName = L"fSuccess";
      goto LABEL_61;
  }
  if ( *(_DWORD *)a1 != 4 )
  {
    v11 = -2147024809;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      0x378u,
      L"CreateWmsSid",
      L"CBRAEx",
      L"0",
      -2147024809);
    if ( IsDebuggerPresent() )
    {
      v25 = -2147024809;
      v12 = 888;
      peUsea = L"0";
      goto LABEL_10;
    }
    LODWORD(peUse) = -2147024809;
    v13 = 888;
    cchReferencedDomainName = L"0";
LABEL_61:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      v13,
      L"CreateWmsSid",
      L"CBRAEx",
      cchReferencedDomainName,
      peUse);
    goto LABEL_62;
  }
  v14 = GetTokenInformationWithLocalAlloc(v6, TokenPrimaryGroup, &v28);
  v8 = v28;
  v11 = v14;
  if ( v14 >= 0 && !CopySid(0x44u, a2, *(PSID *)v28) )
  {
    v15 = GetLastError();
    v11 = v15;
    if ( v15 > 0 )
      v11 = (unsigned __int16)v15 | 0x80070000;
    if ( v11 >= 0 )
      v11 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      0x373u,
      L"CreateWmsSid",
      L"CBRAEx",
      L"fSuccess",
      v11);
    if ( IsDebuggerPresent() )
    {
      v12 = 883;
      goto LABEL_9;
    }
    v13 = 883;
    goto LABEL_60;
  }
LABEL_62:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  LocalFree(v7);
  LocalFree(v8);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140066310  mov     [rsp-8+arg_10], rbx
0x140066315  push    rbp
0x140066316  push    rsi
0x140066317  push    rdi
0x140066318  push    r12
0x14006631a  push    r13
0x14006631c  push    r14
0x14006631e  push    r15
0x140066320  lea     rbp, [rsp-190h]
0x140066328  sub     rsp, 290h
0x14006632f  mov     rax, cs:__security_cookie
0x140066336  xor     rax, rsp
0x140066339  mov     [rbp+1C0h+var_40], rax
0x140066340  mov     rsi, rdx
0x140066343  mov     rdi, rcx
0x140066346  xor     edx, edx; Val
0x140066348  lea     rcx, [rsp+2C0h+var_250]; void *
0x14006634d  mov     r8d, 208h; Size
0x140066353  call    memset_0
0x140066358  mov     eax, [rdi]
0x14006635a  xor     r9d, r9d
0x14006635d  xor     r12d, r12d
0x140066360  mov     dword ptr [rsp+2C0h+var_278], 104h
0x140066368  xor     r13d, r13d
0x14006636b  mov     [rsp+2C0h+TokenHandle], r9
0x140066370  sub     eax, 3
0x140066373  mov     [rsp+2C0h+var_268], r12
0x140066378  mov     [rsp+2C0h+var_270], r13
0x14006637d  lea     r14d, [r9+44h]
0x140066381  mov     [rsp+2C0h+cbSid], r14d
0x140066386  mov     [rsp+2C0h+var_27C], r9d
0x14006638b  cmp     eax, 1
0x14006638e  ja      loc_140066458
0x140066394  call    cs:__imp_GetCurrentProcess
0x14006639a  mov     rcx, rax; ProcessHandle
0x14006639d  lea     r8, [rsp+2C0h+TokenHandle]; TokenHandle
0x1400663a2  lea     edx, [r12+8]; DesiredAccess
0x1400663a7  call    cs:__imp_OpenProcessToken
0x1400663ad  test    eax, eax
0x1400663af  jnz     loc_140066453
0x1400663b5  call    cs:__imp_GetLastError
0x1400663bb  mov     ebx, eax
0x1400663bd  test    eax, eax
0x1400663bf  jle     short loc_1400663CA
0x1400663c1  movzx   ebx, ax
0x1400663c4  or      ebx, 80070000h
0x1400663ca  mov     eax, 80004005h
0x1400663cf  lea     r14, aCbraex; "CBRAEx"
0x1400663d6  test    ebx, ebx
0x1400663d8  lea     rsi, aCreatewmssid; "CreateWmsSid"
0x1400663df  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x1400663e6  mov     r9, r14; unsigned __int16 *
0x1400663e9  cmovns  ebx, eax
0x1400663ec  lea     r15, aFsuccess; "fSuccess"
0x1400663f3  mov     dword ptr [rsp+2C0h+cchReferencedDomainName], ebx; int
0x1400663f7  mov     r8, rsi; unsigned __int16 *
0x1400663fa  mov     edx, 34Eh; unsigned int
0x1400663ff  mov     [rsp+2C0h+ReferencedDomainName], r15; unsigned __int16 *
0x140066404  mov     rcx, rdi; unsigned __int16 *
0x140066407  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006640c  call    cs:__imp_IsDebuggerPresent
0x140066412  test    eax, eax
0x140066414  jz      short loc_140066448
0x140066416  mov     r9d, 34Eh
0x14006641c  mov     [rsp+2C0h+var_288], ebx
0x140066420  mov     [rsp+2C0h+peUse], r15
0x140066425  mov     [rsp+2C0h+cchReferencedDomainName], r14
0x14006642a  mov     r8, rdi
0x14006642d  mov     [rsp+2C0h+ReferencedDomainName], rsi
0x140066432  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140066439  mov     ecx, 2; unsigned __int8
0x14006643e  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140066443  jmp     loc_140066842
0x140066448  mov     r8d, 34Eh
0x14006644e  jmp     loc_140066822
0x140066453  mov     r9, [rsp+2C0h+TokenHandle]
0x140066458  mov     ecx, [rdi]
0x14006645a  xor     ebx, ebx
0x14006645c  test    ecx, ecx
0x14006645e  jz      loc_140066795
0x140066464  sub     ecx, 1
0x140066467  jz      loc_1400666E4
0x14006646d  sub     ecx, 1
0x140066470  jz      loc_140066658
0x140066476  sub     ecx, 1
0x140066479  jz      loc_1400665A8
0x14006647f  cmp     ecx, 1
0x140066482  jz      short loc_1400664F8
0x140066484  lea     rax, a0; "0"
0x14006648b  mov     ebx, 80070057h
0x140066490  lea     r14, aCbraex; "CBRAEx"
0x140066497  mov     dword ptr [rsp+2C0h+cchReferencedDomainName], ebx; int
0x14006649b  lea     rsi, aCreatewmssid; "CreateWmsSid"
0x1400664a2  mov     [rsp+2C0h+ReferencedDomainName], rax; unsigned __int16 *
0x1400664a7  mov     r15d, 378h
0x1400664ad  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x1400664b4  mov     r9, r14; unsigned __int16 *
0x1400664b7  mov     r8, rsi; unsigned __int16 *
0x1400664ba  mov     edx, r15d; unsigned int
0x1400664bd  mov     rcx, rdi; unsigned __int16 *
0x1400664c0  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400664c5  call    cs:__imp_IsDebuggerPresent
0x1400664cb  test    eax, eax
0x1400664cd  lea     rax, a0; "0"
0x1400664d4  jz      short loc_1400664E7
0x1400664d6  mov     [rsp+2C0h+var_288], ebx
0x1400664da  mov     r9d, r15d
0x1400664dd  mov     [rsp+2C0h+peUse], rax
0x1400664e2  jmp     loc_140066425
0x1400664e7  mov     dword ptr [rsp+2C0h+peUse], ebx
0x1400664eb  mov     r8d, r15d
0x1400664ee  mov     [rsp+2C0h+cchReferencedDomainName], rax
0x1400664f3  jmp     loc_14006682B
0x1400664f8  lea     r8, [rsp+2C0h+var_270]; void **
0x1400664fd  mov     edx, 5; TokenInformationClass
0x140066502  mov     rcx, r9; TokenHandle
0x140066505  call    ?GetTokenInformationWithLocalAlloc@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAX@Z; GetTokenInformationWithLocalAlloc(void *,_TOKEN_INFORMATION_CLASS,void * *)
0x14006650a  mov     r13, [rsp+2C0h+var_270]
0x14006650f  mov     ebx, eax
0x140066511  test    eax, eax
0x140066513  js      loc_140066842
0x140066519  mov     r8, [r13+0]; pSourceSid
0x14006651d  mov     rdx, rsi; pDestinationSid
0x140066520  mov     ecx, r14d; nDestinationSidLength
0x140066523  call    cs:__imp_CopySid
0x140066529  test    eax, eax
0x14006652b  jnz     loc_140066842
0x140066531  call    cs:__imp_GetLastError
0x140066537  mov     ebx, eax
0x140066539  test    eax, eax
0x14006653b  jle     short loc_140066546
0x14006653d  movzx   ebx, ax
0x140066540  or      ebx, 80070000h
0x140066546  mov     eax, 80004005h
0x14006654b  lea     r14, aCbraex; "CBRAEx"
0x140066552  test    ebx, ebx
0x140066554  lea     rsi, aCreatewmssid; "CreateWmsSid"
0x14006655b  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140066562  mov     r9, r14; unsigned __int16 *
0x140066565  cmovns  ebx, eax
0x140066568  lea     r15, aFsuccess; "fSuccess"
0x14006656f  mov     dword ptr [rsp+2C0h+cchReferencedDomainName], ebx; int
0x140066573  mov     r8, rsi; unsigned __int16 *
0x140066576  mov     edx, 373h; unsigned int
0x14006657b  mov     [rsp+2C0h+ReferencedDomainName], r15; unsigned __int16 *
0x140066580  mov     rcx, rdi; unsigned __int16 *
0x140066583  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140066588  call    cs:__imp_IsDebuggerPresent
0x14006658e  test    eax, eax
0x140066590  jz      short loc_14006659D
0x140066592  mov     r9d, 373h
0x140066598  jmp     loc_14006641C
0x14006659d  mov     r8d, 373h
0x1400665a3  jmp     loc_140066822
0x1400665a8  lea     r8, [rsp+2C0h+var_268]; void **
0x1400665ad  mov     edx, 1; TokenInformationClass
0x1400665b2  mov     rcx, r9; TokenHandle
0x1400665b5  call    ?GetTokenInformationWithLocalAlloc@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAX@Z; GetTokenInformationWithLocalAlloc(void *,_TOKEN_INFORMATION_CLASS,void * *)
0x1400665ba  mov     r12, [rsp+2C0h+var_268]
0x1400665bf  mov     ebx, eax
0x1400665c1  test    eax, eax
0x1400665c3  js      loc_140066842
0x1400665c9  mov     r8, [r12]; pSourceSid
0x1400665cd  mov     rdx, rsi; pDestinationSid
0x1400665d0  mov     ecx, r14d; nDestinationSidLength
0x1400665d3  call    cs:__imp_CopySid
0x1400665d9  test    eax, eax
0x1400665db  jnz     loc_140066842
0x1400665e1  call    cs:__imp_GetLastError
0x1400665e7  mov     ebx, eax
0x1400665e9  test    eax, eax
0x1400665eb  jle     short loc_1400665F6
0x1400665ed  movzx   ebx, ax
0x1400665f0  or      ebx, 80070000h
0x1400665f6  mov     eax, 80004005h
0x1400665fb  lea     r14, aCbraex; "CBRAEx"
0x140066602  test    ebx, ebx
0x140066604  lea     rsi, aCreatewmssid; "CreateWmsSid"
0x14006660b  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140066612  mov     r9, r14; unsigned __int16 *
0x140066615  cmovns  ebx, eax
0x140066618  lea     r15, aFsuccess; "fSuccess"
0x14006661f  mov     dword ptr [rsp+2C0h+cchReferencedDomainName], ebx; int
0x140066623  mov     r8, rsi; unsigned __int16 *
0x140066626  mov     edx, 36Ah; unsigned int
0x14006662b  mov     [rsp+2C0h+ReferencedDomainName], r15; unsigned __int16 *
0x140066630  mov     rcx, rdi; unsigned __int16 *
0x140066633  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140066638  call    cs:__imp_IsDebuggerPresent
0x14006663e  test    eax, eax
0x140066640  jz      short loc_14006664D
0x140066642  mov     r9d, 36Ah
0x140066648  jmp     loc_14006641C
0x14006664d  mov     r8d, 36Ah
0x140066653  jmp     loc_140066822
0x140066658  mov     rcx, [rdi+8]; unsigned __int16 *
0x14006665c  mov     rdx, rsi; void *
0x14006665f  call    ?s_GetLocalGroupSid@CUserManagement@@SAJPEBGPEAX_K@Z; CUserManagement::s_GetLocalGroupSid(ushort const *,void *,unsigned __int64)
0x140066664  mov     ebx, eax
0x140066666  test    eax, eax
0x140066668  jns     loc_140066842
0x14006666e  mov     dword ptr [rsp+2C0h+cchReferencedDomainName], eax; int
0x140066672  lea     rsi, aCreatewmssid; "CreateWmsSid"
0x140066679  mov     r14d, 360h
0x14006667f  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140066686  lea     r15, aHr; "hr"
0x14006668d  mov     r8, rsi; unsigned __int16 *
0x140066690  mov     edx, r14d; unsigned int
0x140066693  mov     [rsp+2C0h+ReferencedDomainName], r15; unsigned __int16 *
0x140066698  mov     rcx, rdi; unsigned __int16 *
0x14006669b  lea     r9, aChra; "CHRA"
0x1400666a2  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400666a7  call    cs:__imp_IsDebuggerPresent
0x1400666ad  test    eax, eax
0x1400666af  lea     rax, aChra; "CHRA"
0x1400666b6  jz      short loc_1400666CE
0x1400666b8  mov     [rsp+2C0h+var_288], ebx
0x1400666bc  mov     r9d, r14d
0x1400666bf  mov     [rsp+2C0h+peUse], r15
0x1400666c4  mov     [rsp+2C0h+cchReferencedDomainName], rax
0x1400666c9  jmp     loc_14006642A
0x1400666ce  mov     dword ptr [rsp+2C0h+peUse], ebx
0x1400666d2  mov     r8d, r14d
0x1400666d5  mov     [rsp+2C0h+cchReferencedDomainName], r15
0x1400666da  mov     [rsp+2C0h+ReferencedDomainName], rax
0x1400666df  jmp     loc_140066830
0x1400666e4  mov     rdx, [rdi+8]; lpAccountName
0x1400666e8  lea     rax, [rsp+2C0h+var_27C]
0x1400666ed  mov     [rsp+2C0h+peUse], rax; peUse
0x1400666f2  lea     r9, [rsp+2C0h+cbSid]; cbSid
0x1400666f7  lea     rax, [rsp+2C0h+var_278]
0x1400666fc  mov     r8, rsi; Sid
0x1400666ff  mov     [rsp+2C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x140066704  xor     ecx, ecx; lpSystemName
0x140066706  lea     rax, [rsp+2C0h+var_250]
0x14006670b  mov     [rsp+2C0h+ReferencedDomainName], rax; ReferencedDomainName
0x140066710  call    cs:__imp_LookupAccountNameW
0x140066716  test    eax, eax
0x140066718  jnz     loc_140066842
0x14006671e  call    cs:__imp_GetLastError
0x140066724  mov     ebx, eax
0x140066726  test    eax, eax
0x140066728  jle     short loc_140066733
0x14006672a  movzx   ebx, ax
0x14006672d  or      ebx, 80070000h
0x140066733  mov     eax, 80004005h
0x140066738  lea     r14, aCbraex; "CBRAEx"
0x14006673f  test    ebx, ebx
0x140066741  lea     rsi, aCreatewmssid; "CreateWmsSid"
0x140066748  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x14006674f  mov     r9, r14; unsigned __int16 *
0x140066752  cmovns  ebx, eax
0x140066755  lea     r15, aFsuccess; "fSuccess"
0x14006675c  mov     dword ptr [rsp+2C0h+cchReferencedDomainName], ebx; int
0x140066760  mov     r8, rsi; unsigned __int16 *
0x140066763  mov     edx, 35Bh; unsigned int
0x140066768  mov     [rsp+2C0h+ReferencedDomainName], r15; unsigned __int16 *
0x14006676d  mov     rcx, rdi; unsigned __int16 *
0x140066770  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140066775  call    cs:__imp_IsDebuggerPresent
0x14006677b  test    eax, eax
0x14006677d  jz      short loc_14006678A
0x14006677f  mov     r9d, 35Bh
0x140066785  jmp     loc_14006641C
0x14006678a  mov     r8d, 35Bh
0x140066790  jmp     loc_140066822
0x140066795  mov     ecx, [rdi+4]; WellKnownSidType
0x140066798  lea     r9, [rsp+2C0h+cbSid]; cbSid
0x14006679d  mov     r8, rsi; pSid
0x1400667a0  xor     edx, edx; DomainSid
0x1400667a2  call    cs:__imp_CreateWellKnownSid
0x1400667a8  test    eax, eax
0x1400667aa  jnz     loc_140066842
0x1400667b0  call    cs:__imp_GetLastError
0x1400667b6  mov     ebx, eax
0x1400667b8  test    eax, eax
0x1400667ba  jle     short loc_1400667C5
0x1400667bc  movzx   ebx, ax
0x1400667bf  or      ebx, 80070000h
0x1400667c5  mov     eax, 80004005h
0x1400667ca  lea     r14, aCbraex; "CBRAEx"
0x1400667d1  test    ebx, ebx
0x1400667d3  lea     rsi, aCreatewmssid; "CreateWmsSid"
0x1400667da  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x1400667e1  mov     r9, r14; unsigned __int16 *
0x1400667e4  cmovns  ebx, eax
0x1400667e7  lea     r15, aFsuccess; "fSuccess"
0x1400667ee  mov     dword ptr [rsp+2C0h+cchReferencedDomainName], ebx; int
0x1400667f2  mov     r8, rsi; unsigned __int16 *
0x1400667f5  mov     edx, 355h; unsigned int
0x1400667fa  mov     [rsp+2C0h+ReferencedDomainName], r15; unsigned __int16 *
0x1400667ff  mov     rcx, rdi; unsigned __int16 *
0x140066802  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140066807  call    cs:__imp_IsDebuggerPresent
0x14006680d  test    eax, eax
0x14006680f  jz      short loc_14006681C
0x140066811  mov     r9d, 355h
0x140066817  jmp     loc_14006641C
0x14006681c  mov     r8d, 355h
0x140066822  mov     dword ptr [rsp+2C0h+peUse], ebx
  ... truncated ...
```
