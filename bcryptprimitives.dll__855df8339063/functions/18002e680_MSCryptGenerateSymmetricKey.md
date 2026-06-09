# MSCryptGenerateSymmetricKey

- ea: `0x18002e680`
- end: `0x18002eb7c`
- name: `MSCryptGenerateSymmetricKey`
- size: `1276`
- prototype: `__int64 __fastcall(int, int, int, int, void *Src, size_t Size, int)`
- caller_count: `4`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x18000c860`
- `0x18002cd40`
- `0x18002d2e0`
- `0x180067358`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x18002cc50`
- `0x18002d800`
- `0x18002e570`
- `0x18002e680`
- `0x18002eb90`
- `0x18002f2e0`
- `0x1800303b0`
- `0x180031910`
- `0x180034380`
- `0x1800536b0`
- `0x1800593e0`
- `0x180063170`
- `0x1800631a8`
- `0x1800710b0`

## string_xrefs

- `0x18002e908`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18002e9e5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18002ea9f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

## pseudocode

```c
__int64 __fastcall MSCryptGenerateSymmetricKey(
        _DWORD *a1,
        _QWORD *a2,
        __int64 a3,
        unsigned int a4,
        char *Src,
        size_t Size,
        int a7)
{
  unsigned int v8; // esi
  __int64 v9; // rbx
  unsigned int v10; // r14d
  int v11; // r10d
  __int64 v12; // rdx
  unsigned int v13; // r9d
  __int64 v14; // r9
  __int64 v15; // r14
  int v16; // eax
  int v17; // edx
  __int64 v18; // r8
  int v19; // r15d
  int v21; // eax
  unsigned __int64 v22; // rbp
  __int128 *v23; // r13
  __int64 v24; // rdi
  int v25; // eax
  unsigned int v26; // r12d
  __int64 v27; // r8
  __int64 v28; // r8
  __int64 v29; // r8
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rcx
  __int64 v33; // r8
  __int128 *v34; // [rsp+40h] [rbp-58h] BYREF
  _QWORD v35[10]; // [rsp+48h] [rbp-50h] BYREF

  v8 = a4;
  v9 = a3;
  if ( (a7 & 0xFFFFFE5F) != 0 )
  {
    v31 = 474;
    goto LABEL_65;
  }
  if ( !a1 || a1[1] != 1297306433 )
  {
    v26 = -1073741816;
LABEL_32:
    SymCryptWipeAsm(v9, v8);
    return v26;
  }
  if ( !a3 )
  {
    v26 = -1073741811;
    goto LABEL_32;
  }
  if ( (a7 & 0x20) != 0 && (a1[2] != 65538 || a1[3] != 5) )
  {
    v31 = 497;
LABEL_65:
    v26 = -1073741811;
    v32 = 3221225485LL;
LABEL_50:
    DebugTraceError(v32, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", v31);
    goto LABEL_32;
  }
  if ( a4 >= 0xC80 )
    v8 = 3200;
  if ( v8 < a1[7] && (a1[2] != 65538 || a1[3] != 5 || v8 < 0x250) )
  {
    v26 = -1073741789;
    goto LABEL_32;
  }
  v10 = Size;
  *(_DWORD *)a3 = v8;
  *(_DWORD *)(a3 + 4) = 1297306443;
  *(_DWORD *)(a3 + 8) = a1[2];
  *(_DWORD *)(a3 + 12) = a1[3];
  *(_DWORD *)(a3 + 16) = a1[4];
  *(_DWORD *)(a3 + 20) = a1[5];
  *(_DWORD *)(a3 + 24) = a1[6];
  *(_DWORD *)(a3 + 28) = 0;
  *(_QWORD *)(a3 + 32) = a1;
  v11 = a1[2];
  v12 = 112LL * ((unsigned int)(unsigned __int16)v11 - 1);
  if ( (a7 & 0x80u) != 0 )
  {
    if ( (unsigned int)Size > *(_DWORD *)((char *)&qword_180084108[1] + v12 + 4) )
      goto LABEL_34;
  }
  else if ( (unsigned int)Size >= *(_DWORD *)((char *)qword_180084108 + v12 + 4) )
  {
    v10 = *(_DWORD *)((char *)qword_180084108 + v12 + 4);
  }
  v13 = *(_DWORD *)((char *)qword_180084108 + v12);
  if ( v10 < v13
    || (LODWORD(a3) = *(_DWORD *)((char *)&qword_180084108[1] + v12), (_DWORD)a3)
    && (LODWORD(v12) = (v10 - v13) % (unsigned int)a3, (_DWORD)v12) )
  {
LABEL_34:
    v26 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        48);
    goto LABEL_32;
  }
  if ( (a7 & 0x100) != 0
    && (v11 != 65544 || g_fSelftest && !memcmp_0(Src, &Src[(unsigned __int64)v10 >> 1], (unsigned __int64)v10 >> 1)) )
  {
    v31 = 571;
    goto LABEL_65;
  }
  *(_DWORD *)(v9 + 56) = v10;
  memcpy_0((void *)(v9 + 60), Src, v10);
  *(_DWORD *)(v9 + 24) = 8 * v10;
  v15 = v9 + 40;
  *(_OWORD *)(v9 + 40) = 0;
  v16 = a1[2];
  if ( v16 != 65538 )
  {
    switch ( v16 )
    {
      case 65537:
        v19 = SymCryptRc4Init(v9 + 320, v9 + 60, *(unsigned int *)(v9 + 56));
        goto LABEL_19;
      case 65539:
        v29 = *(unsigned int *)(v9 + 56);
        *(_DWORD *)(v9 + 24) = 56;
        v19 = SymCryptDesExpandKey(v9 + 80, v9 + 60, v29);
        goto LABEL_19;
      case 65540:
        v33 = *(unsigned int *)(v9 + 56);
        *(_DWORD *)(v9 + 24) = 184;
        v19 = SymCryptDesxExpandKey(v9 + 96, v9 + 60, v33);
        goto LABEL_19;
      case 65541:
        v28 = *(unsigned int *)(v9 + 56);
        *(_DWORD *)(v9 + 24) = 168;
        v19 = SymCrypt3DesExpandKey(v9 + 96, v9 + 60, v28);
        goto LABEL_19;
      case 65542:
        v30 = *(unsigned int *)(v9 + 56);
        *(_DWORD *)(v9 + 24) = 112;
        v19 = SymCrypt3DesExpandKey(v9 + 80, v9 + 60, v30);
        goto LABEL_19;
      case 65543:
        v27 = *(unsigned int *)(v9 + 56);
        *(_DWORD *)(v9 + 336) = a1[9];
        *(_DWORD *)(v9 + 24) = a1[9];
        v19 = SymCryptRc2ExpandKeyEx(v9 + 192, v9 + 60, v27);
        goto LABEL_19;
      case 65544:
        *(_DWORD *)(v9 + 24) >>= 1;
        v19 = SymCryptXtsAesExpandKey(v9 + 128, v9 + 60, *(unsigned int *)(v9 + 56));
        goto LABEL_19;
      case 65545:
        goto LABEL_20;
      default:
        v26 = -1073741637;
        v31 = 741;
        v32 = 3221225659LL;
        goto LABEL_50;
    }
  }
  LOBYTE(v14) = 1;
  v19 = SymCryptAesExpandKeyInternal(v9 + 96, v9 + 60, *(unsigned int *)(v9 + 56), v14);
  if ( !v19 )
  {
    if ( *(_DWORD *)(v9 + 12) != 5 )
      goto LABEL_19;
    if ( *(_DWORD *)v9 >= 0xC80u )
    {
      v21 = SymCryptGcmExpandKey(v9 + 592, SymCryptAesBlockCipher_Fast, v9 + 60, *(unsigned int *)(v9 + 56));
      *(_DWORD *)(v9 + 28) |= 1u;
      v19 = v21;
    }
  }
  if ( *(_DWORD *)(v9 + 12) == 5 && (a7 & 0x20) != 0 )
  {
    *(_DWORD *)(v9 + 28) |= 2u;
    v34 = 0;
    v22 = 12;
    v35[0] = 0;
    AesRNGState_select(&v34, v17, v18);
    v23 = v34;
    do
    {
      v24 = 0x10000;
      if ( v22 < 0x10000 )
        v24 = v22;
      v25 = AesRNGState_generate(v23, v15, v24, v35);
      v15 += v24;
      v26 = v25;
      v22 -= v24;
    }
    while ( v22 );
    if ( v25 < 0 )
      goto LABEL_32;
  }
LABEL_19:
  if ( v19 )
  {
    v26 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        v18,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        237);
    goto LABEL_32;
  }
LABEL_20:
  if ( a2 )
    *a2 = v9;
  return 0;
}

```

