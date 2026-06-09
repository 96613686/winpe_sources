# ImportEccKeyBlobWithParameters

- ea: `0x180048430`
- end: `0x180048bc6`
- name: `ImportEccKeyBlobWithParameters`
- size: `1942`
- prototype: `__int64 __fastcall(__int64, unsigned int *, unsigned int, int, int, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800476d0`

## callees

- `0x18000ee60`
- `0x18001ad88`
- `0x18001c380`
- `0x18001c420`
- `0x1800225d0`
- `0x1800228b0`
- `0x180023ce0`
- `0x1800243b8`
- `0x180046658`
- `0x180048430`
- `0x180056520`
- `0x180056cf0`
- `0x1800631a8`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800486d0`
- `ntdll!RtlAllocateHeap` at `0x1800486d0`

## string_xrefs

- `0x18004848f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18004853e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800485a5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180048653`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18004869a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800486fd`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800488b6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800488ee`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180048a5f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180048b0b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180048b90`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall ImportEccKeyBlobWithParameters(
        __int64 a1,
        unsigned int *a2,
        unsigned int a3,
        int a4,
        int a5,
        unsigned int a6,
        _QWORD *a7)
{
  void *v7; // r12
  unsigned int v8; // r15d
  unsigned int *v9; // rbx
  unsigned int v11; // esi
  unsigned __int64 v12; // rcx
  unsigned int v13; // eax
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  int v16; // r13d
  int KeyMagicForAlgId; // eax
  int v18; // edx
  int v19; // r8d
  unsigned int v20; // ecx
  _OWORD *Heap; // rax
  int v22; // edx
  int v23; // r8d
  _DWORD *v24; // r14
  _QWORD *v25; // rcx
  __int64 v26; // rax
  unsigned int v27; // r15d
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // r8
  _DWORD *v31; // rdi
  unsigned int v32; // edx
  __int64 v33; // rax
  int v34; // eax
  int v35; // edx
  int v36; // r8d
  _QWORD *v37; // rcx
  __int64 v38; // rax
  int v39; // r11d
  _QWORD *v40; // rdi
  __int64 v41; // rbx
  int v42; // eax
  __int64 v43; // r9
  __int64 v44; // r11
  __int64 v45; // r15
  __int64 v46; // rbp
  bool v47; // zf
  _QWORD *v48; // rax
  int v49; // edi
  int v50; // ebx
  __int64 v51; // rax
  int v52; // edx
  int v53; // r8d
  unsigned int v54; // eax
  unsigned int v55; // eax
  int v56; // edx
  int v57; // r8d
  _QWORD *v58; // rcx
  char v60; // [rsp+30h] [rbp-58h]
  char v61; // [rsp+30h] [rbp-58h]
  int v62; // [rsp+40h] [rbp-48h]
  _QWORD *v63; // [rsp+98h] [rbp+10h] BYREF
  int v64; // [rsp+A0h] [rbp+18h] BYREF
  int v65; // [rsp+A8h] [rbp+20h]

  v65 = a4;
  v7 = 0;
  v63 = 0;
  v8 = a3;
  v64 = 0;
  v9 = a2;
  if ( a3 < 0x20 )
  {
    v11 = -1073741789;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        35,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        222);
    return v11;
  }
  v12 = 7LL * a2[4];
  if ( v12 > 0xFFFFFFFF )
  {
    v11 = -1073741675;
    v58 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v11;
    v61 = -25;
LABEL_100:
    WPP_SF_sDsd(
      v58[2],
      (_DWORD)a2,
      a3,
      (unsigned int)"Status",
      149,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
      v61);
    return v11;
  }
  v13 = v12 + 32;
  if ( (int)v12 + 32 < (unsigned int)v12 )
    goto LABEL_94;
  a3 = a2[5];
  v14 = a3 + v13;
  if ( a3 + v13 < v13 )
    goto LABEL_94;
  LODWORD(a2) = v14 + a2[6];
  if ( (unsigned int)a2 < v14 )
    goto LABEL_94;
  v15 = (_DWORD)a2 + v9[7];
  if ( v15 < (unsigned int)a2 )
    goto LABEL_94;
  v16 = a5;
  if ( !a5 )
    goto LABEL_13;
  if ( v15 + a3 < v15 )
  {
LABEL_94:
    v11 = -1073741675;
    v58 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v11;
    v61 = -14;
    goto LABEL_100;
  }
  v15 += a3;
