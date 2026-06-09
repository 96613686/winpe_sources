# GenerateSecretAgreementPrivateKey(uchar * const,ushort *,ushort *,uchar *,ulong,uchar *,ulong,ulong,ulong,_SID_KEY_BLOB_VER,void * *,ushort * *)

- ea: `0x18000dfc0`
- end: `0x18000e537`
- name: `?GenerateSecretAgreementPrivateKey@@YAJQEAEPEAG1PEAEK2KKKW4_SID_KEY_BLOB_VER@@PEAPEAXPEAPEAG@Z`
- size: `1399`
- prototype: `int __high(unsigned __int8 *const, unsigned __int16 *, unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int, unsigned int, enum _SID_KEY_BLOB_VER, void **, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800080e8`
- `0x18000e8a0`
- `0x1800190b4`

## callees

- `0x180001f64`
- `0x18000d6a0`
- `0x18000dfc0`
- `0x180010920`
- `0x180010950`
- `0x180010f9c`
- `0x18001a450`
- `0x18001a6ac`

## import_xrefs

- `bcrypt!BCryptFinalizeKeyPair` at `0x18000e3e9`
- `bcrypt!BCryptFinalizeKeyPair` at `0x18000e3e9`
- `bcrypt!BCryptGenerateKeyPair` at `0x18000e0c5`
- `bcrypt!BCryptGenerateKeyPair` at `0x18000e0c5`
- `bcrypt!BCryptSetProperty` at `0x18000e127`
- `bcrypt!BCryptSetProperty` at `0x18000e39e`
- `bcrypt!BCryptSetProperty` at `0x18000e127`
- `bcrypt!BCryptSetProperty` at `0x18000e39e`
- `bcrypt!BCryptDestroyKey` at `0x18000e4b6`
- `bcrypt!BCryptDestroyKey` at `0x18000e4b6`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000e4a7`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000e4a7`

## string_xrefs

- `0x18000e055`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeysecagr.cxx`
- `0x18000e088`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeysecagr.cxx`
- `0x18000e170`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeysecagr.cxx`
- `0x18000e411`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeysecagr.cxx`

## pseudocode

