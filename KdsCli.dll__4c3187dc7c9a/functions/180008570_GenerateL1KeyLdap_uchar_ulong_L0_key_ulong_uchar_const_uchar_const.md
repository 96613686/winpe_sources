# GenerateL1KeyLdap(uchar *,ulong,_L0_key *,ulong,uchar * const,uchar * const)

- ea: `0x180008570`
- end: `0x180008848`
- name: `?GenerateL1KeyLdap@@YAJPEAEKPEAU_L0_key@@KQEAE2@Z`
- size: `728`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, struct _L0_key *, unsigned int, unsigned __int8 *const, unsigned __int8 *const)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007e98`

## callees

- `0x180001630`
- `0x180008570`
- `0x18000d6a0`
- `0x18000d9d0`
- `0x180010920`
- `0x180010950`
- `0x18001a450`
- `0x18001a6ac`

## string_xrefs

- `0x180008646`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`
- `0x1800087fc`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`

## pseudocode

```c
__int64 __fastcall GenerateL1KeyLdap(
        unsigned __int8 *a1,
        unsigned int a2,
        struct _L0_key *a3,
        int a4,
        unsigned __int8 *const a5,
        unsigned __int8 *const a6)
{
  struct _GUID v6; // xmm0
  char *derivedKeyLength; // r12
  unsigned int v10; // edx
  HRESULT DerivedKey; // eax
  char *v12; // rsi
  unsigned int v13; // ebx
  unsigned int v14; // r9d
  char *v15; // r13
  int v16; // r15d
  size_t offset; // r14
  char *v18; // rax
  unsigned int v19; // ecx
  DWORD v20; // r9d
  BYTE *pNonce; // [rsp+20h] [rbp-C9h]
  BYTE *pNoncea; // [rsp+20h] [rbp-C9h]
  PBYTE *ppKey; // [rsp+48h] [rbp-A1h]
  PBYTE *ppKeya; // [rsp+48h] [rbp-A1h]
  WCHAR algId[2]; // [rsp+70h] [rbp-79h] BYREF
  size_t Size; // [rsp+74h] [rbp-75h] BYREF
  int v28; // [rsp+7Ch] [rbp-6Dh]
  DWORD cbNonce[2]; // [rsp+80h] [rbp-69h]
  void *Src; // [rsp+88h] [rbp-61h] BYREF
  void *v31; // [rsp+90h] [rbp-59h]
  unsigned __int8 *v32; // [rsp+98h] [rbp-51h]
  struct _GUID v33; // [rsp+A0h] [rbp-49h] BYREF
  char v34; // [rsp+B0h] [rbp-39h] BYREF

  v6 = *(struct _GUID *)((char *)a3 + 12);
  *(_QWORD *)cbNonce = a5;
  v32 = a6;
  derivedKeyLength = 0;
  v28 = a4;
  Size = a2;
  v10 = *(_DWORD *)a3;
  v31 = a1;
  Src = 0;
  *(_DWORD *)algId = 0;
  v33 = v6;
  DerivedKey = GenerateKDFContext(
                 &v33,
                 v10,
                 31,
                 -1,
                 1u,
                 (unsigned __int8 **)&Src,
                 (unsigned int *)&Size + 1,
                 (unsigned int *)algId);
  v12 = (char *)Src;
  v13 = DerivedKey;
  if ( DerivedKey < 0 )
  {
    v14 = 714;
LABEL_17:
    v19 = DerivedKey;
    goto LABEL_18;
  }
  v15 = &v34;
  v16 = 31 - a4;
  offset = HIDWORD(Size);
  if ( !v16 )
    LODWORD(v15) = cbNonce[0];
  if ( (unsigned int)(HIDWORD(Size) + Size) >= HIDWORD(Size) )
  {
    v18 = (char *)SIDKeyProvAlloc((unsigned int)(HIDWORD(Size) + Size));
    derivedKeyLength = v18;
    if ( !v18 )
    {
      v13 = -2147024882;
      v14 = 743;
      v19 = -2147024882;
LABEL_18:
      SidKeyDebugTraceError(v19, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", v14);
      goto LABEL_19;
    }
    memcpy_0(v18, v12, offset);
    memcpy_0(&derivedKeyLength[offset], v31, (unsigned int)Size);
    LODWORD(ppKey) = 0;
    LODWORD(pNonce) = 64;
    DerivedKey = GenerateDerivedKey(
                   *((PINFORMATIONCARD_CRYPTO_HANDLE *)a3 + 5),
                   *((_QWORD *)a3 + 6),
                   (PBYTE)*((unsigned int *)a3 + 14),
                   (_DWORD)a3 + 176,
                   pNonce,
                   (DWORD)derivedKeyLength,
                   offset + Size,
                   algId,
                   0,
                   ppKey);
    v13 = DerivedKey;
    if ( DerivedKey < 0 )
    {
      v14 = 766;
      goto LABEL_17;
    }
    if ( v16 )
    {
      --*(_DWORD *)&v12[*(unsigned int *)algId];
      LODWORD(ppKeya) = 0;
      LODWORD(pNoncea) = 64;
      DerivedKey = GenerateDerivedKey(
                     *((PINFORMATIONCARD_CRYPTO_HANDLE *)a3 + 5),
                     *((_QWORD *)a3 + 6),
                     (PBYTE)*((unsigned int *)a3 + 14),
                     (DWORD)v15,
                     pNoncea,
                     (DWORD)v12,
                     offset,
                     algId,
                     0,
                     ppKeya);
      v13 = DerivedKey;
      if ( DerivedKey < 0 )
      {
        v14 = 793;
        goto LABEL_17;
      }
    }
    if ( v28 )
    {
      v20 = cbNonce[0];
      *(_DWORD *)&v12[*(unsigned int *)algId] = v28 - 1;
      LODWORD(ppKeya) = 0;
      LODWORD(pNoncea) = 64;
      DerivedKey = GenerateDerivedKey(
                     *((PINFORMATIONCARD_CRYPTO_HANDLE *)a3 + 5),
                     *((_QWORD *)a3 + 6),
                     (PBYTE)*((unsigned int *)a3 + 14),
                     v20,
                     pNoncea,
                     (DWORD)v12,
                     offset,
                     algId,
                     0,
                     ppKeya);
      v13 = DerivedKey;
      if ( DerivedKey < 0 )
      {
        v14 = 821;
        goto LABEL_17;
      }
    }
  }
  else
  {
    SidKeyDebugTraceError(0x80070216, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", 0x2DEu);
    v13 = -2147024809;
  }
LABEL_19:
  SIDKeyProvFree(derivedKeyLength);
  SIDKeyProvFree(v12);
  return v13;
}

```

## disassembly

```asm
0x180008570  mov     [rsp-8+arg_18], rbx
0x180008575  push    rbp
0x180008576  push    rsi
0x180008577  push    rdi
0x180008578  push    r12
0x18000857a  push    r13
0x18000857c  push    r14
0x18000857e  push    r15
0x180008580  lea     rbp, [rsp-17h]
0x180008585  sub     rsp, 100h
0x18000858c  mov     rax, cs:__security_cookie
0x180008593  xor     rax, rsp
0x180008596  mov     [rbp+47h+var_40], rax
0x18000859a  movups  xmm0, xmmword ptr [r8+0Ch]
0x18000859f  mov     rax, [rbp+47h+arg_20]
0x1800085a3  xor     r13d, r13d
0x1800085a6  mov     qword ptr [rbp+47h+cbNonce], rax
0x1800085aa  mov     rdi, r8
0x1800085ad  mov     rax, [rbp+47h+arg_28]
0x1800085b1  mov     r14d, r9d
0x1800085b4  mov     [rbp+47h+var_98], rax
0x1800085b8  mov     r12d, r13d
0x1800085bb  lea     rax, [rbp+47h+var_C0]
0x1800085bf  mov     [rbp+47h+var_B4], r9d
0x1800085c3  mov     [rsp+130h+algId], rax; unsigned int *
0x1800085c8  lea     r15d, [r13+1Fh]
0x1800085cc  lea     rax, [rbp+47h+Size+4]
0x1800085d0  mov     dword ptr [rbp+47h+Size], edx
0x1800085d3  mov     edx, [rdi]; unsigned int
0x1800085d5  or      r9d, 0FFFFFFFFh; int
0x1800085d9  mov     qword ptr [rsp+130h+offset], rax; unsigned int *
0x1800085de  mov     r8d, r15d; int
0x1800085e1  lea     rax, [rbp+47h+Src]
0x1800085e5  mov     [rbp+47h+var_A0], rcx
0x1800085e9  mov     qword ptr [rsp+130h+derivedKeyLength], rax; unsigned __int8 **
0x1800085ee  lea     rcx, [rbp+47h+var_90]; struct _GUID *
0x1800085f2  mov     dword ptr [rsp+130h+pNonce], 1; unsigned int
0x1800085fa  mov     [rbp+47h+Src], r13
0x1800085fe  mov     dword ptr [rbp+47h+Size+4], r13d
0x180008602  mov     dword ptr [rbp+47h+var_C0], r13d
0x180008606  movdqu  xmmword ptr [rbp+47h+var_90.Data1], xmm0
0x18000860b  call    ?GenerateKDFContext@@YAJU_GUID@@KJJKPEAPEAEPEAK2@Z; GenerateKDFContext(_GUID,ulong,long,long,ulong,uchar * *,ulong *,ulong *)
0x180008610  mov     rsi, [rbp+47h+Src]
0x180008614  mov     ebx, eax
0x180008616  test    eax, eax
0x180008618  jns     short loc_180008625
0x18000861a  mov     r9d, 2CAh
0x180008620  jmp     loc_1800087FA
0x180008625  mov     eax, dword ptr [rbp+47h+Size]
0x180008628  lea     r13, [rbp+47h+var_80]
0x18000862c  sub     r15d, r14d
0x18000862f  mov     r14d, dword ptr [rbp+47h+Size+4]
0x180008633  cmovz   r13, qword ptr [rbp+47h+cbNonce]
0x180008638  add     eax, r14d
0x18000863b  cmp     eax, r14d
0x18000863e  jnb     short loc_180008668
0x180008640  mov     r9d, 2DEh; unsigned int
0x180008646  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000864d  lea     rdx, aHr; "hr"
0x180008654  mov     ecx, 80070216h; unsigned int
0x180008659  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000865e  mov     ebx, 80070057h
0x180008663  jmp     loc_18000880F
0x180008668  mov     ecx, eax; unsigned __int64
0x18000866a  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000866f  mov     r12, rax
0x180008672  test    rax, rax
0x180008675  jnz     short loc_18000868C
0x180008677  mov     ebx, 8007000Eh
0x18000867c  mov     r9d, 2E7h
0x180008682  mov     ecx, 8007000Eh
0x180008687  jmp     loc_1800087FC
0x18000868c  mov     r8, r14; Size
0x18000868f  mov     rdx, rsi; Src
0x180008692  mov     rcx, r12; void *
0x180008695  call    memcpy_0
0x18000869a  mov     r8d, dword ptr [rbp+47h+Size]; Size
0x18000869e  lea     rcx, [r14+r12]; void *
0x1800086a2  mov     rdx, [rbp+47h+var_A0]; Src
0x1800086a6  call    memcpy_0
0x1800086ab  mov     r8d, [rdi+38h]; pLabel
0x1800086af  lea     r9, [rdi+0B0h]; cbNonce
0x1800086b6  mov     rcx, [rdi+28h]; hCrypto
0x1800086ba  xor     eax, eax
0x1800086bc  mov     [rsp+130h+var_C8], rax
0x1800086c1  lea     edx, [rax+40h]
0x1800086c4  mov     [rsp+130h+var_D0], edx
0x1800086c8  mov     [rsp+130h+var_D8], r13
0x1800086cd  mov     [rsp+130h+var_E0], 1
0x1800086d5  mov     dword ptr [rsp+130h+ppKey], eax; ppKey
0x1800086d9  mov     [rsp+130h+pcbKey], rax; pcbKey
0x1800086de  lea     rax, [rbp+47h+var_C0]
0x1800086e2  mov     [rsp+130h+algId], rax; algId
0x1800086e7  mov     eax, dword ptr [rbp+47h+Size]
0x1800086ea  add     eax, r14d
0x1800086ed  mov     [rsp+130h+offset], eax; offset
0x1800086f1  mov     qword ptr [rsp+130h+derivedKeyLength], r12; derivedKeyLength
0x1800086f6  mov     dword ptr [rsp+130h+pNonce], edx; pNonce
0x1800086fa  mov     rdx, [rdi+30h]; cbLabel
0x1800086fe  call    ?GenerateDerivedKey@@YAJPEBGPEAEK1K1KPEAK1KK1KPEAPEAG@Z; GenerateDerivedKey(ushort const *,uchar *,ulong,uchar *,ulong,uchar *,ulong,ulong *,uchar *,ulong,ulong,uchar *,ulong,ushort * *)
0x180008703  xor     edx, edx
0x180008705  mov     ebx, eax
0x180008707  test    eax, eax
0x180008709  jns     short loc_180008716
0x18000870b  mov     r9d, 2FEh
0x180008711  jmp     loc_1800087FA
0x180008716  test    r15d, r15d
0x180008719  jz      short loc_180008784
0x18000871b  mov     eax, dword ptr [rbp+47h+var_C0]
0x18000871e  mov     r9, r13; cbNonce
0x180008721  mov     [rsp+130h+var_C8], rdx
0x180008726  mov     [rsp+130h+var_D0], 40h ; '@'
0x18000872e  dec     dword ptr [rax+rsi]
0x180008731  mov     rax, qword ptr [rbp+47h+cbNonce]
0x180008735  mov     r8d, [rdi+38h]; pLabel
0x180008739  mov     rcx, [rdi+28h]; hCrypto
0x18000873d  mov     [rsp+130h+var_D8], rax
0x180008742  lea     rax, [rbp+47h+var_C0]
0x180008746  mov     [rsp+130h+var_E0], r15d
0x18000874b  mov     dword ptr [rsp+130h+ppKey], edx; ppKey
0x18000874f  mov     [rsp+130h+pcbKey], rdx; pcbKey
0x180008754  mov     rdx, [rdi+30h]; cbLabel
0x180008758  mov     [rsp+130h+algId], rax; algId
0x18000875d  mov     [rsp+130h+offset], r14d; offset
0x180008762  mov     qword ptr [rsp+130h+derivedKeyLength], rsi; derivedKeyLength
0x180008767  mov     dword ptr [rsp+130h+pNonce], 40h ; '@'; pNonce
0x18000876f  call    ?GenerateDerivedKey@@YAJPEBGPEAEK1K1KPEAK1KK1KPEAPEAG@Z; GenerateDerivedKey(ushort const *,uchar *,ulong,uchar *,ulong,uchar *,ulong,ulong *,uchar *,ulong,ulong,uchar *,ulong,ushort * *)
0x180008774  xor     edx, edx
0x180008776  mov     ebx, eax
0x180008778  test    eax, eax
0x18000877a  jns     short loc_180008784
0x18000877c  mov     r9d, 319h
0x180008782  jmp     short loc_1800087FA
0x180008784  mov     ecx, [rbp+47h+var_B4]
0x180008787  test    ecx, ecx
0x180008789  jz      loc_18000880F
0x18000878f  mov     eax, dword ptr [rbp+47h+var_C0]
0x180008792  dec     ecx
0x180008794  mov     r9, qword ptr [rbp+47h+cbNonce]; cbNonce
0x180008798  mov     [rsp+130h+var_C8], rdx
0x18000879d  mov     [rsp+130h+var_D0], 40h ; '@'
0x1800087a5  mov     [rax+rsi], ecx
0x1800087a8  mov     rax, [rbp+47h+var_98]
0x1800087ac  mov     r8d, [rdi+38h]; pLabel
0x1800087b0  mov     rcx, [rdi+28h]; hCrypto
0x1800087b4  mov     [rsp+130h+var_D8], rax
0x1800087b9  lea     rax, [rbp+47h+var_C0]
0x1800087bd  mov     [rsp+130h+var_E0], 1
0x1800087c5  mov     dword ptr [rsp+130h+ppKey], edx; ppKey
0x1800087c9  mov     [rsp+130h+pcbKey], rdx; pcbKey
0x1800087ce  mov     rdx, [rdi+30h]; cbLabel
0x1800087d2  mov     [rsp+130h+algId], rax; algId
0x1800087d7  mov     [rsp+130h+offset], r14d; offset
0x1800087dc  mov     qword ptr [rsp+130h+derivedKeyLength], rsi; derivedKeyLength
0x1800087e1  mov     dword ptr [rsp+130h+pNonce], 40h ; '@'; pNonce
0x1800087e9  call    ?GenerateDerivedKey@@YAJPEBGPEAEK1K1KPEAK1KK1KPEAPEAG@Z; GenerateDerivedKey(ushort const *,uchar *,ulong,uchar *,ulong,uchar *,ulong,ulong *,uchar *,ulong,ulong,uchar *,ulong,ushort * *)
0x1800087ee  mov     ebx, eax
0x1800087f0  test    eax, eax
0x1800087f2  jns     short loc_18000880F
0x1800087f4  mov     r9d, 335h; unsigned int
0x1800087fa  mov     ecx, eax; unsigned int
0x1800087fc  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180008803  lea     rdx, aHr; "hr"
0x18000880a  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000880f  mov     rcx, r12; lpMem
0x180008812  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180008817  mov     rcx, rsi; lpMem
0x18000881a  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000881f  mov     eax, ebx
0x180008821  mov     rcx, [rbp+47h+var_40]
0x180008825  xor     rcx, rsp; StackCookie
0x180008828  call    __security_check_cookie
0x18000882d  mov     rbx, [rsp+130h+arg_18]
0x180008835  add     rsp, 100h
0x18000883c  pop     r15
0x18000883e  pop     r14
0x180008840  pop     r13
0x180008842  pop     r12
0x180008844  pop     rdi
0x180008845  pop     rsi
0x180008846  pop     rbp
0x180008847  retn
```
