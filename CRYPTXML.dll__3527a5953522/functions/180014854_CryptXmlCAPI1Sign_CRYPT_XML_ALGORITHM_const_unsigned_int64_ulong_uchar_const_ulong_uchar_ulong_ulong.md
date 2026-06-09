# CryptXmlCAPI1Sign(_CRYPT_XML_ALGORITHM const *,unsigned __int64,ulong,uchar const *,ulong,uchar *,ulong,ulong *)

- ea: `0x180014854`
- end: `0x180014cda`
- name: `?CryptXmlCAPI1Sign@@YAJPEBU_CRYPT_XML_ALGORITHM@@_KKPEBEKPEAEKPEAK@Z`
- size: `1158`
- prototype: `int(const struct _CRYPT_XML_ALGORITHM *, unsigned __int64, unsigned int, const unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007730`

## callees

- `0x1800070d0`
- `0x18000f200`
- `0x180014854`
- `0x180014ce0`
- `0x180017b30`
- `0x180017b84`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800149c3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800149c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014955`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014955`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c9d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800148ed`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800149a6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180014c5a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800148ed`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800149a6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180014c5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bfb`
- `CRYPTSP!CryptCreateHash` at `0x180014a63`
- `CRYPTSP!CryptCreateHash` at `0x180014a63`
- `CRYPTSP!CryptHashData` at `0x180014b7f`
- `CRYPTSP!CryptHashData` at `0x180014b7f`
- `CRYPTSP!CryptDestroyHash` at `0x180014cb2`
- `CRYPTSP!CryptDestroyHash` at `0x180014cb2`
- `CRYPTSP!CryptSignHashW` at `0x180014beb`
- `CRYPTSP!CryptSignHashW` at `0x180014beb`

## string_xrefs

- `0x18001489d`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x180014a92`: `onecore\ds\security\cryptoapi\xml\lib\capi1.cpp`
- `0x180014b38`: `onecore\ds\security\cryptoapi\xml\lib\capi1.cpp`
- `0x180014baa`: `onecore\ds\security\cryptoapi\xml\lib\capi1.cpp`
- `0x180014c16`: `onecore\ds\security\cryptoapi\xml\lib\capi1.cpp`
- `0x180014aa7`: `CryptCreateHash`

## pseudocode

