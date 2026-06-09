# CreateVsmKeyAttestationRootClaim

- ea: `0x140013700`
- end: `0x140013ae5`
- name: `CreateVsmKeyAttestationRootClaim`
- size: `997`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140012ee8`

## callees

- `0x140003ad6`
- `0x14001212c`
- `0x140012864`
- `0x140013700`
- `0x140037b10`
- `0x140037edc`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x140013862`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x140013872`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x140013951`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x140013862`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x140013872`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x140013951`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140013aa6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140013aaf`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140013ab9`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140013ac2`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140013aa6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140013aaf`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140013ab9`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140013ac2`
- `IUMBASE!GetSignedReport` at `0x140013825`
- `IUMBASE!GetSignedReport` at `0x1400138c0`
- `IUMBASE!GetSignedReport` at `0x140013825`
- `IUMBASE!GetSignedReport` at `0x1400138c0`

## string_xrefs

- `0x1400137d7`: `onecore\ds\security\cryptoapi\ncrypt\ium\trustlet\bcryptiumkeyattest.cxx`
- `0x1400139fe`: `onecore\ds\security\cryptoapi\ncrypt\ium\trustlet\bcryptiumkeyattest.cxx`
- `0x140013a93`: `onecore\ds\security\cryptoapi\ncrypt\ium\trustlet\bcryptiumkeyattest.cxx`
- `0x140013793`: `CreateVsmKeyAttestationRootClaim`

## pseudocode

```c
__int64 __fastcall CreateVsmKeyAttestationRootClaim(
        __int64 *a1,
        const void *a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        unsigned int *a6)
{
  size_t v7; // r15
  HLOCAL v9; // r13
  __int64 v10; // rax
  unsigned int v11; // esi
  char *v12; // rdi
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // r8
  __int64 v16; // rcx
  void *v17; // rsi
  __int64 v18; // rbx
  int SignedReport; // ecx
  int v20; // eax
  __int64 v21; // r8
  unsigned int v22; // eax
  __int64 v23; // rcx
  unsigned int v24; // ebx
  unsigned int v25; // r14d
  SIZE_T v26; // rdx
  char *v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // r8
  int v31; // eax
  unsigned int v33; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v34; // [rsp+54h] [rbp-2Ch] BYREF
  void *v35; // [rsp+58h] [rbp-28h]
  SIZE_T uBytes; // [rsp+60h] [rbp-20h] BYREF
  SIZE_T Size; // [rsp+68h] [rbp-18h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-10h] BYREF
  void *v39; // [rsp+78h] [rbp-8h]
  char v40; // [rsp+C0h] [rbp+40h]

  v7 = a3;
  uBytes = 0;
  v9 = 0;
  Size = 0;
  v10 = *a1;
  if ( *a1 )
  {
    v11 = *(_DWORD *)v10;
    v39 = *(void **)(v10 + 8);
  }
  else
  {
    v11 = 0;
    v39 = 0;
  }
  if ( !a4 || (v40 = 0, !a5) )
    v40 = 1;
  hMem = 0;
  v12 = 0;
  v34 = 0;
  v33 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_9b7bb3a056503060c4cc3cbe91885dc2_Traceguids,
      "CreateVsmKeyAttestationRootClaim");
  *a6 = 0;
  v13 = BCryptIumBuildRootClaimHashBuffer((__int64)a2, v7, &hMem, &v34, a1);
  v14 = v13;
  if ( v13 >= 0 )
  {
    v18 = v34;
    SignedReport = GetSignedReport(32780, 32780, hMem, v34, 0, &uBytes, 0, &Size, 1);
    if ( (int)(SignedReport + 0x80000000) >= 0 && SignedReport != -805306333 )
    {
      v14 = (unsigned __int16)SignedReport;
      v15 = 1221;
      if ( (_WORD)SignedReport )
        v14 = (unsigned __int16)SignedReport | 0xC0070000;
      v16 = v14;
      goto LABEL_12;
    }
    v35 = LocalAlloc(0, uBytes);
    v9 = LocalAlloc(0, Size);
    if ( !v35 || !v9 )
    {
      v21 = 1231;
      goto LABEL_49;
    }
    v20 = GetSignedReport(32780, 32780, hMem, v18, v35, &uBytes, v9, &Size, 1);
    if ( v20 < 0 )
    {
      v14 = (unsigned __int16)v20;
      v21 = 1248;
      v22 = (unsigned __int16)v20 | 0xC0070000;
      if ( v14 )
        v14 = v22;
      v23 = v14;
      goto LABEL_51;
    }
    v24 = v7 + 36;
    if ( (unsigned int)v7 >= 0xFFFFFFDC )
    {
      v23 = 3221225621LL;
      v21 = 1255;
LABEL_50:
      v14 = v23;
LABEL_51:
      VBS_ATTEST_TRACE_ERROR_IN(
        v23,
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\trustlet\\bcryptiumkeyattest.cxx",
        v21);
      v17 = v35;
      goto LABEL_52;
    }
    v25 = v24 + v11;
    if ( v24 + v11 < v11 )
    {
      v23 = 3221225621LL;
      v21 = 1261;
      goto LABEL_50;
    }
    if ( v25 + (unsigned int)uBytes < (unsigned int)uBytes )
    {
      v23 = 3221225621LL;
      v21 = 1267;
      goto LABEL_50;
    }
    v26 = v25 + (unsigned int)uBytes + (unsigned int)Size;
    if ( (unsigned int)v26 < (unsigned int)Size )
    {
      v23 = 3221225621LL;
      v21 = 1273;
      goto LABEL_50;
    }
    v27 = (char *)LocalAlloc(0, v26);
    v12 = v27;
    if ( !v27 )
    {
      v21 = 1282;
LABEL_49:
      v23 = 3221225495LL;
      goto LABEL_50;
    }
    *(_DWORD *)v27 = 1396788054;
    *((_DWORD *)v27 + 1) = 2;
    *((_DWORD *)v27 + 2) = 5;
    *(_QWORD *)(v27 + 12) = 1212371542;
    *((_DWORD *)v27 + 5) = v7;
    *((_DWORD *)v27 + 6) = v11;
    *((_DWORD *)v27 + 7) = uBytes;
    *((_DWORD *)v27 + 8) = Size;
    memcpy_0(v27 + 36, a2, v7);
    if ( v24 < (unsigned int)v7 )
    {
      v23 = 3221225621LL;
      v21 = 1305;
      goto LABEL_50;
    }
    memcpy_0(&v12[v24], v39, v11);
    v17 = v35;
    memcpy_0(&v12[v25], v35, uBytes);
    v28 = v25 + (unsigned int)uBytes;
    if ( (unsigned int)v28 >= (unsigned int)uBytes )
    {
      memcpy_0(&v12[v28], v9, Size);
      v31 = VBSAttestationSerializeAttestationStatement(v12, 0, &v33);
      v14 = v31;
      if ( v31 >= 0 )
      {
        if ( v40 )
          goto LABEL_47;
        if ( v33 > a5 )
        {
          v14 = -1073741789;
          v30 = 1344;
          v29 = 3221225507LL;
          goto LABEL_38;
        }
        v33 = a5;
        v31 = VBSAttestationSerializeAttestationStatement(v12, a4, &v33);
        v14 = v31;
        if ( v31 >= 0 )
        {
LABEL_47:
          v14 = 0;
          *a6 = v33;
          goto LABEL_52;
        }
        v30 = 1355;
      }
      else
      {
        v30 = 1334;
      }
      v29 = (unsigned int)v31;
    }
    else
    {
      v29 = 3221225621LL;
      v30 = 1321;
      v14 = -1073741675;
    }
LABEL_38:
    VBS_ATTEST_TRACE_ERROR_IN(
      v29,
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\trustlet\\bcryptiumkeyattest.cxx",
      v30);
    goto LABEL_52;
  }
  v15 = 1203;
  v16 = (unsigned int)v13;