## disassembly

```asm
0x18002e680  mov     [rsp+arg_8], rdx
0x18002e685  push    rbx
0x18002e686  push    rbp
0x18002e687  push    rsi
0x18002e688  push    rdi
0x18002e689  push    r12
0x18002e68b  push    r13
0x18002e68d  push    r14
0x18002e68f  push    r15
0x18002e691  sub     rsp, 58h
0x18002e695  mov     rdi, rcx
0x18002e698  mov     esi, r9d
0x18002e69b  mov     ecx, [rsp+98h+arg_30]
0x18002e6a2  mov     rbx, r8
0x18002e6a5  test    ecx, 0FFFFFE5Fh
0x18002e6ab  jnz     loc_18002EA7C
0x18002e6b1  test    rdi, rdi
0x18002e6b4  jz      loc_18002EA12
0x18002e6ba  cmp     dword ptr [rdi+4], 4D535341h
0x18002e6c1  jnz     loc_18002EA12
0x18002e6c7  test    rbx, rbx
0x18002e6ca  jz      loc_18002EAB0
0x18002e6d0  mov     ebp, ecx
0x18002e6d2  and     ebp, 20h
0x18002e6d5  jnz     loc_18002EABB
0x18002e6db  mov     eax, 0C80h
0x18002e6e0  cmp     esi, eax
0x18002e6e2  cmovnb  esi, eax
0x18002e6e5  cmp     esi, [rdi+1Ch]
0x18002e6e8  jb      loc_18002EAD7
0x18002e6ee  mov     r14d, dword ptr [rsp+98h+Size]
0x18002e6f6  lea     r15, cs:180000000h
0x18002e6fd  mov     [r8], esi
0x18002e700  mov     dword ptr [r8+4], 4D53534Bh
0x18002e708  mov     eax, [rdi+8]
0x18002e70b  mov     [r8+8], eax
0x18002e70f  mov     eax, [rdi+0Ch]
0x18002e712  mov     [r8+0Ch], eax
0x18002e716  mov     eax, [rdi+10h]
0x18002e719  mov     [r8+10h], eax
0x18002e71d  mov     eax, [rdi+14h]
0x18002e720  mov     [r8+14h], eax
0x18002e724  mov     eax, [rdi+18h]
0x18002e727  mov     [r8+18h], eax
0x18002e72b  mov     dword ptr [r8+1Ch], 0
0x18002e733  mov     [r8+20h], rdi
0x18002e737  mov     r10d, [rdi+8]
0x18002e73b  movzx   eax, r10w
0x18002e73f  dec     eax
0x18002e741  imul    rdx, rax, 70h ; 'p'
0x18002e745  test    cl, cl
0x18002e747  js      loc_18002E8D4
0x18002e74d  mov     eax, [rdx+r15+8410Ch]
0x18002e755  cmp     r14d, eax
0x18002e758  jb      short loc_18002E75D
0x18002e75a  mov     r14d, eax
0x18002e75d  mov     r9d, [rdx+r15+84108h]
0x18002e765  cmp     r14d, r9d
0x18002e768  jb      loc_18002E8E5
0x18002e76e  mov     r8d, [rdx+r15+84110h]
0x18002e776  test    r8d, r8d
0x18002e779  jz      short loc_18002E78E
0x18002e77b  xor     edx, edx
0x18002e77d  mov     eax, r14d
0x18002e780  sub     eax, r9d
0x18002e783  div     r8d
0x18002e786  test    edx, edx
0x18002e788  jnz     loc_18002E8E5
0x18002e78e  mov     r13, [rsp+98h+Src]
0x18002e796  bt      ecx, 8
0x18002e79a  jb      loc_18002EAFF
0x18002e7a0  mov     r8d, r14d; Size
0x18002e7a3  lea     rcx, [rbx+3Ch]; void *
0x18002e7a7  mov     rdx, r13; Src
0x18002e7aa  mov     [rbx+38h], r14d
0x18002e7ae  call    memcpy_0
0x18002e7b3  lea     eax, ds:0[r14*8]
0x18002e7bb  xorps   xmm0, xmm0
0x18002e7be  mov     [rbx+18h], eax
0x18002e7c1  lea     r14, [rbx+28h]
0x18002e7c5  movups  xmmword ptr [r14], xmm0
0x18002e7c9  mov     eax, [rdi+8]
0x18002e7cc  cmp     eax, 10002h
0x18002e7d1  jnz     loc_18002E932
0x18002e7d7  mov     r8d, [rbx+38h]
0x18002e7db  lea     rcx, [rbx+60h]
0x18002e7df  mov     r9b, 1
0x18002e7e2  lea     rdx, [rbx+3Ch]
0x18002e7e6  call    SymCryptAesExpandKeyInternal
0x18002e7eb  mov     r15d, eax
0x18002e7ee  test    eax, eax
0x18002e7f0  jnz     short loc_18002E84F
0x18002e7f2  cmp     dword ptr [rbx+0Ch], 5
0x18002e7f6  jz      short loc_18002E825
0x18002e7f8  test    r15d, r15d
0x18002e7fb  jnz     loc_18002E9BA
0x18002e801  mov     rax, [rsp+98h+arg_8]; jumptable 000000018002E94B case 65545
0x18002e809  test    rax, rax
0x18002e80c  jz      short loc_18002E811
0x18002e80e  mov     [rax], rbx
0x18002e811  xor     eax, eax
0x18002e813  add     rsp, 58h
0x18002e817  pop     r15
0x18002e819  pop     r14
0x18002e81b  pop     r13
0x18002e81d  pop     r12
0x18002e81f  pop     rdi
0x18002e820  pop     rsi
0x18002e821  pop     rbp
0x18002e822  pop     rbx
0x18002e823  retn
0x18002e825  cmp     dword ptr [rbx], 0C80h
0x18002e82b  jb      short loc_18002E84F
0x18002e82d  mov     r9d, [rbx+38h]
0x18002e831  lea     rcx, [rbx+250h]
0x18002e838  lea     r8, [rbx+3Ch]
0x18002e83c  lea     rdx, SymCryptAesBlockCipher_Fast
0x18002e843  call    SymCryptGcmExpandKey
0x18002e848  or      dword ptr [rbx+1Ch], 1
0x18002e84c  mov     r15d, eax
0x18002e84f  cmp     dword ptr [rbx+0Ch], 5
0x18002e853  jnz     short loc_18002E7F8
0x18002e855  test    ebp, ebp
0x18002e857  jz      short loc_18002E7F8
0x18002e859  or      dword ptr [rbx+1Ch], 2
0x18002e85d  lea     rcx, [rsp+98h+var_58]
0x18002e862  mov     [rsp+98h+var_58], 0
0x18002e86b  mov     ebp, 0Ch
0x18002e870  mov     [rsp+98h+var_50], 0
0x18002e879  call    AesRNGState_select
0x18002e87e  mov     r13, [rsp+98h+var_58]
0x18002e883  nop     dword ptr [rax+00h]
0x18002e887  nop     word ptr [rax+rax+00000000h]
0x18002e890  mov     edi, 10000h
0x18002e895  lea     r9, [rsp+98h+var_50]
0x18002e89a  cmp     rbp, rdi
0x18002e89d  mov     rdx, r14
0x18002e8a0  mov     rcx, r13
0x18002e8a3  cmovb   rdi, rbp
0x18002e8a7  mov     r8, rdi
0x18002e8aa  call    AesRNGState_generate
0x18002e8af  add     r14, rdi
0x18002e8b2  mov     r12d, eax
0x18002e8b5  sub     rbp, rdi
0x18002e8b8  jnz     short loc_18002E890
0x18002e8ba  test    eax, eax
0x18002e8bc  jns     loc_18002E7F8
0x18002e8c2  mov     edx, esi
0x18002e8c4  mov     rcx, rbx
0x18002e8c7  call    SymCryptWipeAsm
0x18002e8cc  mov     eax, r12d
0x18002e8cf  jmp     loc_18002E813
0x18002e8d4  mov     eax, [rdx+r15+84114h]
0x18002e8dc  cmp     r14d, eax
0x18002e8df  jbe     loc_18002E75D
0x18002e8e5  mov     r12d, 0C000000Dh
0x18002e8eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e8f2  lea     rax, WPP_GLOBAL_Control
0x18002e8f9  cmp     rcx, rax
0x18002e8fc  jz      short loc_18002E8C2
0x18002e8fe  test    byte ptr [rcx+1Ch], 1
0x18002e902  jz      short loc_18002E8C2
0x18002e904  mov     rcx, [rcx+10h]
0x18002e908  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002e90f  mov     [rsp+98h+var_68], 230h
0x18002e917  lea     r9, aStatus; "Status"
0x18002e91e  mov     [rsp+98h+var_70], rax
0x18002e923  mov     [rsp+98h+var_78], 0C000000Dh
0x18002e92b  call    WPP_SF_sDsd
0x18002e930  jmp     short loc_18002E8C2
0x18002e932  add     eax, 0FFFEFFFFh; switch 9 cases
0x18002e937  cmp     eax, 8
0x18002e93a  ja      def_18002E94B; jumptable 000000018002E94B default case, case 65538
0x18002e940  mov     eax, ds:(jpt_18002E94B - 180000000h)[r15+rax*4]
0x18002e948  add     rax, r15
0x18002e94b  jmp     rax; switch jump
0x18002e951  mov     r9d, [rdi+24h]; jumptable 000000018002E94B case 65543
0x18002e955  lea     rcx, [rbx+0C0h]
0x18002e95c  mov     r8d, [rbx+38h]
0x18002e960  lea     rdx, [rbx+3Ch]
0x18002e964  mov     [rbx+150h], r9d
0x18002e96b  mov     eax, [rdi+24h]
0x18002e96e  mov     [rbx+18h], eax
0x18002e971  call    SymCryptRc2ExpandKeyEx
0x18002e976  mov     r15d, eax
0x18002e979  jmp     loc_18002E7F8
0x18002e97e  mov     r8d, [rbx+38h]; jumptable 000000018002E94B case 65537
0x18002e982  lea     rcx, [rbx+140h]
0x18002e989  lea     rdx, [rbx+3Ch]
0x18002e98d  call    SymCryptRc4Init
0x18002e992  mov     r15d, eax
0x18002e995  jmp     loc_18002E7F8
0x18002e99a  mov     r8d, [rbx+38h]; jumptable 000000018002E94B case 65541
0x18002e99e  lea     rcx, [rbx+60h]
0x18002e9a2  lea     rdx, [rbx+3Ch]
0x18002e9a6  mov     dword ptr [rbx+18h], 0A8h
0x18002e9ad  call    SymCrypt3DesExpandKey
0x18002e9b2  mov     r15d, eax
0x18002e9b5  jmp     loc_18002E7F8
0x18002e9ba  mov     r12d, 0C000000Dh
0x18002e9c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e9c7  lea     rax, WPP_GLOBAL_Control
0x18002e9ce  cmp     rcx, rax
0x18002e9d1  jz      loc_18002E8C2
0x18002e9d7  test    byte ptr [rcx+1Ch], 1
0x18002e9db  jz      loc_18002E8C2
0x18002e9e1  mov     rcx, [rcx+10h]
0x18002e9e5  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002e9ec  mov     [rsp+98h+var_68], 2EDh
0x18002e9f4  lea     r9, aStatus; "Status"
0x18002e9fb  mov     [rsp+98h+var_70], rax
0x18002ea00  mov     [rsp+98h+var_78], 0C000000Dh
0x18002ea08  call    WPP_SF_sDsd
0x18002ea0d  jmp     loc_18002E8C2
0x18002ea12  mov     r12d, 0C0000008h
0x18002ea18  jmp     loc_18002E8C2
0x18002ea1d  mov     r8d, [rbx+38h]; jumptable 000000018002E94B case 65539
0x18002ea21  lea     rcx, [rbx+50h]
0x18002ea25  lea     rdx, [rbx+3Ch]
0x18002ea29  mov     dword ptr [rbx+18h], 38h ; '8'
0x18002ea30  call    SymCryptDesExpandKey
0x18002ea35  mov     r15d, eax
0x18002ea38  jmp     loc_18002E7F8
0x18002ea3d  mov     r8d, [rbx+38h]; jumptable 000000018002E94B case 65542
0x18002ea41  lea     rcx, [rbx+50h]
0x18002ea45  lea     rdx, [rbx+3Ch]
0x18002ea49  mov     dword ptr [rbx+18h], 70h ; 'p'
0x18002ea50  call    SymCrypt3DesExpandKey
0x18002ea55  mov     r15d, eax
0x18002ea58  jmp     loc_18002E7F8
0x18002ea5d  shr     dword ptr [rbx+18h], 1; jumptable 000000018002E94B case 65544
0x18002ea60  lea     rcx, [rbx+80h]
0x18002ea67  mov     r8d, [rbx+38h]
0x18002ea6b  lea     rdx, [rbx+3Ch]
0x18002ea6f  call    SymCryptXtsAesExpandKey
0x18002ea74  mov     r15d, eax
0x18002ea77  jmp     loc_18002E7F8
0x18002ea7c  mov     r9d, 1DAh
0x18002ea82  jmp     loc_180081E44
0x18002ea87  mov     r12d, 0C00000BBh; jumptable 000000018002E94B default case, case 65538
0x18002ea8d  mov     r9d, 2E5h
0x18002ea93  mov     ecx, 0C00000BBh
0x18002ea98  lea     rdx, aStatus; "Status"
0x18002ea9f  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002eaa6  call    DebugTraceError
0x18002eaab  jmp     loc_18002E8C2
0x18002eab0  mov     r12d, 0C000000Dh
0x18002eab6  jmp     loc_18002E8C2
0x18002eabb  cmp     dword ptr [rdi+8], 10002h
0x18002eac2  jnz     loc_180081E54
0x18002eac8  cmp     dword ptr [rdi+0Ch], 5
0x18002eacc  jz      loc_18002E6DB
0x18002ead2  jmp     loc_180081E54
0x18002ead7  cmp     dword ptr [rdi+8], 10002h
0x18002eade  jnz     loc_180081E5C
0x18002eae4  cmp     dword ptr [rdi+0Ch], 5
0x18002eae8  jnz     loc_180081E5C
0x18002eaee  cmp     esi, 250h
0x18002eaf4  jnb     loc_18002E6EE
0x18002eafa  jmp     loc_180081E5C
0x18002eaff  cmp     r10d, 10008h
0x18002eb06  jnz     loc_180081E3E
0x18002eb0c  cmp     cs:g_fSelftest, 0
0x18002eb13  jz      loc_18002E7A0
0x18002eb19  mov     r8d, r14d
0x18002eb1c  mov     rcx, r13; Buf1
0x18002eb1f  shr     r8, 1; Size
0x18002eb22  lea     rdx, [r8+r13]; Buf2
0x18002eb26  call    memcmp_0
0x18002eb2b  test    eax, eax
0x18002eb2d  jnz     loc_18002E7A0
0x18002eb33  jmp     loc_180081E3E
0x18002eb38  mov     r8d, [rbx+38h]; jumptable 000000018002E94B case 65540
0x18002eb3c  lea     rcx, [rbx+60h]
0x18002eb40  lea     rdx, [rbx+3Ch]
0x18002eb44  mov     dword ptr [rbx+18h], 0B8h
0x18002eb4b  call    SymCryptDesxExpandKey
0x18002eb50  mov     r15d, eax
0x18002eb53  jmp     loc_18002E7F8
0x180081e3e  mov     r9d, 23Bh
0x180081e44  mov     r12d, 0C000000Dh
0x180081e4a  mov     ecx, 0C000000Dh
0x180081e4f  jmp     loc_18002EA98
0x180081e54  mov     r9d, 1F1h
0x180081e5a  jmp     short loc_180081E44
0x180081e5c  mov     r12d, 0C0000023h
0x180081e62  jmp     loc_18002E8C2
```
