# MSCryptExportKeyPair

- ea: `0x18003c600`
- end: `0x18003cb0e`
- name: `MSCryptExportKeyPair`
- size: `1294`
- prototype: `__int64 __fastcall(__int64, __int64, const wchar_t *, __int64, unsigned int, unsigned int *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18004a060`
- `0x18006c820`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x18003c600`
- `0x18003cfd4`
- `0x18003d574`
- `0x18003d5b0`
- `0x18003d678`
- `0x180056cf0`
- `0x1800755a4`
- `0x18007f765`

## string_xrefs

- `0x18003c93f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18003c9b6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18003c9f2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18003ca39`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180081f56`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptExportKeyPair(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        __int64 a4,
        unsigned int a5,
        unsigned int *a6,
        int a7)
{
  __int64 v9; // rax
  int v10; // edx
  __int64 v11; // r8
  __int64 v12; // r14
  __int64 v13; // rsi
  unsigned int v14; // edi
  unsigned int v15; // r15d
  int v16; // r13d
  int v17; // edx
  int v18; // r8d
  unsigned int v19; // ecx
  int v20; // esi
  __int64 v21; // r12
  __int64 v22; // r10
  __int64 v23; // rdi
  unsigned int v24; // r11d
  unsigned int Value; // eax
  int v26; // edx
  unsigned int v27; // ebx
  int v28; // r8d
  _QWORD *v29; // rcx
  __int64 v30; // r8
  __int64 v31; // rcx
  unsigned int v32; // edx
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r15
  __int64 i; // rdi
  __int64 v41; // r8
  unsigned int Uint64; // eax
  __int64 v44; // r9
  __int64 v45; // rax
  __int64 v46; // rcx
  unsigned int CrtValue; // eax
  __int64 v48; // rcx
  char v49; // [rsp+30h] [rbp-91h]
  __int64 v50; // [rsp+50h] [rbp-71h]
  __int64 v51; // [rsp+58h] [rbp-69h]
  __int64 v52; // [rsp+60h] [rbp-61h]
  __int64 v53; // [rsp+68h] [rbp-59h]
  __int64 v54; // [rsp+70h] [rbp-51h]
  __int128 v55; // [rsp+78h] [rbp-49h]
  __int128 v56; // [rsp+88h] [rbp-39h]
  __int128 v57; // [rsp+98h] [rbp-29h] BYREF
  __int128 v58; // [rsp+A8h] [rbp-19h] BYREF

  v55 = 0;
  v56 = 0;
  v58 = 0;
  v57 = 0;
  if ( a7 )
  {
    v27 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        0,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        140);
    return v27;
  }
  if ( a2 )
  {
    v44 = 1171;
LABEL_64:
    v27 = -1073741637;
    v48 = 3221225659LL;
    goto LABEL_65;
  }
  v9 = validateMSCryptRsaKey();
  v12 = v9;
  if ( !v9 || *(_DWORD *)(v9 + 16) == (_DWORD)v11 || (v13 = *(_QWORD *)(v9 + 32)) == 0 )
  {
    v27 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        v11,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        157);
    return v27;
  }
  v53 = v11;
  v52 = v11;
  v51 = v11;
  v50 = v11;
  if ( HIDWORD(*(_QWORD *)(v13 + 56)) )
    v14 = ((__int64 (*)(void))SymCryptUint32Bytesize)() + 4;
  else
    v14 = SymCryptUint32Bytesize(*(unsigned int *)(v13 + 56));
  v15 = (unsigned int)(*(_DWORD *)(v13 + 16) + 7) >> 3;
  v16 = wcscmp_0(a3, L"RSAFULLPRIVATEBLOB");
  if ( !wcscmp_0(a3, L"RSAPUBLICBLOB") || !wcscmp_0(a3, L"PUBLICBLOB") )
  {
    v19 = v14 + v15 + 24;
    *a6 = v19;
    if ( !a4 )
      return 0;
    if ( a5 < v19 )
    {
      v27 = -1073741789;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v17,
          v18,
          (unsigned int)"Status",
          35,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
          186);
      return v27;
    }
    v20 = 0;
    *(_DWORD *)a4 = 826364754;
    v21 = v14;
    *(_DWORD *)(a4 + 4) = *(_DWORD *)(v12 + 12);
    v22 = v14 + a4 + 24;
    *(_DWORD *)(a4 + 8) = v14;
    *(_DWORD *)(a4 + 12) = v15;
    *(_QWORD *)(a4 + 16) = 0;
    v23 = *(_QWORD *)(v12 + 32);
    v24 = v15;
  }
  else
  {
    if ( wcscmp_0(a3, L"RSAPRIVATEBLOB") && wcscmp_0(a3, L"PRIVATEBLOB") && v16 )
    {
      v44 = 1331;
      goto LABEL_64;
    }
    if ( !*(_BYTE *)(v13 + 8) )
      return (unsigned int)-1073741811;
    v30 = (unsigned int)(*(_DWORD *)(v13 + 36) + 7) >> 3;
    v31 = (unsigned int)(*(_DWORD *)(v13 + 32) + 7) >> 3;
    v32 = v15 + v31 + v14 + v30 + 24;
    *a6 = v32;
    if ( !v16 )
    {
      v32 = v31 + v14 + 2 * (v15 + v30 + v31 + 12);
      *a6 = v32;
    }
    if ( !a4 )
      return 0;
    if ( a5 < v32 )
      return (unsigned int)-1073741789;
    *(_DWORD *)a4 = 843141970;
    if ( !v16 )
      *(_DWORD *)a4 = 859919186;
    v33 = (unsigned int)v31;
    v21 = v14;
    v22 = v14 + a4 + 24;
    *(_DWORD *)(a4 + 4) = *(_DWORD *)(v12 + 12);
    *(_DWORD *)(a4 + 16) = v31;
    *(_DWORD *)(a4 + 8) = v14;
    *(_DWORD *)(a4 + 12) = v15;
    v34 = v15 + v22 + v31;
    *(_DWORD *)(a4 + 20) = v30;
    v24 = v15;
    *(_QWORD *)&v55 = v15 + v22;
    *(_QWORD *)&v56 = v33;
    *((_QWORD *)&v55 + 1) = v34;
    *((_QWORD *)&v56 + 1) = (unsigned int)v30;
    if ( v16 )
    {
      v35 = v53;
      v36 = v53;
      v37 = v53;
      v38 = v53;
    }
    else
    {
      v45 = v30 + v34;
      *(_QWORD *)&v57 = v33;
      v46 = v30 + v34 + v33;
      *(_QWORD *)&v58 = v45;
      v35 = v30 + v46;
      *((_QWORD *)&v58 + 1) = v46;
      v36 = v33;
      *((_QWORD *)&v57 + 1) = (unsigned int)v30;
      v37 = v35 + v33;
      v38 = v15;
    }
    v23 = *(_QWORD *)(v12 + 32);
    v50 = v38;
    v51 = v37;
    v52 = v36;
    v53 = v35;
    if ( !*(_BYTE *)(v23 + 8) )
    {
      Value = 32782;
      goto LABEL_14;
    }
    v20 = 2;
  }
  v54 = v23;
  if ( v22 )
  {
    Value = SymCryptFdefRawGetValue(
              (unsigned int)*(_QWORD *)(v23 + 120) + 128,
              *(_DWORD *)(*(_QWORD *)(v23 + 120) + 100LL),
              v22,
              v24,
              2);
    if ( Value )
    {
LABEL_14:
      v27 = SymcryptErrorCodeToNtStatus(Value);
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v49 = 69;
LABEL_41:
        WPP_SF_sDsd(
          v29[2],
          v26,
          v28,
          (unsigned int)"Status",
          v27,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
          v49);
        return v27;
      }
      return v27;
    }
  }
  v39 = *(_QWORD *)(v23 + 56);
  if ( v20 )
  {
    for ( i = 0; (unsigned int)i < 2; i = (unsigned int)(i + 1) )
    {
      v41 = *((_QWORD *)&v55 + i);
      if ( v41 )
      {
        Value = SymCryptFdefRawGetValue(
                  (unsigned int)*(_QWORD *)(v54 + 8 * i + 128) + 128,
                  *(_DWORD *)(*(_QWORD *)(v54 + 8 * i + 128) + 100LL),
                  v41,
                  *((_QWORD *)&v56 + i),
                  2);
        if ( Value )
          goto LABEL_14;
      }
    }
  }
  Uint64 = SymCryptStoreMsbFirstUint64(v39, a4 + 24, v21);
  if ( !Uint64 )
  {
    if ( !v16 )
    {
      CrtValue = SymCryptRsakeyGetCrtValue(
                   *(_QWORD *)(v12 + 32),
                   (unsigned int)&v58,
                   (unsigned int)&v57,
                   v20,
                   v53,
                   v52,
                   v51,
                   v50);
      if ( CrtValue )
      {
        v27 = SymcryptErrorCodeToNtStatus(CrtValue);
        v48 = v27;
        v44 = 1377;
LABEL_65:
        DebugTraceError(v48, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", v44);
        return v27;
      }
    }
    return 0;
  }
  v27 = SymcryptErrorCodeToNtStatus(Uint64);
  v29 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v49 = 77;
    goto LABEL_41;
  }
  return v27;
}

