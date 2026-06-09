# MSCryptCreateMultiHash

- ea: `0x180013b70`
- end: `0x180014230`
- name: `MSCryptCreateMultiHash`
- size: `1728`
- prototype: `__int64 __fastcall(int, int, int, int, int, void *Src, size_t Size, int)`
- caller_count: `7`
- callee_count: `31`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800117d0`
- `0x180013b30`
- `0x180016af4`
- `0x180016db0`
- `0x180053de4`
- `0x180058a04`
- `0x18007dd2c`

## callees

- `0x180001530`
- `0x180001730`
- `0x180001930`
- `0x180001b40`
- `0x180001e40`
- `0x18000ecb0`
- `0x180013b70`
- `0x180014240`
- `0x180014590`
- `0x180015390`
- `0x180016a00`
- `0x180016ad0`
- `0x180016d30`
- `0x180016d60`
- `0x180017590`
- `0x180018590`
- `0x1800185e0`
- `0x180018ac0`
- `0x180018b10`
- `0x18002e570`
- `0x1800317b0`
- `0x180031ef0`
- `0x180032210`
- `0x180034050`
- `0x18003409c`
- `0x1800593e0`
- `0x180063170`
- `0x180063180`
- `0x180065680`
- `0x180077ec8`
- `0x180078008`

## string_xrefs

- `0x180080934`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptCreateMultiHash(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        void *Src,
        size_t Size,
        unsigned int a8)
{
  unsigned int v8; // ebp
  __int64 *v10; // r12
  _DWORD *v11; // rax
  __int64 v12; // rdx
  unsigned int v13; // r8d
  _DWORD *v14; // r14
  unsigned int v15; // eax
  unsigned int v16; // edi
  int v17; // eax
  void *v18; // r15
  unsigned int v19; // edi
  __int64 v21; // rbp
  unsigned int k; // ebp
  unsigned int i; // ebp
  unsigned int v24; // r8d
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rax
  unsigned __int64 v28; // rdx
  __int64 v29; // r9
  __int64 v30; // rcx
  unsigned int j; // ebp
  unsigned int v32; // r8d
  __int64 v33; // rdx
  __int64 v34; // rbp
  unsigned int m; // ebp
  unsigned int n; // ebp
  unsigned int ii; // ebp
  unsigned int jj; // ebp
  unsigned int kk; // ebp
  unsigned int mm; // ebp
  unsigned int nn; // ebp
  unsigned int i1; // ebp
  int v43; // eax
  unsigned int i2; // ebp
  unsigned int i3; // ebp
  __int64 v46; // rax
  __int64 v47; // rax
  unsigned int v48; // ecx
  __int64 v49; // rax

  v8 = a8;
  v10 = a2;
  if ( (a8 & 0xFFFFFFDF) != 0 )
  {
    v29 = 957;
LABEL_75:
    v19 = -1073741811;
    v30 = 3221225485LL;
    goto LABEL_76;
  }
  v11 = (_DWORD *)validateMSCryptHashAlgorithm(a1);
  v14 = v11;
  if ( !v11 )
  {
    v19 = -1073741816;
    v29 = 966;
    v30 = 3221225480LL;
LABEL_76:
    DebugTraceError(v30, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", v29);
    return v19;
  }
  if ( !v12 || !a4 )
  {
    v29 = 974;
    goto LABEL_75;
  }
  if ( !v11[8] && !v11[13] && (Src || (_DWORD)Size) )
  {
    v29 = 986;
    goto LABEL_75;
  }
  v15 = v11[4];
  v16 = 1;
  if ( v13 )
  {
    if ( !v14[11] || v14[13] || v14[2] == 131080 )
    {
      v29 = 1006;
LABEL_46:
      v19 = -1073741637;
      v30 = 3221225659LL;
      goto LABEL_76;
    }
    v28 = (v13 - 1) * (unsigned __int64)(unsigned int)v14[6];
    if ( v28 > 0xFFFFFFFF )
      return (unsigned int)-1073741811;
    v15 = v28 + v14[5];
    if ( v15 < (unsigned int)v28 )
      return (unsigned int)-1073741811;
    v8 = a8 | 0x20;
    v16 = v13;
    a8 |= 0x20u;
  }
  if ( a5 >= v15 )
  {
    *(_DWORD *)a4 = v15;
    *(_DWORD *)(a4 + 4) = 1297303624;
    *(_DWORD *)(a4 + 8) = v14[2];
    *(_DWORD *)(a4 + 12) = v14[3];
    *(_DWORD *)(a4 + 16) = v14[8];
    if ( v14[10] || (v17 = 0, (v8 & 0x20) != 0) )
      v17 = 1;
    *(_DWORD *)(a4 + 24) = v17;
    v18 = (void *)(a4 + 48);
    *(_DWORD *)(a4 + 28) = v14[13];
    *(_DWORD *)(a4 + 32) = 0;
    *(_DWORD *)(a4 + 36) = v13 != 0;
    *(_BYTE *)(a4 + 40) = *((_BYTE *)v14 + 48);
    *(_DWORD *)(a4 + 44) = v16;
    *(_DWORD *)(a4 + 112) = v14[7];
    memset_0((void *)(a4 + 48), 0, 0x40u);
    *(_DWORD *)(a4 + 20) = 0;
    switch ( v14[2] )
    {
      case 0x20001:
        v24 = 0;
        v25 = 0;
        do
        {
          v26 = 112 * v25;
          ++v24;
          *(_QWORD *)(v26 + a4 + 144) = 0;
          *(_QWORD *)(v26 + a4 + 152) = 0;
          *(_DWORD *)(v26 + a4 + 128) = 0;
          v27 = v25 + 2;
          ++v25;
          *(_OWORD *)(112 * v27 + a4) = xmmword_18008D800;
        }
        while ( v24 < v16 );
        goto LABEL_13;
      case 0x20002:
        for ( i = 0; i < v16; ++i )
          SymCryptSha1Init(a4 + 128 + ((unsigned __int64)i << 7));
        goto LABEL_19;
      case 0x20003:
        for ( j = 0; j < v16; ++j )
          SymCryptWipeAsm(a4 + 128 + 112LL * j, 112);
        goto LABEL_19;
      case 0x20004:
        v32 = 0;
        v33 = 0;
        do
        {
          v46 = 112 * v33;
          ++v32;
          *(_QWORD *)(v46 + a4 + 144) = 0;
          *(_QWORD *)(v46 + a4 + 152) = 0;
          *(_DWORD *)(v46 + a4 + 128) = 0;
          v47 = v33 + 2;
          ++v33;
          *(_OWORD *)(112 * v47 + a4) = xmmword_18008E038;
        }
        while ( v32 < v16 );
        goto LABEL_13;
      case 0x20005:
        SymCryptParallelSha256Init(a4 + 128, v16);
        goto LABEL_13;
      case 0x20006:
        SymCryptParallelSha384Init(a4 + 128, v16);
        goto LABEL_13;
      case 0x20007:
        SymCryptParallelSha512Init(a4 + 128, v16);
        goto LABEL_13;
      case 0x20008:
        if ( !(unsigned int)SymCryptGcmExpandKey(a4 + 128, SymCryptAesBlockCipher_Fast, Src, (unsigned int)Size)
          && (unsigned int)(Size - 16) <= 0x10
          && (Size & 7) == 0 )
        {
          *(_DWORD *)(a4 + 116) = 0;
          goto LABEL_13;
        }
        v19 = -1073741306;
        v29 = 1161;
        v30 = 3221225990LL;
        goto LABEL_76;
      case 0x20009:
        SymCryptHmacSha1ExpandKey(a4 + 128, Src, (unsigned int)Size);
        v34 = 0;
        do
        {
          SymCryptHmacSha1Init(a4 + 208 + 144 * v34, a4 + 128);
          v34 = (unsigned int)(v34 + 1);
        }
        while ( (unsigned int)v34 < v16 );
        goto LABEL_26;
      case 0x2000A:
        SymCryptHmacMd5ExpandKey(a4 + 128, Src, (unsigned int)Size);
        for ( k = 0; k < v16; ++k )
          SymCryptHmacMd5Init(a4 + 176 + ((unsigned __int64)k << 7), a4 + 128);
        goto LABEL_26;
      case 0x2000B:
        SymCryptHmacSha256ExpandKey(a4 + 128, Src, (unsigned int)Size);
        v21 = 0;
        do
        {
          SymCryptHmacSha256Init(a4 + 208 + 144 * v21, a4 + 128);
          v21 = (unsigned int)(v21 + 1);
        }
        while ( (unsigned int)v21 < v16 );
        goto LABEL_26;
      case 0x2000C:
        SymCryptHmacSha384ExpandKey(a4 + 128, Src, (unsigned int)Size);
        for ( m = 0; m < v16; ++m )
          SymCryptHmacSha512Init(a4 + 272 + 240LL * m, a4 + 128);
        goto LABEL_26;
      case 0x2000D:
        SymCryptHmacSha512ExpandKey(a4 + 128, Src, (unsigned int)Size);
        for ( n = 0; n < v16; ++n )
          SymCryptHmacSha512Init(a4 + 272 + 240LL * n, a4 + 128);
        goto LABEL_26;
      case 0x2000E:
        if ( (unsigned int)SymCryptAesCmacExpandKey(a4 + 128, Src, (unsigned int)Size) )
        {
          v29 = 1261;
          goto LABEL_75;
        }
        v48 = 0;
        do
        {
          v49 = v48++;
          v49 <<= 6;
          *(_QWORD *)(a4 + v49 + 704) = 0;
          *(_QWORD *)(a4 + v49 + 672) = 0;
          *(_QWORD *)(a4 + v49 + 680) = 0;
          *(_QWORD *)(a4 + v49 + 712) = a4 + 128;
        }
        while ( v48 < v16 );
LABEL_20:
        v8 = a8;
        goto LABEL_13;
      case 0x2000F:
        for ( ii = 0; ii < v16; ++ii )
          SymCryptSha3_256Init((void *)(a4 + 128 + 240LL * ii));
        goto LABEL_19;
      case 0x20010:
        for ( jj = 0; jj < v16; ++jj )
          SymCryptSha3_384Init((void *)(a4 + 128 + 240LL * jj));
        goto LABEL_19;
      case 0x20011:
        for ( kk = 0; kk < v16; ++kk )
          SymCryptSha3_512Init((void *)(a4 + 128 + 240LL * kk));
        goto LABEL_19;
      case 0x20012:
        SymCryptHmacExpandKey(&SymCryptSha3_256Algorithm_default, a4 + 128, Src, (unsigned int)Size);
        for ( mm = 0; mm < v16; ++mm )
          SymCryptHmacInit(a4 + 640 + 272LL * mm, a4 + 128);
        goto LABEL_26;
      case 0x20013:
        SymCryptHmacExpandKey(&SymCryptSha3_384Algorithm_default, a4 + 128, Src, (unsigned int)Size);
        for ( nn = 0; nn < v16; ++nn )
          SymCryptHmacInit(a4 + 640 + 272LL * nn, a4 + 128);
        goto LABEL_26;
      case 0x20014:
        SymCryptHmacExpandKey(&SymCryptSha3_512Algorithm_default, a4 + 128, Src, (unsigned int)Size);
        for ( i1 = 0; i1 < v16; ++i1 )
          SymCryptHmacInit(a4 + 640 + 272LL * i1, a4 + 128);
LABEL_26:
        v10 = a2;
        goto LABEL_19;
      case 0x20015:
      case 0x20016:
        *(_QWORD *)(a4 + 184) = 0;
        *(_DWORD *)(a4 + 192) = 0;
        *(_QWORD *)(a4 + 264) = 0;
        *(_DWORD *)(a4 + 272) = 0;
        *(_DWORD *)(a4 + 280) = 0;
        goto LABEL_13;
      case 0x20017:
        *(_QWORD *)(a4 + 432) = 0;
        *(_DWORD *)(a4 + 440) = 0;
        *(_QWORD *)(a4 + 512) = 0;
        *(_DWORD *)(a4 + 520) = 0;
        v43 = MSCryptCustomBufferUpdate(a4 + 368, Src, (unsigned int)Size);
        v19 = v43;
        if ( v43 >= 0 )
          goto LABEL_109;
        v29 = 1395;
        goto LABEL_108;
      case 0x20018:
        *(_QWORD *)(a4 + 432) = 0;
        *(_DWORD *)(a4 + 440) = 0;
        *(_QWORD *)(a4 + 512) = 0;
        *(_DWORD *)(a4 + 520) = 0;
        v43 = MSCryptCustomBufferUpdate(a4 + 368, Src, (unsigned int)Size);
        v19 = v43;
        if ( v43 < 0 )
        {
          v29 = 1416;
LABEL_108:
          v30 = (unsigned int)v43;
          goto LABEL_76;
        }
LABEL_109:
        *(_DWORD *)(a4 + 528) = 0;
LABEL_13:
        if ( *(_DWORD *)(a4 + 28) )
        {
          if ( (unsigned int)Size <= v14[7] )
          {
            memcpy_0(v18, Src, (unsigned int)Size);
          }
          else
          {
            v43 = MSCryptHashDataInternal(a4, Src);
            v19 = v43;
            if ( v43 < 0 )
            {
              v29 = 1474;
              goto LABEL_108;
            }
            v43 = MSCryptHashResultInternal(a4, (__int64)v18, *(_DWORD *)(a4 + 12), v8);
            v19 = v43;
            if ( v43 < 0 )
            {
              v29 = 1483;
              goto LABEL_108;
            }
          }
        }
        *v10 = a4;
        return 0;
      case 0x20019:
        for ( i2 = 0; i2 < v16; ++i2 )
          SymCryptShake128Init((void *)(a4 + 128 + 240LL * i2));
        goto LABEL_19;
      case 0x2001A:
        for ( i3 = 0; i3 < v16; ++i3 )
          SymCryptShake256Init((void *)(a4 + 128 + 240LL * i3));
LABEL_19:
        v18 = (void *)(a4 + 48);
        goto LABEL_20;
      default:
        v29 = 1453;
        goto LABEL_46;
    }
  }
  return (unsigned int)-1073741789;
}

```

