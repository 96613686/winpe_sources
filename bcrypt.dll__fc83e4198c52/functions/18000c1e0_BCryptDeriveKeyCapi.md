# BCryptDeriveKeyCapi

- ea: `0x18000c1e0`
- end: `0x18000cab7`
- name: `BCryptDeriveKeyCapi`
- size: `2263`
- prototype: `NTSTATUS __stdcall(BCRYPT_HASH_HANDLE hHash, BCRYPT_ALG_HANDLE hTargetAlg, PUCHAR pbDerivedKey, ULONG cbDerivedKey, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x180005060`
- `0x180006020`
- `0x1800066f0`
- `0x180006da0`
- `0x1800078e0`
- `0x180007a7c`
- `0x18000c1e0`
- `0x18000cac0`
- `0x18000cae4`
- `0x18000cc10`
- `0x18000ed20`
- `0x1800124c4`
- `0x18001b785`
- `0x18001b79d`
- `0x18001b7a9`
- `0x18001b7b5`
- `0x18001b7e0`
- `0x18001c010`

## string_xrefs

- `0x18000c3aa`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000c429`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000c521`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000c581`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000c5bc`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000c877`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000c960`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000c9db`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000ca95`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptDeriveKeyCapi(
        BCRYPT_HASH_HANDLE hHash,
        BCRYPT_ALG_HANDLE hTargetAlg,
        PUCHAR pbDerivedKey,
        ULONG cbDerivedKey,
        ULONG dwFlags)
{
  size_t v5; // rsi
  _BYTE *v8; // rcx
  NTSTATUS Property; // eax
  int v10; // edi
  __int64 v11; // rdi
  UCHAR *v12; // rbx
  unsigned __int64 v13; // rcx
  __int64 v14; // rcx
  void *v15; // rsp
  void *v16; // rsp
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  unsigned int v20; // r10d
  __int64 v21; // r13
  __int64 v22; // r12
  int v23; // edx
  int v24; // r8d
  unsigned int v25; // r13d
  BOOL v26; // edi
  UCHAR *v28; // rax
  __int64 v29; // rcx
  UCHAR *v30; // r8
  __int64 v31; // rdx
  __m128 v32; // xmm1
  __int64 v33; // xmm1_8
  UCHAR v34; // dl
  int v35; // edx
  int v36; // r8d
  int v37; // edx
  int v38; // r8d
  int v39; // edx
  int v40; // r8d
  NTSTATUS v41; // eax
  __int64 v42; // r9
  int v43; // eax
  __int64 v44; // r9
  NTSTATUS v45; // eax
  int v46; // eax
  __int64 v47; // [rsp+0h] [rbp-40h] BYREF
  ULONG *pcbResult; // [rsp+20h] [rbp-20h]
  ULONG cbSecret[2]; // [rsp+28h] [rbp-18h]
  ULONG v50; // [rsp+30h] [rbp-10h]
  UCHAR pbOutput[4]; // [rsp+40h] [rbp+0h] BYREF
  ULONG v52; // [rsp+44h] [rbp+4h] BYREF
  unsigned int v53; // [rsp+48h] [rbp+8h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp+10h] BYREF
  BCRYPT_HASH_HANDLE hHasha; // [rsp+58h] [rbp+18h] BYREF
  UCHAR v56[8]; // [rsp+60h] [rbp+20h] BYREF
  BCRYPT_HANDLE hObject; // [rsp+68h] [rbp+28h]
  wchar_t v58[8]; // [rsp+70h] [rbp+30h] BYREF
  UCHAR pbInput[64]; // [rsp+80h] [rbp+40h] BYREF
  UCHAR v60[64]; // [rsp+C0h] [rbp+80h] BYREF

  v5 = cbDerivedKey;
  *(_DWORD *)pbOutput = 0;
  *(_QWORD *)v56 = 0;
  phHash = 0;
  hHasha = 0;
  v52 = 0;
  hObject = hTargetAlg;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_qqqdD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      pbDerivedKey,
      hHash,
      hTargetAlg,
      pbDerivedKey,
      cbDerivedKey,
      dwFlags);
    v8 = WPP_GLOBAL_Control;
  }
  if ( dwFlags || !pbDerivedKey || !(_DWORD)v5 )
  {
    v10 = -1073741811;
    if ( v8 == (_BYTE *)&WPP_GLOBAL_Control || (v8[28] & 1) == 0 )
      goto LABEL_33;
    v50 = 7138;
    *(_QWORD *)cbSecret = "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c";
    LODWORD(pcbResult) = -1073741811;
LABEL_32:
    WPP_SF_sDsd(
      *((_QWORD *)v8 + 2),
      (_DWORD)hTargetAlg,
      (_DWORD)pbDerivedKey,
      (unsigned int)"Status",
      (char)pcbResult,
      *(__int64 *)cbSecret,
      v50);
    goto LABEL_33;
  }
  Property = BCryptGetProperty(hHash, L"HashDigestLength", pbOutput, 4u, &v52, 0);
  v10 = Property;
  if ( Property < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_33;
    v50 = 7160;
    *(_QWORD *)cbSecret = "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c";
    LODWORD(pcbResult) = Property;
    goto LABEL_32;
  }
  v11 = (unsigned int)(2 * *(_DWORD *)pbOutput);
  if ( (unsigned int)v11 < (unsigned int)v5 || *(_DWORD *)pbOutput > 0x40u )
  {
    v10 = -1073741811;
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 7167);
    goto LABEL_33;
  }
  v12 = 0;
  if ( !(_DWORD)v11 )
    goto LABEL_102;
  if ( (unsigned int)v11 > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_102;
  v13 = (unsigned int)v11 + g_ulAdditionalProbeSize + 8;
  if ( v13 < (unsigned int)v11 || !(unsigned int)VerifyStackAvailable(v13) )
    goto LABEL_102;
  v14 = v11 + 23;
  if ( v11 + 23 <= (unsigned __int64)(v11 + 8) )
    v14 = 0xFFFFFFFFFFFFFF0LL;
  v15 = alloca(v14 & 0xFFFFFFFFFFFFFFF0uLL);
  v16 = alloca(v14 & 0xFFFFFFFFFFFFFFF0uLL);
  v12 = pbOutput;
  if ( &v47 == (__int64 *)-64LL || (*(_DWORD *)pbOutput = 1801679955, (v12 = (UCHAR *)&v53) == 0) )
  {
LABEL_102:
    if ( v11 + 8 >= (unsigned __int64)(unsigned int)v11 )
    {
      v28 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
      v12 = v28;
      if ( v28 )
      {
        *(_DWORD *)v28 = 1885431112;
        v12 = v28 + 8;
      }
    }
  }
  if ( !v12 )
  {
    v10 = -1073741801;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_33;
    v50 = 7183;
    *(_QWORD *)cbSecret = "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c";
    LODWORD(pcbResult) = -1073741801;
    goto LABEL_32;
  }
  v53 = *(_DWORD *)pbOutput;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_qqdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_GLOBAL_Control, hHash, v12, *(_DWORD *)pbOutput, 0);
  v17 = ValidateBaseHashHandle(hHash);
  v21 = v17;
  if ( !v17 )
  {
    v10 = -1073741816;
    if ( v19 != v18 && (*(_BYTE *)(v19 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(v19 + 16),
        v18,
        v19,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        245);
    goto LABEL_46;
  }
  v22 = *(_QWORD *)(v17 + 8);
  v10 = (*(__int64 (__fastcall **)(_QWORD, UCHAR *, _QWORD, _QWORD))(v22 + 104))(*(_QWORD *)(v17 + 16), v12, v20, 0);
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v23,
        v24,
        (unsigned int)"Status",
        v10,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        255);
    goto LABEL_46;
  }
  if ( (*(_BYTE *)(v22 + 8) & 8) == 0 )
    goto LABEL_23;
  v43 = (*(__int64 (__fastcall **)(_QWORD, UCHAR *, _QWORD, _QWORD))(v22 + 96))(*(_QWORD *)(v21 + 24), v12, v53, 0);
  v10 = v43;
  if ( v43 < 0 )
  {
    v44 = 6155;
LABEL_90:
    DebugTraceError((unsigned int)v43, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v44);
LABEL_46:
    DebugTraceError((unsigned int)v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 7193);
    goto LABEL_27;
  }
  v43 = (*(__int64 (__fastcall **)(_QWORD, UCHAR *, _QWORD, _QWORD))(v22 + 104))(*(_QWORD *)(v21 + 24), v12, v53, 0);
  v10 = v43;
  if ( v43 < 0 )
  {
    v44 = 6164;
    goto LABEL_90;
  }
