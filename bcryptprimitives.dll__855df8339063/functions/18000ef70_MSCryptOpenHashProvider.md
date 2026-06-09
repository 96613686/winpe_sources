# MSCryptOpenHashProvider

- ea: `0x18000ef70`
- end: `0x18000f442`
- name: `MSCryptOpenHashProvider`
- size: `1234`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f450`
- `0x1800117d0`
- `0x180012ff4`
- `0x180053de4`
- `0x180058a04`
- `0x18007dd2c`
- `0x18007ebb4`

## callees

- `0x18000ee60`
- `0x18000ef70`
- `0x18007f765`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000f127`
- `ntdll!RtlAllocateHeap` at `0x18000f127`

## string_xrefs

- `0x18000f0aa`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18000f1f1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18000f2c2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18000f33d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18000f3b0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18000f40e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptOpenHashProvider(_QWORD *a1, const wchar_t *a2, int a3)
{
  char v3; // bl
  char v6; // si
  unsigned int v7; // r12d
  int v8; // ebx
  __int64 v9; // r11
  const wchar_t *v10; // rax
  __int64 v11; // r9
  int v12; // ecx
  int v13; // edx
  __int64 v14; // r10
  const wchar_t *v15; // rax
  __int64 v16; // r9
  __int64 v17; // r8
  int v18; // ecx
  int v19; // edx
  unsigned int v20; // ebx
  int v21; // ebx
  __int64 v22; // rdi
  _OWORD *Heap; // rax
  int v24; // edx
  BOOL v25; // edx
  BOOL v26; // ecx
  int v28; // edx
  int v29; // r8d
  int v30; // edx

  v3 = a3;
  if ( (a3 & 0xFFFFFF92) != 0 )
  {
    v20 = -1073741811;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v20;
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
      12);
    return 3221225485LL;
  }
  if ( !a1 )
  {
    v20 = -1073741811;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v20;
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
      19);
    return 3221225485LL;
  }
  if ( !a2 )
  {
    v20 = -1073741811;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v20;
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0,
      a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
      26);
    return 3221225485LL;
  }
  v6 = a3 & 0xF7;
  if ( wcscmp_0(a2, L"AES-CMAC") )
    v6 = v3;
  if ( (v6 & 0x40) != 0
    && (!wcscmp_0(a2, L"CSHAKE128")
     || !wcscmp_0(a2, L"CSHAKE256")
     || !wcscmp_0(a2, L"KMAC128")
     || !wcscmp_0(a2, L"KMAC256")) )
  {
    v20 = -1073741637;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v28,
        v29,
        (unsigned int)"Status",
        187,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
        45);
    return v20;
  }
  v7 = 26;
  v8 = (v6 & 8) != 0;
  v9 = 0;
  while ( 1 )
  {
    v10 = a2;
    v11 = 12 * v9;
    do
    {
      v12 = *(const wchar_t *)((char *)v10 + rgHashAlgorithmDefaults[12 * v9 + 7] - (_QWORD)a2);
      v13 = *v10 - v12;
      if ( v13 )
        break;
      ++v10;
    }
    while ( v12 );
    if ( !v13 )
    {
      if ( v8 == LODWORD(rgHashAlgorithmDefaults[v11 + 8]) )
        goto LABEL_28;
      if ( (v6 & 8) != 0 && HIDWORD(rgHashAlgorithmDefaults[v11 + 8]) )
        v7 = v9;
    }
    v14 = (unsigned int)(v9 + 1);
    v15 = a2;
    v16 = 12 * v14;
    v17 = rgHashAlgorithmDefaults[12 * v14 + 7] - (_QWORD)a2;
    do
    {
      v18 = *(const wchar_t *)((char *)v15 + v17);
      v19 = *v15 - v18;
      if ( v19 )
        break;
      ++v15;
    }
    while ( v18 );
    if ( v19 )
      goto LABEL_16;
    if ( v8 == LODWORD(rgHashAlgorithmDefaults[v16 + 8]) )
      break;
    if ( (v6 & 8) != 0 && HIDWORD(rgHashAlgorithmDefaults[v16 + 8]) )
      v7 = v9 + 1;
LABEL_16:
    v9 = (unsigned int)(v9 + 2);
    if ( (unsigned int)v9 >= 0x1A )
      goto LABEL_17;
  }
  if ( (unsigned int)v14 < 0x1A )
  {
    LODWORD(v9) = v9 + 1;
    goto LABEL_28;
  }
