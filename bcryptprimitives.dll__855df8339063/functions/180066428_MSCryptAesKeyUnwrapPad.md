# MSCryptAesKeyUnwrapPad

- ea: `0x180066428`
- end: `0x1800667db`
- name: `MSCryptAesKeyUnwrapPad`
- size: `947`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180067358`

## callees

- `0x18000d630`
- `0x18000ecb0`
- `0x180010270`
- `0x1800102a0`
- `0x180063170`
- `0x180066428`
- `0x1800667e4`
- `0x18007f790`

## string_xrefs

- `0x18006648b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\aeskeywrap.c`
- `0x1800664d2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\aeskeywrap.c`
- `0x18006652c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\aeskeywrap.c`
- `0x18006672b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\aeskeywrap.c`

## pseudocode

```c
__int64 __fastcall MSCryptAesKeyUnwrapPad(
        __int64 a1,
        void *a2,
        unsigned __int32 *a3,
        unsigned __int64 *a4,
        unsigned int a5)
{
  _QWORD *v5; // rsi
  unsigned int v6; // r13d
  unsigned __int32 *v7; // r12
  __int64 v9; // rdi
  __int64 v10; // r15
  __int64 v11; // r9
  unsigned int v12; // ebx
  int v13; // eax
  unsigned int v14; // edi
  __int64 v15; // r9
  __int64 v16; // rcx
  int v17; // eax
  unsigned __int64 v18; // rbx
  const void *v19; // rdx
  __int64 v20; // r12
  __int64 i; // r15
  __int64 v22; // rcx
  unsigned __int32 v23; // edx
  unsigned __int8 v24; // r8
  unsigned __int32 v25; // edi
  char v26; // al
  void *v27; // rcx
  unsigned __int64 **v28; // rax
  unsigned __int64 **v29; // rax
  __int64 v30; // rcx
  _BYTE *v31; // rax
  int v33; // [rsp+50h] [rbp-51h] BYREF
  int v34; // [rsp+54h] [rbp-4Dh] BYREF
  int v35; // [rsp+58h] [rbp-49h]
  void *v36; // [rsp+60h] [rbp-41h]
  unsigned __int32 *v37; // [rsp+68h] [rbp-39h]
  int *v38; // [rsp+70h] [rbp-31h]
  unsigned __int64 *v39; // [rsp+78h] [rbp-29h] BYREF
  unsigned __int64 *v40; // [rsp+80h] [rbp-21h] BYREF
  __int64 v41; // [rsp+88h] [rbp-19h]

  v5 = 0;
  v39 = a4;
  v34 = 0;
  v33 = 0;
  v6 = 0;
  v38 = &v33;
  v7 = a3;
  v37 = a3;
  v36 = a2;
  v35 = 0;
  v9 = 32;
  v10 = 8;
  if ( a1 )
  {
    if ( !a3 )
    {
      v11 = 617;
      goto LABEL_3;
    }
    v13 = MSCryptAesKeyUnwrapPadValidateInput(a1, a5);
    v12 = v13;
    if ( v13 < 0 )
    {
      DebugTraceError(
        (unsigned int)v13,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\aeskeywrap.c",
        624);
      v10 = 8;
      goto LABEL_36;
    }
    v14 = (a5 - 8) >> 3;
    v6 = 8 * v14;
    if ( !v36 )
    {
      *v7 = v6;
      v10 = 8;
LABEL_34:
      v12 = 0;
      goto LABEL_35;
    }
    if ( *v7 < v6 )
    {
      v12 = -1073741789;
      v15 = 646;
      v16 = 3221225507LL;
LABEL_12:
      DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\aeskeywrap.c", v15);
      v10 = 8;
      goto LABEL_35;
    }
    v5 = (_QWORD *)SafeAllocaAllocateFromHeap(v6);
    if ( !v5 )
    {
      v12 = -1073741801;
      v15 = 654;
      v16 = 3221225495LL;
      goto LABEL_12;
    }
    v35 = *(_DWORD *)(a1 + 12);
    *(_DWORD *)(a1 + 12) = 2;
    if ( v14 == 1 )
    {
      v17 = MSCryptDecrypt(a1, (unsigned __int64)v39, 0x10u, 0, 0, 0, (unsigned __int64)&v40, 0x20u, &v34, 0);
      v12 = v17;
      if ( v17 < 0 )
      {
        v15 = 683;
LABEL_18:
        v16 = (unsigned int)v17;
        goto LABEL_12;
      }
      LODWORD(v18) = (_DWORD)v40;
      v39 = v40;
      *v5 = v41;
    }
    else
    {
      v18 = *v39;
      v19 = v39 + 1;
      v39 = (unsigned __int64 *)*v39;
      memcpy_0(v5, v19, a5 - 8LL);
      v20 = 5;
LABEL_21:
      if ( v20 >= 0 )
      {
        for ( i = v14; ; --i )
        {
          if ( i <= 0 )
          {
            --v20;
            goto LABEL_21;
          }
          v40 = (unsigned __int64 *)(v18 ^ _byteswap_uint64(i + v20 * v14));
          v41 = v5[i - 1];
          v17 = MSCryptDecrypt(a1, (unsigned __int64)&v40, 0x20u, 0, 0, 0, (unsigned __int64)&v40, 0x20u, &v34, 0);
          v12 = v17;
          if ( v17 < 0 )
            break;
          v18 = (unsigned __int64)v40;
          v5[i - 1] = v41;
          v39 = (unsigned __int64 *)v18;
        }
        v15 = 720;
        goto LABEL_18;
      }
      v7 = v37;
    }
    v22 = 1;
    v23 = _byteswap_ulong(HIDWORD(v39));
    v10 = 8;
    v24 = 0;
    v25 = v18 ^ 0xA65959A6 | (v23 >> 3) ^ (v14 - ((v23 & 7) != 0));
    v33 = v25;
    do
    {
      v26 = (v23 & 7) != 0 && v22 >= (unsigned __int64)(v23 & 7) ? *((_BYTE *)&v5[v6 / 8 - 1] + v22) : 0;
      ++v22;
      v24 |= v26;
    }
    while ( v22 < 8 );
    v33 = v24 | v25;
    if ( !*v38 )
    {
      v27 = v36;
      *v7 = v23;
      memcpy_0(v27, v5, v23);
      goto LABEL_34;
    }
    v12 = -1073739509;
    DebugTraceError(3221227787LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\aeskeywrap.c", 752);
LABEL_35:
    v9 = 32;
    goto LABEL_36;
  }
  v11 = 610;
LABEL_3:
  v12 = -1073741811;
  DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\aeskeywrap.c", v11);
LABEL_36:
  v28 = &v40;
  do
  {
    *(_BYTE *)v28 = 0;
    v28 = (unsigned __int64 **)((char *)v28 + 1);
    --v9;
  }
  while ( v9 );
  v29 = &v39;
  do
  {
    *(_BYTE *)v29 = 0;
    v29 = (unsigned __int64 **)((char *)v29 + 1);
    --v10;
  }
  while ( v10 );
  if ( v5 )
  {
    v30 = v6;
    v31 = v5;
    if ( v6 )
    {
      do
      {
        *v31++ = 0;
        --v30;
      }
      while ( v30 );
    }
    MSCryptFree(v5);
  }
  if ( a1 && v35 )
    *(_DWORD *)(a1 + 12) = v35;
  return v12;
}

```

## disassembly

```asm
0x180066428  push    rbp
0x18006642a  push    rbx
0x18006642b  push    rsi
0x18006642c  push    rdi
0x18006642d  push    r12
0x18006642f  push    r13
0x180066431  push    r14
0x180066433  push    r15
0x180066435  lea     rbp, [rsp-17h]
0x18006643a  sub     rsp, 0B8h
0x180066441  mov     rax, cs:__security_cookie
0x180066448  xor     rax, rsp
0x18006644b  mov     [rbp+4Fh+var_50], rax
0x18006644f  xor     esi, esi
0x180066451  mov     [rbp+4Fh+var_78], r9
0x180066455  lea     rax, [rbp+4Fh+var_A0]
0x180066459  mov     [rbp+4Fh+var_9C], esi
0x18006645c  mov     [rbp+4Fh+var_A0], esi
0x18006645f  xor     r13d, r13d
0x180066462  mov     [rbp+4Fh+var_80], rax
0x180066466  mov     r12, r8
0x180066469  xor     eax, eax
0x18006646b  mov     [rbp+4Fh+var_88], r8
0x18006646f  mov     [rbp+4Fh+var_90], rdx
0x180066473  mov     r14, rcx
0x180066476  mov     [rbp+4Fh+var_98], eax
0x180066479  lea     edi, [rsi+20h]
0x18006647c  lea     r15d, [rsi+8]
0x180066480  test    rcx, rcx
0x180066483  jnz     short loc_1800664AD
0x180066485  mov     r9d, 262h
0x18006648b  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180066492  mov     ecx, 0C000000Dh
0x180066497  lea     rdx, aStatus; "Status"
0x18006649e  mov     ebx, 0C000000Dh
0x1800664a3  call    DebugTraceError
0x1800664a8  jmp     loc_180066764
0x1800664ad  test    r12, r12
0x1800664b0  jnz     short loc_1800664BA
0x1800664b2  mov     r9d, 269h
0x1800664b8  jmp     short loc_18006648B
0x1800664ba  mov     r15d, [rbp+4Fh+arg_20]
0x1800664be  mov     edx, r15d
0x1800664c1  call    MSCryptAesKeyUnwrapPadValidateInput
0x1800664c6  mov     ebx, eax
0x1800664c8  test    eax, eax
0x1800664ca  jns     short loc_1800664F2
0x1800664cc  mov     r9d, 270h
0x1800664d2  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800664d9  lea     rdx, aStatus; "Status"
0x1800664e0  mov     ecx, eax
0x1800664e2  call    DebugTraceError
0x1800664e7  mov     r15d, 8
0x1800664ed  jmp     loc_180066764
0x1800664f2  lea     edi, [r15-8]
0x1800664f6  shr     edi, 3
0x1800664f9  lea     r13d, ds:0[rdi*8]
0x180066501  cmp     [rbp+4Fh+var_90], rsi
0x180066505  jnz     short loc_180066516
0x180066507  mov     [r12], r13d
0x18006650b  mov     r15d, 8
0x180066511  jmp     loc_18006675D
0x180066516  cmp     [r12], r13d
0x18006651a  jnb     short loc_18006654A
0x18006651c  mov     ebx, 0C0000023h
0x180066521  mov     r9d, 286h
0x180066527  mov     ecx, 0C0000023h
0x18006652c  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180066533  lea     rdx, aStatus; "Status"
0x18006653a  call    DebugTraceError
0x18006653f  mov     r15d, 8
0x180066545  jmp     loc_18006675F
0x18006654a  mov     ecx, r13d
0x18006654d  call    SafeAllocaAllocateFromHeap
0x180066552  mov     rsi, rax
0x180066555  test    rax, rax
0x180066558  jnz     short loc_18006656C
0x18006655a  mov     ebx, 0C0000017h
0x18006655f  mov     r9d, 28Eh
0x180066565  mov     ecx, 0C0000017h
0x18006656a  jmp     short loc_18006652C
0x18006656c  mov     eax, [r14+0Ch]
0x180066570  mov     [rbp+4Fh+var_98], eax
0x180066573  mov     dword ptr [r14+0Ch], 2
0x18006657b  cmp     edi, 1
0x18006657e  jnz     short loc_1800665ED
0x180066580  mov     rdx, [rbp+4Fh+var_78]
0x180066584  lea     rax, [rbp+4Fh+var_9C]
0x180066588  mov     [rsp+0F0h+var_A8], 0
0x180066590  lea     r8d, [rdi+0Fh]
0x180066594  mov     [rsp+0F0h+var_B0], rax
0x180066599  xor     r9d, r9d
0x18006659c  mov     [rsp+0F0h+var_B8], 20h ; ' '
0x1800665a4  lea     rax, [rbp+4Fh+var_70]
0x1800665a8  mov     [rsp+0F0h+var_C0], rax
0x1800665ad  mov     rcx, r14
0x1800665b0  mov     [rsp+0F0h+var_C8], 0
0x1800665b8  mov     [rsp+0F0h+var_D0], 0
0x1800665c1  call    MSCryptDecrypt
0x1800665c6  mov     ebx, eax
0x1800665c8  test    eax, eax
0x1800665ca  jns     short loc_1800665D9
0x1800665cc  mov     r9d, 2ABh
0x1800665d2  mov     ecx, eax
0x1800665d4  jmp     loc_18006652C
0x1800665d9  mov     rbx, [rbp+4Fh+var_70]
0x1800665dd  mov     rax, [rbp+4Fh+var_68]
0x1800665e1  mov     [rbp+4Fh+var_78], rbx
0x1800665e5  mov     [rsi], rax
0x1800665e8  jmp     loc_1800666B7
0x1800665ed  mov     rax, [rbp+4Fh+var_78]
0x1800665f1  lea     r8, [r15-8]; Size
0x1800665f5  mov     rcx, rsi; void *
0x1800665f8  mov     rbx, [rax]
0x1800665fb  lea     rdx, [rax+8]; Src
0x1800665ff  mov     [rbp+4Fh+var_78], rbx
0x180066603  call    memcpy_0
0x180066608  mov     r12d, 5
0x18006660e  test    r12, r12
0x180066611  js      loc_1800666B3
0x180066617  mov     r15d, edi
0x18006661a  mov     eax, edi
0x18006661c  test    r15, r15
0x18006661f  jle     short loc_1800666A0
0x180066621  imul    rax, r12
0x180066625  mov     [rsp+0F0h+var_A8], 0
0x18006662d  lea     rcx, [rbp+4Fh+var_70]
0x180066631  add     rax, r15
0x180066634  lea     rdx, [rbp+4Fh+var_70]
0x180066638  bswap   rax
0x18006663b  xor     rax, rbx
0x18006663e  xor     r9d, r9d
0x180066641  mov     [rbp+4Fh+var_70], rax
0x180066645  mov     rax, [rsi+r15*8-8]
0x18006664a  mov     [rbp+4Fh+var_68], rax
0x18006664e  lea     rax, [rbp+4Fh+var_9C]
0x180066652  mov     [rsp+0F0h+var_B0], rax
0x180066657  mov     eax, 20h ; ' '
0x18006665c  mov     [rsp+0F0h+var_B8], eax
0x180066660  mov     r8d, eax
0x180066663  mov     [rsp+0F0h+var_C0], rcx
0x180066668  mov     rcx, r14
0x18006666b  mov     [rsp+0F0h+var_C8], 0
0x180066673  mov     [rsp+0F0h+var_D0], 0
0x18006667c  call    MSCryptDecrypt
0x180066681  mov     ebx, eax
0x180066683  test    eax, eax
0x180066685  js      short loc_1800666A8
0x180066687  mov     rbx, [rbp+4Fh+var_70]
0x18006668b  mov     rax, [rbp+4Fh+var_68]
0x18006668f  mov     [rsi+r15*8-8], rax
0x180066694  dec     r15
0x180066697  mov     [rbp+4Fh+var_78], rbx
0x18006669b  jmp     loc_18006661A
0x1800666a0  dec     r12
0x1800666a3  jmp     loc_18006660E
0x1800666a8  mov     r9d, 2D0h
0x1800666ae  jmp     loc_1800665D2
0x1800666b3  mov     r12, [rbp+4Fh+var_88]
0x1800666b7  mov     edx, dword ptr [rbp+4Fh+var_78+4]
0x1800666ba  lea     r9d, [r13-8]
0x1800666be  mov     eax, 0
0x1800666c3  mov     ecx, 1
0x1800666c8  bswap   edx
0x1800666ca  mov     r10d, edx
0x1800666cd  and     r10d, 7
0x1800666d1  lea     r15d, [rcx+7]
0x1800666d5  setnz   al
0x1800666d8  xor     ebx, 0A65959A6h
0x1800666de  sub     edi, eax
0x1800666e0  xor     r8b, r8b
0x1800666e3  mov     eax, edx
0x1800666e5  shr     eax, 3
0x1800666e8  xor     edi, eax
0x1800666ea  or      edi, ebx
0x1800666ec  test    r10d, r10d
0x1800666ef  mov     [rbp+4Fh+var_A0], edi
0x1800666f2  setnz   r11b
0x1800666f6  add     r9, rsi
0x1800666f9  cmp     rcx, r10
0x1800666fc  setnb   al
0x1800666ff  and     al, r11b
0x180066702  neg     al
0x180066704  and     al, [r9+rcx]
0x180066708  inc     rcx
0x18006670b  or      r8b, al
0x18006670e  cmp     rcx, r15
0x180066711  jl      short loc_1800666F9
0x180066713  movzx   eax, r8b
0x180066717  or      edi, eax
0x180066719  mov     rax, [rbp+4Fh+var_80]
0x18006671d  mov     [rbp+4Fh+var_A0], edi
0x180066720  cmp     dword ptr [rax], 0
0x180066723  jz      short loc_18006674A
0x180066725  mov     r9d, 2F0h
0x18006672b  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180066732  lea     rdx, aStatus; "Status"
0x180066739  mov     ecx, 0C000090Bh
0x18006673e  mov     ebx, 0C000090Bh
0x180066743  call    DebugTraceError
0x180066748  jmp     short loc_18006675F
0x18006674a  mov     rcx, [rbp+4Fh+var_90]; void *
0x18006674e  mov     [r12], edx
0x180066752  mov     r8d, edx; Size
0x180066755  mov     rdx, rsi; Src
0x180066758  call    memcpy_0
0x18006675d  xor     ebx, ebx
0x18006675f  mov     edi, 20h ; ' '
0x180066764  lea     rax, [rbp+4Fh+var_70]
0x180066768  mov     byte ptr [rax], 0
0x18006676b  inc     rax
0x18006676e  sub     rdi, 1
0x180066772  jnz     short loc_180066768
0x180066774  lea     rax, [rbp+4Fh+var_78]
0x180066778  mov     byte ptr [rax], 0
0x18006677b  inc     rax
0x18006677e  sub     r15, 1
0x180066782  jnz     short loc_180066778
0x180066784  test    rsi, rsi
0x180066787  jz      short loc_1800667A8
0x180066789  mov     ecx, r13d
0x18006678c  mov     rax, rsi
0x18006678f  test    r13d, r13d
0x180066792  jz      short loc_1800667A0
0x180066794  mov     byte ptr [rax], 0
0x180066797  inc     rax
0x18006679a  sub     rcx, 1
0x18006679e  jnz     short loc_180066794
0x1800667a0  mov     rcx, rsi
0x1800667a3  call    MSCryptFree
0x1800667a8  test    r14, r14
0x1800667ab  jz      short loc_1800667B8
0x1800667ad  mov     eax, [rbp+4Fh+var_98]
0x1800667b0  test    eax, eax
0x1800667b2  jz      short loc_1800667B8
0x1800667b4  mov     [r14+0Ch], eax
0x1800667b8  mov     eax, ebx
0x1800667ba  mov     rcx, [rbp+4Fh+var_50]
0x1800667be  xor     rcx, rsp; StackCookie
0x1800667c1  call    __security_check_cookie
0x1800667c6  add     rsp, 0B8h
0x1800667cd  pop     r15
0x1800667cf  pop     r14
0x1800667d1  pop     r13
0x1800667d3  pop     r12
0x1800667d5  pop     rdi
0x1800667d6  pop     rsi
0x1800667d7  pop     rbx
0x1800667d8  pop     rbp
0x1800667d9  retn
```
