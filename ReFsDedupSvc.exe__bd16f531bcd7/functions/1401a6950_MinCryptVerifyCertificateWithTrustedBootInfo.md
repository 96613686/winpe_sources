# MinCryptVerifyCertificateWithTrustedBootInfo

- ea: `0x1401a6950`
- end: `0x1401a72da`
- name: `MinCryptVerifyCertificateWithTrustedBootInfo`
- size: `2442`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14014e9e8`
- `0x14014eeec`

## callees

- `0x140004870`
- `0x1400057d4`
- `0x1400057e0`
- `0x1400057f8`
- `0x1401a4a84`
- `0x1401a53b8`
- `0x1401a5490`
- `0x1401a5634`
- `0x1401a56e8`
- `0x1401a5ad8`
- `0x1401a6134`
- `0x1401a628c`
- `0x1401a62d4`
- `0x1401a65dc`
- `0x1401a6634`
- `0x1401a66f8`
- `0x1401a6794`
- `0x1401a67e8`
- `0x1401a6848`
- `0x1401a68d4`
- `0x1401a6950`
- `0x1401a7848`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x1401a6f3c`
- `ntdll!RtlCompareMemory` at `0x1401a7005`
- `ntdll!RtlCompareMemory` at `0x1401a6f3c`
- `ntdll!RtlCompareMemory` at `0x1401a7005`

## pseudocode