```c
__int64 __fastcall CryptXmlCAPI1Sign(
        const struct _CRYPT_XML_ALGORITHM *a1,
        HCRYPTPROV a2,
        DWORD a3,
        const unsigned __int8 *a4,
        DWORD dwDataLen,
        unsigned __int8 *pbSignature,
        unsigned int a7,
        unsigned int *pdwSigLen)
{
  unsigned int *v9; // rsi
  __int64 i; // rbx
  int (__fastcall *v12)(const struct _CRYPT_XML_ALGORITHM *, HLOCAL *); // rax
  const char *v13; // rax
  int v14; // r10d
  __int64 j; // rbx
  _OWORD *v16; // rax
  signed int LastError; // eax
  signed int v18; // ebx
  const char *v19; // rax
  const char *v20; // r10
  __int64 v21; // r9
  ALG_ID LegacyAlgId; // eax
  signed int v23; // eax
  const char *v24; // r8
  int v25; // r9d
  const char *v26; // rax
  const char *v27; // rax
  const char *v28; // rcx
  const char *v29; // r8
  const char *v30; // rax
  bool v31; // zf
  signed int v32; // eax
  unsigned __int8 *v33; // rdi
  DWORD v34; // edx
  HCRYPTHASH v35; // rcx
  signed int v36; // eax
  __int64 v37; // rbx
  unsigned __int8 *v38; // rcx
  unsigned int v39; // edx
  BYTE *lpString2; // [rsp+20h] [rbp-20h]
  HCRYPTHASH phHash[2]; // [rsp+30h] [rbp-10h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp+40h] BYREF
  HCRYPTPROV hProv; // [rsp+88h] [rbp+48h]
  DWORD dwKeySpec; // [rsp+90h] [rbp+50h]

  dwKeySpec = a3;
  hProv = a2;
  v31 = dword_180022FC8 == 0;
  v9 = pdwSigLen;
  phHash[0] = 0;
  hMem = 0;
  *pdwSigLen = 0;
  if ( v31 )
    LoadRegExtensions();
  if ( a1 )
  {
    hMem = 0;
    for ( i = 0; (unsigned int)i < dword_180022FC0; i = (unsigned int)(i + 1) )
    {
      if ( CompareStringW(0, 1u, a1->wszAlgorithm, -1, *(PCNZWCH *)(*((_QWORD *)qword_180022FD8 + i) + 8LL), -1) == 2 )
      {
        v12 = *(int (__fastcall **)(const struct _CRYPT_XML_ALGORITHM *, HLOCAL *))(*((_QWORD *)qword_180022FD8 + i)
                                                                                  + 152LL);
        if ( v12 )
        {
          if ( v12(a1, &hMem) >= 0 )
            goto LABEL_21;
          v13 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
          WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v14, v13, 1118);
          if ( hMem )
          {
            LocalFree(hMem);
            hMem = 0;
          }
        }
      }
    }
    for ( j = 0; ; j = (unsigned int)(j + 1) )
    {
      if ( (unsigned int)j >= 0x11 )
      {
        v18 = -2146885372;
        v27 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885372, v27, 1167);
        goto LABEL_33;
      }
      if ( CompareStringW(0, 1u, a1->wszAlgorithm, -1, (PCNZWCH)qword_180022180[9 * j + 1], -1) == 2 )
        break;
    }
    v16 = LocalAlloc(0x40u, 0x48u);
    hMem = v16;
    if ( v16 )
    {
      *v16 = *(_OWORD *)&qword_180022180[9 * j];
      v16[1] = *(_OWORD *)&qword_180022180[9 * j + 2];
      v16[2] = *(_OWORD *)&qword_180022180[9 * j + 4];
      v16[3] = *(_OWORD *)&qword_180022180[9 * j + 6];
      *((_QWORD *)v16 + 8) = qword_180022180[9 * j + 8];
      goto LABEL_21;
    }
    LastError = GetLastError();
    v18 = LastError;
    if ( LastError > 0 )
      v18 = (unsigned __int16)LastError | 0x80070000;
    v19 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
    v21 = 1155;
  }
  else
  {
    v18 = -2147024809;
    v19 = "";
    do
      v28 = v19--;
    while ( *v19 != 92 && v19 > "onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp" );
    v20 = "ERROR  : (0x%08x) %s:%u";
    v21 = 1086;
    if ( *v19 == 92 )
      v19 = v28;
  }
  WPPTraceLogA(v20, (unsigned int)v18, v19, v21);
  if ( v18 >= 0 )
  {
LABEL_21:
    LegacyAlgId = GetLegacyAlgId(*((PCNZWCH *)hMem + 4));
    if ( !CryptCreateHash(hProv, LegacyAlgId, 0, 0, phHash) )
    {
      v23 = GetLastError();
      v18 = v23;
      if ( v23 > 0 )
        v18 = (unsigned __int16)v23 | 0x80070000;
      v24 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\capi1.cpp");
      v25 = 119;
      v26 = "CryptCreateHash";
LABEL_25:
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %s", v18, v24, v25, v26);
      goto LABEL_54;
    }
    if ( !CryptHashData(phHash[0], a4, dwDataLen, 0) )
    {
      v32 = GetLastError();
      v18 = v32;
      if ( v32 > 0 )
        v18 = (unsigned __int16)v32 | 0x80070000;
      v24 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\capi1.cpp");
      v25 = 131;
      v26 = "CryptHashData";
      goto LABEL_25;
    }
    v33 = pbSignature;
    v34 = dwKeySpec;
    v35 = phHash[0];
    lpString2 = pbSignature;
    *v9 = a7;
    if ( !CryptSignHashW(v35, v34, 0, 0, lpString2, v9) )
    {
      v36 = GetLastError();
      v18 = v36;
      if ( v36 > 0 )
        v18 = (unsigned __int16)v36 | 0x80070000;
      v24 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\capi1.cpp");
      v25 = 150;
      v26 = "CryptSignHash";
      goto LABEL_25;
    }
    if ( CompareStringW(0, 1u, *((PCNZWCH *)hMem + 5), -1, L"DSA", -1) == 2 )
    {
      v37 = *v9 >> 1;
      I_ReverseBuffer(v33, *v9 >> 1);
      v38 = &v33[v37];
      v39 = v37;
    }
    else
    {
      if ( !v33 )
      {
LABEL_53:
        v18 = 0;
        goto LABEL_54;
      }
      v39 = *v9;
      v38 = v33;
    }
    I_ReverseBuffer(v38, v39);
    goto LABEL_53;
  }
LABEL_33:
  v29 = "";
  while ( 1 )
  {
    v30 = v29--;
    v31 = *v29 == 92;
    if ( *v29 == 92 )
      break;
    if ( v29 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\capi1.cpp" )
    {
      v31 = *v29 == 92;
      break;
    }
  }
  if ( v31 )
    v29 = v30;
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v18, v29, 102);
LABEL_54:
  if ( hMem )
    LocalFree(hMem);
  if ( phHash[0] )
    CryptDestroyHash(phHash[0]);
  if ( v18 < 0 )
    return (unsigned int)-2146885364;
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180014854  mov     [rsp-38h+dwKeySpec], r8d
0x180014859  mov     [rsp-38h+hProv], rdx
0x18001485e  push    rbp
0x18001485f  push    rbx
0x180014860  push    rsi
0x180014861  push    rdi
0x180014862  push    r12
0x180014864  push    r13
0x180014866  push    r15
0x180014868  mov     rbp, rsp
0x18001486b  sub     rsp, 40h
0x18001486f  cmp     cs:dword_180022FC8, 0
0x180014876  mov     r12, r9
0x180014879  mov     rsi, [rbp+pdwSigLen]
0x18001487d  mov     r13, rcx
0x180014880  mov     [rbp+phHash], 0
0x180014888  mov     [rbp+hMem], 0
0x180014890  mov     dword ptr [rsi], 0
0x180014896  jnz     short loc_18001489D
0x180014898  call    _LoadRegExtensions
0x18001489d  lea     r15, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800148a4  test    r13, r13
0x1800148a7  jz      loc_180014AEC
0x1800148ad  mov     [rbp+hMem], 0
0x1800148b5  xor     ebx, ebx
0x1800148b7  cmp     ebx, cs:dword_180022FC0
0x1800148bd  jnb     loc_180014970
0x1800148c3  mov     rax, cs:qword_180022FD8
0x1800148ca  or      r9d, 0FFFFFFFFh; cchCount1
0x1800148ce  mov     r8, [r13+8]; lpString1
0x1800148d2  xor     ecx, ecx; Locale
0x1800148d4  mov     [rsp+40h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800148dc  mov     rax, [rax+rbx*8]
0x1800148e0  lea     edx, [r9+2]; dwCmpFlags
0x1800148e4  mov     rax, [rax+8]
0x1800148e8  mov     [rsp+40h+lpString2], rax; lpString2
0x1800148ed  call    cs:__imp_CompareStringW
0x1800148f4  nop     dword ptr [rax+rax+00h]
0x1800148f9  cmp     eax, 2
0x1800148fc  jnz     short loc_180014969
0x1800148fe  mov     rax, cs:qword_180022FD8
0x180014905  mov     rcx, [rax+rbx*8]
0x180014909  mov     rax, [rcx+98h]
0x180014910  test    rax, rax
0x180014913  jz      short loc_180014969
0x180014915  lea     rdx, [rbp+hMem]
0x180014919  mov     rcx, r13
0x18001491c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014921  mov     r10d, eax
0x180014924  test    eax, eax
0x180014926  jns     loc_180014A41
0x18001492c  mov     rcx, r15; char *
0x18001492f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180014934  mov     r8, rax
0x180014937  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18001493e  mov     edx, r10d
0x180014941  mov     r9d, 45Eh
0x180014947  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18001494c  mov     rcx, [rbp+hMem]; hMem
0x180014950  test    rcx, rcx
0x180014953  jz      short loc_180014969
0x180014955  call    cs:__imp_LocalFree
0x18001495c  nop     dword ptr [rax+rax+00h]
0x180014961  mov     [rbp+hMem], 0
0x180014969  inc     ebx
0x18001496b  jmp     loc_1800148B7
0x180014970  xor     ebx, ebx
0x180014972  lea     rcx, qword_180022180
0x180014979  cmp     ebx, 11h
0x18001497c  jnb     loc_180014AC6
0x180014982  mov     r8, [r13+8]; lpString1
0x180014986  lea     rdi, [rbx+rbx*8]
0x18001498a  mov     rax, [rcx+rdi*8+8]
0x18001498f  or      r9d, 0FFFFFFFFh; cchCount1
0x180014993  mov     [rsp+40h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001499b  xor     ecx, ecx; Locale
0x18001499d  mov     [rsp+40h+lpString2], rax; lpString2
0x1800149a2  lea     edx, [r9+2]; dwCmpFlags
0x1800149a6  call    cs:__imp_CompareStringW
0x1800149ad  nop     dword ptr [rax+rax+00h]
0x1800149b2  cmp     eax, 2
0x1800149b5  jz      short loc_1800149BB
0x1800149b7  inc     ebx
0x1800149b9  jmp     short loc_180014972
0x1800149bb  mov     edx, 48h ; 'H'; uBytes
0x1800149c0  lea     ecx, [rdx-8]; uFlags
0x1800149c3  call    cs:__imp_LocalAlloc
0x1800149ca  nop     dword ptr [rax+rax+00h]
0x1800149cf  mov     [rbp+hMem], rax
0x1800149d3  test    rax, rax
0x1800149d6  jnz     short loc_180014A0D
0x1800149d8  call    cs:__imp_GetLastError
0x1800149df  nop     dword ptr [rax+rax+00h]
0x1800149e4  mov     ebx, eax
0x1800149e6  test    eax, eax
0x1800149e8  jle     short loc_1800149F3
0x1800149ea  movzx   ebx, ax
0x1800149ed  or      ebx, 80070000h
0x1800149f3  mov     rcx, r15; char *
0x1800149f6  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800149fd  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180014a02  mov     r9d, 483h
0x180014a08  jmp     loc_180014B1C
0x180014a0d  lea     rcx, qword_180022180
0x180014a14  movups  xmm0, xmmword ptr [rcx+rdi*8]
0x180014a18  movups  xmmword ptr [rax], xmm0
0x180014a1b  movups  xmm1, xmmword ptr [rcx+rdi*8+10h]
0x180014a20  movups  xmmword ptr [rax+10h], xmm1
0x180014a24  movups  xmm0, xmmword ptr [rcx+rdi*8+20h]
0x180014a29  movups  xmmword ptr [rax+20h], xmm0
0x180014a2d  movups  xmm1, xmmword ptr [rcx+rdi*8+30h]
0x180014a32  movups  xmmword ptr [rax+30h], xmm1
0x180014a36  movsd   xmm0, qword ptr [rcx+rdi*8+40h]
0x180014a3c  movsd   qword ptr [rax+40h], xmm0
0x180014a41  mov     rcx, [rbp+hMem]
0x180014a45  mov     rcx, [rcx+20h]; lpString1
0x180014a49  call    _GetLegacyAlgId
0x180014a4e  mov     rcx, [rbp+hProv]; hProv
0x180014a52  mov     edx, eax; Algid
0x180014a54  lea     rax, [rbp+phHash]
0x180014a58  xor     r9d, r9d; dwFlags
0x180014a5b  xor     r8d, r8d; hKey
0x180014a5e  mov     [rsp+40h+lpString2], rax; phHash
0x180014a63  call    cs:__imp_CryptCreateHash
0x180014a6a  nop     dword ptr [rax+rax+00h]
0x180014a6f  test    eax, eax
0x180014a71  jnz     loc_180014B71
0x180014a77  call    cs:__imp_GetLastError
0x180014a7e  nop     dword ptr [rax+rax+00h]
0x180014a83  mov     ebx, eax
0x180014a85  test    eax, eax
0x180014a87  jle     short loc_180014A92
0x180014a89  movzx   ebx, ax
0x180014a8c  or      ebx, 80070000h
0x180014a92  lea     rcx, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180014a99  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180014a9e  mov     r8, rax
0x180014aa1  mov     r9d, 77h ; 'w'
0x180014aa7  lea     rax, aCryptcreatehas_0; "CryptCreateHash"
0x180014aae  mov     edx, ebx
0x180014ab0  mov     [rsp+40h+lpString2], rax
0x180014ab5  lea     rcx, aError0x08xSUS; "ERROR  : (0x%08x) %s:%u : %s"
0x180014abc  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180014ac1  jmp     loc_180014C94
0x180014ac6  mov     rcx, r15; char *
0x180014ac9  mov     ebx, 80092104h
0x180014ace  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180014ad3  mov     r8, rax
0x180014ad6  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180014add  mov     edx, ebx
0x180014adf  mov     r9d, 48Fh
0x180014ae5  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180014aea  jmp     short loc_180014B31
0x180014aec  mov     ebx, 80070057h
0x180014af1  lea     rax, aOnecoreDsSecur_6+30h; ""
0x180014af8  mov     rcx, rax
0x180014afb  dec     rax
0x180014afe  cmp     byte ptr [rax], 5Ch ; '\'
0x180014b01  jz      short loc_180014B08
0x180014b03  cmp     rax, r15
0x180014b06  ja      short loc_180014AF8
0x180014b08  cmp     byte ptr [rax], 5Ch ; '\'
0x180014b0b  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180014b12  mov     r9d, 43Eh
0x180014b18  cmovz   rax, rcx
0x180014b1c  mov     r8, rax
0x180014b1f  mov     edx, ebx
0x180014b21  mov     rcx, r10; char *
0x180014b24  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180014b29  test    ebx, ebx
0x180014b2b  jns     loc_180014A41
0x180014b31  lea     r8, aOnecoreDsSecur_10+2Fh; ""
0x180014b38  lea     rcx, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180014b3f  mov     rax, r8
0x180014b42  dec     r8
0x180014b45  cmp     byte ptr [r8], 5Ch ; '\'
0x180014b49  jz      short loc_180014B54
0x180014b4b  cmp     r8, rcx
0x180014b4e  ja      short loc_180014B3F
0x180014b50  cmp     byte ptr [r8], 5Ch ; '\'
0x180014b54  cmovz   r8, rax
0x180014b58  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180014b5f  mov     r9d, 66h ; 'f'
0x180014b65  mov     edx, ebx
0x180014b67  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180014b6c  jmp     loc_180014C94
0x180014b71  mov     r8d, [rbp+dwDataLen]; dwDataLen
0x180014b75  xor     r9d, r9d; dwFlags
0x180014b78  mov     rcx, [rbp+phHash]; hHash
0x180014b7c  mov     rdx, r12; pbData
0x180014b7f  call    cs:__imp_CryptHashData
0x180014b86  nop     dword ptr [rax+rax+00h]
0x180014b8b  test    eax, eax
0x180014b8d  jnz     short loc_180014BCB
0x180014b8f  call    cs:__imp_GetLastError
0x180014b96  nop     dword ptr [rax+rax+00h]
0x180014b9b  mov     ebx, eax
0x180014b9d  test    eax, eax
0x180014b9f  jle     short loc_180014BAA
0x180014ba1  movzx   ebx, ax
0x180014ba4  or      ebx, 80070000h
0x180014baa  lea     rcx, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180014bb1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180014bb6  mov     r8, rax
0x180014bb9  mov     r9d, 83h
0x180014bbf  lea     rax, aCrypthashdata_0; "CryptHashData"
0x180014bc6  jmp     loc_180014AAE
0x180014bcb  mov     eax, [rbp+arg_30]
0x180014bce  xor     r9d, r9d; dwFlags
0x180014bd1  mov     rdi, [rbp+pbSignature]
0x180014bd5  xor     r8d, r8d; szDescription
0x180014bd8  mov     edx, [rbp+dwKeySpec]; dwKeySpec
0x180014bdb  mov     rcx, [rbp+phHash]; hHash
0x180014bdf  mov     qword ptr [rsp+40h+cchCount2], rsi; pdwSigLen
0x180014be4  mov     [rsp+40h+lpString2], rdi; pbSignature
0x180014be9  mov     [rsi], eax
0x180014beb  call    cs:__imp_CryptSignHashW
0x180014bf2  nop     dword ptr [rax+rax+00h]
0x180014bf7  test    eax, eax
0x180014bf9  jnz     short loc_180014C37
0x180014bfb  call    cs:__imp_GetLastError
0x180014c02  nop     dword ptr [rax+rax+00h]
0x180014c07  mov     ebx, eax
0x180014c09  test    eax, eax
0x180014c0b  jle     short loc_180014C16
0x180014c0d  movzx   ebx, ax
0x180014c10  or      ebx, 80070000h
0x180014c16  lea     rcx, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180014c1d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180014c22  mov     r8, rax
0x180014c25  mov     r9d, 96h
0x180014c2b  lea     rax, aCryptsignhash; "CryptSignHash"
0x180014c32  jmp     loc_180014AAE
0x180014c37  mov     r8, [rbp+hMem]
0x180014c3b  lea     rax, aDsa; "DSA"
0x180014c42  or      r9d, 0FFFFFFFFh; cchCount1
0x180014c46  xor     ecx, ecx; Locale
0x180014c48  mov     [rsp+40h+cchCount2], r9d; cchCount2
0x180014c4d  mov     [rsp+40h+lpString2], rax; lpString2
0x180014c52  mov     r8, [r8+28h]; lpString1
0x180014c56  lea     edx, [r9+2]; dwCmpFlags
0x180014c5a  call    cs:__imp_CompareStringW
0x180014c61  nop     dword ptr [rax+rax+00h]
0x180014c66  cmp     eax, 2
0x180014c69  jnz     short loc_180014C83
0x180014c6b  mov     eax, [rsi]
0x180014c6d  mov     rcx, rdi; unsigned __int8 *
0x180014c70  shr     eax, 1
0x180014c72  mov     edx, eax; unsigned int
0x180014c74  mov     ebx, eax
0x180014c76  call    ?I_ReverseBuffer@@YAXPEAEK@Z; I_ReverseBuffer(uchar *,ulong)
0x180014c7b  lea     rcx, [rdi+rbx]
0x180014c7f  mov     edx, ebx
0x180014c81  jmp     short loc_180014C8D
0x180014c83  test    rdi, rdi
0x180014c86  jz      short loc_180014C92
0x180014c88  mov     edx, [rsi]; unsigned int
0x180014c8a  mov     rcx, rdi; unsigned __int8 *
0x180014c8d  call    ?I_ReverseBuffer@@YAXPEAEK@Z; I_ReverseBuffer(uchar *,ulong)
0x180014c92  xor     ebx, ebx
0x180014c94  mov     rcx, [rbp+hMem]; hMem
0x180014c98  test    rcx, rcx
0x180014c9b  jz      short loc_180014CA9
0x180014c9d  call    cs:__imp_LocalFree
0x180014ca4  nop     dword ptr [rax+rax+00h]
0x180014ca9  mov     rcx, [rbp+phHash]; hHash
0x180014cad  test    rcx, rcx
0x180014cb0  jz      short loc_180014CBE
0x180014cb2  call    cs:__imp_CryptDestroyHash
0x180014cb9  nop     dword ptr [rax+rax+00h]
0x180014cbe  mov     eax, 8009210Ch
0x180014cc3  test    ebx, ebx
0x180014cc5  cmovs   ebx, eax
0x180014cc8  mov     eax, ebx
0x180014cca  add     rsp, 40h
0x180014cce  pop     r15
0x180014cd0  pop     r13
0x180014cd2  pop     r12
0x180014cd4  pop     rdi
0x180014cd5  pop     rsi
0x180014cd6  pop     rbx
0x180014cd7  pop     rbp
0x180014cd8  retn
```