```c
__int64 __fastcall GenerateSecretAgreementPrivateKey(
        DWORD a1,
        WCHAR *a2,
        struct _INFORMATIONCARD_CRYPTO_HANDLE *a3,
        DWORD a4,
        unsigned int pLabel,
        UCHAR *pbInput,
        ULONG cbInput,
        unsigned int Size,
        ULONG dwLength,
        int a10,
        _QWORD *a11,
        wchar_t **a12)
{
  int v12; // edi
  const wchar_t *v14; // rsi
  ULONG v15; // r13d
  int v16; // edi
  int v17; // ebx
  unsigned int v18; // r9d
  unsigned int v19; // ecx
  signed int CachedBCryptHandle; // eax
  NTSTATUS v21; // eax
  unsigned int v22; // ebx
  const wchar_t *v23; // rax
  unsigned int v24; // ecx
  unsigned int v25; // r9d
  NTSTATUS v26; // eax
  UCHAR *v27; // rax
  unsigned __int64 v28; // rdi
  __int64 v29; // rax
  HRESULT DerivedKey; // eax
  _BYTE *v31; // r14
  void *v32; // rax
  unsigned int v33; // r12d
  int v34; // r8d
  bool v35; // zf
  UCHAR *v36; // rsi
  unsigned __int8 *v37; // r15
  int v38; // r14d
  int v39; // r9d
  int v40; // r10d
  int v41; // r11d
  _BYTE *v42; // r12
  int v43; // r10d
  unsigned int v44; // r11d
  _BYTE *v45; // r15
  __int64 v46; // rdx
  NTSTATUS v47; // eax
  const wchar_t *v48; // rax
  __int64 v49; // rax
  unsigned __int64 v50; // rdi
  wchar_t *v51; // rax
  BCRYPT_KEY_HANDLE v52; // rax
  PUCHAR v53; // rcx
  __int64 v54; // rdx
  PUCHAR v55; // rax
  void *v56; // rdx
  __int64 v57; // rcx
  _BYTE *v58; // rax
  BYTE *dwFlags; // [rsp+28h] [rbp-99h]
  PBYTE *ppKey; // [rsp+50h] [rbp-71h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+78h] [rbp-49h] BYREF
  int v63; // [rsp+80h] [rbp-41h] BYREF
  void *lpMem; // [rsp+88h] [rbp-39h]
  void *v65; // [rsp+90h] [rbp-31h]
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+98h] [rbp-29h] BYREF
  PUCHAR v67; // [rsp+A0h] [rbp-21h]
  wchar_t *v68; // [rsp+A8h] [rbp-19h]
  UCHAR *v69; // [rsp+B0h] [rbp-11h]
  const wchar_t *v70; // [rsp+B8h] [rbp-9h]

  v12 = *a2;
  hAlgorithm = 0;
  phKey = 0;
  v63 = 1;
  v14 = 0;
  v67 = 0;
  v15 = 0;
  v70 = 0;
  v68 = 0;
  lpMem = 0;
  v65 = 0;
  v16 = v12 - 68;
  if ( !v16 )
  {
    v16 = a2[1] - 72;
    if ( a2[1] == 72 )
      v16 = a2[2];
  }
  if ( Size <= 0x40 )
  {
    CachedBCryptHandle = GetCachedBCryptHandle(a2, &hAlgorithm, 4u, &v63);
    v17 = CachedBCryptHandle;
    if ( CachedBCryptHandle < 0 )
    {
      SidKeyDebugTraceError(
        CachedBCryptHandle,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeysecagr.cxx",
        0xBDu);
      v14 = L"msKds-SecretAgreementAlgorithmID";
      if ( v17 == -805306345 )
        v14 = 0;
      goto LABEL_69;
    }
    v21 = BCryptGenerateKeyPair(hAlgorithm, &phKey, dwLength, 0);
    v22 = v21;
    if ( v21 < 0 )
    {
      if ( v21 == -1073741811 )
      {
        v14 = L"msKds-PublicKeyLength";
      }
      else
      {
        v23 = L"msKds-SecretAgreementAlgorithmID";
        if ( v22 == -1073741801 )
          v23 = 0;
        v14 = v23;
      }
      v24 = v22;
      v25 = 208;
      goto LABEL_68;
    }
    if ( v16 )
    {
      v15 = Size;
    }
    else
    {
      if ( pbInput )
      {
        v26 = BCryptSetProperty(phKey, L"SecretAgreementParam", pbInput, cbInput, 0);
        v22 = v26;
        if ( v26 < 0 )
        {
          v14 = L"msKds-SecretAgreementParam";
          v24 = v26;
          v25 = 228;
          goto LABEL_66;
        }
      }
      v15 = dwLength >> 3;
      if ( dwLength >> 3 < 0x80 )
      {
        v17 = -805306355;
        v18 = 240;
        v19 = -805306355;
        goto LABEL_6;
      }
    }
    v27 = (UCHAR *)SIDKeyProvAlloc(v15);
    v67 = v27;
    if ( !v27 )
    {
      v18 = 248;
LABEL_27:
      v17 = -2147024882;
      v19 = -2147024882;
      goto LABEL_6;
    }
    v28 = v15 - (unsigned __int64)Size;
    v69 = &v27[v28];
    v29 = -1;
    do
      ++v29;
    while ( a2[v29] );
    LODWORD(ppKey) = 0;
    LODWORD(dwFlags) = 64;
    DerivedKey = GenerateDerivedKey(a3, a4, (PBYTE)pLabel, a1, dwFlags, (DWORD)a2, 2 * v29 + 2, 0, 0, ppKey);
    v17 = DerivedKey;
    if ( DerivedKey < 0 )
    {
      v18 = 271;
      v19 = DerivedKey;
      goto LABEL_6;
    }
    if ( a10 == 1 && pbInput )
    {
      lpMem = SIDKeyProvAlloc(Size);
      v31 = lpMem;
      v32 = SIDKeyProvAlloc(Size);
      v65 = v32;
      if ( !v31 || !v32 )
      {
        v18 = 290;
        goto LABEL_27;
      }
      memcpy_0(v31, &pbInput[v28 + 12], Size);
      v33 = Size;
      v34 = 0;
      v31[Size - 1] &= ~1u;
      if ( *v31 )
      {
LABEL_39:
        v35 = v34 == Size;
      }
      else
      {
        while ( 1 )
        {
          v35 = v34 == Size;
          if ( v34 >= Size )
            break;
          if ( v31[++v34] )
            goto LABEL_39;
        }
      }
      if ( v35 )
      {
        v17 = -2147024809;
        v18 = 309;
        v19 = -2147024809;
        goto LABEL_6;
      }
      if ( v34 >= 0 )
      {
        v36 = v69;
        v37 = v31;
        do
        {
          v38 = 256;
          v39 = v33 - v34 - 1;
          do
          {
            v40 = 0;
            v41 = v39;
            if ( v39 >= 0 )
            {
              v42 = v65;
              do
              {
                v43 = v36[v41] - v37[v41 + v34] + v40;
                v42[v41] = v43;
                v40 = v43 >> 8;
                --v41;
              }
              while ( v41 >= 0 );
              v33 = Size;
            }
            v44 = 0;
            if ( v33 )
            {
              v45 = v65;
              do
              {
                v46 = (int)v44++;
                v36[v46] = v40 & v36[v46] | ~(_BYTE)v40 & v45[v46];
              }
              while ( v44 < v33 );
              v37 = (unsigned __int8 *)lpMem;
            }
            --v38;
          }
          while ( v38 );
          --v34;
        }
        while ( v34 >= 0 );
        v14 = v70;
      }
    }
    v47 = BCryptSetProperty(phKey, L"PrivKeyVal", v67, v15, 0);
    v24 = v47;
    if ( v47 < 0 )
    {
      if ( v47 == -1073741811 )
      {
        v14 = L"msKds-PrivateKeyLength";
      }
      else
      {
        v48 = L"msKds-SecretAgreementAlgorithmID";
        if ( v24 == -1073741801 )
          v48 = v14;
        v14 = v48;
      }
      v22 = v24;
      v25 = 355;
LABEL_68:
      SidKeyDebugTraceError(v24, "status", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeysecagr.cxx", v25);
      v17 = v22 | 0x10000000;
      if ( v17 >= 0 )
        goto LABEL_78;
      goto LABEL_69;
    }
    v26 = BCryptFinalizeKeyPair(phKey, 0);
    v24 = v26;
    if ( v26 >= 0 )
    {
      v52 = phKey;
      phKey = 0;
      *a11 = v52;
      goto LABEL_78;
    }
    v14 = L"msKds-SecretAgreementAlgorithmID";
    v22 = v26;
    v25 = 369;
LABEL_66:
    if ( v26 == -1073741801 )
      v14 = 0;
    goto LABEL_68;
  }
  v17 = -805306355;
  v18 = 174;
  v19 = -805306355;
LABEL_6:
  SidKeyDebugTraceError(v19, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeysecagr.cxx", v18);
LABEL_69:
  if ( a12 )
  {
    if ( v68 )
    {
      *a12 = v68;
    }
    else if ( v14 )
    {
      v49 = -1;
      do
        ++v49;
      while ( v14[v49] );
      v50 = 2 * v49 + 2;
      v51 = (wchar_t *)SIDKeyProvAlloc(v50);
      *a12 = v51;
      if ( v51 )
        wcscpy_s(v51, v50, v14);
    }
  }
LABEL_78:
  if ( !v63 && hAlgorithm )
    BCryptCloseAlgorithmProvider(hAlgorithm, 0);
  if ( phKey )
    BCryptDestroyKey(phKey);
  v53 = v67;
  if ( v67 )
  {
    v54 = v15;
    v55 = v67;
    if ( v15 )
    {
      do
      {
        *v55++ = 0;
        --v54;
      }
      while ( v54 );
    }
    SIDKeyProvFree(v53);
  }
  if ( lpMem )
    SIDKeyProvFree(lpMem);
  v56 = v65;
  if ( v65 )
  {
    v57 = Size;
    v58 = v65;
    if ( Size )
    {
      do
      {
        *v58++ = 0;
        --v57;
      }
      while ( v57 );
    }
    SIDKeyProvFree(v56);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18000dfc0  mov     rax, rsp
0x18000dfc3  mov     [rax+10h], rbx
0x18000dfc7  mov     [rax+20h], r9
0x18000dfcb  mov     [rax+18h], r8
0x18000dfcf  mov     [rax+8], rcx
0x18000dfd3  push    rbp
0x18000dfd4  push    rsi
0x18000dfd5  push    rdi
0x18000dfd6  push    r12
0x18000dfd8  push    r13
0x18000dfda  push    r14
0x18000dfdc  push    r15
0x18000dfde  lea     rbp, [rax-3Fh]
0x18000dfe2  sub     rsp, 0C0h
0x18000dfe9  movzx   edi, word ptr [rdx]
0x18000dfec  xor     eax, eax
0x18000dfee  xor     r15d, r15d
0x18000dff1  mov     [rbp+37h+hAlgorithm], rax
0x18000dff5  mov     [rbp+37h+phKey], rax
0x18000dff9  mov     r14, rdx
0x18000dffc  mov     [rbp+37h+var_78], 1
0x18000e003  mov     esi, eax
0x18000e005  mov     [rbp+37h+var_58], rax
0x18000e009  mov     r13d, eax
0x18000e00c  mov     [rbp+37h+var_40], rax
0x18000e010  mov     [rbp+37h+var_50], rax
0x18000e014  mov     [rbp+37h+lpMem], rax
0x18000e018  mov     [rbp+37h+var_68], r15
0x18000e01c  sub     edi, 44h ; 'D'
0x18000e01f  jnz     short loc_18000E034
0x18000e021  movzx   edi, word ptr [rdx+2]
0x18000e025  sub     edi, 48h ; 'H'
0x18000e028  jnz     short loc_18000E034
0x18000e02a  movzx   edi, word ptr [rdx+4]
0x18000e02e  movzx   ecx, r15w
0x18000e032  sub     edi, ecx
0x18000e034  mov     r12d, dword ptr [rbp+37h+Size]
0x18000e038  cmp     r12d, 40h ; '@'
0x18000e03c  jbe     short loc_18000E066
0x18000e03e  mov     ebx, 0D000000Dh
0x18000e043  mov     r9d, 0AEh; unsigned int
0x18000e049  mov     ecx, 0D000000Dh; unsigned int
0x18000e04e  lea     rdx, aHr; "hr"
0x18000e055  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000e05c  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000e061  jmp     loc_18000E42C
0x18000e066  lea     r9, [rbp+37h+var_78]; int *
0x18000e06a  mov     r8d, 4; unsigned int
0x18000e070  lea     rdx, [rbp+37h+hAlgorithm]; void **
0x18000e074  mov     rcx, r14; Src
0x18000e077  call    ?GetCachedBCryptHandle@@YAJPEBGPEAPEAXKPEAH@Z; GetCachedBCryptHandle(ushort const *,void * *,ulong,int *)
0x18000e07c  mov     ebx, eax
0x18000e07e  test    eax, eax
0x18000e080  jns     short loc_18000E0B3
0x18000e082  mov     r9d, 0BDh; unsigned int
0x18000e088  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000e08f  lea     rdx, aHr; "hr"
0x18000e096  mov     ecx, eax; unsigned int
0x18000e098  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000e09d  cmp     ebx, 0D0000017h
0x18000e0a3  lea     rsi, aMskdsSecretagr; "msKds-SecretAgreementAlgorithmID"
0x18000e0aa  cmovz   rsi, r15
0x18000e0ae  jmp     loc_18000E42C
0x18000e0b3  mov     r8d, [rbp+37h+dwLength]; dwLength
0x18000e0ba  lea     rdx, [rbp+37h+phKey]; phKey
0x18000e0be  mov     rcx, [rbp+37h+hAlgorithm]; hAlgorithm
0x18000e0c2  xor     r9d, r9d; dwFlags
0x18000e0c5  call    cs:__imp_BCryptGenerateKeyPair
0x18000e0cb  mov     ebx, eax
0x18000e0cd  test    eax, eax
0x18000e0cf  jns     short loc_18000E102
0x18000e0d1  cmp     eax, 0C000000Dh
0x18000e0d6  jnz     short loc_18000E0E1
0x18000e0d8  lea     rsi, aMskdsPublickey; "msKds-PublicKeyLength"
0x18000e0df  jmp     short loc_18000E0F5
0x18000e0e1  cmp     ebx, 0C0000017h
0x18000e0e7  lea     rax, aMskdsSecretagr; "msKds-SecretAgreementAlgorithmID"
0x18000e0ee  cmovz   rax, rsi
0x18000e0f2  mov     rsi, rax
0x18000e0f5  mov     ecx, ebx
0x18000e0f7  mov     r9d, 0D0h
0x18000e0fd  jmp     loc_18000E411
0x18000e102  mov     r15, [rbp+37h+pbInput]
0x18000e106  xor     ebx, ebx
0x18000e108  test    edi, edi
0x18000e10a  jnz     short loc_18000E18B
0x18000e10c  test    r15, r15
0x18000e10f  jz      short loc_18000E14C
0x18000e111  mov     r9d, [rbp+37h+cbInput]; cbInput
0x18000e115  lea     rdx, pszProperty; "SecretAgreementParam"
0x18000e11c  mov     rcx, [rbp+37h+phKey]; hObject
0x18000e120  mov     r8, r15; pbInput
0x18000e123  mov     [rsp+0F0h+dwFlags], ebx; dwFlags
0x18000e127  call    cs:__imp_BCryptSetProperty
0x18000e12d  mov     ebx, eax
0x18000e12f  test    eax, eax
0x18000e131  jns     short loc_18000E14A
0x18000e133  lea     rsi, aMskdsSecretagr_0; "msKds-SecretAgreementParam"
0x18000e13a  xor     r15d, r15d
0x18000e13d  mov     ecx, eax
0x18000e13f  mov     r9d, 0E4h
0x18000e145  jmp     loc_18000E408
0x18000e14a  xor     ebx, ebx
0x18000e14c  mov     r13d, [rbp+37h+dwLength]
0x18000e153  shr     r13d, 3
0x18000e157  cmp     r13d, 80h
0x18000e15e  jnb     short loc_18000E18E
0x18000e160  mov     ebx, 0D000000Dh
0x18000e165  mov     r9d, 0F0h; unsigned int
0x18000e16b  mov     ecx, 0D000000Dh; unsigned int
0x18000e170  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000e177  lea     rdx, aHr; "hr"
0x18000e17e  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000e183  xor     r15d, r15d
0x18000e186  jmp     loc_18000E42C
0x18000e18b  mov     r13d, r12d
0x18000e18e  mov     ecx, r13d; unsigned __int64
0x18000e191  mov     edi, r13d
0x18000e194  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000e199  mov     [rbp+37h+var_58], rax
0x18000e19d  test    rax, rax
0x18000e1a0  jnz     short loc_18000E1B4
0x18000e1a2  mov     r9d, 0F8h
0x18000e1a8  mov     ebx, 8007000Eh
0x18000e1ad  mov     ecx, 8007000Eh
0x18000e1b2  jmp     short loc_18000E170
0x18000e1b4  sub     rdi, r12
0x18000e1b7  lea     rdx, [rdi+rax]
0x18000e1bb  mov     rax, [rbp+37h+arg_58]
0x18000e1c2  neg     rax
0x18000e1c5  mov     [rbp+37h+var_48], rdx
0x18000e1c9  lea     rax, [rbp+37h+var_50]
0x18000e1cd  sbb     rcx, rcx
0x18000e1d0  and     rcx, rax
0x18000e1d3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e1d7  inc     rax
0x18000e1da  cmp     [r14+rax*2], bx
0x18000e1df  jnz     short loc_18000E1D7
0x18000e1e1  mov     r9, qword ptr [rbp+37h+cbNonce]; cbNonce
0x18000e1e5  lea     eax, ds:2[rax*2]
0x18000e1ec  mov     r8d, dword ptr [rbp+37h+pLabel]; pLabel
0x18000e1f0  mov     [rsp+68h], rcx
0x18000e1f5  mov     ecx, dword ptr [rbp+37h+Size]
0x18000e1f8  mov     dword ptr [rsp+0F0h+var_90], ecx
0x18000e1fc  mov     rcx, [rbp+37h+hCrypto]; hCrypto
0x18000e200  mov     qword ptr [rsp+0F0h+var_98], rdx
0x18000e205  mov     rdx, qword ptr [rbp+37h+cbLabel]; cbLabel
0x18000e209  mov     dword ptr [rsp+0F0h+var_A0], 1
0x18000e211  mov     dword ptr [rsp+0F0h+ppKey], ebx; ppKey
0x18000e215  mov     [rsp+0F0h+pcbKey], rbx; pcbKey
0x18000e21a  mov     [rsp+0F0h+algId], rbx; algId
0x18000e21f  mov     [rsp+0F0h+offset], eax; offset
0x18000e223  mov     qword ptr [rsp+0F0h+derivedKeyLength], r14; derivedKeyLength
0x18000e228  mov     [rsp+0F0h+dwFlags], 40h ; '@'; pNonce
0x18000e230  call    ?GenerateDerivedKey@@YAJPEBGPEAEK1K1KPEAK1KK1KPEAPEAG@Z; GenerateDerivedKey(ushort const *,uchar *,ulong,uchar *,ulong,uchar *,ulong,ulong *,uchar *,ulong,ulong,uchar *,ulong,ushort * *)
0x18000e235  mov     ebx, eax
0x18000e237  test    eax, eax
0x18000e239  jns     short loc_18000E248
0x18000e23b  mov     r9d, 10Fh
0x18000e241  mov     ecx, eax
0x18000e243  jmp     loc_18000E170
0x18000e248  cmp     [rbp+37h+arg_48], 1
0x18000e24f  jnz     loc_18000E384
0x18000e255  test    r15, r15
0x18000e258  jz      loc_18000E384
0x18000e25e  mov     rcx, r12; unsigned __int64
0x18000e261  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000e266  mov     rcx, r12; unsigned __int64
0x18000e269  mov     [rbp+37h+lpMem], rax
0x18000e26d  mov     r14, rax
0x18000e270  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000e275  mov     [rbp+37h+var_68], rax
0x18000e279  test    r14, r14
0x18000e27c  jz      loc_18000E3BA
0x18000e282  test    rax, rax
0x18000e285  jz      loc_18000E3BA
0x18000e28b  lea     rdx, [r15+0Ch]
0x18000e28f  mov     r8, r12; Size
0x18000e292  add     rdx, rdi; Src
0x18000e295  mov     rcx, r14; void *
0x18000e298  call    memcpy_0
0x18000e29d  mov     r12d, dword ptr [rbp+37h+Size]
0x18000e2a1  xor     r15d, r15d
0x18000e2a4  mov     r8d, r15d
0x18000e2a7  lea     ecx, [r12-1]
0x18000e2ac  and     byte ptr [rcx+r14], 0FEh
0x18000e2b1  cmp     [r14], r15b
0x18000e2b4  jnz     short loc_18000E2C7
0x18000e2b6  cmp     r8d, r12d
0x18000e2b9  jnb     short loc_18000E2CA
0x18000e2bb  inc     r8d
0x18000e2be  movsxd  rax, r8d
0x18000e2c1  cmp     [rax+r14], r15b
0x18000e2c5  jz      short loc_18000E2B6
0x18000e2c7  cmp     r8d, r12d
0x18000e2ca  jnz     short loc_18000E2E1
0x18000e2cc  mov     ebx, 80070057h
0x18000e2d1  mov     r9d, 135h
0x18000e2d7  mov     ecx, 80070057h
0x18000e2dc  jmp     loc_18000E04E
0x18000e2e1  test    r8d, r8d
0x18000e2e4  js      loc_18000E387
0x18000e2ea  mov     rsi, [rbp+37h+var_48]
0x18000e2ee  mov     r15, r14
0x18000e2f1  xor     edi, edi
0x18000e2f3  mov     r9d, r12d
0x18000e2f6  mov     r14d, 100h
0x18000e2fc  sub     r9d, r8d
0x18000e2ff  dec     r9d
0x18000e302  mov     r10d, edi
0x18000e305  mov     r11d, r9d
0x18000e308  test    r9d, r9d
0x18000e30b  js      short loc_18000E33B
0x18000e30d  mov     r12, [rbp+37h+var_68]
0x18000e311  lea     eax, [r11+r8]
0x18000e315  mov     edx, r11d
0x18000e318  movsxd  rcx, eax
0x18000e31b  movzx   eax, byte ptr [rcx+r15]
0x18000e320  movzx   ecx, byte ptr [rdx+rsi]
0x18000e324  sub     ecx, eax
0x18000e326  add     r10d, ecx
0x18000e329  mov     [rdx+r12], r10b
0x18000e32d  sar     r10d, 8
0x18000e331  sub     r11d, 1
0x18000e335  jns     short loc_18000E311
0x18000e337  mov     r12d, dword ptr [rbp+37h+Size]
0x18000e33b  mov     r11d, edi
0x18000e33e  test    r12d, r12d
0x18000e341  jz      short loc_18000E370
0x18000e343  mov     r15, [rbp+37h+var_68]
0x18000e347  mov     dil, r10b
0x18000e34a  not     dil
0x18000e34d  movsxd  rdx, r11d
0x18000e350  inc     r11d
0x18000e353  mov     cl, [rdx+r15]
0x18000e357  mov     al, [rdx+rsi]
0x18000e35a  and     cl, dil
0x18000e35d  and     al, r10b
0x18000e360  or      cl, al
0x18000e362  mov     [rdx+rsi], cl
0x18000e365  cmp     r11d, r12d
0x18000e368  jb      short loc_18000E34D
0x18000e36a  mov     r15, [rbp+37h+lpMem]
0x18000e36e  xor     edi, edi
0x18000e370  sub     r14d, 1
0x18000e374  jnz     short loc_18000E302
0x18000e376  sub     r8d, 1
0x18000e37a  jns     loc_18000E2F3
0x18000e380  mov     rsi, [rbp+37h+var_40]
0x18000e384  xor     r15d, r15d
0x18000e387  mov     r8, [rbp+37h+var_58]; pbInput
0x18000e38b  lea     rdx, aPrivkeyval; "PrivKeyVal"
0x18000e392  mov     rcx, [rbp+37h+phKey]; hObject
0x18000e396  mov     r9d, r13d; cbInput
0x18000e399  mov     [rsp+0F0h+dwFlags], r15d; dwFlags
0x18000e39e  call    cs:__imp_BCryptSetProperty
0x18000e3a4  mov     ecx, eax
0x18000e3a6  test    eax, eax
0x18000e3a8  jns     short loc_18000E3E3
0x18000e3aa  cmp     eax, 0C000000Dh
0x18000e3af  jnz     short loc_18000E3C5
0x18000e3b1  lea     rsi, aMskdsPrivateke; "msKds-PrivateKeyLength"
0x18000e3b8  jmp     short loc_18000E3D9
0x18000e3ba  mov     r9d, 122h
0x18000e3c0  jmp     loc_18000E1A8
0x18000e3c5  cmp     ecx, 0C0000017h
0x18000e3cb  lea     rax, aMskdsSecretagr; "msKds-SecretAgreementAlgorithmID"
0x18000e3d2  cmovz   rax, rsi
0x18000e3d6  mov     rsi, rax
0x18000e3d9  mov     ebx, ecx
0x18000e3db  mov     r9d, 163h
0x18000e3e1  jmp     short loc_18000E411
0x18000e3e3  mov     rcx, [rbp+37h+phKey]; hKey
0x18000e3e7  xor     edx, edx; dwFlags
0x18000e3e9  call    cs:__imp_BCryptFinalizeKeyPair
0x18000e3ef  mov     ecx, eax; unsigned int
0x18000e3f1  test    eax, eax
0x18000e3f3  jns     loc_18000E481
0x18000e3f9  lea     rsi, aMskdsSecretagr; "msKds-SecretAgreementAlgorithmID"
0x18000e400  mov     ebx, eax
0x18000e402  mov     r9d, 171h; unsigned int
0x18000e408  cmp     eax, 0C0000017h
0x18000e40d  cmovz   rsi, r15
0x18000e411  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000e418  lea     rdx, aStatus; "status"
0x18000e41f  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000e424  or      ebx, 10000000h
0x18000e42a  jge     short loc_18000E493
0x18000e42c  mov     r14, [rbp+37h+arg_58]
0x18000e433  test    r14, r14
0x18000e436  jz      short loc_18000E493
0x18000e438  mov     rax, [rbp+37h+var_50]
0x18000e43c  test    rax, rax
0x18000e43f  jz      short loc_18000E446
0x18000e441  mov     [r14], rax
0x18000e444  jmp     short loc_18000E493
0x18000e446  test    rsi, rsi
0x18000e449  jz      short loc_18000E493
0x18000e44b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e44f  inc     rax
  ... truncated ...
```