LABEL_13:
  if ( v8 < v15 )
  {
    v11 = -1073741789;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        35,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        251);
    return v11;
  }
  KeyMagicForAlgId = MSCryptEcGetKeyMagicForAlgId(*(_DWORD *)(a1 + 8), *(_QWORD *)(a1 + 16), a4, a5, (__int64)&v64);
  v11 = KeyMagicForAlgId;
  if ( KeyMagicForAlgId < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v18,
        v19,
        (unsigned int)"Status",
        KeyMagicForAlgId,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        16);
    return v11;
  }
  v20 = *v9;
  if ( *v9 == v64 )
  {
LABEL_37:
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x28u);
    v24 = Heap;
    if ( !Heap )
    {
      v11 = -1073741801;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v22,
            v23,
            (unsigned int)"Status",
            23,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
            62);
          v25 = WPP_GLOBAL_Control;
        }
        if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 1) != 0 )
          WPP_SF_sDsd(
            v25[2],
            v22,
            v23,
            (unsigned int)"Status",
            23,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
            54);
      }
      goto LABEL_92;
    }
    *Heap = 0;
    Heap[1] = 0;
    *((_QWORD *)Heap + 4) = 0;
    *((_DWORD *)Heap + 2) = *(_DWORD *)(a1 + 8);
    *(_DWORD *)Heap = 40;
    *((_DWORD *)Heap + 1) = 1297304409;
    v26 = *(_QWORD *)(a1 + 16);
    if ( v26 )
    {
      v24[8] |= 1u;
      *((_QWORD *)v24 + 2) = v26;
    }
    v27 = v8 - 2 * v9[4] - 4;
    if ( v16 )
      v27 -= v9[5];
    if ( !*(_QWORD *)(a1 + 16) )
      goto LABEL_56;
    v28 = AssignGenericDomainParameters(&v63, *(unsigned int *)(a1 + 8), v9 + 1, v27, 0, 0);
    v7 = v63;
    v11 = v28;
    if ( v28 < 0 )
      goto LABEL_86;
    if ( !v63 || (v31 = **(_DWORD ***)(a1 + 16), !(unsigned int)TestIfCurveParametersAreEqual(v31, *v63)) )
    {
      v11 = -1073741811;
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_86;
      v60 = 84;
LABEL_63:
      WPP_SF_sDsd(
        v37[2],
        v29,
        v30,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        v60);
      goto LABEL_86;
    }
    if ( !v31
      || v31[2] != v9[3]
      || (v32 = v31[6], v32 != v9[7])
      || (v33 = (unsigned int)(v31[4] + v31[5] + 5 * v31[3]),
          memcmp_0((char *)v31 + v33 + 28, (char *)v9 + v33 + 32, v32)) )
    {
LABEL_56:
      v34 = AssignGenericDomainParameters(v24 + 4, *(unsigned int *)(a1 + 8), v9 + 1, v27, 0, 0);
      v11 = v34;
      if ( v34 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v35,
            v36,
            (unsigned int)"Status",
            v34,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
            98);
        goto LABEL_86;
      }
      v24[8] = 0;
    }
    v38 = *((_QWORD *)v24 + 2);
    v63 = 0;
    v39 = *(_DWORD *)(*(_QWORD *)v38 + 12LL);
    v40 = (_QWORD *)*(unsigned int *)(*(_QWORD *)v38 + 16LL);
    v41 = (__int64)v9
        + (_QWORD)v40
        + *(unsigned int *)(*(_QWORD *)v38 + 24LL)
        + 5 * v39
        + *(unsigned int *)(*(_QWORD *)v38 + 20LL)
        + 32;
    v42 = IsAllZeros(v41, (unsigned int)(2 * v39));
    v29 = 0;
    v45 = v44 + v41;
    if ( !v42 )
      v29 = (unsigned int)v44;
    v46 = 0;
    v62 = v29;
    v47 = v42 == 0;
    v48 = v63;
    if ( v47 )
      v46 = v41;
    if ( v16 )
      v48 = v40;
    v63 = v48;
    if ( !v16 )
      v45 = 0;
    if ( (a6 & 0x20) != 0 && (!v45 || !v46) )
    {
      v11 = -1073741811;
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_86;
      v60 = -115;
      goto LABEL_63;
    }
    v49 = BCryptFlagsToSymCryptKeyValidationFlags(a6, v29, v30, v43);
    v50 = 4096;
    if ( !v65 )
      v50 = 0x2000;
    v51 = SymCryptEckeyAllocate(*(_QWORD *)(*((_QWORD *)v24 + 2) + 8LL));
    *((_QWORD *)v24 + 3) = v51;
    if ( v51 )
    {
      v54 = SymCryptEckeySetValue(
              v45,
              (_DWORD)v63,
              v46,
              v62,
              (unsigned int)(*(_DWORD *)(**((_QWORD **)v24 + 2) + 4LL) != 3) + 1,
              2,
              v49 | (unsigned int)v50,
              v51);
      if ( !v54 )
      {
        *a7 = v24;
LABEL_92:
        if ( v7 )
          FreeGenericEccKeyParameters(v7);
        return v11;
      }
      v55 = SymcryptErrorCodeToNtStatus(v54);
      v11 = v55;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v56,
          v57,
          (unsigned int)"Status",
          v55,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          168);
    }
    else
    {
      v11 = -1073741801;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v52,
          v53,
          (unsigned int)"Status",
          23,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          152);
    }
