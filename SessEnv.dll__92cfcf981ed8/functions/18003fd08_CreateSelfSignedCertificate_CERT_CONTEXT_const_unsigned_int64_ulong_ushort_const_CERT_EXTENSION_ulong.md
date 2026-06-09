# CreateSelfSignedCertificate(_CERT_CONTEXT const * *,unsigned __int64,ulong,ushort const *,_CERT_EXTENSION *,ulong)

- ea: `0x18003fd08`
- end: `0x18003feee`
- name: `?CreateSelfSignedCertificate@@YAJPEAPEBU_CERT_CONTEXT@@_KKPEBGPEAU_CERT_EXTENSION@@K@Z`
- size: `486`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT **, NCRYPT_KEY_HANDLE, __int64, const unsigned __int16 *, struct _CERT_EXTENSION *, DWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x1800402cc`

## callees

- `0x18001a280`
- `0x18001a8d0`
- `0x18003fd08`
- `0x18003fef4`
- `0x180040030`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fe12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fe12`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003fddb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003fddb`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18003fe08`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18003fe50`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18003fe08`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18003fe50`
- `CRYPT32!CertCreateSelfSignCertificate` at `0x18003fe94`
- `CRYPT32!CertCreateSelfSignCertificate` at `0x18003fe94`
- `ncrypt!NCryptIsKeyHandle` at `0x18003fdaa`
- `ncrypt!NCryptIsKeyHandle` at `0x18003fdaa`

## pseudocode

```c
__int64 __fastcall CreateSelfSignedCertificate(
        const struct _CERT_CONTEXT **a1,
        NCRYPT_KEY_HANDLE a2,
        __int64 a3,
        const unsigned __int16 *a4,
        struct _CERT_EXTENSION *a5,
        DWORD a6)
{
  signed int KeyProviderInfo; // ebx
  BOOL IsKeyHandle; // esi
  __int64 v10; // rax
  signed int LastError; // eax
  __int64 v12; // rax
  struct _CRYPT_KEY_PROV_INFO *p_Block; // r9
  const struct _CERT_CONTEXT *v14; // rax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-79h] BYREF
  FILETIME FileTime; // [rsp+48h] [rbp-71h] BYREF
  struct _CERT_EXTENSIONS pExtensions; // [rsp+50h] [rbp-69h] BYREF
  struct _CRYPTOAPI_BLOB pSubjectIssuerBlob; // [rsp+60h] [rbp-59h] BYREF
  struct _CRYPT_ALGORITHM_IDENTIFIER pSignatureAlgorithm; // [rsp+70h] [rbp-49h] BYREF
  struct _CRYPT_KEY_PROV_INFO Block; // [rsp+88h] [rbp-31h] BYREF
  struct _SYSTEMTIME pEndTime; // [rsp+B8h] [rbp-1h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+C8h] [rbp+Fh] BYREF

  *a1 = 0;
  pSignatureAlgorithm.pszObjId = "1.2.840.113549.1.1.11";
  FileTime = 0;
  SystemTimeAsFileTime = 0;
  *(_QWORD *)&pSignatureAlgorithm.Parameters.cbData = 0;
  pSignatureAlgorithm.Parameters.pbData = 0;
  pEndTime = 0;
  SystemTime = 0;
  pSubjectIssuerBlob = 0;
  pExtensions = 0;
  memset(&Block, 0, sizeof(Block));
  KeyProviderInfo = EncodeNameForCertificate(&pSubjectIssuerBlob.cbData, a4);
  if ( KeyProviderInfo >= 0 )
  {
    pExtensions.cExtension = a6;
    pExtensions.rgExtension = a5;
    IsKeyHandle = NCryptIsKeyHandle(a2);
    if ( !IsKeyHandle )
    {
      KeyProviderInfo = GetKeyProviderInfo(&Block, a2);
      if ( KeyProviderInfo < 0 )
        goto LABEL_13;
      Block.dwFlags |= 0x20u;
      Block.dwKeySpec = 1;
    }
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    FileTime = SystemTimeAsFileTime;
    v10 = *(_QWORD *)&SystemTimeAsFileTime - 864000000000LL;
    SystemTimeAsFileTime.dwLowDateTime -= 711573504;
    SystemTimeAsFileTime.dwHighDateTime = HIDWORD(v10);
    if ( !FileTimeToSystemTime(&SystemTimeAsFileTime, &SystemTime) )
      goto LABEL_6;
    v12 = *(_QWORD *)&FileTime + 157248000000000LL;
    FileTime.dwLowDateTime += 657358848;
    FileTime.dwHighDateTime = HIDWORD(v12);
    if ( !FileTimeToSystemTime(&FileTime, &pEndTime) )
      goto LABEL_6;
    p_Block = &Block;
    if ( IsKeyHandle )
      p_Block = 0;
    v14 = CertCreateSelfSignCertificate(
            a2,
            &pSubjectIssuerBlob,
            0,
            p_Block,
            &pSignatureAlgorithm,
            &SystemTime,
            &pEndTime,
            &pExtensions);
    *a1 = v14;
    if ( v14 )
    {
      KeyProviderInfo = 0;
    }
    else
    {
LABEL_6:
      LastError = GetLastError();
      KeyProviderInfo = LastError;
      if ( LastError > 0 )
        KeyProviderInfo = (unsigned __int16)LastError | 0x80070000;
    }
  }
LABEL_13:
  if ( pSubjectIssuerBlob.pbData )
    operator delete(pSubjectIssuerBlob.pbData);
  if ( Block.pwszContainerName )
    operator delete(Block.pwszContainerName);
  if ( Block.pwszProvName )
    operator delete(Block.pwszProvName);
  return (unsigned int)KeyProviderInfo;
}