```

## disassembly

```asm
0x18003c600  push    rbp
0x18003c602  push    rbx
0x18003c603  push    rsi
0x18003c604  push    rdi
0x18003c605  push    r12
0x18003c607  push    r13
0x18003c609  push    r14
0x18003c60b  push    r15
0x18003c60d  lea     rbp, [rsp-7]
0x18003c612  sub     rsp, 0C8h
0x18003c619  xorps   xmm0, xmm0
0x18003c61c  xorps   xmm1, xmm1
0x18003c61f  mov     r12, r8
0x18003c622  mov     rbx, r9
0x18003c625  xor     r8d, r8d
0x18003c628  movups  [rbp+3Fh+var_88], xmm0
0x18003c62c  movups  [rbp+3Fh+var_78], xmm1
0x18003c630  movups  [rbp+3Fh+var_58], xmm0
0x18003c634  movups  [rbp+3Fh+var_68], xmm1
0x18003c638  cmp     [rbp+3Fh+arg_30], r8d
0x18003c63c  jnz     loc_18003C990
0x18003c642  test    rdx, rdx
0x18003c645  jnz     loc_18003CA5C
0x18003c64b  call    validateMSCryptRsaKey
0x18003c650  mov     r14, rax
0x18003c653  test    rax, rax
0x18003c656  jz      loc_18003C9CC
0x18003c65c  cmp     [rax+10h], r8d
0x18003c660  jz      loc_18003C9CC
0x18003c666  mov     rsi, [rax+20h]
0x18003c66a  test    rsi, rsi
0x18003c66d  jz      loc_18003C9CC
0x18003c673  mov     rcx, [rsi+38h]
0x18003c677  shr     rcx, 20h
0x18003c67b  mov     [rbp+3Fh+var_98], r8
0x18003c67f  mov     [rbp+3Fh+var_A0], r8
0x18003c683  mov     [rbp+3Fh+var_A8], r8
0x18003c687  mov     [rbp+3Fh+var_B0], r8
0x18003c68b  test    ecx, ecx
0x18003c68d  jnz     loc_18003C983
0x18003c693  mov     ecx, [rsi+38h]
0x18003c696  call    SymCryptUint32Bytesize
0x18003c69b  mov     edi, eax
0x18003c69d  mov     r15d, [rsi+10h]
0x18003c6a1  lea     rdx, aRsafullprivate; "RSAFULLPRIVATEBLOB"
0x18003c6a8  add     r15d, 7
0x18003c6ac  mov     rcx, r12; String1
0x18003c6af  shr     r15d, 3
0x18003c6b3  call    wcscmp_0
0x18003c6b8  lea     rdx, aRsapublicblob; "RSAPUBLICBLOB"
0x18003c6bf  mov     rcx, r12; String1
0x18003c6c2  mov     r13d, eax
0x18003c6c5  call    wcscmp_0
0x18003c6ca  test    eax, eax
0x18003c6cc  jnz     loc_18003C78A
0x18003c6d2  mov     rax, [rbp+3Fh+arg_28]
0x18003c6d6  lea     ecx, [r15+18h]
0x18003c6da  add     ecx, edi
0x18003c6dc  mov     [rax], ecx
0x18003c6de  test    rbx, rbx
0x18003c6e1  jz      loc_18003C96A
0x18003c6e7  cmp     [rbp+3Fh+arg_20], ecx
0x18003c6ea  jb      loc_18003CA0B
0x18003c6f0  xor     esi, esi
0x18003c6f2  mov     dword ptr [rbx], 31415352h
0x18003c6f8  mov     eax, [r14+0Ch]
0x18003c6fc  lea     r10, [rbx+18h]
0x18003c700  mov     r12d, edi
0x18003c703  mov     [rbx+4], eax
0x18003c706  add     r10, r12
0x18003c709  mov     [rbx+8], edi
0x18003c70c  mov     [rbx+0Ch], r15d
0x18003c710  mov     [rbx+10h], rsi
0x18003c714  mov     rdi, [r14+20h]
0x18003c718  mov     r11d, r15d
0x18003c71b  xor     eax, eax
0x18003c71d  mov     [rbp+3Fh+var_90], rdi
0x18003c721  test    r10, r10
0x18003c724  jz      loc_18003C8A4
0x18003c72a  mov     rdx, [rdi+78h]
0x18003c72e  mov     r9, r11
0x18003c731  mov     r8, r10
0x18003c734  mov     dword ptr [rsp+100h+var_E0], 2
0x18003c73c  lea     rcx, [rdx+80h]
0x18003c743  mov     edx, [rdx+64h]
0x18003c746  call    SymCryptFdefRawGetValue
0x18003c74b  test    eax, eax
0x18003c74d  jz      loc_18003C8A4
0x18003c753  mov     ecx, eax
0x18003c755  call    SymcryptErrorCodeToNtStatus
0x18003c75a  mov     ebx, eax
0x18003c75c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c763  lea     rax, WPP_GLOBAL_Control
0x18003c76a  cmp     rcx, rax
0x18003c76d  jz      loc_18003C96C
0x18003c773  test    byte ptr [rcx+1Ch], 1
0x18003c777  jz      loc_18003C96C
0x18003c77d  mov     dword ptr [rsp+100h+var_D0], 545h
0x18003c785  jmp     loc_18003C93F
0x18003c78a  lea     rdx, aPublicblob; "PUBLICBLOB"
0x18003c791  mov     rcx, r12; String1
0x18003c794  call    wcscmp_0
0x18003c799  test    eax, eax
0x18003c79b  jz      loc_18003C6D2
0x18003c7a1  lea     rdx, aRsaprivateblob; "RSAPRIVATEBLOB"
0x18003c7a8  mov     rcx, r12; String1
0x18003c7ab  call    wcscmp_0
0x18003c7b0  test    eax, eax
0x18003c7b2  jz      short loc_18003C7CB
0x18003c7b4  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x18003c7bb  mov     rcx, r12; String1
0x18003c7be  call    wcscmp_0
0x18003c7c3  test    eax, eax
0x18003c7c5  jnz     loc_18003CA67
0x18003c7cb  cmp     byte ptr [rsi+8], 0
0x18003c7cf  jz      loc_18003CA52
0x18003c7d5  mov     r8d, [rsi+24h]
0x18003c7d9  mov     ecx, [rsi+20h]
0x18003c7dc  add     r8d, 7
0x18003c7e0  mov     r9, [rbp+3Fh+arg_28]
0x18003c7e4  add     ecx, 7
0x18003c7e7  shr     r8d, 3
0x18003c7eb  shr     ecx, 3
0x18003c7ee  lea     edx, [r8+18h]
0x18003c7f2  add     edx, edi
0x18003c7f4  add     edx, ecx
0x18003c7f6  add     edx, r15d
0x18003c7f9  mov     [r9], edx
0x18003c7fc  test    r13d, r13d
0x18003c7ff  jz      loc_18003CA75
0x18003c805  test    rbx, rbx
0x18003c808  jz      loc_18003C96A
0x18003c80e  cmp     [rbp+3Fh+arg_20], edx
0x18003c811  jb      loc_18003CA8B
0x18003c817  mov     dword ptr [rbx], 32415352h
0x18003c81d  test    r13d, r13d
0x18003c820  jnz     short loc_18003C828
0x18003c822  mov     dword ptr [rbx], 33415352h
0x18003c828  mov     eax, [r14+0Ch]
0x18003c82c  lea     r10, [rbx+18h]
0x18003c830  mov     edx, ecx
0x18003c832  mov     r12d, edi
0x18003c835  add     r10, r12
0x18003c838  mov     [rbx+4], eax
0x18003c83b  mov     [rbx+10h], ecx
0x18003c83e  mov     r9d, r8d
0x18003c841  mov     [rbx+8], edi
0x18003c844  lea     rax, [r15+r10]
0x18003c848  mov     [rbx+0Ch], r15d
0x18003c84c  add     rcx, rax
0x18003c84f  mov     [rbx+14h], r8d
0x18003c853  mov     r11d, r15d
0x18003c856  mov     qword ptr [rbp+3Fh+var_88], rax
0x18003c85a  mov     qword ptr [rbp+3Fh+var_78], rdx
0x18003c85e  mov     qword ptr [rbp+3Fh+var_88+8], rcx
0x18003c862  mov     qword ptr [rbp+3Fh+var_78+8], r9
0x18003c866  test    r13d, r13d
0x18003c869  jz      loc_18003CA95
0x18003c86f  mov     rax, [rbp+3Fh+var_98]
0x18003c873  mov     rcx, rax
0x18003c876  mov     rdx, rax
0x18003c879  mov     r8, rax
0x18003c87c  mov     rdi, [r14+20h]
0x18003c880  mov     [rbp+3Fh+var_B0], r8
0x18003c884  mov     [rbp+3Fh+var_A8], rdx
0x18003c888  mov     [rbp+3Fh+var_A0], rcx
0x18003c88c  cmp     byte ptr [rdi+8], 0
0x18003c890  mov     [rbp+3Fh+var_98], rax
0x18003c894  jz      loc_18003CABF
0x18003c89a  mov     esi, 2
0x18003c89f  jmp     loc_18003C71B
0x18003c8a4  mov     r15, [rdi+38h]
0x18003c8a8  test    esi, esi
0x18003c8aa  jz      short loc_18003C902
0x18003c8ac  cmp     esi, 2
0x18003c8af  jnz     loc_18003CABF
0x18003c8b5  xor     edi, edi
0x18003c8b7  cmp     edi, 2
0x18003c8ba  jnb     short loc_18003C8FA
0x18003c8bc  mov     r8, qword ptr [rbp+rdi*8+3Fh+var_88]
0x18003c8c1  test    r8, r8
0x18003c8c4  jz      short loc_18003C8F6
0x18003c8c6  mov     rax, [rbp+3Fh+var_90]
0x18003c8ca  mov     r9, qword ptr [rbp+rdi*8+3Fh+var_78]
0x18003c8cf  mov     dword ptr [rsp+100h+var_E0], 2
0x18003c8d7  mov     rdx, [rax+rdi*8+80h]
0x18003c8df  lea     rcx, [rdx+80h]
0x18003c8e6  mov     edx, [rdx+64h]
0x18003c8e9  call    SymCryptFdefRawGetValue
0x18003c8ee  test    eax, eax
0x18003c8f0  jnz     loc_18003C753
0x18003c8f6  inc     edi
0x18003c8f8  jmp     short loc_18003C8B7
0x18003c8fa  test    eax, eax
0x18003c8fc  jnz     loc_18003C753
0x18003c902  lea     rdx, [rbx+18h]
0x18003c906  mov     r8, r12
0x18003c909  mov     rcx, r15
0x18003c90c  call    SymCryptStoreMsbFirstUint64
0x18003c911  test    eax, eax
0x18003c913  jz      short loc_18003C961
0x18003c915  mov     ecx, eax
0x18003c917  call    SymcryptErrorCodeToNtStatus
0x18003c91c  mov     ebx, eax
0x18003c91e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c925  lea     rax, WPP_GLOBAL_Control
0x18003c92c  cmp     rcx, rax
0x18003c92f  jz      short loc_18003C96C
0x18003c931  test    byte ptr [rcx+1Ch], 1
0x18003c935  jz      short loc_18003C96C
0x18003c937  mov     dword ptr [rsp+100h+var_D0], 54Dh
0x18003c93f  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003c946  mov     [rsp+100h+var_D8], rax
0x18003c94b  mov     dword ptr [rsp+100h+var_E0], ebx
0x18003c94f  mov     rcx, [rcx+10h]
0x18003c953  lea     r9, aStatus; "Status"
0x18003c95a  call    WPP_SF_sDsd
0x18003c95f  jmp     short loc_18003C96C
0x18003c961  test    r13d, r13d
0x18003c964  jz      loc_18003CAC9
0x18003c96a  xor     ebx, ebx
0x18003c96c  mov     eax, ebx
0x18003c96e  add     rsp, 0C8h
0x18003c975  pop     r15
0x18003c977  pop     r14
0x18003c979  pop     r13
0x18003c97b  pop     r12
0x18003c97d  pop     rdi
0x18003c97e  pop     rsi
0x18003c97f  pop     rbx
0x18003c980  pop     rbp
0x18003c981  retn
0x18003c983  call    SymCryptUint32Bytesize
0x18003c988  lea     edi, [rax+4]
0x18003c98b  jmp     loc_18003C69D
0x18003c990  mov     ebx, 0C000000Dh
0x18003c995  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c99c  lea     rax, WPP_GLOBAL_Control
0x18003c9a3  cmp     rcx, rax
0x18003c9a6  jz      short loc_18003C96C
0x18003c9a8  test    byte ptr [rcx+1Ch], 1
0x18003c9ac  jz      short loc_18003C96C
0x18003c9ae  mov     dword ptr [rsp+100h+var_D0], 48Ch
0x18003c9b6  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003c9bd  mov     [rsp+100h+var_D8], rax
0x18003c9c2  mov     dword ptr [rsp+100h+var_E0], 0C000000Dh
0x18003c9ca  jmp     short loc_18003C94F
0x18003c9cc  mov     ebx, 0C0000008h
0x18003c9d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c9d8  lea     rax, WPP_GLOBAL_Control
0x18003c9df  cmp     rcx, rax
0x18003c9e2  jz      short loc_18003C96C
0x18003c9e4  test    byte ptr [rcx+1Ch], 1
0x18003c9e8  jz      short loc_18003C96C
0x18003c9ea  mov     dword ptr [rsp+100h+var_D0], 49Dh
0x18003c9f2  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003c9f9  mov     [rsp+100h+var_D8], rax
0x18003c9fe  mov     dword ptr [rsp+100h+var_E0], 0C0000008h
0x18003ca06  jmp     loc_18003C94F
0x18003ca0b  mov     ebx, 0C0000023h
0x18003ca10  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ca17  lea     rax, WPP_GLOBAL_Control
0x18003ca1e  cmp     rcx, rax
0x18003ca21  jz      loc_18003C96C
0x18003ca27  test    byte ptr [rcx+1Ch], 1
0x18003ca2b  jz      loc_18003C96C
0x18003ca31  mov     dword ptr [rsp+100h+var_D0], 4BAh
0x18003ca39  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003ca40  mov     [rsp+100h+var_D8], rax
0x18003ca45  mov     dword ptr [rsp+100h+var_E0], 0C0000023h
0x18003ca4d  jmp     loc_18003C94F
0x18003ca52  mov     ebx, 0C000000Dh
0x18003ca57  jmp     loc_18003C96C
0x18003ca5c  mov     r9d, 493h
0x18003ca62  jmp     loc_180081F32
0x18003ca67  test    r13d, r13d
0x18003ca6a  jz      loc_18003C7CB
0x18003ca70  jmp     loc_180081F2C
0x18003ca75  lea     edx, [rcx+0Ch]
0x18003ca78  add     edx, r8d
0x18003ca7b  add     edx, r15d
0x18003ca7e  lea     edx, [rdi+rdx*2]
0x18003ca81  add     edx, ecx
0x18003ca83  mov     [r9], edx
0x18003ca86  jmp     loc_18003C805
0x18003ca8b  mov     ebx, 0C0000023h
0x18003ca90  jmp     loc_18003C96C
0x18003ca95  lea     rax, [r8+rcx]
0x18003ca99  mov     qword ptr [rbp+3Fh+var_68], rdx
0x18003ca9d  lea     rcx, [rax+rdx]
0x18003caa1  mov     qword ptr [rbp+3Fh+var_58], rax
0x18003caa5  lea     rax, [r8+rcx]
0x18003caa9  mov     qword ptr [rbp+3Fh+var_58+8], rcx
0x18003caad  mov     rcx, rdx
0x18003cab0  mov     qword ptr [rbp+3Fh+var_68+8], r9
0x18003cab4  add     rdx, rax
0x18003cab7  mov     r8, r11
0x18003caba  jmp     loc_18003C87C
0x18003cabf  mov     eax, 800Eh
0x18003cac4  jmp     loc_18003C753
  ... truncated ...
```