LABEL_86:
    MSCryptEccDestroyKeyPair(v24);
    goto LABEL_92;
  }
  if ( !*(_QWORD *)(a1 + 16) )
  {
    if ( v64 != 1447314245
      && v64 != 1346650949
      && v64 != 1447772997
      && v64 != 1347109701
      && (v20 == 1447314245 || v20 == 1346650949 || v20 == 1447772997 || v20 == 1347109701) )
    {
      v11 = -1073741811;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v18,
          v19,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          39);
      return v11;
    }
    goto LABEL_37;
  }
  v11 = -1073741811;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v18,
      v19,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
      46);
  return v11;
}

```

## disassembly

```asm
0x180048430  mov     rax, rsp
0x180048433  mov     [rax+20h], r9d
0x180048437  push    rbx
0x180048438  push    rbp
0x180048439  push    rsi
0x18004843a  push    rdi
0x18004843b  push    r12
0x18004843d  push    r13
0x18004843f  push    r15
0x180048441  sub     rsp, 50h
0x180048445  xor     r12d, r12d
0x180048448  mov     r10d, r9d
0x18004844b  mov     [rax+10h], r12
0x18004844f  mov     r15d, r8d
0x180048452  mov     [rax+18h], r12d
0x180048456  mov     rbx, rdx
0x180048459  mov     rbp, rcx
0x18004845c  cmp     r8d, 20h ; ' '
0x180048460  jnb     short loc_1800484A6
0x180048462  mov     esi, 0C0000023h
0x180048467  mov     rcx, cs:WPP_GLOBAL_Control
0x18004846e  lea     rbx, WPP_GLOBAL_Control
0x180048475  cmp     rcx, rbx
0x180048478  jz      loc_180048BB4
0x18004847e  test    byte ptr [rcx+1Ch], 1
0x180048482  jz      loc_180048BB4
0x180048488  mov     dword ptr [rax-58h], 8DEh
0x18004848f  lea     rdi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180048496  mov     [rax-60h], rdi
0x18004849a  mov     dword ptr [rax-68h], 0C0000023h
0x1800484a1  jmp     loc_180048BA4
0x1800484a6  mov     eax, [rdx+10h]
0x1800484a9  imul    rcx, rax, 7
0x1800484ad  mov     eax, 0FFFFFFFFh
0x1800484b2  cmp     rcx, rax
0x1800484b5  ja      loc_180048B6A
0x1800484bb  lea     eax, [rcx+20h]
0x1800484be  cmp     eax, ecx
0x1800484c0  jb      loc_180048B42
0x1800484c6  mov     r8d, [rdx+14h]
0x1800484ca  lea     ecx, [r8+rax]
0x1800484ce  cmp     ecx, eax
0x1800484d0  jb      loc_180048B42
0x1800484d6  mov     edx, [rdx+18h]
0x1800484d9  add     edx, ecx
0x1800484db  cmp     edx, ecx
0x1800484dd  jb      loc_180048B42
0x1800484e3  mov     ecx, [rbx+1Ch]
0x1800484e6  add     ecx, edx
0x1800484e8  cmp     ecx, edx
0x1800484ea  jb      loc_180048B42
0x1800484f0  mov     r13d, [rsp+88h+arg_20]
0x1800484f8  test    r13d, r13d
0x1800484fb  jz      short loc_18004850B
0x1800484fd  lea     eax, [rcx+r8]
0x180048501  cmp     eax, ecx
0x180048503  jb      loc_180048B42
0x180048509  mov     ecx, eax
0x18004850b  cmp     r15d, ecx
0x18004850e  jnb     short loc_180048557
0x180048510  mov     esi, 0C0000023h
0x180048515  mov     rcx, cs:WPP_GLOBAL_Control
0x18004851c  lea     rbx, WPP_GLOBAL_Control
0x180048523  cmp     rcx, rbx
0x180048526  jz      loc_180048BB4
0x18004852c  test    byte ptr [rcx+1Ch], 1
0x180048530  jz      loc_180048BB4
0x180048536  mov     dword ptr [rsp+88h+var_58], 8FBh
0x18004853e  lea     rdi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180048545  mov     [rsp+88h+var_60], rdi
0x18004854a  mov     dword ptr [rsp+88h+var_68], 0C0000023h
0x180048552  jmp     loc_180048BA4
0x180048557  mov     rdx, [rbp+10h]
0x18004855b  lea     rax, [rsp+88h+arg_10]
0x180048563  mov     ecx, [rbp+8]
0x180048566  mov     r9d, r13d
0x180048569  mov     r8d, r10d
0x18004856c  mov     [rsp+88h+var_68], rax
0x180048571  call    MSCryptEcGetKeyMagicForAlgId
0x180048576  mov     esi, eax
0x180048578  test    eax, eax
0x18004857a  jns     short loc_1800485BA
0x18004857c  mov     rcx, cs:WPP_GLOBAL_Control
0x180048583  lea     rbx, WPP_GLOBAL_Control
0x18004858a  cmp     rcx, rbx
0x18004858d  jz      loc_180048BB4
0x180048593  test    byte ptr [rcx+1Ch], 1
0x180048597  jz      loc_180048BB4
0x18004859d  mov     dword ptr [rsp+88h+var_58], 910h
0x1800485a5  lea     rdi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800485ac  mov     [rsp+88h+var_60], rdi
0x1800485b1  mov     dword ptr [rsp+88h+var_68], eax
0x1800485b5  jmp     loc_180048BA4
0x1800485ba  mov     ecx, [rbx]
0x1800485bc  mov     eax, [rsp+88h+arg_10]
0x1800485c3  cmp     ecx, eax
0x1800485c5  jz      loc_1800486B3
0x1800485cb  cmp     [rbp+10h], r12
0x1800485cf  jnz     loc_18004866C
0x1800485d5  cmp     eax, 56444345h
0x1800485da  jz      loc_1800486B3
0x1800485e0  cmp     eax, 50444345h
0x1800485e5  jz      loc_1800486B3
0x1800485eb  cmp     eax, 564B4345h
0x1800485f0  jz      loc_1800486B3
0x1800485f6  cmp     eax, 504B4345h
0x1800485fb  jz      loc_1800486B3
0x180048601  cmp     ecx, 56444345h
0x180048607  jz      short loc_180048625
0x180048609  cmp     ecx, 50444345h
0x18004860f  jz      short loc_180048625
0x180048611  cmp     ecx, 564B4345h
0x180048617  jz      short loc_180048625
0x180048619  cmp     ecx, 504B4345h
0x18004861f  jnz     loc_1800486B3
0x180048625  mov     esi, 0C000000Dh
0x18004862a  mov     rcx, cs:WPP_GLOBAL_Control
0x180048631  lea     rbx, WPP_GLOBAL_Control
0x180048638  cmp     rcx, rbx
0x18004863b  jz      loc_180048BB4
0x180048641  test    byte ptr [rcx+1Ch], 1
0x180048645  jz      loc_180048BB4
0x18004864b  mov     dword ptr [rsp+88h+var_58], 927h
0x180048653  lea     rdi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004865a  mov     [rsp+88h+var_60], rdi
0x18004865f  mov     dword ptr [rsp+88h+var_68], 0C000000Dh
0x180048667  jmp     loc_180048BA4
0x18004866c  mov     esi, 0C000000Dh
0x180048671  mov     rcx, cs:WPP_GLOBAL_Control
0x180048678  lea     rbx, WPP_GLOBAL_Control
0x18004867f  cmp     rcx, rbx
0x180048682  jz      loc_180048BB4
0x180048688  test    byte ptr [rcx+1Ch], 1
0x18004868c  jz      loc_180048BB4
0x180048692  mov     dword ptr [rsp+88h+var_58], 92Eh
0x18004869a  lea     rdi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800486a1  mov     [rsp+88h+var_60], rdi
0x1800486a6  mov     dword ptr [rsp+88h+var_68], 0C000000Dh
0x1800486ae  jmp     loc_180048BA4
0x1800486b3  mov     rcx, gs:60h
0x1800486bc  xor     edx, edx; Flags
0x1800486be  mov     r8d, 28h ; '('; Size
0x1800486c4  mov     [rsp+88h+arg_0], r14
0x1800486cc  mov     rcx, [rcx+30h]; HeapHandle
0x1800486d0  call    cs:__imp_RtlAllocateHeap
0x1800486d7  nop     dword ptr [rax+rax+00h]
0x1800486dc  mov     r14, rax
0x1800486df  test    rax, rax
0x1800486e2  jnz     loc_180048778
0x1800486e8  mov     esi, 0C0000017h
0x1800486ed  mov     ebp, esi
0x1800486ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800486f6  lea     rbx, WPP_GLOBAL_Control
0x1800486fd  lea     rdi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180048704  cmp     rcx, rbx
0x180048707  jz      loc_180048B2B
0x18004870d  test    byte ptr [rcx+1Ch], 1
0x180048711  jz      short loc_18004873F
0x180048713  mov     rcx, [rcx+10h]
0x180048717  lea     r9, aStatus; "Status"
0x18004871e  mov     dword ptr [rsp+88h+var_58], 63Eh
0x180048726  mov     [rsp+88h+var_60], rdi
0x18004872b  mov     dword ptr [rsp+88h+var_68], 0C0000017h
0x180048733  call    WPP_SF_sDsd
0x180048738  mov     rcx, cs:WPP_GLOBAL_Control
0x18004873f  cmp     rcx, rbx
0x180048742  jz      loc_180048B2B
0x180048748  test    byte ptr [rcx+1Ch], 1
0x18004874c  jz      loc_180048B2B
0x180048752  mov     rcx, [rcx+10h]
0x180048756  lea     r9, aStatus; "Status"
0x18004875d  mov     dword ptr [rsp+88h+var_58], 936h
0x180048765  mov     [rsp+88h+var_60], rdi
0x18004876a  mov     dword ptr [rsp+88h+var_68], ebp
0x18004876e  call    WPP_SF_sDsd
0x180048773  jmp     loc_180048B2B
0x180048778  xor     eax, eax
0x18004877a  xorps   xmm0, xmm0
0x18004877d  movups  xmmword ptr [r14], xmm0
0x180048781  movups  xmmword ptr [r14+10h], xmm0
0x180048786  mov     [r14+20h], rax
0x18004878a  mov     eax, [rbp+8]
0x18004878d  mov     [r14+8], eax
0x180048791  mov     dword ptr [r14], 28h ; '('
0x180048798  mov     dword ptr [r14+4], 4D534B59h
0x1800487a0  mov     rax, [rbp+10h]
0x1800487a4  test    rax, rax
0x1800487a7  jz      short loc_1800487B2
0x1800487a9  or      dword ptr [r14+20h], 1
0x1800487ae  mov     [r14+10h], rax
0x1800487b2  mov     eax, [rbx+10h]
0x1800487b5  add     eax, eax
0x1800487b7  sub     r15d, eax
0x1800487ba  add     r15d, 0FFFFFFFCh
0x1800487be  test    r13d, r13d
0x1800487c1  jz      short loc_1800487C7
0x1800487c3  sub     r15d, [rbx+14h]
0x1800487c7  cmp     [rbp+10h], r12
0x1800487cb  jz      loc_180048867
0x1800487d1  mov     edx, [rbp+8]
0x1800487d4  lea     r8, [rbx+4]
0x1800487d8  mov     dword ptr [rsp+88h+var_60], r12d
0x1800487dd  lea     rcx, [rsp+88h+arg_8]
0x1800487e5  mov     r9d, r15d
0x1800487e8  mov     [rsp+88h+var_68], r12
0x1800487ed  call    AssignGenericDomainParameters
0x1800487f2  mov     r12, [rsp+88h+arg_8]
0x1800487fa  mov     esi, eax
0x1800487fc  test    eax, eax
0x1800487fe  js      loc_180048912
0x180048804  test    r12, r12
0x180048807  jz      loc_1800488C8
0x18004880d  mov     rax, [rbp+10h]
0x180048811  mov     rdx, [r12]
0x180048815  mov     rdi, [rax]
0x180048818  mov     rcx, rdi
0x18004881b  call    TestIfCurveParametersAreEqual
0x180048820  test    eax, eax
0x180048822  jz      loc_1800488C8
0x180048828  test    rdi, rdi
0x18004882b  jz      short loc_180048867
0x18004882d  mov     eax, [rbx+0Ch]
0x180048830  cmp     [rdi+8], eax
0x180048833  jnz     short loc_180048867
0x180048835  mov     edx, [rdi+18h]
0x180048838  cmp     edx, [rbx+1Ch]
0x18004883b  jnz     short loc_180048867
0x18004883d  mov     eax, [rdi+0Ch]
0x180048840  lea     rcx, [rdi+1Ch]
0x180048844  mov     r8d, edx; Size
0x180048847  lea     rdx, [rbx+20h]
0x18004884b  lea     eax, [rax+rax*4]
0x18004884e  add     eax, [rdi+14h]
0x180048851  add     eax, [rdi+10h]
0x180048854  add     rdx, rax; Buf2
0x180048857  add     rcx, rax; Buf1
0x18004885a  call    memcmp_0
0x18004885f  test    eax, eax
0x180048861  jz      loc_180048932
0x180048867  mov     edx, [rbp+8]
0x18004886a  lea     rcx, [r14+10h]
0x18004886e  mov     dword ptr [rsp+88h+var_60], 0
0x180048876  lea     r8, [rbx+4]
0x18004887a  mov     r9d, r15d
0x18004887d  mov     [rsp+88h+var_68], 0
0x180048886  call    AssignGenericDomainParameters
0x18004888b  mov     esi, eax
0x18004888d  test    eax, eax
0x18004888f  jns     loc_18004892A
0x180048895  mov     rcx, cs:WPP_GLOBAL_Control
0x18004889c  lea     rbx, WPP_GLOBAL_Control
0x1800488a3  cmp     rcx, rbx
0x1800488a6  jz      short loc_180048912
0x1800488a8  test    byte ptr [rcx+1Ch], 1
0x1800488ac  jz      short loc_180048912
0x1800488ae  mov     dword ptr [rsp+88h+var_58], 962h
0x1800488b6  lea     rdi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800488bd  mov     [rsp+88h+var_60], rdi
0x1800488c2  mov     dword ptr [rsp+88h+var_68], eax
0x1800488c6  jmp     short loc_180048902
0x1800488c8  mov     esi, 0C000000Dh
0x1800488cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800488d4  lea     rbx, WPP_GLOBAL_Control
0x1800488db  cmp     rcx, rbx
0x1800488de  jz      short loc_180048912
0x1800488e0  test    byte ptr [rcx+1Ch], 1
0x1800488e4  jz      short loc_180048912
0x1800488e6  mov     dword ptr [rsp+88h+var_58], 954h
0x1800488ee  lea     rdi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800488f5  mov     [rsp+88h+var_60], rdi
0x1800488fa  mov     dword ptr [rsp+88h+var_68], 0C000000Dh
0x180048902  mov     rcx, [rcx+10h]
0x180048906  lea     r9, aStatus; "Status"
0x18004890d  call    WPP_SF_sDsd
0x180048912  mov     r13d, [rsp+88h+arg_18]
0x18004891a  mov     edx, r13d
0x18004891d  mov     rcx, r14; P
0x180048920  call    MSCryptEccDestroyKeyPair
0x180048925  jmp     loc_180048B2B
0x18004892a  mov     dword ptr [r14+20h], 0
0x180048932  mov     rax, [r14+10h]
0x180048936  xor     edx, edx
0x180048938  mov     [rsp+88h+arg_8], rdx
0x180048940  add     rbx, 20h ; ' '
0x180048944  mov     r8, [rax]
0x180048947  mov     r11d, [r8+0Ch]
0x18004894b  mov     edi, [r8+10h]
0x18004894f  mov     edx, [r8+18h]
0x180048953  mov     eax, [r8+14h]
0x180048957  add     rdx, rdi
0x18004895a  lea     ecx, [r11+r11*4]
0x18004895e  add     r11d, r11d
0x180048961  add     rdx, rcx
0x180048964  add     rax, rdx
0x180048967  mov     edx, r11d
0x18004896a  add     rbx, rax
0x18004896d  mov     rcx, rbx
0x180048970  call    IsAllZeros
0x180048975  xor     edx, edx
0x180048977  mov     ecx, r11d
  ... truncated ...
```
