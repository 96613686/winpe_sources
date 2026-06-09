# CertificateInfo::VerifyAndGetEmbeddedCertificateInfo(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,_WINTRUST_DATA *,Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus &,CertificateInfo &)

- ea: `0x18004d9fc`
- end: `0x18004dcd8`
- name: `?VerifyAndGetEmbeddedCertificateInfo@CertificateInfo@@CAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAU_WINTRUST_DATA@@AEAW4IsolationQueryAppIdentityStatus@IsolationEnvironment@AI@Windows@@AEAV1@@Z`
- size: `732`
- prototype: `__int64 __fastcall(char *, LPVOID pWVTData, enum Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus *, struct CertificateInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004d35c`
- `0x18004d4b4`

## callees

- `0x180002520`
- `0x180011e18`
- `0x180013230`
- `0x18004cd24`
- `0x18004d9fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004dc4e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004dc4e`
- `WINTRUST!WinVerifyTrust` at `0x18004da53`
- `WINTRUST!WinVerifyTrust` at `0x18004da53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004db55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dba2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004db55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dba2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004db75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004dbc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004dc1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004db75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004dbc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004dc1d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004dafe`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004dafe`
- `api-ms-win-security-base-l1-2-0!SetCachedSigningLevel` at `0x18004db4b`
- `api-ms-win-security-base-l1-2-0!SetCachedSigningLevel` at `0x18004db4b`
- `api-ms-win-security-base-l1-2-0!GetCachedSigningLevel` at `0x18004db27`
- `api-ms-win-security-base-l1-2-0!GetCachedSigningLevel` at `0x18004db98`
- `api-ms-win-security-base-l1-2-0!GetCachedSigningLevel` at `0x18004db27`
- `api-ms-win-security-base-l1-2-0!GetCachedSigningLevel` at `0x18004db98`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18004dc38`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18004dc38`

## string_xrefs

- `0x18004da9d`: `CRYPT_E_SECURITY_SETTINGS`
- `0x18004dbec`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\certificateinfo.cpp`

## pseudocode

