# ImportEccKeyBlobWithoutParameters

- ea: `0x180047c50`
- end: `0x180048429`
- name: `ImportEccKeyBlobWithoutParameters`
- size: `2009`
- prototype: `__int64 __fastcall(__int64, _DWORD *, wchar_t *, unsigned int, int, int, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800476d0`

## callees

- `0x18000ee60`
- `0x1800102a0`
- `0x18001ad88`
- `0x18001c380`
- `0x18001c420`
- `0x180022340`
- `0x1800225d0`
- `0x180023ce0`
- `0x1800243b8`
- `0x180046658`
- `0x180047c50`
- `0x180049370`
- `0x180056cf0`
- `0x1800593e0`
- `0x180063170`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180047e2d`
- `ntdll!RtlFreeHeap` at `0x180047e4f`
- `ntdll!RtlFreeHeap` at `0x180048367`
- `ntdll!RtlFreeHeap` at `0x180047e2d`
- `ntdll!RtlFreeHeap` at `0x180047e4f`
- `ntdll!RtlFreeHeap` at `0x180048367`

## string_xrefs

- `0x180047dbb`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180047fe1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180048089`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18004814c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18004821c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800482a9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18004832c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800483be`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall ImportEccKeyBlobWithoutParameters(
        __int64 a1,
        _DWORD *a2,
        wchar_t *a3,
        unsigned int a4,
        int a5,
        int a6,
        unsigned int a7,
        _QWORD *a8)
{
  PVOID v8; // r15
  unsigned int v10; // esi
  _DWORD *v11; // rdi
  __int64 v12; // r12
  char *v13; // r14
  int v14; // r10d
  int v15; // ecx
  __int64 v16; // rax
  __int64 v17; // r9
  int v19; // eax
  unsigned int v20; // ebx
  _QWORD *v21; // rcx
  _QWORD *v22; // r14
  __int64 v23; // rbp
  void *v24; // rbp
  int v25; // eax
  _QWORD *v26; // rcx
  unsigned int v27; // ecx
  int KeyMagicForAlgId; // eax
  int v29; // eax
  int v30; // eax
  int v31; // edx
  int v32; // r8d
  _QWORD *v33; // rbp
  int v34; // r12d
  __int64 *v35; // rax
  char *v36; // rsi
  __int64 v37; // r15
  _DWORD *v38; // rcx
  __int64 v39; // rdi
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  unsigned int v43; // r11d
  unsigned int v44; // eax
  char *v45; // rax
  int v46; // edx
  int v47; // r8d
  size_t v48; // r8
  _DWORD *v49; // rdi
  int v50; // r15d
  char *v51; // rdi
  int v52; // r13d
  int v53; // esi
  __int64 v54; // rax
  int v55; // edx
  int v56; // r8d
  unsigned int v57; // eax
  unsigned int v58; // eax
  int v59; // edx
  int v60; // r8d
  char v62; // [rsp+30h] [rbp-68h]
  PVOID P; // [rsp+40h] [rbp-58h] BYREF
  int v64; // [rsp+48h] [rbp-50h] BYREF
  PVOID v65; // [rsp+50h] [rbp-48h]
  PVOID v66; // [rsp+58h] [rbp-40h] BYREF
  _DWORD *v68; // [rsp+A8h] [rbp+10h]

  v68 = a2;
  v8 = *(PVOID *)(a1 + 16);
  v10 = (unsigned int)a3;
  v11 = a2;
  v12 = a1;
  v13 = 0;
  v66 = 0;
  v14 = 0;
  v64 = 0;
  LODWORD(P) = 0;
  v65 = v8;
  if ( !v8 )
  {
    v15 = *a2;
    v8 = 0;
    P = 0;
    v16 = 0;
    v65 = 0;
    if ( v15 == 827540293
      || v15 == 844317509
      || v15 == 827016005
      || v15 == 843793221
      || (v16 = 1, v15 == 861094725)
      || v15 == 877871941
      || v15 == 860570437
      || v15 == 877347653
      || (v16 = 2, v15 == 894649157)
      || v15 == 911426373
      || v15 == 894124869
      || v15 == 910902085
      || (v16 = 3, v15 == 1346650949)
      || v15 == 1447314245
      || v15 == 1347109701
      || v15 == 1447772997 )
    {
      a3 = (&off_180084728)[6 * v16];
      if ( a3 )
      {
        v17 = -1;
        while ( a3[++v17] != 0 )
          ;
        v19 = LoadCurve(&P, 196619, a3, (unsigned int)(2 * v17 + 2));
        v20 = v19;
        if ( v19 < 0 )
        {
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)a2,
              (_DWORD)a3,
              (unsigned int)"Status",
              v19,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
              238);
            v21 = WPP_GLOBAL_Control;
          }
          v22 = P;
          if ( P )
          {
            v23 = *((_QWORD *)P + 1);
            if ( v23 )
            {
              SymCryptWipeAsm(*((_QWORD *)P + 1), *(unsigned int *)(v23 + 40));
              v24 = (void *)(v23 - *(unsigned int *)(v23 - 4));
              if ( v24 )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v24);
              v22[1] = 0;
            }
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v22);
            v21 = WPP_GLOBAL_Control;
          }
          if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 1) != 0 )
            WPP_SF_sDsd(
              v21[2],
              (_DWORD)a2,
              (_DWORD)a3,
              (unsigned int)"Status",
              v20,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
              213);
          goto LABEL_116;
        }
        v8 = P;
        v65 = P;
      }
    }
    v14 = *v11;
    LODWORD(P) = *v11;
  }
  if ( v10 < 8 || !v8 )
  {
    v20 = -1073741811;
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_116;
    v62 = -24;
    goto LABEL_115;
  }
  LODWORD(a3) = *(_DWORD *)(*(_QWORD *)v8 + 12LL);
  LODWORD(a2) = (_DWORD)a3;
  if ( (unsigned int)a3 <= *(_DWORD *)(*(_QWORD *)v8 + 16LL) )
    LODWORD(a2) = *(_DWORD *)(*(_QWORD *)v8 + 16LL);
  v25 = v11[1];
  if ( a6 )
  {
    if ( v25 == (_DWORD)a2 )
      goto LABEL_50;
    v20 = -1073741811;
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_116;
    v62 = -5;
LABEL_115:
    WPP_SF_sDsd(
      v26[2],
      (_DWORD)a2,
      (_DWORD)a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
      v62);
    goto LABEL_116;
  }
  if ( v25 != (_DWORD)a3 && v25 != (_DWORD)a2 )
  {
    v20 = -1073741811;
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_116;
    v62 = -13;
    goto LABEL_115;
  }
LABEL_50:
  v27 = 2 * v25 + 8;
  if ( a6 )
    v27 += v25;
  if ( v10 < v27 )
  {
    v20 = -1073741811;
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_116;
    v62 = 9;
    goto LABEL_115;
  }
  if ( !v14 )
  {
    KeyMagicForAlgId = MSCryptEcGetKeyMagicForAlgId(*(_DWORD *)(v12 + 8), (_DWORD)v8, a5, a6, (__int64)&P);
    v20 = KeyMagicForAlgId;
    if ( KeyMagicForAlgId < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)a2,
          (_DWORD)a3,
          (unsigned int)"Status",
          KeyMagicForAlgId,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          22);
      goto LABEL_116;
    }
    v14 = (int)P;
  }
  v29 = *v11;
  if ( *v11 != v14 && v29 != 1447314245 && v29 != 1346650949 && v29 != 1447772997 && v29 != 1347109701 )
  {
    v20 = -1073741811;
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_116;
    v62 = 38;
    goto LABEL_115;
  }
  v30 = AllocateGenericEccKey(&v66, &v64, a4, v12);
  v20 = v30;
  if ( v30 >= 0 )
  {
    v33 = v66;
    LODWORD(P) = 0;
    v34 = 0;
    v35 = (__int64 *)*((_QWORD *)v66 + 2);
    if ( !v35 )
    {
      v35 = (__int64 *)v8;
      *((_QWORD *)v66 + 2) = v8;
      v65 = 0;
    }
    v36 = (char *)(v11 + 2);
    v37 = *v35;
    v38 = v11 + 2;
    v39 = (unsigned int)(2 * v11[1]);
    if ( !(unsigned int)IsAllZeros(v38, v39) )
    {
      v44 = *(_DWORD *)(v37 + 12);
      if ( v43 > v44 )
      {
        v45 = (char *)SafeAllocaAllocateFromHeap(2 * v44);
        v13 = v45;
        if ( !v45 )
        {
          v20 = -1073741801;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v46,
              v47,
              (unsigned int)"Status",
              23,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
              77);
LABEL_109:
          v8 = v65;
          v12 = a1;
          goto LABEL_110;
        }
        v48 = *(unsigned int *)(v37 + 12);
        v34 = 2 * v48;
        memcpy_0(v45, v36, v48);
        v49 = v68;
        memcpy_0(&v13[*(unsigned int *)(v37 + 12)], &v36[v68[1]], *(unsigned int *)(v37 + 12));
        LODWORD(P) = 1;
LABEL_86:
        if ( a6 )
        {
          v50 = *(_DWORD *)(v37 + 16);
          v51 = &v36[2 * v49[1]];
        }
        else
        {
          v51 = 0;
          v50 = 0;
        }
        if ( (a7 & 0x20) == 0 || v51 && v13 )
        {
          v52 = BCryptFlagsToSymCryptKeyValidationFlags(a7, v40, v41, v42);
          v53 = 4096;
          if ( !a5 )
            v53 = 0x2000;
          v54 = SymCryptEckeyAllocate(*(_QWORD *)(v33[2] + 8LL));
          v33[3] = v54;
          if ( v54 )
          {
            v57 = SymCryptEckeySetValue(
                    (_DWORD)v51,
                    v50,
                    (_DWORD)v13,
                    v34,
                    (unsigned int)(*(_DWORD *)(*(_QWORD *)v33[2] + 4LL) != 3) + 1,
                    2,
                    v52 | (unsigned int)v53,
                    v54);
            if ( v57 )
            {
              v58 = SymcryptErrorCodeToNtStatus(v57);
              v20 = v58;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v59,
                  v60,
                  (unsigned int)"Status",
                  v58,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
                  136);
              }
            }
            else
            {
              *a8 = v33;
              v33 = 0;
            }
          }
          else
          {
            v20 = -1073741801;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v55,
                v56,
                (unsigned int)"Status",
                23,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
                120);
          }
        }
        else
        {
          v20 = -1073741811;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v40,
              v41,
              (unsigned int)"Status",
              13,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
              109);
        }
        if ( (_DWORD)P )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
        goto LABEL_109;
      }
      v13 = v36;
      v34 = v39;
    }
    v49 = v68;
    goto LABEL_86;
  }
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
    v33 = v66;
  }
  else
  {
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v31,
      v32,
      (unsigned int)"Status",
      v30,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
      45);
    v33 = v66;
  }
LABEL_110:
  if ( v33 )
    MSCryptEccDestroyKeyPair(v33);
LABEL_116:
  if ( !*(_QWORD *)(v12 + 16) && v8 )
    FreeGenericEccKeyParameters(v8);
  return v20;
}

```

