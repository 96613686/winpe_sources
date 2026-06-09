# MSCryptRsaImportKeyPair

- ea: `0x18004a3b0`
- end: `0x18004accd`
- name: `MSCryptRsaImportKeyPair`
- size: `2333`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, const wchar_t *, _QWORD *, _DWORD *, unsigned int, unsigned int, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004a060`
- `0x18004a370`
- `0x18006cb20`

## callees

- `0x18000ee60`
- `0x1800102a0`
- `0x18001c420`
- `0x180043050`
- `0x180049500`
- `0x18004a3b0`
- `0x180051a44`
- `0x180056cf0`
- `0x1800593e0`
- `0x180067358`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18004ab1d`
- `ntdll!RtlFreeHeap` at `0x18004ab43`
- `ntdll!RtlFreeHeap` at `0x18004ac1f`
- `ntdll!RtlFreeHeap` at `0x18004ab1d`
- `ntdll!RtlFreeHeap` at `0x18004ab43`
- `ntdll!RtlFreeHeap` at `0x18004ac1f`

## string_xrefs

- `0x18004a4dc`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18004a5ce`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18004a631`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18004a7fc`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18004aaca`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18004abbe`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18004ac56`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18004ac92`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptRsaImportKeyPair(
        __int64 a1,
        const wchar_t *a2,
        const wchar_t *a3,
        _QWORD *a4,
        _DWORD *a5,
        unsigned int a6,
        unsigned int a7,
        int a8)
{
  const wchar_t *v8; // rdi
  unsigned int SymcryptRsakey; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rax
  int v15; // edx
  int v16; // r8d
  _DWORD *v17; // r12
  int v18; // edx
  int v19; // r8d
  unsigned int v20; // r10d
  _DWORD *v21; // rdi
  const wchar_t *v22; // rdx
  __int64 i; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rcx
  int v28; // ebp
  _QWORD *v29; // rcx
  __int64 v30; // r9
  __int64 v31; // rax
  __int64 v32; // rcx
  unsigned int v33; // ecx
  __int64 v34; // r14
  unsigned int v35; // r15d
  int v36; // eax
  int v37; // edx
  int v38; // r8d
  _QWORD *v39; // rsi
  int v40; // edx
  int v41; // r8d
  __int64 v42; // r9
  _BYTE *v43; // rdx
  unsigned __int64 v44; // rcx
  __int64 j; // r8
  __int64 v46; // rax
  int v47; // eax
  int v48; // r9d
  int v49; // r10d
  int v50; // edx
  int v51; // r8d
  int v52; // r8d
  unsigned int v53; // eax
  int v54; // edx
  int v55; // r8d
  __int64 v56; // rdi
  void *v57; // rdi
  __int64 v58; // rcx
  _BYTE *v59; // rax
  char v61; // [rsp+30h] [rbp-B8h]
  char v62; // [rsp+30h] [rbp-B8h]
  unsigned int v63; // [rsp+60h] [rbp-88h] BYREF
  PVOID P; // [rsp+68h] [rbp-80h] BYREF
  __int64 v65; // [rsp+70h] [rbp-78h] BYREF
  __int128 v66; // [rsp+78h] [rbp-70h] BYREF
  __int128 v67; // [rsp+88h] [rbp-60h] BYREF

  v8 = a2;
  v65 = 0;
  P = 0;
  v67 = 0;
  v63 = 0;
  v66 = 0;
  *a4 = 0;
  if ( (a7 & 0xFFFFFFF7) != 0 )
  {
    SymcryptRsakey = -1073741811;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return SymcryptRsakey;
    v61 = -109;
    goto LABEL_136;
  }
  if ( ((a8 - 1) & 0xFFFFFFFC) != 0 || a8 == 3 )
  {
    SymcryptRsakey = -1073741811;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return SymcryptRsakey;
    v61 = -100;
LABEL_136:
    WPP_SF_sDsd(
      v11[2],
      (_DWORD)a2,
      (_DWORD)a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
      v61);
    return SymcryptRsakey;
  }
  if ( !a1 || *(_DWORD *)(a1 + 4) != 1297306177 )
  {
    SymcryptRsakey = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        164);
    return SymcryptRsakey;
  }
  v12 = -1;
  if ( a3 )
  {
    a2 = L"PKCS11RsaAesWrapBlob";
    v13 = -1;
    while ( 1 )
    {
      if ( a3[v13 + 1] != aPkcs11rsaaeswr[v13 + 1] )
        goto LABEL_14;
      v13 += 2;
      if ( v13 == 21 )
        break;
      if ( a3[v13] != aPkcs11rsaaeswr[v13] )
        goto LABEL_14;
    }
    if ( !v8 )
    {
      SymcryptRsakey = -1073741811;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return SymcryptRsakey;
      v61 = -82;
      goto LABEL_136;
    }
    if ( (int)Pkcs11ConvertToKeyBlob(a1, (_DWORD)v8, 0, (unsigned int)&v63, (__int64)a5, a6) < 0 )
    {
      SymcryptRsakey = -1073741811;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return SymcryptRsakey;
      v61 = -69;
      goto LABEL_136;
    }
    v14 = SafeAllocaAllocateFromHeap(v63);
    v17 = (_DWORD *)v14;
    if ( !v14 )
    {
      SymcryptRsakey = -1073741801;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v15,
          v16,
          (unsigned int)"Status",
          23,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
          194);
      return SymcryptRsakey;
    }
    if ( (int)Pkcs11ConvertToKeyBlob(a1, (_DWORD)v8, v14, (unsigned int)&v63, (__int64)a5, a6) < 0 )
    {
      SymcryptRsakey = -1073741811;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v18,
          v19,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
          207);
      goto LABEL_127;
    }
    v20 = v63;
    v21 = v17;
    a3 = L"RSAPRIVATEBLOB";
  }
  else
  {
LABEL_14:
    if ( v8 )
    {
      SymcryptRsakey = -1073741637;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)a2,
          (_DWORD)a3,
          (unsigned int)"Status",
          187,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
          217);
      return SymcryptRsakey;
    }
    v20 = a6;
    v17 = 0;
    v21 = a5;
  }
  v22 = L"RSAPUBLICBLOB";
  for ( i = 0; i != 14; i += 2 )
  {
    if ( a3[i] != aRsapublicblob[i] || a3[i + 1] != aRsapublicblob[i + 1] )
    {
      v22 = L"PUBLICBLOB";
      v24 = -1;
      do
      {
        if ( a3[v24 + 1] != aPublicblob[v24 + 1] )
          goto LABEL_46;
        v24 += 2;
        if ( v24 == 11 )
          goto LABEL_40;
      }
      while ( a3[v24] == aPublicblob[v24] );
      while ( 1 )
      {
LABEL_46:
        if ( a3[v12 + 1] != aRsaprivateblob[v12 + 1] )
        {
LABEL_49:
          v22 = L"PRIVATEBLOB";
          v25 = 0;
          while ( a3[v25] == aPrivateblob[v25] && a3[v25 + 1] == aPrivateblob[v25 + 1] )
          {
            v25 += 2;
            if ( v25 == 12 )
              goto LABEL_53;
          }
          SymcryptRsakey = -1073741637;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (unsigned int)L"PRIVATEBLOB",
              (_DWORD)a3,
              (unsigned int)"Status",
              187,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
              249);
          goto LABEL_126;
        }
        v12 += 2;
        if ( v12 == 15 )
          break;
        if ( a3[v12] != aRsaprivateblob[v12] )
          goto LABEL_49;
      }
LABEL_53:
      if ( v20 < 0x18 )
        goto LABEL_54;
      if ( *v21 != 843141970 )
      {
        SymcryptRsakey = -2146893819;
        goto LABEL_120;
      }
      LODWORD(a3) = v21[1];
      if ( (unsigned int)((_DWORD)a3 - 256) > 0x3F00 )
      {
        SymcryptRsakey = -2146893783;
        goto LABEL_120;
      }
      v22 = (const wchar_t *)(unsigned int)v21[2];
      if ( (unsigned int)v22 > 0x7FFFFFFF
        || (v30 = (unsigned int)v21[3], (unsigned int)v30 > 0x7FFFFFFF)
        || (v31 = (unsigned int)v21[4], (unsigned int)v31 > 0x7FFFFFFF)
        || (v32 = (unsigned int)v21[5], (unsigned int)v32 > 0x7FFFFFFF) )
      {
LABEL_54:
        SymcryptRsakey = -2146893819;
      }
      else
      {
        if ( v20 >= (unsigned __int64)v22 + v30 + v31 + v32 + 24 )
        {
          v28 = 1;
          goto LABEL_80;
        }
        SymcryptRsakey = -2146893819;
      }
LABEL_120:
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v62 = -14;
        goto LABEL_69;
      }
      goto LABEL_126;
    }
  }
LABEL_40:
  if ( v20 < 0x18 )
    goto LABEL_41;
  if ( *v21 != 826364754 )
  {
    SymcryptRsakey = -2146893819;
    goto LABEL_66;
  }
  LODWORD(a3) = v21[1];
  if ( (unsigned int)((_DWORD)a3 - 256) > 0x3F00 )
  {
    SymcryptRsakey = -2146893783;
LABEL_66:
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v62 = -25;
LABEL_69:
      WPP_SF_sDsd(
        v29[2],
        (_DWORD)v22,
        (_DWORD)a3,
        (unsigned int)"Status",
        SymcryptRsakey,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        v62);
    }
  }
  else
  {
    v26 = (unsigned int)v21[2];
    if ( (unsigned int)v26 > 0x7FFFFFFF
      || (v27 = (unsigned int)v21[3], (unsigned int)v27 > 0x7FFFFFFF)
      || v21[4]
      || v21[5] )
    {
LABEL_41:
      SymcryptRsakey = -2146893819;
      goto LABEL_66;
    }
    v22 = (const wchar_t *)(v27 + v26 + 24);
    if ( (const wchar_t *)v20 != v22 )
    {
      SymcryptRsakey = -2146893819;
      goto LABEL_66;
    }
    v28 = 0;
LABEL_80:
    v33 = v21[3];
    v34 = (unsigned int)v21[2];
    v35 = 8 * v33;
    if ( (unsigned int)((_DWORD)a3 + 7) >> 3 >= v33 )
      v35 = (unsigned int)a3;
    v36 = CreateAndInitializeNewKey(a1, v35, &P);
    v39 = P;
    SymcryptRsakey = v36;
    if ( v36 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v37,
          v38,
          (unsigned int)"Status",
          v36,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
          19);
      goto LABEL_112;
    }
    SymcryptRsakey = AllocateSymcryptRsakey(P);
    if ( (SymcryptRsakey & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v40,
          v41,
          (unsigned int)"Status",
          SymcryptRsakey,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
          26);
      goto LABEL_112;
    }
    v42 = 0;
    v43 = v21 + 6;
    if ( v28 )
    {
      v42 = 2;
      *(_QWORD *)&v67 = (char *)v21 + v34 + (unsigned int)v21[3] + 24;
      *(_QWORD *)&v66 = (unsigned int)v21[4];
      *((_QWORD *)&v67 + 1) = v67 + (unsigned int)v21[4];
      *((_QWORD *)&v66 + 1) = (unsigned int)v21[5];
    }
    v44 = (unsigned int)v21[2];
    if ( v44 <= 8 )
    {
LABEL_95:
      for ( j = 0; v44; --v44 )
      {
        v46 = (unsigned __int8)*v43++;
        j = v46 | (j << 8);
      }
      v65 = j;
      v47 = BCryptFlagsToSymCryptKeyValidationFlags(a7, v43, j, v42);
      switch ( a8 )
      {
        case 4:
          v47 |= 0x3100u;
          break;
        case 1:
          v47 |= 0x1000u;
          break;
        case 2:
          v47 |= 0x2000u;
          break;
      }
      v52 = v47 | 0x100;
      if ( v35 >= 0x400 )
        v52 = v47;
      v53 = SymCryptRsakeySetValueInternal(
              v49,
              v21[3],
              (unsigned int)&v65,
              1,
              0,
              0,
              (__int64)&v67,
              (__int64)&v66,
              v48,
              2,
              v52,
              v39[4]);
      if ( v53 )
      {
        SymcryptRsakey = SymcryptErrorCodeToNtStatus(v53);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v54,
            v55,
            (unsigned int)"Status",
            SymcryptRsakey,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
            87);
        goto LABEL_112;
      }
      SymcryptRsakey = 0;
      *((_DWORD *)v39 + 4) = 1;
      *a4 = v39;
    }
    else
    {
      while ( !*v43 )
      {
        ++v43;
        if ( --v44 <= 8 )
          goto LABEL_95;
      }
      SymcryptRsakey = SymcryptErrorCodeToNtStatus(32786);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v50,
          v51,
          (unsigned int)"Status",
          SymcryptRsakey,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
          45);
LABEL_112:
      if ( v39 )
      {
        v56 = v39[4];
        if ( v56 )
        {
          SymCryptWipeAsm(v39[4], *(unsigned int *)(v56 + 4));
          v57 = (void *)(v56 - *(unsigned int *)(v56 - 4));
          if ( v57 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v57);
          v39[4] = 0;
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v39);
      }
    }
  }
LABEL_126:
  if ( v17 )
  {
LABEL_127:
    v58 = v63;
    v59 = v17;
    if ( v63 )
    {
      do
      {
        *v59++ = 0;
        --v58;
      }
      while ( v58 );
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
  }
  return SymcryptRsakey;
}

```

