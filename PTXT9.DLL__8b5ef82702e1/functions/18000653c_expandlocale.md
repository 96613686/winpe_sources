# _expandlocale

- ea: `0x18000653c`
- end: `0x18000681c`
- name: `_expandlocale`
- size: `736`
- prototype: ``
- caller_count: `23`
- callee_count: `21`
- tags: ``

## callers

- `0x180002de0`
- `0x180004710`
- `0x1800048e0`
- `0x18000bb10`
- `0x18000d9d4`
- `0x18000f4c4`
- `0x18003636c`
- `0x180036700`
- `0x180041820`
- `0x180042e00`
- `0x1800436f4`
- `0x18006cecc`
- `0x18006e450`
- `0x18006e860`
- `0x1800884d4`
- `0x180094db0`
- `0x1800958b0`
- `0x1800a0770`
- `0x1800a4330`
- `0x1800a4990`
- `0x1800a4d64`
- `0x1800a4ee0`
- `0x1800a5470`

## callees

- `0x18000653c`
- `0x18000b78c`
- `0x18000b7bc`
- `0x18000b820`
- `0x18000be94`
- `0x18001b740`
- `0x1800225a0`
- `0x18002deec`
- `0x180040f30`
- `0x180043924`
- `0x180043944`
- `0x180043a00`
- `0x18004d1c0`
- `0x18004d22c`
- `0x18004d240`
- `0x18004d268`
- `0x18004d8d0`
- `0x18004df30`
- `0x18008ab9c`
- `0x18008ae2c`
- `0x18009b624`

## pseudocode