LABEL_17:
  if ( v7 >= 0x1A )
  {
    v20 = -1073741637;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v19,
        v17,
        (unsigned int)"Status",
        187,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
        57);
    return v20;
  }
  LODWORD(v9) = v7;
LABEL_28:
  v21 = v6 & 4;
  if ( (v6 & 4) != 0
    && ((v30 = rgHashAlgorithmDefaults[12 * (unsigned int)v9 + 1], ((v30 - 131081) & 0xFFFFFFFC) != 0) || v30 == 131082) )
  {
    return (unsigned int)-1073741637;
  }
  else
  {
    v22 = 12LL * (unsigned int)v9;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, LODWORD(rgHashAlgorithmDefaults[v22]));
    if ( Heap )
    {
      *Heap = *(_OWORD *)&rgHashAlgorithmDefaults[v22];
      Heap[1] = *(_OWORD *)&rgHashAlgorithmDefaults[v22 + 2];
      Heap[2] = *(_OWORD *)&rgHashAlgorithmDefaults[v22 + 4];
      *((_QWORD *)Heap + 6) = rgHashAlgorithmDefaults[v22 + 6];
      *((_DWORD *)Heap + 9) = v6 & 1;
      v25 = (v6 & 0x40) != 0;
      *((_DWORD *)Heap + 11) = v25;
      v26 = v21 != 0;
      *((_BYTE *)Heap + 48) = v21 != 0;
      if ( (v6 & 0x20) != 0 )
        v26 = 1;
      *((_DWORD *)Heap + 10) = v25 || v26;
      if ( (v6 & 8) != 0 && !LODWORD(rgHashAlgorithmDefaults[v22 + 8]) )
        *((_DWORD *)Heap + 13) = 1;
      *a1 = Heap;
      return 0;
    }
    else
    {
      v20 = -1073741801;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v24,
          0,
          (unsigned int)"Status",
          23,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
          77);
    }
  }
  return v20;
}