```c
__int64 __fastcall MinCryptVerifyCertificateWithTrustedBootInfo(
        struct _CRYPTOAPI_BLOB *a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        union _LARGE_INTEGER *a5,
        _OWORD *a6)
{
  union _LARGE_INTEGER *v6; // r14
  __int64 v7; // rdi
  _OWORD *v8; // r12
  struct _CRYPTOAPI_BLOB *v9; // r15
  __int64 v10; // r13
  __int64 v11; // rsi
  __int64 v12; // rbx
  struct _MINCRYPT_CHAIN_INFO near **v13; // rcx
  union _LARGE_INTEGER *v14; // rcx
  __int64 v15; // rdx
  union _LARGE_INTEGER *v16; // rsi
  struct _CRYPTOAPI_BLOB *v17; // rdi
  __int64 result; // rax
  struct _CRYPTOAPI_BLOB *v19; // rdx
  unsigned int v20; // edi
  union _LARGE_INTEGER *v21; // rdi
  const struct _CRYPTOAPI_BLOB *v22; // rcx
  union _LARGE_INTEGER v23; // rax
  struct _CRYPTOAPI_BLOB *v24; // rdx
  unsigned __int8 v25; // al
  __int64 v26; // rdi
  unsigned int v27; // esi
  __int64 v28; // r8
  void *v29; // rdx
  __int64 v30; // r8
  unsigned int v31; // eax
  void *v32; // r13
  int v33; // esi
  int v34; // r12d
  __int64 i; // rdi
  unsigned int v36; // eax
  unsigned int v37; // edi
  void *v38; // rdx
  size_t v39; // r8
  unsigned int cbData; // eax
  int v41; // eax
  int v42; // ecx
  __int64 v43; // r12
  __int64 RootByKey; // rax
  int v45; // edi
  union _LARGE_INTEGER v46; // rax
  unsigned int v47; // r13d
  struct _CRYPTOAPI_BLOB *v48; // rcx
  unsigned int v49; // eax
  __int64 v50; // r9
  union _LARGE_INTEGER v51; // rax
  __int128 v52; // xmm0
  __int64 v53; // r12
  unsigned int v54; // ecx
  const struct _ROOT_INFO near *const *v55; // r13
  __int64 IssuerCertificateByName; // rax
  _QWORD *v57; // r8
  union _LARGE_INTEGER v58; // rcx
  int v59; // eax
  union _LARGE_INTEGER v60; // rax
  unsigned int v61; // r12d
  unsigned int v62; // r13d
  unsigned int v63; // edi
  unsigned int v64; // eax
  __int64 v65; // rax
  unsigned int v66; // edi
  __int64 v67; // r13
  union _LARGE_INTEGER v68; // rax
  unsigned __int8 v69; // [rsp+40h] [rbp-C0h]
  unsigned int LowPart; // [rsp+44h] [rbp-BCh] BYREF
  size_t Size; // [rsp+48h] [rbp-B8h] BYREF
  int j; // [rsp+50h] [rbp-B0h]
  int v73; // [rsp+54h] [rbp-ACh]
  void *Buf1; // [rsp+58h] [rbp-A8h]
  _OWORD *v75; // [rsp+60h] [rbp-A0h]
  int v76; // [rsp+68h] [rbp-98h]
  struct _CRYPTOAPI_BLOB *v77; // [rsp+70h] [rbp-90h]
  __int64 v78; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v79; // [rsp+80h] [rbp-80h]
  unsigned int v80; // [rsp+84h] [rbp-7Ch]
  __int64 v81; // [rsp+88h] [rbp-78h]
  __int64 v82; // [rsp+90h] [rbp-70h]
  __int64 v83; // [rsp+98h] [rbp-68h]
  __int64 v84; // [rsp+A0h] [rbp-60h]
  union _LARGE_INTEGER *v85; // [rsp+A8h] [rbp-58h]
  char v86[32]; // [rsp+B0h] [rbp-50h] BYREF
  SIZE_T Length; // [rsp+D0h] [rbp-30h]
  _BYTE *v88; // [rsp+D8h] [rbp-28h]
  char v89[48]; // [rsp+F0h] [rbp-10h] BYREF
  char v90[16]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v91[16]; // [rsp+130h] [rbp+30h] BYREF
  int v92; // [rsp+140h] [rbp+40h]
  void *v93; // [rsp+148h] [rbp+48h]

  v6 = a5;
  v7 = g_ulUseChainStore;
  v8 = a6;
  v9 = a1;
  v77 = a1;
  v10 = a4;
  *(_OWORD *)&a5->LowPart = 0;
  v80 = a2;
  *(_OWORD *)&a5[2].LowPart = 0;
  v83 = a3;
  *(_OWORD *)&a5[4].LowPart = 0;
  v81 = a4;
  v11 = 104 * v7;
  v85 = a5;
  v12 = 0x7FFFFFFFFFFFFFFFLL;
  v13 = &g_rgChainInfo + 13 * v7;
  v75 = a6;
  a5[2].QuadPart = (LONGLONG)v13;
  j = 0;
  v84 = 0;
  v76 = 0;
  v78 = 0;
  v69 = 0;
  LOBYTE(v73) = 0;
  Size = 0;
  a5->LowPart = 48;
  memset_0(v13, 0, 0x68u);
  *(struct _MINCRYPT_CHAIN_INFO near **)((char *)&g_rgChainInfo + v11 + 8) = (struct _MINCRYPT_CHAIN_INFO near *)&(&g_rgPublicKeys)[20 * v7];
  *(struct _MINCRYPT_CHAIN_INFO near **)((char *)&g_rgChainInfo + v11 + 40) = (struct _MINCRYPT_CHAIN_INFO near *)(&g_rgSignerInfo + 150 * v7);
  if ( a6 )
    memset_0(a6, 0, 0xA8u);
  v14 = a5 + 1;
  v15 = 1;
  v16 = a5 + 1;
  while ( 1 )
  {
    if ( HIDWORD(Size) )
    {
      if ( !v10 || (*(_DWORD *)(v10 + 4) & 1) == 0 )
        goto LABEL_28;
      v17 = &g_rgEKUsNonLeaf;
      v16 = v14;
    }
    else
    {
      v17 = (struct _CRYPTOAPI_BLOB *)(0x140000000LL + 800LL * g_ulUseChainStore + 2238912);
      *(_QWORD *)(v6[2].QuadPart + 24) = v17;
    }
    LowPart = 50;
    result = I_MinCryptGetCertificateEKUs(v9 + 14, &LowPart, v17);
    if ( (int)result < 0 )
      return result;
    v19 = v17;
    v20 = LowPart;
    if ( !I_MinCryptCheckEKURequirements(LowPart, v19, (struct _MINCRYPT_POLICY_REQS *)v10) )
    {
      v16->LowPart |= 0x80000u;
      return 3221226536LL;
    }
    if ( !HIDWORD(Size) )
    {
      *(_DWORD *)(v6[2].QuadPart + 32) = v20;
      v21 = v6 + 4;
      if ( !(unsigned __int8)MinAsn1DecodeTime(&v9[8], &v6[4]) || !(unsigned __int8)MinAsn1DecodeTime(&v9[9], &v6[5]) )
      {
        v21->QuadPart = 0;
        v6[5].QuadPart = 0;
      }
      v22 = (const struct _CRYPTOAPI_BLOB *)&qword_1401BDA20;
      if ( g_MobilePlatform )
        v22 = &stru_1401BDA30;
      v23 = v6[2];
      v24 = *(struct _CRYPTOAPI_BLOB **)(v23.QuadPart + 24);
      v23.LowPart = *(_DWORD *)(v23.QuadPart + 32);
      Buf1 = v24;
      LowPart = v23.LowPart;
      v25 = I_MinCryptCheckEKU(v22, v23.LowPart, v24);
      v69 = v25;
      if ( v25 && g_FlightSignedNotBefore.QuadPart > 0 && v21->QuadPart < g_FlightSignedNotBefore.QuadPart )
      {
        v16->LowPart |= 0x600000u;
      }
      else
      {
        if ( g_IgnoreLifetimeSigningEKU
          || g_TrustFlightSigning && v25
          || v10 && (*(_DWORD *)(v10 + 4) & 4) != 0
          || !I_MinCryptCheckEKU(&stru_1401BDA40, LowPart, (struct _CRYPTOAPI_BLOB *const)Buf1)
          || !I_MinCryptSignerCertExpired(v69, v6 + 4, v6 + 5) )
        {
          v8 = v75;
          goto LABEL_28;
        }
        v16->LowPart |= 0x400000u;
      }
      return 3221227013LL;
    }
LABEL_28:
    v26 = 120LL * HIDWORD(Size);
    Buf1 = (void *)(*(_QWORD *)(v6[2].QuadPart + 40) + v26 + 8);
    v27 = MinCryptDecodeHashAlgorithmIdentifier(&v9[3], v15);
    LowPart = v27;
    result = MinCryptHashMemory(v27, 1, (int)v9 + 32, (_DWORD)Buf1, (__int64)&Size);
    if ( (int)result < 0 )
      return result;
    *(_DWORD *)(v26 + *(_QWORD *)(v6[2].QuadPart + 40)) = v27;
    *(_DWORD *)(*(_QWORD *)(v6[2].QuadPart + 40) + v26 + 4) = Size;
    *(struct _CRYPTOAPI_BLOB *)(*(_QWORD *)(v6[2].QuadPart + 40) + v26 + 104) = v9[1];
    I_MinCryptGetCommonName(v9 + 7, (struct _MINCRYPT_STRING *)(v26 + *(_QWORD *)(v6[2].QuadPart + 40) + 88LL));
    I_MinCryptGetCommonName(v9 + 10, (struct _MINCRYPT_STRING *)(v26 + *(_QWORD *)(v6[2].QuadPart + 40) + 72LL));
    v28 = (unsigned int)Size;
    v29 = Buf1;
    ++*(_DWORD *)(v6[2].QuadPart + 48);
    if ( (int)MinCryptIsCertificateRevoked(v27, v29, v28, &v78) < 0 )
    {
      if ( !v69 && !g_IgnoreFlightSigningEKU )
        goto LABEL_41;
      v31 = LowPart;
      v32 = Buf1;
      v33 = 0;
      v34 = Size;
      for ( i = 0; i != 3; ++i )
      {
        if ( v31 == dword_1401BD408[4 * i] )
        {
          v36 = dword_1401BD40C[4 * i];
          if ( v34 == v36 && !memcmp_0(v32, *(&off_1401BD410 + 2 * i), v36) )
            v33 = 1;
          v31 = LowPart;
        }
      }
      v6 = v85;
      v9 = v77;
      v10 = v81;
      v8 = v75;
      if ( !v33 || !g_TrustFlightSigning )
      {
LABEL_41:
        v6[1].LowPart |= 0x200000u;
        v76 = 1;
        if ( v78 < v12 )
          v12 = v78;
      }
    }
    v37 = HIDWORD(Size);
    if ( !HIDWORD(Size) && v8 )
    {
      v38 = Buf1;
      v8[1] = *(_OWORD *)(*(_QWORD *)(v6[2].QuadPart + 40) + 88LL);
      v8[2] = *(_OWORD *)(*(_QWORD *)(v6[2].QuadPart + 40) + 72LL);
      *((_DWORD *)v8 + 34) = v9[6].cbData;
      *((_QWORD *)v8 + 18) = v9[6].pbData;
      *((_DWORD *)v8 + 12) = LowPart;
      v39 = (unsigned int)Size;
      *((_DWORD *)v8 + 13) = Size;
      memcpy_0((char *)v8 + 56, v38, v39);
      *((_DWORD *)v8 + 38) = v9[1].cbData;
      *((_QWORD *)v8 + 20) = v9[1].pbData;
    }
    cbData = v9[7].cbData;
    if ( cbData == v9[10].cbData )
    {
      v41 = memcmp_0(v9[7].pbData, v9[10].pbData, cbData);
      v42 = (unsigned __int8)v73;
      if ( !v41 )
        v42 = 1;
      v73 = v42;
    }
    LOBYTE(v30) = v73;
    v16 = v6 + 1;
    result = MincryptValidateBasicConstraints(&v9[14], v37, v30, &v6[1]);
    if ( (int)result < 0 )
      return result;
    v43 = (__int64)&v9[11];
    if ( !(_BYTE)v73 )
      break;
    RootByKey = I_MinCryptFindRootByKey(&v9[11]);
    v45 = 1;
    if ( RootByKey )
    {
      v43 = RootByKey + 16;
      v16->LowPart |= *(_DWORD *)(RootByKey + 32) | 1;
      *(_DWORD *)(v6[2].QuadPart + 52) = *(_DWORD *)(RootByKey + 36);
    }
    else
    {
      v46 = v6[2];
      v16->LowPart = 1;
      *(_DWORD *)(v46.QuadPart + 52) = 2;
      if ( v10
        && (*(_DWORD *)(v10 + 4) & 2) != 0
        && (int)MinAsn1ParsePublicKeyInfo(&v9[11], v89) >= 0
        && (int)MinAsn1ParseRSAPublicKey(v90, v86) >= 0 )
      {
        v47 = Length;
        v48 = (struct _CRYPTOAPI_BLOB *)v88;
        v77 = (struct _CRYPTOAPI_BLOB *)v88;
        if ( (unsigned int)Length > 1 )
        {
          if ( *v88 )
            goto LABEL_61;
          v48 = (struct _CRYPTOAPI_BLOB *)(v88 + 1);
          v77 = (struct _CRYPTOAPI_BLOB *)(v88 + 1);
          v47 = Length - 1;
        }
        if ( !v47 )
          goto LABEL_70;
LABEL_61:
        if ( v47 <= 0x200 )
        {
          v49 = 0;
          v50 = qword_140243F30;
          v79 = dword_140243F2C;
          v82 = qword_140243F30;
          for ( j = 0; v49 < v79; j = ++v49 )
          {
            if ( v47 == *(_DWORD *)(v50 + 16LL * v49) )
            {
              v45 = 1;
              if ( RtlCompareMemory(v48, *(const void **)(v50 + 16LL * v49 + 8), v47) == v47 )
              {
                v16->LowPart |= 0x200u;
                break;
              }
              v49 = j;
              v48 = v77;
              v50 = v82;
            }
          }
        }
      }
    }
LABEL_70:
    v51 = v6[2];
    v52 = *(_OWORD *)v43;
    j = 1;
    *(_OWORD *)(*(_QWORD *)(v51.QuadPart + 8) + 16LL * *(unsigned int *)(v51.QuadPart + 16)) = v52;
    ++*(_DWORD *)(v6[2].QuadPart + 16);
LABEL_77:
    if ( !HIDWORD(Size) )
    {
      v57 = v75;
      if ( v75 )
      {
        *((_DWORD *)v75 + 30) = *(_DWORD *)v43;
        v57[16] = *(_QWORD *)(v43 + 8);
      }
    }
    v10 = v81;
    result = MinCryptVerifySignedHash2(LowPart, (_DWORD)Buf1, Size, (int)v9 + 64, v43, v81);
    if ( (int)result < 0 )
      return result;
    if ( v45 )
      goto LABEL_108;
    v15 = 1;
    if ( ++HIDWORD(Size) >= 9u )
    {
      v60 = v6[2];
      v16->LowPart |= 0x10u;
      *(_DWORD *)(v60.QuadPart + 52) = 1;
      goto LABEL_107;
    }
    v9 = (struct _CRYPTOAPI_BLOB *)v84;
    v14 = v6 + 1;
    v8 = v75;
    v77 = (struct _CRYPTOAPI_BLOB *)v84;
  }
  *(_OWORD *)(*(_QWORD *)(v6[2].QuadPart + 8) + 16LL * (unsigned int)(*(_DWORD *)(v6[2].QuadPart + 16))++) = *(_OWORD *)v43;
  v53 = 0;
  while ( 1 )
  {
    v54 = v9[7].cbData;
    v55 = &RootTable + 5 * v53;
    if ( v54 == *(_DWORD *)v55 && RtlCompareMemory(v9[7].pbData, (&off_1401BDA78)[5 * v53], v54) == v54 )
      break;
    v53 = (unsigned int)(v53 + 1);
    if ( (unsigned int)v53 >= 0xD )
      goto LABEL_75;
  }
  if ( v55 )
  {
    v43 = (__int64)(v55 + 2);
    v16->LowPart |= *((_DWORD *)v55 + 8);
    v58 = v6[2];
    v45 = 1;
    v59 = *((_DWORD *)v55 + 9);
    j = 1;
    *(_DWORD *)(v58.QuadPart + 52) = v59;
    *(_OWORD *)(*(_QWORD *)(v6[2].QuadPart + 8) + 16LL * (unsigned int)(*(_DWORD *)(v6[2].QuadPart + 16))++) = *((_OWORD *)v55 + 1);
    goto LABEL_77;
  }
LABEL_75:
  IssuerCertificateByName = MinCryptFindIssuerCertificateByName(&v9[7], v80, v83);
  v84 = IssuerCertificateByName;
  if ( IssuerCertificateByName )
  {
    v45 = j;
    v43 = IssuerCertificateByName + 176;
    goto LABEL_77;
  }
  if ( v81 && (*(_DWORD *)(v81 + 4) & 2) != 0 )
  {
    v61 = dword_140243F2C;
    v62 = dword_140243F28;
    v82 = qword_140243F30;
    v83 = qword_140243F20;
    memset_0(v91, 0, 0xF0u);
    v63 = 0;
    if ( v62 )
    {
      while ( 1 )
      {
        if ( (int)MinAsn1ParseCertificate(*(_QWORD *)(v83 + 16LL * v63 + 8), *(unsigned int *)(v83 + 16LL * v63), v91) >= 0 )
        {
          v64 = v9[1].cbData;
          if ( v92 == v64 && !memcmp_0(v93, v9[1].pbData, v64) )
          {
            result = 0;
            goto LABEL_103;
          }
          v65 = MinCryptFindIssuerCertificateByName(&v9[7], 1, v91);
          if ( v65 )
            break;
        }
        if ( ++v63 >= v62 )
          goto LABEL_98;
      }
      result = MinCryptVerifySignedHash2(LowPart, (_DWORD)Buf1, Size, (int)v9 + 64, v65 + 176, 0);
LABEL_102:
      if ( (int)result >= 0 )
      {
LABEL_103:
        v16->LowPart |= 0x200u;
        goto LABEL_108;
      }
    }
    else
    {
LABEL_98:
      v66 = 0;
      if ( v61 )
      {
        v67 = v82;
        while ( 1 )
        {
          result = MinCryptVerifySignedHashFromRawKeyComponents(
                     LowPart,
                     (_DWORD)Buf1,
                     Size,
                     (int)v9 + 64,
                     v67 + 16LL * v66,
                     65537,
                     0);
          if ( (int)result >= 0 )
            goto LABEL_103;
          if ( ++v66 >= v61 )
            goto LABEL_102;
        }
      }
    }
  }
  v68 = v6[2];
  v16->LowPart |= 0x10u;
  *(_DWORD *)(v68.QuadPart + 52) = 1;
LABEL_107:
  result = 0;
LABEL_108:
  if ( v76 )
  {
    v6[3].QuadPart = v12;
    return 3221227011LL;
  }
  return result;
}

```

