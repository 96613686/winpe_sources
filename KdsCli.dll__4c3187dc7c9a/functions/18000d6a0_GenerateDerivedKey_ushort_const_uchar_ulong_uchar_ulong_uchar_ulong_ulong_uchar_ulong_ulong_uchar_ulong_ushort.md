# GenerateDerivedKey(ushort const *,uchar *,ulong,uchar *,ulong,uchar *,ulong,ulong *,uchar *,ulong,ulong,uchar *,ulong,ushort * *)

- ea: `0x18000d6a0`
- end: `0x18000d9bf`
- name: `?GenerateDerivedKey@@YAJPEBGPEAEK1K1KPEAK1KK1KPEAPEAG@Z`
- size: `799`
- prototype: `HRESULT __stdcall(PINFORMATIONCARD_CRYPTO_HANDLE hCrypto, DWORD cbLabel, PBYTE pLabel, DWORD cbNonce, PBYTE pNonce, DWORD derivedKeyLength, DWORD offset, LPCWSTR algId, DWORD *pcbKey, PBYTE *ppKey)`
- caller_count: `9`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004624`
- `0x180008570`
- `0x180008850`
- `0x18000dfc0`
- `0x18000e644`
- `0x180016b30`
- `0x180018298`
- `0x180018b88`
- `0x180018c7c`

## callees

- `0x180001f64`
- `0x18000d63c`
- `0x18000d6a0`
- `0x18000da88`
- `0x180010920`
- `0x180010950`
- `0x180010f9c`
- `0x18001a450`
- `0x18001a6ac`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x18000d84d`
- `bcrypt!BCryptDestroyKey` at `0x18000d8b5`
- `bcrypt!BCryptDestroyKey` at `0x18000d84d`
- `bcrypt!BCryptDestroyKey` at `0x18000d8b5`
- `bcrypt!BCryptKeyDerivation` at `0x18000d831`
- `bcrypt!BCryptKeyDerivation` at `0x18000d831`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000d808`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000d808`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000d8cf`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000d8cf`

## string_xrefs

