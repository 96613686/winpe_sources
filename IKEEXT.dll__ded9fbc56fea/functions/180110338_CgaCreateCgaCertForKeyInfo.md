# CgaCreateCgaCertForKeyInfo

- ea: `0x180110338`
- end: `0x1801104b7`
- name: `CgaCreateCgaCertForKeyInfo`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18010fdd8`

## callees

- `0x1800037c4`
- `0x1800061ec`
- `0x180050850`
- `0x180110338`
- `0x180110770`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180110448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180110448`
- `RPCRT4!UuidToStringW` at `0x1801103d9`
- `RPCRT4!UuidToStringW` at `0x1801103d9`
- `RPCRT4!RpcStringFreeW` at `0x180110481`
- `RPCRT4!RpcStringFreeW` at `0x180110481`
- `RPCRT4!UuidCreate` at `0x1801103bb`
- `RPCRT4!UuidCreate` at `0x1801103bb`
- `CRYPT32!CertCreateSelfSignCertificate` at `0x18011043a`
- `CRYPT32!CertCreateSelfSignCertificate` at `0x18011043a`

## string_xrefs

- `0x1801103c5`: `UuidCreate`
- `0x18011044e`: `CertCreateSelfSignCertificate`

## pseudocode

```c
__int64 __fastcall CgaCreateCgaCertForKeyInfo(WCHAR *a1, WCHAR *a2, DWORD a3, PCCERT_CONTEXT *a4)
{
  __int64 CgaCertSubject; // rax
  unsigned int v9; // ebx
  DWORD LastError; // eax
  __int64 v11; // rcx
  const char *v12; // rdx
  PCCERT_CONTEXT v13; // rax
  __int64 result; // rax
  RPC_WSTR StringUuid; // [rsp+40h] [rbp-39h] BYREF
  struct _CRYPTOAPI_BLOB pSubjectIssuerBlob; // [rsp+48h] [rbp-31h] BYREF
  _CRYPT_KEY_PROV_INFO pKeyProvInfo; // [rsp+58h] [rbp-21h] BYREF
  UUID Uuid; // [rsp+88h] [rbp+Fh] BYREF

  StringUuid = 0;
  *a4 = 0;
  pSubjectIssuerBlob = 0;
  memset(&pKeyProvInfo, 0, sizeof(pKeyProvInfo));
  Uuid = 0;
  CgaCertSubject = CgaGetCgaCertSubject(&pSubjectIssuerBlob);
  v9 = CgaCertSubject;
  if ( !CgaCertSubject )
  {
    if ( a1 )
    {
      pKeyProvInfo.pwszContainerName = a1;
      pKeyProvInfo.pwszProvName = a2;
      pKeyProvInfo.dwProvType = a3;
LABEL_9:
      pKeyProvInfo.dwFlags = 96;
      pKeyProvInfo.dwKeySpec = 2;
      v13 = CertCreateSelfSignCertificate(0, &pSubjectIssuerBlob, 0, &pKeyProvInfo, 0, 0, 0, 0);
      *a4 = v13;
      if ( v13 )
        goto LABEL_12;
      LastError = GetLastError();
      v12 = "CertCreateSelfSignCertificate";
      goto LABEL_11;
    }
    LastError = UuidCreate(&Uuid);
    if ( LastError )
    {
      v12 = "UuidCreate";
    }
    else
    {
      LastError = UuidToStringW(&Uuid, &StringUuid);
      if ( !LastError )
      {
        pKeyProvInfo.pwszContainerName = StringUuid;
        pKeyProvInfo.dwProvType = 1;
        goto LABEL_9;
      }
      v12 = "UuidToStringW";
    }
LABEL_11:
    v9 = WfpReportSysErrorAsWinError(v11, v12, LastError, 1);
  }
LABEL_12:
  if ( pSubjectIssuerBlob.pbData )
    WfpMemFree(&pSubjectIssuerBlob.pbData);
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  result = (unsigned __int16)v9;
  if ( (v9 & 0x1FFF0000) != 0x70000 )
    return v9;
  return result;
}

```

## disassembly