## disassembly

```asm
0x18004a3b0  mov     rax, rsp
0x18004a3b3  mov     [rax+20h], r9
0x18004a3b7  push    rbx
0x18004a3b8  push    rbp
0x18004a3b9  push    rsi
0x18004a3ba  push    rdi
0x18004a3bb  push    r12
0x18004a3bd  push    r13
0x18004a3bf  push    r14
0x18004a3c1  push    r15
0x18004a3c3  sub     rsp, 0A8h
0x18004a3ca  xor     r15d, r15d
0x18004a3cd  xorps   xmm0, xmm0
0x18004a3d0  test    [rsp+0E8h+arg_30], 0FFFFFFF7h
0x18004a3db  xorps   xmm1, xmm1
0x18004a3de  mov     rdi, rdx
0x18004a3e1  mov     [rax-78h], r15
0x18004a3e5  mov     r13, rcx
0x18004a3e8  mov     [rax-80h], r15
0x18004a3ec  movups  xmmword ptr [rax-60h], xmm0
0x18004a3f0  mov     [rsp+0E8h+var_88], r15d
0x18004a3f5  movups  xmmword ptr [rax-70h], xmm1
0x18004a3f9  mov     [r9], r15
0x18004a3fc  jz      short loc_18004A431
0x18004a3fe  mov     ebx, 0C000000Dh
0x18004a403  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a40a  lea     rax, WPP_GLOBAL_Control
0x18004a411  cmp     rcx, rax
0x18004a414  jz      loc_18004ACB6
0x18004a41a  test    byte ptr [rcx+1Ch], 1
0x18004a41e  jz      loc_18004ACB6
0x18004a424  mov     dword ptr [rsp+0E8h+var_B8], 593h
0x18004a42c  jmp     loc_18004AC92
0x18004a431  mov     ecx, [rsp+0E8h+arg_38]
0x18004a438  lea     eax, [rcx-1]
0x18004a43b  test    eax, 0FFFFFFFCh
0x18004a440  jnz     loc_18004AC6C
0x18004a446  cmp     ecx, 3
0x18004a449  jz      loc_18004AC6C
0x18004a44f  test    r13, r13
0x18004a452  jz      loc_18004AC30
0x18004a458  cmp     dword ptr [r13+4], 4D535241h
0x18004a460  jnz     loc_18004AC30
0x18004a466  lea     r14, aRsaprivateblob; "RSAPRIVATEBLOB"
0x18004a46d  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18004a474  test    r8, r8
0x18004a477  jz      short loc_18004A4A5
0x18004a479  lea     rdx, aPkcs11rsaaeswr; "PKCS11RsaAesWrapBlob"
0x18004a480  mov     rcx, rbx
0x18004a483  movzx   eax, word ptr [r8+rcx*2+2]
0x18004a489  cmp     ax, [rdx+rcx*2+2]
0x18004a48e  jnz     short loc_18004A4A5
0x18004a490  add     rcx, 2
0x18004a494  cmp     rcx, 15h
0x18004a498  jz      short loc_18004A4F5
0x18004a49a  movzx   eax, word ptr [r8+rcx*2]
0x18004a49f  cmp     ax, [rdx+rcx*2]
0x18004a4a3  jz      short loc_18004A483
0x18004a4a5  test    rdi, rdi
0x18004a4a8  jz      loc_18004A66B
0x18004a4ae  mov     ebx, 0C00000BBh
0x18004a4b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a4ba  lea     rax, WPP_GLOBAL_Control
0x18004a4c1  cmp     rcx, rax
0x18004a4c4  jz      loc_18004ACB6
0x18004a4ca  test    byte ptr [rcx+1Ch], 1
0x18004a4ce  jz      loc_18004ACB6
0x18004a4d4  mov     dword ptr [rsp+0E8h+var_B8], 5D9h
0x18004a4dc  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004a4e3  mov     [rsp+0E8h+var_C0], rax
0x18004a4e8  mov     dword ptr [rsp+0E8h+var_C8], 0C00000BBh
0x18004a4f0  jmp     loc_18004ACA6
0x18004a4f5  test    rdi, rdi
0x18004a4f8  jnz     short loc_18004A52D
0x18004a4fa  mov     ebx, 0C000000Dh
0x18004a4ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a506  lea     rax, WPP_GLOBAL_Control
0x18004a50d  cmp     rcx, rax
0x18004a510  jz      loc_18004ACB6
0x18004a516  test    byte ptr [rcx+1Ch], 1
0x18004a51a  jz      loc_18004ACB6
0x18004a520  mov     dword ptr [rsp+0E8h+var_B8], 5AEh
0x18004a528  jmp     loc_18004AC92
0x18004a52d  mov     esi, [rsp+0E8h+arg_28]
0x18004a534  lea     r9, [rsp+0E8h+var_88]
0x18004a539  mov     rbp, [rsp+0E8h+arg_20]
0x18004a541  xor     r8d, r8d
0x18004a544  mov     dword ptr [rsp+0E8h+var_C0], esi
0x18004a548  mov     rdx, rdi
0x18004a54b  mov     rcx, r13
0x18004a54e  mov     [rsp+0E8h+var_C8], rbp
0x18004a553  call    Pkcs11ConvertToKeyBlob
0x18004a558  test    eax, eax
0x18004a55a  jns     short loc_18004A58F
0x18004a55c  mov     ebx, 0C000000Dh
0x18004a561  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a568  lea     rax, WPP_GLOBAL_Control
0x18004a56f  cmp     rcx, rax
0x18004a572  jz      loc_18004ACB6
0x18004a578  test    byte ptr [rcx+1Ch], 1
0x18004a57c  jz      loc_18004ACB6
0x18004a582  mov     dword ptr [rsp+0E8h+var_B8], 5BBh
0x18004a58a  jmp     loc_18004AC92
0x18004a58f  mov     ecx, [rsp+0E8h+var_88]
0x18004a593  call    SafeAllocaAllocateFromHeap
0x18004a598  mov     r12, rax
0x18004a59b  test    rax, rax
0x18004a59e  jnz     short loc_18004A5E7
0x18004a5a0  mov     ebx, 0C0000017h
0x18004a5a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a5ac  lea     rax, WPP_GLOBAL_Control
0x18004a5b3  cmp     rcx, rax
0x18004a5b6  jz      loc_18004ACB6
0x18004a5bc  test    byte ptr [rcx+1Ch], 1
0x18004a5c0  jz      loc_18004ACB6
0x18004a5c6  mov     dword ptr [rsp+0E8h+var_B8], 5C2h
0x18004a5ce  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004a5d5  mov     [rsp+0E8h+var_C0], rax
0x18004a5da  mov     dword ptr [rsp+0E8h+var_C8], 0C0000017h
0x18004a5e2  jmp     loc_18004ACA6
0x18004a5e7  mov     dword ptr [rsp+0E8h+var_C0], esi
0x18004a5eb  lea     r9, [rsp+0E8h+var_88]
0x18004a5f0  mov     r8, r12
0x18004a5f3  mov     [rsp+0E8h+var_C8], rbp
0x18004a5f8  mov     rdx, rdi
0x18004a5fb  mov     rcx, r13
0x18004a5fe  call    Pkcs11ConvertToKeyBlob
0x18004a603  test    eax, eax
0x18004a605  jns     short loc_18004A65E
0x18004a607  mov     ebx, 0C000000Dh
0x18004a60c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a613  lea     rax, WPP_GLOBAL_Control
0x18004a61a  cmp     rcx, rax
0x18004a61d  jz      loc_18004ABEB
0x18004a623  test    byte ptr [rcx+1Ch], 1
0x18004a627  jz      loc_18004ABEB
0x18004a62d  mov     rcx, [rcx+10h]
0x18004a631  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004a638  mov     dword ptr [rsp+0E8h+var_B8], 5CFh
0x18004a640  lea     r9, aStatus; "Status"
0x18004a647  mov     [rsp+0E8h+var_C0], rax
0x18004a64c  mov     dword ptr [rsp+0E8h+var_C8], 0C000000Dh
0x18004a654  call    WPP_SF_sDsd
0x18004a659  jmp     loc_18004ABEB
0x18004a65e  mov     r10d, [rsp+0E8h+var_88]
0x18004a663  mov     rdi, r12
0x18004a666  mov     r8, r14
0x18004a669  jmp     short loc_18004A67E
0x18004a66b  mov     r10d, [rsp+0E8h+arg_28]
0x18004a673  mov     r12, r15
0x18004a676  mov     rdi, [rsp+0E8h+arg_20]
0x18004a67e  lea     rdx, aRsapublicblob; "RSAPUBLICBLOB"
0x18004a685  mov     rcx, r15
0x18004a688  nop     dword ptr [rax+rax+00000000h]
0x18004a690  movzx   eax, word ptr [r8+rcx*2]
0x18004a695  cmp     ax, [rdx+rcx*2]
0x18004a699  jnz     short loc_18004A6C6
0x18004a69b  movzx   eax, word ptr [r8+rcx*2+2]
0x18004a6a1  cmp     ax, [rdx+rcx*2+2]
0x18004a6a6  jnz     short loc_18004A6C6
0x18004a6a8  add     rcx, 2
0x18004a6ac  cmp     rcx, 0Eh
0x18004a6b0  jnz     short loc_18004A690
0x18004a6b2  cmp     r10d, 18h
0x18004a6b6  jnb     loc_18004A75E
0x18004a6bc  mov     ebx, 80090005h
0x18004a6c1  jmp     loc_18004A7D3
0x18004a6c6  lea     rdx, aPublicblob; "PUBLICBLOB"
0x18004a6cd  mov     rcx, rbx
0x18004a6d0  movzx   eax, word ptr [r8+rcx*2+2]
0x18004a6d6  cmp     ax, [rdx+rcx*2+2]
0x18004a6db  jnz     short loc_18004A6F2
0x18004a6dd  add     rcx, 2
0x18004a6e1  cmp     rcx, 0Bh
0x18004a6e5  jz      short loc_18004A6B2
0x18004a6e7  movzx   eax, word ptr [r8+rcx*2]
0x18004a6ec  cmp     ax, [rdx+rcx*2]
0x18004a6f0  jz      short loc_18004A6D0
0x18004a6f2  movzx   eax, word ptr [r8+rbx*2+2]
0x18004a6f8  cmp     ax, [r14+rbx*2+2]
0x18004a6fe  jnz     short loc_18004A716
0x18004a700  add     rbx, 2
0x18004a704  cmp     rbx, 0Fh
0x18004a708  jz      short loc_18004A74A
0x18004a70a  movzx   eax, word ptr [r8+rbx*2]
0x18004a70f  cmp     ax, [r14+rbx*2]
0x18004a714  jz      short loc_18004A6F2
0x18004a716  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x18004a71d  mov     rcx, r15
0x18004a720  movzx   eax, word ptr [r8+rcx*2]
0x18004a725  cmp     ax, [rdx+rcx*2]
0x18004a729  jnz     loc_18004AB98
0x18004a72f  movzx   eax, word ptr [r8+rcx*2+2]
0x18004a735  cmp     ax, [rdx+rcx*2+2]
0x18004a73a  jnz     loc_18004AB98
0x18004a740  add     rcx, 2
0x18004a744  cmp     rcx, 0Ch
0x18004a748  jnz     short loc_18004A720
0x18004a74a  cmp     r10d, 18h
0x18004a74e  jnb     loc_18004A811
0x18004a754  mov     ebx, 80090005h
0x18004a759  jmp     loc_18004AB72
0x18004a75e  cmp     dword ptr [rdi], 31415352h
0x18004a764  jz      short loc_18004A76D
0x18004a766  mov     ebx, 80090005h
0x18004a76b  jmp     short loc_18004A7D3
0x18004a76d  mov     r8d, [rdi+4]
0x18004a771  lea     eax, [r8-100h]
0x18004a778  cmp     eax, 3F00h
0x18004a77d  ja      short loc_18004A7CE
0x18004a77f  mov     eax, [rdi+8]
0x18004a782  cmp     eax, 7FFFFFFFh
0x18004a787  ja      loc_18004A6BC
0x18004a78d  mov     ecx, [rdi+0Ch]
0x18004a790  cmp     ecx, 7FFFFFFFh
0x18004a796  ja      loc_18004A6BC
0x18004a79c  cmp     [rdi+10h], r15d
0x18004a7a0  jnz     loc_18004A6BC
0x18004a7a6  cmp     [rdi+14h], r15d
0x18004a7aa  jnz     loc_18004A6BC
0x18004a7b0  lea     rdx, [rax+18h]
0x18004a7b4  mov     eax, r10d
0x18004a7b7  add     rdx, rcx
0x18004a7ba  cmp     rax, rdx
0x18004a7bd  jz      short loc_18004A7C6
0x18004a7bf  mov     ebx, 80090005h
0x18004a7c4  jmp     short loc_18004A7D3
0x18004a7c6  mov     ebp, r15d
0x18004a7c9  jmp     loc_18004A89A
0x18004a7ce  mov     ebx, 80090029h
0x18004a7d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a7da  lea     rax, WPP_GLOBAL_Control
0x18004a7e1  cmp     rcx, rax
0x18004a7e4  jz      loc_18004ABE2
0x18004a7ea  test    byte ptr [rcx+1Ch], 1
0x18004a7ee  jz      loc_18004ABE2
0x18004a7f4  mov     dword ptr [rsp+0E8h+var_B8], 5E7h
0x18004a7fc  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004a803  mov     [rsp+0E8h+var_C0], rax
0x18004a808  mov     dword ptr [rsp+0E8h+var_C8], ebx
0x18004a80c  jmp     loc_18004ABD2
0x18004a811  cmp     dword ptr [rdi], 32415352h
0x18004a817  jz      short loc_18004A823
0x18004a819  mov     ebx, 80090005h
0x18004a81e  jmp     loc_18004AB72
0x18004a823  mov     r8d, [rdi+4]
0x18004a827  lea     eax, [r8-100h]
0x18004a82e  cmp     eax, 3F00h
0x18004a833  ja      loc_18004AB6D
0x18004a839  mov     edx, [rdi+8]
0x18004a83c  cmp     edx, 7FFFFFFFh
0x18004a842  ja      loc_18004A754
0x18004a848  mov     r9d, [rdi+0Ch]
0x18004a84c  cmp     r9d, 7FFFFFFFh
0x18004a853  ja      loc_18004A754
0x18004a859  mov     eax, [rdi+10h]
0x18004a85c  cmp     eax, 7FFFFFFFh
0x18004a861  ja      loc_18004A754
0x18004a867  mov     ecx, [rdi+14h]
0x18004a86a  cmp     ecx, 7FFFFFFFh
0x18004a870  ja      loc_18004A754
0x18004a876  add     rcx, rax
0x18004a879  lea     rax, [rdx+18h]
0x18004a87d  add     rcx, r9
0x18004a880  add     rcx, rax
0x18004a883  mov     eax, r10d
0x18004a886  cmp     rax, rcx
0x18004a889  jnb     short loc_18004A895
0x18004a88b  mov     ebx, 80090005h
0x18004a890  jmp     loc_18004AB72
0x18004a895  mov     ebp, 1
0x18004a89a  mov     ecx, [rdi+0Ch]
0x18004a89d  lea     eax, [r8+7]
0x18004a8a1  mov     r14d, [rdi+8]
0x18004a8a5  shr     eax, 3
0x18004a8a8  cmp     eax, ecx
0x18004a8aa  lea     r15d, ds:0[rcx*8]
0x18004a8b2  mov     rcx, r13
0x18004a8b5  cmovnb  r15d, r8d
0x18004a8b9  lea     r8, [rsp+0E8h+P]
0x18004a8be  mov     edx, r15d
0x18004a8c1  call    CreateAndInitializeNewKey
0x18004a8c6  mov     rsi, [rsp+0E8h+P]
0x18004a8cb  mov     ebx, eax
0x18004a8cd  test    eax, eax
0x18004a8cf  jns     short loc_18004A8FF
0x18004a8d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a8d8  lea     rax, WPP_GLOBAL_Control
0x18004a8df  cmp     rcx, rax
0x18004a8e2  jz      loc_18004AAE6
0x18004a8e8  test    byte ptr [rcx+1Ch], 1
0x18004a8ec  jz      loc_18004AAE6
0x18004a8f2  mov     dword ptr [rsp+0E8h+var_B8], 613h
0x18004a8fa  jmp     loc_18004AAC6
0x18004a8ff  mov     rcx, rsi
0x18004a902  call    AllocateSymcryptRsakey
0x18004a907  mov     ebx, eax
0x18004a909  test    eax, eax
0x18004a90b  jns     short loc_18004A93B
0x18004a90d  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