- `0x18000d741`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeykdf.cxx`
- `0x18000d7b2`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeykdf.cxx`
- `0x18000d948`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeykdf.cxx`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
HRESULT __stdcall GenerateDerivedKey(
        PINFORMATIONCARD_CRYPTO_HANDLE hCrypto,
        DWORD cbLabel,
        PBYTE pLabel,
        DWORD cbNonce,
        PBYTE pNonce,
        DWORD derivedKeyLength,
        DWORD offset,
        LPCWSTR algId,
        DWORD *pcbKey,
        PBYTE *ppKey)
{
  const void *v10; // r12
  unsigned __int8 *v11; // rbx
  signed int v12; // eax
  HRESULT v13; // edi
  void *pbSecret; // r14
  ULONG v15; // esi
  const wchar_t *v16; // rbx
  ULONG v17; // eax
  void *v18; // rax
  unsigned int v19; // r9d
  unsigned int v20; // ecx
  int v21; // r12d
  ULONG cbSecret; // eax
  NTSTATUS v23; // eax
  __int64 v24; // rcx
  _BYTE *v25; // rax
  unsigned int v27; // r9d
  __int64 v28; // rax
  unsigned __int64 v29; // r12
  wchar_t *v30; // rax
  unsigned int v31; // [rsp+38h] [rbp-49h]
  int v32; // [rsp+50h] [rbp-31h] BYREF
  int v33; // [rsp+54h] [rbp-2Dh] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+58h] [rbp-29h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+60h] [rbp-21h] BYREF
  struct _BCryptBufferDesc *lpMem; // [rsp+68h] [rbp-19h] BYREF
  _DWORD *v37; // [rsp+70h] [rbp-11h] BYREF
  unsigned int v38; // [rsp+120h] [rbp+9Fh]
  void *v39; // [rsp+128h] [rbp+A7h]
  ULONG v40; // [rsp+130h] [rbp+AFh]
  wchar_t **v41; // [rsp+138h] [rbp+B7h]

  v33 = 1;
  v10 = *(const void **)&cbNonce;
  hAlgorithm = 0;
  v11 = *(unsigned __int8 **)&cbLabel;
  phKey = 0;
  lpMem = 0;
  v32 = 0;
  v37 = 0;
  GetCachedBCryptHandle((WCHAR *)hCrypto, &hAlgorithm, 7u, &v33);
  v12 = ParseBCryptKDFParam(
          *(unsigned __int8 **)&derivedKeyLength,
          offset,
          (unsigned int *)algId,
          (unsigned int **)((unsigned __int64)&v37 & -(__int64)(algId != 0)),
          (unsigned __int8 *)pcbKey,
          (unsigned int)ppKey,
          v11,
          v31,
          &lpMem);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v16 = 0;
    v17 = (unsigned int)pNonce;
    if ( (unsigned int)pNonce <= v40 )
      v17 = v40;
    v15 = v17;
    v18 = SIDKeyProvAlloc(v17);
    pbSecret = v18;
    if ( v18 )
    {
      memcpy_0(v18, v10, (unsigned int)pNonce);
      v21 = 0;
      if ( !v38 )
      {
LABEL_20:
        memcpy_0(v39, pbSecret, v40);
LABEL_21:
        v24 = v15;
        v25 = pbSecret;
        if ( v15 )
        {
          do
          {
            *v25++ = 0;
            --v24;
          }
          while ( v24 );
        }
        SIDKeyProvFree(pbSecret);
        goto LABEL_24;
      }
      while ( 1 )
      {
        cbSecret = (unsigned int)pNonce;
        if ( v21 )
          cbSecret = v40;
        v23 = BCryptGenerateSymmetricKey(hAlgorithm, &phKey, 0, 0, (PUCHAR)pbSecret, cbSecret, 0);
        if ( v23 < 0 )
          break;
        v23 = BCryptKeyDerivation(phKey, lpMem, pbSecret, v40, &v32, 0);
        if ( v23 < 0 )
        {
          v16 = L"msKds-KDFParam";
          v27 = 359;
          goto LABEL_36;
        }
        if ( v32 != v40 )
        {
          v13 = -2147467259;
          v19 = 366;
          v20 = -2147467259;
          goto LABEL_9;
        }
        v23 = BCryptDestroyKey(phKey);
        phKey = 0;
        if ( v23 < 0 )
        {
          v16 = L"msKds-KDFParam";
          v27 = 379;
          goto LABEL_36;
        }
        if ( v37 )
          --*v37;
        if ( ++v21 >= v38 )
          goto LABEL_20;
      }
      v16 = L"msKds-KDFAlgorithmID";
      v27 = 341;
LABEL_36:
      v13 = v23 | 0x10000000;
      if ( (v23 | 0x10000000) == 0xD0000017 )
        v16 = 0;
      SidKeyDebugTraceError(
        v23 | 0x10000000,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeykdf.cxx",
        v27);
      if ( v13 >= 0 )
        goto LABEL_21;
    }
    else
    {
      v13 = -2147024882;
      v19 = 317;
      v20 = -2147024882;
LABEL_9:
      SidKeyDebugTraceError(v20, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeykdf.cxx", v19);
    }
  }
  else
  {
    pbSecret = 0;
    v15 = 0;
    SidKeyDebugTraceError(v12, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeykdf.cxx", 0x134u);
    v16 = L"msKds-KDFParam";
    if ( v13 == -805306345 )
      v16 = 0;
  }
  if ( v41 )
  {
    if ( v16 )
    {
      v28 = -1;
      do
        ++v28;
      while ( v16[v28] );
      v29 = 2 * v28 + 2;
      v30 = (wchar_t *)SIDKeyProvAlloc(v29);
      *v41 = v30;
      if ( v30 )
        wcscpy_s(v30, v29, v16);
    }
  }
  if ( pbSecret )
    goto LABEL_21;
LABEL_24:
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( !v33 && hAlgorithm )
    BCryptCloseAlgorithmProvider(hAlgorithm, 0);
  if ( lpMem )
    FreeBCryptBuffers(lpMem);
  return v13;
}

```

