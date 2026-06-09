# ScHelperCMSSignMessage(_CERT_CONTEXT const *,_CRYPT_ALGORITHM_IDENTIFIER *,uchar *,ulong,int,char *,_CERT_CONTEXT const * *,ulong,uchar * *,ulong *)

- ea: `0x18006d958`
- end: `0x18006dccf`
- name: `?ScHelperCMSSignMessage@@YAHPEBU_CERT_CONTEXT@@PEAU_CRYPT_ALGORITHM_IDENTIFIER@@PEAEKHPEADPEAPEBU1@KPEAPEAEPEAK@Z`
- size: `887`
- prototype: `__int64 __usercall@<rax>(PCCERT_CONTEXT pCert@<rcx>, struct _CRYPT_ALGORITHM_IDENTIFIER *@<rdx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, int, LPSTR, const struct _CERT_CONTEXT **, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18006e520`

## callees

- `0x180002ad0`
- `0x180003908`
- `0x18006d958`
- `0x18006e1e8`
- `0x180071868`
- `0x180099be0`
- `0x180099c40`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006da45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006da45`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006da3d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006daa2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006da3d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006daa2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006dc7f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006dc7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006da92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006da92`
- `CRYPT32!CryptMsgGetParam` at `0x18006dc6c`
- `CRYPT32!CryptMsgGetParam` at `0x18006dca6`
- `CRYPT32!CryptMsgGetParam` at `0x18006dc6c`
- `CRYPT32!CryptMsgGetParam` at `0x18006dca6`
- `CRYPT32!CryptMsgOpenToEncode` at `0x18006dc1f`
- `CRYPT32!CryptMsgOpenToEncode` at `0x18006dc1f`
- `CRYPT32!CryptMsgUpdate` at `0x18006dc3f`
- `CRYPT32!CryptMsgUpdate` at `0x18006dc3f`
- `CRYPT32!CryptMsgClose` at `0x18006da84`
- `CRYPT32!CryptMsgClose` at `0x18006da84`

## pseudocode

