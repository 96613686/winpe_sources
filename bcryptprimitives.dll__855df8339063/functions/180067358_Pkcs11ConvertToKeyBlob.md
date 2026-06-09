# Pkcs11ConvertToKeyBlob

- ea: `0x180067358`
- end: `0x1800678f5`
- name: `Pkcs11ConvertToKeyBlob`
- size: `1437`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18002cd40`
- `0x1800476d0`
- `0x18004a3b0`

## callees

- `0x18000ecb0`
- `0x180010270`
- `0x1800102a0`
- `0x180010630`
- `0x18002e680`
- `0x18003cb4c`
- `0x18003cfd4`
- `0x180047480`
- `0x1800495b0`
- `0x180063170`
- `0x180063180`
- `0x180066428`
- `0x180067358`
- `0x1800678fc`
- `0x180067c40`
- `0x18006c8f0`
- `0x18007f790`

## string_xrefs

- `0x180067414`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`
- `0x18006759a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`
- `0x1800675d4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`
- `0x180067639`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`
- `0x18006768f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`
- `0x180067701`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`
- `0x18006785b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`

## pseudocode

```c
__int64 __fastcall Pkcs11ConvertToKeyBlob(__int64 a1, __int64 a2, _DWORD *a3, _DWORD *a4, _DWORD *a5, unsigned int a6)
{
  int v7; // r15d
  PVOID v10; // r13
  __int64 v11; // r12
  unsigned int v12; // ebx
  __int64 v13; // r9
  __int64 v14; // rcx
  int RsaProperty; // eax
  unsigned int v16; // ecx
  unsigned int v17; // edx
  int v18; // ecx
  int v19; // ebx
  _BYTE *Src; // rsi
  int v21; // eax
  int v22; // eax
  __int64 v23; // r14
  int SymmetricKey; // eax
  __int64 v25; // r9
  __int64 v26; // rcx
  unsigned int v27; // edi
  unsigned int v28; // edi
  int v29; // eax
  __int64 v30; // rax
  const void *v31; // r14
  __int64 v32; // r9
  __int64 v33; // rcx
  int v34; // eax
  __int64 v35; // rdi
  __int64 v36; // r9
  __int64 v37; // rcx
  int v38; // ecx
  bool v39; // zf
  int v40; // ecx
  _DWORD *v41; // rax
  int v42; // r15d
  size_t v43; // r8
  __int64 v44; // rcx
  _BYTE *v45; // rax
  int *v46; // rax
  __int64 v47; // rax
  _BYTE *v48; // rcx
  size_t v50; // [rsp+28h] [rbp-D8h]
  size_t Size; // [rsp+50h] [rbp-B0h] BYREF
  size_t v52; // [rsp+58h] [rbp-A8h] BYREF
  PVOID P; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD *v54; // [rsp+68h] [rbp-98h]
  int v55[2]; // [rsp+70h] [rbp-90h] BYREF
  int v56; // [rsp+78h] [rbp-88h]
  __int64 v57; // [rsp+80h] [rbp-80h]
  char *v58; // [rsp+88h] [rbp-78h] BYREF
  char *v59; // [rsp+90h] [rbp-70h]
  int v60; // [rsp+98h] [rbp-68h]
  int v61; // [rsp+9Ch] [rbp-64h]
  _DWORD *v62; // [rsp+A0h] [rbp-60h]
  int v63[148]; // [rsp+B0h] [rbp-50h] BYREF

  v62 = a3;
  v7 = (int)a3;
  v57 = a1;
  v54 = a4;
  v56 = 0;
  LODWORD(v52) = 0;
  Size = 0;
  v10 = 0;
  P = 0;
  v11 = 0;
  *(_QWORD *)v55 = 0;
  v61 = 0;
  memset_0(v63, 0, sizeof(v63));
  if ( !a4 || !a1 )
  {
    Src = 0;
    v12 = -1073741811;
    v32 = 603;
    v33 = 3221225485LL;
    goto LABEL_60;
  }
  if ( !validateMSCryptRsaKey(a2) )
  {
    v12 = -1073741811;
    v13 = 611;
    v14 = 3221225485LL;
LABEL_5:
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\pkcsblob.c", v13);
    return v12;
  }
  RsaProperty = GetRsaProperty(a2, L"KeyLength", (char *)&Size + 4);
  v12 = RsaProperty;
  if ( RsaProperty < 0 )
  {
    v13 = 625;
LABEL_8:
    v14 = (unsigned int)RsaProperty;
    goto LABEL_5;
  }
  HIDWORD(Size) >>= 3;
  RsaProperty = Pkcs11VerifyRsaAesWrapBlob(a5, a6);
  v12 = RsaProperty;
  if ( RsaProperty < 0 )
  {
    v13 = 636;
    goto LABEL_8;
  }
  v16 = a5[1] + 16;
  if ( a5[1] >= 0xFFFFFFF0 )
  {
    v13 = 646;
LABEL_13:
    v12 = -1073741675;
    v14 = 3221225621LL;
    goto LABEL_5;
  }
  v17 = v16 + a5[2];
  v58 = (char *)a5 + v16;
  if ( v17 < v16 )
  {
    v13 = 654;
    goto LABEL_13;
  }
  v18 = a5[3];
  if ( v18 )
    v59 = (char *)a5 + v17;
  else
    v59 = 0;
  v60 = v18;
  RsaProperty = MSCryptRsaDecrypt(
                  a2,
                  (__int64)(a5 + 4),
                  HIDWORD(Size),
                  (__int64)&v58,
                  0,
                  0,
                  0,
                  0,
                  (unsigned int *)&v52,
                  4);
  v12 = RsaProperty;
  if ( RsaProperty < 0 )
  {
    v13 = 673;
    goto LABEL_8;
  }
  v19 = v52;
  Src = (_BYTE *)SafeAllocaAllocateFromHeap((unsigned int)v52);
  if ( !Src )
  {
    v12 = -1073741801;
    v13 = 680;
    v14 = 3221225495LL;
    goto LABEL_5;
  }
  v21 = MSCryptRsaDecrypt(
          a2,
          (__int64)(a5 + 4),
          HIDWORD(Size),
          (__int64)&v58,
          0,
          0,
          (__int64)Src,
          v19,
          (unsigned int *)&v52,
          4);
  v12 = v21;
  if ( v21 < 0 )
  {
    DebugTraceError(
      (unsigned int)v21,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\pkcsblob.c",
      696);
LABEL_68:
    v47 = (unsigned int)v52;
    v48 = Src;
    if ( (_DWORD)v52 )
    {
      do
      {
        *v48++ = 0;
        --v47;
      }
      while ( v47 );
    }
    MSCryptFree(Src);
    return v12;
  }
  v22 = MSCryptOpenSymmetricProvider(&P, L"AES", 0);
  v12 = v22;
  if ( v22 < 0 )
  {
    DebugTraceError(
      (unsigned int)v22,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\pkcsblob.c",
      707);
    v10 = P;
    goto LABEL_65;
  }
  v10 = P;
  v23 = 592;
  LODWORD(v50) = v52;
  SymmetricKey = MSCryptGenerateSymmetricKey((int)P, (int)v55, (int)v63, 592, Src, v50, 0);
  v12 = SymmetricKey;
  if ( SymmetricKey < 0 )
  {
    v25 = 720;
    v26 = (unsigned int)SymmetricKey;
LABEL_29:
    DebugTraceError(v26, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\pkcsblob.c", v25);
    v11 = *(_QWORD *)v55;
    goto LABEL_62;
  }
  v27 = a5[1];
  if ( v27 < HIDWORD(Size) )
  {
    v12 = -1073741675;
    v25 = 727;
    v26 = 3221225621LL;
    goto LABEL_29;
  }
  v28 = v27 - HIDWORD(Size);
  v11 = *(_QWORD *)v55;
  P = (char *)a5 + HIDWORD(Size) + 16;
  v29 = MSCryptAesKeyUnwrapPad(v55[0], 0, (unsigned int)&Size, (_DWORD)P, v28);
  v12 = v29;
  if ( v29 < 0 )
  {
    DebugTraceError(
      (unsigned int)v29,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\pkcsblob.c",
      739);
    goto LABEL_62;
  }
  v30 = SafeAllocaAllocateFromHeap((unsigned int)Size);
  v31 = (const void *)v30;
  if ( v30 )
  {
    v34 = MSCryptAesKeyUnwrapPad(v11, v30, (unsigned int)&Size, (_DWORD)P, v28);
    v35 = (unsigned int)Size;
    v12 = v34;
    if ( v34 >= 0 )
    {
      if ( (*(_DWORD *)(v57 + 8) & 0xFFFF0000) != 0x30000 )
      {
        v41 = v62;
        v42 = Size + 12;
        if ( v62 )
        {
          if ( (unsigned int)Size > 0xC80 )
          {
            v12 = -1073741481;
            v36 = 805;
            v37 = 3221225815LL;
            goto LABEL_38;
          }
          if ( *v54 < (unsigned int)Size )
          {
            *v54 = v42;
            v12 = -2146893784;
            v37 = 2148073512LL;
            v36 = 812;
            goto LABEL_38;
          }
          v43 = (unsigned int)Size;
          *v62 = 1296188491;
          v41[1] = 1;
          v41[2] = v35;
          memcpy_0(v41 + 3, v31, v43);
        }
        *v54 = v42;
        goto LABEL_55;
      }
      v38 = *(unsigned __int16 *)(v57 + 8);
      LODWORD(Size) = 0;
      if ( (unsigned int)(v38 - 4) <= 2 || (v39 = v38 == 11, v40 = 3, v39) )
        v40 = 5;
      v34 = Pkcs8ConvertToKeyBlob(v40, v7, (_DWORD)v54, (_DWORD)v31, v35, (__int64)&Size);
      v12 = v34;
      if ( v34 >= 0 )
      {
        if ( !(_DWORD)Size || (_DWORD)Size == *(_DWORD *)(v57 + 8) )
          goto LABEL_55;
        v12 = -1073739509;
        v36 = 787;
        v37 = 3221227787LL;
        goto LABEL_38;
      }
      v36 = 779;
    }
    else
    {
      v36 = 757;
    }
    v37 = (unsigned int)v34;
LABEL_38:
    DebugTraceError(v37, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\pkcsblob.c", v36);
LABEL_55:
    v44 = v35;
    v45 = v31;
    if ( (_DWORD)v35 )
    {
      do
      {
        *v45++ = 0;
        --v44;
      }
      while ( v44 );
    }
    MSCryptFree(v31);
    goto LABEL_61;
  }
  v12 = -1073741801;
  v32 = 746;
  v33 = 3221225495LL;
LABEL_60:
  DebugTraceError(v33, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\pkcsblob.c", v32);
LABEL_61:
  v23 = 592;
LABEL_62:
  if ( v11 )
  {
    MSCryptDestroyKey(v11);
    v46 = v63;
    do
    {
      *(_BYTE *)v46 = 0;
      v46 = (int *)((char *)v46 + 1);
      --v23;
    }
    while ( v23 );
  }
LABEL_65:
  if ( v10 )
    MSCryptCloseSymmetricProvider(v10);
  if ( Src )
    goto LABEL_68;
  return v12;
}

```