```

## disassembly

```asm
0x18003fd08  push    rbp
0x18003fd0a  push    rbx
0x18003fd0b  push    rsi
0x18003fd0c  push    rdi
0x18003fd0d  push    r14
0x18003fd0f  lea     rbp, [rsp-27h]
0x18003fd14  sub     rsp, 0E0h
0x18003fd1b  mov     rax, cs:__security_cookie
0x18003fd22  xor     rax, rsp
0x18003fd25  mov     [rbp+47h+var_28], rax
0x18003fd29  mov     rsi, [rbp+47h+arg_20]
0x18003fd2d  lea     rax, a12840113549111; "1.2.840.113549.1.1.11"
0x18003fd34  xorps   xmm0, xmm0
0x18003fd37  mov     qword ptr [rcx], 0
0x18003fd3e  mov     rdi, rdx
0x18003fd41  mov     [rbp+47h+var_90.pszObjId], rax
0x18003fd45  mov     r14, rcx
0x18003fd48  mov     qword ptr [rbp+47h+FileTime.dwLowDateTime], 0
0x18003fd50  xorps   xmm1, xmm1
0x18003fd53  mov     qword ptr [rbp+47h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18003fd5b  mov     rdx, r9; unsigned __int16 *
0x18003fd5e  mov     qword ptr [rbp+47h+var_90.Parameters.cbData], 0
0x18003fd66  lea     rcx, [rbp+47h+pSubjectIssuerBlob]; pcbEncoded
0x18003fd6a  mov     [rbp+47h+var_90.Parameters.pbData], 0
0x18003fd72  movups  xmmword ptr [rbp+47h+var_48.wYear], xmm0
0x18003fd76  movups  xmmword ptr [rbp+47h+SystemTime.wYear], xmm0
0x18003fd7a  movups  xmmword ptr [rbp+47h+pSubjectIssuerBlob.cbData], xmm0
0x18003fd7e  movups  xmmword ptr [rbp+47h+var_B0.cExtension], xmm1
0x18003fd82  movups  xmmword ptr [rbp+47h+Block], xmm0
0x18003fd86  movups  [rbp+47h+var_68], xmm0
0x18003fd8a  movups  [rbp+47h+var_58], xmm0
0x18003fd8e  call    ?EncodeNameForCertificate@@YAJPEAU_CRYPTOAPI_BLOB@@PEBG@Z; EncodeNameForCertificate(_CRYPTOAPI_BLOB *,ushort const *)
0x18003fd93  mov     ebx, eax
0x18003fd95  test    eax, eax
0x18003fd97  js      loc_18003FEA8
0x18003fd9d  mov     eax, [rbp+47h+arg_28]
0x18003fda0  mov     rcx, rdi; hKey
0x18003fda3  mov     [rbp+47h+var_B0.cExtension], eax
0x18003fda6  mov     [rbp+47h+var_B0.rgExtension], rsi
0x18003fdaa  call    cs:__imp_NCryptIsKeyHandle
0x18003fdb0  mov     esi, eax
0x18003fdb2  test    eax, eax
0x18003fdb4  jnz     short loc_18003FDD7
0x18003fdb6  mov     rdx, rdi; unsigned __int64
0x18003fdb9  lea     rcx, [rbp+47h+Block]; struct _CRYPT_KEY_PROV_INFO *
0x18003fdbd  call    ?GetKeyProviderInfo@@YAJPEAU_CRYPT_KEY_PROV_INFO@@_K@Z; GetKeyProviderInfo(_CRYPT_KEY_PROV_INFO *,unsigned __int64)
0x18003fdc2  mov     ebx, eax
0x18003fdc4  test    eax, eax
0x18003fdc6  js      loc_18003FEA8
0x18003fdcc  or      dword ptr [rbp+47h+var_68+4], 20h
0x18003fdd0  mov     dword ptr [rbp+47h+var_58+8], 1
0x18003fdd7  lea     rcx, [rbp+47h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003fddb  call    cs:__imp_GetSystemTimeAsFileTime
0x18003fde1  mov     rax, qword ptr [rbp+47h+SystemTimeAsFileTime.dwLowDateTime]
0x18003fde5  lea     rdx, [rbp+47h+SystemTime]; lpSystemTime
0x18003fde9  mov     qword ptr [rbp+47h+FileTime.dwLowDateTime], rax
0x18003fded  mov     rcx, 0C92A69C000h
0x18003fdf7  sub     rax, rcx
0x18003fdfa  lea     rcx, [rbp+47h+SystemTimeAsFileTime]; lpFileTime
0x18003fdfe  mov     [rbp+47h+SystemTimeAsFileTime.dwLowDateTime], eax
0x18003fe01  shr     rax, 20h
0x18003fe05  mov     [rbp+47h+SystemTimeAsFileTime.dwHighDateTime], eax
0x18003fe08  call    cs:__imp_FileTimeToSystemTime
0x18003fe0e  test    eax, eax
0x18003fe10  jnz     short loc_18003FE2D
0x18003fe12  call    cs:__imp_GetLastError
0x18003fe18  mov     ebx, eax
0x18003fe1a  test    eax, eax
0x18003fe1c  jle     loc_18003FEA8
0x18003fe22  movzx   ebx, ax
0x18003fe25  or      ebx, 80070000h
0x18003fe2b  jmp     short loc_18003FEA8
0x18003fe2d  mov     rax, qword ptr [rbp+47h+FileTime.dwLowDateTime]
0x18003fe31  lea     rdx, [rbp+47h+var_48]; lpSystemTime
0x18003fe35  mov     rcx, 8F04272E8000h
0x18003fe3f  add     rax, rcx
0x18003fe42  lea     rcx, [rbp+47h+FileTime]; lpFileTime
0x18003fe46  mov     [rbp+47h+FileTime.dwLowDateTime], eax
0x18003fe49  shr     rax, 20h
0x18003fe4d  mov     [rbp+47h+FileTime.dwHighDateTime], eax
0x18003fe50  call    cs:__imp_FileTimeToSystemTime
0x18003fe56  test    eax, eax
0x18003fe58  jz      short loc_18003FE12
0x18003fe5a  xor     eax, eax
0x18003fe5c  lea     r9, [rbp+47h+Block]
0x18003fe60  test    esi, esi
0x18003fe62  lea     rdx, [rbp+47h+pSubjectIssuerBlob]; pSubjectIssuerBlob
0x18003fe66  mov     rcx, rdi; hCryptProvOrNCryptKey
0x18003fe69  cmovnz  r9, rax; pKeyProvInfo
0x18003fe6d  lea     rax, [rbp+47h+var_B0]
0x18003fe71  mov     [rsp+100h+pExtensions], rax; pExtensions
0x18003fe76  xor     r8d, r8d; dwFlags
0x18003fe79  lea     rax, [rbp+47h+var_48]
0x18003fe7d  mov     [rsp+100h+pEndTime], rax; pEndTime
0x18003fe82  lea     rax, [rbp+47h+SystemTime]
0x18003fe86  mov     [rsp+100h+pStartTime], rax; pStartTime
0x18003fe8b  lea     rax, [rbp+47h+var_90]
0x18003fe8f  mov     [rsp+100h+pSignatureAlgorithm], rax; pSignatureAlgorithm
0x18003fe94  call    cs:__imp_CertCreateSelfSignCertificate
0x18003fe9a  mov     [r14], rax
0x18003fe9d  test    rax, rax
0x18003fea0  jz      loc_18003FE12
0x18003fea6  xor     ebx, ebx
0x18003fea8  mov     rcx, [rbp+47h+pSubjectIssuerBlob.pbData]; Block
0x18003feac  test    rcx, rcx
0x18003feaf  jz      short loc_18003FEB6
0x18003feb1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003feb6  mov     rcx, [rbp+47h+Block]; Block
0x18003feba  test    rcx, rcx
0x18003febd  jz      short loc_18003FEC4
0x18003febf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003fec4  mov     rcx, [rbp+47h+Block+8]; Block
0x18003fec8  test    rcx, rcx
0x18003fecb  jz      short loc_18003FED2
0x18003fecd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003fed2  mov     eax, ebx
0x18003fed4  mov     rcx, [rbp+47h+var_28]
0x18003fed8  xor     rcx, rsp; StackCookie
0x18003fedb  call    __security_check_cookie
0x18003fee0  add     rsp, 0E0h
0x18003fee7  pop     r14
0x18003fee9  pop     rdi
0x18003feea  pop     rsi
0x18003feeb  pop     rbx
0x18003feec  pop     rbp
0x18003feed  retn
```