```c
__int64 __fastcall expandlocale(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  __int64 result; // rax
  unsigned int v5; // r15d
  __int16 v6; // si
  unsigned int v9; // r13d
  __int64 v10; // r8
  __int64 v11; // rdx
  int v12; // r12d
  int v13; // r14d
  unsigned int v14; // r14d
  unsigned int v15; // esi
  int v16; // eax
  bool v17; // cc
  int v18; // r8d
  __int64 v19; // rcx
  __int32 v20; // ecx
  int v21; // eax
  __int32 v22; // eax
  __int32 v23; // ecx
  void *v24; // rax
  size_t v25; // r9
  __int64 v26; // rsi
  __int64 v27; // rdx
  __int64 v28; // rdx
  int v29; // ecx
  int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // r8
  void *v33; // rax
  size_t v34; // r9
  __int64 v35; // rcx
  int v36; // eax
  int v37; // esi
  int v38; // esi
  void *v39; // rax
  size_t v40; // r9
  __int16 v41; // [rsp+40h] [rbp-C0h]
  __int32 v42; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD v43[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v44; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v45; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v46[16]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v47; // [rsp+80h] [rbp-80h] BYREF
  __m256i v48; // [rsp+90h] [rbp-70h]
  __int128 v49; // [rsp+B0h] [rbp-50h]
  __int128 v50; // [rsp+C0h] [rbp-40h]
  __int128 v51; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v52; // [rsp+E0h] [rbp-20h]
  __int128 v53; // [rsp+F0h] [rbp-10h]
  __int128 v54; // [rsp+100h] [rbp+0h]
  __int128 v55; // [rsp+110h] [rbp+10h]
  __int128 v56; // [rsp+120h] [rbp+20h]
  __int128 v57; // [rsp+130h] [rbp+30h]
  __int64 v58; // [rsp+140h] [rbp+40h]
  __int128 v59; // [rsp+150h] [rbp+50h] BYREF
  __m256i v60; // [rsp+160h] [rbp+60h]
  __int128 v61; // [rsp+180h] [rbp+80h]
  __int128 v62; // [rsp+190h] [rbp+90h]
  __int128 v63; // [rsp+1A0h] [rbp+A0h]
  __int128 v64; // [rsp+1B0h] [rbp+B0h]
  __int128 v65; // [rsp+1C0h] [rbp+C0h]
  __int128 v66; // [rsp+1D0h] [rbp+D0h]
  __int128 v67; // [rsp+1E0h] [rbp+E0h]
  __int128 v68; // [rsp+1F0h] [rbp+F0h]
  __int128 v69; // [rsp+200h] [rbp+100h]
  __int64 v70; // [rsp+210h] [rbp+110h]
  _QWORD v71[2]; // [rsp+220h] [rbp+120h] BYREF

  result = 0;
  v41 = a3;
  v5 = a4;
  v6 = a3;
  v9 = a4;
  v43[0] = 0;
  if ( !*(_QWORD *)(a1 + 7760) || (*(_BYTE *)(a1 + 7776) & 2) != 0 )
    return result;
  if ( (_WORD)a3 == 0xFFFF )
  {
    v24 = (void *)sub_18004D1C0(qword_1800DABA8, a4);
    result = (__int64)memcpy(v24, &dword_1800DABB0, v25);
    dword_1800DABB0 = v5;
    return result;
  }
  result = sub_18000B820(a4, &v47, a3, &v44);
  if ( !(_DWORD)result )
    return result;
  v11 = (unsigned int)(__int16)v47;
  v12 = -1;
  if ( (__int16)v47 == 20
    || (__int16)v47 == 21
    || (__int16)v47 == 22
    || (__int16)v47 == 23
    || (unsigned int)((__int16)v47 - 24) <= 1 )
  {
    v12 = 0;
  }
  v13 = v54;
  if ( (_WORD)v47 )
    goto LABEL_11;
  v11 = *(unsigned int *)(*(_QWORD *)(a1 + 7576) + 1984LL);
  if ( (int)v11 >= 0 )
  {
    if ( (v54 & 1) != 0 )
    {
      v26 = v48.m256i_i64[1];
      sub_180040F30(v48.m256i_i64[1], HIDWORD(v54), &v42, v71);
      if ( v48.m256i_i32[4] < v42 )
        goto LABEL_63;
      v10 = HIDWORD(v71[0]);
      if ( v48.m256i_i32[5] != HIDWORD(v71[0]) + v42 )
        goto LABEL_63;
      v27 = HIDWORD(v54);
      HIDWORD(v71[0]) += *(_DWORD *)(a2 + 12) - v48.m256i_i32[5];
    }
    else
    {
      v26 = *((_QWORD *)&v47 + 1);
      if ( !*((_QWORD *)&v47 + 1) )
        goto LABEL_63;
      sub_180040F30(*((_QWORD *)&v47 + 1), v11, &v42, v71);
      if ( *(_DWORD *)(a2 + 8) < v42 )
        goto LABEL_63;
      v10 = *(unsigned int *)(a2 + 12);
      v11 = (unsigned int)(v42 + HIDWORD(v71[0]));
      if ( (int)v10 <= (int)v11 )
        goto LABEL_63;
      v28 = *(_QWORD *)(a1 + 7576);
      HIDWORD(v71[0]) = v10 - v42;
      v27 = *(unsigned int *)(v28 + 1984);
    }
    sub_18001B740(*(_QWORD *)(v26 + 136), v27, v71);
LABEL_63:
    v6 = v41;
  }
  if ( (v13 & 1) != 0 )
  {
    v48.m256i_i32[5] = *(_DWORD *)(a2 + 12);
LABEL_13:
    if ( v12 )
    {
      v20 = v48.m256i_i32[1] - v48.m256i_i32[0];
      v10 = *(unsigned int *)(a2 + 12);
      v11 = (unsigned int)(*(_DWORD *)(a2 + 12) - *(_DWORD *)(a2 + 8));
      v21 = *(_DWORD *)(a2 + 12) - *(_DWORD *)(a2 + 8);
      if ( v48.m256i_i32[1] <= v48.m256i_i32[0] )
        v20 = 0;
      if ( (int)v10 <= *(_DWORD *)(a2 + 8) )
        v21 = 0;
      if ( v21 == v20 )
        goto LABEL_41;
      if ( (int)v10 <= *(_DWORD *)(a2 + 8) )
        v11 = 0;
      if ( (_DWORD)v11 )
LABEL_41:
        DWORD2(v54) = -1;
    }
    goto LABEL_14;
  }
LABEL_11:
  if ( (*(_BYTE *)(a1 + 7776) & 8) == 0 || (v13 & 2) == 0 )
    goto LABEL_12;
  v29 = *(_DWORD *)(a2 + 8);
  v30 = *(_DWORD *)(a2 + 12) - v29;
  if ( *(_DWORD *)(a2 + 12) <= v29 )
    v30 = 0;
  if ( v30 )
  {
LABEL_12:
    *(_OWORD *)&v48.m256i_u64[1] = *(_OWORD *)a2;
    if ( (*(_BYTE *)(a1 + 7776) & 4) != 0 )
    {
      v22 = sub_1800225A0(*(_QWORD *)a2, *(unsigned int *)(a2 + 8));
      v23 = v48.m256i_i32[5];
      if ( *(_DWORD *)(a2 + 12) < v22 )
        v23 = v22;
      v48.m256i_i32[5] = v23;
    }
    goto LABEL_13;
  }
  if ( v12 )
  {
    v71[0] = 0;
    v59 = v47;
    v60 = v48;
    v61 = v49;
    v62 = v50;
    v63 = v51;
    v64 = v52;
    v65 = v53;
    v66 = v54;
    v67 = v55;
    v68 = v56;
    v69 = v57;
    v70 = v58;
    v31 = *(_QWORD *)(a1 + 7760);
    v45 = v44;
    if ( (*(unsigned int (__fastcall **)(__int64, _QWORD *, _BYTE *, __int32 *))(*(_QWORD *)v31 + 40LL))(
           v31,
           v71,
           v46,
           &v42)
      && v71[0] == a1 + 32 )
    {
      v9 = v42;
      if ( (unsigned int)sub_18000B820((unsigned int)v42, &v47, v32, &v44)
        && (unsigned int)sub_18008AB9C(*(_QWORD *)(a1 + 72), &v47, &v44, 0xFFFFFFFFLL)
        && (unsigned int)sub_18008AB9C(*(_QWORD *)(a1 + 72), &v59, &v45, 0) )
      {
        sub_18004D268(v71);
        v33 = (void *)sub_18004D1C0(qword_1800DABA8, v5);
        memcpy(v33, &dword_1800DABB0, v34);
        dword_1800DABB0 = v5;
        DWORD1(v55) = sub_180043944(*(_QWORD *)(a1 + 72), &v47);
        HIDWORD(v44) = DWORD1(v55) + 176;
        v43[0] = 1329876565;
        v43[1] = v9;
        result = sub_18000BE94(qword_1800DA9F8, (unsigned int)v43, DWORD1(v55) + 176, 1329876565, (__int64)&v44, 0, 16);
        if ( !(_DWORD)result )
          return result;
        v13 = v54;
        v48.m256i_i32[5] = v60.m256i_i32[0];
        v48.m256i_i32[4] = v60.m256i_i32[0];
        v48.m256i_i32[0] = v60.m256i_i32[0];
        v43[0] = -1;
        goto LABEL_13;
      }
      v13 = v54;
    }
    sub_18004D268(v71);
    goto LABEL_12;
  }
LABEL_14:
  v14 = v13 & 0xFFFFFFFD;
  WORD1(v47) = v6;
  v15 = HIDWORD(v53) & 0xFFFFFFF7 | ((unsigned int)dword_1800DAEBC >> 1) & 8;
  v16 = 0;
  v17 = *(_DWORD *)(a1 + 7780) <= 0;
  HIDWORD(v53) = v15;
  if ( !v17 )
    v16 = 4;
  LODWORD(v54) = v14 & 0xFFFFFFFB | v16;
  if ( v12 )
  {
    if ( (int)v50 <= 0
      || (v35 = *(_QWORD *)(a1 + 7576), !*(_DWORD *)(v35 + 64))
      || (unsigned int)sub_18009B624(v35, *(_QWORD *)(v35 + 2048), v10, 0) )
    {
      sub_180043924(*(_QWORD *)(a1 + 7576), &v51, 0);
      if ( SDWORD2(v52) > 0 )
      {
        v36 = sub_18004D22C(*(_QWORD *)(*(_QWORD *)(a1 + 7576) + 2056LL));
        v37 = HIDWORD(v44) + 16 * v36;
        result = sub_18000B7BC();
        v5 = result;
        if ( (_DWORD)result == -1 )
          return result;
        HIDWORD(v71[0]) = result;
        LODWORD(v71[0]) = 1329876565;
        result = sub_18000BE94(qword_1800DA9F8, (unsigned int)v71, v37, 1329876565, (__int64)&v45, 0, 16);
        if ( !(_DWORD)result )
          return result;
        result = sub_18008AB9C(*(_QWORD *)(a1 + 72), &v47, &v44, 0xFFFFFFFFLL);
        if ( !(_DWORD)result )
          return result;
        result = sub_180043A00(*(_QWORD *)(a1 + 72), &v47, &v45);
        if ( !(_DWORD)result )
          return result;
        v38 = DWORD1(v55);
        result = sub_18008AE2C(*(_QWORD *)(*(_QWORD *)(a1 + 7576) + 2048LL), &v45, (unsigned int)(DWORD1(v55) + 176));
        if ( !(_DWORD)result )
          return result;
        result = sub_18008AE2C(
                   *(_QWORD *)(*(_QWORD *)(a1 + 7576) + 2056LL),
                   &v45,
                   (unsigned int)(v38 + DWORD2(v53) + 176));
        if ( !(_DWORD)result )
          return result;
        v39 = (void *)sub_18004D1C0(qword_1800DABA8, v9);
        memcpy(v39, &dword_1800DABB0, v40);
        v44 = v45;
        dword_1800DABB0 = v9;
      }
    }
    else
    {
      HIDWORD(v53) = v15 | 1;
    }
  }
  result = sub_18000B78C(&v47, v11, &v44);
  if ( !(_DWORD)result )
    return result;
  if ( *(_QWORD *)a2 )
    (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 7760) + 120LL))(
      *(_QWORD *)(a1 + 7760),
      *(unsigned int *)(*(_QWORD *)a2 + 24LL));
  result = v43[0];
  if ( v43[0] )
  {
    result = sub_180043A00(*(_QWORD *)(a1 + 72), &v47, &v44);
    if ( !(_DWORD)result )
      return result;
    result = v43[0];
  }
  if ( (v54 & 1) == 0 && !(_DWORD)result )
  {
    v18 = 0;
    if ( *(_QWORD *)a2 )
      v18 = *(_DWORD *)(*(_QWORD *)a2 + 24LL);
    result = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, int))(**(_QWORD **)(a1 + 7760) + 32LL))(
               *(_QWORD *)(a1 + 7760),
               a1 + 32,
               (unsigned int)v41,
               v5,
               v18);
    if ( *(_QWORD *)a2 )
    {
      v19 = *(_QWORD *)(*(_QWORD *)a2 + 40LL);
      if ( v19 )
        result = sub_18002DEEC(v19, 4294967281LL, (unsigned int)v41);
    }
  }
  if ( (unsigned __int16)v47 <= 2u )
    *(_DWORD *)(a1 + 7776) |= 8u;
  *(_DWORD *)(a1 + 7776) |= 1u;
  return result;
}

```