## disassembly

```asm
0x1401a6950  push    rbp
0x1401a6952  push    rbx
0x1401a6953  push    rsi
0x1401a6954  push    rdi
0x1401a6955  push    r12
0x1401a6957  push    r13
0x1401a6959  push    r14
0x1401a695b  push    r15
0x1401a695d  lea     rbp, [rsp-138h]
0x1401a6965  sub     rsp, 238h
0x1401a696c  mov     rax, cs:__security_cookie
0x1401a6973  xor     rax, rsp
0x1401a6976  mov     [rbp+170h+var_50], rax
0x1401a697d  mov     r14, [rbp+170h+arg_20]
0x1401a6984  lea     rax, cs:140000000h
0x1401a698b  mov     edi, cs:?g_ulUseChainStore@@3KA; ulong g_ulUseChainStore
0x1401a6991  xorps   xmm0, xmm0
0x1401a6994  mov     r12, [rbp+170h+arg_28]
0x1401a699b  mov     r15, rcx
0x1401a699e  mov     [rsp+270h+var_200], rcx
0x1401a69a3  mov     r13, r9
0x1401a69a6  movups  xmmword ptr [r14], xmm0
0x1401a69aa  mov     [rbp+170h+var_1EC], edx
0x1401a69ad  xor     edx, edx; Val
0x1401a69af  movups  xmmword ptr [r14+10h], xmm0
0x1401a69b4  lea     rcx, rva ?g_rgChainInfo@@3PAU_MINCRYPT_CHAIN_INFO@@A[rax]; _MINCRYPT_CHAIN_INFO near * g_rgChainInfo ...
0x1401a69bb  mov     [rbp+170h+var_1D8], r8
0x1401a69bf  movups  xmmword ptr [r14+20h], xmm0
0x1401a69c4  lea     r8d, [rdx+68h]; Size
0x1401a69c8  mov     [rbp+170h+var_1E8], r9
0x1401a69cc  imul    rsi, rdi, 68h ; 'h'
0x1401a69d0  mov     [rbp+170h+var_1C8], r14
0x1401a69d4  mov     rbx, 7FFFFFFFFFFFFFFFh
0x1401a69de  add     rcx, rsi; void *
0x1401a69e1  mov     [rsp+270h+var_210], r12
0x1401a69e6  mov     [r14+10h], rcx
0x1401a69ea  mov     dword ptr [rsp+270h+Size+4], edx
0x1401a69ee  mov     [rsp+270h+var_220], edx
0x1401a69f2  mov     [rbp+170h+var_1D0], rdx
0x1401a69f6  mov     [rsp+270h+var_208], edx
0x1401a69fa  mov     [rsp+270h+var_1F8], rdx
0x1401a69ff  mov     [rsp+270h+var_230], dl
0x1401a6a03  mov     byte ptr [rsp+270h+var_21C], dl
0x1401a6a07  mov     dword ptr [rsp+270h+Size], edx
0x1401a6a0b  mov     dword ptr [r14], 30h ; '0'
0x1401a6a12  call    memset_0
0x1401a6a17  lea     rcx, ?g_rgPublicKeys@@3PAY09U_CRYPTOAPI_BLOB@@A; _CRYPTOAPI_BLOB (near * g_rgPublicKeys)[10]
0x1401a6a1e  lea     r8, cs:140000000h
0x1401a6a25  lea     rax, [rdi+rdi*4]
0x1401a6a29  shl     rax, 5
0x1401a6a2d  add     rax, rcx
0x1401a6a30  lea     rcx, ?g_rgSignerInfo@@3PAY09U_MINCRYPT_SIGNER_INFO@@A; _MINCRYPT_SIGNER_INFO (near * g_rgSignerInfo)[10]
0x1401a6a37  mov     [rsi+r8+221F98h], rax
0x1401a6a3f  imul    rax, rdi, 4B0h
0x1401a6a46  add     rax, rcx
0x1401a6a49  mov     [rsi+r8+221FB8h], rax
0x1401a6a51  test    r12, r12
0x1401a6a54  jz      short loc_1401A6A6D
0x1401a6a56  xor     edx, edx; Val
0x1401a6a58  mov     r8d, 0A8h; Size
0x1401a6a5e  mov     rcx, r12; void *
0x1401a6a61  call    memset_0
0x1401a6a66  lea     r8, cs:140000000h
0x1401a6a6d  lea     rcx, [r14+8]
0x1401a6a71  mov     edx, 1
0x1401a6a76  mov     rsi, rcx
0x1401a6a79  cmp     dword ptr [rsp+270h+Size+4], 0
0x1401a6a7e  jz      short loc_1401A6AA1
0x1401a6a80  test    r13, r13
0x1401a6a83  jz      loc_1401A6BFC
0x1401a6a89  mov     eax, [r13+4]
0x1401a6a8d  test    dl, al
0x1401a6a8f  jz      loc_1401A6BFC
0x1401a6a95  lea     rdi, ?g_rgEKUsNonLeaf@@3PAU_CRYPTOAPI_BLOB@@A; _CRYPTOAPI_BLOB near * g_rgEKUsNonLeaf
0x1401a6a9c  mov     rsi, rcx
0x1401a6a9f  jmp     short loc_1401A6AC0
0x1401a6aa1  mov     eax, cs:?g_ulUseChainStore@@3KA; ulong g_ulUseChainStore
0x1401a6aa7  imul    rcx, rax, 320h
0x1401a6aae  mov     rax, [r14+10h]
0x1401a6ab2  lea     rdi, [rcx+2229C0h]
0x1401a6ab9  add     rdi, r8
0x1401a6abc  mov     [rax+18h], rdi
0x1401a6ac0  lea     rcx, [r15+0E0h]; struct _CRYPTOAPI_BLOB *
0x1401a6ac7  mov     [rsp+270h+var_22C], 32h ; '2'
0x1401a6acf  mov     r8, rdi; struct _CRYPTOAPI_BLOB *
0x1401a6ad2  lea     rdx, [rsp+270h+var_22C]; unsigned int *
0x1401a6ad7  call    ?I_MinCryptGetCertificateEKUs@@YAJPEAU_CRYPTOAPI_BLOB@@PEAKQEAU1@@Z; I_MinCryptGetCertificateEKUs(_CRYPTOAPI_BLOB *,ulong *,_CRYPTOAPI_BLOB * const)
0x1401a6adc  test    eax, eax
0x1401a6ade  js      loc_1401A72B6
0x1401a6ae4  mov     rdx, rdi; struct _CRYPTOAPI_BLOB *
0x1401a6ae7  mov     r8, r13; struct _MINCRYPT_POLICY_REQS *
0x1401a6aea  mov     edi, [rsp+270h+var_22C]
0x1401a6aee  mov     ecx, edi; unsigned int
0x1401a6af0  call    ?I_MinCryptCheckEKURequirements@@YAEKQEAU_CRYPTOAPI_BLOB@@PEAU_MINCRYPT_POLICY_REQS@@@Z; I_MinCryptCheckEKURequirements(ulong,_CRYPTOAPI_BLOB * const,_MINCRYPT_POLICY_REQS *)
0x1401a6af5  test    al, al
0x1401a6af7  jz      loc_1401A72AD
0x1401a6afd  cmp     dword ptr [rsp+270h+Size+4], 0
0x1401a6b02  jnz     loc_1401A6BFC
0x1401a6b08  mov     rax, [r14+10h]
0x1401a6b0c  lea     rcx, [r15+80h]
0x1401a6b13  lea     r12, [r14+28h]
0x1401a6b17  mov     [rax+20h], edi
0x1401a6b1a  lea     rdi, [r14+20h]
0x1401a6b1e  mov     rdx, rdi
0x1401a6b21  call    MinAsn1DecodeTime
0x1401a6b26  test    al, al
0x1401a6b28  jz      short loc_1401A6B3D
0x1401a6b2a  lea     rcx, [r15+90h]
0x1401a6b31  mov     rdx, r12
0x1401a6b34  call    MinAsn1DecodeTime
0x1401a6b39  test    al, al
0x1401a6b3b  jnz     short loc_1401A6B4C
0x1401a6b3d  mov     qword ptr [rdi], 0
0x1401a6b44  mov     qword ptr [r12], 0
0x1401a6b4c  cmp     cs:?g_MobilePlatform@@3EA, 0; uchar g_MobilePlatform
0x1401a6b53  lea     rax, stru_1401BDA30
0x1401a6b5a  lea     rcx, qword_1401BDA20
0x1401a6b61  cmovnz  rcx, rax; struct _CRYPTOAPI_BLOB *
0x1401a6b65  mov     rax, [r14+10h]
0x1401a6b69  mov     rdx, [rax+18h]
0x1401a6b6d  mov     eax, [rax+20h]
0x1401a6b70  mov     r8, rdx; struct _CRYPTOAPI_BLOB *
0x1401a6b73  mov     [rsp+270h+Buf1], rdx
0x1401a6b78  mov     edx, eax; unsigned int
0x1401a6b7a  mov     [rsp+270h+var_22C], eax
0x1401a6b7e  call    ?I_MinCryptCheckEKU@@YAEPEBU_CRYPTOAPI_BLOB@@KQEAU1@@Z; I_MinCryptCheckEKU(_CRYPTOAPI_BLOB const *,ulong,_CRYPTOAPI_BLOB * const)
0x1401a6b83  mov     [rsp+270h+var_230], al
0x1401a6b87  test    al, al
0x1401a6b89  jz      short loc_1401A6BA4
0x1401a6b8b  mov     rax, cs:?g_FlightSignedNotBefore@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_FlightSignedNotBefore
0x1401a6b92  test    rax, rax
0x1401a6b95  jle     short loc_1401A6BA0
0x1401a6b97  cmp     [rdi], rax
0x1401a6b9a  jl      loc_1401A712A
0x1401a6ba0  mov     al, [rsp+270h+var_230]
0x1401a6ba4  cmp     cs:?g_IgnoreLifetimeSigningEKU@@3EA, 0; uchar g_IgnoreLifetimeSigningEKU
0x1401a6bab  jnz     short loc_1401A6BF7
0x1401a6bad  cmp     cs:?g_TrustFlightSigning@@3EA, 0; uchar g_TrustFlightSigning
0x1401a6bb4  jz      short loc_1401A6BBA
0x1401a6bb6  test    al, al
0x1401a6bb8  jnz     short loc_1401A6BF7
0x1401a6bba  test    r13, r13
0x1401a6bbd  jz      short loc_1401A6BC7
0x1401a6bbf  mov     eax, [r13+4]
0x1401a6bc3  test    al, 4
0x1401a6bc5  jnz     short loc_1401A6BF7
0x1401a6bc7  mov     r8, [rsp+270h+Buf1]; struct _CRYPTOAPI_BLOB *
0x1401a6bcc  lea     rcx, stru_1401BDA40; struct _CRYPTOAPI_BLOB *
0x1401a6bd3  mov     edx, [rsp+270h+var_22C]; unsigned int
0x1401a6bd7  call    ?I_MinCryptCheckEKU@@YAEPEBU_CRYPTOAPI_BLOB@@KQEAU1@@Z; I_MinCryptCheckEKU(_CRYPTOAPI_BLOB const *,ulong,_CRYPTOAPI_BLOB * const)
0x1401a6bdc  test    al, al
0x1401a6bde  jz      short loc_1401A6BF7
0x1401a6be0  mov     cl, [rsp+270h+var_230]; unsigned __int8
0x1401a6be4  mov     r8, r12; union _LARGE_INTEGER *
0x1401a6be7  mov     rdx, rdi; union _LARGE_INTEGER *
0x1401a6bea  call    ?I_MinCryptSignerCertExpired@@YAEEPEAT_LARGE_INTEGER@@0@Z; I_MinCryptSignerCertExpired(uchar,_LARGE_INTEGER *,_LARGE_INTEGER *)
0x1401a6bef  test    al, al
0x1401a6bf1  jnz     loc_1401A713A
0x1401a6bf7  mov     r12, [rsp+270h+var_210]
0x1401a6bfc  mov     eax, dword ptr [rsp+270h+Size+4]
0x1401a6c00  imul    rdi, rax, 78h ; 'x'
0x1401a6c04  mov     rax, [r14+10h]
0x1401a6c08  mov     rcx, [rax+28h]
0x1401a6c0c  lea     rax, [rdi+8]
0x1401a6c10  add     rax, rcx
0x1401a6c13  lea     rcx, [r15+30h]
0x1401a6c17  mov     [rsp+270h+Buf1], rax
0x1401a6c1c  call    MinCryptDecodeHashAlgorithmIdentifier
0x1401a6c21  mov     r9, [rsp+270h+Buf1]
0x1401a6c26  lea     r8, [r15+20h]
0x1401a6c2a  mov     esi, eax
0x1401a6c2c  mov     [rsp+270h+var_22C], eax
0x1401a6c30  lea     rax, [rsp+270h+Size]
0x1401a6c35  mov     ecx, esi
0x1401a6c37  mov     edx, 1
0x1401a6c3c  mov     [rsp+270h+var_250], rax
0x1401a6c41  call    MinCryptHashMemory
0x1401a6c46  test    eax, eax
0x1401a6c48  js      loc_1401A72B6
0x1401a6c4e  mov     rax, [r14+10h]
0x1401a6c52  mov     rcx, [rax+28h]
0x1401a6c56  mov     [rdi+rcx], esi
0x1401a6c59  mov     rax, [r14+10h]
0x1401a6c5d  mov     rcx, [rax+28h]
0x1401a6c61  mov     eax, dword ptr [rsp+270h+Size]
0x1401a6c65  mov     [rcx+rdi+4], eax
0x1401a6c69  mov     rax, [r14+10h]
0x1401a6c6d  movups  xmm0, xmmword ptr [r15+10h]
0x1401a6c72  mov     rcx, [rax+28h]
0x1401a6c76  movdqu  xmmword ptr [rcx+rdi+68h], xmm0
0x1401a6c7c  mov     rax, [r14+10h]
0x1401a6c80  lea     rcx, [r15+70h]; struct _CRYPTOAPI_BLOB *
0x1401a6c84  mov     rdx, [rax+28h]
0x1401a6c88  add     rdx, 58h ; 'X'
0x1401a6c8c  add     rdx, rdi; struct _MINCRYPT_STRING *
0x1401a6c8f  call    ?I_MinCryptGetCommonName@@YAEPEAU_CRYPTOAPI_BLOB@@PEAU_MINCRYPT_STRING@@@Z; I_MinCryptGetCommonName(_CRYPTOAPI_BLOB *,_MINCRYPT_STRING *)
0x1401a6c94  mov     rax, [r14+10h]
0x1401a6c98  lea     rcx, [r15+0A0h]; struct _CRYPTOAPI_BLOB *
0x1401a6c9f  mov     rdx, [rax+28h]
0x1401a6ca3  add     rdx, 48h ; 'H'
0x1401a6ca7  add     rdx, rdi; struct _MINCRYPT_STRING *
0x1401a6caa  call    ?I_MinCryptGetCommonName@@YAEPEAU_CRYPTOAPI_BLOB@@PEAU_MINCRYPT_STRING@@@Z; I_MinCryptGetCommonName(_CRYPTOAPI_BLOB *,_MINCRYPT_STRING *)
0x1401a6caf  mov     rax, [r14+10h]
0x1401a6cb3  lea     r9, [rsp+270h+var_1F8]
0x1401a6cb8  mov     r8d, dword ptr [rsp+270h+Size]
0x1401a6cbd  mov     ecx, esi
0x1401a6cbf  mov     rdx, [rsp+270h+Buf1]
0x1401a6cc4  inc     dword ptr [rax+30h]
0x1401a6cc7  call    MinCryptIsCertificateRevoked
0x1401a6ccc  test    eax, eax
0x1401a6cce  jns     loc_1401A6D7F
0x1401a6cd4  cmp     [rsp+270h+var_230], 0
0x1401a6cd9  jnz     short loc_1401A6CE4
0x1401a6cdb  cmp     cs:?g_IgnoreFlightSigningEKU@@3EA, 0; uchar g_IgnoreFlightSigningEKU
0x1401a6ce2  jz      short loc_1401A6D63
0x1401a6ce4  mov     eax, [rsp+270h+var_22C]
0x1401a6ce8  lea     r15, cs:140000000h
0x1401a6cef  mov     r13, [rsp+270h+Buf1]
0x1401a6cf4  xor     esi, esi
0x1401a6cf6  mov     r12d, dword ptr [rsp+270h+Size]
0x1401a6cfb  xor     edi, edi
0x1401a6cfd  lea     r14d, [rsi+1]
0x1401a6d01  mov     rdx, rdi
0x1401a6d04  add     rdx, rdx
0x1401a6d07  cmp     eax, ds:rva dword_1401BD408[r15+rdx*8]
0x1401a6d0f  jnz     short loc_1401A6D3B
0x1401a6d11  mov     eax, ds:rva dword_1401BD40C[r15+rdx*8]
0x1401a6d19  cmp     r12d, eax
0x1401a6d1c  jnz     short loc_1401A6D37
0x1401a6d1e  mov     rdx, ds:rva off_1401BD410[r15+rdx*8]; Buf2
0x1401a6d26  mov     r8d, eax; Size
0x1401a6d29  mov     rcx, r13; Buf1
0x1401a6d2c  call    memcmp_0
0x1401a6d31  test    eax, eax
0x1401a6d33  cmovz   esi, r14d
0x1401a6d37  mov     eax, [rsp+270h+var_22C]
0x1401a6d3b  add     rdi, r14
0x1401a6d3e  cmp     rdi, 3
0x1401a6d42  jnz     short loc_1401A6D01
0x1401a6d44  mov     r14, [rbp+170h+var_1C8]
0x1401a6d48  mov     r15, [rsp+270h+var_200]
0x1401a6d4d  mov     r13, [rbp+170h+var_1E8]
0x1401a6d51  mov     r12, [rsp+270h+var_210]
0x1401a6d56  test    esi, esi
0x1401a6d58  jz      short loc_1401A6D63
0x1401a6d5a  cmp     cs:?g_TrustFlightSigning@@3EA, 0; uchar g_TrustFlightSigning
0x1401a6d61  jnz     short loc_1401A6D7F
0x1401a6d63  bts     dword ptr [r14+8], 15h
0x1401a6d69  mov     esi, 1
0x1401a6d6e  cmp     [rsp+270h+var_1F8], rbx
0x1401a6d73  mov     [rsp+270h+var_208], esi
0x1401a6d77  cmovl   rbx, [rsp+270h+var_1F8]
0x1401a6d7d  jmp     short loc_1401A6D84
0x1401a6d7f  mov     esi, 1
0x1401a6d84  mov     edi, dword ptr [rsp+270h+Size+4]
0x1401a6d88  test    edi, edi
0x1401a6d8a  jnz     short loc_1401A6E0B
0x1401a6d8c  test    r12, r12
0x1401a6d8f  jz      short loc_1401A6E0B
0x1401a6d91  mov     rax, [r14+10h]
0x1401a6d95  mov     rdx, [rsp+270h+Buf1]; Src
0x1401a6d9a  mov     rcx, [rax+28h]
0x1401a6d9e  movups  xmm0, xmmword ptr [rcx+58h]
0x1401a6da2  movdqu  xmmword ptr [r12+10h], xmm0
0x1401a6da9  mov     rax, [r14+10h]
0x1401a6dad  mov     rcx, [rax+28h]
0x1401a6db1  movups  xmm0, xmmword ptr [rcx+48h]
0x1401a6db5  lea     rcx, [r12+38h]; void *
0x1401a6dba  movdqu  xmmword ptr [r12+20h], xmm0
0x1401a6dc1  mov     eax, [r15+60h]
0x1401a6dc5  mov     [r12+88h], eax
0x1401a6dcd  mov     rax, [r15+68h]
0x1401a6dd1  mov     [r12+90h], rax
0x1401a6dd9  mov     eax, [rsp+270h+var_22C]
0x1401a6ddd  mov     [r12+30h], eax
0x1401a6de2  mov     eax, dword ptr [rsp+270h+Size]
0x1401a6de6  mov     r8d, eax; Size
0x1401a6de9  mov     [r12+34h], eax
0x1401a6dee  call    memcpy_0
0x1401a6df3  mov     eax, [r15+10h]
0x1401a6df7  mov     [r12+98h], eax
0x1401a6dff  mov     rax, [r15+18h]
0x1401a6e03  mov     [r12+0A0h], rax
0x1401a6e0b  mov     eax, [r15+70h]
0x1401a6e0f  cmp     eax, [r15+0A0h]
0x1401a6e16  jnz     short loc_1401A6E3B
0x1401a6e18  mov     rdx, [r15+0A8h]; Buf2
0x1401a6e1f  mov     r8d, eax; Size
0x1401a6e22  mov     rcx, [r15+78h]; Buf1
0x1401a6e26  call    memcmp_0
0x1401a6e2b  mov     ecx, [rsp+270h+var_21C]
0x1401a6e2f  test    eax, eax
0x1401a6e31  movzx   ecx, cl
0x1401a6e34  cmovz   ecx, esi
0x1401a6e37  mov     [rsp+270h+var_21C], ecx
0x1401a6e3b  mov     r8b, byte ptr [rsp+270h+var_21C]
0x1401a6e40  lea     rsi, [r14+8]
0x1401a6e44  mov     r9, rsi
0x1401a6e47  lea     rcx, [r15+0E0h]
0x1401a6e4e  mov     edx, edi
  ... truncated ...
```
