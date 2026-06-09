# vdbeCommit

- ea: `0x180040640`
- end: `0x180040df9`
- name: `vdbeCommit`
- size: `1977`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003fbf8`

## callees

- `0x18001eb90`
- `0x1800257e0`
- `0x1800324d0`
- `0x18003338c`
- `0x18003f2cc`
- `0x18003f490`
- `0x18003f4fc`
- `0x18003f690`
- `0x18003f8d0`
- `0x18003fb60`
- `0x1800405a0`
- `0x180040640`
- `0x180040e00`
- `0x180040ecc`
- `0x180040ff0`
- `0x1800412a8`
- `0x180041490`
- `0x180041b5c`
- `0x180041d10`
- `0x180041eb0`
- `0x180047100`
- `0x18004ae40`
- `0x180053a98`
- `0x1800644a8`
- `0x18006ed3c`
- `0x18006f234`
- `0x180073510`
- `0x180074f3c`
- `0x1800b0010`

## string_xrefs

- `0x180040ad4`: `MJ delete: %s`

## pseudocode

```c
__int64 __fastcall vdbeCommit(__int64 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  int v5; // r13d
  int v6; // r14d
  unsigned int v7; // esi
  int v8; // ebp
  int v11; // ebx
  __int64 v13; // rcx
  __int64 v14; // r12
  __int64 (__fastcall *v15)(_QWORD); // rax
  const char *v16; // r9
  char *v17; // r8
  __int64 *v18; // rax
  __int64 v19; // rdx
  char v20; // r10
  int *v21; // rcx
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // r14
  int v25; // ebx
  __int64 v26; // rax
  int v27; // ebx
  __int64 v28; // rbp
  int v29; // ebx
  __int64 v30; // rbp
  _QWORD *v31; // r14
  __int64 v32; // rbx
  bool v33; // cc
  int v34; // ebp
  __int64 v35; // r14
  __int64 v36; // rcx
  void (__fastcall *v37)(__int64, __int64, char *, const char *); // rax
  __int64 v38; // r14
  __int64 v39; // rcx
  __int64 (__fastcall *v40)(__int64); // rax
  bool v41; // zf
  __int64 v42; // r13
  __int64 v43; // r12
  int v44; // r15d
  const char *v45; // rbp
  void (__fastcall *v46)(__int64, const char *, _QWORD); // rax
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // rbx
  int i; // r15d
  int v51; // r15d
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rcx
  int v55; // eax
  __int64 v56; // rdx
  __int64 v57; // rcx
  int v58; // eax
  __int64 v59; // rbp
  __int64 v60; // r15
  __int64 v61; // rcx
  __int64 (__fastcall *v62)(__int64, const char *, __int64); // rax
  unsigned int v63; // ebx
  int j; // ebx
  __int64 v65; // rcx
  int v66; // [rsp+80h] [rbp+8h] BYREF
  __int64 v67; // [rsp+90h] [rbp+18h] BYREF
  __int64 v68; // [rsp+98h] [rbp+20h] BYREF

  v4 = a1[73];
  v5 = 0;
  a1[73] = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  do
  {
    if ( v8 >= *((_DWORD *)a1 + 137) )
      break;
    v13 = *(_QWORD *)(v4 + 8LL * v8);
    v14 = *(_QWORD *)(v13 + 16);
    if ( v14 )
    {
      v15 = *(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v14 + 120LL);
      if ( v15 )
      {
        v7 = v15(*(_QWORD *)(v13 + 16));
        sqlite3VtabImportErrmsg(a2, v14);
      }
    }
    ++v8;
  }
  while ( !v7 );
  a1[73] = v4;
  v11 = 0;
  if ( v7 )
    return v7;
  while ( v11 < *((_DWORD *)a1 + 10) )
  {
    v59 = 32LL * v11;
    v60 = *(_QWORD *)(a1[4] + v59 + 8);
    if ( v60 && *(_BYTE *)(v60 + 16) == 2 )
    {
      v6 = 1;
      if ( *(_BYTE *)(v60 + 17) )
      {
        ++*(_DWORD *)(v60 + 20);
        if ( !*(_BYTE *)(v60 + 18) )
          btreeLockCarefully(v60, a2, a3, a4);
      }
      v61 = **(_QWORD **)(v60 + 8);
      if ( *(_BYTE *)(a1[4] + v59 + 16) != 1
        && *((_BYTE *)&qword_1800BE080 + *(unsigned __int8 *)(v61 + 9))
        && !(unsigned int)sqlite3PagerIsMemdb() )
      {
        ++v5;
      }
      v7 = sqlite3PagerExclusiveLock(v61);
      if ( *(_BYTE *)(v60 + 17) )
      {
        v41 = (*(_DWORD *)(v60 + 20))-- == 1;
        if ( v41 )
          unlockBtreeMutex(v60);
      }
    }
    ++v11;
    if ( v7 )
      return v7;
  }
  if ( v6 )
  {
    v40 = (__int64 (__fastcall *)(__int64))a1[36];
    if ( v40 )
    {
      v7 = v40(a1[35]);
      if ( v7 )
        return 531;
    }
  }
  v16 = (const char *)&dword_1800B56B4;
  v17 = byte_1800CD000;
  v18 = *(__int64 **)(*(_QWORD *)(a1[4] + 8) + 8LL);
  v19 = *v18;
  v20 = *(_BYTE *)(*v18 + 19);
  if ( v20 || *(char **)v19 == byte_1800CD000 )
  {
    v21 = &dword_1800B56B4;
  }
  else
  {
    v21 = *(int **)(v19 + 216);
    if ( !v21 )
    {
LABEL_25:
      v27 = 0;
      do
      {
        if ( v27 >= *((_DWORD *)a1 + 10) )
          break;
        v28 = *(_QWORD *)(32LL * v27 + a1[4] + 8);
        if ( v28 )
        {
          v7 = 0;
          if ( *(_BYTE *)(v28 + 16) == 2 )
          {
            v31 = *(_QWORD **)(v28 + 8);
            if ( *(_BYTE *)(v28 + 17) )
            {
              ++*(_DWORD *)(v28 + 20);
              if ( !*(_BYTE *)(v28 + 18) )
                btreeLockCarefully(v28, v19, v17, v16);
            }
            if ( *((_BYTE *)v31 + 33) && (v7 = autoVacuumCommit(v28)) != 0 )
            {
              sqlite3BtreeLeave(v28);
            }
            else
            {
              if ( *((_BYTE *)v31 + 35) )
                *(_DWORD *)(*v31 + 32LL) = *((_DWORD *)v31 + 16);
              v7 = sqlite3PagerCommitPhaseOne(*v31, 0, 0, v16);
              if ( *(_BYTE *)(v28 + 17) )
              {
                v41 = (*(_DWORD *)(v28 + 20))-- == 1;
                if ( v41 )
                  unlockBtreeMutex(v28);
              }
            }
          }
        }
        ++v27;
      }
      while ( !v7 );
      v29 = 0;
      if ( v7 )
        return v7;
      while ( 1 )
      {
        if ( v29 >= *((_DWORD *)a1 + 10) )
        {
          v32 = a1[73];
          if ( v32 )
          {
            v33 = *((_DWORD *)a1 + 137) <= 0;
            v34 = 0;
            a1[73] = 0;
            if ( !v33 )
            {
              do
              {
                v35 = *(_QWORD *)(v32 + 8LL * v34);
                v36 = *(_QWORD *)(v35 + 16);
                if ( v36 )
                {
                  v37 = *(void (__fastcall **)(__int64, __int64, char *, const char *))(*(_QWORD *)v36 + 128LL);
                  if ( v37 )
                    v37(v36, v19, v17, v16);
                }
                *(_DWORD *)(v35 + 32) = 0;
                sqlite3VtabUnlock(v35);
                ++v34;
              }
              while ( v34 < *((_DWORD *)a1 + 137) );
            }
            sqlite3DbFree(a1, v32);
            *((_DWORD *)a1 + 137) = 0;
          }
          return v7;
        }
        v30 = *(_QWORD *)(32LL * v29 + a1[4] + 8);
        if ( v30 )
        {
          if ( *(_BYTE *)(v30 + 16) )
          {
            if ( *(_BYTE *)(v30 + 17) )
            {
              ++*(_DWORD *)(v30 + 20);
              if ( !*(_BYTE *)(v30 + 18) )
                btreeLockCarefully(v30, v19, v17, v16);
            }
            if ( *(_BYTE *)(v30 + 16) == 2 )
            {
              v38 = *(_QWORD *)(v30 + 8);
              v7 = sqlite3PagerCommitPhaseTwo(*(_QWORD *)v38, v19, v17, v16);
              if ( v7 )
              {
                sqlite3BtreeLeave(v30);
                goto LABEL_38;
              }
              --*(_DWORD *)(v30 + 28);
              v39 = *(_QWORD *)(v38 + 96);
              *(_BYTE *)(v38 + 36) = 1;
              sqlite3BitvecDestroy(v39);
              *(_QWORD *)(v38 + 96) = 0;
            }
            btreeEndTransaction(v30, v19, v17, v16);
            if ( *(_BYTE *)(v30 + 17) )
            {
              v41 = (*(_DWORD *)(v30 + 20))-- == 1;
              if ( v41 )
                unlockBtreeMutex(v30);
            }
          }
          v7 = 0;
        }
LABEL_38:
        ++v29;
        if ( v7 )
          return v7;
      }
    }
  }
  v22 = -1;
  v23 = -1;
  do
    ++v23;
  while ( *((_BYTE *)v21 + v23) );
  if ( (v23 & 0x3FFFFFFF) == 0 || v5 <= 1 )
    goto LABEL_25;
  v24 = *a1;
  if ( v20 || *(char **)v19 == byte_1800CD000 )
  {
    v68 = 0;
    v66 = 0;
    goto LABEL_21;
  }
  v16 = *(const char **)(v19 + 216);
  v68 = 0;
  v66 = 0;
  if ( v16 )
  {
    do
LABEL_21:
      ++v22;
    while ( v16[v22] );
    v25 = v22 & 0x3FFFFFFF;
    goto LABEL_23;
  }
  v25 = 0;
LABEL_23:
  v26 = sqlite3MPrintf(a1, "%.4c%s%.16c", 0, v16, 0);
  if ( !v26 )
    return 7;
  v42 = 0;
  v43 = v26;
  v44 = 0;
  v45 = (const char *)(v26 + 4);
  while ( 1 )
  {
    LODWORD(v67) = 0;
    if ( !v44 )
      goto LABEL_74;
    if ( v44 > 100 )
      break;
    if ( v44 == 1 )
      sqlite3_log(13, "MJ collide: %s", v45);
LABEL_74:
    sqlite3_randomness(4, &v67);
    sqlite3_snprintf(13, &v45[v25], "-mj%06X9%02X", (unsigned int)v67 >> 8, (unsigned __int8)v67);
    v7 = (*(__int64 (__fastcall **)(__int64, const char *, _QWORD, int *))(v24 + 56))(v24, v45, 0, &v66);
    if ( v7 )
      goto LABEL_90;
    if ( !v66 )
      goto LABEL_79;
    ++v44;
  }
  sqlite3_log(13, "MJ delete: %s", v45);
  v46 = *(void (__fastcall **)(__int64, const char *, _QWORD))(v24 + 48);
  if ( v46 )
    v46(v24, v45, 0);
LABEL_79:
  v7 = sqlite3OsOpenMalloc(v24, (_DWORD)v45, (unsigned int)&v68, 16406, 0);
  if ( v7 )
  {
LABEL_90:
    sqlite3DbFree(a1, v43);
    return v7;
  }
  v49 = v68;
  for ( i = 0; i < *((_DWORD *)a1 + 10); ++i )
  {
    if ( (unsigned int)sqlite3BtreeTxnState(*(_QWORD *)(32LL * i + a1[4] + 8), v47, v48) == 2 )
    {
      v54 = *(_QWORD *)(**(_QWORD **)(v53 + 8) + 224LL);
      v67 = v54;
      if ( v54 )
      {
        v55 = sqlite3Strlen30(v54);
        v7 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(v56 + 24))(
               v49,
               v57,
               (unsigned int)(v55 + 1),
               v42);
        v58 = sqlite3Strlen30(v67);
        if ( v7 )
          goto LABEL_127;
        v42 += v58 + 1;
      }
    }
  }
  if ( (sqlite3OsDeviceCharacteristics(v49) & 0x400) == 0 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 40LL))(v49, 2);
    if ( v7 )
    {
LABEL_127:
      sqlite3OsClose(v49);
      sqlite3_free(v49);
      sqlite3OsDelete(v24, v45, 0);
      goto LABEL_90;
    }
  }
  v51 = 0;
  while ( v51 < *((_DWORD *)a1 + 10) )
  {
    v52 = *(_QWORD *)(32LL * v51 + a1[4] + 8);
    if ( v52 )
      v7 = sqlite3BtreeCommitPhaseOne(v52, v45);
    ++v51;
    if ( v7 )
    {
      sqlite3OsClose(v49);
      sqlite3_free(v49);
      goto LABEL_90;
    }
  }
  sqlite3OsClose(v49);
  sqlite3_free(v49);
  v62 = *(__int64 (__fastcall **)(__int64, const char *, __int64))(v24 + 48);
  if ( !v62 )
  {
    sqlite3DbFree(a1, v43);
    goto LABEL_115;
  }
  v63 = v62(v24, v45, 1);
  sqlite3DbFree(a1, v43);
  if ( !v63 )
  {
LABEL_115:
    v7 = 0;
    if ( qword_1800D0DA0 )
      qword_1800D0DA0();
    for ( j = 0; j < *((_DWORD *)a1 + 10); ++j )
    {
      v65 = *(_QWORD *)(32LL * j + a1[4] + 8);
      if ( v65 )
        sqlite3BtreeCommitPhaseTwo(v65, 1);
    }
    if ( qword_1800D0DA8 )
      qword_1800D0DA8();
    callFinaliser(a1, 128);
    return v7;
  }
  return v63;
}

