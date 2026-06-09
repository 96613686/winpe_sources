# SIPolicyVerifySignedData

- ea: `0x180028178`
- end: `0x18002838d`
- name: `SIPolicyVerifySignedData`
- size: `533`
- prototype: `__int64 __fastcall(BYTE *pbSignedBlob, DWORD cbSignedBlob, __int64, __int64, __int64, _QWORD *, _DWORD *, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180016958`
- `0x180022db4`
- `0x180025f64`

## callees

- `0x180023d60`
- `0x1800279a8`
- `0x180027cc4`
- `0x180028178`
- `0x180028394`
- `0x1800284c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028204`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002822a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002822a`
- `CRYPT32!CryptMsgClose` at `0x18002824f`
- `CRYPT32!CryptMsgClose` at `0x18002824f`
- `CRYPT32!CryptMsgUpdate` at `0x180028287`
- `CRYPT32!CryptMsgUpdate` at `0x180028287`
- `CRYPT32!CertFreeCertificateContext` at `0x180028241`
- `CRYPT32!CertFreeCertificateContext` at `0x180028241`
- `CRYPT32!CryptMsgOpenToDecode` at `0x1800281f6`
- `CRYPT32!CryptMsgOpenToDecode` at `0x1800281f6`

## pseudocode

```c
__int64 __fastcall SIPolicyVerifySignedData(
        BYTE *pbSignedBlob,
        DWORD cbSignedBlob,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        _DWORD *a7,
        __int64 a8)
{
  void *v10; // r14
  const CERT_CONTEXT *v11; // rsi
  HCRYPTMSG v12; // rax
  void *v13; // rdi
  signed int LastError; // eax
  unsigned int v15; // ebx
  signed int v16; // ebx
  int CryptMessageParam; // eax
  __int64 v19; // rdx
  int DecodedMessageBlob; // eax
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int64 v23; // [rsp+38h] [rbp-59h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+40h] [rbp-51h] BYREF
  _BYTE *v25; // [rsp+48h] [rbp-49h]
  __int64 v26; // [rsp+50h] [rbp-41h]
  __int128 v27; // [rsp+58h] [rbp-39h] BYREF
  __int128 v28; // [rsp+68h] [rbp-29h]
  __int128 v29; // [rsp+78h] [rbp-19h]
  __int64 v30; // [rsp+88h] [rbp-9h]

  v25 = 0;
  v30 = 0;
  *a6 = 0;
  v26 = 0;
  LODWORD(v23) = 0;
  *a7 = 0;
  v10 = 0;
  v11 = 0;
  pCertContext = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v12 = CryptMsgOpenToDecode(0x10001u, 0, 0, 0, 0, 0);
  v13 = v12;
  if ( v12 && CryptMsgUpdate(v12, pbSignedBlob, cbSignedBlob, 1) )
  {
    CryptMessageParam = GetCryptMessageParam(v13, 1u, (__int64)&v23);
    v10 = v25;
    v16 = CryptMessageParam;
    if ( CryptMessageParam >= 0 )
    {
      if ( *v25 == 2 )
      {
        v16 = ValidateOid(a3, v19, v13);
        if ( v16 >= 0 )
        {
          DecodedMessageBlob = VerifySignatureGetDecodedMessageBlob(pbSignedBlob, cbSignedBlob, (__int64)&pCertContext);
          v11 = pCertContext;
          v16 = DecodedMessageBlob;
          if ( DecodedMessageBlob >= 0 )
          {
            v16 = ConvertCertCtxToChainInfo(v13, pCertContext);
            if ( v16 >= 0 )
            {
              *a6 = v26;
              *a7 = 0;
              if ( a8 )
              {
                v21 = v28;
                *(_OWORD *)a8 = v27;
                v22 = v29;
                *(_OWORD *)(a8 + 16) = v21;
                *(_QWORD *)&v21 = v30;
                *(_OWORD *)(a8 + 32) = v22;
                *(_QWORD *)(a8 + 48) = v21;
                v30 = 0;
                v27 = 0;
                v28 = 0;
                v29 = 0;
              }
            }
          }
        }
      }
      else
      {
        v16 = -1073740760;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
    v16 = v15 & 0xAFFFFFFF | 0x40000000;
  }
  LocalFree(v10);
  SIPolicyFreeSIChainInfo(&v27);
  if ( v11 )
    CertFreeCertificateContext(v11);
  if ( v13 )
    CryptMsgClose(v13);
  if ( v16 < 0 )
    return (unsigned int)-1073740760;
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180028178  mov     rax, rsp
0x18002817b  mov     [rax+8], rbx
0x18002817f  mov     [rax+20h], r9d
0x180028183  mov     [rax+18h], r8
0x180028187  push    rbp
0x180028188  push    rsi
0x180028189  push    rdi
0x18002818a  push    r12
0x18002818c  push    r13
0x18002818e  push    r14
0x180028190  push    r15
0x180028192  lea     rbp, [rax-3Fh]
0x180028196  sub     rsp, 90h
0x18002819d  mov     r13, [rbp+37h+arg_28]
0x1800281a1  xor     ebx, ebx
0x1800281a3  xorps   xmm0, xmm0
0x1800281a6  mov     [rsp+28h], rbx; pStreamInfo
0x1800281ab  xor     eax, eax
0x1800281ad  mov     [rbp+37h+var_80], rbx
0x1800281b1  mov     [rbp+37h+var_40], rax
0x1800281b5  mov     r15d, edx
0x1800281b8  mov     rax, [rbp+37h+arg_30]
0x1800281bc  mov     r12, rcx
0x1800281bf  mov     [r13+0], rbx
0x1800281c3  xor     r9d, r9d; hCryptProv
0x1800281c6  xor     r8d, r8d; dwMsgType
0x1800281c9  mov     [rbp+37h+var_78], rbx
0x1800281cd  xor     edx, edx; dwFlags
0x1800281cf  mov     dword ptr [rbp+37h+var_90], ebx
0x1800281d2  mov     ecx, 10001h; dwMsgEncodingType
0x1800281d7  mov     [rax], ebx
0x1800281d9  mov     r14d, ebx
0x1800281dc  mov     [rbp+37h+arg_18], ebx
0x1800281df  mov     esi, ebx
0x1800281e1  mov     [rbp+37h+pCertContext], rbx
0x1800281e5  movups  [rbp+37h+var_70], xmm0
0x1800281e9  mov     [rsp+0C0h+pRecipientInfo], rbx; pRecipientInfo
0x1800281ee  movups  [rbp+37h+var_60], xmm0
0x1800281f2  movups  [rbp+37h+var_50], xmm0
0x1800281f6  call    cs:__imp_CryptMsgOpenToDecode
0x1800281fc  mov     rdi, rax
0x1800281ff  test    rax, rax
0x180028202  jnz     short loc_180028278
0x180028204  call    cs:__imp_GetLastError
0x18002820a  mov     ebx, eax
0x18002820c  test    eax, eax
0x18002820e  jle     short loc_180028219
0x180028210  movzx   ebx, ax
0x180028213  or      ebx, 80070000h
0x180028219  btr     ebx, 1Ch
0x18002821d  bts     ebx, 1Eh
0x180028221  mov     r15d, 0C0000428h
0x180028227  mov     rcx, r14; hMem
0x18002822a  call    cs:__imp_LocalFree
0x180028230  lea     rcx, [rbp+37h+var_70]
0x180028234  call    SIPolicyFreeSIChainInfo
0x180028239  test    rsi, rsi
0x18002823c  jz      short loc_180028247
0x18002823e  mov     rcx, rsi; pCertContext
0x180028241  call    cs:__imp_CertFreeCertificateContext
0x180028247  test    rdi, rdi
0x18002824a  jz      short loc_180028255
0x18002824c  mov     rcx, rdi; hCryptMsg
0x18002824f  call    cs:__imp_CryptMsgClose
0x180028255  test    ebx, ebx
0x180028257  cmovs   ebx, r15d
0x18002825b  mov     eax, ebx
0x18002825d  mov     rbx, [rsp+0C0h+arg_0]
0x180028265  add     rsp, 90h
0x18002826c  pop     r15
0x18002826e  pop     r14
0x180028270  pop     r13
0x180028272  pop     r12
0x180028274  pop     rdi
0x180028275  pop     rsi
0x180028276  pop     rbp
0x180028277  retn
0x180028278  mov     r9d, 1; fFinal
0x18002827e  mov     r8d, r15d; cbData
0x180028281  mov     rdx, r12; pbData
0x180028284  mov     rcx, rdi; hCryptMsg
0x180028287  call    cs:__imp_CryptMsgUpdate
0x18002828d  test    eax, eax
0x18002828f  jz      loc_180028204
0x180028295  lea     rax, [rbp+37h+var_90]
0x180028299  mov     edx, 1; dwParamType
0x18002829e  lea     r9, [rbp+37h+var_80]
0x1800282a2  mov     [rsp+0C0h+pRecipientInfo], rax; __int64
0x1800282a7  mov     rcx, rdi; hCryptMsg
0x1800282aa  call    GetCryptMessageParam
0x1800282af  mov     r14, [rbp+37h+var_80]
0x1800282b3  mov     ebx, eax
0x1800282b5  test    eax, eax
0x1800282b7  js      loc_180028221
0x1800282bd  cmp     byte ptr [r14], 2
0x1800282c1  jz      short loc_1800282D1
0x1800282c3  mov     r15d, 0C0000428h
0x1800282c9  mov     ebx, r15d
0x1800282cc  jmp     loc_180028227
0x1800282d1  mov     rcx, [rbp+37h+arg_10]
0x1800282d5  mov     r8, rdi
0x1800282d8  call    ValidateOid
0x1800282dd  mov     ebx, eax
0x1800282df  test    eax, eax
0x1800282e1  js      loc_180028221
0x1800282e7  lea     rax, [rbp+37h+pCertContext]
0x1800282eb  mov     edx, r15d; cbSignedBlob
0x1800282ee  lea     r9, [rbp+37h+arg_18]
0x1800282f2  mov     [rsp+0C0h+pRecipientInfo], rax; __int64
0x1800282f7  lea     r8, [rbp+37h+var_78]
0x1800282fb  mov     rcx, r12; pbSignedBlob
0x1800282fe  call    VerifySignatureGetDecodedMessageBlob
0x180028303  mov     rsi, [rbp+37h+pCertContext]
0x180028307  mov     ebx, eax
0x180028309  test    eax, eax
0x18002830b  js      loc_180028221
0x180028311  mov     r8, [rbp+37h+arg_20]
0x180028315  lea     r9, [rbp+37h+var_70]
0x180028319  mov     rdx, rsi; pCertContext
0x18002831c  mov     rcx, rdi; pvPara
0x18002831f  call    ConvertCertCtxToChainInfo
0x180028324  mov     ebx, eax
0x180028326  test    eax, eax
0x180028328  js      loc_180028221
0x18002832e  mov     rax, [rbp+37h+var_78]
0x180028332  mov     r15d, 0C0000428h
0x180028338  mov     rcx, [rbp+37h+arg_30]
0x18002833c  mov     [r13+0], rax
0x180028340  mov     eax, [rbp+37h+arg_18]
0x180028343  mov     [rcx], eax
0x180028345  mov     rax, [rbp+37h+arg_38]
0x180028349  test    rax, rax
0x18002834c  jz      loc_180028227
0x180028352  movups  xmm0, [rbp+37h+var_70]
0x180028356  movups  xmm1, [rbp+37h+var_60]
0x18002835a  movups  xmmword ptr [rax], xmm0
0x18002835d  movups  xmm0, [rbp+37h+var_50]
0x180028361  movups  xmmword ptr [rax+10h], xmm1
0x180028365  movsd   xmm1, [rbp+37h+var_40]
0x18002836a  movups  xmmword ptr [rax+20h], xmm0
0x18002836e  xorps   xmm0, xmm0
0x180028371  movsd   qword ptr [rax+30h], xmm1
0x180028376  xor     eax, eax
0x180028378  mov     [rbp+37h+var_40], rax
0x18002837c  movups  [rbp+37h+var_70], xmm0
0x180028380  movups  [rbp+37h+var_60], xmm0
0x180028384  movups  [rbp+37h+var_50], xmm0
0x180028388  jmp     loc_180028227
```