## disassembly

```asm
0x18000653c  push    rbp
0x18000653e  push    rbx
0x18000653f  push    rsi
0x180006540  push    rdi
0x180006541  push    r12
0x180006543  push    r13
0x180006545  push    r14
0x180006547  push    r15
0x180006549  lea     rbp, [rsp-148h]
0x180006551  sub     rsp, 248h
0x180006558  mov     rax, cs:__security_cookie
0x18000655f  xor     rax, rsp
0x180006562  mov     [rbp+180h+var_50], rax
0x180006569  xor     eax, eax
0x18000656b  mov     [rsp+280h+var_240], r8w
0x180006571  mov     r15d, r9d
0x180006574  movzx   esi, r8w
0x180006578  mov     rdi, rdx
0x18000657b  mov     rbx, rcx
0x18000657e  mov     r13d, r9d
0x180006581  mov     [rsp+280h+var_238], eax
0x180006585  cmp     [rcx+1E50h], rax
0x18000658c  jz      loc_1800066F7
0x180006592  test    byte ptr [rcx+1E60h], 2
0x180006599  jnz     loc_1800066F7
0x18000659f  or      r14d, 0FFFFFFFFh
0x1800065a3  cmp     r8w, r14w
0x1800065a7  jz      loc_18005572A
0x1800065ad  lea     r9, [rsp+280h+var_230]
0x1800065b2  mov     ecx, r13d
0x1800065b5  lea     rdx, [rbp+180h+var_200]
0x1800065b9  call    sub_18000B820
0x1800065be  xor     r9d, r9d
0x1800065c1  test    eax, eax
0x1800065c3  jz      loc_1800066F7
0x1800065c9  movsx   edx, [rbp+180h+var_200]
0x1800065cd  mov     r12d, r14d
0x1800065d0  mov     ecx, edx
0x1800065d2  sub     ecx, 14h
0x1800065d5  jz      short loc_1800065EA
0x1800065d7  sub     ecx, 1
0x1800065da  jz      short loc_1800065EA
0x1800065dc  sub     ecx, 1
0x1800065df  jz      short loc_1800065EA
0x1800065e1  sub     ecx, 1
0x1800065e4  jnz     loc_18000671A
0x1800065ea  mov     r12d, r9d
0x1800065ed  mov     r14d, [rbp+180h+var_180]
0x1800065f1  test    dx, dx
0x1800065f4  jz      loc_18005575E
0x1800065fa  test    byte ptr [rbx+1E60h], 8
0x180006601  jnz     loc_180006773
0x180006607  movups  xmm0, xmmword ptr [rdi]
0x18000660a  mov     eax, 4
0x18000660f  movdqu  [rbp+180h+var_1E8], xmm0
0x180006614  test    [rbx+1E60h], al
0x18000661a  jnz     loc_1800067ED
0x180006620  xor     r9d, r9d
0x180006623  test    r12d, r12d
0x180006626  jnz     loc_180006782
0x18000662c  mov     eax, [rbp+180h+var_184]
0x18000662f  and     r14d, 0FFFFFFFDh
0x180006633  and     eax, 0FFFFFFF7h
0x180006636  mov     [rbp+180h+var_1FE], si
0x18000663a  mov     esi, cs:dword_1800DAEBC
0x180006640  mov     ecx, 4
0x180006645  shr     esi, 1
0x180006647  and     esi, 8
0x18000664a  or      esi, eax
0x18000664c  mov     eax, r9d
0x18000664f  cmp     [rbx+1E64h], r9d
0x180006656  mov     [rbp+180h+var_184], esi
0x180006659  cmovg   eax, ecx
0x18000665c  and     r14d, 0FFFFFFFBh
0x180006660  or      eax, r14d
0x180006663  xor     r14d, r14d
0x180006666  mov     [rbp+180h+var_180], eax
0x180006669  test    r12d, r12d
0x18000666c  jnz     loc_1800067B5
0x180006672  lea     r8, [rsp+280h+var_230]
0x180006677  lea     rcx, [rbp+180h+var_200]
0x18000667b  call    sub_18000B78C
0x180006680  test    eax, eax
0x180006682  jz      short loc_1800066F7
0x180006684  mov     rdx, [rdi]
0x180006687  test    rdx, rdx
0x18000668a  jnz     loc_180006731
0x180006690  mov     eax, [rsp+280h+var_238]
0x180006694  test    eax, eax
0x180006696  jnz     loc_180055BC9
0x18000669c  test    byte ptr [rbp+180h+var_180], 1
0x1800066a0  jnz     short loc_1800066E5
0x1800066a2  test    eax, eax
0x1800066a4  jnz     short loc_1800066E5
0x1800066a6  mov     rax, [rdi]
0x1800066a9  mov     r8d, r14d
0x1800066ac  test    rax, rax
0x1800066af  jnz     loc_18000674D
0x1800066b5  mov     rcx, [rbx+1E50h]
0x1800066bc  lea     rdx, [rbx+20h]
0x1800066c0  movsx   esi, [rsp+280h+var_240]
0x1800066c5  mov     r9d, r15d
0x1800066c8  mov     dword ptr [rsp+280h+var_260], r8d
0x1800066cd  mov     r8d, esi
0x1800066d0  mov     rax, [rcx]
0x1800066d3  mov     rax, [rax+20h]
0x1800066d7  call    cs:__guard_dispatch_icall_fptr
0x1800066dd  mov     rcx, [rdi]
0x1800066e0  test    rcx, rcx
0x1800066e3  jnz     short loc_180006756
0x1800066e5  cmp     [rbp+180h+var_200], 2
0x1800066ea  jbe     loc_1800067E1
0x1800066f0  or      dword ptr [rbx+1E60h], 1
0x1800066f7  mov     rcx, [rbp+180h+var_50]
0x1800066fe  xor     rcx, rsp; StackCookie
0x180006701  call    __security_check_cookie
0x180006706  add     rsp, 248h
0x18000670d  pop     r15
0x18000670f  pop     r14
0x180006711  pop     r13
0x180006713  pop     r12
0x180006715  pop     rdi
0x180006716  pop     rsi
0x180006717  pop     rbx
0x180006718  pop     rbp
0x180006719  retn
0x18000671a  sub     ecx, 1
0x18000671d  jz      loc_1800065EA
0x180006723  cmp     ecx, 1
0x180006726  jnz     loc_1800065ED
0x18000672c  jmp     loc_1800065EA
0x180006731  mov     rcx, [rbx+1E50h]
0x180006738  mov     edx, [rdx+18h]
0x18000673b  mov     rax, [rcx]
0x18000673e  mov     rax, [rax+78h]
0x180006742  call    cs:__guard_dispatch_icall_fptr
0x180006748  jmp     loc_180006690
0x18000674d  mov     r8d, [rax+18h]
0x180006751  jmp     loc_1800066B5
0x180006756  mov     rcx, [rcx+28h]
0x18000675a  test    rcx, rcx
0x18000675d  jz      short loc_1800066E5
0x18000675f  xor     r9d, r9d
0x180006762  mov     r8d, esi
0x180006765  lea     edx, [r9-0Fh]
0x180006769  call    sub_18002DEEC
0x18000676e  jmp     loc_1800066E5
0x180006773  test    r14b, 2
0x180006777  jz      loc_180006607
0x18000677d  jmp     loc_180055843
0x180006782  mov     eax, [rbp+180h+var_1EC]
0x180006785  mov     ecx, eax
0x180006787  sub     ecx, [rbp+180h+var_1F0]
0x18000678a  mov     r8d, [rdi+0Ch]
0x18000678e  mov     edx, r8d
0x180006791  sub     edx, [rdi+8]
0x180006794  cmp     eax, [rbp+180h+var_1F0]
0x180006797  mov     eax, edx
0x180006799  cmovle  ecx, r9d
0x18000679d  cmp     r8d, [rdi+8]
0x1800067a1  cmovle  eax, r9d
0x1800067a5  cmp     eax, ecx
0x1800067a7  jnz     short loc_180006809
0x1800067a9  mov     [rbp+180h+var_178], 0FFFFFFFFh
0x1800067b0  jmp     loc_18000662C
0x1800067b5  cmp     dword ptr [rbp+180h+var_1C0], r14d
0x1800067b9  jg      loc_180055A54
0x1800067bf  mov     rcx, [rbx+1D98h]
0x1800067c6  lea     rdx, [rbp+180h+var_1B0]
0x1800067ca  xor     r8d, r8d
0x1800067cd  call    sub_180043924
0x1800067d2  cmp     [rbp+180h+var_198], r14d
0x1800067d6  jle     loc_180006672
0x1800067dc  jmp     loc_180055A84
0x1800067e1  or      dword ptr [rbx+1E60h], 8
0x1800067e8  jmp     loc_1800066F0
0x1800067ed  mov     edx, [rdi+8]
0x1800067f0  mov     rcx, [rdi]
0x1800067f3  call    sub_1800225A0
0x1800067f8  mov     ecx, dword ptr [rbp+180h+var_1E8+0Ch]
0x1800067fb  cmp     [rdi+0Ch], eax
0x1800067fe  cmovl   ecx, eax
0x180006801  mov     dword ptr [rbp+180h+var_1E8+0Ch], ecx
0x180006804  jmp     loc_180006620
0x180006809  cmp     r8d, [rdi+8]
0x18000680d  cmovle  edx, r9d
0x180006811  test    edx, edx
0x180006813  jz      loc_18000662C
0x180006819  jmp     short loc_1800067A9
0x18005572a  mov     rcx, cs:qword_1800DABA8
0x180055731  mov     edx, r15d
0x180055734  mov     rax, [rcx]
0x180055737  movsxd  r9, dword ptr [rax+8]
0x18005573b  call    sub_18004D1C0
0x180055740  mov     rcx, rax; void *
0x180055743  lea     rdx, dword_1800DABB0; Src
0x18005574a  mov     r8, r9; Size
0x18005574d  call    memcpy
0x180055752  mov     cs:dword_1800DABB0, r15d
0x180055759  jmp     loc_1800066F7
0x18005575e  mov     rax, [rbx+1D98h]
0x180055765  mov     edx, [rax+7C0h]
0x18005576b  test    edx, edx
0x18005576d  js      loc_18005582E
0x180055773  test    r14b, 1
0x180055777  jz      short loc_1800557C5
0x180055779  mov     rsi, qword ptr [rbp+180h+var_1E8]
0x18005577d  lea     r9, [rbp+180h+var_60]
0x180055784  mov     edx, [rbp+180h+var_174]
0x180055787  lea     r8, [rsp+280h+var_23C]
0x18005578c  mov     rcx, rsi
0x18005578f  call    sub_180040F30
0x180055794  mov     eax, [rsp+280h+var_23C]
0x180055798  cmp     dword ptr [rbp+180h+var_1E8+8], eax
0x18005579b  jl      loc_180055826
0x1800557a1  mov     r8d, dword ptr [rbp+180h+var_60+4]
0x1800557a8  add     eax, r8d
0x1800557ab  cmp     dword ptr [rbp+180h+var_1E8+0Ch], eax
0x1800557ae  jnz     short loc_180055826
0x1800557b0  mov     eax, [rdi+0Ch]
0x1800557b3  sub     eax, dword ptr [rbp+180h+var_1E8+0Ch]
0x1800557b6  mov     edx, [rbp+180h+var_174]
0x1800557b9  add     r8d, eax
0x1800557bc  mov     dword ptr [rbp+180h+var_60+4], r8d
0x1800557c3  jmp     short loc_180055813
0x1800557c5  mov     rsi, [rbp+180h+var_1F8]
0x1800557c9  test    rsi, rsi
0x1800557cc  jz      short loc_180055829
0x1800557ce  lea     r9, [rbp+180h+var_60]
0x1800557d5  mov     rcx, rsi
0x1800557d8  lea     r8, [rsp+280h+var_23C]
0x1800557dd  call    sub_180040F30
0x1800557e2  mov     ecx, [rsp+280h+var_23C]
0x1800557e6  cmp     [rdi+8], ecx
0x1800557e9  jl      short loc_180055826
0x1800557eb  mov     edx, dword ptr [rbp+180h+var_60+4]
0x1800557f1  mov     r8d, [rdi+0Ch]
0x1800557f5  add     edx, ecx
0x1800557f7  cmp     r8d, edx
0x1800557fa  jle     short loc_180055826
0x1800557fc  mov     rdx, [rbx+1D98h]
0x180055803  sub     r8d, ecx
0x180055806  mov     dword ptr [rbp+180h+var_60+4], r8d
0x18005580d  mov     edx, [rdx+7C0h]
0x180055813  mov     rcx, [rsi+88h]
0x18005581a  lea     r8, [rbp+180h+var_60]
0x180055821  call    sub_18001B740
0x180055826  xor     r9d, r9d
0x180055829  movzx   esi, [rsp+280h+var_240]
0x18005582e  test    r14b, 1
0x180055832  jz      loc_1800065FA
0x180055838  mov     eax, [rdi+0Ch]
0x18005583b  mov     dword ptr [rbp+180h+var_1E8+0Ch], eax
0x18005583e  jmp     loc_180006623
0x180055843  mov     ecx, [rdi+8]
0x180055846  mov     eax, [rdi+0Ch]
0x180055849  sub     eax, ecx
0x18005584b  cmp     [rdi+0Ch], ecx
0x18005584e  cmovle  eax, r9d
0x180055852  test    eax, eax
0x180055854  jnz     loc_180006607
0x18005585a  test    r12d, r12d
0x18005585d  jz      loc_18000662C
0x180055863  lea     rax, [rbp+180h+var_200]
0x180055867  mov     [rbp+180h+var_60], r9
0x18005586e  movups  xmm0, xmmword ptr [rax]
0x180055871  lea     rcx, [rbp+180h+var_130]
0x180055875  mov     edx, 80h
0x18005587a  movups  xmm1, xmmword ptr [rax+10h]
0x18005587e  lea     r9, [rsp+280h+var_23C]
0x180055883  movups  xmmword ptr [rcx], xmm0
0x180055886  lea     r8, [rsp+280h+var_210]
0x18005588b  movups  xmm0, xmmword ptr [rax+20h]
0x18005588f  movups  xmmword ptr [rcx+10h], xmm1
0x180055893  movups  xmm1, xmmword ptr [rax+30h]
0x180055897  movups  xmmword ptr [rcx+20h], xmm0
0x18005589b  movups  xmm0, xmmword ptr [rax+40h]
0x18005589f  movups  xmmword ptr [rcx+30h], xmm1
0x1800558a3  movups  xmm1, xmmword ptr [rax+50h]
0x1800558a7  movups  xmmword ptr [rcx+40h], xmm0
0x1800558ab  movups  xmm0, xmmword ptr [rax+60h]
0x1800558af  movups  xmmword ptr [rcx+50h], xmm1
0x1800558b3  movups  xmmword ptr [rcx+60h], xmm0
0x1800558b7  add     rcx, rdx
0x1800558ba  movups  xmm0, xmmword ptr [rax+70h]
0x1800558be  add     rax, rdx
0x1800558c1  lea     rdx, [rbp+180h+var_60]
0x1800558c8  movups  xmmword ptr [rcx-10h], xmm0
0x1800558cc  movups  xmm1, xmmword ptr [rax]
0x1800558cf  movups  xmm0, xmmword ptr [rax+10h]
0x1800558d3  movups  xmmword ptr [rcx], xmm1
0x1800558d6  movups  xmm1, xmmword ptr [rax+20h]
0x1800558da  movups  xmmword ptr [rcx+10h], xmm0
0x1800558de  movups  xmm0, xmmword ptr [rax+30h]
0x1800558e2  mov     rax, [rax+40h]
0x1800558e6  movups  xmmword ptr [rcx+20h], xmm1
0x1800558ea  movups  xmmword ptr [rcx+30h], xmm0
0x1800558ee  mov     [rcx+40h], rax
0x1800558f2  mov     rcx, [rbx+1E50h]
0x1800558f9  movaps  xmm0, [rsp+280h+var_230]
  ... truncated ...
```