## disassembly

```asm
0x180047c50  mov     rax, rsp
0x180047c53  mov     [rax+10h], rdx
0x180047c57  mov     [rax+8], rcx
0x180047c5b  push    rbx
0x180047c5c  push    r15
0x180047c5e  sub     rsp, 88h
0x180047c65  mov     r15, [rcx+10h]
0x180047c69  mov     [rax+18h], rbp
0x180047c6d  mov     ebp, r9d
0x180047c70  mov     [rax-18h], rsi
0x180047c74  mov     esi, r8d
0x180047c77  mov     [rax-20h], rdi
0x180047c7b  mov     rdi, rdx
0x180047c7e  mov     [rax-28h], r12
0x180047c82  mov     r12, rcx
0x180047c85  mov     [rax-30h], r13
0x180047c89  mov     [rax-38h], r14
0x180047c8d  xor     r14d, r14d
0x180047c90  mov     [rax-40h], r14
0x180047c94  mov     r10d, r14d
0x180047c97  mov     [rax-50h], r14d
0x180047c9b  mov     [rax-58h], r14d
0x180047c9f  mov     [rsp+98h+var_48], r15
0x180047ca4  test    r15, r15
0x180047ca7  jnz     loc_180047E9D
0x180047cad  mov     ecx, [rdx]
0x180047caf  mov     r15d, r14d
0x180047cb2  mov     [rax-58h], r14
0x180047cb6  mov     eax, r14d
0x180047cb9  mov     [rsp+98h+var_48], r14
0x180047cbe  cmp     ecx, 31534345h
0x180047cc4  jz      loc_180047D59
0x180047cca  cmp     ecx, 32534345h
0x180047cd0  jz      loc_180047D59
0x180047cd6  cmp     ecx, 314B4345h
0x180047cdc  jz      short loc_180047D59
0x180047cde  cmp     ecx, 324B4345h
0x180047ce4  jz      short loc_180047D59
0x180047ce6  mov     eax, 1
0x180047ceb  cmp     ecx, 33534345h
0x180047cf1  jz      short loc_180047D59
0x180047cf3  cmp     ecx, 34534345h
0x180047cf9  jz      short loc_180047D59
0x180047cfb  cmp     ecx, 334B4345h
0x180047d01  jz      short loc_180047D59
0x180047d03  cmp     ecx, 344B4345h
0x180047d09  jz      short loc_180047D59
0x180047d0b  mov     eax, 2
0x180047d10  cmp     ecx, 35534345h
0x180047d16  jz      short loc_180047D59
0x180047d18  cmp     ecx, 36534345h
0x180047d1e  jz      short loc_180047D59
0x180047d20  cmp     ecx, 354B4345h
0x180047d26  jz      short loc_180047D59
0x180047d28  cmp     ecx, 364B4345h
0x180047d2e  jz      short loc_180047D59
0x180047d30  mov     eax, 3
0x180047d35  cmp     ecx, 50444345h
0x180047d3b  jz      short loc_180047D59
0x180047d3d  cmp     ecx, 56444345h
0x180047d43  jz      short loc_180047D59
0x180047d45  cmp     ecx, 504B4345h
0x180047d4b  jz      short loc_180047D59
0x180047d4d  cmp     ecx, 564B4345h
0x180047d53  jnz     loc_180047E95
0x180047d59  lea     rax, [rax+rax*2]
0x180047d5d  add     rax, rax
0x180047d60  lea     r8, off_180084728; "nistP256"
0x180047d67  mov     r8, [r8+rax*8]
0x180047d6b  test    r8, r8
0x180047d6e  jz      loc_180047E95
0x180047d74  mov     r9, 0FFFFFFFFFFFFFFFFh
0x180047d7b  nop     dword ptr [rax+rax+00h]
0x180047d80  cmp     [r8+r9*2+2], r10w
0x180047d86  lea     r9, [r9+1]
0x180047d8a  jnz     short loc_180047D80
0x180047d8c  lea     r9d, ds:2[r9*2]
0x180047d94  mov     edx, 3000Bh
0x180047d99  lea     rcx, [rsp+98h+P]
0x180047d9e  call    LoadCurve
0x180047da3  mov     ebx, eax
0x180047da5  test    eax, eax
0x180047da7  jns     loc_180047E8B
0x180047dad  mov     rcx, cs:WPP_GLOBAL_Control
0x180047db4  lea     rdi, WPP_GLOBAL_Control
0x180047dbb  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180047dc2  cmp     rcx, rdi
0x180047dc5  jz      short loc_180047DF5
0x180047dc7  test    byte ptr [rcx+1Ch], 1
0x180047dcb  jz      short loc_180047DF5
0x180047dcd  mov     rcx, [rcx+10h]
0x180047dd1  lea     r9, aStatus; "Status"
0x180047dd8  mov     dword ptr [rsp+98h+var_68], 3EEh
0x180047de0  mov     [rsp+98h+var_70], rsi
0x180047de5  mov     dword ptr [rsp+98h+var_78], eax
0x180047de9  call    WPP_SF_sDsd
0x180047dee  mov     rcx, cs:WPP_GLOBAL_Control
0x180047df5  mov     r14, [rsp+98h+P]
0x180047dfa  test    r14, r14
0x180047dfd  jz      short loc_180047E62
0x180047dff  mov     rbp, [r14+8]
0x180047e03  test    rbp, rbp
0x180047e06  jz      short loc_180047E3D
0x180047e08  mov     edx, [rbp+28h]
0x180047e0b  mov     rcx, rbp
0x180047e0e  call    SymCryptWipeAsm
0x180047e13  mov     eax, [rbp-4]
0x180047e16  sub     rbp, rax
0x180047e19  jz      short loc_180047E39
0x180047e1b  mov     rcx, gs:60h
0x180047e24  mov     r8, rbp; P
0x180047e27  xor     edx, edx; Flags
0x180047e29  mov     rcx, [rcx+30h]; HeapHandle
0x180047e2d  call    cs:__imp_RtlFreeHeap
0x180047e34  nop     dword ptr [rax+rax+00h]
0x180047e39  mov     [r14+8], r15
0x180047e3d  mov     rcx, gs:60h
0x180047e46  mov     r8, r14; P
0x180047e49  xor     edx, edx; Flags
0x180047e4b  mov     rcx, [rcx+30h]; HeapHandle
0x180047e4f  call    cs:__imp_RtlFreeHeap
0x180047e56  nop     dword ptr [rax+rax+00h]
0x180047e5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180047e62  cmp     rcx, rdi
0x180047e65  jz      loc_1800483E2
0x180047e6b  test    byte ptr [rcx+1Ch], 1
0x180047e6f  jz      loc_1800483E2
0x180047e75  mov     dword ptr [rsp+98h+var_68], 7D5h
0x180047e7d  mov     [rsp+98h+var_70], rsi
0x180047e82  mov     dword ptr [rsp+98h+var_78], ebx
0x180047e86  jmp     loc_1800483D2
0x180047e8b  mov     r15, [rsp+98h+P]
0x180047e90  mov     [rsp+98h+var_48], r15
0x180047e95  mov     r10d, [rdi]
0x180047e98  mov     dword ptr [rsp+98h+P], r10d
0x180047e9d  cmp     esi, 8
0x180047ea0  jb      loc_180048398
0x180047ea6  test    r15, r15
0x180047ea9  jz      loc_180048398
0x180047eaf  mov     rax, [r15]
0x180047eb2  mov     r13d, [rsp+98h+arg_28]
0x180047eba  mov     r8d, [rax+0Ch]
0x180047ebe  mov     edx, r8d
0x180047ec1  cmp     r8d, [rax+10h]
0x180047ec5  cmovbe  edx, [rax+10h]
0x180047ec9  mov     eax, [rdi+4]
0x180047ecc  test    r13d, r13d
0x180047ecf  jnz     short loc_180047F0D
0x180047ed1  cmp     eax, r8d
0x180047ed4  jz      short loc_180047F44
0x180047ed6  cmp     eax, edx
0x180047ed8  jz      short loc_180047F44
0x180047eda  mov     ebx, 0C000000Dh
0x180047edf  mov     rcx, cs:WPP_GLOBAL_Control
0x180047ee6  lea     rdi, WPP_GLOBAL_Control
0x180047eed  cmp     rcx, rdi
0x180047ef0  jz      loc_1800483E2
0x180047ef6  test    byte ptr [rcx+1Ch], 1
0x180047efa  jz      loc_1800483E2
0x180047f00  mov     dword ptr [rsp+98h+var_68], 7F3h
0x180047f08  jmp     loc_1800483BE
0x180047f0d  cmp     eax, edx
0x180047f0f  jz      short loc_180047F44
0x180047f11  mov     ebx, 0C000000Dh
0x180047f16  mov     rcx, cs:WPP_GLOBAL_Control
0x180047f1d  lea     rdi, WPP_GLOBAL_Control
0x180047f24  cmp     rcx, rdi
0x180047f27  jz      loc_1800483E2
0x180047f2d  test    byte ptr [rcx+1Ch], 1
0x180047f31  jz      loc_1800483E2
0x180047f37  mov     dword ptr [rsp+98h+var_68], 7FBh
0x180047f3f  jmp     loc_1800483BE
0x180047f44  lea     ecx, ds:8[rax*2]
0x180047f4b  test    r13d, r13d
0x180047f4e  jz      short loc_180047F52
0x180047f50  add     ecx, eax
0x180047f52  cmp     esi, ecx
0x180047f54  jnb     short loc_180047F89
0x180047f56  mov     ebx, 0C000000Dh
0x180047f5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180047f62  lea     rdi, WPP_GLOBAL_Control
0x180047f69  cmp     rcx, rdi
0x180047f6c  jz      loc_1800483E2
0x180047f72  test    byte ptr [rcx+1Ch], 1
0x180047f76  jz      loc_1800483E2
0x180047f7c  mov     dword ptr [rsp+98h+var_68], 809h
0x180047f84  jmp     loc_1800483BE
0x180047f89  mov     esi, [rsp+98h+arg_20]
0x180047f90  test    r10d, r10d
0x180047f93  jnz     short loc_180047FFB
0x180047f95  mov     ecx, [r12+8]
0x180047f9a  lea     rax, [rsp+98h+P]
0x180047f9f  mov     r9d, r13d
0x180047fa2  mov     [rsp+98h+var_78], rax
0x180047fa7  mov     r8d, esi
0x180047faa  mov     rdx, r15
0x180047fad  call    MSCryptEcGetKeyMagicForAlgId
0x180047fb2  mov     ebx, eax
0x180047fb4  test    eax, eax
0x180047fb6  jns     short loc_180047FF6
0x180047fb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180047fbf  lea     rdi, WPP_GLOBAL_Control
0x180047fc6  cmp     rcx, rdi
0x180047fc9  jz      loc_1800483E2
0x180047fcf  test    byte ptr [rcx+1Ch], 1
0x180047fd3  jz      loc_1800483E2
0x180047fd9  mov     dword ptr [rsp+98h+var_68], 816h
0x180047fe1  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180047fe8  mov     [rsp+98h+var_70], rsi
0x180047fed  mov     dword ptr [rsp+98h+var_78], eax
0x180047ff1  jmp     loc_1800483D2
0x180047ff6  mov     r10d, dword ptr [rsp+98h+P]
0x180047ffb  mov     eax, [rdi]
0x180047ffd  cmp     eax, r10d
0x180048000  jz      short loc_180048051
0x180048002  cmp     eax, 56444345h
0x180048007  jz      short loc_180048051
0x180048009  cmp     eax, 50444345h
0x18004800e  jz      short loc_180048051
0x180048010  cmp     eax, 564B4345h
0x180048015  jz      short loc_180048051
0x180048017  cmp     eax, 504B4345h
0x18004801c  jz      short loc_180048051
0x18004801e  mov     ebx, 0C000000Dh
0x180048023  mov     rcx, cs:WPP_GLOBAL_Control
0x18004802a  lea     rdi, WPP_GLOBAL_Control
0x180048031  cmp     rcx, rdi
0x180048034  jz      loc_1800483E2
0x18004803a  test    byte ptr [rcx+1Ch], 1
0x18004803e  jz      loc_1800483E2
0x180048044  mov     dword ptr [rsp+98h+var_68], 826h
0x18004804c  jmp     loc_1800483BE
0x180048051  mov     r9, r12
0x180048054  lea     rdx, [rsp+98h+var_50]
0x180048059  mov     r8d, ebp
0x18004805c  lea     rcx, [rsp+98h+var_40]
0x180048061  call    AllocateGenericEccKey
0x180048066  mov     ebx, eax
0x180048068  test    eax, eax
0x18004806a  jns     short loc_1800480C1
0x18004806c  mov     rcx, cs:WPP_GLOBAL_Control
0x180048073  lea     rdi, WPP_GLOBAL_Control
0x18004807a  cmp     rcx, rdi
0x18004807d  jz      short loc_1800480B7
0x18004807f  test    byte ptr [rcx+1Ch], 1
0x180048083  jz      short loc_1800480B7
0x180048085  mov     rcx, [rcx+10h]
0x180048089  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180048090  mov     dword ptr [rsp+98h+var_68], 82Dh
0x180048098  lea     r9, aStatus; "Status"
0x18004809f  mov     [rsp+98h+var_70], rsi
0x1800480a4  mov     dword ptr [rsp+98h+var_78], eax
0x1800480a8  call    WPP_SF_sDsd
0x1800480ad  mov     rbp, [rsp+98h+var_40]
0x1800480b2  jmp     loc_180048380
0x1800480b7  mov     rbp, [rsp+98h+var_40]
0x1800480bc  jmp     loc_180048387
0x1800480c1  mov     rbp, [rsp+98h+var_40]
0x1800480c6  xor     ecx, ecx
0x1800480c8  mov     dword ptr [rsp+98h+P], ecx
0x1800480cc  mov     r12d, ecx
0x1800480cf  mov     rax, [rbp+10h]
0x1800480d3  test    rax, rax
0x1800480d6  jnz     short loc_1800480E4
0x1800480d8  mov     rax, r15
0x1800480db  mov     [rbp+10h], r15
0x1800480df  mov     [rsp+98h+var_48], rcx
0x1800480e4  mov     r11d, [rdi+4]
0x1800480e8  lea     rsi, [rdi+8]
0x1800480ec  mov     r15, [rax]
0x1800480ef  mov     rcx, rsi
0x1800480f2  lea     edi, [r11+r11]
0x1800480f6  mov     edx, edi
0x1800480f8  call    IsAllZeros
0x1800480fd  test    eax, eax
0x1800480ff  jnz     loc_1800481B7
0x180048105  mov     eax, [r15+0Ch]
0x180048109  cmp     r11d, eax
0x18004810c  jbe     loc_1800481B1
0x180048112  lea     ecx, [rax+rax]
0x180048115  call    SafeAllocaAllocateFromHeap
0x18004811a  mov     r14, rax
0x18004811d  test    rax, rax
0x180048120  jnz     short loc_180048179
0x180048122  mov     ebx, 0C0000017h
0x180048127  mov     rcx, cs:WPP_GLOBAL_Control
0x18004812e  lea     rdi, WPP_GLOBAL_Control
0x180048135  cmp     rcx, rdi
0x180048138  jz      loc_180048373
0x18004813e  test    byte ptr [rcx+1Ch], 1
0x180048142  jz      loc_180048373
0x180048148  mov     rcx, [rcx+10h]
0x18004814c  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180048153  mov     dword ptr [rsp+98h+var_68], 84Dh
0x18004815b  lea     r9, aStatus; "Status"
0x180048162  mov     [rsp+98h+var_70], rsi
0x180048167  mov     dword ptr [rsp+98h+var_78], 0C0000017h
0x18004816f  call    WPP_SF_sDsd
0x180048174  jmp     loc_180048373
0x180048179  mov     r8d, [r15+0Ch]; Size
  ... truncated ...
```
