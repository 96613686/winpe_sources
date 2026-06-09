# CNLLexInterface::CheckSeal(void)

- ea: `0x180060a90`
- end: `0x180060ccb`
- name: `?CheckSeal@CNLLexInterface@@QEBAXXZ`
- size: `571`
- prototype: `void __fastcall(CNLLexInterface *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180060e6c`

## callees

- `0x180035640`
- `0x18003ed6c`
- `0x180060a90`
- `0x18009e2b6`
- `0x18009e300`
- `0x1800b0010`

## import_xrefs

- `CRYPT32!CertOpenSystemStoreW` at `0x180060b0d`
- `CRYPT32!CertOpenSystemStoreW` at `0x180060b0d`
- `CRYPT32!CertCloseStore` at `0x180060c85`
- `CRYPT32!CertCloseStore` at `0x180060c85`
- `CRYPT32!CertFindCertificateInStore` at `0x180060c6e`
- `CRYPT32!CertFindCertificateInStore` at `0x180060c6e`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180060b69`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180060b69`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180060c15`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180060c15`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDecrypt` at `0x180060bf4`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDecrypt` at `0x180060bf4`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180060c49`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180060c49`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetUserKey` at `0x180060b84`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetUserKey` at `0x180060b99`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetUserKey` at `0x180060b84`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetUserKey` at `0x180060b99`

## pseudocode

```c
void __fastcall CNLLexInterface::CheckSeal(CNLLexInterface *this)
{
  __int64 v2; // rcx
  bool v3; // zf
  int v4; // eax
  HCERTSTORE v5; // rsi
  const CERT_CONTEXT *i; // rax
  _OWORD *v7; // rax
  __int128 v8; // xmm0
  const CERT_CONTEXT *v9; // rbx
  DWORD pdwDataLen; // [rsp+30h] [rbp-69h] BYREF
  DWORD pcbData; // [rsp+34h] [rbp-65h] BYREF
  int pvFindPara; // [rsp+38h] [rbp-61h] BYREF
  BOOL pfCallerFreeProvOrNCryptKey; // [rsp+3Ch] [rbp-5Dh] BYREF
  HCRYPTPROV_OR_NCRYPT_KEY_HANDLE phCryptProvOrNCryptKey; // [rsp+40h] [rbp-59h] BYREF
  HCRYPTKEY phUserKey; // [rsp+48h] [rbp-51h] BYREF
  BYTE pbData[16]; // [rsp+50h] [rbp-49h] BYREF
  __int128 v17; // [rsp+60h] [rbp-39h]
  __int128 v18; // [rsp+70h] [rbp-29h]
  _BYTE pvData[64]; // [rsp+80h] [rbp-19h] BYREF
  const void *retaddr; // [rsp+F8h] [rbp+5Fh]

  v2 = *((_QWORD *)this + 3);
  if ( v2
    && (*(unsigned __int8 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v2 + 256LL))(
         v2,
         L"bad38fed4a2d43dab43e8c0bead5f8ed") )
  {
    v3 = *(_WORD *)this == 19;
    pvFindPara = 0;
    if ( !v3 || (v4 = *((_DWORD *)this + 2)) == 0 )
      v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 56LL))(*((_QWORD *)this + 3));
    pvFindPara = v4;
    v5 = CertOpenSystemStoreW(0, L"MY");
    for ( i = CertFindCertificateInStore(v5, 0x10001u, 0, 0x90000u, &pvFindPara, 0);
          ;
          i = CertFindCertificateInStore(v5, 0x10001u, 0, 0x90000u, &pvFindPara, v9) )
    {
      v9 = i;
      if ( !i )
        break;
      phCryptProvOrNCryptKey = 0;
      pdwDataLen = 0;
      pcbData = 0;
      phUserKey = 0;
      pfCallerFreeProvOrNCryptKey = 0;
      if ( CryptAcquireCertificatePrivateKey(
             i,
             0x42u,
             0,
             &phCryptProvOrNCryptKey,
             &pdwDataLen,
             &pfCallerFreeProvOrNCryptKey)
        && (CryptGetUserKey(phCryptProvOrNCryptKey, 2u, &phUserKey)
         || CryptGetUserKey(phCryptProvOrNCryptKey, 1u, &phUserKey)) )
      {
        v7 = (_OWORD *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 64LL))(*((_QWORD *)this + 3));
        *(_OWORD *)pbData = *v7;
        v17 = v7[1];
        v8 = v7[2];
        pdwDataLen = 48;
        v18 = v8;
        if ( CryptDecrypt(phUserKey, 0, 1, 0, pbData, &pdwDataLen) )
        {
          pcbData = 48;
          if ( CertGetCertificateContextProperty(v9, 3u, pvData, &pcbData) )
          {
            if ( pdwDataLen == pcbData && !memcmp_0(pvData, pbData, pdwDataLen) )
              break;
          }
        }
      }
      else if ( pfCallerFreeProvOrNCryptKey )
      {
        CryptReleaseContext(phCryptProvOrNCryptKey, 0);
      }
    }
    CertCloseStore(v5, 0);
    if ( !v9 )
    {
      CNLException::CNLException((CNLException *)pvData, 3241218064LL, retaddr);
      throw (CNLException *)pvData;
    }
  }
}

```

