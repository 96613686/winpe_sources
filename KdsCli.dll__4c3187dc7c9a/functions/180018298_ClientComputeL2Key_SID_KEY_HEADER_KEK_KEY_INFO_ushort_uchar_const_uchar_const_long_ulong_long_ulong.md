# ClientComputeL2Key(_SID_KEY_HEADER *,_KEK_KEY_INFO *,ushort *,uchar * const,uchar * const,long,ulong,long,ulong)

- ea: `0x180018298`
- end: `0x180018517`
- name: `?ClientComputeL2Key@@YAJPEAU_SID_KEY_HEADER@@PEAU_KEK_KEY_INFO@@PEAGQEAE3JKJK@Z`
- size: `639`
- prototype: `int(struct _SID_KEY_HEADER *, struct _KEK_KEY_INFO *, unsigned __int16 *, unsigned __int8 *const, unsigned __int8 *const, int, unsigned int, int, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016b30`
- `0x180018c7c`

## callees

- `0x18000d6a0`
- `0x18000d9d0`
- `0x180010950`
- `0x180018298`
- `0x18001a450`

## string_xrefs

- `0x180018351`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x18001844e`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`
- `0x1800184cb`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyrpcclient.cxx`

## pseudocode

```c
__int64 __fastcall ClientComputeL2Key(
        struct _SID_KEY_HEADER *a1,
        struct _KEK_KEY_INFO *a2,
        struct _INFORMATIONCARD_CRYPTO_HANDLE *a3,
        unsigned __int8 *const a4,
        unsigned __int8 *const a5,
        int a6,
        unsigned int a7,
        int a8,
        unsigned int a9)
{
  int v9; // eax
  unsigned int v10; // ebx
  void *v11; // r14
  void *v12; // rsi
  DWORD v13; // r12d
  unsigned int v16; // edx
  signed int v17; // eax
  HRESULT DerivedKey; // eax
  unsigned int v19; // r9d
  unsigned int v20; // edx
  int v21; // r8d
  signed int v22; // eax
  BYTE *pNonce; // [rsp+20h] [rbp-89h]
  BYTE *pNoncea; // [rsp+20h] [rbp-89h]
  PBYTE *ppKey; // [rsp+48h] [rbp-61h]
  DWORD offset; // [rsp+70h] [rbp-39h] BYREF
  DWORD v28; // [rsp+74h] [rbp-35h] BYREF
  PBYTE pLabel; // [rsp+78h] [rbp-31h]
  DWORD derivedKeyLength[2]; // [rsp+80h] [rbp-29h] BYREF
  DWORD v31[2]; // [rsp+88h] [rbp-21h] BYREF
  DWORD cbLabel[4]; // [rsp+90h] [rbp-19h]
  struct _GUID v33; // [rsp+A0h] [rbp-9h] BYREF
  unsigned int algId; // [rsp+F0h] [rbp+47h] BYREF
  PINFORMATIONCARD_CRYPTO_HANDLE hCrypto; // [rsp+100h] [rbp+57h]

  hCrypto = a3;
  v9 = *((_DWORD *)a1 + 11);
  v10 = 0;
  v11 = 0;
  offset = 0;
  v12 = 0;
  *(_QWORD *)derivedKeyLength = 0;
  *(_QWORD *)v31 = 0;
  v13 = (unsigned int)a4;
  v28 = 0;
  algId = 0;
  *(_QWORD *)cbLabel = 0;
  LODWORD(pLabel) = v9;
  if ( v9 )
    *(_QWORD *)cbLabel = (char *)a1 + *((unsigned int *)a1 + 10) + 80;
  if ( a6 > 0 )
  {
    v16 = *((_DWORD *)a1 + 3);
    v33 = *(struct _GUID *)((char *)a1 + 24);
    v17 = GenerateKDFContext(&v33, v16, a7, -1, 1u, (unsigned __int8 **)derivedKeyLength, &offset, &algId);
    v10 = v17;
    if ( v17 < 0 )
    {
      SidKeyDebugTraceError(
        v17,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
        0x1F3u);
      v11 = *(void **)derivedKeyLength;
      goto LABEL_20;
    }
    v11 = *(void **)derivedKeyLength;
    LODWORD(ppKey) = 0;
    LODWORD(pNonce) = 64;
    DerivedKey = GenerateDerivedKey(
                   hCrypto,
                   cbLabel[0],
                   (PBYTE)(unsigned int)pLabel,
                   v13,
                   pNonce,
                   derivedKeyLength[0],
                   offset,
                   (LPCWSTR)&algId,
                   0,
                   ppKey);
    v10 = DerivedKey;
    if ( DerivedKey < 0 )
    {
      v19 = 520;
LABEL_19:
      SidKeyDebugTraceError(
        DerivedKey,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
        v19);
      goto LABEL_20;
    }
  }
  if ( *((_DWORD *)a1 + 17) && (!a2 || *((_DWORD *)a1 + 4) <= *((_DWORD *)a2 + 4)) )
    v13 = (unsigned int)a5;
  if ( a8 > 0 )
  {
    v20 = *((_DWORD *)a1 + 3);
    if ( !a2 )
      a2 = a1;
    v21 = *((_DWORD *)a2 + 4);
    v33 = *(struct _GUID *)((char *)a1 + 24);
    v22 = GenerateKDFContext(&v33, v20, v21, a9, 2u, (unsigned __int8 **)v31, &v28, &algId);
    v10 = v22;
    if ( v22 < 0 )
    {
      SidKeyDebugTraceError(
        v22,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyrpcclient.cxx",
        0x228u);
      v12 = *(void **)v31;
      goto LABEL_20;
    }
    v12 = *(void **)v31;
    LODWORD(ppKey) = 0;
    LODWORD(pNoncea) = 64;
    DerivedKey = GenerateDerivedKey(
                   hCrypto,
                   cbLabel[0],
                   (PBYTE)(unsigned int)pLabel,
                   v13,
                   pNoncea,
                   v31[0],
                   v28,
                   (LPCWSTR)&algId,
                   0,
                   ppKey);
    v10 = DerivedKey;
    if ( DerivedKey < 0 )
    {
      v19 = 573;
      goto LABEL_19;
    }
  }
LABEL_20:
  if ( v11 )
    SIDKeyProvFree(v11);
  if ( v12 )
    SIDKeyProvFree(v12);
  return v10;
}