## disassembly

```asm
0x18000d6a0  push    rbp
0x18000d6a2  push    rbx
0x18000d6a3  push    rsi
0x18000d6a4  push    rdi
0x18000d6a5  push    r12
0x18000d6a7  push    r13
0x18000d6a9  push    r14
0x18000d6ab  push    r15
0x18000d6ad  lea     rbp, [rsp-7]
0x18000d6b2  sub     rsp, 88h
0x18000d6b9  xor     r13d, r13d
0x18000d6bc  mov     [rbp+3Fh+var_6C], 1
0x18000d6c3  mov     r12, r9
0x18000d6c6  mov     [rbp+3Fh+hAlgorithm], r13
0x18000d6ca  mov     rbx, rdx
0x18000d6cd  mov     [rbp+3Fh+phKey], r13
0x18000d6d1  lea     r9, [rbp+3Fh+var_6C]; int *
0x18000d6d5  mov     [rbp+3Fh+lpMem], r13
0x18000d6d9  lea     r8d, [r13+7]; unsigned int
0x18000d6dd  mov     [rbp+3Fh+var_70], r13d
0x18000d6e1  lea     rdx, [rbp+3Fh+hAlgorithm]; void **
0x18000d6e5  mov     [rbp+3Fh+var_50], r13
0x18000d6e9  call    ?GetCachedBCryptHandle@@YAJPEBGPEAPEAXKPEAH@Z; GetCachedBCryptHandle(ushort const *,void * *,ulong,int *)
0x18000d6ee  mov     r8, [rbp+3Fh+algId]; unsigned int *
0x18000d6f5  mov     edx, [rbp+3Fh+offset]; unsigned int
0x18000d6f8  mov     rax, r8
0x18000d6fb  mov     rcx, [rbp+3Fh+derivedKeyLength]; unsigned __int8 *
0x18000d6ff  neg     rax
0x18000d702  lea     rax, [rbp+3Fh+var_50]
0x18000d706  sbb     r9, r9
0x18000d709  and     r9, rax; unsigned int **
0x18000d70c  lea     rax, [rbp+3Fh+lpMem]
0x18000d710  mov     [rsp+0C0h+var_80], rax; struct _BCryptBufferDesc **
0x18000d715  mov     eax, dword ptr [rbp+3Fh+ppKey]
0x18000d71b  mov     qword ptr [rsp+0C0h+dwFlags], rbx; unsigned __int8 *
0x18000d720  mov     [rsp+0C0h+cbSecret], eax; unsigned int
0x18000d724  mov     rax, [rbp+3Fh+pcbKey]
0x18000d72b  mov     [rsp+0C0h+pbSecret], rax; unsigned __int8 *
0x18000d730  call    ?ParseBCryptKDFParam@@YAJPEAEKPEAKPEAPEAK0K0KPEAPEAU_BCryptBufferDesc@@@Z; ParseBCryptKDFParam(uchar *,ulong,ulong *,ulong * *,uchar *,ulong,uchar *,ulong,_BCryptBufferDesc * *)
0x18000d735  mov     edi, eax
0x18000d737  test    eax, eax
0x18000d739  jns     short loc_18000D772
0x18000d73b  mov     r9d, 134h; unsigned int
0x18000d741  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000d748  lea     rdx, aHr; "hr"
0x18000d74f  mov     ecx, eax; unsigned int
0x18000d751  mov     r14d, r13d
0x18000d754  mov     esi, r13d
0x18000d757  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000d75c  cmp     edi, 0D0000017h
0x18000d762  lea     rbx, aMskdsKdfparam; "msKds-KDFParam"
0x18000d769  cmovz   rbx, r13
0x18000d76d  jmp     loc_18000D96C
0x18000d772  mov     r15d, [rbp+3Fh+arg_60]
0x18000d779  mov     rbx, r13
0x18000d77c  mov     r13d, dword ptr [rbp+3Fh+pNonce]
0x18000d780  mov     eax, r13d
0x18000d783  cmp     r13d, r15d
0x18000d786  cmovbe  eax, r15d
0x18000d78a  mov     ecx, eax; unsigned __int64
0x18000d78c  mov     esi, eax
0x18000d78e  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000d793  mov     r14, rax
0x18000d796  test    rax, rax
0x18000d799  jnz     short loc_18000D7C6
0x18000d79b  mov     edi, 8007000Eh
0x18000d7a0  mov     r9d, 13Dh; unsigned int
0x18000d7a6  mov     ecx, 8007000Eh; unsigned int
0x18000d7ab  lea     rdx, aHr; "hr"
0x18000d7b2  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000d7b9  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000d7be  xor     r13d, r13d
0x18000d7c1  jmp     loc_18000D96C
0x18000d7c6  mov     r8, r13; Size
0x18000d7c9  mov     rdx, r12; Src
0x18000d7cc  mov     rcx, r14; void *
0x18000d7cf  call    memcpy_0
0x18000d7d4  xor     r12d, r12d
0x18000d7d7  cmp     [rbp+3Fh+arg_50], ebx
0x18000d7dd  jbe     loc_18000D87A
0x18000d7e3  mov     rcx, [rbp+3Fh+hAlgorithm]; hAlgorithm
0x18000d7e7  lea     rdx, [rbp+3Fh+phKey]; phKey
0x18000d7eb  mov     eax, r13d
0x18000d7ee  mov     [rsp+0C0h+dwFlags], ebx; dwFlags
0x18000d7f2  test    r12d, r12d
0x18000d7f5  cmovnz  eax, r15d
0x18000d7f9  xor     r9d, r9d; cbKeyObject
0x18000d7fc  mov     [rsp+0C0h+cbSecret], eax; cbSecret
0x18000d800  xor     r8d, r8d; pbKeyObject
0x18000d803  mov     [rsp+0C0h+pbSecret], r14; pbSecret
0x18000d808  call    cs:__imp_BCryptGenerateSymmetricKey
0x18000d80e  test    eax, eax
0x18000d810  js      loc_18000D92F
0x18000d816  mov     rdx, [rbp+3Fh+lpMem]
0x18000d81a  lea     rax, [rbp+3Fh+var_70]
0x18000d81e  mov     rcx, [rbp+3Fh+phKey]
0x18000d822  mov     r9d, r15d
0x18000d825  mov     [rsp+0C0h+cbSecret], ebx
0x18000d829  mov     r8, r14
0x18000d82c  mov     [rsp+0C0h+pbSecret], rax
0x18000d831  call    cs:__imp_BCryptKeyDerivation
0x18000d837  test    eax, eax
0x18000d839  js      loc_18000D920
0x18000d83f  cmp     [rbp+3Fh+var_70], r15d
0x18000d843  jnz     loc_18000D90B
0x18000d849  mov     rcx, [rbp+3Fh+phKey]; hKey
0x18000d84d  call    cs:__imp_BCryptDestroyKey
0x18000d853  mov     [rbp+3Fh+phKey], rbx
0x18000d857  test    eax, eax
0x18000d859  js      loc_18000D8FC
0x18000d85f  mov     rax, [rbp+3Fh+var_50]
0x18000d863  test    rax, rax
0x18000d866  jz      short loc_18000D86A
0x18000d868  dec     dword ptr [rax]
0x18000d86a  inc     r12d
0x18000d86d  cmp     r12d, [rbp+3Fh+arg_50]
0x18000d874  jb      loc_18000D7E3
0x18000d87a  mov     rcx, [rbp+3Fh+arg_58]; void *
0x18000d881  mov     r8, r15; Size
0x18000d884  mov     rdx, r14; Src
0x18000d887  call    memcpy_0
0x18000d88c  xor     r13d, r13d
0x18000d88f  mov     ecx, esi
0x18000d891  mov     rax, r14
0x18000d894  test    esi, esi
0x18000d896  jz      short loc_18000D8A4
0x18000d898  mov     [rax], r13b
0x18000d89b  inc     rax
0x18000d89e  sub     rcx, 1
0x18000d8a2  jnz     short loc_18000D898
0x18000d8a4  mov     rcx, r14; lpMem
0x18000d8a7  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000d8ac  mov     rcx, [rbp+3Fh+phKey]; hKey
0x18000d8b0  test    rcx, rcx
0x18000d8b3  jz      short loc_18000D8BB
0x18000d8b5  call    cs:__imp_BCryptDestroyKey
0x18000d8bb  cmp     [rbp+3Fh+var_6C], r13d
0x18000d8bf  jnz     short loc_18000D8D5
0x18000d8c1  mov     rax, [rbp+3Fh+hAlgorithm]
0x18000d8c5  test    rax, rax
0x18000d8c8  jz      short loc_18000D8D5
0x18000d8ca  xor     edx, edx; dwFlags
0x18000d8cc  mov     rcx, rax; hAlgorithm
0x18000d8cf  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000d8d5  mov     rax, [rbp+3Fh+lpMem]
0x18000d8d9  test    rax, rax
0x18000d8dc  jz      short loc_18000D8E6
0x18000d8de  mov     rcx, rax; lpMem
0x18000d8e1  call    ?FreeBCryptBuffers@@YAXPEAU_BCryptBufferDesc@@@Z; FreeBCryptBuffers(_BCryptBufferDesc *)
0x18000d8e6  mov     eax, edi
0x18000d8e8  add     rsp, 88h
0x18000d8ef  pop     r15
0x18000d8f1  pop     r14
0x18000d8f3  pop     r13
0x18000d8f5  pop     r12
0x18000d8f7  pop     rdi
0x18000d8f8  pop     rsi
0x18000d8f9  pop     rbx
0x18000d8fa  pop     rbp
0x18000d8fb  retn
0x18000d8fc  lea     rbx, aMskdsKdfparam; "msKds-KDFParam"
0x18000d903  mov     r9d, 17Bh
0x18000d909  jmp     short loc_18000D93C
0x18000d90b  mov     edi, 80004005h
0x18000d910  mov     r9d, 16Eh
0x18000d916  mov     ecx, 80004005h
0x18000d91b  jmp     loc_18000D7AB
0x18000d920  lea     rbx, aMskdsKdfparam; "msKds-KDFParam"
0x18000d927  mov     r9d, 167h
0x18000d92d  jmp     short loc_18000D93C
0x18000d92f  lea     rbx, aMskdsKdfalgori; "msKds-KDFAlgorithmID"
0x18000d936  mov     r9d, 155h; unsigned int
0x18000d93c  xor     r13d, r13d
0x18000d93f  lea     rdx, aHr; "hr"
0x18000d946  mov     edi, eax
0x18000d948  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000d94f  bts     edi, 1Ch
0x18000d953  cmp     edi, 0D0000017h
0x18000d959  mov     ecx, edi; unsigned int
0x18000d95b  cmovz   rbx, r13
0x18000d95f  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000d964  test    edi, edi
0x18000d966  jns     loc_18000D88F
0x18000d96c  mov     r15, [rbp+3Fh+arg_68]
0x18000d973  test    r15, r15
0x18000d976  jz      short loc_18000D9B1
0x18000d978  test    rbx, rbx
0x18000d97b  jz      short loc_18000D9B1
0x18000d97d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d981  inc     rax
0x18000d984  cmp     [rbx+rax*2], r13w
0x18000d989  jnz     short loc_18000D981
0x18000d98b  lea     r12, ds:2[rax*2]
0x18000d993  mov     rcx, r12; unsigned __int64
0x18000d996  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000d99b  mov     [r15], rax
0x18000d99e  test    rax, rax
0x18000d9a1  jz      short loc_18000D9B1
0x18000d9a3  mov     r8, rbx; Source
0x18000d9a6  mov     rdx, r12; SizeInWords
0x18000d9a9  mov     rcx, rax; Destination
0x18000d9ac  call    wcscpy_s
0x18000d9b1  test    r14, r14
0x18000d9b4  jz      loc_18000D8AC
0x18000d9ba  jmp     loc_18000D88F
```