```

## disassembly

```asm
0x180040640  push    rbx
0x180040642  push    rbp
0x180040643  push    rsi
0x180040644  push    rdi
0x180040645  push    r13
0x180040647  push    r14
0x180040649  push    r15
0x18004064b  sub     rsp, 40h
0x18004064f  mov     rbx, [rcx+248h]
0x180040656  xor     r11d, r11d
0x180040659  mov     r13d, r11d
0x18004065c  mov     [rcx+248h], r11
0x180040663  mov     r14d, r11d
0x180040666  mov     [rsp+78h+arg_8], r12
0x18004066e  mov     esi, r11d
0x180040671  mov     ebp, r11d
0x180040674  mov     r15, rdx
0x180040677  mov     rdi, rcx
0x18004067a  cmp     ebp, [rdi+224h]
0x180040680  jl      short loc_1800406AC
0x180040682  mov     [rdi+248h], rbx
0x180040689  xor     ebx, ebx
0x18004068b  test    esi, esi
0x18004068d  jz      loc_180040DA3
0x180040693  mov     eax, esi
0x180040695  mov     r12, [rsp+78h+arg_8]
0x18004069d  add     rsp, 40h
0x1800406a1  pop     r15
0x1800406a3  pop     r14
0x1800406a5  pop     r13
0x1800406a7  pop     rdi
0x1800406a8  pop     rsi
0x1800406a9  pop     rbp
0x1800406aa  pop     rbx
0x1800406ab  retn
0x1800406ac  movsxd  rax, ebp
0x1800406af  mov     rcx, [rbx+rax*8]
0x1800406b3  mov     r12, [rcx+10h]
0x1800406b7  test    r12, r12
0x1800406ba  jz      short loc_1800406DE
0x1800406bc  mov     rax, [r12]
0x1800406c0  mov     rax, [rax+78h]
0x1800406c4  test    rax, rax
0x1800406c7  jz      short loc_1800406DE
0x1800406c9  mov     rcx, r12
0x1800406cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800406d1  mov     rdx, r12
0x1800406d4  mov     rcx, r15
0x1800406d7  mov     esi, eax
0x1800406d9  call    sqlite3VtabImportErrmsg
0x1800406de  inc     ebp
0x1800406e0  test    esi, esi
0x1800406e2  jz      short loc_18004067A
0x1800406e4  jmp     short loc_180040682
0x1800406e6  test    r14d, r14d
0x1800406e9  jnz     loc_18004096D
0x1800406ef  mov     rax, [rdi+20h]
0x1800406f3  lea     r9, dword_1800B56B4
0x1800406fa  lea     r8, byte_1800CD000
0x180040701  mov     rcx, [rax+8]
0x180040705  mov     rax, [rcx+8]
0x180040709  mov     rdx, [rax]
0x18004070c  movzx   r10d, byte ptr [rdx+13h]
0x180040711  test    r10b, r10b
0x180040714  jnz     loc_180040DAF
0x18004071a  cmp     [rdx], r8
0x18004071d  jz      loc_180040DAF
0x180040723  mov     rcx, [rdx+0D8h]
0x18004072a  test    rcx, rcx
0x18004072d  jz      loc_1800407CD
0x180040733  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18004073a  mov     rax, rbx
0x18004073d  nop     dword ptr [rax]
0x180040740  inc     rax
0x180040743  cmp     byte ptr [rcx+rax], 0
0x180040747  jnz     short loc_180040740
0x180040749  and     eax, 3FFFFFFFh
0x18004074e  jz      short loc_1800407CD
0x180040750  cmp     r13d, 1
0x180040754  jle     short loc_1800407CD
0x180040756  mov     r14, [rdi]
0x180040759  test    r10b, r10b
0x18004075c  jnz     loc_180040DB7
0x180040762  cmp     [rdx], r8
0x180040765  jz      loc_180040DB7
0x18004076b  mov     r9, [rdx+0D8h]
0x180040772  xor     r11d, r11d
0x180040775  mov     [rsp+78h+arg_18], r11
0x18004077d  mov     [rsp+78h+arg_0], r11d
0x180040785  test    r9, r9
0x180040788  jz      loc_180040965
0x18004078e  xchg    ax, ax
0x180040790  inc     rbx
0x180040793  cmp     byte ptr [r9+rbx], 0
0x180040798  jnz     short loc_180040790
0x18004079a  and     ebx, 3FFFFFFFh
0x1800407a0  xor     r8d, r8d
0x1800407a3  mov     [rsp+78h+var_58], r11
0x1800407a8  lea     rdx, a4cS16c; "%.4c%s%.16c"
0x1800407af  mov     rcx, rdi
0x1800407b2  call    sqlite3MPrintf
0x1800407b7  mov     rbp, rax
0x1800407ba  test    rax, rax
0x1800407bd  jnz     loc_180040A21
0x1800407c3  mov     eax, 7
0x1800407c8  jmp     loc_180040695
0x1800407cd  xor     r11d, r11d
0x1800407d0  mov     ebx, r11d
0x1800407d3  test    esi, esi
0x1800407d5  jnz     short loc_180040800
0x1800407d7  cmp     ebx, [rdi+28h]
0x1800407da  jge     short loc_180040800
0x1800407dc  mov     rax, [rdi+20h]
0x1800407e0  movsxd  rcx, ebx
0x1800407e3  shl     rcx, 5
0x1800407e7  mov     rbp, [rcx+rax+8]
0x1800407ec  test    rbp, rbp
0x1800407ef  jz      short loc_1800407FA
0x1800407f1  cmp     byte ptr [rbp+10h], 2
0x1800407f5  mov     esi, r11d
0x1800407f8  jz      short loc_180040866
0x1800407fa  inc     ebx
0x1800407fc  test    esi, esi
0x1800407fe  jz      short loc_1800407D7
0x180040800  mov     ebx, r11d
0x180040803  test    esi, esi
0x180040805  jnz     loc_180040693
0x18004080b  cmp     ebx, [rdi+28h]
0x18004080e  jge     loc_1800408B1
0x180040814  mov     rax, [rdi+20h]
0x180040818  movsxd  rcx, ebx
0x18004081b  shl     rcx, 5
0x18004081f  mov     rbp, [rcx+rax+8]
0x180040824  test    rbp, rbp
0x180040827  jz      short loc_18004085B
0x180040829  cmp     byte ptr [rbp+10h], 0
0x18004082d  jz      short loc_180040858
0x18004082f  cmp     byte ptr [rbp+11h], 0
0x180040833  jnz     loc_1800409D6
0x180040839  cmp     byte ptr [rbp+10h], 2
0x18004083d  jz      loc_180040931
0x180040843  mov     rcx, rbp
0x180040846  call    btreeEndTransaction
0x18004084b  cmp     byte ptr [rbp+11h], 0
0x18004084f  jnz     loc_18004099D
0x180040855  xor     r11d, r11d
0x180040858  mov     esi, r11d
0x18004085b  inc     ebx
0x18004085d  test    esi, esi
0x18004085f  jz      short loc_18004080B
0x180040861  jmp     loc_180040693
0x180040866  cmp     byte ptr [rbp+11h], 0
0x18004086a  mov     r14, [rbp+8]
0x18004086e  jnz     loc_180040A07
0x180040874  cmp     byte ptr [r14+21h], 0
0x180040879  jnz     loc_1800409B4
0x18004087f  cmp     byte ptr [r14+23h], 0
0x180040884  jz      short loc_180040890
0x180040886  mov     rdx, [r14]
0x180040889  mov     eax, [r14+40h]
0x18004088d  mov     [rdx+20h], eax
0x180040890  mov     rcx, [r14]
0x180040893  xor     r8d, r8d
0x180040896  xor     edx, edx
0x180040898  call    sqlite3PagerCommitPhaseOne
0x18004089d  cmp     byte ptr [rbp+11h], 0
0x1800408a1  mov     esi, eax
0x1800408a3  jnz     loc_1800409F0
0x1800408a9  xor     r11d, r11d
0x1800408ac  jmp     loc_1800407FA
0x1800408b1  mov     rbx, [rdi+248h]
0x1800408b8  test    rbx, rbx
0x1800408bb  jz      loc_180040693
0x1800408c1  cmp     dword ptr [rdi+224h], 0
0x1800408c8  mov     ebp, r11d
0x1800408cb  mov     [rdi+248h], r11
0x1800408d2  jle     short loc_180040917
0x1800408d4  movsxd  rax, ebp
0x1800408d7  mov     r14, [rbx+rax*8]
0x1800408db  mov     rcx, [r14+10h]
0x1800408df  test    rcx, rcx
0x1800408e2  jz      short loc_1800408FB
0x1800408e4  mov     rax, [rcx]
0x1800408e7  mov     rax, [rax+80h]
0x1800408ee  test    rax, rax
0x1800408f1  jz      short loc_1800408FB
0x1800408f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800408f8  xor     r11d, r11d
0x1800408fb  mov     rcx, r14
0x1800408fe  mov     [r14+20h], r11d
0x180040902  call    sqlite3VtabUnlock
0x180040907  inc     ebp
0x180040909  mov     r11d, 0
0x18004090f  cmp     ebp, [rdi+224h]
0x180040915  jl      short loc_1800408D4
0x180040917  mov     rdx, rbx
0x18004091a  mov     rcx, rdi
0x18004091d  call    sqlite3DbFree
0x180040922  mov     dword ptr [rdi+224h], 0
0x18004092c  jmp     loc_180040693
0x180040931  mov     r14, [rbp+8]
0x180040935  mov     rcx, [r14]
0x180040938  call    sqlite3PagerCommitPhaseTwo
0x18004093d  mov     esi, eax
0x18004093f  test    eax, eax
0x180040941  jnz     loc_180040C2C
0x180040947  dec     dword ptr [rbp+1Ch]
0x18004094a  mov     rcx, [r14+60h]
0x18004094e  mov     byte ptr [r14+24h], 1
0x180040953  call    sqlite3BitvecDestroy
0x180040958  mov     qword ptr [r14+60h], 0
0x180040960  jmp     loc_180040843
0x180040965  mov     ebx, r11d
0x180040968  jmp     loc_1800407A0
0x18004096d  mov     rax, [rdi+120h]
0x180040974  test    rax, rax
0x180040977  jz      loc_1800406EF
0x18004097d  mov     rcx, [rdi+118h]
0x180040984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040989  mov     esi, eax
0x18004098b  test    eax, eax
0x18004098d  jz      loc_1800406EF
0x180040993  mov     eax, 213h
0x180040998  jmp     loc_180040695
0x18004099d  sub     dword ptr [rbp+14h], 1
0x1800409a1  jnz     loc_180040855
0x1800409a7  mov     rcx, rbp
0x1800409aa  call    unlockBtreeMutex
0x1800409af  jmp     loc_180040855
0x1800409b4  mov     rcx, rbp
0x1800409b7  call    autoVacuumCommit
0x1800409bc  mov     esi, eax
0x1800409be  test    eax, eax
0x1800409c0  jz      loc_18004087F
0x1800409c6  mov     rcx, rbp
0x1800409c9  call    sqlite3BtreeLeave
0x1800409ce  xor     r11d, r11d
0x1800409d1  jmp     loc_1800407FA
0x1800409d6  inc     dword ptr [rbp+14h]
0x1800409d9  cmp     byte ptr [rbp+12h], 0
0x1800409dd  jnz     loc_180040839
0x1800409e3  mov     rcx, rbp
0x1800409e6  call    btreeLockCarefully
0x1800409eb  jmp     loc_180040839
0x1800409f0  sub     dword ptr [rbp+14h], 1
0x1800409f4  jnz     loc_1800408A9
0x1800409fa  mov     rcx, rbp
0x1800409fd  call    unlockBtreeMutex
0x180040a02  jmp     loc_1800408A9
0x180040a07  inc     dword ptr [rbp+14h]
0x180040a0a  cmp     byte ptr [rbp+12h], 0
0x180040a0e  jnz     loc_180040874
0x180040a14  mov     rcx, rbp
0x180040a17  call    btreeLockCarefully
0x180040a1c  jmp     loc_180040874
0x180040a21  xor     r13d, r13d
0x180040a24  mov     r12, rbp
0x180040a27  mov     r15d, r13d
0x180040a2a  add     rbp, 4
0x180040a2e  mov     dword ptr [rsp+78h+arg_10], r13d
0x180040a36  test    r15d, r15d
0x180040a39  jz      short loc_180040A5F
0x180040a3b  cmp     r15d, 64h ; 'd'
0x180040a3f  jg      loc_180040AD1
0x180040a45  cmp     r15d, 1
0x180040a49  jnz     short loc_180040A5F
0x180040a4b  mov     r8, rbp
0x180040a4e  lea     rdx, aMjCollideS; "MJ collide: %s"
0x180040a55  mov     ecx, 0Dh
0x180040a5a  call    sqlite3_log
0x180040a5f  lea     rdx, [rsp+78h+arg_10]
0x180040a67  mov     ecx, 4
0x180040a6c  call    sqlite3_randomness
0x180040a71  mov     r9d, dword ptr [rsp+78h+arg_10]
0x180040a79  lea     r8, aMj06x902x; "-mj%06X9%02X"
0x180040a80  movzx   eax, r9b
0x180040a84  mov     ecx, 0Dh
0x180040a89  mov     edx, ebx
0x180040a8b  shr     r9d, 8
0x180040a8f  add     rdx, rbp
0x180040a92  mov     dword ptr [rsp+78h+var_58], eax
0x180040a96  call    sqlite3_snprintf
0x180040a9b  mov     rax, [r14+38h]
0x180040a9f  lea     r9, [rsp+78h+arg_0]
0x180040aa7  xor     r8d, r8d
0x180040aaa  mov     rdx, rbp
0x180040aad  mov     rcx, r14
0x180040ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040ab5  mov     esi, eax
0x180040ab7  test    eax, eax
0x180040ab9  jnz     loc_180040BA2
0x180040abf  cmp     [rsp+78h+arg_0], r13d
0x180040ac7  jz      short loc_180040AFA
0x180040ac9  inc     r15d
0x180040acc  jmp     loc_180040A2E
0x180040ad1  mov     r8, rbp
0x180040ad4  lea     rdx, aMjDeleteS; "MJ delete: %s"
0x180040adb  mov     ecx, 0Dh
0x180040ae0  call    sqlite3_log
0x180040ae5  mov     rax, [r14+30h]
  ... truncated ...
```