```

## disassembly

```asm
0x180018298  mov     [rsp-8+arg_8], rbx
0x18001829d  mov     [rsp-8+hCrypto], r8
0x1800182a2  push    rbp
0x1800182a3  push    rsi
0x1800182a4  push    rdi
0x1800182a5  push    r12
0x1800182a7  push    r13
0x1800182a9  push    r14
0x1800182ab  push    r15
0x1800182ad  lea     rbp, [rsp-7]
0x1800182b2  sub     rsp, 0B0h
0x1800182b9  mov     eax, [rcx+2Ch]
0x1800182bc  xor     ebx, ebx
0x1800182be  xor     r14d, r14d
0x1800182c1  mov     [rbp+37h+var_70], ebx
0x1800182c4  xor     esi, esi
0x1800182c6  mov     qword ptr [rbp+37h+var_60], r14
0x1800182ca  mov     qword ptr [rbp+37h+var_58], rsi
0x1800182ce  mov     r12, r9
0x1800182d1  mov     [rbp+37h+var_6C], ebx
0x1800182d4  mov     r15, rdx
0x1800182d7  mov     [rbp+37h+arg_0], ebx
0x1800182da  mov     rdi, rcx
0x1800182dd  mov     qword ptr [rbp+37h+cbLabel], rbx
0x1800182e1  mov     dword ptr [rbp+37h+pLabel], eax
0x1800182e4  test    eax, eax
0x1800182e6  jz      short loc_1800182F6
0x1800182e8  mov     eax, [rcx+28h]
0x1800182eb  add     rax, 50h ; 'P'
0x1800182ef  add     rax, rcx
0x1800182f2  mov     qword ptr [rbp+37h+cbLabel], rax
0x1800182f6  mov     r13d, [rbp+37h+arg_28]
0x1800182fa  test    r13d, r13d
0x1800182fd  jle     loc_1800183D2
0x180018303  movups  xmm0, xmmword ptr [rcx+18h]
0x180018307  mov     edx, [rcx+0Ch]; unsigned int
0x18001830a  lea     rax, [rbp+37h+arg_0]
0x18001830e  mov     r8d, [rbp+37h+arg_30]; int
0x180018312  lea     rcx, [rbp+37h+var_40]; struct _GUID *
0x180018316  mov     [rsp+0E0h+algId], rax; unsigned int *
0x18001831b  or      r9d, 0FFFFFFFFh; int
0x18001831f  lea     rax, [rbp+37h+var_70]
0x180018323  mov     qword ptr [rsp+0E0h+offset], rax; unsigned int *
0x180018328  lea     rax, [rbp+37h+var_60]
0x18001832c  mov     qword ptr [rsp+0E0h+derivedKeyLength], rax; unsigned __int8 **
0x180018331  mov     dword ptr [rsp+0E0h+pNonce], 1; unsigned int
0x180018339  movdqu  xmmword ptr [rbp+37h+var_40.Data1], xmm0
0x18001833e  call    ?GenerateKDFContext@@YAJU_GUID@@KJJKPEAPEAEPEAK2@Z; GenerateKDFContext(_GUID,ulong,long,long,ulong,uchar * *,ulong *,ulong *)
0x180018343  xor     ecx, ecx
0x180018345  mov     ebx, eax
0x180018347  test    eax, eax
0x180018349  jns     short loc_18001836F
0x18001834b  mov     r9d, 1F3h; unsigned int
0x180018351  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180018358  lea     rdx, aHr; "hr"
0x18001835f  mov     ecx, eax; unsigned int
0x180018361  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180018366  mov     r14, qword ptr [rbp+37h+var_60]
0x18001836a  jmp     loc_1800184E0
0x18001836f  mov     r14, qword ptr [rbp+37h+var_60]
0x180018373  lea     rax, [rbp+37h+arg_0]
0x180018377  mov     r8d, dword ptr [rbp+37h+pLabel]; pLabel
0x18001837b  mov     edx, 40h ; '@'
0x180018380  mov     [rsp+0E0h+var_78], rcx
0x180018385  mov     r9, r12; cbNonce
0x180018388  mov     [rsp+0E0h+var_80], edx
0x18001838c  mov     [rsp+0E0h+var_88], r12
0x180018391  mov     [rsp+0E0h+var_90], r13d
0x180018396  mov     dword ptr [rsp+0E0h+ppKey], ecx; ppKey
0x18001839a  mov     [rsp+0E0h+pcbKey], rcx; pcbKey
0x18001839f  mov     rcx, [rbp+37h+hCrypto]; hCrypto
0x1800183a3  mov     [rsp+0E0h+algId], rax; algId
0x1800183a8  mov     eax, [rbp+37h+var_70]
0x1800183ab  mov     [rsp+0E0h+offset], eax; offset
0x1800183af  mov     qword ptr [rsp+0E0h+derivedKeyLength], r14; derivedKeyLength
0x1800183b4  mov     dword ptr [rsp+0E0h+pNonce], edx; pNonce
0x1800183b8  mov     rdx, qword ptr [rbp+37h+cbLabel]; cbLabel
0x1800183bc  call    ?GenerateDerivedKey@@YAJPEBGPEAEK1K1KPEAK1KK1KPEAPEAG@Z; GenerateDerivedKey(ushort const *,uchar *,ulong,uchar *,ulong,uchar *,ulong,ulong *,uchar *,ulong,ulong,uchar *,ulong,ushort * *)
0x1800183c1  mov     ebx, eax
0x1800183c3  test    eax, eax
0x1800183c5  jns     short loc_1800183D2
0x1800183c7  mov     r9d, 208h
0x1800183cd  jmp     loc_1800184CB
0x1800183d2  cmp     [rdi+44h], esi
0x1800183d5  jz      short loc_1800183E9
0x1800183d7  test    r15, r15
0x1800183da  jz      short loc_1800183E5
0x1800183dc  mov     eax, [r15+10h]
0x1800183e0  cmp     [rdi+10h], eax
0x1800183e3  ja      short loc_1800183E9
0x1800183e5  mov     r12, [rbp+37h+arg_20]
0x1800183e9  mov     r13d, [rbp+37h+arg_38]
0x1800183ed  test    r13d, r13d
0x1800183f0  jle     loc_1800184E0
0x1800183f6  movups  xmm0, xmmword ptr [rdi+18h]
0x1800183fa  mov     r9d, [rbp+37h+arg_40]; int
0x180018401  lea     rax, [rbp+37h+arg_0]
0x180018405  mov     edx, [rdi+0Ch]; unsigned int
0x180018408  lea     rcx, [rbp+37h+var_40]; struct _GUID *
0x18001840c  mov     [rsp+0E0h+algId], rax; unsigned int *
0x180018411  test    r15, r15
0x180018414  lea     rax, [rbp+37h+var_6C]
0x180018418  mov     qword ptr [rsp+0E0h+offset], rax; unsigned int *
0x18001841d  cmovz   r15, rdi
0x180018421  lea     rax, [rbp+37h+var_58]
0x180018425  mov     qword ptr [rsp+0E0h+derivedKeyLength], rax; unsigned __int8 **
0x18001842a  mov     dword ptr [rsp+0E0h+pNonce], 2; unsigned int
0x180018432  mov     r8d, [r15+10h]; int
0x180018436  movdqu  xmmword ptr [rbp+37h+var_40.Data1], xmm0
0x18001843b  call    ?GenerateKDFContext@@YAJU_GUID@@KJJKPEAPEAEPEAK2@Z; GenerateKDFContext(_GUID,ulong,long,long,ulong,uchar * *,ulong *,ulong *)
0x180018440  xor     ecx, ecx
0x180018442  mov     ebx, eax
0x180018444  test    eax, eax
0x180018446  jns     short loc_180018469
0x180018448  mov     r9d, 228h; unsigned int
0x18001844e  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180018455  lea     rdx, aHr; "hr"
0x18001845c  mov     ecx, eax; unsigned int
0x18001845e  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180018463  mov     rsi, qword ptr [rbp+37h+var_58]
0x180018467  jmp     short loc_1800184E0
0x180018469  mov     rax, [rbp+37h+arg_20]
0x18001846d  mov     edx, 40h ; '@'
0x180018472  mov     rsi, qword ptr [rbp+37h+var_58]
0x180018476  mov     r9, r12; cbNonce
0x180018479  mov     r8d, dword ptr [rbp+37h+pLabel]; pLabel
0x18001847d  mov     [rsp+0E0h+var_78], rcx
0x180018482  mov     [rsp+0E0h+var_80], edx
0x180018486  mov     [rsp+0E0h+var_88], rax
0x18001848b  lea     rax, [rbp+37h+arg_0]
0x18001848f  mov     [rsp+0E0h+var_90], r13d
0x180018494  mov     dword ptr [rsp+0E0h+ppKey], ecx; ppKey
0x180018498  mov     [rsp+0E0h+pcbKey], rcx; pcbKey
0x18001849d  mov     rcx, [rbp+37h+hCrypto]; hCrypto
0x1800184a1  mov     [rsp+0E0h+algId], rax; algId
0x1800184a6  mov     eax, [rbp+37h+var_6C]
0x1800184a9  mov     [rsp+0E0h+offset], eax; offset
0x1800184ad  mov     qword ptr [rsp+0E0h+derivedKeyLength], rsi; derivedKeyLength
0x1800184b2  mov     dword ptr [rsp+0E0h+pNonce], edx; pNonce
0x1800184b6  mov     rdx, qword ptr [rbp+37h+cbLabel]; cbLabel
0x1800184ba  call    ?GenerateDerivedKey@@YAJPEBGPEAEK1K1KPEAK1KK1KPEAPEAG@Z; GenerateDerivedKey(ushort const *,uchar *,ulong,uchar *,ulong,uchar *,ulong,ulong *,uchar *,ulong,ulong,uchar *,ulong,ushort * *)
0x1800184bf  mov     ebx, eax
0x1800184c1  test    eax, eax
0x1800184c3  jns     short loc_1800184E0
0x1800184c5  mov     r9d, 23Dh; unsigned int
0x1800184cb  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800184d2  mov     ecx, eax; unsigned int
0x1800184d4  lea     rdx, aHr; "hr"
0x1800184db  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800184e0  test    r14, r14
0x1800184e3  jz      short loc_1800184ED
0x1800184e5  mov     rcx, r14; lpMem
0x1800184e8  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x1800184ed  test    rsi, rsi
0x1800184f0  jz      short loc_1800184FA
0x1800184f2  mov     rcx, rsi; lpMem
0x1800184f5  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x1800184fa  mov     eax, ebx
0x1800184fc  mov     rbx, [rsp+0E0h+arg_8]
0x180018504  add     rsp, 0B0h
0x18001850b  pop     r15
0x18001850d  pop     r14
0x18001850f  pop     r13
0x180018511  pop     r12
0x180018513  pop     rdi
0x180018514  pop     rsi
0x180018515  pop     rbp
0x180018516  retn
```