LABEL_23:
  v25 = *(_DWORD *)pbOutput;
  v26 = *(_DWORD *)pbOutput < (unsigned int)v5;
  if ( !hObject || (_DWORD)v5 != 16 || *(_DWORD *)pbOutput >= 0x20u )
    goto LABEL_25;
  v45 = BCryptGetProperty(hObject, L"AlgorithmName", (PUCHAR)v58, 8u, &v52, 0);
  if ( v45 < 0 )
  {
    DebugTraceError((unsigned int)v45, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 7221);
    v25 = *(_DWORD *)pbOutput;
    goto LABEL_25;
  }
  v46 = wcscmp_0(v58, L"AES");
  v25 = *(_DWORD *)pbOutput;
  if ( v46 )
  {
LABEL_25:
    if ( !v26 )
    {
LABEL_26:
      memcpy_0(pbDerivedKey, v12, v5);
      v10 = 0;
      goto LABEL_27;
    }
  }
  memset_0(pbInput, 54, sizeof(pbInput));
  memset_0(v60, 92, sizeof(v60));
  v29 = 0;
  if ( v25 >= 8 )
  {
    v30 = &v12[v25 - 1];
    v31 = v25 - 1;
    if ( (v60 > v30 || &v60[v31] < v12) && (pbInput > v30 || &pbInput[v31] < v12) )
    {
      if ( v25 < 0x10 )
        goto LABEL_103;
      do
      {
        v32 = (__m128)_mm_loadu_si128((const __m128i *)&v12[v29]);
        *(__m128 *)&pbInput[v29] = _mm_xor_ps((__m128)_mm_loadu_si128((const __m128i *)&pbInput[v29]), v32);
        *(__m128 *)&v60[v29] = _mm_xor_ps((__m128)_mm_loadu_si128((const __m128i *)&v60[v29]), v32);
        v29 = (unsigned int)(v29 + 16);
      }
      while ( (unsigned int)v29 < (v25 & 0xFFFFFFF0) );
      if ( (v25 & 0xF) >= 8 )
      {
LABEL_103:
        do
        {
          v33 = *(_QWORD *)&v12[v29];
          *(_QWORD *)&pbInput[v29] ^= v33;
          *(_QWORD *)&v60[v29] ^= v33;
          v29 = (unsigned int)(v29 + 8);
        }
        while ( (unsigned int)v29 < v25 - (v25 & 7) );
      }
    }
  }
  for ( ; (unsigned int)v29 < v25; v29 = (unsigned int)(v29 + 1) )
  {
    v34 = v12[v29];
    pbInput[v29] ^= v34;
    v60[v29] ^= v34;
  }
  v10 = BCryptGetProperty(hHash, L"ProviderHandle", v56, 8u, &v52, 0);
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v35,
        v36,
        (unsigned int)"Status",
        v10,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        92);
    goto LABEL_27;
  }
  v10 = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)v56, &phHash, 0, 0, 0, 0, 0);
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v37,
        v38,
        (unsigned int)"Status",
        v10,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        105);
    goto LABEL_27;
  }
  v10 = BCryptHashData(phHash, pbInput, 0x40u, 0);
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v39,
        v40,
        (unsigned int)"Status",
        v10,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        115);
    goto LABEL_27;
  }
  v41 = BCryptFinishHash(phHash, v12, *(ULONG *)pbOutput, 0);
  v10 = v41;
  if ( v41 < 0 )
  {
    v42 = 7293;
  }
  else
  {
    v41 = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)v56, &hHasha, 0, 0, 0, 0, 0);
    v10 = v41;
    if ( v41 < 0 )
    {
      v42 = 7306;
    }
    else
    {
      v41 = BCryptHashData(hHasha, v60, 0x40u, 0);
      v10 = v41;
      if ( v41 < 0 )
      {
        v42 = 7316;
      }
      else
      {
        v41 = BCryptFinishHash(hHasha, &v12[*(unsigned int *)pbOutput], *(ULONG *)pbOutput, 0);
        v10 = v41;
        if ( v41 >= 0 )
          goto LABEL_26;
        v42 = 7326;
      }
    }
  }
  DebugTraceError((unsigned int)v41, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v42);