```c
__int64 __fastcall ScHelperCMSSignMessage(
        PCCERT_CONTEXT pCert,
        struct _CRYPT_ALGORITHM_IDENTIFIER *a2,
        unsigned __int8 *a3,
        DWORD a4,
        int a5,
        LPSTR pszInnerContentObjID,
        const struct _CERT_CONTEXT **a7,
        unsigned int a8,
        unsigned __int8 **a9,
        unsigned int *a10)
{
  void *v12; // r15
  const char *pszObjId; // rcx
  unsigned __int8 *v14; // r14
  __int128 v15; // xmm0
  BYTE *v16; // xmm1_8
  unsigned int v17; // esi
  DWORD LastError; // ebx
  DWORD *p_pcbData; // rbx
  unsigned __int64 v21; // rdi
  unsigned __int64 v22; // rcx
  __int64 v23; // rcx
  unsigned __int64 v24; // rcx
  void *v25; // rsp
  void *v26; // rsp
  DWORD *v27; // rax
  unsigned int v28; // r9d
  __int64 v29; // r8
  __int64 v30; // rdx
  const struct _CERT_CONTEXT *v31; // rax
  HCRYPTMSG v32; // rax
  BOOL v33; // ebx
  DWORD v34; // eax
  __int64 v35; // [rsp+0h] [rbp-30h] BYREF
  DWORD pcbData; // [rsp+30h] [rbp+0h] BYREF
  DWORD dwErrCode; // [rsp+34h] [rbp+4h] BYREF
  DWORD cbData; // [rsp+38h] [rbp+8h] BYREF
  __int128 v39; // [rsp+40h] [rbp+10h] BYREF
  __int128 pvMsgEncodeInfo; // [rsp+50h] [rbp+20h] BYREF
  __int128 v41; // [rsp+60h] [rbp+30h]
  __int128 v42; // [rsp+70h] [rbp+40h]
  BYTE *pbData; // [rsp+80h] [rbp+50h]
  int v44; // [rsp+90h] [rbp+60h] BYREF
  PCERT_INFO pCertInfo; // [rsp+98h] [rbp+68h]
  __int128 v46; // [rsp+B0h] [rbp+80h]
  BYTE *v47; // [rsp+C0h] [rbp+90h]

  pbData = a3;
  cbData = a4;
  v12 = 0;
  pvMsgEncodeInfo = 0;
  v41 = 0;
  v42 = 0;
  memset_0(&v44, 0, 0x60u);
  pszObjId = a2->pszObjId;
  dwErrCode = 0;
  pcbData = 0;
  v39 = 0;
  v14 = 0;
  strncmp_0(pszObjId, "1.3.14.3.2.26", 0xEu);
  v44 = 96;
  *a9 = 0;
  *a10 = 0;
  v15 = *(_OWORD *)&a2->pszObjId;
  pCertInfo = pCert->pCertInfo;
  v16 = a2->Parameters.pbData;
  v46 = v15;
  v47 = v16;
  if ( (int)ScHelperCryptAcquireCertificatePrivateKey(pCert, (__int64)&dwErrCode) >= 0 )
  {
    *(_QWORD *)&pvMsgEncodeInfo = 0x100000030LL;
    v17 = 1;
    *((_QWORD *)&pvMsgEncodeInfo + 1) = &v44;
    if ( a8 )
    {
      p_pcbData = 0;
      v21 = 16LL * a8;
      if ( !v21 )
        goto LABEL_43;
      if ( v21 > g_ulMaxStackAllocSize )
        goto LABEL_43;
      v22 = v21 + g_ulAdditionalProbeSize + 8;
      if ( v22 < v21 || !(unsigned int)VerifyStackAvailable(v22) )
        goto LABEL_43;
      v23 = v21 + 23;
      if ( v21 + 23 <= v21 + 8 )
        v23 = 0xFFFFFFFFFFFFFF0LL;
      v24 = v23 & 0xFFFFFFFFFFFFFFF0uLL;
      v25 = alloca(v24);
      v26 = alloca(v24);
      p_pcbData = &pcbData;
      if ( &v35 == (__int64 *)-48LL || (pcbData = 1801679955, (p_pcbData = &cbData) == 0) )
      {
LABEL_43:
        if ( v21 + 8 >= v21 )
        {
          v27 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
          p_pcbData = v27;
          if ( v27 )
          {
            *v27 = 1885431112;
            p_pcbData = v27 + 2;
          }
        }
      }
      *((_QWORD *)&v41 + 1) = p_pcbData;
      if ( !p_pcbData )
        goto LABEL_3;
      v28 = 0;
      v29 = 0;
      while ( 1 )
      {
        v30 = 2 * v29;
        ++v28;
        *(_QWORD *)&p_pcbData[2 * v30 + 2] = a7[v29]->pbCertEncoded;
        v31 = a7[v29++];
        *(_DWORD *)(*((_QWORD *)&v41 + 1) + 8 * v30) = v31->cbCertEncoded;
        if ( v28 >= a8 )
          break;
        p_pcbData = (DWORD *)*((_QWORD *)&v41 + 1);
      }
      LODWORD(v41) = a8;
    }
    else
    {
      LODWORD(v39) = pCert->cbCertEncoded;
      *((_QWORD *)&v39 + 1) = pCert->pbCertEncoded;
      *((_QWORD *)&v41 + 1) = &v39;
      LODWORD(v41) = 1;
    }
    v32 = CryptMsgOpenToEncode(0x10001u, 0x40u, 2u, &pvMsgEncodeInfo, pszInnerContentObjID, 0);
    v12 = v32;
    if ( v32 )
    {
      if ( CryptMsgUpdate(v32, pbData, cbData, 1) )
      {
        v33 = a5 != 0;
        if ( CryptMsgGetParam(v12, v33 + 2, 0, 0, &pcbData) )
        {
          v14 = (unsigned __int8 *)LocalAlloc(0x40u, pcbData);
          if ( v14 )
          {
            if ( CryptMsgGetParam(v12, v33 + 2, 0, v14, &pcbData) )
            {
              v34 = pcbData;
              *a9 = v14;
              v14 = 0;
              *a10 = v34;
              LastError = dwErrCode;
              goto LABEL_4;
            }
          }
        }
      }
    }
  }
  else
  {
    SetLastError(dwErrCode);
  }
LABEL_3:
  v17 = 0;
  LastError = GetLastError();
LABEL_4:
  if ( *((_QWORD *)&v41 + 1)
    && *((__int128 **)&v41 + 1) != &v39
    && *(_DWORD *)(*((_QWORD *)&v41 + 1) - 8LL) == 1885431112 )
  {
    ((void (*)(void))g_pfnFree)();
  }
  if ( v12 )
    CryptMsgClose(v12);
  if ( v14 )
    LocalFree(v14);
  if ( !v17 && LastError )
    SetLastError(LastError);
  return v17;
}

```

## disassembly

