# GenerateSIDKey(uchar * const,ulong,_KEK_KEY_INFO *,_SID_KEY_BLOB_VER,uchar * *,ulong *,uchar *,ulong)

- ea: `0x180018c7c`
- end: `0x1800190ac`
- name: `?GenerateSIDKey@@YAJQEAEKPEAU_KEK_KEY_INFO@@W4_SID_KEY_BLOB_VER@@PEAPEAEPEAKPEAEK@Z`
- size: `1072`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, int, _QWORD *, unsigned int *, __int64)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180009408`
- `0x1800196cc`
- `0x180019bec`

## callees

- `0x180001630`
- `0x18000d6a0`
- `0x180010920`
- `0x180010950`
- `0x180018298`
- `0x1800189b8`
- `0x180018b88`
- `0x180018c7c`
- `0x1800190b4`
- `0x18001a214`
- `0x18001a450`
- `0x18001a6ac`

## string_xrefs

- `0x180018d58`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x180018dc1`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x180018e29`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x180018f5e`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`

## pseudocode

```c
__int64 __fastcall GenerateSIDKey(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        _QWORD *a5,
        unsigned int *a6,
        __int64 a7)
{
  void *v9; // r15
  int SpecifiedSecretAgreementSecret; // eax
  unsigned int v11; // edi
  unsigned int v12; // r9d
  unsigned int v13; // ecx
  __int64 v14; // rax
  bool v15; // zf
  signed int LatestSecretAgreementSecret; // eax
  unsigned int v17; // r13d
  _OWORD *v18; // rax
  _OWORD *v19; // r14
  BYTE *v20; // r8
  DWORD v21; // edx
  HRESULT DerivedKey; // eax
  char *v23; // rbx
  __int64 v24; // r9
  BYTE *pNonce; // [rsp+20h] [rbp-E0h]
  PBYTE *ppKey; // [rsp+48h] [rbp-B8h]
  size_t Size; // [rsp+70h] [rbp-90h] BYREF
  int v29; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v30; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v31; // [rsp+80h] [rbp-80h] BYREF
  int v32; // [rsp+84h] [rbp-7Ch]
  void *Src; // [rsp+88h] [rbp-78h]
  unsigned __int8 *v34; // [rsp+90h] [rbp-70h] BYREF
  _QWORD *v35; // [rsp+98h] [rbp-68h]
  __int64 v36; // [rsp+A0h] [rbp-60h]
  unsigned int *v37; // [rsp+A8h] [rbp-58h]
  __int128 v38; // [rsp+B0h] [rbp-50h]
  __int128 v39; // [rsp+C0h] [rbp-40h]
  unsigned __int8 cbNonce[64]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int8 v41[64]; // [rsp+110h] [rbp+10h] BYREF

  v35 = a5;
  v37 = a6;
  v9 = 0;
  v32 = a4;
  v29 = 0;
  v34 = 0;
  Src = 0;
  HIDWORD(Size) = 0;
  v31 = 0;
  v30 = 0;
  v38 = 0;
  v39 = 0;
  SpecifiedSecretAgreementSecret = ParseSidKeyResult(
                                     (const struct _SID_KEY_HEADER *)a1,
                                     a2,
                                     (struct _KEK_KEY_INFO *)a3,
                                     v41,
                                     &v29,
                                     &v31,
                                     cbNonce,
                                     (int *)&Size + 1,
                                     &v30,
                                     &v34);
  v11 = SpecifiedSecretAgreementSecret;
  if ( SpecifiedSecretAgreementSecret < 0 )
  {
    v12 = 948;
LABEL_3:
    v13 = SpecifiedSecretAgreementSecret;
LABEL_4:
    SidKeyDebugTraceError(v13, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx", v12);
    return v11;
  }
  v14 = *(unsigned int *)(a1 + 40) + 80LL + a1 + *(unsigned int *)(a1 + 44);
  v15 = (*(_BYTE *)(a1 + 8) & 1) == 0;
  v36 = v14;
  if ( v15 )
  {
    if ( v29 > 0 || SHIDWORD(Size) > 0 )
    {
      SpecifiedSecretAgreementSecret = ClientComputeL2Key(
                                         (struct _SID_KEY_HEADER *)a1,
                                         (struct _KEK_KEY_INFO *)a3,
                                         (unsigned __int16 *)(a1 + 80),
                                         v41,
                                         cbNonce,
                                         v29,
                                         v31,
                                         SHIDWORD(Size),
                                         v30);
      v11 = SpecifiedSecretAgreementSecret;
      if ( SpecifiedSecretAgreementSecret < 0 )
      {
        v12 = 1000;
        goto LABEL_3;
      }
      v14 = v36;
    }
    if ( a3 )
    {
      if ( (*(_BYTE *)(a3 + 8) & 1) != 0 )
      {
        SpecifiedSecretAgreementSecret = GenerateSpecifiedSecretAgreementSecret(a1, a3, a1 + 80, v14, cbNonce, v32, a7);
        v11 = SpecifiedSecretAgreementSecret;
        if ( SpecifiedSecretAgreementSecret < 0 )
        {
          v12 = 1025;
          goto LABEL_3;
        }
      }
      else
      {
        v20 = (BYTE *)*(unsigned int *)(a1 + 44);
        v21 = 0;
        if ( (_DWORD)v20 )
          v21 = a1 + *(_DWORD *)(a1 + 40) + 80;
        LODWORD(ppKey) = 0;
        LODWORD(pNonce) = 64;
        DerivedKey = GenerateDerivedKey(
                       (PINFORMATIONCARD_CRYPTO_HANDLE)(a1 + 80),
                       v21,
                       v20,
                       (DWORD)cbNonce,
                       pNonce,
                       a3 + 52,
                       *(_DWORD *)(a3 + 40),
                       0,
                       0,
                       ppKey);
        v11 = DerivedKey;
        if ( DerivedKey < 0 )
        {
          SidKeyDebugTraceError(
            DerivedKey,
            "hr",
            "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
            0x37Eu);
          v12 = 1042;
          v13 = v11;
          goto LABEL_4;
        }
      }
    }
    else
    {
      SpecifiedSecretAgreementSecret = GenerateLatestSecretFromSidKey(a1, a1 + 80, cbNonce, a7);
      v11 = SpecifiedSecretAgreementSecret;
      if ( SpecifiedSecretAgreementSecret < 0 )
      {
        v12 = 1062;
        goto LABEL_3;
      }
    }
    goto LABEL_9;
  }
  LatestSecretAgreementSecret = GenerateLatestSecretAgreementSecret(a1, a1 + 80, v14, v34, a7);
  v11 = LatestSecretAgreementSecret;
  if ( LatestSecretAgreementSecret >= 0 )
  {
    v9 = Src;
LABEL_9:
    if ( v35 )
    {
      v17 = *(_DWORD *)(a1 + 72) + 32 + *(_DWORD *)(a1 + 76) + 52;
      v18 = SIDKeyProvAlloc(v17);
      v19 = v18;
      if ( v18 )
      {
        *v18 = *(_OWORD *)a1;
        v18[1] = *(_OWORD *)(a1 + 16);
        *((_QWORD *)v18 + 4) = *(_QWORD *)(a1 + 32);
        *((_DWORD *)v18 + 10) = 32;
        *(_OWORD *)((char *)v18 + 52) = v38;
        *(_OWORD *)((char *)v18 + 68) = v39;
        v23 = (char *)v18 + *((unsigned int *)v18 + 10) + 52;
        memcpy_0(
          v23,
          (const void *)(*(unsigned int *)(a1 + 40)
                       + 80LL
                       + a1
                       + *(unsigned int *)(a1 + 44)
                       + *(unsigned int *)(a1 + 48)
                       + (unsigned __int64)*(unsigned int *)(a1 + 52)),
          *(unsigned int *)(a1 + 72));
        v24 = *(unsigned int *)(a1 + 72);
        *((_DWORD *)v19 + 11) = v24;
        memcpy_0(
          &v23[v24],
          (const void *)(*(unsigned int *)(a1 + 40)
                       + 80LL
                       + *(unsigned int *)(a1 + 72)
                       + *(unsigned int *)(a1 + 48)
                       + (unsigned __int64)*(unsigned int *)(a1 + 52)
                       + a1
                       + *(unsigned int *)(a1 + 44)),
          *(unsigned int *)(a1 + 76));
        *((_DWORD *)v19 + 12) = *(_DWORD *)(a1 + 76);
        *v35 = v19;
        *v37 = v17;
      }
      else
      {
        v11 = -2147024882;
        SidKeyDebugTraceError(
          0x8007000E,
          "hr",
          "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
          0x43Cu);
      }
    }
    goto LABEL_28;
  }
  SidKeyDebugTraceError(
    LatestSecretAgreementSecret,
    "hr",
    "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
    0x3D3u);
  v9 = Src;
LABEL_28:
  if ( v9 )
    SIDKeyProvFree(v9);
  return v11;
}

```

## disassembly

```asm
0x180018c7c  mov     [rsp-8+arg_8], rbx
0x180018c81  push    rbp
0x180018c82  push    rsi
0x180018c83  push    rdi
0x180018c84  push    r12
0x180018c86  push    r13
0x180018c88  push    r14
0x180018c8a  push    r15
0x180018c8c  lea     rbp, [rsp-60h]
0x180018c91  sub     rsp, 160h
0x180018c98  mov     rax, cs:__security_cookie
0x180018c9f  xor     rax, rsp
0x180018ca2  mov     [rbp+90h+var_40], rax
0x180018ca6  mov     rax, [rbp+90h+arg_20]
0x180018cad  xor     r14d, r14d
0x180018cb0  mov     r13, [rbp+90h+arg_30]
0x180018cb7  xorps   xmm0, xmm0
0x180018cba  mov     [rbp+90h+var_F8], rax
0x180018cbe  mov     rbx, r8
0x180018cc1  mov     rax, [rbp+90h+arg_28]
0x180018cc8  mov     rsi, rcx
0x180018ccb  mov     [rbp+90h+var_E8], rax
0x180018ccf  mov     r15d, r14d
0x180018cd2  lea     rax, [rbp+90h+var_100]
0x180018cd6  mov     [rbp+90h+var_10C], r9d
0x180018cda  mov     [rsp+190h+ppKey], rax; unsigned __int8 **
0x180018cdf  lea     r9, [rbp+90h+var_80]; unsigned __int8 *
0x180018ce3  lea     rax, [rsp+190h+var_114]
0x180018ce8  mov     [rsp+190h+var_118], r14d
0x180018ced  mov     [rsp+190h+pcbKey], rax; unsigned int *
0x180018cf2  mov     r12d, r14d
0x180018cf5  lea     rax, [rsp+190h+Size+4]
0x180018cfa  mov     dword ptr [rsp+190h+Size+4], r14d
0x180018cff  mov     [rsp+190h+algId], rax; int *
0x180018d04  lea     rax, [rbp+90h+cbNonce]
0x180018d08  mov     qword ptr [rsp+190h+offset], rax; unsigned __int8 *
0x180018d0d  lea     rax, [rbp+90h+var_110]
0x180018d11  mov     qword ptr [rsp+190h+derivedKeyLength], rax; unsigned int *
0x180018d16  lea     rax, [rsp+190h+var_118]
0x180018d1b  mov     [rsp+190h+pNonce], rax; int *
0x180018d20  mov     [rbp+90h+var_100], r14
0x180018d24  mov     [rbp+90h+Src], r14
0x180018d28  mov     dword ptr [rsp+190h+Size], r14d
0x180018d2d  mov     [rbp+90h+var_110], r14d
0x180018d31  mov     [rsp+190h+var_114], r14d
0x180018d36  movups  [rbp+90h+var_E0], xmm0
0x180018d3a  movups  [rbp+90h+var_D0], xmm0
0x180018d3e  call    ?ParseSidKeyResult@@YAJPEBU_SID_KEY_HEADER@@KPEAU_KEK_KEY_INFO@@QEAEPEAJPEAK234PEAPEAE@Z; ParseSidKeyResult(_SID_KEY_HEADER const *,ulong,_KEK_KEY_INFO *,uchar * const,long *,ulong *,uchar * const,long *,ulong *,uchar * *)
0x180018d43  mov     edi, eax
0x180018d45  test    eax, eax
0x180018d47  jns     short loc_180018D69
0x180018d49  mov     r9d, 3B4h; unsigned int
0x180018d4f  mov     ecx, eax; unsigned int
0x180018d51  lea     rdx, aHr; "hr"
0x180018d58  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180018d5f  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180018d64  jmp     loc_180019083
0x180018d69  mov     eax, [rsi+2Ch]
0x180018d6c  lea     r14, [rsi+50h]
0x180018d70  mov     ecx, [rsi+28h]
0x180018d73  add     rax, rsi
0x180018d76  add     rcx, 50h ; 'P'
0x180018d7a  add     rax, rcx
0x180018d7d  test    byte ptr [rsi+8], 1
0x180018d81  mov     [rbp+90h+var_F0], rax
0x180018d85  jz      loc_180018E4B
0x180018d8b  mov     r9, [rbp+90h+var_100]
0x180018d8f  lea     rcx, [rsp+190h+Size]
0x180018d94  mov     [rsp+190h+algId], rcx
0x180018d99  mov     r8, rax
0x180018d9c  lea     rcx, [rbp+90h+Src]
0x180018da0  mov     rdx, r14
0x180018da3  mov     qword ptr [rsp+190h+offset], rcx
0x180018da8  mov     rcx, rsi
0x180018dab  mov     [rsp+190h+pNonce], r13
0x180018db0  call    GenerateLatestSecretAgreementSecret
0x180018db5  mov     edi, eax
0x180018db7  test    eax, eax
0x180018db9  jns     short loc_180018DDF
0x180018dbb  mov     r9d, 3D3h; unsigned int
0x180018dc1  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180018dc8  lea     rdx, aHr; "hr"
0x180018dcf  mov     ecx, eax; unsigned int
0x180018dd1  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180018dd6  mov     r15, [rbp+90h+Src]
0x180018dda  jmp     loc_180019076
0x180018ddf  mov     r15, [rbp+90h+Src]
0x180018de3  mov     r12d, dword ptr [rsp+190h+Size]
0x180018de8  cmp     [rbp+90h+var_F8], 0
0x180018ded  jz      loc_180019076
0x180018df3  mov     ecx, [rsi+48h]
0x180018df6  mov     eax, 20h ; ' '
0x180018dfb  mov     r13d, [rsi+4Ch]
0x180018dff  test    r12d, r12d
0x180018e02  cmovnz  eax, r12d
0x180018e06  add     r13d, 34h ; '4'
0x180018e0a  add     ecx, eax
0x180018e0c  add     r13d, ecx
0x180018e0f  mov     ecx, r13d; unsigned __int64
0x180018e12  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180018e17  mov     r14, rax
0x180018e1a  test    rax, rax
0x180018e1d  jnz     loc_180018FB0
0x180018e23  mov     r9d, 43Ch; unsigned int
0x180018e29  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180018e30  lea     rdx, aHr; "hr"
0x180018e37  mov     ecx, 8007000Eh; unsigned int
0x180018e3c  mov     edi, 8007000Eh
0x180018e41  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180018e46  jmp     loc_180019076
0x180018e4b  mov     edx, [rsp+190h+var_118]
0x180018e4f  mov     ecx, dword ptr [rsp+190h+Size+4]
0x180018e53  test    edx, edx
0x180018e55  jg      short loc_180018E5B
0x180018e57  test    ecx, ecx
0x180018e59  jle     short loc_180018EA2
0x180018e5b  mov     eax, [rsp+190h+var_114]
0x180018e5f  lea     r9, [rbp+90h+var_80]; unsigned __int8 *
0x180018e63  mov     dword ptr [rsp+190h+pcbKey], eax; unsigned int
0x180018e67  mov     r8, r14; unsigned __int16 *
0x180018e6a  mov     eax, [rbp+90h+var_110]
0x180018e6d  mov     dword ptr [rsp+190h+algId], ecx; int
0x180018e71  mov     rcx, rsi; struct _SID_KEY_HEADER *
0x180018e74  mov     [rsp+190h+offset], eax; unsigned int
0x180018e78  lea     rax, [rbp+90h+cbNonce]
0x180018e7c  mov     [rsp+190h+derivedKeyLength], edx; int
0x180018e80  mov     rdx, rbx; struct _KEK_KEY_INFO *
0x180018e83  mov     [rsp+190h+pNonce], rax; unsigned __int8 *
0x180018e88  call    ?ClientComputeL2Key@@YAJPEAU_SID_KEY_HEADER@@PEAU_KEK_KEY_INFO@@PEAGQEAE3JKJK@Z; ClientComputeL2Key(_SID_KEY_HEADER *,_KEK_KEY_INFO *,ushort *,uchar * const,uchar * const,long,ulong,long,ulong)
0x180018e8d  mov     edi, eax
0x180018e8f  test    eax, eax
0x180018e91  jns     short loc_180018E9E
0x180018e93  mov     r9d, 3E8h
0x180018e99  jmp     loc_180018D4F
0x180018e9e  mov     rax, [rbp+90h+var_F0]
0x180018ea2  test    rbx, rbx
0x180018ea5  jz      loc_180018F80
0x180018eab  test    byte ptr [rbx+8], 1
0x180018eaf  jz      short loc_180018EEC
0x180018eb1  mov     ecx, [rbp+90h+var_10C]
0x180018eb4  mov     r9, rax
0x180018eb7  mov     qword ptr [rsp+190h+offset], r13
0x180018ebc  mov     r8, r14
0x180018ebf  mov     [rsp+190h+derivedKeyLength], ecx
0x180018ec3  mov     rdx, rbx
0x180018ec6  lea     rcx, [rbp+90h+cbNonce]
0x180018eca  mov     [rsp+190h+pNonce], rcx
0x180018ecf  mov     rcx, rsi
0x180018ed2  call    GenerateSpecifiedSecretAgreementSecret
0x180018ed7  mov     edi, eax
0x180018ed9  test    eax, eax
0x180018edb  jns     loc_180018DE8
0x180018ee1  mov     r9d, 401h
0x180018ee7  jmp     loc_180018D4F
0x180018eec  mov     r8d, [rsi+2Ch]; pLabel
0x180018ef0  xor     edx, edx
0x180018ef2  mov     ecx, [rbx+28h]
0x180018ef5  test    r8d, r8d
0x180018ef8  jz      short loc_180018F04
0x180018efa  mov     edx, [rsi+28h]
0x180018efd  add     rdx, 50h ; 'P'
0x180018f01  add     rdx, rsi; cbLabel
0x180018f04  mov     [rsp+190h+var_128], r12
0x180018f09  lea     rax, [rbx+34h]
0x180018f0d  mov     [rsp+190h+var_130], 20h ; ' '
0x180018f15  lea     r9, [rbp+90h+cbNonce]; cbNonce
0x180018f19  mov     [rsp+190h+var_138], r13
0x180018f1e  mov     [rsp+190h+var_140], 1
0x180018f26  mov     dword ptr [rsp+190h+ppKey], r12d; ppKey
0x180018f2b  mov     [rsp+190h+pcbKey], r12; pcbKey
0x180018f30  mov     [rsp+190h+algId], r12; algId
0x180018f35  mov     [rsp+190h+offset], ecx; offset
0x180018f39  mov     rcx, r14; hCrypto
0x180018f3c  mov     qword ptr [rsp+190h+derivedKeyLength], rax; derivedKeyLength
0x180018f41  mov     dword ptr [rsp+190h+pNonce], 40h ; '@'; pNonce
0x180018f49  call    ?GenerateDerivedKey@@YAJPEBGPEAEK1K1KPEAK1KK1KPEAPEAG@Z; GenerateDerivedKey(ushort const *,uchar *,ulong,uchar *,ulong,uchar *,ulong,ulong *,uchar *,ulong,ulong,uchar *,ulong,ushort * *)
0x180018f4e  mov     edi, eax
0x180018f50  test    eax, eax
0x180018f52  jns     loc_180018DE8
0x180018f58  mov     r9d, 37Eh; unsigned int
0x180018f5e  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180018f65  lea     rdx, aHr; "hr"
0x180018f6c  mov     ecx, eax; unsigned int
0x180018f6e  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180018f73  mov     r9d, 412h
0x180018f79  mov     ecx, edi
0x180018f7b  jmp     loc_180018D51
0x180018f80  lea     rax, [rbp+90h+var_E0]
0x180018f84  mov     r9, r13
0x180018f87  lea     r8, [rbp+90h+cbNonce]
0x180018f8b  mov     qword ptr [rsp+190h+derivedKeyLength], rax
0x180018f90  mov     rdx, r14
0x180018f93  mov     rcx, rsi
0x180018f96  call    GenerateLatestSecretFromSidKey
0x180018f9b  mov     edi, eax
0x180018f9d  test    eax, eax
0x180018f9f  jns     loc_180018DE8
0x180018fa5  mov     r9d, 426h
0x180018fab  jmp     loc_180018D4F
0x180018fb0  lea     rbx, [rax+34h]
0x180018fb4  movups  xmm0, xmmword ptr [rsi]
0x180018fb7  movups  xmmword ptr [rax], xmm0
0x180018fba  movups  xmm1, xmmword ptr [rsi+10h]
0x180018fbe  movups  xmmword ptr [rax+10h], xmm1
0x180018fc2  movsd   xmm0, qword ptr [rsi+20h]
0x180018fc7  movsd   qword ptr [rax+20h], xmm0
0x180018fcc  test    r12d, r12d
0x180018fcf  jz      short loc_180018FE5
0x180018fd1  mov     r8d, r12d; Size
0x180018fd4  mov     rdx, r15; Src
0x180018fd7  mov     rcx, rbx; void *
0x180018fda  mov     [rax+28h], r12d
0x180018fde  call    memcpy_0
0x180018fe3  jmp     short loc_180018FFB
0x180018fe5  mov     dword ptr [rax+28h], 20h ; ' '
0x180018fec  movups  xmm0, [rbp+90h+var_E0]
0x180018ff0  movups  xmmword ptr [rbx], xmm0
0x180018ff3  movups  xmm1, [rbp+90h+var_D0]
0x180018ff7  movups  xmmword ptr [rbx+10h], xmm1
0x180018ffb  mov     eax, [r14+28h]
0x180018fff  mov     edx, [rsi+34h]
0x180019002  add     rbx, rax
0x180019005  mov     eax, [rsi+30h]
0x180019008  mov     ecx, [rsi+2Ch]
0x18001900b  add     rdx, rax
0x18001900e  mov     eax, [rsi+28h]
0x180019011  add     rcx, rsi
0x180019014  mov     r8d, [rsi+48h]; Size
0x180019018  add     rdx, rcx
0x18001901b  add     rax, 50h ; 'P'
0x18001901f  mov     rcx, rbx; void *
0x180019022  add     rdx, rax; Src
0x180019025  call    memcpy_0
0x18001902a  mov     r9d, [rsi+48h]
0x18001902e  mov     [r14+2Ch], r9d
0x180019032  mov     eax, [rsi+30h]
0x180019035  mov     ecx, [rsi+34h]
0x180019038  mov     edx, [rsi+2Ch]
0x18001903b  add     rcx, rax
0x18001903e  mov     eax, [rsi+48h]
0x180019041  add     rdx, rsi
0x180019044  mov     r8d, [rsi+4Ch]; Size
0x180019048  add     rcx, rax
0x18001904b  mov     eax, [rsi+28h]
0x18001904e  add     rdx, rcx
0x180019051  add     rax, 50h ; 'P'
0x180019055  lea     rcx, [rbx+r9]; void *
0x180019059  add     rdx, rax; Src
0x18001905c  call    memcpy_0
0x180019061  mov     eax, [rsi+4Ch]
0x180019064  mov     [r14+30h], eax
0x180019068  mov     rax, [rbp+90h+var_F8]
0x18001906c  mov     [rax], r14
0x18001906f  mov     rax, [rbp+90h+var_E8]
0x180019073  mov     [rax], r13d
0x180019076  test    r15, r15
0x180019079  jz      short loc_180019083
0x18001907b  mov     rcx, r15; lpMem
0x18001907e  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180019083  mov     eax, edi
0x180019085  mov     rcx, [rbp+90h+var_40]
0x180019089  xor     rcx, rsp; StackCookie
0x18001908c  call    __security_check_cookie
0x180019091  mov     rbx, [rsp+190h+arg_8]
0x180019099  add     rsp, 160h
0x1800190a0  pop     r15
0x1800190a2  pop     r14
0x1800190a4  pop     r13
0x1800190a6  pop     r12
0x1800190a8  pop     rdi
0x1800190a9  pop     rsi
0x1800190aa  pop     rbp
0x1800190ab  retn
```