LABEL_12:
  VBS_ATTEST_TRACE_ERROR_IN(v16, "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\trustlet\\bcryptiumkeyattest.cxx", v15);
  v17 = 0;
LABEL_52:
  LocalFree(v9);
  LocalFree(v17);
  LocalFree(hMem);
  LocalFree(v12);
  return v14;
}

```

## disassembly

```asm
0x140013700  mov     [rsp-38h+arg_10], rbx
0x140013705  mov     [rsp-38h+arg_18], r9
0x14001370a  mov     [rsp-38h+Src], rdx
0x14001370f  push    rbp
0x140013710  push    rsi
0x140013711  push    rdi
0x140013712  push    r12
0x140013714  push    r13
0x140013716  push    r14
0x140013718  push    r15
0x14001371a  mov     rbp, rsp
0x14001371d  sub     rsp, 80h
0x140013724  mov     rbx, rcx
0x140013727  mov     r15d, r8d
0x14001372a  xor     ecx, ecx
0x14001372c  mov     r14, rdx
0x14001372f  mov     [rbp+uBytes], rcx
0x140013733  mov     r13d, ecx
0x140013736  mov     [rbp+Size], rcx
0x14001373a  mov     rax, [rbx]
0x14001373d  test    rax, rax
0x140013740  jz      short loc_14001374E
0x140013742  mov     esi, [rax]
0x140013744  mov     rax, [rax+8]
0x140013748  mov     [rbp+var_8], rax
0x14001374c  jmp     short loc_140013754
0x14001374e  mov     esi, ecx
0x140013750  mov     [rbp+var_8], rcx
0x140013754  mov     r12d, [rbp+arg_20]
0x140013758  test    r9, r9
0x14001375b  jz      short loc_140013765
0x14001375d  mov     [rbp+arg_0], cl
0x140013760  test    r12d, r12d
0x140013763  jnz     short loc_140013769
0x140013765  mov     [rbp+arg_0], 1
0x140013769  mov     [rbp+hMem], rcx
0x14001376d  mov     rdi, rcx
0x140013770  mov     [rbp+var_2C], ecx
0x140013773  mov     [rbp+var_30], ecx
0x140013776  mov     rcx, cs:WPP_GLOBAL_Control
0x14001377d  lea     rax, WPP_GLOBAL_Control
0x140013784  cmp     rcx, rax
0x140013787  jz      short loc_1400137AB
0x140013789  test    byte ptr [rcx+1Ch], 4
0x14001378d  jz      short loc_1400137AB
0x14001378f  mov     rcx, [rcx+10h]
0x140013793  lea     r9, aCreatevsmkeyat; "CreateVsmKeyAttestationRootClaim"
0x14001379a  mov     edx, 0Ch
0x14001379f  lea     r8, WPP_9b7bb3a056503060c4cc3cbe91885dc2_Traceguids
0x1400137a6  call    WPP_SF_s
0x1400137ab  mov     rax, [rbp+arg_28]
0x1400137af  lea     r9, [rbp+var_2C]
0x1400137b3  lea     r8, [rbp+hMem]
0x1400137b7  mov     [rsp+80h+var_60], rbx
0x1400137bc  mov     edx, r15d
0x1400137bf  mov     rcx, r14
0x1400137c2  mov     [rax], edi
0x1400137c4  call    BCryptIumBuildRootClaimHashBuffer
0x1400137c9  mov     ebx, eax
0x1400137cb  test    eax, eax
0x1400137cd  jns     short loc_1400137EB
0x1400137cf  mov     r8d, 4B3h
0x1400137d5  mov     ecx, eax
0x1400137d7  lea     rdx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1400137de  call    VBS_ATTEST_TRACE_ERROR_IN
0x1400137e3  mov     rsi, rdi
0x1400137e6  jmp     loc_140013AA3
0x1400137eb  mov     ebx, [rbp+var_2C]
0x1400137ee  lea     rax, [rbp+Size]
0x1400137f2  mov     r8, [rbp+hMem]
0x1400137f6  mov     r14d, 1
0x1400137fc  mov     [rsp+80h+var_40], r14d
0x140013801  mov     r9d, ebx
0x140013804  mov     [rsp+80h+var_48], rax
0x140013809  lea     rax, [rbp+uBytes]
0x14001380d  mov     [rsp+80h+var_50], rdi
0x140013812  mov     [rsp+80h+var_58], rax
0x140013817  mov     eax, 800Ch
0x14001381c  mov     edx, eax
0x14001381e  mov     [rsp+80h+var_60], rdi
0x140013823  mov     ecx, eax
0x140013825  call    cs:__imp_GetSignedReport
0x14001382b  mov     edx, 80000000h
0x140013830  mov     ecx, eax
0x140013832  add     eax, edx
0x140013834  test    edx, eax
0x140013836  jnz     short loc_14001385C
0x140013838  cmp     ecx, 0D0000023h
0x14001383e  jz      short loc_14001385C
0x140013840  movzx   ebx, cx
0x140013843  mov     r8d, 4C5h
0x140013849  mov     eax, ebx
0x14001384b  or      eax, 0C0070000h
0x140013850  test    ebx, ebx
0x140013852  cmovnz  ebx, eax
0x140013855  mov     ecx, ebx
0x140013857  jmp     loc_1400137D7
0x14001385c  mov     rdx, [rbp+uBytes]; uBytes
0x140013860  xor     ecx, ecx; uFlags
0x140013862  call    cs:__imp_LocalAlloc
0x140013868  mov     rdx, [rbp+Size]; uBytes
0x14001386c  xor     ecx, ecx; uFlags
0x14001386e  mov     [rbp+var_28], rax
0x140013872  call    cs:__imp_LocalAlloc
0x140013878  mov     r13, rax
0x14001387b  mov     rax, [rbp+var_28]
0x14001387f  test    rax, rax
0x140013882  jz      loc_140013A86
0x140013888  test    r13, r13
0x14001388b  jz      loc_140013A86
0x140013891  mov     r8, [rbp+hMem]
0x140013895  lea     rdx, [rbp+Size]
0x140013899  mov     [rsp+80h+var_40], r14d
0x14001389e  mov     ecx, 800Ch
0x1400138a3  mov     [rsp+80h+var_48], rdx
0x1400138a8  mov     r9, rbx
0x1400138ab  lea     rdx, [rbp+uBytes]
0x1400138af  mov     [rsp+80h+var_50], r13
0x1400138b4  mov     [rsp+80h+var_58], rdx
0x1400138b9  mov     edx, ecx
0x1400138bb  mov     [rsp+80h+var_60], rax
0x1400138c0  call    cs:__imp_GetSignedReport
0x1400138c6  test    eax, eax
0x1400138c8  jns     short loc_1400138E6
0x1400138ca  movzx   ebx, ax
0x1400138cd  mov     r8d, 4E0h
0x1400138d3  mov     eax, ebx
0x1400138d5  or      eax, 0C0070000h
0x1400138da  test    ebx, ebx
0x1400138dc  cmovnz  ebx, eax
0x1400138df  mov     ecx, ebx
0x1400138e1  jmp     loc_140013A93
0x1400138e6  lea     ebx, [r15+24h]
0x1400138ea  cmp     ebx, 24h ; '$'
0x1400138ed  jnb     short loc_1400138FF
0x1400138ef  mov     ecx, 0C0000095h
0x1400138f4  mov     r8d, 4E7h
0x1400138fa  jmp     loc_140013A91
0x1400138ff  lea     r14d, [rbx+rsi]
0x140013903  cmp     r14d, esi
0x140013906  jnb     short loc_140013918
0x140013908  mov     ecx, 0C0000095h
0x14001390d  mov     r8d, 4EDh
0x140013913  jmp     loc_140013A91
0x140013918  mov     rax, [rbp+uBytes]
0x14001391c  lea     ecx, [r14+rax]
0x140013920  cmp     ecx, eax
0x140013922  jnb     short loc_140013934
0x140013924  mov     ecx, 0C0000095h
0x140013929  mov     r8d, 4F3h
0x14001392f  jmp     loc_140013A91
0x140013934  mov     rax, [rbp+Size]
0x140013938  lea     edx, [rcx+rax]; uBytes
0x14001393b  cmp     edx, eax
0x14001393d  jnb     short loc_14001394F
0x14001393f  mov     ecx, 0C0000095h
0x140013944  mov     r8d, 4F9h
0x14001394a  jmp     loc_140013A91
0x14001394f  xor     ecx, ecx; uFlags
0x140013951  call    cs:__imp_LocalAlloc
0x140013957  mov     rdi, rax
0x14001395a  test    rax, rax
0x14001395d  jnz     short loc_14001396A
0x14001395f  mov     r8d, 502h
0x140013965  jmp     loc_140013A8C
0x14001396a  mov     rdx, [rbp+Src]; Src
0x14001396e  lea     rcx, [rdi+24h]; void *
0x140013972  mov     dword ptr [rax], 53414B56h
0x140013978  mov     r8, r15; Size
0x14001397b  mov     dword ptr [rax+4], 2
0x140013982  mov     dword ptr [rax+8], 5
0x140013989  mov     qword ptr [rax+0Ch], 48435256h
0x140013991  mov     [rax+14h], r15d
0x140013995  mov     [rax+18h], esi
0x140013998  mov     eax, dword ptr [rbp+uBytes]
0x14001399b  mov     [rdi+1Ch], eax
0x14001399e  mov     eax, dword ptr [rbp+Size]
0x1400139a1  mov     [rdi+20h], eax
0x1400139a4  call    memcpy_0
0x1400139a9  cmp     ebx, r15d
0x1400139ac  jnb     short loc_1400139BE
0x1400139ae  mov     ecx, 0C0000095h
0x1400139b3  mov     r8d, 519h
0x1400139b9  jmp     loc_140013A91
0x1400139be  mov     rdx, [rbp+var_8]; Src
0x1400139c2  mov     ecx, ebx
0x1400139c4  add     rcx, rdi; void *
0x1400139c7  mov     r8d, esi; Size
0x1400139ca  call    memcpy_0
0x1400139cf  mov     rsi, [rbp+var_28]
0x1400139d3  mov     r8, [rbp+uBytes]; Size
0x1400139d7  mov     rdx, rsi; Src
0x1400139da  mov     ecx, r14d
0x1400139dd  add     rcx, rdi; void *
0x1400139e0  call    memcpy_0
0x1400139e5  mov     rax, [rbp+uBytes]
0x1400139e9  lea     ecx, [r14+rax]
0x1400139ed  cmp     ecx, eax
0x1400139ef  jnb     short loc_140013A0F
0x1400139f1  mov     ecx, 0C0000095h
0x1400139f6  mov     r8d, 529h
0x1400139fc  mov     ebx, ecx
0x1400139fe  lea     rdx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x140013a05  call    VBS_ATTEST_TRACE_ERROR_IN
0x140013a0a  jmp     loc_140013AA3
0x140013a0f  mov     r8, [rbp+Size]; Size
0x140013a13  add     rcx, rdi; void *
0x140013a16  mov     rdx, r13; Src
0x140013a19  call    memcpy_0
0x140013a1e  lea     r8, [rbp+var_30]
0x140013a22  xor     edx, edx
0x140013a24  mov     rcx, rdi
0x140013a27  call    VBSAttestationSerializeAttestationStatement
0x140013a2c  mov     ebx, eax
0x140013a2e  test    eax, eax
0x140013a30  jns     short loc_140013A3C
0x140013a32  mov     r8d, 536h
0x140013a38  mov     ecx, eax
0x140013a3a  jmp     short loc_1400139FE
0x140013a3c  cmp     [rbp+arg_0], 0
0x140013a40  jnz     short loc_140013A79
0x140013a42  cmp     [rbp+var_30], r12d
0x140013a46  jbe     short loc_140013A57
0x140013a48  mov     ebx, 0C0000023h
0x140013a4d  mov     r8d, 540h
0x140013a53  mov     ecx, ebx
0x140013a55  jmp     short loc_1400139FE
0x140013a57  mov     rdx, [rbp+arg_18]
0x140013a5b  lea     r8, [rbp+var_30]
0x140013a5f  mov     rcx, rdi
0x140013a62  mov     [rbp+var_30], r12d
0x140013a66  call    VBSAttestationSerializeAttestationStatement
0x140013a6b  mov     ebx, eax
0x140013a6d  test    eax, eax
0x140013a6f  jns     short loc_140013A79
0x140013a71  mov     r8d, 54Bh
0x140013a77  jmp     short loc_140013A38
0x140013a79  mov     rcx, [rbp+arg_28]
0x140013a7d  xor     ebx, ebx
0x140013a7f  mov     eax, [rbp+var_30]
0x140013a82  mov     [rcx], eax
0x140013a84  jmp     short loc_140013AA3
0x140013a86  mov     r8d, 4CFh
0x140013a8c  mov     ecx, 0C0000017h
0x140013a91  mov     ebx, ecx
0x140013a93  lea     rdx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x140013a9a  call    VBS_ATTEST_TRACE_ERROR_IN
0x140013a9f  mov     rsi, [rbp+var_28]
0x140013aa3  mov     rcx, r13; hMem
0x140013aa6  call    cs:__imp_LocalFree
0x140013aac  mov     rcx, rsi; hMem
0x140013aaf  call    cs:__imp_LocalFree
0x140013ab5  mov     rcx, [rbp+hMem]; hMem
0x140013ab9  call    cs:__imp_LocalFree
0x140013abf  mov     rcx, rdi; hMem
0x140013ac2  call    cs:__imp_LocalFree
0x140013ac8  mov     eax, ebx
0x140013aca  mov     rbx, [rsp+80h+arg_10]
0x140013ad2  add     rsp, 80h
0x140013ad9  pop     r15
0x140013adb  pop     r14
0x140013add  pop     r13
0x140013adf  pop     r12
0x140013ae1  pop     rdi
0x140013ae2  pop     rsi
0x140013ae3  pop     rbp
0x140013ae4  retn
```