```asm
0x18006d958  push    rbp
0x18006d95a  push    rbx
0x18006d95b  push    rsi
0x18006d95c  push    rdi
0x18006d95d  push    r12
0x18006d95f  push    r13
0x18006d961  push    r14
0x18006d963  push    r15
0x18006d965  sub     rsp, 108h
0x18006d96c  lea     rbp, [rsp+30h]
0x18006d971  mov     rax, cs:__security_cookie
0x18006d978  xor     rax, rbp
0x18006d97b  mov     [rbp+110h+var_50], rax
0x18006d982  xorps   xmm0, xmm0
0x18006d985  mov     [rbp+110h+pbData], r8
0x18006d989  mov     rbx, rdx
0x18006d98c  mov     [rbp+110h+cbData], r9d
0x18006d990  mov     rdi, rcx
0x18006d993  xor     r15d, r15d
0x18006d996  xor     edx, edx; Val
0x18006d998  lea     rcx, [rbp+110h+var_B0]; void *
0x18006d99c  movups  [rbp+110h+pvMsgEncodeInfo], xmm0
0x18006d9a0  lea     esi, [r15+60h]
0x18006d9a4  mov     r8d, esi; Size
0x18006d9a7  movups  [rbp+110h+var_E0], xmm0
0x18006d9ab  movups  [rbp+110h+var_D0], xmm0
0x18006d9af  call    memset_0
0x18006d9b4  mov     rcx, [rbx]; Str1
0x18006d9b7  lea     r8d, [r15+0Eh]; MaxCount
0x18006d9bb  xorps   xmm0, xmm0
0x18006d9be  mov     [rbp+110h+dwErrCode], r15d
0x18006d9c2  lea     rdx, Str2; "1.3.14.3.2.26"
0x18006d9c9  mov     [rbp+110h+pcbData], r15d
0x18006d9cd  movups  [rbp+110h+var_100], xmm0
0x18006d9d1  xor     r14d, r14d
0x18006d9d4  call    strncmp_0
0x18006d9d9  mov     r13, [rbp+110h+arg_40]
0x18006d9e0  lea     r9, [rbp+110h+var_98]
0x18006d9e4  mov     ecx, eax
0x18006d9e6  mov     [rbp+110h+var_B0], esi
0x18006d9e9  mov     rax, [rbp+110h+arg_48]
0x18006d9f0  lea     r8, [rbp+110h+var_A0]
0x18006d9f4  xor     edx, edx
0x18006d9f6  mov     [r13+0], r14
0x18006d9fa  test    ecx, ecx
0x18006d9fc  mov     rcx, rdi; pCert
0x18006d9ff  mov     [rax], r14d
0x18006da02  setnz   dl
0x18006da05  mov     rax, [rdi+18h]
0x18006da09  movups  xmm0, xmmword ptr [rbx]
0x18006da0c  mov     [rbp+110h+var_A8], rax
0x18006da10  lea     rax, [rbp+110h+dwErrCode]
0x18006da14  movsd   xmm1, qword ptr [rbx+10h]
0x18006da19  mov     [rsp+140h+pszInnerContentObjID], rax; __int64
0x18006da1e  movaps  [rbp+110h+var_90], xmm0
0x18006da25  movsd   [rbp+110h+var_80], xmm1
0x18006da2d  call    ScHelperCryptAcquireCertificatePrivateKey
0x18006da32  test    eax, eax
0x18006da34  jns     loc_18006DACD
0x18006da3a  mov     ecx, [rbp+110h+dwErrCode]; dwErrCode
0x18006da3d  call    cs:__imp_SetLastError
0x18006da43  xor     esi, esi
0x18006da45  call    cs:__imp_GetLastError
0x18006da4b  mov     ebx, eax
0x18006da4d  mov     rcx, qword ptr [rbp+110h+var_E0+8]
0x18006da51  test    rcx, rcx
0x18006da54  jz      short loc_18006DA7C
0x18006da56  lea     rax, [rbp+110h+var_100]
0x18006da5a  cmp     rcx, rax
0x18006da5d  jz      short loc_18006DA7C
0x18006da5f  test    rcx, rcx
0x18006da62  jz      short loc_18006DA7C
0x18006da64  add     rcx, 0FFFFFFFFFFFFFFF8h
0x18006da68  cmp     dword ptr [rcx], 70616548h
0x18006da6e  jnz     short loc_18006DA7C
0x18006da70  mov     rax, cs:g_pfnFree
0x18006da77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006da7c  test    r15, r15
0x18006da7f  jz      short loc_18006DA8A
0x18006da81  mov     rcx, r15; hCryptMsg
0x18006da84  call    cs:__imp_CryptMsgClose
0x18006da8a  test    r14, r14
0x18006da8d  jz      short loc_18006DA98
0x18006da8f  mov     rcx, r14; hMem
0x18006da92  call    cs:__imp_LocalFree
0x18006da98  test    esi, esi
0x18006da9a  jnz     short loc_18006DAA8
0x18006da9c  test    ebx, ebx
0x18006da9e  jz      short loc_18006DAA8
0x18006daa0  mov     ecx, ebx; dwErrCode
0x18006daa2  call    cs:__imp_SetLastError
0x18006daa8  mov     eax, esi
0x18006daaa  mov     rcx, [rbp+110h+var_50]
0x18006dab1  xor     rcx, rbp; StackCookie
0x18006dab4  call    __security_check_cookie
0x18006dab9  lea     rsp, [rbp+0D8h]
0x18006dac0  pop     r15
0x18006dac2  pop     r14
0x18006dac4  pop     r13
0x18006dac6  pop     r12
0x18006dac8  pop     rdi
0x18006dac9  pop     rsi
0x18006daca  pop     rbx
0x18006dacb  pop     rbp
0x18006dacc  retn
0x18006dacd  mov     r12d, [rbp+110h+arg_38]
0x18006dad4  lea     rax, [rbp+110h+var_B0]
0x18006dad8  mov     dword ptr [rbp+110h+pvMsgEncodeInfo], 30h ; '0'
0x18006dadf  mov     esi, 1
0x18006dae4  mov     dword ptr [rbp+110h+pvMsgEncodeInfo+4], esi
0x18006dae7  mov     qword ptr [rbp+110h+pvMsgEncodeInfo+8], rax
0x18006daeb  test    r12d, r12d
0x18006daee  jz      loc_18006DBE1
0x18006daf4  mov     edi, r12d
0x18006daf7  xor     ebx, ebx
0x18006daf9  shl     rdi, 4
0x18006dafd  test    rdi, rdi
0x18006db00  jz      short loc_18006DB63
0x18006db02  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18006db09  ja      short loc_18006DB63
0x18006db0b  mov     rcx, cs:g_ulAdditionalProbeSize
0x18006db12  add     rcx, 8
0x18006db16  add     rcx, rdi
0x18006db19  cmp     rcx, rdi
0x18006db1c  jb      short loc_18006DB63
0x18006db1e  call    VerifyStackAvailable
0x18006db23  test    eax, eax
0x18006db25  jz      short loc_18006DB63
0x18006db27  lea     rax, [rdi+8]
0x18006db2b  lea     rcx, [rax+0Fh]
0x18006db2f  cmp     rcx, rax
0x18006db32  ja      short loc_18006DB3E
0x18006db34  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18006db3e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18006db42  mov     rax, rcx
0x18006db45  call    _alloca_probe
0x18006db4a  sub     rsp, rcx
0x18006db4d  lea     rbx, [rsp+140h+pcbData]
0x18006db52  test    rbx, rbx
0x18006db55  jz      short loc_18006DB63
0x18006db57  mov     dword ptr [rbx], 6B637453h
0x18006db5d  add     rbx, 8
0x18006db61  jnz     short loc_18006DB8A
0x18006db63  lea     rcx, [rdi+8]
0x18006db67  cmp     rcx, rdi
0x18006db6a  jb      short loc_18006DB8A
0x18006db6c  mov     rax, cs:g_pfnAllocate
0x18006db73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006db78  mov     rbx, rax
0x18006db7b  test    rax, rax
0x18006db7e  jz      short loc_18006DB8A
0x18006db80  mov     dword ptr [rax], 70616548h
0x18006db86  add     rbx, 8
0x18006db8a  mov     qword ptr [rbp+110h+var_E0+8], rbx
0x18006db8e  test    rbx, rbx
0x18006db91  jz      loc_18006DA43
0x18006db97  mov     r10, [rbp+110h+arg_30]
0x18006db9e  xor     r9d, r9d
0x18006dba1  test    r12d, r12d
0x18006dba4  jz      short loc_18006DBDB
0x18006dba6  xor     r8d, r8d
0x18006dba9  mov     rax, [r10+r8*8]
0x18006dbad  mov     rdx, r8
0x18006dbb0  add     rdx, rdx
0x18006dbb3  add     r9d, esi
0x18006dbb6  mov     rcx, [rax+8]
0x18006dbba  mov     [rbx+rdx*8+8], rcx
0x18006dbbf  mov     rax, [r10+r8*8]
0x18006dbc3  add     r8, rsi
0x18006dbc6  mov     ecx, [rax+10h]
0x18006dbc9  mov     rax, qword ptr [rbp+110h+var_E0+8]
0x18006dbcd  mov     [rax+rdx*8], ecx
0x18006dbd0  cmp     r9d, r12d
0x18006dbd3  jnb     short loc_18006DBDB
0x18006dbd5  mov     rbx, qword ptr [rbp+110h+var_E0+8]
0x18006dbd9  jmp     short loc_18006DBA9
0x18006dbdb  mov     dword ptr [rbp+110h+var_E0], r12d
0x18006dbdf  jmp     short loc_18006DBFA
0x18006dbe1  mov     eax, [rdi+10h]
0x18006dbe4  mov     dword ptr [rbp+110h+var_100], eax
0x18006dbe7  mov     rax, [rdi+8]
0x18006dbeb  mov     qword ptr [rbp+110h+var_100+8], rax
0x18006dbef  lea     rax, [rbp+110h+var_100]
0x18006dbf3  mov     qword ptr [rbp+110h+var_E0+8], rax
0x18006dbf7  mov     dword ptr [rbp+110h+var_E0], esi
0x18006dbfa  mov     rax, [rbp+110h+arg_28]
0x18006dc01  lea     r9, [rbp+110h+pvMsgEncodeInfo]; pvMsgEncodeInfo
0x18006dc05  mov     edi, 40h ; '@'
0x18006dc0a  mov     [rsp+140h+pStreamInfo], r14; pStreamInfo
0x18006dc0f  mov     edx, edi; dwFlags
0x18006dc11  mov     [rsp+140h+pszInnerContentObjID], rax; pszInnerContentObjID
0x18006dc16  mov     ecx, 10001h; dwMsgEncodingType
0x18006dc1b  lea     r8d, [rdi-3Eh]; dwMsgType
0x18006dc1f  call    cs:__imp_CryptMsgOpenToEncode
0x18006dc25  mov     r15, rax
0x18006dc28  test    rax, rax
0x18006dc2b  jz      loc_18006DA43
0x18006dc31  mov     r8d, [rbp+110h+cbData]; cbData
0x18006dc35  mov     r9d, esi; fFinal
0x18006dc38  mov     rdx, [rbp+110h+pbData]; pbData
0x18006dc3c  mov     rcx, rax; hCryptMsg
0x18006dc3f  call    cs:__imp_CryptMsgUpdate
0x18006dc45  test    eax, eax
0x18006dc47  jz      loc_18006DA43
0x18006dc4d  neg     [rbp+110h+arg_20]
0x18006dc53  lea     rax, [rbp+110h+pcbData]
0x18006dc57  mov     rcx, r15; hCryptMsg
0x18006dc5a  mov     [rsp+140h+pszInnerContentObjID], rax; pcbData
0x18006dc5f  sbb     ebx, ebx
0x18006dc61  xor     r9d, r9d; pvData
0x18006dc64  neg     ebx
0x18006dc66  xor     r8d, r8d; dwIndex
0x18006dc69  lea     edx, [rbx+2]; dwParamType
0x18006dc6c  call    cs:__imp_CryptMsgGetParam
0x18006dc72  test    eax, eax
0x18006dc74  jz      loc_18006DA43
0x18006dc7a  mov     edx, [rbp+110h+pcbData]; uBytes
0x18006dc7d  mov     ecx, edi; uFlags
0x18006dc7f  call    cs:__imp_LocalAlloc
0x18006dc85  mov     r14, rax
0x18006dc88  test    rax, rax
0x18006dc8b  jz      loc_18006DA43
0x18006dc91  lea     rax, [rbp+110h+pcbData]
0x18006dc95  mov     r9, r14; pvData
0x18006dc98  xor     r8d, r8d; dwIndex
0x18006dc9b  mov     [rsp+140h+pszInnerContentObjID], rax; pcbData
0x18006dca0  lea     edx, [rbx+2]; dwParamType
0x18006dca3  mov     rcx, r15; hCryptMsg
0x18006dca6  call    cs:__imp_CryptMsgGetParam
0x18006dcac  test    eax, eax
0x18006dcae  jz      loc_18006DA43
0x18006dcb4  mov     rcx, [rbp+110h+arg_48]
0x18006dcbb  mov     eax, [rbp+110h+pcbData]
0x18006dcbe  mov     [r13+0], r14
0x18006dcc2  xor     r14d, r14d
0x18006dcc5  mov     [rcx], eax
0x18006dcc7  mov     ebx, [rbp+110h+dwErrCode]
0x18006dcca  jmp     loc_18006DA4D
```