```c
__int64 __fastcall CertificateInfo::VerifyAndGetEmbeddedCertificateInfo(
        const WCHAR *a1,
        HANDLE *pWVTData,
        enum Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus *a3,
        struct CertificateInfo *a4)
{
  LONG v7; // eax
  const wchar_t *v8; // r8
  __int64 result; // rax
  char v10; // r14
  const WCHAR *v11; // rcx
  char *FileW; // rbx
  signed int LastError; // eax
  unsigned int v14; // esi
  char v15; // r15
  const WCHAR *v16; // rcx
  LPWSTR FileNameW; // r15
  __int64 *v18; // rbx
  HANDLE *v19; // rcx
  _BYTE v20[4]; // [rsp+40h] [rbp-38h] BYREF
  int v21; // [rsp+44h] [rbp-34h] BYREF
  char *v22; // [rsp+48h] [rbp-30h] BYREF
  HANDLE *v23; // [rsp+50h] [rbp-28h]
  GUID pgActionID; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  v23 = pWVTData;
  pgActionID.Data1 = 11191659;
  *(_DWORD *)&pgActionID.Data2 = 298896708;
  *(_DWORD *)pgActionID.Data4 = -1073692020;
  *(_DWORD *)&pgActionID.Data4[4] = -292175281;
  v7 = WinVerifyTrust(0, &pgActionID, pWVTData);
  if ( v7 )
  {
    switch ( v7 )
    {
      case -2146885594:
        v8 = L"CRYPT_E_SECURITY_SETTINGS";
        break;
      case -2146762748:
        v8 = L"TRUST_E_SUBJECT_NOT_TRUSTED";
        break;
      case -2146762496:
        v8 = L"TRUST_E_NOSIGNATURE";
        break;
      default:
        v8 = L"Unknown error code";
        if ( v7 == -2146762479 )
          v8 = L"TRUST_E_EXPLICIT_DISTRUST";
        break;
    }
    Log(4u, L"[QueryAppIdentity] Call to WinVerifyTrust failed with error: %s", v8);
    result = 2147500037LL;
    *(_DWORD *)a3 = 4;
    return result;
  }
  v10 = 1;
  *(_BYTE *)a4 = 1;
  if ( *((_QWORD *)a1 + 3) <= 7u )
    v11 = a1;
  else
    v11 = *(const WCHAR **)a1;
  v20[0] = 0;
  v21 = 1;
  FileW = (char *)CreateFileW(v11, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( !(unsigned int)GetCachedSigningLevel(FileW, &v21, v20, 0, 0, 0) )
  {
    v22 = FileW;
    if ( !(unsigned int)SetCachedSigningLevel(&v22, 1, 4, 0) )
    {
      LastError = GetLastError();
      v14 = LastError;
      if ( LastError == -1073740760 )
      {
        if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(FileW);
        goto LABEL_43;
      }
LABEL_22:
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(FileW);
      if ( (v14 & 0x80000000) != 0 )
      {
        if ( *((_QWORD *)a1 + 3) > 7u )
          a1 = *(const WCHAR **)a1;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x1C3,
          (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\certificateinfo.cpp",
          (const char *)v14,
          (int)"[QueryAppIdentity] CheckTrustLevel failed for file %s",
          (const char *)a1);
        return v14;
      }
      goto LABEL_43;
    }
    if ( !(unsigned int)GetCachedSigningLevel(FileW, &v21, v20, 0, 0, 0) )
    {
      LastError = GetLastError();
      v14 = LastError;
      goto LABEL_22;
    }
  }
  v15 = v20[0];
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  if ( v15 != 12 )
  {
LABEL_43:
    v10 = 0;
LABEL_44:
    v19 = v23;
    *((_BYTE *)a4 + 40) = v10;
    return CertificateInfo::ExtractThumbprintInfoFromStateData(v19[7], a3, a4);
  }
  if ( *((_QWORD *)a1 + 3) <= 7u )
    v16 = a1;
  else
    v16 = *(const WCHAR **)a1;
  FileNameW = PathFindFileNameW(v16);
  v18 = (__int64 *)&AllowedWindowsSignedClients;
  do
  {
    if ( !(unsigned int)_o__wcsicmp(FileNameW, *v18) )
    {
      Log(4u, L"Process %s is an exempted Windows signed client.", FileNameW);
      goto LABEL_44;
    }
    ++v18;
  }
  while ( v18 != &qword_1800B80E8 );
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(const WCHAR **)a1;
  Log(4u, L"[QueryAppIdentity] Skipping process %s is a non-exempt Windows signed binary.", a1);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18004d9fc  push    rbp
0x18004d9fe  push    rbx
0x18004d9ff  push    rsi
0x18004da00  push    rdi
0x18004da01  push    r12
0x18004da03  push    r13
0x18004da05  push    r14
0x18004da07  push    r15
0x18004da09  mov     rbp, rsp
0x18004da0c  sub     rsp, 78h
0x18004da10  mov     rax, cs:__security_cookie
0x18004da17  xor     rax, rsp
0x18004da1a  mov     [rbp+var_10], rax
0x18004da1e  mov     r13, r8
0x18004da21  mov     [rbp+var_28], rdx
0x18004da25  mov     r8, rdx; pWVTData
0x18004da28  mov     [rbp+pgActionID.Data1], 0AAC56Bh
0x18004da2f  mov     rdi, rcx
0x18004da32  mov     dword ptr [rbp+pgActionID.Data2], 11D0CD44h
0x18004da39  lea     rdx, [rbp+pgActionID]; pgActionID
0x18004da3d  mov     dword ptr [rbp+pgActionID.Data4], 0C000C28Ch
0x18004da44  xor     ecx, ecx; hwnd
0x18004da46  mov     dword ptr [rbp+pgActionID.Data4+4], 0EE95C24Fh
0x18004da4d  mov     r12, r9
0x18004da50  xor     r15d, r15d
0x18004da53  call    cs:__imp_WinVerifyTrust
0x18004da59  test    eax, eax
0x18004da5b  jz      short loc_18004DAC5
0x18004da5d  cmp     eax, 80092026h
0x18004da62  jz      short loc_18004DA9D
0x18004da64  cmp     eax, 800B0004h
0x18004da69  jz      short loc_18004DA94
0x18004da6b  cmp     eax, 800B0100h
0x18004da70  jz      short loc_18004DA8B
0x18004da72  cmp     eax, 800B0111h
0x18004da77  lea     r8, aUnknownErrorCo; "Unknown error code"
0x18004da7e  lea     rcx, aTrustEExplicit; "TRUST_E_EXPLICIT_DISTRUST"
0x18004da85  cmovz   r8, rcx
0x18004da89  jmp     short loc_18004DAA4
0x18004da8b  lea     r8, aTrustENosignat; "TRUST_E_NOSIGNATURE"
0x18004da92  jmp     short loc_18004DAA4
0x18004da94  lea     r8, aTrustESubjectN; "TRUST_E_SUBJECT_NOT_TRUSTED"
0x18004da9b  jmp     short loc_18004DAA4
0x18004da9d  lea     r8, aCryptESecurity; "CRYPT_E_SECURITY_SETTINGS"
0x18004daa4  mov     esi, 4
0x18004daa9  lea     rdx, aQueryappidenti_31; "[QueryAppIdentity] Call to WinVerifyTru"...
0x18004dab0  mov     ecx, esi; unsigned __int8
0x18004dab2  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18004dab7  mov     eax, 80004005h
0x18004dabc  mov     [r13+0], esi
0x18004dac0  jmp     loc_18004DCBB
0x18004dac5  mov     r14d, 1
0x18004dacb  mov     [r12], r14b
0x18004dacf  cmp     qword ptr [rdi+18h], 7
0x18004dad4  jbe     short loc_18004DADB
0x18004dad6  mov     rcx, [rdi]
0x18004dad9  jmp     short loc_18004DADE
0x18004dadb  mov     rcx, rdi; lpFileName
0x18004dade  mov     [rsp+78h+hTemplateFile], r15; hTemplateFile
0x18004dae3  xor     r9d, r9d; lpSecurityAttributes
0x18004dae6  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18004daee  mov     r8d, r14d; dwShareMode
0x18004daf1  mov     edx, 80000000h; dwDesiredAccess
0x18004daf6  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x18004dafe  call    cs:__imp_CreateFileW
0x18004db04  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], r15
0x18004db09  lea     r8, [rbp+var_38]
0x18004db0d  mov     rcx, rax
0x18004db10  mov     [rbp+var_38], r15b
0x18004db14  xor     r9d, r9d
0x18004db17  mov     [rbp+var_34], r14d
0x18004db1b  lea     rdx, [rbp+var_34]
0x18004db1f  mov     qword ptr [rsp+78h+dwCreationDisposition], r15
0x18004db24  mov     rbx, rax
0x18004db27  call    cs:__imp_GetCachedSigningLevel
0x18004db2d  mov     esi, 4
0x18004db32  test    eax, eax
0x18004db34  jnz     loc_18004DC0C
0x18004db3a  xor     r9d, r9d
0x18004db3d  mov     [rbp+var_30], rbx
0x18004db41  mov     r8d, esi
0x18004db44  lea     rcx, [rbp+var_30]
0x18004db48  mov     edx, r14d
0x18004db4b  call    cs:__imp_SetCachedSigningLevel
0x18004db51  test    eax, eax
0x18004db53  jnz     short loc_18004DB80
0x18004db55  call    cs:__imp_GetLastError
0x18004db5b  mov     esi, eax
0x18004db5d  cmp     eax, 0C0000428h
0x18004db62  jnz     short loc_18004DBAA
0x18004db64  lea     rax, [rbx-1]
0x18004db68  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004db6c  ja      loc_18004DCA0
0x18004db72  mov     rcx, rbx; hObject
0x18004db75  call    cs:__imp_CloseHandle
0x18004db7b  jmp     loc_18004DCA0
0x18004db80  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], r15
0x18004db85  lea     r8, [rbp+var_38]
0x18004db89  xor     r9d, r9d
0x18004db8c  mov     qword ptr [rsp+78h+dwCreationDisposition], r15
0x18004db91  lea     rdx, [rbp+var_34]
0x18004db95  mov     rcx, rbx
0x18004db98  call    cs:__imp_GetCachedSigningLevel
0x18004db9e  test    eax, eax
0x18004dba0  jnz     short loc_18004DC0C
0x18004dba2  call    cs:__imp_GetLastError
0x18004dba8  mov     esi, eax
0x18004dbaa  test    eax, eax
0x18004dbac  jle     short loc_18004DBB7
0x18004dbae  movzx   esi, ax
0x18004dbb1  or      esi, 80070000h
0x18004dbb7  lea     rax, [rbx-1]
0x18004dbbb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004dbbf  ja      short loc_18004DBCA
0x18004dbc1  mov     rcx, rbx; hObject
0x18004dbc4  call    cs:__imp_CloseHandle
0x18004dbca  test    esi, esi
0x18004dbcc  jns     loc_18004DCA0
0x18004dbd2  cmp     qword ptr [rdi+18h], 7
0x18004dbd7  jbe     short loc_18004DBDC
0x18004dbd9  mov     rdi, [rdi]
0x18004dbdc  mov     rcx, [rbp+40h]; this
0x18004dbe0  lea     rax, aQueryappidenti_9; "[QueryAppIdentity] CheckTrustLevel fail"...
0x18004dbe7  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rdi; char *
0x18004dbec  lea     r8, aOnecoreuapWind_16; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004dbf3  mov     r9d, esi; char *
0x18004dbf6  mov     qword ptr [rsp+78h+dwCreationDisposition], rax; int
0x18004dbfb  mov     edx, 1C3h; void *
0x18004dc00  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004dc05  mov     eax, esi
0x18004dc07  jmp     loc_18004DCBB
0x18004dc0c  mov     r15b, [rbp+var_38]
0x18004dc10  lea     rax, [rbx-1]
0x18004dc14  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004dc18  ja      short loc_18004DC23
0x18004dc1a  mov     rcx, rbx; hObject
0x18004dc1d  call    cs:__imp_CloseHandle
0x18004dc23  cmp     r15b, 0Ch
0x18004dc27  jnz     short loc_18004DC9D
0x18004dc29  cmp     qword ptr [rdi+18h], 7
0x18004dc2e  jbe     short loc_18004DC35
0x18004dc30  mov     rcx, [rdi]
0x18004dc33  jmp     short loc_18004DC38
0x18004dc35  mov     rcx, rdi; pszPath
0x18004dc38  call    cs:__imp_PathFindFileNameW
0x18004dc3e  mov     r15, rax
0x18004dc41  lea     rbx, ?AllowedWindowsSignedClients@@3PAPEB_WA; wchar_t const * near * AllowedWindowsSignedClients
0x18004dc48  mov     rdx, [rbx]
0x18004dc4b  mov     rcx, r15
0x18004dc4e  call    cs:__imp__o__wcsicmp
0x18004dc54  test    eax, eax
0x18004dc56  jz      short loc_18004DC8A
0x18004dc58  add     rbx, 8
0x18004dc5c  lea     rax, qword_1800B80E8
0x18004dc63  cmp     rbx, rax
0x18004dc66  jnz     short loc_18004DC48
0x18004dc68  cmp     qword ptr [rdi+18h], 7
0x18004dc6d  jbe     short loc_18004DC72
0x18004dc6f  mov     rdi, [rdi]
0x18004dc72  mov     r8, rdi
0x18004dc75  lea     rdx, aQueryappidenti_25; "[QueryAppIdentity] Skipping process %s "...
0x18004dc7c  mov     ecx, esi; unsigned __int8
0x18004dc7e  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18004dc83  mov     eax, 80070057h
0x18004dc88  jmp     short loc_18004DCBB
0x18004dc8a  mov     r8, r15
0x18004dc8d  lea     rdx, aProcessSIsAnEx; "Process %s is an exempted Windows signe"...
0x18004dc94  mov     ecx, esi; unsigned __int8
0x18004dc96  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18004dc9b  jmp     short loc_18004DCA3
0x18004dc9d  xor     r15d, r15d
0x18004dca0  mov     r14b, r15b
0x18004dca3  mov     rcx, [rbp+var_28]
0x18004dca7  mov     r8, r12; struct CertificateInfo *
0x18004dcaa  mov     [r12+28h], r14b
0x18004dcaf  mov     rdx, r13; enum Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus *
0x18004dcb2  mov     rcx, [rcx+38h]; hStateData
0x18004dcb6  call    ?ExtractThumbprintInfoFromStateData@CertificateInfo@@CAJPEAXAEAW4IsolationQueryAppIdentityStatus@IsolationEnvironment@AI@Windows@@AEAV1@@Z; CertificateInfo::ExtractThumbprintInfoFromStateData(void *,Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus &,CertificateInfo &)
0x18004dcbb  mov     rcx, [rbp+var_10]
0x18004dcbf  xor     rcx, rsp; StackCookie
0x18004dcc2  call    __security_check_cookie
0x18004dcc7  add     rsp, 78h
0x18004dccb  pop     r15
0x18004dccd  pop     r14
0x18004dccf  pop     r13
0x18004dcd1  pop     r12
0x18004dcd3  pop     rdi
0x18004dcd4  pop     rsi
0x18004dcd5  pop     rbx
0x18004dcd6  pop     rbp
0x18004dcd7  retn
```