LABEL_27:
  if ( *((_DWORD *)v12 - 2) == 1885431112 )
    ((void (__fastcall *)(UCHAR *))g_pfnFree)(v12 - 8);
LABEL_33:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( hHasha )
    BCryptDestroyHash(hHasha);
  return v10;
}

```

## disassembly

```asm
0x18000c1e0  push    rbp
0x18000c1e2  push    rbx
0x18000c1e3  push    rsi
0x18000c1e4  push    rdi
0x18000c1e5  push    r12
0x18000c1e7  push    r13
0x18000c1e9  push    r14
0x18000c1eb  push    r15
0x18000c1ed  sub     rsp, 118h
0x18000c1f4  lea     rbp, [rsp+40h]
0x18000c1f9  mov     rax, cs:__security_cookie
0x18000c200  xor     rax, rbp
0x18000c203  mov     [rbp+110h+var_50], rax
0x18000c20a  xor     r12d, r12d
0x18000c20d  mov     esi, r9d
0x18000c210  mov     dword ptr [rbp+110h+pbOutput], r12d
0x18000c214  mov     r14, r8
0x18000c217  mov     qword ptr [rbp+110h+var_F0], r12
0x18000c21b  mov     rax, rdx
0x18000c21e  mov     [rbp+110h+phHash], r12
0x18000c222  mov     r15, rcx
0x18000c225  mov     [rbp+110h+hHash], r12
0x18000c229  mov     [rbp+110h+var_10C], r12d
0x18000c22d  mov     [rbp+110h+hObject], rdx
0x18000c231  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c238  lea     r13, WPP_GLOBAL_Control
0x18000c23f  mov     ebx, [rbp+110h+dwFlags]
0x18000c245  cmp     rcx, r13
0x18000c248  jnz     loc_18000C4C3
0x18000c24e  test    ebx, ebx
0x18000c250  jnz     loc_18000C561
0x18000c256  test    r14, r14
0x18000c259  jz      loc_18000C561
0x18000c25f  test    esi, esi
0x18000c261  jz      loc_18000C561
0x18000c267  lea     rax, [rbp+110h+var_10C]
0x18000c26b  mov     [rsp+150h+cbSecret], r12d; dwFlags
0x18000c270  mov     r9d, 4; cbOutput
0x18000c276  mov     [rsp+150h+pcbResult], rax; pcbResult
0x18000c27b  lea     r8, [rbp+110h+pbOutput]; pbOutput
0x18000c27f  mov     rcx, r15; hObject
0x18000c282  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18000c289  call    BCryptGetProperty
0x18000c28e  mov     edi, eax
0x18000c290  test    eax, eax
0x18000c292  js      loc_18000C59A
0x18000c298  mov     eax, dword ptr [rbp+110h+pbOutput]
0x18000c29b  lea     edi, [rax+rax]
0x18000c29e  cmp     edi, esi
0x18000c2a0  jb      loc_18000CA8F
0x18000c2a6  cmp     eax, 40h ; '@'
0x18000c2a9  ja      loc_18000CA8F
0x18000c2af  mov     rbx, r12
0x18000c2b2  test    edi, edi
0x18000c2b4  jz      loc_18000C48D
0x18000c2ba  mov     r13d, edi
0x18000c2bd  cmp     r13, cs:g_ulMaxStackAllocSize
0x18000c2c4  ja      loc_18000C48D
0x18000c2ca  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000c2d1  add     rcx, 8
0x18000c2d5  add     rcx, r13
0x18000c2d8  cmp     rcx, r13
0x18000c2db  jb      loc_18000C48D
0x18000c2e1  call    VerifyStackAvailable
0x18000c2e6  test    eax, eax
0x18000c2e8  jz      loc_18000C48D
0x18000c2ee  lea     rax, [rdi+8]
0x18000c2f2  lea     rcx, [rax+0Fh]
0x18000c2f6  cmp     rcx, rax
0x18000c2f9  ja      short loc_18000C305
0x18000c2fb  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000c305  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000c309  mov     rax, rcx
0x18000c30c  call    __chkstk_0
0x18000c311  sub     rsp, rcx
0x18000c314  lea     rbx, [rsp+150h+pbOutput]
0x18000c319  test    rbx, rbx
0x18000c31c  jz      loc_18000C48D
0x18000c322  mov     dword ptr [rbx], 6B637453h
0x18000c328  add     rbx, 8
0x18000c32c  jz      loc_18000C48D
0x18000c332  test    rbx, rbx
0x18000c335  jz      loc_18000C403
0x18000c33b  mov     r10d, dword ptr [rbp+110h+pbOutput]
0x18000c33f  mov     [rbp+110h+var_108], r10d
0x18000c343  mov     r8, cs:WPP_GLOBAL_Control
0x18000c34a  lea     rdx, WPP_GLOBAL_Control
0x18000c351  cmp     r8, rdx
0x18000c354  jz      short loc_18000C361
0x18000c356  test    byte ptr [r8+1Ch], 4
0x18000c35b  jnz     loc_18000C925
0x18000c361  mov     rcx, r15
0x18000c364  call    ValidateBaseHashHandle
0x18000c369  mov     r13, rax
0x18000c36c  test    rax, rax
0x18000c36f  jz      loc_18000C862
0x18000c375  mov     r12, [rax+8]
0x18000c379  xor     r9d, r9d
0x18000c37c  mov     rcx, [rax+10h]
0x18000c380  mov     r8d, r10d
0x18000c383  mov     rdx, rbx
0x18000c386  mov     rax, [r12+68h]
0x18000c38b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c390  mov     edi, eax
0x18000c392  test    eax, eax
0x18000c394  js      loc_18000C4FC
0x18000c39a  test    byte ptr [r12+8], 8
0x18000c3a0  jnz     loc_18000C98D
0x18000c3a6  mov     r13d, dword ptr [rbp+110h+pbOutput]
0x18000c3aa  lea     r12, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c3b1  mov     rcx, [rbp+110h+hObject]; hObject
0x18000c3b5  xor     edi, edi
0x18000c3b7  cmp     r13d, esi
0x18000c3ba  mov     eax, 1
0x18000c3bf  cmovb   edi, eax
0x18000c3c2  test    rcx, rcx
0x18000c3c5  jz      short loc_18000C3D0
0x18000c3c7  cmp     esi, 10h
0x18000c3ca  jz      loc_18000C9F8
0x18000c3d0  test    edi, edi
0x18000c3d2  jnz     loc_18000C5D1
0x18000c3d8  mov     r8, rsi; Size
0x18000c3db  mov     rdx, rbx; Src
0x18000c3de  mov     rcx, r14; void *
0x18000c3e1  call    memcpy_0
0x18000c3e6  xor     edi, edi
0x18000c3e8  cmp     dword ptr [rbx-8], 70616548h
0x18000c3ef  lea     rcx, [rbx-8]
0x18000c3f3  jnz     short loc_18000C44D
0x18000c3f5  mov     rax, cs:g_pfnFree
0x18000c3fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c401  jmp     short loc_18000C44D
0x18000c403  mov     edi, 0C0000017h
0x18000c408  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c40f  lea     rax, WPP_GLOBAL_Control
0x18000c416  cmp     rcx, rax
0x18000c419  jz      short loc_18000C44D
0x18000c41b  test    byte ptr [rcx+1Ch], 1
0x18000c41f  jz      short loc_18000C44D
0x18000c421  mov     [rsp+150h+var_120], 1C0Fh
0x18000c429  lea     r12, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c430  mov     qword ptr [rsp+150h+cbSecret], r12
0x18000c435  mov     dword ptr [rsp+150h+pcbResult], 0C0000017h
0x18000c43d  mov     rcx, [rcx+10h]
0x18000c441  lea     r9, aStatus; "Status"
0x18000c448  call    WPP_SF_sDsd
0x18000c44d  mov     rcx, [rbp+110h+phHash]; hHash
0x18000c451  test    rcx, rcx
0x18000c454  jnz     loc_18000C8D4
0x18000c45a  mov     rcx, [rbp+110h+hHash]; hHash
0x18000c45e  test    rcx, rcx
0x18000c461  jnz     loc_18000C883
0x18000c467  mov     eax, edi
0x18000c469  mov     rcx, [rbp+110h+var_50]
0x18000c470  xor     rcx, rbp; StackCookie
0x18000c473  call    __security_check_cookie
0x18000c478  lea     rsp, [rbp+0D8h]
0x18000c47f  pop     r15
0x18000c481  pop     r14
0x18000c483  pop     r13
0x18000c485  pop     r12
0x18000c487  pop     rdi
0x18000c488  pop     rsi
0x18000c489  pop     rbx
0x18000c48a  pop     rbp
0x18000c48b  retn
0x18000c48d  mov     eax, edi
0x18000c48f  lea     rcx, [rdi+8]
0x18000c493  cmp     rcx, rax
0x18000c496  jb      loc_18000C332
0x18000c49c  mov     rax, cs:g_pfnAllocate
0x18000c4a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4a8  mov     rbx, rax
0x18000c4ab  test    rax, rax
0x18000c4ae  jz      loc_18000C332
0x18000c4b4  mov     dword ptr [rax], 70616548h
0x18000c4ba  add     rbx, 8
0x18000c4be  jmp     loc_18000C332
0x18000c4c3  test    byte ptr [rcx+1Ch], 4
0x18000c4c7  jz      loc_18000C24E
0x18000c4cd  mov     rcx, [rcx+10h]
0x18000c4d1  mov     edx, 29h ; ')'
0x18000c4d6  mov     [rsp+150h+var_118], ebx
0x18000c4da  mov     r9, r15
0x18000c4dd  mov     [rsp+150h+var_120], esi
0x18000c4e1  mov     qword ptr [rsp+150h+cbSecret], r14
0x18000c4e6  mov     [rsp+150h+pcbResult], rax
0x18000c4eb  call    WPP_SF_qqqdD
0x18000c4f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4f7  jmp     loc_18000C24E
0x18000c4fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c503  lea     rax, WPP_GLOBAL_Control
0x18000c50a  cmp     rcx, rax
0x18000c50d  jz      loc_18000C877
0x18000c513  test    byte ptr [rcx+1Ch], 1
0x18000c517  jz      loc_18000C877
0x18000c51d  mov     rcx, [rcx+10h]
0x18000c521  lea     r12, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c528  mov     [rsp+150h+var_120], 17FFh
0x18000c530  lea     r9, aStatus; "Status"
0x18000c537  mov     qword ptr [rsp+150h+cbSecret], r12
0x18000c53c  mov     dword ptr [rsp+150h+pcbResult], edi
0x18000c540  call    WPP_SF_sDsd
0x18000c545  mov     r9d, 1C19h
0x18000c54b  lea     rdx, aStatus; "Status"
0x18000c552  mov     r8, r12
0x18000c555  mov     ecx, edi
0x18000c557  call    DebugTraceError
0x18000c55c  jmp     loc_18000C3E8
0x18000c561  mov     edi, 0C000000Dh
0x18000c566  cmp     rcx, r13
0x18000c569  jz      loc_18000C44D
0x18000c56f  test    byte ptr [rcx+1Ch], 1
0x18000c573  jz      loc_18000C44D
0x18000c579  mov     [rsp+150h+var_120], 1BE2h
0x18000c581  lea     r12, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c588  mov     qword ptr [rsp+150h+cbSecret], r12
0x18000c58d  mov     dword ptr [rsp+150h+pcbResult], 0C000000Dh
0x18000c595  jmp     loc_18000C43D
0x18000c59a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5a1  cmp     rcx, r13
0x18000c5a4  jz      loc_18000C44D
0x18000c5aa  test    byte ptr [rcx+1Ch], 1
0x18000c5ae  jz      loc_18000C44D
0x18000c5b4  mov     [rsp+150h+var_120], 1BF8h
0x18000c5bc  lea     r12, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c5c3  mov     qword ptr [rsp+150h+cbSecret], r12
0x18000c5c8  mov     dword ptr [rsp+150h+pcbResult], eax
0x18000c5cc  jmp     loc_18000C43D
0x18000c5d1  mov     edx, 36h ; '6'; Val
0x18000c5d6  lea     rcx, [rbp+110h+pbInput]; void *
0x18000c5da  mov     r8d, 40h ; '@'; Size
0x18000c5e0  call    memset_0
0x18000c5e5  mov     edx, 5Ch ; '\'; Val
0x18000c5ea  lea     rcx, [rbp+110h+var_90]; void *
0x18000c5f1  mov     r8d, 40h ; '@'; Size
0x18000c5f7  call    memset_0
0x18000c5fc  xor     ecx, ecx
0x18000c5fe  cmp     r13d, 8
0x18000c602  jb      loc_18000C6CA
0x18000c608  lea     eax, [r13-1]
0x18000c60c  lea     r8, [rax+rbx]
0x18000c610  mov     edx, eax
0x18000c612  lea     rax, [rbp+110h+var_90]
0x18000c619  cmp     rax, r8
0x18000c61c  ja      short loc_18000C631
0x18000c61e  lea     rax, [rbp+110h+var_90]
0x18000c625  add     rax, rdx
0x18000c628  cmp     rax, rbx
0x18000c62b  jnb     loc_18000C6CA
0x18000c631  lea     rax, [rbp+110h+pbInput]
0x18000c635  cmp     rax, r8
0x18000c638  ja      short loc_18000C64A
0x18000c63a  lea     rax, [rbp+110h+pbInput]
0x18000c63e  add     rax, rdx
0x18000c641  cmp     rax, rbx
0x18000c644  jnb     loc_18000C6CA
0x18000c64a  cmp     r13d, 10h
0x18000c64e  jb      short loc_18000C68F
0x18000c650  mov     edx, r13d
0x18000c653  and     edx, 0FFFFFFF0h
0x18000c656  movdqu  xmm1, xmmword ptr [rcx+rbx]
0x18000c65b  movdqu  xmm0, xmmword ptr [rbp+rcx+110h+pbInput]
0x18000c661  xorps   xmm0, xmm1
0x18000c664  movdqu  xmmword ptr [rbp+rcx+110h+pbInput], xmm0
0x18000c66a  movdqu  xmm0, xmmword ptr [rbp+rcx+110h+var_90]
0x18000c673  xorps   xmm0, xmm1
0x18000c676  movdqu  xmmword ptr [rbp+rcx+110h+var_90], xmm0
0x18000c67f  add     ecx, 10h
0x18000c682  cmp     ecx, edx
0x18000c684  jb      short loc_18000C656
0x18000c686  mov     eax, r13d
0x18000c689  and     al, 0Fh
0x18000c68b  cmp     al, 8
0x18000c68d  jb      short loc_18000C6CA
0x18000c68f  mov     eax, r13d
0x18000c692  mov     edx, r13d
0x18000c695  and     eax, 7
0x18000c698  sub     edx, eax
0x18000c69a  movq    xmm1, qword ptr [rcx+rbx]
0x18000c69f  movq    xmm0, qword ptr [rbp+rcx+110h+pbInput]
0x18000c6a5  xorps   xmm0, xmm1
0x18000c6a8  movq    qword ptr [rbp+rcx+110h+pbInput], xmm0
0x18000c6ae  movq    xmm0, qword ptr [rbp+rcx+110h+var_90]
0x18000c6b7  xorps   xmm1, xmm0
0x18000c6ba  movq    qword ptr [rbp+rcx+110h+var_90], xmm1
0x18000c6c3  add     ecx, 8
0x18000c6c6  cmp     ecx, edx
0x18000c6c8  jb      short loc_18000C69A
0x18000c6ca  cmp     ecx, r13d
0x18000c6cd  jnb     short loc_18000C6E5
0x18000c6cf  movzx   edx, byte ptr [rcx+rbx]
0x18000c6d3  xor     [rbp+rcx+110h+pbInput], dl
0x18000c6d7  xor     [rbp+rcx+110h+var_90], dl
0x18000c6de  inc     ecx
0x18000c6e0  cmp     ecx, r13d
0x18000c6e3  jb      short loc_18000C6CF
0x18000c6e5  lea     rax, [rbp+110h+var_10C]
0x18000c6e9  mov     [rsp+150h+cbSecret], 0; dwFlags
0x18000c6f1  mov     r9d, 8; cbOutput
  ... truncated ...
```
