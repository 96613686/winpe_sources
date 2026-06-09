# CreateVsmKeyAttestationIdentityClaim

- ea: `0x140013124`
- end: `0x1400136f8`
- name: `CreateVsmKeyAttestationIdentityClaim`
- size: `1492`
- prototype: `__int64 __usercall@<rax>(BCRYPT_KEY_HANDLE hKey@<rcx>, __int64, SIZE_T uBytes, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140012ee8`

## callees

- `0x140003ad6`
- `0x14001212c`
- `0x1400124e8`
- `0x14001260c`
- `0x140012aac`
- `0x140013124`
- `0x140037b10`
- `0x140037edc`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1400132bf`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1400133b8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1400134dd`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1400132bf`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1400133b8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1400134dd`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400136a5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400136af`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400136b8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400136c1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400136cb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400136d5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400136a5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400136af`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400136b8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400136c1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400136cb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400136d5`
- `bcrypt!BCryptSignHash` at `0x140013407`
- `bcrypt!BCryptSignHash` at `0x140013407`
- `bcrypt!BCryptGetProperty` at `0x1400132a6`
- `bcrypt!BCryptGetProperty` at `0x1400132fe`
- `bcrypt!BCryptGetProperty` at `0x140013393`
- `bcrypt!BCryptGetProperty` at `0x1400132a6`
- `bcrypt!BCryptGetProperty` at `0x1400132fe`
- `bcrypt!BCryptGetProperty` at `0x140013393`

## string_xrefs

- `0x140013211`: `onecore\ds\security\cryptoapi\ncrypt\ium\trustlet\bcryptiumkeyattest.cxx`
- `0x140013244`: `onecore\ds\security\cryptoapi\ncrypt\ium\trustlet\bcryptiumkeyattest.cxx`
- `0x140013618`: `onecore\ds\security\cryptoapi\ncrypt\ium\trustlet\bcryptiumkeyattest.cxx`
- `0x140013691`: `onecore\ds\security\cryptoapi\ncrypt\ium\trustlet\bcryptiumkeyattest.cxx`
- `0x1400131df`: `CreateVsmKeyAttestationIdentityClaim`

## pseudocode

```c
__int64 __fastcall CreateVsmKeyAttestationIdentityClaim(
        BCRYPT_KEY_HANDLE hKey,
        int **a2,
        const void *a3,
        unsigned int a4,
        __int64 a5,
        SIZE_T uBytes,
        unsigned int *a7)
{
  size_t v8; // r13
  int *v10; // rax
  unsigned int v11; // r14d
  char v12; // r15
  int *v13; // rax
  __int64 v14; // rbx
  unsigned int *v15; // rsi
  unsigned int v16; // ebx
  __int64 v17; // r8
  __int64 v18; // rcx
  UCHAR *v19; // r14
  int ClaimPaddingInfo; // eax
  void *v21; // rcx
  int Property; // eax
  HLOCAL v23; // rax
  PUCHAR *p_pbInput; // rcx
  bool v25; // zf
  size_t v26; // r15
  char v27; // r9
  __int64 v28; // rcx
  __int64 v29; // r8
  NTSTATUS v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // edx
  int v33; // r8d
  unsigned int v34; // ecx
  unsigned int v35; // eax
  int v36; // r8d
  int v37; // ecx
  ULONG v38; // r8d
  unsigned int v39; // ecx
  char *v40; // rax
  int *v41; // r12
  unsigned int v42; // ebx
  unsigned int v43; // ebx
  unsigned int v44; // ebx
  unsigned int v45; // ebx
  ULONG v46; // ebx
  __int64 v47; // r8
  __int64 v48; // rcx
  int v49; // eax
  void *pPaddingInfo; // [rsp+50h] [rbp-51h]
  UCHAR *v52; // [rsp+58h] [rbp-49h]
  ULONG cbOutput; // [rsp+60h] [rbp-41h] BYREF
  UCHAR pbOutput[4]; // [rsp+64h] [rbp-3Dh] BYREF
  ULONG v55; // [rsp+68h] [rbp-39h] BYREF
  size_t Size; // [rsp+6Ch] [rbp-35h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-29h] BYREF
  HLOCAL v58; // [rsp+80h] [rbp-21h]
  ULONG pcbResult; // [rsp+88h] [rbp-19h] BYREF
  void *v60; // [rsp+90h] [rbp-11h] BYREF
  PUCHAR pbInput; // [rsp+98h] [rbp-9h] BYREF
  void *v62; // [rsp+A0h] [rbp-1h]
  char v63; // [rsp+F8h] [rbp+57h]

  v8 = a4;
  v52 = 0;
  *(_DWORD *)pbOutput = 0;
  v10 = *a2;
  pcbResult = 0;
  if ( v10 )
  {
    v11 = *v10;
    v62 = (void *)*((_QWORD *)v10 + 1);
  }
  else
  {
    v11 = 0;
    v62 = 0;
  }
  pPaddingInfo = 0;
  v60 = 0;
  v55 = 0;
  hMem = 0;
  Size = 0;
  v58 = 0;
  cbOutput = 0;
  pbInput = 0;
  if ( !a5 || (v12 = 0, !(_DWORD)uBytes) )
    v12 = 1;
  v13 = a2[1];
  v63 = v12;
  if ( v13 )
    v14 = *((_QWORD *)v13 + 1);
  else
    v14 = 0;
  v15 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_9b7bb3a056503060c4cc3cbe91885dc2_Traceguids,
      "CreateVsmKeyAttestationIdentityClaim");
  *a7 = 0;
  if ( !v14 )
  {
    v16 = -1073741811;
    v17 = 873;
    v18 = 3221225485LL;
LABEL_15:
    VBS_ATTEST_TRACE_ERROR_IN(
      v18,
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\trustlet\\bcryptiumkeyattest.cxx",
      v17);
    v19 = 0;
LABEL_84:
    v21 = pPaddingInfo;
    goto LABEL_85;
  }
  ClaimPaddingInfo = BCryptIumGetClaimPaddingInfo(hKey, a2, &v55, &v60);
  v16 = ClaimPaddingInfo;
  if ( ClaimPaddingInfo >= 0 )
  {
    pPaddingInfo = v60;
    Property = BCryptIumBuildClaimPadding(v55, v60, &hMem, &Size);
    v16 = Property;
    if ( Property < 0 )
    {
      v17 = 895;
LABEL_20:
      v18 = (unsigned int)Property;
      goto LABEL_15;
    }
    Property = BCryptGetProperty(hKey, L"AlgorithmName", 0, 0, &cbOutput, 0);
    v16 = Property;
    if ( Property < 0 )
    {
      v17 = 908;
      goto LABEL_20;
    }
    v23 = LocalAlloc(0, cbOutput);
    v58 = v23;
    if ( !v23 )
    {
      v18 = 3221225495LL;
      v17 = 915;
      v16 = -1073741801;
      goto LABEL_15;
    }
    Property = BCryptGetProperty(hKey, L"AlgorithmName", (PUCHAR)v23, cbOutput, &cbOutput, 0);
    v16 = Property;
    if ( Property < 0 )
    {
      v17 = 927;
      goto LABEL_20;
    }
    p_pbInput = &pbInput;
    v25 = v12 == 0;
    v26 = (unsigned int)Size;
    if ( !v25 )
      p_pbInput = 0;
    Property = BCryptIumBuildIdentityClaimHashBuffer(
                 hKey,
                 (__int64)a3,
                 v8,
                 (UCHAR *)hMem,
                 Size,
                 (UCHAR *)v58,
                 cbOutput,
                 (HLOCAL *)p_pbInput,
                 (_DWORD *)&Size + 1,
                 a2);
    v16 = Property;
    if ( Property < 0 )
    {
      v17 = 945;
      goto LABEL_20;
    }
    Property = BCryptGetProperty(hKey, L"SignatureLength", pbOutput, 4u, &pcbResult, 0);
    v16 = Property;
    if ( Property < 0 )
    {
      v17 = 958;
      goto LABEL_20;
    }
    v27 = v63;
    if ( !v63 )
    {
      v52 = (UCHAR *)LocalAlloc(0, *(unsigned int *)pbOutput);
      if ( !v52 )
      {
        v28 = 3221225495LL;
        v29 = 968;
        v16 = -1073741801;
LABEL_82:
        VBS_ATTEST_TRACE_ERROR_IN(
          v28,
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\trustlet\\bcryptiumkeyattest.cxx",
          v29);
        goto LABEL_83;
      }
      v30 = BCryptSignHash(hKey, pPaddingInfo, pbInput, HIDWORD(Size), v52, *(ULONG *)pbOutput, (ULONG *)pbOutput, v55);
      v16 = v30;
      if ( v30 < 0 )
      {
        v29 = 983;
        v28 = (unsigned int)v30;
        goto LABEL_82;
      }
      v27 = 0;
    }
    if ( (int)v8 + 32 < (unsigned int)v8 )
    {
      v16 = -1073741675;
      goto LABEL_81;
    }
    v31 = v11 + v8 + 32;
    v32 = -1;
    v33 = -1;
    if ( v31 >= v11 )
      v33 = v11 + v8 + 32;
    v16 = v31 < v11 ? 0xC0000095 : 0;
    if ( v31 < v11 )
      goto LABEL_81;
    v34 = *a2[1];
    v35 = v34 + v33;
    v36 = -1;
    if ( v35 >= v34 )
      v36 = v35;
    v16 = v35 < v34 ? 0xC0000095 : 0;
    if ( v35 < v34 )
      goto LABEL_81;
    v37 = v36 + v26;
    if ( v36 + (int)v26 < (unsigned int)v26
      || (v38 = v37 + cbOutput, v37 + cbOutput < cbOutput)
      || (v39 = v38 + *(_DWORD *)pbOutput, v38 + *(_DWORD *)pbOutput < *(_DWORD *)pbOutput) )
    {
      v16 = -1073741675;
LABEL_81:
      v29 = 1023;
      v28 = v16;
      goto LABEL_82;
    }
    if ( v39 + 12 >= 0xC )
      v32 = v39 + 12;
    v16 = v39 >= 0xFFFFFFF4 ? 0xC0000095 : 0;
    *a7 = v32;
    if ( v39 + 12 < 0xC )
      goto LABEL_81;
    if ( v27 )
    {
LABEL_83:
      v19 = v52;
      goto LABEL_84;
    }
    if ( (unsigned int)uBytes < v32 )
    {
      v28 = 3221225507LL;
      v29 = 1030;
      v16 = -1073741789;
      goto LABEL_82;
    }
    v40 = (char *)LocalAlloc(0, (unsigned int)uBytes);
    v15 = (unsigned int *)v40;
    if ( !v40 )
    {
      v28 = 3221225495LL;
      v29 = 1041;
      v16 = -1073741801;
      goto LABEL_82;
    }
    v41 = a2[1];
    *(_DWORD *)v40 = 1396788054;
    *((_DWORD *)v40 + 1) = 2;
    *((_DWORD *)v40 + 2) = 6;
    *(_QWORD *)(v40 + 12) = 1212369238;
    *((_DWORD *)v40 + 8) = v26;
    *((_DWORD *)v40 + 10) = *(_DWORD *)pbOutput;
    *((_DWORD *)v40 + 5) = v8;
    *((_DWORD *)v40 + 7) = *v41;
    *((_DWORD *)v40 + 6) = v11;
    *((_DWORD *)v40 + 9) = cbOutput;
    memcpy_0(v40 + 44, a3, v8);
    v42 = v8 + 44;
    if ( (int)v8 + 44 < (unsigned int)v8 )
    {
      v29 = 1072;
LABEL_60:
      v16 = -1073741675;
      v28 = 3221225621LL;
      goto LABEL_82;
    }
    memcpy_0((char *)v15 + v42, v62, v11);
    v43 = v11 + v42;
    if ( v43 < v11 )
    {
      v29 = 1080;
      goto LABEL_60;
    }
    memcpy_0((char *)v15 + v43, *((const void **)v41 + 1), v15[7]);
    v44 = v15[7] + v43;
    if ( v44 < v15[7] )
    {
      v29 = 1088;
      goto LABEL_60;
    }
    memcpy_0((char *)v15 + v44, hMem, v26);
    v45 = v26 + v44;
    if ( v45 < (unsigned int)v26 )
    {
      v29 = 1096;
      goto LABEL_60;
    }
    memcpy_0((char *)v15 + v45, v58, cbOutput);
    v46 = cbOutput + v45;
    if ( v46 < cbOutput )
    {
      v29 = 1104;
      goto LABEL_60;
    }
    v19 = v52;
    memcpy_0((char *)v15 + v46, v52, *(unsigned int *)pbOutput);
    if ( v46 + *(_DWORD *)pbOutput >= *(_DWORD *)pbOutput )
    {
      LODWORD(a7) = 0;
      v49 = VBSAttestationSerializeAttestationStatement(v15, 0, &a7);
      v16 = v49;
      if ( v49 >= 0 )
      {
        if ( (unsigned int)a7 > (unsigned int)uBytes )
        {
          v48 = 3221225507LL;
          v47 = 1133;
          v16 = -1073741789;
          goto LABEL_71;
        }
        v49 = VBSAttestationSerializeAttestationStatement(v15, a5, &a7);
        v16 = v49;
        if ( v49 >= 0 )
        {
          v16 = 0;
          goto LABEL_84;
        }
        v47 = 1144;
      }
      else
      {
        v47 = 1125;
      }
      v48 = (unsigned int)v49;
    }
    else
    {
      v16 = -1073741675;
      v47 = 1112;
      v48 = 3221225621LL;
    }
LABEL_71:
    VBS_ATTEST_TRACE_ERROR_IN(
      v48,
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\trustlet\\bcryptiumkeyattest.cxx",
      v47);
    goto LABEL_84;
  }
  VBS_ATTEST_TRACE_ERROR_IN(
    (unsigned int)ClaimPaddingInfo,
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\trustlet\\bcryptiumkeyattest.cxx",
    884);
  v21 = v60;
  v19 = 0;