```

## disassembly

```asm
0x18000ef70  push    rbx
0x18000ef72  push    rdi
0x18000ef73  push    r14
0x18000ef75  sub     rsp, 50h
0x18000ef79  mov     ebx, r8d
0x18000ef7c  mov     rdi, rdx
0x18000ef7f  mov     r14, rcx
0x18000ef82  test    r8d, 0FFFFFF92h
0x18000ef89  jnz     loc_18000F313
0x18000ef8f  test    rcx, rcx
0x18000ef92  jz      loc_18000F386
0x18000ef98  test    rdx, rdx
0x18000ef9b  jz      loc_18000F3E4
0x18000efa1  mov     [rsp+68h+arg_8], rsi
0x18000efa6  lea     rdx, aAesCmac_0; "AES-CMAC"
0x18000efad  mov     rcx, rdi; String1
0x18000efb0  mov     [rsp+68h+var_28], r15
0x18000efb5  call    wcscmp_0
0x18000efba  mov     esi, ebx
0x18000efbc  and     esi, 0FFFFFFF7h
0x18000efbf  test    eax, eax
0x18000efc1  cmovnz  esi, ebx
0x18000efc4  mov     r15d, esi
0x18000efc7  and     r15d, 40h
0x18000efcb  jnz     loc_18000F248
0x18000efd1  mov     [rsp+68h+arg_0], rbp
0x18000efd6  xor     ebx, ebx
0x18000efd8  mov     [rsp+68h+arg_10], r12
0x18000efe0  mov     ebp, esi
0x18000efe2  and     ebp, 8
0x18000efe5  mov     [rsp+68h+var_20], r13
0x18000efea  mov     r12d, 1Ah
0x18000eff0  lea     r13, rgHashAlgorithmDefaults
0x18000eff7  setnz   bl
0x18000effa  xor     r11d, r11d
0x18000effd  nop     dword ptr [rax]
0x18000f000  lea     r9, [r11+r11*2]
0x18000f004  mov     rax, rdi
0x18000f007  shl     r9, 5
0x18000f00b  mov     r8, [r9+r13+38h]
0x18000f010  sub     r8, rdi
0x18000f013  movzx   edx, word ptr [rax]
0x18000f016  movzx   ecx, word ptr [rax+r8]
0x18000f01b  sub     edx, ecx
0x18000f01d  jnz     short loc_18000F027
0x18000f01f  add     rax, 2
0x18000f023  test    ecx, ecx
0x18000f025  jnz     short loc_18000F013
0x18000f027  test    edx, edx
0x18000f029  jz      loc_18000F0C3
0x18000f02f  lea     r10d, [r11+1]
0x18000f033  mov     rax, rdi
0x18000f036  lea     r9, [r10+r10*2]
0x18000f03a  shl     r9, 5
0x18000f03e  mov     r8, [r9+r13+38h]
0x18000f043  sub     r8, rdi
0x18000f046  nop     word ptr [rax+rax+00000000h]
0x18000f050  movzx   edx, word ptr [rax]
0x18000f053  movzx   ecx, word ptr [rax+r8]
0x18000f058  sub     edx, ecx
0x18000f05a  jnz     short loc_18000F064
0x18000f05c  add     rax, 2
0x18000f060  test    ecx, ecx
0x18000f062  jnz     short loc_18000F050
0x18000f064  test    edx, edx
0x18000f066  jz      short loc_18000F0E6
0x18000f068  add     r11d, 2
0x18000f06c  cmp     r11d, 1Ah
0x18000f070  jb      short loc_18000F000
0x18000f072  cmp     r12d, 1Ah
0x18000f076  jb      loc_18000F37E
0x18000f07c  mov     ebx, 0C00000BBh
0x18000f081  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f088  lea     rax, WPP_GLOBAL_Control
0x18000f08f  cmp     rcx, rax
0x18000f092  jz      loc_18000F1A3
0x18000f098  test    byte ptr [rcx+1Ch], 1
0x18000f09c  jz      loc_18000F1A3
0x18000f0a2  mov     [rsp+68h+var_38], 339h
0x18000f0aa  lea     rax, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f0b1  mov     [rsp+68h+var_40], rax
0x18000f0b6  mov     [rsp+68h+var_48], 0C00000BBh
0x18000f0be  jmp     loc_18000F205
0x18000f0c3  cmp     ebx, [r9+r13+40h]
0x18000f0c8  jz      short loc_18000F0FE
0x18000f0ca  test    ebp, ebp
0x18000f0cc  jz      loc_18000F02F
0x18000f0d2  cmp     dword ptr [r9+r13+44h], 0
0x18000f0d8  jz      loc_18000F02F
0x18000f0de  mov     r12d, r11d
0x18000f0e1  jmp     loc_18000F02F
0x18000f0e6  cmp     ebx, [r9+r13+40h]
0x18000f0eb  jnz     loc_18000F22C
0x18000f0f1  cmp     r10d, 1Ah
0x18000f0f5  jnb     loc_18000F072
0x18000f0fb  mov     r11d, r10d
0x18000f0fe  mov     ebx, esi
0x18000f100  mov     ecx, r11d
0x18000f103  and     ebx, 4
0x18000f106  jnz     loc_18000F2EF
0x18000f10c  lea     rdi, [rcx+rcx*2]
0x18000f110  xor     edx, edx; Flags
0x18000f112  mov     rcx, gs:60h
0x18000f11b  shl     rdi, 5
0x18000f11f  mov     rcx, [rcx+30h]; HeapHandle
0x18000f123  mov     r8d, [rdi+r13]; Size
0x18000f127  call    cs:__imp_RtlAllocateHeap
0x18000f12e  nop     dword ptr [rax+rax+00h]
0x18000f133  mov     r8, rax
0x18000f136  test    rax, rax
0x18000f139  jz      loc_18000F1CB
0x18000f13f  movups  xmm0, xmmword ptr [rdi+r13]
0x18000f144  xor     edx, edx
0x18000f146  movups  xmmword ptr [rax], xmm0
0x18000f149  movups  xmm1, xmmword ptr [rdi+r13+10h]
0x18000f14f  movups  xmmword ptr [rax+10h], xmm1
0x18000f153  movups  xmm0, xmmword ptr [rdi+r13+20h]
0x18000f159  movups  xmmword ptr [rax+20h], xmm0
0x18000f15d  movsd   xmm1, qword ptr [rdi+r13+30h]
0x18000f164  movsd   qword ptr [rax+30h], xmm1
0x18000f169  mov     eax, esi
0x18000f16b  and     eax, 1
0x18000f16e  test    r15d, r15d
0x18000f171  mov     [r8+24h], eax
0x18000f175  setnz   dl
0x18000f178  test    ebx, ebx
0x18000f17a  mov     [r8+2Ch], edx
0x18000f17e  setnz   al
0x18000f181  test    sil, 20h
0x18000f185  movzx   ecx, al
0x18000f188  mov     [r8+30h], al
0x18000f18c  mov     eax, 1
0x18000f191  cmovnz  ecx, eax
0x18000f194  or      ecx, edx
0x18000f196  mov     [r8+28h], ecx
0x18000f19a  test    ebp, ebp
0x18000f19c  jnz     short loc_18000F217
0x18000f19e  mov     [r14], r8
0x18000f1a1  xor     ebx, ebx
0x18000f1a3  mov     r13, [rsp+68h+var_20]
0x18000f1a8  mov     r12, [rsp+68h+arg_10]
0x18000f1b0  mov     rbp, [rsp+68h+arg_0]
0x18000f1b5  mov     rsi, [rsp+68h+arg_8]
0x18000f1ba  mov     r15, [rsp+68h+var_28]
0x18000f1bf  mov     eax, ebx
0x18000f1c1  add     rsp, 50h
0x18000f1c5  pop     r14
0x18000f1c7  pop     rdi
0x18000f1c8  pop     rbx
0x18000f1c9  retn
0x18000f1cb  mov     ebx, 0C0000017h
0x18000f1d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f1d7  lea     rax, WPP_GLOBAL_Control
0x18000f1de  cmp     rcx, rax
0x18000f1e1  jz      short loc_18000F1A3
0x18000f1e3  test    byte ptr [rcx+1Ch], 1
0x18000f1e7  jz      short loc_18000F1A3
0x18000f1e9  mov     [rsp+68h+var_38], 34Dh
0x18000f1f1  lea     rax, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f1f8  mov     [rsp+68h+var_40], rax
0x18000f1fd  mov     [rsp+68h+var_48], 0C0000017h
0x18000f205  mov     rcx, [rcx+10h]
0x18000f209  lea     r9, aStatus; "Status"
0x18000f210  call    WPP_SF_sDsd
0x18000f215  jmp     short loc_18000F1A3
0x18000f217  cmp     dword ptr [rdi+r13+40h], 0
0x18000f21d  jnz     loc_18000F19E
0x18000f223  mov     [r8+34h], eax
0x18000f227  jmp     loc_18000F19E
0x18000f22c  test    ebp, ebp
0x18000f22e  jz      loc_18000F068
0x18000f234  cmp     dword ptr [r9+r13+44h], 0
0x18000f23a  jz      loc_18000F068
0x18000f240  mov     r12d, r10d
0x18000f243  jmp     loc_18000F068
0x18000f248  lea     rdx, aCshake128_0; "CSHAKE128"
0x18000f24f  mov     rcx, rdi; String1
0x18000f252  call    wcscmp_0
0x18000f257  test    eax, eax
0x18000f259  jz      short loc_18000F298
0x18000f25b  lea     rdx, aCshake256_0; "CSHAKE256"
0x18000f262  mov     rcx, rdi; String1
0x18000f265  call    wcscmp_0
0x18000f26a  test    eax, eax
0x18000f26c  jz      short loc_18000F298
0x18000f26e  lea     rdx, aKmac128_0; "KMAC128"
0x18000f275  mov     rcx, rdi; String1
0x18000f278  call    wcscmp_0
0x18000f27d  test    eax, eax
0x18000f27f  jz      short loc_18000F298
0x18000f281  lea     rdx, aKmac256_0; "KMAC256"
0x18000f288  mov     rcx, rdi; String1
0x18000f28b  call    wcscmp_0
0x18000f290  test    eax, eax
0x18000f292  jnz     loc_18000EFD1
0x18000f298  mov     ebx, 0C00000BBh
0x18000f29d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2a4  lea     rax, WPP_GLOBAL_Control
0x18000f2ab  cmp     rcx, rax
0x18000f2ae  jz      loc_18000F1B5
0x18000f2b4  test    byte ptr [rcx+1Ch], 1
0x18000f2b8  jz      loc_18000F1B5
0x18000f2be  mov     rcx, [rcx+10h]
0x18000f2c2  lea     rax, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f2c9  mov     [rsp+68h+var_38], 32Dh
0x18000f2d1  lea     r9, aStatus; "Status"
0x18000f2d8  mov     [rsp+68h+var_40], rax
0x18000f2dd  mov     [rsp+68h+var_48], 0C00000BBh
0x18000f2e5  call    WPP_SF_sDsd
0x18000f2ea  jmp     loc_18000F1B5
0x18000f2ef  lea     rax, [rcx+rcx*2]
0x18000f2f3  shl     rax, 5
0x18000f2f7  mov     edx, [rax+r13+8]
0x18000f2fc  lea     eax, [rdx-20009h]
0x18000f302  test    eax, 0FFFFFFFCh
0x18000f307  jz      short loc_18000F371
0x18000f309  mov     ebx, 0C00000BBh
0x18000f30e  jmp     loc_18000F1A3
0x18000f313  mov     ebx, 0C000000Dh
0x18000f318  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f31f  lea     rax, WPP_GLOBAL_Control
0x18000f326  cmp     rcx, rax
0x18000f329  jz      loc_18000F1BF
0x18000f32f  test    byte ptr [rcx+1Ch], 1
0x18000f333  jz      loc_18000F1BF
0x18000f339  mov     rcx, [rcx+10h]
0x18000f33d  lea     rax, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f344  mov     [rsp+68h+var_38], 30Ch
0x18000f34c  lea     r9, aStatus; "Status"
0x18000f353  mov     [rsp+68h+var_40], rax
0x18000f358  mov     [rsp+68h+var_48], 0C000000Dh
0x18000f360  call    WPP_SF_sDsd
0x18000f365  mov     eax, ebx
0x18000f367  add     rsp, 50h
0x18000f36b  pop     r14
0x18000f36d  pop     rdi
0x18000f36e  pop     rbx
0x18000f36f  retn
0x18000f371  cmp     edx, 2000Ah
0x18000f377  jz      short loc_18000F309
0x18000f379  jmp     loc_18000F10C
0x18000f37e  mov     r11d, r12d
0x18000f381  jmp     loc_18000F0FE
0x18000f386  mov     ebx, 0C000000Dh
0x18000f38b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f392  lea     rax, WPP_GLOBAL_Control
0x18000f399  cmp     rcx, rax
0x18000f39c  jz      loc_18000F1BF
0x18000f3a2  test    byte ptr [rcx+1Ch], 1
0x18000f3a6  jz      loc_18000F1BF
0x18000f3ac  mov     rcx, [rcx+10h]
0x18000f3b0  lea     rax, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f3b7  mov     [rsp+68h+var_38], 313h
0x18000f3bf  lea     r9, aStatus; "Status"
0x18000f3c6  mov     [rsp+68h+var_40], rax
0x18000f3cb  mov     [rsp+68h+var_48], 0C000000Dh
0x18000f3d3  call    WPP_SF_sDsd
0x18000f3d8  mov     eax, ebx
0x18000f3da  add     rsp, 50h
0x18000f3de  pop     r14
0x18000f3e0  pop     rdi
0x18000f3e1  pop     rbx
0x18000f3e2  retn
0x18000f3e4  mov     ebx, 0C000000Dh
0x18000f3e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f3f0  lea     rax, WPP_GLOBAL_Control
0x18000f3f7  cmp     rcx, rax
0x18000f3fa  jz      loc_18000F1BF
0x18000f400  test    byte ptr [rcx+1Ch], 1
0x18000f404  jz      loc_18000F1BF
0x18000f40a  mov     rcx, [rcx+10h]
0x18000f40e  lea     rax, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f415  mov     [rsp+68h+var_38], 31Ah
0x18000f41d  lea     r9, aStatus; "Status"
0x18000f424  mov     [rsp+68h+var_40], rax
0x18000f429  mov     [rsp+68h+var_48], 0C000000Dh
0x18000f431  call    WPP_SF_sDsd
0x18000f436  mov     eax, ebx
0x18000f438  add     rsp, 50h
0x18000f43c  pop     r14
0x18000f43e  pop     rdi
0x18000f43f  pop     rbx
0x18000f440  retn
```