## disassembly

```asm
0x180013b70  mov     [rsp+arg_8], rdx
0x180013b75  push    rbx
0x180013b76  push    rbp
0x180013b77  push    rsi
0x180013b78  push    rdi
0x180013b79  push    r12
0x180013b7b  push    r13
0x180013b7d  push    r14
0x180013b7f  push    r15
0x180013b81  sub     rsp, 28h
0x180013b85  mov     ebp, [rsp+68h+arg_38]
0x180013b8c  mov     rbx, r9
0x180013b8f  mov     r12, rdx
0x180013b92  test    ebp, 0FFFFFFDFh
0x180013b98  jnz     loc_180013E6F
0x180013b9e  call    validateMSCryptHashAlgorithm
0x180013ba3  xor     r9d, r9d
0x180013ba6  mov     r14, rax
0x180013ba9  test    rax, rax
0x180013bac  jz      loc_180013E7A
0x180013bb2  test    rdx, rdx
0x180013bb5  jz      loc_1800141BC
0x180013bbb  test    rbx, rbx
0x180013bbe  jz      loc_1800141BC
0x180013bc4  mov     esi, dword ptr [rsp+68h+Size]
0x180013bcb  mov     r13, [rsp+68h+Src]
0x180013bd3  cmp     [rax+20h], r9d
0x180013bd7  jnz     short loc_180013BE3
0x180013bd9  cmp     [rax+34h], r9d
0x180013bdd  jz      loc_180013E8F
0x180013be3  mov     eax, [rax+10h]
0x180013be6  mov     edi, 1
0x180013beb  test    r8d, r8d
0x180013bee  jnz     loc_180013EA5
0x180013bf4  cmp     [rsp+68h+arg_20], eax
0x180013bfb  jb      loc_180013CCD
0x180013c01  mov     [rbx], eax
0x180013c03  mov     dword ptr [rbx+4], 4D534848h
0x180013c0a  mov     eax, [r14+8]
0x180013c0e  mov     [rbx+8], eax
0x180013c11  mov     eax, [r14+0Ch]
0x180013c15  mov     [rbx+0Ch], eax
0x180013c18  mov     eax, [r14+20h]
0x180013c1c  mov     [rbx+10h], eax
0x180013c1f  cmp     [r14+28h], r9d
0x180013c23  jz      loc_180013D48
0x180013c29  mov     eax, 1
0x180013c2e  mov     [rbx+18h], eax
0x180013c31  lea     r15, [rbx+30h]
0x180013c35  mov     eax, [r14+34h]
0x180013c39  test    r8d, r8d
0x180013c3c  mov     [rbx+1Ch], eax
0x180013c3f  mov     rcx, r15; void *
0x180013c42  mov     eax, r9d
0x180013c45  mov     [rbx+20h], r9d
0x180013c49  setnz   al
0x180013c4c  xor     edx, edx; Val
0x180013c4e  mov     [rbx+24h], eax
0x180013c51  mov     al, [r14+30h]
0x180013c55  mov     [rbx+28h], al
0x180013c58  mov     [rbx+2Ch], edi
0x180013c5b  lea     r8d, [rdx+40h]; Size
0x180013c5f  mov     eax, [r14+1Ch]
0x180013c63  mov     [rbx+70h], eax
0x180013c66  call    memset_0
0x180013c6b  mov     dword ptr [rbx+14h], 0
0x180013c72  mov     eax, [r14+8]
0x180013c76  add     eax, 0FFFDFFFFh; switch 26 cases
0x180013c7b  cmp     eax, 19h
0x180013c7e  ja      def_180013C95; jumptable 0000000180013C95 default case
0x180013c84  lea     rcx, cs:180000000h
0x180013c8b  mov     eax, ds:(jpt_180013C95 - 180000000h)[rcx+rax*4]
0x180013c92  add     rax, rcx
0x180013c95  jmp     rax; switch jump
0x180013c9b  mov     edx, edi; jumptable 0000000180013C95 case 131077
0x180013c9d  lea     rcx, [rbx+80h]
0x180013ca4  call    SymCryptParallelSha256Init
0x180013ca9  cmp     dword ptr [rbx+1Ch], 0
0x180013cad  jnz     loc_18001418F
0x180013cb3  mov     [r12], rbx
0x180013cb7  xor     edi, edi
0x180013cb9  mov     eax, edi
0x180013cbb  add     rsp, 28h
0x180013cbf  pop     r15
0x180013cc1  pop     r14
0x180013cc3  pop     r13
0x180013cc5  pop     r12
0x180013cc7  pop     rdi
0x180013cc8  pop     rsi
0x180013cc9  pop     rbp
0x180013cca  pop     rbx
0x180013ccb  retn
0x180013ccd  mov     edi, 0C0000023h
0x180013cd2  jmp     short loc_180013CB9
0x180013cd4  mov     qword ptr [rbx+0B8h], 0; jumptable 0000000180013C95 cases 131093,131094
0x180013cdf  mov     dword ptr [rbx+0C0h], 0
0x180013ce9  mov     qword ptr [rbx+108h], 0
0x180013cf4  mov     dword ptr [rbx+110h], 0
0x180013cfe  mov     dword ptr [rbx+118h], 0
0x180013d08  jmp     short loc_180013CA9
0x180013d0a  lea     r15, [rbx+80h]; jumptable 0000000180013C95 case 131083
0x180013d11  mov     r8, rsi
0x180013d14  mov     rcx, r15
0x180013d17  mov     rdx, r13
0x180013d1a  call    SymCryptHmacSha256ExpandKey
0x180013d1f  xor     ebp, ebp
0x180013d21  test    edi, edi
0x180013d23  jnz     short loc_180013D81
0x180013d25  lea     r15, [rbx+30h]
0x180013d29  mov     ebp, [rsp+68h+arg_38]
0x180013d30  jmp     loc_180013CA9
0x180013d35  mov     edx, edi; jumptable 0000000180013C95 case 131079
0x180013d37  lea     rcx, [rbx+80h]
0x180013d3e  call    SymCryptParallelSha512Init
0x180013d43  jmp     loc_180013CA9
0x180013d48  mov     eax, r9d
0x180013d4b  test    bpl, 20h
0x180013d4f  jnz     loc_180013C29
0x180013d55  jmp     loc_180013C2E
0x180013d5a  lea     r15, [rbx+80h]; jumptable 0000000180013C95 case 131082
0x180013d61  mov     r8, rsi
0x180013d64  mov     rcx, r15
0x180013d67  mov     rdx, r13
0x180013d6a  call    SymCryptHmacMd5ExpandKey
0x180013d6f  xor     ebp, ebp
0x180013d71  test    edi, edi
0x180013d73  jz      short loc_180013D25
0x180013d75  lea     r12, [rbx+0B0h]
0x180013d7c  jmp     loc_180080A14
0x180013d81  lea     r12, [rbx+0D0h]
0x180013d88  lea     rcx, ds:0[rbp*8]
0x180013d90  mov     rdx, r15
0x180013d93  add     rcx, rbp
0x180013d96  shl     rcx, 4
0x180013d9a  add     rcx, r12
0x180013d9d  call    SymCryptHmacSha256Init
0x180013da2  inc     ebp
0x180013da4  cmp     ebp, edi
0x180013da6  jb      short loc_180013D88
0x180013da8  mov     r12, [rsp+68h+arg_8]
0x180013dad  jmp     loc_180013D25
0x180013db2  xor     ebp, ebp; jumptable 0000000180013C95 case 131074
0x180013db4  test    edi, edi
0x180013db6  jz      loc_180013D29
0x180013dbc  lea     r15, [rbx+80h]
0x180013dc3  jmp     loc_180080958
0x180013dc8  mov     edx, edi; jumptable 0000000180013C95 case 131078
0x180013dca  lea     rcx, [rbx+80h]
0x180013dd1  call    SymCryptParallelSha384Init
0x180013dd6  jmp     loc_180013CA9
0x180013ddb  xor     r8d, r8d; jumptable 0000000180013C95 case 131073
0x180013dde  test    edi, edi
0x180013de0  jz      loc_180013CA9
0x180013de6  xor     edx, edx
0x180013de8  imul    rax, rdx, 70h ; 'p'
0x180013dec  inc     r8d
0x180013def  mov     qword ptr [rax+rbx+90h], 0
0x180013dfb  mov     qword ptr [rax+rbx+98h], 0
0x180013e07  mov     dword ptr [rax+rbx+80h], 0
0x180013e12  lea     rax, [rdx+2]
0x180013e16  movups  xmm0, cs:xmmword_18008D800
0x180013e1d  inc     rdx
0x180013e20  imul    rcx, rax, 70h ; 'p'
0x180013e24  movdqu  xmmword ptr [rcx+rbx], xmm0
0x180013e29  cmp     r8d, edi
0x180013e2c  jb      short loc_180013DE8
0x180013e2e  jmp     loc_180013CA9
0x180013e33  mov     edx, [r14+18h]
0x180013e37  lea     ecx, [r8-1]
0x180013e3b  imul    rdx, rcx
0x180013e3f  mov     eax, 0FFFFFFFFh
0x180013e44  cmp     rdx, rax
0x180013e47  jbe     short loc_180013E53
0x180013e49  mov     edi, 0C000000Dh
0x180013e4e  jmp     loc_180013CB9
0x180013e53  mov     eax, [r14+14h]
0x180013e57  add     eax, edx
0x180013e59  cmp     eax, edx
0x180013e5b  jb      short loc_180013E49
0x180013e5d  or      ebp, 20h
0x180013e60  mov     edi, r8d
0x180013e63  mov     [rsp+68h+arg_38], ebp
0x180013e6a  jmp     loc_180013BF4
0x180013e6f  mov     r9d, 3BDh
0x180013e75  jmp     loc_18008092A
0x180013e7a  mov     edi, 0C0000008h
0x180013e7f  mov     r9d, 3C6h
0x180013e85  mov     ecx, 0C0000008h
0x180013e8a  jmp     loc_180080934
0x180013e8f  test    r13, r13
0x180013e92  jnz     loc_180080924
0x180013e98  test    esi, esi
0x180013e9a  jz      loc_180013BE3
0x180013ea0  jmp     loc_180080924
0x180013ea5  cmp     [r14+2Ch], r9d
0x180013ea9  jz      loc_18008094D
0x180013eaf  cmp     [r14+34h], r9d
0x180013eb3  jnz     loc_18008094D
0x180013eb9  cmp     dword ptr [r14+8], 20008h
0x180013ec1  jz      loc_18008094D
0x180013ec7  jmp     loc_180013E33
0x180013ecc  mov     r9d, 5ADh; jumptable 0000000180013C95 default case
0x180013ed2  mov     edi, 0C00000BBh
0x180013ed7  mov     ecx, 0C00000BBh
0x180013edc  jmp     loc_180080934
0x180013ee1  xor     ebp, ebp; jumptable 0000000180013C95 case 131075
0x180013ee3  test    edi, edi
0x180013ee5  jz      loc_180013D29
0x180013eeb  lea     r15, [rbx+80h]
0x180013ef2  jmp     loc_180080971
0x180013ef7  xor     r8d, r8d; jumptable 0000000180013C95 case 131076
0x180013efa  test    edi, edi
0x180013efc  jz      loc_180013CA9
0x180013f02  xor     edx, edx
0x180013f04  jmp     loc_18008098F
0x180013f09  mov     r9, rsi; jumptable 0000000180013C95 case 131080
0x180013f0c  lea     rcx, [rbx+80h]
0x180013f13  mov     r8, r13
0x180013f16  lea     rdx, SymCryptAesBlockCipher_Fast
0x180013f1d  call    SymCryptGcmExpandKey
0x180013f22  test    eax, eax
0x180013f24  jnz     loc_1800809DA
0x180013f2a  lea     eax, [rsi-10h]
0x180013f2d  cmp     eax, 10h
0x180013f30  ja      loc_1800809DA
0x180013f36  test    sil, 7
0x180013f3a  jnz     loc_1800809DA
0x180013f40  mov     dword ptr [rbx+74h], 0
0x180013f47  jmp     loc_180013CA9
0x180013f4c  lea     r15, [rbx+80h]; jumptable 0000000180013C95 case 131081
0x180013f53  mov     r8, rsi
0x180013f56  mov     rcx, r15
0x180013f59  mov     rdx, r13
0x180013f5c  call    SymCryptHmacSha1ExpandKey
0x180013f61  xor     ebp, ebp
0x180013f63  test    edi, edi
0x180013f65  jz      loc_180013D25
0x180013f6b  lea     r12, [rbx+0D0h]
0x180013f72  jmp     loc_1800809EF
0x180013f77  lea     r15, [rbx+80h]; jumptable 0000000180013C95 case 131084
0x180013f7e  mov     r8, rsi
0x180013f81  mov     rcx, r15
0x180013f84  mov     rdx, r13
0x180013f87  call    SymCryptHmacSha384ExpandKey
0x180013f8c  xor     ebp, ebp
0x180013f8e  test    edi, edi
0x180013f90  jz      loc_180013D25
0x180013f96  lea     r12, [rbx+110h]
0x180013f9d  jmp     loc_180080A30
0x180013fa2  lea     r15, [rbx+80h]; jumptable 0000000180013C95 case 131085
0x180013fa9  mov     r8, rsi
0x180013fac  mov     rcx, r15
0x180013faf  mov     rdx, r13
0x180013fb2  call    SymCryptHmacSha512ExpandKey
0x180013fb7  xor     ebp, ebp
0x180013fb9  test    edi, edi
0x180013fbb  jz      loc_180013D25
0x180013fc1  lea     r12, [rbx+110h]
0x180013fc8  jmp     loc_180080A4F
0x180013fcd  lea     rbp, [rbx+80h]; jumptable 0000000180013C95 case 131086
0x180013fd4  mov     r8, rsi
0x180013fd7  mov     rcx, rbp
0x180013fda  mov     rdx, r13
0x180013fdd  call    SymCryptAesCmacExpandKey
0x180013fe2  test    eax, eax
0x180013fe4  jz      loc_180080A6E
0x180013fea  mov     r9d, 4EDh
0x180013ff0  jmp     loc_18008092A
0x180013ff5  xor     ebp, ebp; jumptable 0000000180013C95 case 131087
0x180013ff7  test    edi, edi
0x180013ff9  jz      loc_180013D29
0x180013fff  lea     r15, [rbx+80h]
0x180014006  jmp     loc_180080AB5
0x18001400b  xor     ebp, ebp; jumptable 0000000180013C95 case 131088
0x18001400d  test    edi, edi
0x18001400f  jz      loc_180013D29
0x180014015  lea     r15, [rbx+80h]
0x18001401c  jmp     loc_180080AD1
0x180014021  xor     ebp, ebp; jumptable 0000000180013C95 case 131089
0x180014023  test    edi, edi
0x180014025  jz      loc_180013D29
0x18001402b  lea     r15, [rbx+80h]
0x180014032  jmp     loc_180080AED
0x180014037  lea     r15, [rbx+80h]; jumptable 0000000180013C95 case 131090
0x18001403e  mov     r9, rsi
0x180014041  mov     rdx, r15
0x180014044  lea     rcx, SymCryptSha3_256Algorithm_default
0x18001404b  mov     r8, r13
0x18001404e  call    SymCryptHmacExpandKey
0x180014053  xor     ebp, ebp
0x180014055  test    edi, edi
0x180014057  jz      loc_180013D25
0x18001405d  lea     r12, [rbx+280h]
0x180014064  jmp     loc_180080B09
0x180014069  lea     r15, [rbx+80h]; jumptable 0000000180013C95 case 131091
0x180014070  mov     r9, rsi
0x180014073  mov     rdx, r15
0x180014076  lea     rcx, SymCryptSha3_384Algorithm_default
0x18001407d  mov     r8, r13
0x180014080  call    SymCryptHmacExpandKey
  ... truncated ...
```
