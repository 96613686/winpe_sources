# CryptXmlImportPublicKey

- ea: `0x1800013a0`
- end: `0x180001a32`
- name: `CryptXmlImportPublicKey`
- size: `1682`
- prototype: `HRESULT __stdcall(DWORD dwFlags, const CRYPT_XML_KEY_VALUE *pKeyValue, BCRYPT_KEY_HANDLE *phKey)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002470`

## callees

- `0x1800013a0`
- `0x1800070d0`
- `0x18000b1a0`
- `0x180012838`
- `0x180014ce0`
- `0x18001860d`
- `0x180018625`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001a02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001a02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001a19`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001a19`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000149d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800014ef`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000153e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000149d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800014ef`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000153e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800019f1`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800019f1`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800018c8`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800018c8`
- `bcrypt!BCryptImportKeyPair` at `0x180001931`
- `bcrypt!BCryptImportKeyPair` at `0x180001931`

## string_xrefs

- `0x18000142c`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x180001459`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x180001594`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x1800015fe`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x18000161d`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x1800016b9`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x1800017f6`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x18000183e`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x1800018da`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x180001944`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x18000198c`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x1800018f4`: `BCryptOpenAlgorithmProvider`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
HRESULT __stdcall CryptXmlImportPublicKey(
        DWORD dwFlags,
        const CRYPT_XML_KEY_VALUE *pKeyValue,
        BCRYPT_KEY_HANDLE *phKey)
{
  UCHAR *v4; // rsi
  HRESULT v6; // ebp
  const char *v7; // r8
  char v8; // al
  const char *v9; // rdx
  bool v10; // zf
  int v11; // r9d
  __int64 v12; // rcx
  const WCHAR *v13; // r12
  __int64 v14; // rdi
  ULONG v15; // r15d
  int *v16; // rax
  const WCHAR *v17; // r13
  size_t cbData; // r8
  BYTE *pbData; // rdx
  UCHAR *v20; // rcx
  const char *v21; // rax
  ULONG v22; // eax
  ULONG v23; // edi
  UCHAR *v24; // rax
  UCHAR *v25; // rcx
  __int64 v26; // rax
  UCHAR *v27; // rcx
  UCHAR *v28; // rax
  __int64 v29; // rcx
  UCHAR *v30; // rax
  UCHAR *v31; // rdi
  char v32; // al
  NTSTATUS v33; // eax
  const char *v34; // rax
  const char *v35; // rax
  int v36; // r10d
  char v37; // al
  HANDLE ProcessHeap; // rax
  ULONG v40; // [rsp+40h] [rbp-58h]
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-48h] BYREF
  int Size; // [rsp+A8h] [rbp+10h]
  ULONG Sizea; // [rsp+A8h] [rbp+10h]
  ULONG Sizeb; // [rsp+A8h] [rbp+10h]
  size_t Sizec; // [rsp+A8h] [rbp+10h]
  ULONG v46; // [rsp+B8h] [rbp+20h]
  UCHAR *v47; // [rsp+B8h] [rbp+20h]

  v4 = 0;
  phAlgorithm = 0;
  if ( !pKeyValue || !phKey )
  {
    v6 = -2147024809;
    v7 = "";
    while ( 1 )
    {
      v37 = *(v7 - 1);
      v9 = v7--;
      v10 = v37 == 92;
      if ( v37 == 92 )
        break;
      if ( v7 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp" )
      {
        v10 = v37 == 92;
        break;
      }
    }
    v11 = 2746;
    goto LABEL_61;
  }
  *phKey = 0;
  v6 = 1;
  if ( (dwFlags & 0x10000000) != 0 || (v6 = I_CryptXmlImportPublicKeyExtension(pKeyValue, phKey), v6 < 0) )
  {
    switch ( pKeyValue->dwType )
    {
      case 2u:
        v29 = pKeyValue->DSAKeyValue.P.cbData + 24;
        v15 = v29 + pKeyValue->DSAKeyValue.Q.cbData;
        v30 = (UCHAR *)CryptXmlAlloc(v29, v15);
        v31 = v30;
        if ( !v30 )
        {
          v6 = -2147024882;
          v7 = "";
          while ( 1 )
          {
            v32 = *(v7 - 1);
            v9 = v7--;
            v10 = v32 == 92;
            if ( v32 == 92 )
              break;
            if ( v7 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp" )
            {
              v10 = v32 == 92;
              break;
            }
          }
          v11 = 2875;
          goto LABEL_61;
        }
        *(_DWORD *)v30 = 826364754;
        v17 = L"RSAPUBLICBLOB";
        v13 = L"RSA";
        *((_DWORD *)v30 + 1) = 8 * pKeyValue->DSAKeyValue.P.cbData;
        v4 = v30;
        *((_DWORD *)v30 + 3) = pKeyValue->DSAKeyValue.P.cbData;
        *((_DWORD *)v30 + 2) = pKeyValue->DSAKeyValue.Q.cbData;
        memcpy_0(v30 + 24, pKeyValue->DSAKeyValue.Q.pbData, pKeyValue->DSAKeyValue.Q.cbData);
        cbData = pKeyValue->DSAKeyValue.P.cbData;
        pbData = pKeyValue->DSAKeyValue.P.pbData;
        v20 = &v31[pKeyValue->DSAKeyValue.Q.cbData + 24];
        break;
      case 1u:
        v22 = pKeyValue->DSAKeyValue.Y.cbData;
        Sizea = v22;
        if ( !v22
          || (v23 = pKeyValue->DSAKeyValue.P.cbData, v22 > v23)
          || (v46 = pKeyValue->DSAKeyValue.G.cbData, v46 > v23)
          || pKeyValue->DSAKeyValue.Counter.cbData > 4
          || pKeyValue->DSAKeyValue.Seed.cbData > 0x14
          || pKeyValue->DSAKeyValue.Q.cbData > 0x14 )
        {
          v6 = -2146885361;
          v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
          v11 = 2788;
          goto LABEL_63;
        }
        v15 = v23 + 2 * (v23 + 26);
        v24 = (UCHAR *)CryptXmlAlloc(*(_QWORD *)&dwFlags, v15);
        v25 = v24;
        if ( !v24 )
        {
          v6 = -2147024882;
          v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
          v11 = 2802;
          goto LABEL_63;
        }
        *(_DWORD *)v24 = 1112560452;
        v17 = L"DSAPUBLICBLOB";
        v13 = L"DSA";
        v40 = v23 - Sizea;
        v4 = v24;
        *((_DWORD *)v24 + 1) = pKeyValue->DSAKeyValue.P.cbData;
        v26 = pKeyValue->DSAKeyValue.Counter.cbData;
        Sizeb = v23 - v46;
        if ( (_DWORD)v26 )
        {
          memcpy_0(&v25[-v26 + 12], pKeyValue->DSAKeyValue.Counter.pbData, (unsigned int)v26);
          memcpy_0(v4 + 12, pKeyValue->DSAKeyValue.Seed.pbData, pKeyValue->DSAKeyValue.Seed.cbData);
          v25 = v4;
        }
        else
        {
          *((_DWORD *)v25 + 2) = -1;
        }
        memcpy_0(v25 + 32, pKeyValue->DSAKeyValue.Q.pbData, pKeyValue->DSAKeyValue.Q.cbData);
        memcpy_0(v4 + 52, pKeyValue->DSAKeyValue.P.pbData, pKeyValue->DSAKeyValue.P.cbData);
        v27 = &v4[pKeyValue->DSAKeyValue.P.cbData + 52];
        v47 = v27;
        if ( Sizeb )
        {
          memset_0(v27, 0, Sizeb);
          v27 = &v47[Sizeb];
          v47 = v27;
        }
        memcpy_0(v27, pKeyValue->DSAKeyValue.G.pbData, pKeyValue->DSAKeyValue.G.cbData);
        v28 = &v47[pKeyValue->DSAKeyValue.G.cbData];
        Sizec = (size_t)v28;
        if ( v40 )
        {
          memset_0(v28, 0, v40);
          v28 = (UCHAR *)(v40 + Sizec);
        }
        cbData = pKeyValue->DSAKeyValue.Y.cbData;
        v20 = v28;
        pbData = pKeyValue->DSAKeyValue.Y.pbData;
        break;
      case 3u:
        if ( pKeyValue->ECDSAKeyValue.ExplicitPara.cbData )
        {
          v6 = -2147467263;
          v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
          v11 = 2905;
LABEL_63:
          WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v6, v7, v11);
          goto LABEL_64;
        }
        if ( CompareStringW(0, 1u, pKeyValue->ECDSAKeyValue.wszNamedCurve, -1, String2, -1) == 2 )
        {
          Size = 827540293;
          v13 = L"ECDSA_P256";
          v14 = 32;
        }
        else if ( CompareStringW(0, 1u, pKeyValue->ECDSAKeyValue.wszNamedCurve, -1, aUrnOid13132034, -1) == 2 )
        {
          Size = 861094725;
          v13 = L"ECDSA_P384";
          v14 = 48;
        }
        else
        {
          if ( CompareStringW(0, 1u, pKeyValue->ECDSAKeyValue.wszNamedCurve, -1, Src, -1) != 2 )
          {
            v6 = -2147467263;
            v21 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
            WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %S", -2147467263, v21, 2935, pKeyValue->ECDSAKeyValue.wszNamedCurve);
            goto LABEL_64;
          }
          Size = 894649157;
          v13 = L"ECDSA_P521";
          v14 = 66;
        }
        if ( pKeyValue->ECDSAKeyValue.X.cbData > (unsigned int)v14
          || pKeyValue->ECDSAKeyValue.Y.cbData > (unsigned int)v14 )
        {
          v6 = -2146885361;
          v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
          v11 = 2947;
          goto LABEL_63;
        }
        v15 = 2 * v14 + 8;
        v16 = (int *)CryptXmlAlloc(v12, v15);
        if ( !v16 )
        {
          v6 = -2147024882;
          v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
          v11 = 2961;
          goto LABEL_63;
        }
        v17 = L"ECCPUBLICBLOB";
        *v16 = Size;
        v4 = (UCHAR *)v16;
        v16[1] = v14;
        memcpy_0(
          (char *)v16 + v14 - pKeyValue->ECDSAKeyValue.X.cbData + 8,
          pKeyValue->ECDSAKeyValue.X.pbData,
          pKeyValue->ECDSAKeyValue.X.cbData);
        cbData = pKeyValue->ECDSAKeyValue.Y.cbData;
        pbData = pKeyValue->ECDSAKeyValue.Y.pbData;
        v20 = &v4[2 * v14 + 8 - cbData];
        break;
      default:
        v6 = -2147467263;
        v7 = "";
        while ( 1 )
        {
          v8 = *(v7 - 1);
          v9 = v7--;
          v10 = v8 == 92;
          if ( v8 == 92 )
            break;
          if ( v7 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp" )
          {
            v10 = v8 == 92;
            break;
          }
        }
        v11 = 2984;
LABEL_61:
        if ( v10 )
          v7 = v9;
        goto LABEL_63;
    }
    memcpy_0(v20, pbData, cbData);
    v33 = BCryptOpenAlgorithmProvider(&phAlgorithm, v13, 0, 0);
    if ( v33 >= 0 )
    {
      if ( BCryptImportKeyPair(phAlgorithm, 0, v17, phKey, v4, v15, 0) < 0 )
      {
        v35 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %s", v36 | 0x10000000, v35, 3013, "BCryptImportKeyPair");
        v6 = -2146885361;
      }
    }
    else
    {
      v6 = v33 | 0x10000000;
      v34 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %s", v6, v34, 2998, "BCryptOpenAlgorithmProvider");
    }
  }
LABEL_64:
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 8u, v4);
  }
  return v6;
}

```