LABEL_85:
  LocalFree(v21);
  LocalFree(hMem);
  LocalFree(v19);
  LocalFree(v15);
  LocalFree(pbInput);
  LocalFree(v58);
  return v16;
}

```

## disassembly

```asm
0x140013124  mov     [rsp-8+arg_0], rbx
0x140013129  mov     [rsp-8+Src], r8
0x14001312e  push    rbp
0x14001312f  push    rsi
0x140013130  push    rdi
0x140013131  push    r12
0x140013133  push    r13
0x140013135  push    r14
0x140013137  push    r15
0x140013139  lea     rbp, [rsp-0Fh]
0x14001313e  sub     rsp, 0B0h
0x140013145  mov     r12, rdx
0x140013148  mov     r13d, r9d
0x14001314b  xor     edx, edx
0x14001314d  mov     rdi, rcx
0x140013150  mov     [rbp+3Fh+var_88], rdx
0x140013154  mov     dword ptr [rbp+3Fh+pbOutput], edx
0x140013157  mov     rax, [r12]
0x14001315b  mov     [rbp+3Fh+var_58], edx
0x14001315e  test    rax, rax
0x140013161  jz      short loc_140013170
0x140013163  mov     rcx, [rax+8]
0x140013167  mov     r14d, [rax]
0x14001316a  mov     [rbp+3Fh+var_40], rcx
0x14001316e  jmp     short loc_140013177
0x140013170  mov     r14d, edx
0x140013173  mov     [rbp+3Fh+var_40], rdx
0x140013177  mov     [rbp+3Fh+pPaddingInfo], rdx
0x14001317b  mov     [rbp+3Fh+var_50], rdx
0x14001317f  mov     [rbp+3Fh+var_78], edx
0x140013182  mov     [rbp+3Fh+hMem], rdx
0x140013186  mov     dword ptr [rbp+3Fh+Size], edx
0x140013189  mov     [rbp+3Fh+var_60], rdx
0x14001318d  mov     [rbp+3Fh+cbOutput], edx
0x140013190  mov     [rbp+3Fh+pbInput], rdx
0x140013194  mov     dword ptr [rbp+3Fh+Size+4], edx
0x140013197  cmp     [rbp+3Fh+arg_20], rdx
0x14001319b  jz      short loc_1400131A5
0x14001319d  mov     r15b, dl
0x1400131a0  cmp     dword ptr [rbp+3Fh+uBytes], edx
0x1400131a3  jnz     short loc_1400131A8
0x1400131a5  mov     r15b, 1
0x1400131a8  mov     rax, [r12+8]
0x1400131ad  mov     [rbp+3Fh+arg_8], r15b
0x1400131b1  test    rax, rax
0x1400131b4  jz      short loc_1400131BC
0x1400131b6  mov     rbx, [rax+8]
0x1400131ba  jmp     short loc_1400131BF
0x1400131bc  mov     rbx, rdx
0x1400131bf  mov     rsi, rdx
0x1400131c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400131c9  lea     rax, WPP_GLOBAL_Control
0x1400131d0  cmp     rcx, rax
0x1400131d3  jz      short loc_1400131F9
0x1400131d5  test    byte ptr [rcx+1Ch], 4
0x1400131d9  jz      short loc_1400131F9
0x1400131db  mov     rcx, [rcx+10h]
0x1400131df  lea     r9, aCreatevsmkeyat_1; "CreateVsmKeyAttestationIdentityClaim"
0x1400131e6  mov     edx, 0Bh
0x1400131eb  lea     r8, WPP_9b7bb3a056503060c4cc3cbe91885dc2_Traceguids
0x1400131f2  call    WPP_SF_s
0x1400131f7  xor     edx, edx
0x1400131f9  mov     rax, [rbp+3Fh+arg_30]
0x1400131fd  mov     [rax], edx
0x1400131ff  test    rbx, rbx
0x140013202  jnz     short loc_140013225
0x140013204  mov     ebx, 0C000000Dh
0x140013209  mov     r8d, 369h
0x14001320f  mov     ecx, ebx
0x140013211  lea     rdx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x140013218  call    VBS_ATTEST_TRACE_ERROR_IN
0x14001321d  mov     r14, rsi
0x140013220  jmp     loc_1400136A1
0x140013225  lea     r9, [rbp+3Fh+var_50]
0x140013229  mov     rdx, r12
0x14001322c  lea     r8, [rbp+3Fh+var_78]
0x140013230  mov     rcx, rdi
0x140013233  call    BCryptIumGetClaimPaddingInfo
0x140013238  mov     ebx, eax
0x14001323a  test    eax, eax
0x14001323c  jns     short loc_14001325E
0x14001323e  mov     r8d, 374h
0x140013244  lea     rdx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x14001324b  mov     ecx, eax
0x14001324d  call    VBS_ATTEST_TRACE_ERROR_IN
0x140013252  mov     rcx, [rbp+3Fh+var_50]
0x140013256  mov     r14, rsi
0x140013259  jmp     loc_1400136A5
0x14001325e  mov     rax, [rbp+3Fh+var_50]
0x140013262  lea     r9, [rbp+3Fh+Size]
0x140013266  mov     ecx, [rbp+3Fh+var_78]
0x140013269  lea     r8, [rbp+3Fh+hMem]
0x14001326d  mov     rdx, rax
0x140013270  mov     [rbp+3Fh+pPaddingInfo], rax
0x140013274  call    BCryptIumBuildClaimPadding
0x140013279  mov     ebx, eax
0x14001327b  test    eax, eax
0x14001327d  jns     short loc_140013289
0x14001327f  mov     r8d, 37Fh
0x140013285  mov     ecx, eax
0x140013287  jmp     short loc_140013211
0x140013289  lea     rax, [rbp+3Fh+cbOutput]
0x14001328d  mov     [rsp+0E0h+dwFlags], esi; dwFlags
0x140013291  xor     r9d, r9d; cbOutput
0x140013294  mov     [rsp+0E0h+pcbResult], rax; pcbResult
0x140013299  xor     r8d, r8d; pbOutput
0x14001329c  lea     rdx, pszProperty; "AlgorithmName"
0x1400132a3  mov     rcx, rdi; hObject
0x1400132a6  call    cs:__imp_BCryptGetProperty
0x1400132ac  mov     ebx, eax
0x1400132ae  test    eax, eax
0x1400132b0  jns     short loc_1400132BA
0x1400132b2  mov     r8d, 38Ch
0x1400132b8  jmp     short loc_140013285
0x1400132ba  mov     edx, [rbp+3Fh+cbOutput]; uBytes
0x1400132bd  xor     ecx, ecx; uFlags
0x1400132bf  call    cs:__imp_LocalAlloc
0x1400132c5  mov     [rbp+3Fh+var_60], rax
0x1400132c9  test    rax, rax
0x1400132cc  jnz     short loc_1400132E0
0x1400132ce  mov     ecx, 0C0000017h
0x1400132d3  mov     r8d, 393h
0x1400132d9  mov     ebx, ecx
0x1400132db  jmp     loc_140013211
0x1400132e0  mov     r9d, [rbp+3Fh+cbOutput]; cbOutput
0x1400132e4  lea     rcx, [rbp+3Fh+cbOutput]
0x1400132e8  mov     [rsp+0E0h+dwFlags], esi; dwFlags
0x1400132ec  lea     rdx, pszProperty; "AlgorithmName"
0x1400132f3  mov     [rsp+0E0h+pcbResult], rcx; pcbResult
0x1400132f8  mov     r8, rax; pbOutput
0x1400132fb  mov     rcx, rdi; hObject
0x1400132fe  call    cs:__imp_BCryptGetProperty
0x140013304  mov     ebx, eax
0x140013306  test    eax, eax
0x140013308  jns     short loc_140013315
0x14001330a  mov     r8d, 39Fh
0x140013310  jmp     loc_140013285
0x140013315  mov     r9, [rbp+3Fh+hMem]
0x140013319  lea     rcx, [rbp+3Fh+pbInput]
0x14001331d  mov     rdx, [rbp+3Fh+Src]
0x140013321  xor     eax, eax
0x140013323  mov     [rsp+0E0h+var_98], r12
0x140013328  test    r15b, r15b
0x14001332b  mov     r15d, dword ptr [rbp+3Fh+Size]
0x14001332f  mov     r8d, r13d
0x140013332  cmovnz  rcx, rax
0x140013336  lea     rax, [rbp+3Fh+Size+4]
0x14001333a  mov     [rsp+0E0h+var_A0], rax
0x14001333f  mov     eax, [rbp+3Fh+cbOutput]
0x140013342  mov     qword ptr [rsp+0E0h+var_A8], rcx
0x140013347  mov     rcx, rdi
0x14001334a  mov     dword ptr [rsp+0E0h+var_B0], eax
0x14001334e  mov     rax, [rbp+3Fh+var_60]
0x140013352  mov     qword ptr [rsp+0E0h+dwFlags], rax
0x140013357  mov     dword ptr [rsp+0E0h+pcbResult], r15d
0x14001335c  call    BCryptIumBuildIdentityClaimHashBuffer
0x140013361  mov     ebx, eax
0x140013363  test    eax, eax
0x140013365  jns     short loc_140013372
0x140013367  mov     r8d, 3B1h
0x14001336d  jmp     loc_140013285
0x140013372  lea     rax, [rbp+3Fh+var_58]
0x140013376  mov     [rsp+0E0h+dwFlags], esi; dwFlags
0x14001337a  mov     r9d, 4; cbOutput
0x140013380  mov     [rsp+0E0h+pcbResult], rax; pcbResult
0x140013385  lea     r8, [rbp+3Fh+pbOutput]; pbOutput
0x140013389  mov     rcx, rdi; hObject
0x14001338c  lea     rdx, aSignaturelengt; "SignatureLength"
0x140013393  call    cs:__imp_BCryptGetProperty
0x140013399  mov     ebx, eax
0x14001339b  test    eax, eax
0x14001339d  jns     short loc_1400133AA
0x14001339f  mov     r8d, 3BEh
0x1400133a5  jmp     loc_140013285
0x1400133aa  mov     r9b, [rbp+3Fh+arg_8]
0x1400133ae  test    r9b, r9b
0x1400133b1  jnz     short loc_140013424
0x1400133b3  mov     edx, dword ptr [rbp+3Fh+pbOutput]; uBytes
0x1400133b6  xor     ecx, ecx; uFlags
0x1400133b8  call    cs:__imp_LocalAlloc
0x1400133be  mov     [rbp+3Fh+var_88], rax
0x1400133c2  mov     rcx, rax
0x1400133c5  test    rax, rax
0x1400133c8  jnz     short loc_1400133DC
0x1400133ca  mov     ecx, 0C0000017h
0x1400133cf  mov     r8d, 3C8h
0x1400133d5  mov     ebx, ecx
0x1400133d7  jmp     loc_140013691
0x1400133dc  mov     eax, [rbp+3Fh+var_78]
0x1400133df  mov     r9d, dword ptr [rbp+3Fh+Size+4]; cbInput
0x1400133e3  mov     r8, [rbp+3Fh+pbInput]; pbInput
0x1400133e7  mov     rdx, [rbp+3Fh+pPaddingInfo]; pPaddingInfo
0x1400133eb  mov     [rsp+0E0h+var_A8], eax; dwFlags
0x1400133ef  lea     rax, [rbp+3Fh+pbOutput]
0x1400133f3  mov     [rsp+0E0h+var_B0], rax; pcbResult
0x1400133f8  mov     eax, dword ptr [rbp+3Fh+pbOutput]
0x1400133fb  mov     [rsp+0E0h+dwFlags], eax; cbOutput
0x1400133ff  mov     [rsp+0E0h+pcbResult], rcx; pbOutput
0x140013404  mov     rcx, rdi; hKey
0x140013407  call    cs:__imp_BCryptSignHash
0x14001340d  mov     ebx, eax
0x14001340f  test    eax, eax
0x140013411  jns     short loc_140013420
0x140013413  mov     r8d, 3D7h
0x140013419  mov     ecx, eax
0x14001341b  jmp     loc_140013691
0x140013420  mov     r9b, [rbp+3Fh+arg_8]
0x140013424  lea     eax, [r13+20h]
0x140013428  cmp     eax, r13d
0x14001342b  jb      loc_140013684
0x140013431  add     eax, r14d
0x140013434  or      edx, 0FFFFFFFFh
0x140013437  cmp     eax, r14d
0x14001343a  mov     r8d, edx
0x14001343d  mov     edi, 0C0000095h
0x140013442  cmovnb  r8d, eax
0x140013446  sbb     ebx, ebx
0x140013448  and     ebx, edi
0x14001344a  cmp     eax, r14d
0x14001344d  jb      loc_140013689
0x140013453  mov     rax, [r12+8]
0x140013458  mov     ecx, [rax]
0x14001345a  lea     eax, [rcx+r8]
0x14001345e  mov     r8d, edx
0x140013461  cmp     eax, ecx
0x140013463  cmovnb  r8d, eax
0x140013467  sbb     ebx, ebx
0x140013469  and     ebx, edi
0x14001346b  cmp     eax, ecx
0x14001346d  jb      loc_140013689
0x140013473  lea     ecx, [r8+r15]
0x140013477  cmp     ecx, r15d
0x14001347a  jb      short loc_140013493
0x14001347c  mov     eax, [rbp+3Fh+cbOutput]
0x14001347f  lea     r8d, [rcx+rax]
0x140013483  cmp     r8d, eax
0x140013486  jb      short loc_140013493
0x140013488  mov     eax, dword ptr [rbp+3Fh+pbOutput]
0x14001348b  lea     ecx, [r8+rax]
0x14001348f  cmp     ecx, eax
0x140013491  jnb     short loc_14001349A
0x140013493  mov     ebx, edi
0x140013495  jmp     loc_140013689
0x14001349a  lea     eax, [rcx+0Ch]
0x14001349d  mov     rcx, [rbp+3Fh+arg_30]
0x1400134a1  cmp     eax, 0Ch
0x1400134a4  cmovnb  edx, eax
0x1400134a7  sbb     ebx, ebx
0x1400134a9  and     ebx, edi
0x1400134ab  mov     [rcx], edx
0x1400134ad  cmp     eax, 0Ch
0x1400134b0  jb      loc_140013689
0x1400134b6  test    r9b, r9b
0x1400134b9  jnz     loc_14001369D
0x1400134bf  mov     eax, dword ptr [rbp+3Fh+uBytes]
0x1400134c2  cmp     eax, edx
0x1400134c4  jnb     short loc_1400134D8
0x1400134c6  mov     ecx, 0C0000023h
0x1400134cb  mov     r8d, 406h
0x1400134d1  mov     ebx, ecx
0x1400134d3  jmp     loc_140013691
0x1400134d8  mov     rdx, rax; uBytes
0x1400134db  xor     ecx, ecx; uFlags
0x1400134dd  call    cs:__imp_LocalAlloc
0x1400134e3  mov     rsi, rax
0x1400134e6  test    rax, rax
0x1400134e9  jnz     short loc_1400134FD
0x1400134eb  mov     ecx, 0C0000017h
0x1400134f0  mov     r8d, 411h
0x1400134f6  mov     ebx, ecx
0x1400134f8  jmp     loc_140013691
0x1400134fd  mov     r12, [r12+8]
0x140013502  lea     rcx, [rsi+2Ch]; void *
0x140013506  mov     rdx, [rbp+3Fh+Src]; Src
0x14001350a  mov     r8, r13; Size
0x14001350d  mov     dword ptr [rax], 53414B56h
0x140013513  mov     dword ptr [rax+4], 2
0x14001351a  mov     dword ptr [rax+8], 6
0x140013521  mov     qword ptr [rax+0Ch], 48434956h
0x140013529  mov     [rax+20h], r15d
0x14001352d  mov     eax, dword ptr [rbp+3Fh+pbOutput]
0x140013530  mov     [rsi+28h], eax
0x140013533  mov     [rsi+14h], r13d
0x140013537  mov     eax, [r12]
0x14001353b  mov     [rsi+1Ch], eax
0x14001353e  mov     [rsi+18h], r14d
0x140013542  mov     eax, [rbp+3Fh+cbOutput]
0x140013545  mov     [rsi+24h], eax
0x140013548  call    memcpy_0
0x14001354d  lea     ebx, [r13+2Ch]
0x140013551  cmp     ebx, r13d
0x140013554  jnb     short loc_140013565
0x140013556  mov     r8d, 430h
0x14001355c  mov     ebx, edi
0x14001355e  mov     ecx, edi
0x140013560  jmp     loc_140013691
0x140013565  mov     rdx, [rbp+3Fh+var_40]; Src
0x140013569  mov     ecx, ebx
0x14001356b  add     rcx, rsi; void *
0x14001356e  mov     r8d, r14d; Size
  ... truncated ...
```