```asm
0x180110338  push    rbp
0x18011033a  push    rbx
0x18011033b  push    rsi
0x18011033c  push    rdi
0x18011033d  push    r14
0x18011033f  push    r15
0x180110341  lea     rbp, [rsp-2Fh]
0x180110346  sub     rsp, 0A8h
0x18011034d  mov     rax, cs:__security_cookie
0x180110354  xor     rax, rsp
0x180110357  mov     [rbp+57h+var_38], rax
0x18011035b  xorps   xmm1, xmm1
0x18011035e  mov     [rbp+57h+StringUuid], 0
0x180110366  xorps   xmm0, xmm0
0x180110369  mov     qword ptr [r9], 0
0x180110370  mov     rdi, rcx
0x180110373  mov     r15, r9
0x180110376  lea     rcx, [rbp+57h+pSubjectIssuerBlob]
0x18011037a  mov     esi, r8d
0x18011037d  movups  xmmword ptr [rbp+57h+pSubjectIssuerBlob.cbData], xmm0
0x180110381  mov     r14, rdx
0x180110384  movups  xmmword ptr [rbp+57h+pKeyProvInfo.pwszContainerName], xmm1
0x180110388  movups  xmmword ptr [rbp+57h+pKeyProvInfo.dwProvType], xmm1
0x18011038c  movups  xmmword ptr [rbp+57h+pKeyProvInfo.rgProvParam], xmm1
0x180110390  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x180110394  call    CgaGetCgaCertSubject
0x180110399  mov     rbx, rax
0x18011039c  test    rax, rax
0x18011039f  jnz     loc_180110466
0x1801103a5  test    rdi, rdi
0x1801103a8  jz      short loc_1801103B7
0x1801103aa  mov     [rbp+57h+pKeyProvInfo.pwszContainerName], rdi
0x1801103ae  mov     [rbp+57h+pKeyProvInfo.pwszProvName], r14
0x1801103b2  mov     [rbp+57h+pKeyProvInfo.dwProvType], esi
0x1801103b5  jmp     short loc_1801103FB
0x1801103b7  lea     rcx, [rbp+57h+Uuid]; Uuid
0x1801103bb  call    cs:__imp_UuidCreate
0x1801103c1  test    eax, eax
0x1801103c3  jz      short loc_1801103D1
0x1801103c5  lea     rdx, aUuidcreate; "UuidCreate"
0x1801103cc  jmp     loc_180110455
0x1801103d1  lea     rdx, [rbp+57h+StringUuid]; StringUuid
0x1801103d5  lea     rcx, [rbp+57h+Uuid]; Uuid
0x1801103d9  call    cs:__imp_UuidToStringW
0x1801103df  test    eax, eax
0x1801103e1  jz      short loc_1801103EC
0x1801103e3  lea     rdx, aUuidtostringw; "UuidToStringW"
0x1801103ea  jmp     short loc_180110455
0x1801103ec  mov     rax, [rbp+57h+StringUuid]
0x1801103f0  mov     [rbp+57h+pKeyProvInfo.pwszContainerName], rax
0x1801103f4  mov     [rbp+57h+pKeyProvInfo.dwProvType], 1
0x1801103fb  mov     [rsp+0D0h+pExtensions], 0; pExtensions
0x180110404  lea     r9, [rbp+57h+pKeyProvInfo]; pKeyProvInfo
0x180110408  mov     [rsp+0D0h+pEndTime], 0; pEndTime
0x180110411  lea     rdx, [rbp+57h+pSubjectIssuerBlob]; pSubjectIssuerBlob
0x180110415  mov     [rsp+0D0h+pStartTime], 0; pStartTime
0x18011041e  xor     r8d, r8d; dwFlags
0x180110421  xor     ecx, ecx; hCryptProvOrNCryptKey
0x180110423  mov     [rsp+0D0h+pSignatureAlgorithm], 0; pSignatureAlgorithm
0x18011042c  mov     [rbp+57h+pKeyProvInfo.dwFlags], 60h ; '`'
0x180110433  mov     [rbp+57h+pKeyProvInfo.dwKeySpec], 2
0x18011043a  call    cs:__imp_CertCreateSelfSignCertificate
0x180110440  mov     [r15], rax
0x180110443  test    rax, rax
0x180110446  jnz     short loc_180110466
0x180110448  call    cs:__imp_GetLastError
0x18011044e  lea     rdx, aCertcreateself_0; "CertCreateSelfSignCertificate"
0x180110455  mov     r9d, 1
0x18011045b  mov     r8d, eax
0x18011045e  call    WfpReportSysErrorAsWinError
0x180110463  mov     rbx, rax
0x180110466  cmp     [rbp+57h+pSubjectIssuerBlob.pbData], 0
0x18011046b  jz      short loc_180110476
0x18011046d  lea     rcx, [rbp+57h+pSubjectIssuerBlob.pbData]
0x180110471  call    WfpMemFree
0x180110476  cmp     [rbp+57h+StringUuid], 0
0x18011047b  jz      short loc_180110487
0x18011047d  lea     rcx, [rbp+57h+StringUuid]; String
0x180110481  call    cs:__imp_RpcStringFreeW
0x180110487  mov     ecx, ebx
0x180110489  movzx   eax, bx
0x18011048c  and     ecx, 1FFF0000h
0x180110492  cmp     ecx, 70000h
0x180110498  cmovnz  eax, ebx
0x18011049b  mov     rcx, [rbp+57h+var_38]
0x18011049f  xor     rcx, rsp; StackCookie
0x1801104a2  call    __security_check_cookie
0x1801104a7  add     rsp, 0A8h
0x1801104ae  pop     r15
0x1801104b0  pop     r14
0x1801104b2  pop     rdi
0x1801104b3  pop     rsi
0x1801104b4  pop     rbx
0x1801104b5  pop     rbp
0x1801104b6  retn
```