## disassembly

```asm
0x1800013a0  mov     r11, rsp
0x1800013a3  push    rbp
0x1800013a4  push    rsi
0x1800013a5  sub     rsp, 88h
0x1800013ac  mov     [r11+8], rbx
0x1800013b0  xor     eax, eax
0x1800013b2  mov     [r11-18h], rdi
0x1800013b6  mov     rbx, rdx
0x1800013b9  mov     [r11-20h], r12
0x1800013bd  mov     esi, eax
0x1800013bf  mov     [r11-28h], r13
0x1800013c3  mov     [r11-30h], r14
0x1800013c7  mov     r14, r8
0x1800013ca  mov     [r11-38h], r15
0x1800013ce  mov     [r11-48h], rax
0x1800013d2  test    rdx, rdx
0x1800013d5  jz      loc_180001980
0x1800013db  test    r8, r8
0x1800013de  jz      loc_180001980
0x1800013e4  mov     [r8], rax
0x1800013e7  mov     ebp, 1
0x1800013ec  bt      ecx, 1Ch
0x1800013f0  jb      short loc_180001407
0x1800013f2  mov     rdx, r8
0x1800013f5  mov     rcx, rbx
0x1800013f8  call    I_CryptXmlImportPublicKeyExtension
0x1800013fd  mov     ebp, eax
0x1800013ff  test    eax, eax
0x180001401  jns     loc_1800019C1
0x180001407  mov     eax, [rbx]
0x180001409  cmp     eax, 2
0x18000140c  jz      loc_180001815
0x180001412  sub     eax, 1
0x180001415  jz      loc_180001653
0x18000141b  cmp     eax, 2
0x18000141e  jz      short loc_180001454
0x180001420  mov     ebp, 80004001h
0x180001425  lea     r8, aOnecoreDsSecur_6+30h; ""
0x18000142c  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180001433  movzx   eax, byte ptr [r8-1]
0x180001438  mov     rdx, r8
0x18000143b  dec     r8
0x18000143e  cmp     al, 5Ch ; '\'
0x180001440  jz      short loc_180001449
0x180001442  cmp     r8, rcx
0x180001445  ja      short loc_180001433
0x180001447  cmp     al, 5Ch ; '\'
0x180001449  mov     r9d, 0BA8h
0x18000144f  jmp     loc_1800019AF
0x180001454  cmp     [rbx+34h], esi
0x180001457  jbe     short loc_180001478
0x180001459  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180001460  mov     ebp, 80004001h
0x180001465  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000146a  mov     r8, rax
0x18000146d  mov     r9d, 0B59h
0x180001473  jmp     loc_1800019B3
0x180001478  mov     r8, [rbx+8]; lpString1
0x18000147c  lea     rax, String2; "urn:oid:1.2.840.10045.3.1.7"
0x180001483  mov     [rsp+98h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000148b  mov     r9d, 0FFFFFFFFh; cchCount1
0x180001491  mov     edx, 1; dwCmpFlags
0x180001496  mov     [rsp+98h+lpString2], rax; lpString2
0x18000149b  xor     ecx, ecx; Locale
0x18000149d  call    cs:__imp_CompareStringW
0x1800014a4  nop     dword ptr [rax+rax+00h]
0x1800014a9  cmp     eax, 2
0x1800014ac  jnz     short loc_1800014CA
0x1800014ae  mov     dword ptr [rsp+98h+Size], 31534345h
0x1800014b9  lea     r12, pszAlgId; "ECDSA_P256"
0x1800014c0  mov     edi, 20h ; ' '
0x1800014c5  jmp     loc_18000156A
0x1800014ca  mov     r8, [rbx+8]; lpString1
0x1800014ce  lea     rax, aUrnOid13132034; "urn:oid:1.3.132.0.34"
0x1800014d5  mov     [rsp+98h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800014dd  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800014e3  mov     edx, 1; dwCmpFlags
0x1800014e8  mov     [rsp+98h+lpString2], rax; lpString2
0x1800014ed  xor     ecx, ecx; Locale
0x1800014ef  call    cs:__imp_CompareStringW
0x1800014f6  nop     dword ptr [rax+rax+00h]
0x1800014fb  cmp     eax, 2
0x1800014fe  jnz     short loc_180001519
0x180001500  mov     dword ptr [rsp+98h+Size], 33534345h
0x18000150b  lea     r12, aEcdsaP384; "ECDSA_P384"
0x180001512  mov     edi, 30h ; '0'
0x180001517  jmp     short loc_18000156A
0x180001519  mov     r8, [rbx+8]; lpString1
0x18000151d  lea     rax, Src; "urn:oid:1.3.132.0.35"
0x180001524  mov     [rsp+98h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000152c  mov     r9d, 0FFFFFFFFh; cchCount1
0x180001532  mov     edx, 1; dwCmpFlags
0x180001537  mov     [rsp+98h+lpString2], rax; lpString2
0x18000153c  xor     ecx, ecx; Locale
0x18000153e  call    cs:__imp_CompareStringW
0x180001545  nop     dword ptr [rax+rax+00h]
0x18000154a  cmp     eax, 2
0x18000154d  jnz     loc_18000161D
0x180001553  mov     dword ptr [rsp+98h+Size], 35534345h
0x18000155e  lea     r12, aEcdsaP521; "ECDSA_P521"
0x180001565  mov     edi, 42h ; 'B'
0x18000156a  cmp     [rbx+10h], edi
0x18000156d  ja      loc_1800015FE
0x180001573  cmp     [rbx+20h], edi
0x180001576  ja      loc_1800015FE
0x18000157c  lea     r15d, ds:8[rdi*2]
0x180001584  mov     edx, r15d
0x180001587  call    CryptXmlAlloc
0x18000158c  mov     rcx, rax
0x18000158f  test    rax, rax
0x180001592  jnz     short loc_1800015B3
0x180001594  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000159b  mov     ebp, 8007000Eh
0x1800015a0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800015a5  mov     r8, rax
0x1800015a8  mov     r9d, 0B91h
0x1800015ae  jmp     loc_1800019B3
0x1800015b3  mov     eax, dword ptr [rsp+98h+Size]
0x1800015ba  lea     r13, pszBlobType; "ECCPUBLICBLOB"
0x1800015c1  mov     [rcx], eax
0x1800015c3  mov     rsi, rcx
0x1800015c6  mov     [rcx+4], edi
0x1800015c9  mov     rax, rdi
0x1800015cc  mov     r8d, [rbx+10h]; Size
0x1800015d0  mov     rdx, [rbx+18h]; Src
0x1800015d4  sub     rax, r8
0x1800015d7  add     rax, 8
0x1800015db  add     rcx, rax; void *
0x1800015de  call    memcpy_0
0x1800015e3  mov     r8d, [rbx+20h]
0x1800015e7  lea     rcx, ds:8[rdi*2]
0x1800015ef  mov     rdx, [rbx+28h]
0x1800015f3  sub     rcx, r8
0x1800015f6  add     rcx, rsi
0x1800015f9  jmp     loc_1800018B5
0x1800015fe  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180001605  mov     ebp, 8009210Fh
0x18000160a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000160f  mov     r8, rax
0x180001612  mov     r9d, 0B83h
0x180001618  jmp     loc_1800019B3
0x18000161d  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180001624  mov     ebp, 80004001h
0x180001629  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000162e  mov     rcx, [rbx+8]
0x180001632  mov     r9d, 0B77h
0x180001638  mov     [rsp+98h+lpString2], rcx
0x18000163d  mov     r8, rax
0x180001640  lea     rcx, aError0x08xSUS_0; "ERROR  : (0x%08x) %s:%u : %S"
0x180001647  mov     edx, ebp
0x180001649  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000164e  jmp     loc_1800019C1
0x180001653  mov     eax, [rbx+38h]
0x180001656  mov     dword ptr [rsp+98h+Size], eax
0x18000165d  cmp     eax, 1
0x180001660  jb      loc_1800017F6
0x180001666  mov     edi, [rbx+8]
0x180001669  cmp     eax, edi
0x18000166b  ja      loc_1800017F6
0x180001671  mov     eax, [rbx+28h]
0x180001674  mov     dword ptr [rsp+98h+arg_18], eax
0x18000167b  cmp     eax, edi
0x18000167d  ja      loc_1800017F6
0x180001683  cmp     dword ptr [rbx+68h], 4
0x180001687  ja      loc_1800017F6
0x18000168d  cmp     dword ptr [rbx+58h], 14h
0x180001691  ja      loc_1800017F6
0x180001697  cmp     dword ptr [rbx+18h], 14h
0x18000169b  ja      loc_1800017F6
0x1800016a1  lea     r15d, [rdi+1Ah]
0x1800016a5  lea     r15d, [rdi+r15*2]
0x1800016a9  mov     edx, r15d
0x1800016ac  call    CryptXmlAlloc
0x1800016b1  mov     rcx, rax
0x1800016b4  test    rax, rax
0x1800016b7  jnz     short loc_1800016D8
0x1800016b9  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800016c0  mov     ebp, 8007000Eh
0x1800016c5  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800016ca  mov     r8, rax
0x1800016cd  mov     r9d, 0AF2h
0x1800016d3  jmp     loc_1800019B3
0x1800016d8  mov     eax, edi
0x1800016da  mov     dword ptr [rcx], 42505344h
0x1800016e0  sub     eax, dword ptr [rsp+98h+Size]
0x1800016e7  lea     r13, aDsapublicblob; "DSAPUBLICBLOB"
0x1800016ee  sub     edi, dword ptr [rsp+98h+arg_18]
0x1800016f5  lea     r12, aDsa; "DSA"
0x1800016fc  mov     [rsp+98h+var_58], eax
0x180001700  mov     rsi, rcx
0x180001703  mov     eax, [rbx+8]
0x180001706  mov     [rcx+4], eax
0x180001709  mov     eax, [rbx+68h]
0x18000170c  mov     dword ptr [rsp+98h+Size], edi
0x180001713  test    eax, eax
0x180001715  jz      short loc_180001740
0x180001717  mov     rdx, [rbx+70h]; Src
0x18000171b  sub     rcx, rax
0x18000171e  add     rcx, 0Ch; void *
0x180001722  mov     r8d, eax; Size
0x180001725  call    memcpy_0
0x18000172a  mov     r8d, [rbx+58h]; Size
0x18000172e  lea     rcx, [rsi+0Ch]; void *
0x180001732  mov     rdx, [rbx+60h]; Src
0x180001736  call    memcpy_0
0x18000173b  mov     rcx, rsi
0x18000173e  jmp     short loc_180001747
0x180001740  mov     dword ptr [rcx+8], 0FFFFFFFFh
0x180001747  mov     r8d, [rbx+18h]; Size
0x18000174b  add     rcx, 20h ; ' '; void *
0x18000174f  mov     rdx, [rbx+20h]; Src
0x180001753  call    memcpy_0
0x180001758  mov     r8d, [rbx+8]; Size
0x18000175c  lea     rdi, [rsi+34h]
0x180001760  mov     rdx, [rbx+10h]; Src
0x180001764  mov     rcx, rdi; void *
0x180001767  call    memcpy_0
0x18000176c  mov     ecx, [rbx+8]
0x18000176f  mov     eax, dword ptr [rsp+98h+Size]
0x180001776  add     rcx, rdi; void *
0x180001779  mov     [rsp+98h+arg_18], rcx
0x180001781  test    eax, eax
0x180001783  jz      short loc_1800017A4
0x180001785  mov     r8d, eax; Size
0x180001788  xor     edx, edx; Val
0x18000178a  mov     edi, eax
0x18000178c  call    memset_0
0x180001791  mov     rcx, [rsp+98h+arg_18]
0x180001799  add     rcx, rdi; void *
0x18000179c  mov     [rsp+98h+arg_18], rcx
0x1800017a4  mov     r8d, [rbx+28h]; Size
0x1800017a8  mov     rdx, [rbx+30h]; Src
0x1800017ac  call    memcpy_0
0x1800017b1  mov     eax, [rbx+28h]
0x1800017b4  add     rax, [rsp+98h+arg_18]
0x1800017bc  mov     ecx, [rsp+98h+var_58]
0x1800017c0  mov     [rsp+98h+Size], rax
0x1800017c8  test    ecx, ecx
0x1800017ca  jz      short loc_1800017E6
0x1800017cc  mov     edi, ecx
0x1800017ce  mov     r8d, ecx; Size
0x1800017d1  mov     rcx, rax; void *
0x1800017d4  xor     edx, edx; Val
0x1800017d6  call    memset_0
0x1800017db  mov     rax, [rsp+98h+Size]
0x1800017e3  add     rax, rdi
0x1800017e6  mov     r8d, [rbx+38h]
0x1800017ea  mov     rcx, rax
0x1800017ed  mov     rdx, [rbx+40h]
0x1800017f1  jmp     loc_1800018B5
0x1800017f6  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800017fd  mov     ebp, 8009210Fh
0x180001802  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180001807  mov     r8, rax
0x18000180a  mov     r9d, 0AE4h
0x180001810  jmp     loc_1800019B3
0x180001815  mov     ecx, [rbx+8]
0x180001818  mov     r15d, [rbx+18h]
0x18000181c  add     ecx, 18h
0x18000181f  add     r15d, ecx
0x180001822  mov     edx, r15d
0x180001825  call    CryptXmlAlloc
0x18000182a  mov     rdi, rax
0x18000182d  test    rax, rax
0x180001830  jnz     short loc_180001866
0x180001832  mov     ebp, 8007000Eh
0x180001837  lea     r8, aOnecoreDsSecur_6+30h; ""
0x18000183e  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180001845  movzx   eax, byte ptr [r8-1]
0x18000184a  mov     rdx, r8
0x18000184d  dec     r8
0x180001850  cmp     al, 5Ch ; '\'
0x180001852  jz      short loc_18000185B
0x180001854  cmp     r8, rcx
0x180001857  ja      short loc_180001845
0x180001859  cmp     al, 5Ch ; '\'
0x18000185b  mov     r9d, 0B3Bh
0x180001861  jmp     loc_1800019AF
0x180001866  mov     dword ptr [rax], 31415352h
0x18000186c  lea     rcx, [rdi+18h]; void *
0x180001870  mov     eax, [rbx+8]
0x180001873  lea     r13, aRsapublicblob; "RSAPUBLICBLOB"
0x18000187a  shl     eax, 3
0x18000187d  lea     r12, aRsa; "RSA"
0x180001884  mov     [rdi+4], eax
0x180001887  mov     rsi, rdi
0x18000188a  mov     eax, [rbx+8]
0x18000188d  mov     [rdi+0Ch], eax
0x180001890  mov     eax, [rbx+18h]
0x180001893  mov     [rdi+8], eax
0x180001896  mov     r8d, [rbx+18h]; Size
0x18000189a  mov     rdx, [rbx+20h]; Src
0x18000189e  call    memcpy_0
0x1800018a3  mov     ecx, [rbx+18h]
0x1800018a6  mov     r8d, [rbx+8]; Size
0x1800018aa  add     rcx, 18h
0x1800018ae  mov     rdx, [rbx+10h]; Src
0x1800018b2  add     rcx, rdi; void *
0x1800018b5  call    memcpy_0
0x1800018ba  xor     r9d, r9d; dwFlags
  ... truncated ...
```