## disassembly

```asm
0x180060a90  push    rbp
0x180060a92  push    rbx
0x180060a93  push    rsi
0x180060a94  push    rdi
0x180060a95  lea     rbp, [rsp-3Fh]
0x180060a9a  sub     rsp, 0D8h
0x180060aa1  mov     rax, cs:__security_cookie
0x180060aa8  xor     rax, rsp
0x180060aab  mov     [rbp+57h+var_30], rax
0x180060aaf  mov     rdi, rcx
0x180060ab2  mov     rcx, [rcx+18h]
0x180060ab6  test    rcx, rcx
0x180060ab9  jz      loc_180060CB3
0x180060abf  mov     rax, [rcx]
0x180060ac2  lea     rdx, aBad38fed4a2d43; "bad38fed4a2d43dab43e8c0bead5f8ed"
0x180060ac9  mov     rax, [rax+100h]
0x180060ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060ad5  test    al, al
0x180060ad7  jz      loc_180060CB3
0x180060add  cmp     word ptr [rdi], 13h
0x180060ae1  mov     [rbp+57h+pvFindPara], 0
0x180060ae8  jnz     short loc_180060AF1
0x180060aea  mov     eax, [rdi+8]
0x180060aed  test    eax, eax
0x180060aef  jnz     short loc_180060B01
0x180060af1  mov     rcx, [rdi+18h]
0x180060af5  mov     rax, [rcx]
0x180060af8  mov     rax, [rax+38h]
0x180060afc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060b01  lea     rdx, szSubsystemProtocol; "MY"
0x180060b08  mov     [rbp+57h+pvFindPara], eax
0x180060b0b  xor     ecx, ecx; hProv
0x180060b0d  call    cs:__imp_CertOpenSystemStoreW
0x180060b13  mov     rsi, rax
0x180060b16  mov     [rsp+0F0h+pfCallerFreeProvOrNCryptKey], 0
0x180060b1f  jmp     loc_180060C54
0x180060b24  xor     r8d, r8d; pvParameters
0x180060b27  mov     [rbp+57h+phCryptProvOrNCryptKey], 0
0x180060b2f  lea     rax, [rbp+57h+var_B4]
0x180060b33  mov     [rbp+57h+pdwDataLen], 0
0x180060b3a  mov     [rsp+0F0h+pfCallerFreeProvOrNCryptKey], rax; pfCallerFreeProvOrNCryptKey
0x180060b3f  lea     r9, [rbp+57h+phCryptProvOrNCryptKey]; phCryptProvOrNCryptKey
0x180060b43  lea     rax, [rbp+57h+pdwDataLen]
0x180060b47  mov     [rbp+57h+pcbData], 0
0x180060b4e  lea     edx, [r8+42h]; dwFlags
0x180060b52  mov     [rbp+57h+phUserKey], 0
0x180060b5a  mov     rcx, rbx; pCert
0x180060b5d  mov     [rbp+57h+var_B4], 0
0x180060b64  mov     [rsp+0F0h+pdwKeySpec], rax; pdwKeySpec
0x180060b69  call    cs:__imp_CryptAcquireCertificatePrivateKey
0x180060b6f  test    eax, eax
0x180060b71  jz      loc_180060C3D
0x180060b77  mov     rcx, [rbp+57h+phCryptProvOrNCryptKey]; hProv
0x180060b7b  lea     r8, [rbp+57h+phUserKey]; phUserKey
0x180060b7f  mov     edx, 2; dwKeySpec
0x180060b84  call    cs:__imp_CryptGetUserKey
0x180060b8a  test    eax, eax
0x180060b8c  jnz     short loc_180060BA7
0x180060b8e  mov     rcx, [rbp+57h+phCryptProvOrNCryptKey]; hProv
0x180060b92  lea     r8, [rbp+57h+phUserKey]; phUserKey
0x180060b96  lea     edx, [rax+1]; dwKeySpec
0x180060b99  call    cs:__imp_CryptGetUserKey
0x180060b9f  test    eax, eax
0x180060ba1  jz      loc_180060C3D
0x180060ba7  mov     rcx, [rdi+18h]
0x180060bab  mov     rax, [rcx]
0x180060bae  mov     rax, [rax+40h]
0x180060bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060bb7  mov     rcx, [rbp+57h+phUserKey]; hKey
0x180060bbb  xor     r9d, r9d; dwFlags
0x180060bbe  xor     edx, edx; hHash
0x180060bc0  movups  xmm0, xmmword ptr [rax]
0x180060bc3  lea     r8d, [r9+1]; Final
0x180060bc7  movups  xmmword ptr [rbp+57h+pbData], xmm0
0x180060bcb  movups  xmm1, xmmword ptr [rax+10h]
0x180060bcf  movups  [rbp+57h+var_90], xmm1
0x180060bd3  movups  xmm0, xmmword ptr [rax+20h]
0x180060bd7  lea     rax, [rbp+57h+pdwDataLen]
0x180060bdb  mov     [rbp+57h+pdwDataLen], 30h ; '0'
0x180060be2  mov     [rsp+0F0h+pfCallerFreeProvOrNCryptKey], rax; pdwDataLen
0x180060be7  lea     rax, [rbp+57h+pbData]
0x180060beb  mov     [rsp+0F0h+pdwKeySpec], rax; pbData
0x180060bf0  movups  [rbp+57h+var_80], xmm0
0x180060bf4  call    cs:__imp_CryptDecrypt
0x180060bfa  test    eax, eax
0x180060bfc  jz      short loc_180060C4F
0x180060bfe  lea     r9, [rbp+57h+pcbData]; pcbData
0x180060c02  mov     [rbp+57h+pcbData], 30h ; '0'
0x180060c09  lea     r8, [rbp+57h+pvData]; pvData
0x180060c0d  mov     edx, 3; dwPropId
0x180060c12  mov     rcx, rbx; pCertContext
0x180060c15  call    cs:__imp_CertGetCertificateContextProperty
0x180060c1b  test    eax, eax
0x180060c1d  jz      short loc_180060C4F
0x180060c1f  mov     eax, [rbp+57h+pdwDataLen]
0x180060c22  cmp     eax, [rbp+57h+pcbData]
0x180060c25  jnz     short loc_180060C4F
0x180060c27  mov     r8d, eax; Size
0x180060c2a  lea     rdx, [rbp+57h+pbData]; Buf2
0x180060c2e  lea     rcx, [rbp+57h+pvData]; Buf1
0x180060c32  call    memcmp_0
0x180060c37  test    eax, eax
0x180060c39  jz      short loc_180060C80
0x180060c3b  jmp     short loc_180060C4F
0x180060c3d  cmp     [rbp+57h+var_B4], 0
0x180060c41  jz      short loc_180060C4F
0x180060c43  mov     rcx, [rbp+57h+phCryptProvOrNCryptKey]; hProv
0x180060c47  xor     edx, edx; dwFlags
0x180060c49  call    cs:__imp_CryptReleaseContext
0x180060c4f  mov     [rsp+0F0h+pfCallerFreeProvOrNCryptKey], rbx; pPrevCertContext
0x180060c54  lea     rax, [rbp+57h+pvFindPara]
0x180060c58  mov     r9d, 90000h; dwFindType
0x180060c5e  xor     r8d, r8d; dwFindFlags
0x180060c61  mov     [rsp+0F0h+pdwKeySpec], rax; pvFindPara
0x180060c66  mov     edx, 10001h; dwCertEncodingType
0x180060c6b  mov     rcx, rsi; hCertStore
0x180060c6e  call    cs:__imp_CertFindCertificateInStore
0x180060c74  mov     rbx, rax
0x180060c77  test    rax, rax
0x180060c7a  jnz     loc_180060B24
0x180060c80  xor     edx, edx; dwFlags
0x180060c82  mov     rcx, rsi; hCertStore
0x180060c85  call    cs:__imp_CertCloseStore
0x180060c8b  test    rbx, rbx
0x180060c8e  jnz     short loc_180060CB3
0x180060c90  mov     r8, [rbp+5Fh]; void *
0x180060c94  lea     rcx, [rbp+57h+pvData]; this
0x180060c98  mov     edx, 0C1311010h; int
0x180060c9d  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180060ca2  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180060ca9  lea     rcx, [rbp+57h+pvData]; pExceptionObject
0x180060cad  call    _CxxThrowException_0
0x180060cb3  mov     rcx, [rbp+57h+var_30]
0x180060cb7  xor     rcx, rsp; StackCookie
0x180060cba  call    __security_check_cookie
0x180060cbf  add     rsp, 0D8h
0x180060cc6  pop     rdi
0x180060cc7  pop     rsi
0x180060cc8  pop     rbx
0x180060cc9  pop     rbp
0x180060cca  retn
```