## disassembly

```asm
0x180067358  mov     [rsp-8+arg_0], rbx
0x18006735d  push    rbp
0x18006735e  push    rsi
0x18006735f  push    rdi
0x180067360  push    r12
0x180067362  push    r13
0x180067364  push    r14
0x180067366  push    r15
0x180067368  lea     rbp, [rsp-210h]
0x180067370  sub     rsp, 310h
0x180067377  mov     rax, cs:__security_cookie
0x18006737e  xor     rax, rsp
0x180067381  mov     [rbp+240h+var_40], rax
0x180067388  mov     rdi, [rbp+240h+arg_20]
0x18006738f  xor     eax, eax
0x180067391  mov     rbx, r9
0x180067394  mov     [rbp+240h+var_2A0], r8
0x180067398  mov     r15, r8
0x18006739b  mov     [rbp+240h+var_2C0], rcx
0x18006739f  mov     r14, rdx
0x1800673a2  mov     [rsp+340h+var_2D8], rbx
0x1800673a7  mov     rsi, rcx
0x1800673aa  mov     dword ptr [rsp+340h+Size+4], eax
0x1800673ae  xor     edx, edx; Val
0x1800673b0  mov     [rsp+340h+var_2C8], eax
0x1800673b4  mov     r8d, 250h; Size
0x1800673ba  mov     dword ptr [rsp+340h+var_2E8], eax
0x1800673be  lea     rcx, [rbp+240h+var_290]; void *
0x1800673c2  mov     dword ptr [rsp+340h+Size], eax
0x1800673c6  mov     r13d, eax
0x1800673c9  mov     [rsp+340h+P], rax
0x1800673ce  mov     r12d, eax
0x1800673d1  mov     qword ptr [rsp+340h+var_2D0], rax
0x1800673d6  mov     [rbp+240h+var_2A4], eax
0x1800673d9  call    memset_0
0x1800673de  test    rbx, rbx
0x1800673e1  jz      loc_180067849
0x1800673e7  test    rsi, rsi
0x1800673ea  jz      loc_180067849
0x1800673f0  mov     rcx, r14
0x1800673f3  call    validateMSCryptRsaKey
0x1800673f8  test    rax, rax
0x1800673fb  jnz     short loc_180067425
0x1800673fd  mov     ebx, 0C000000Dh
0x180067402  mov     r9d, 263h
0x180067408  mov     ecx, 0C000000Dh
0x18006740d  lea     rdx, aStatus; "Status"
0x180067414  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006741b  call    DebugTraceError
0x180067420  jmp     loc_1800678C8
0x180067425  mov     byte ptr [rsp+340h+var_310], r13b
0x18006742a  lea     rax, [rsp+340h+var_2C8]
0x18006742f  mov     esi, 4
0x180067434  mov     dword ptr [rsp+340h+var_318], r13d
0x180067439  mov     r9d, esi
0x18006743c  mov     [rsp+340h+Src], rax
0x180067441  lea     r8, [rsp+340h+Size+4]
0x180067446  mov     rcx, r14
0x180067449  lea     rdx, aKeylength; "KeyLength"
0x180067450  call    GetRsaProperty
0x180067455  mov     ebx, eax
0x180067457  test    eax, eax
0x180067459  jns     short loc_180067465
0x18006745b  mov     r9d, 271h
0x180067461  mov     ecx, eax
0x180067463  jmp     short loc_18006740D
0x180067465  mov     r8d, dword ptr [rsp+340h+Size+4]
0x18006746a  mov     rcx, rdi
0x18006746d  mov     edx, [rbp+240h+arg_28]
0x180067473  shr     r8d, 3
0x180067477  mov     dword ptr [rsp+340h+Size+4], r8d
0x18006747c  call    Pkcs11VerifyRsaAesWrapBlob
0x180067481  mov     ebx, eax
0x180067483  test    eax, eax
0x180067485  jns     short loc_18006748F
0x180067487  mov     r9d, 27Ch
0x18006748d  jmp     short loc_180067461
0x18006748f  mov     ecx, [rdi+4]
0x180067492  add     ecx, 10h
0x180067495  cmp     ecx, 10h
0x180067498  jnb     short loc_1800674AF
0x18006749a  mov     r9d, 286h
0x1800674a0  mov     ebx, 0C0000095h
0x1800674a5  mov     ecx, 0C0000095h
0x1800674aa  jmp     loc_18006740D
0x1800674af  mov     edx, [rdi+8]
0x1800674b2  mov     eax, ecx
0x1800674b4  add     edx, ecx
0x1800674b6  add     rax, rdi
0x1800674b9  mov     [rbp+240h+var_2B8], rax
0x1800674bd  cmp     edx, ecx
0x1800674bf  jnb     short loc_1800674C9
0x1800674c1  mov     r9d, 28Eh
0x1800674c7  jmp     short loc_1800674A0
0x1800674c9  mov     ecx, [rdi+0Ch]
0x1800674cc  lea     r12, [rdi+10h]
0x1800674d0  test    ecx, ecx
0x1800674d2  jnz     short loc_1800674DA
0x1800674d4  mov     [rbp+240h+var_2B0], r13
0x1800674d8  jmp     short loc_1800674E3
0x1800674da  mov     eax, edx
0x1800674dc  add     rax, rdi
0x1800674df  mov     [rbp+240h+var_2B0], rax
0x1800674e3  mov     r8d, dword ptr [rsp+340h+Size+4]
0x1800674e8  lea     rax, [rsp+340h+var_2E8]
0x1800674ed  mov     [rsp+340h+var_2F8], esi
0x1800674f1  lea     r9, [rbp+240h+var_2B8]
0x1800674f5  mov     [rsp+340h+var_300], rax
0x1800674fa  mov     rdx, r12
0x1800674fd  mov     [rsp+340h+var_308], r13d
0x180067502  mov     qword ptr [rsp+340h+var_310], r13
0x180067507  mov     [rbp+240h+var_2A8], ecx
0x18006750a  mov     rcx, r14
0x18006750d  mov     dword ptr [rsp+340h+var_318], r13d
0x180067512  mov     [rsp+340h+Src], r13
0x180067517  call    MSCryptRsaDecrypt
0x18006751c  mov     ebx, eax
0x18006751e  test    eax, eax
0x180067520  jns     short loc_18006752D
0x180067522  mov     r9d, 2A1h
0x180067528  jmp     loc_180067461
0x18006752d  mov     ebx, dword ptr [rsp+340h+var_2E8]
0x180067531  mov     ecx, ebx
0x180067533  call    SafeAllocaAllocateFromHeap
0x180067538  mov     rsi, rax
0x18006753b  test    rax, rax
0x18006753e  jnz     short loc_180067555
0x180067540  mov     ebx, 0C0000017h
0x180067545  mov     r9d, 2A8h
0x18006754b  mov     ecx, 0C0000017h
0x180067550  jmp     loc_18006740D
0x180067555  mov     r8d, dword ptr [rsp+340h+Size+4]
0x18006755a  lea     rax, [rsp+340h+var_2E8]
0x18006755f  mov     [rsp+340h+var_2F8], 4
0x180067567  lea     r9, [rbp+240h+var_2B8]
0x18006756b  mov     [rsp+340h+var_300], rax
0x180067570  mov     rdx, r12
0x180067573  mov     [rsp+340h+var_308], ebx
0x180067577  mov     rcx, r14
0x18006757a  mov     qword ptr [rsp+340h+var_310], rsi
0x18006757f  mov     dword ptr [rsp+340h+var_318], r13d
0x180067584  mov     [rsp+340h+Src], r13
0x180067589  call    MSCryptRsaDecrypt
0x18006758e  mov     ebx, eax
0x180067590  test    eax, eax
0x180067592  jns     short loc_1800675B4
0x180067594  mov     r9d, 2B8h
0x18006759a  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800675a1  lea     rdx, aStatus; "Status"
0x1800675a8  mov     ecx, eax
0x1800675aa  call    DebugTraceError
0x1800675af  jmp     loc_1800678A8
0x1800675b4  xor     r8d, r8d
0x1800675b7  lea     rdx, aAes; "AES"
0x1800675be  lea     rcx, [rsp+340h+P]
0x1800675c3  call    MSCryptOpenSymmetricProvider
0x1800675c8  mov     ebx, eax
0x1800675ca  test    eax, eax
0x1800675cc  jns     short loc_1800675F3
0x1800675ce  mov     r9d, 2C3h
0x1800675d4  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800675db  lea     rdx, aStatus; "Status"
0x1800675e2  mov     ecx, eax
0x1800675e4  call    DebugTraceError
0x1800675e9  mov     r13, [rsp+340h+P]
0x1800675ee  jmp     loc_180067891
0x1800675f3  mov     eax, dword ptr [rsp+340h+var_2E8]
0x1800675f7  lea     r8, [rbp+240h+var_290]; int
0x1800675fb  mov     [rsp+340h+var_310], r13d; int
0x180067600  lea     rdx, [rsp+340h+var_2D0]; int
0x180067605  mov     r13, [rsp+340h+P]
0x18006760a  mov     r14d, 250h
0x180067610  mov     dword ptr [rsp+340h+var_318], eax; Size
0x180067614  mov     rcx, r13; int
0x180067617  mov     r9d, r14d; int
0x18006761a  mov     [rsp+340h+Src], rsi; Src
0x18006761f  call    MSCryptGenerateSymmetricKey
0x180067624  mov     ebx, eax
0x180067626  test    eax, eax
0x180067628  jns     short loc_18006764F
0x18006762a  mov     r9d, 2D0h
0x180067630  mov     ecx, eax
0x180067632  lea     rdx, aStatus; "Status"
0x180067639  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180067640  call    DebugTraceError
0x180067645  mov     r12, qword ptr [rsp+340h+var_2D0]
0x18006764a  jmp     loc_180067874
0x18006764f  mov     eax, dword ptr [rsp+340h+Size+4]
0x180067653  mov     edi, [rdi+4]
0x180067656  cmp     edi, eax
0x180067658  jb      loc_180067834
0x18006765e  sub     edi, eax
0x180067660  lea     r8, [rsp+340h+Size]
0x180067665  add     rax, r12
0x180067668  mov     dword ptr [rsp+340h+Src], edi
0x18006766c  mov     r12, qword ptr [rsp+340h+var_2D0]
0x180067671  mov     r9, rax
0x180067674  mov     rcx, r12
0x180067677  mov     [rsp+340h+P], rax
0x18006767c  xor     edx, edx
0x18006767e  call    MSCryptAesKeyUnwrapPad
0x180067683  mov     ebx, eax
0x180067685  test    eax, eax
0x180067687  jns     short loc_1800676A9
0x180067689  mov     r9d, 2E3h
0x18006768f  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180067696  lea     rdx, aStatus; "Status"
0x18006769d  mov     ecx, eax
0x18006769f  call    DebugTraceError
0x1800676a4  jmp     loc_180067874
0x1800676a9  mov     ecx, dword ptr [rsp+340h+Size]
0x1800676ad  call    SafeAllocaAllocateFromHeap
0x1800676b2  mov     r14, rax
0x1800676b5  test    rax, rax
0x1800676b8  jnz     short loc_1800676CF
0x1800676ba  mov     ebx, 0C0000017h
0x1800676bf  mov     r9d, 2EAh
0x1800676c5  mov     ecx, 0C0000017h
0x1800676ca  jmp     loc_18006785B
0x1800676cf  mov     r9, [rsp+340h+P]
0x1800676d4  lea     r8, [rsp+340h+Size]
0x1800676d9  mov     rdx, r14
0x1800676dc  mov     dword ptr [rsp+340h+Src], edi
0x1800676e0  mov     rcx, r12
0x1800676e3  call    MSCryptAesKeyUnwrapPad
0x1800676e8  mov     edi, dword ptr [rsp+340h+Size]
0x1800676ec  mov     ebx, eax
0x1800676ee  test    eax, eax
0x1800676f0  jns     short loc_180067712
0x1800676f2  mov     r9d, 2F5h
0x1800676f8  mov     ecx, eax
0x1800676fa  lea     rdx, aStatus; "Status"
0x180067701  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180067708  call    DebugTraceError
0x18006770d  jmp     loc_180067814
0x180067712  mov     rcx, [rbp+240h+var_2C0]
0x180067716  mov     eax, [rcx+8]
0x180067719  and     eax, 0FFFF0000h
0x18006771e  cmp     eax, 30000h
0x180067723  jnz     short loc_1800677A2
0x180067725  movzx   ecx, word ptr [rcx+8]
0x180067729  mov     dword ptr [rsp+340h+Size], 0
0x180067731  lea     eax, [rcx-4]
0x180067734  cmp     eax, 2
0x180067737  jbe     short loc_180067743
0x180067739  cmp     ecx, 0Bh
0x18006773c  mov     ecx, 3
0x180067741  jnz     short loc_180067748
0x180067743  mov     ecx, 5
0x180067748  mov     r8, [rsp+340h+var_2D8]
0x18006774d  lea     rax, [rsp+340h+Size]
0x180067752  mov     [rsp+340h+var_318], rax
0x180067757  mov     r9, r14
0x18006775a  mov     rdx, r15
0x18006775d  mov     dword ptr [rsp+340h+Src], edi
0x180067761  call    Pkcs8ConvertToKeyBlob
0x180067766  mov     ebx, eax
0x180067768  test    eax, eax
0x18006776a  jns     short loc_180067774
0x18006776c  mov     r9d, 30Bh
0x180067772  jmp     short loc_1800676F8
0x180067774  mov     eax, dword ptr [rsp+340h+Size]
0x180067778  test    eax, eax
0x18006777a  jz      loc_180067814
0x180067780  mov     rcx, [rbp+240h+var_2C0]
0x180067784  cmp     eax, [rcx+8]
0x180067787  jz      loc_180067814
0x18006778d  mov     ebx, 0C000090Bh
0x180067792  mov     r9d, 313h
0x180067798  mov     ecx, 0C000090Bh
0x18006779d  jmp     loc_1800676FA
0x1800677a2  mov     rax, [rbp+240h+var_2A0]
0x1800677a6  lea     r15d, [rdi+0Ch]
0x1800677aa  test    rax, rax
0x1800677ad  jz      short loc_18006780C
0x1800677af  cmp     edi, 0C80h
0x1800677b5  jbe     short loc_1800677CC
0x1800677b7  mov     ebx, 0C0000157h
0x1800677bc  mov     r9d, 325h
0x1800677c2  mov     ecx, 0C0000157h
0x1800677c7  jmp     loc_1800676FA
0x1800677cc  mov     rcx, [rsp+340h+var_2D8]
0x1800677d1  cmp     [rcx], edi
0x1800677d3  jnb     short loc_1800677ED
0x1800677d5  mov     [rcx], r15d
0x1800677d8  mov     ebx, 80090028h
0x1800677dd  mov     ecx, 80090028h
0x1800677e2  mov     r9d, 32Ch
0x1800677e8  jmp     loc_1800676FA
0x1800677ed  mov     r8, rdi; Size
0x1800677f0  mov     dword ptr [rax], 4D42444Bh
0x1800677f6  lea     rcx, [rax+0Ch]; void *
0x1800677fa  mov     dword ptr [rax+4], 1
0x180067801  mov     rdx, r14; Src
0x180067804  mov     [rax+8], edi
0x180067807  call    memcpy_0
0x18006780c  mov     rax, [rsp+340h+var_2D8]
0x180067811  mov     [rax], r15d
0x180067814  mov     rcx, rdi
0x180067817  mov     rax, r14
  ... truncated ...
```
