# vdbeCommit

- ea: `0x180024f90`
- end: `0x1800256be`
- name: `vdbeCommit`
- size: `1838`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180028df4`

## callees

- `0x180005810`
- `0x18000a9e0`
- `0x18000aac0`
- `0x18000b0ac`
- `0x1800238e0`
- `0x180023ab0`
- `0x180023ad4`
- `0x180023b30`
- `0x180023b48`
- `0x180024440`
- `0x180024b1c`
- `0x180024e18`
- `0x180024f90`
- `0x1800256c4`
- `0x1800257ac`
- `0x1800275f0`
- `0x1800479a4`
- `0x1800494ec`
- `0x180049524`
- `0x180063a1c`
- `0x180066070`
- `0x180067830`
- `0x180067b40`
- `0x1800683d8`
- `0x1800683ec`
- `0x18006a758`
- `0x180085ba0`
- `0x180085d20`
- `0x180089f40`
- `0x180089fec`
- `0x180092ea0`
- `0x18009a010`

## string_xrefs

- `0x1800254bf`: `MJ delete: %s`

## pseudocode

```c
__int64 __fastcall vdbeCommit(__int64 *a1, __int64 a2)
{
  __int64 v2; // rbx
  int v3; // r13d
  int v4; // r14d
  unsigned int v5; // esi
  int v6; // ebp
  int v9; // ebx
  const char *v11; // r9
  __int64 *v12; // rax
  __int64 v13; // r8
  __int64 v14; // rdx
  int *v15; // rcx
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // r14
  int v19; // ebx
  __int64 v20; // rax
  int v21; // ebx
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rbp
  int v25; // ebp
  __int64 v26; // rbx
  _QWORD *v27; // r14
  __int64 v28; // r14
  __int64 v29; // rcx
  __int64 (__fastcall *v30)(__int64); // rax
  __int64 v31; // rbx
  bool v32; // cc
  int v33; // ebp
  __int64 v34; // r14
  __int64 v35; // rcx
  void (__fastcall *v36)(__int64, __int64, __int64, const char *); // rax
  __int64 v37; // rax
  __int64 v38; // rbp
  __int64 v39; // r15
  __int64 v40; // rcx
  int j; // ebx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // r12
  __int64 (__fastcall *v45)(_QWORD); // rax
  int v46; // r15d
  __int64 v47; // r12
  const char *v48; // rbp
  __int64 v49; // r8
  __int64 v50; // rbx
  __int64 v51; // rdx
  int i; // r15d
  __int64 v53; // rcx
  __int64 v54; // rax
  __int64 v55; // r13
  int v56; // eax
  __int64 v57; // rdx
  int v58; // eax
  int v59; // r15d
  __int64 v60; // rcx
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // r8
  __int64 v64; // r9
  int v66; // [rsp+70h] [rbp+8h] BYREF
  __int64 v67; // [rsp+80h] [rbp+18h] BYREF
  __int64 v68; // [rsp+88h] [rbp+20h] BYREF

  v2 = a1[73];
  v3 = 0;
  a1[73] = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  do
  {
    if ( v6 >= *((_DWORD *)a1 + 137) )
      break;
    v43 = *(_QWORD *)(v2 + 8LL * v6);
    v44 = *(_QWORD *)(v43 + 16);
    if ( v44 )
    {
      v45 = *(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v44 + 120LL);
      if ( v45 )
      {
        v5 = v45(*(_QWORD *)(v43 + 16));
        sqlite3VtabImportErrmsg(a2, v44);
      }
    }
    ++v6;
  }
  while ( !v5 );
  a1[73] = v2;
  v9 = 0;
  if ( v5 )
    return v5;
  while ( v9 < *((_DWORD *)a1 + 10) )
  {
    v37 = a1[4];
    v38 = 32LL * v9;
    v39 = *(_QWORD *)(v37 + v38 + 8);
    if ( v39 && *(_BYTE *)(v39 + 16) == 2 )
    {
      v4 = 1;
      sqlite3BtreeEnter(*(_QWORD *)(v37 + v38 + 8));
      v40 = **(_QWORD **)(v39 + 8);
      if ( *(_BYTE *)(a1[4] + v38 + 16) != 1
        && *((_BYTE *)&qword_1800A7470 + *(unsigned __int8 *)(v40 + 9))
        && !(unsigned int)sqlite3PagerIsMemdb() )
      {
        ++v3;
      }
      v5 = sqlite3PagerExclusiveLock(v40);
      sqlite3BtreeLeave(v39);
    }
    ++v9;
    if ( v5 )
      return v5;
  }
  if ( v4 )
  {
    v30 = (__int64 (__fastcall *)(__int64))a1[36];
    if ( v30 )
    {
      v5 = v30(a1[35]);
      if ( v5 )
        return 531;
    }
  }
  v11 = (const char *)&dword_18009E87C;
  v12 = *(__int64 **)(*(_QWORD *)(a1[4] + 8) + 8LL);
  v13 = *v12;
  v14 = *(unsigned __int8 *)(*v12 + 19);
  if ( (_BYTE)v14 || *(char **)v13 == byte_1800B2000 )
  {
    v15 = &dword_18009E87C;
  }
  else
  {
    v15 = *(int **)(v13 + 216);
    if ( !v15 )
    {
LABEL_18:
      v21 = 0;
      do
      {
        if ( v21 >= *((_DWORD *)a1 + 10) )
          break;
        v22 = a1[4];
        v23 = 32LL * v21;
        v24 = *(_QWORD *)(v23 + v22 + 8);
        if ( v24 )
        {
          v5 = 0;
          if ( *(_BYTE *)(v24 + 16) == 2 )
          {
            v27 = *(_QWORD **)(v24 + 8);
            sqlite3BtreeEnter(*(_QWORD *)(v23 + v22 + 8));
            if ( !*((_BYTE *)v27 + 33) || (v5 = autoVacuumCommit(v24)) == 0 )
            {
              if ( *((_BYTE *)v27 + 35) )
                *(_DWORD *)(*v27 + 32LL) = *((_DWORD *)v27 + 16);
              v5 = sqlite3PagerCommitPhaseOne(*v27, 0, 0);
            }
            sqlite3BtreeLeave(v24);
          }
        }
        ++v21;
      }
      while ( !v5 );
      v25 = 0;
      if ( v5 )
        return v5;
      while ( 1 )
      {
        if ( v25 >= *((_DWORD *)a1 + 10) )
        {
          v31 = a1[73];
          if ( v31 )
          {
            v32 = *((_DWORD *)a1 + 137) <= 0;
            v33 = 0;
            a1[73] = 0;
            if ( !v32 )
            {
              do
              {
                v34 = *(_QWORD *)(v31 + 8LL * v33);
                v35 = *(_QWORD *)(v34 + 16);
                if ( v35 )
                {
                  v36 = *(void (__fastcall **)(__int64, __int64, __int64, const char *))(*(_QWORD *)v35 + 128LL);
                  if ( v36 )
                    v36(v35, v14, v13, v11);
                }
                *(_DWORD *)(v34 + 32) = 0;
                sqlite3VtabUnlock(v34);
                ++v33;
              }
              while ( v33 < *((_DWORD *)a1 + 137) );
            }
            sqlite3DbFree(a1, v31);
            *((_DWORD *)a1 + 137) = 0;
          }
          return v5;
        }
        v26 = *(_QWORD *)(32LL * v25 + a1[4] + 8);
        if ( v26 )
        {
          if ( *(_BYTE *)(v26 + 16) )
          {
            if ( *(_BYTE *)(v26 + 17) )
            {
              ++*(_DWORD *)(v26 + 20);
              if ( !*(_BYTE *)(v26 + 18) )
                btreeLockCarefully(v26, v14, v13, v11);
            }
            if ( *(_BYTE *)(v26 + 16) == 2 )
            {
              v28 = *(_QWORD *)(v26 + 8);
              v5 = sqlite3PagerCommitPhaseTwo(*(_QWORD *)v28, v14, v13, v11);
              if ( v5 )
              {
                sqlite3BtreeLeave(v26);
                goto LABEL_30;
              }
              --*(_DWORD *)(v26 + 28);
              v29 = *(_QWORD *)(v28 + 96);
              *(_BYTE *)(v28 + 36) = 1;
              sqlite3BitvecDestroy(v29);
              *(_QWORD *)(v28 + 96) = 0;
            }
            btreeEndTransaction(v26, v14, v13, v11);
            if ( *(_BYTE *)(v26 + 17) )
            {
              if ( (*(_DWORD *)(v26 + 20))-- == 1 )
                unlockBtreeMutex(v26);
            }
          }
          v5 = 0;
        }
LABEL_30:
        ++v25;
        if ( v5 )
          return v5;
      }
    }
  }
  v16 = -1;
  v17 = -1;
  do
    ++v17;
  while ( *((_BYTE *)v15 + v17) );
  if ( (v17 & 0x3FFFFFFF) == 0 || v3 <= 1 )
    goto LABEL_18;
  v18 = *a1;
  if ( (_BYTE)v14 || *(char **)v13 == byte_1800B2000 )
  {
    v68 = 0;
    v66 = 0;
    do
LABEL_14:
      ++v16;
    while ( v11[v16] );
    v19 = v16 & 0x3FFFFFFF;
    goto LABEL_16;
  }
  v11 = *(const char **)(v13 + 216);
  v68 = 0;
  v66 = 0;
  if ( v11 )
    goto LABEL_14;
  v19 = 0;
LABEL_16:
  v20 = sqlite3MPrintf(a1, "%.4c%s%.16c", 0, v11, 0);
  if ( v20 )
  {
    v46 = 0;
    v47 = v20;
    v48 = (const char *)(v20 + 4);
    while ( 1 )
    {
      LODWORD(v67) = 0;
      if ( v46 )
      {
        if ( v46 > 100 )
        {
          sqlite3_log(13, "MJ delete: %s", v48);
          sqlite3OsDelete(v18, v48, 0);
LABEL_92:
          v5 = sqlite3OsOpenMalloc(v18, (_DWORD)v48, (unsigned int)&v68, 16406, 0);
          if ( !v5 )
          {
            v50 = v68;
            v51 = 0;
            v67 = 0;
            for ( i = 0; i < *((_DWORD *)a1 + 10); ++i )
            {
              if ( (unsigned int)sqlite3BtreeTxnState(*(_QWORD *)(32LL * i + a1[4] + 8), v51, v49) == 2 )
              {
                v54 = *(_QWORD *)(v53 + 8);
                v55 = *(_QWORD *)(*(_QWORD *)v54 + 224LL);
                if ( v55 )
                {
                  v56 = sqlite3Strlen30(*(_QWORD *)(*(_QWORD *)v54 + 224LL));
                  v5 = sqlite3OsWrite(v50, v55, (unsigned int)(v56 + 1), v57);
                  v58 = sqlite3Strlen30(v55);
                  if ( v5 )
                    goto LABEL_100;
                  v51 = v58 + 1 + v67;
                  v67 = v51;
                }
              }
            }
            if ( (sqlite3OsDeviceCharacteristics(v50) & 0x400) == 0 && (v5 = sqlite3OsSync(v50, 2)) != 0 )
            {
LABEL_100:
              sqlite3OsClose(v50);
              sqlite3_free(v50);
              sqlite3OsDelete(v18, v48, 0);
            }
            else
            {
              v59 = 0;
              do
              {
                if ( v59 >= *((_DWORD *)a1 + 10) )
                  break;
                v60 = *(_QWORD *)(32LL * v59 + a1[4] + 8);
                if ( v60 )
                  v5 = sqlite3BtreeCommitPhaseOne(v60, v48);
                ++v59;
              }
              while ( !v5 );
              sqlite3OsClose(v50);
              sqlite3_free(v50);
              if ( !v5 )
              {
                v5 = sqlite3OsDelete(v18, v48, 1);
                sqlite3DbFree(a1, v47);
                if ( !v5 )
                {
                  if ( qword_1800B5AF8 )
                    qword_1800B5AF8(v62, v61, v63, v64);
                  for ( j = 0; j < *((_DWORD *)a1 + 10); ++j )
                  {
                    v42 = *(_QWORD *)(32LL * j + a1[4] + 8);
                    if ( v42 )
                      sqlite3BtreeCommitPhaseTwo(v42, 1);
                  }
                  if ( qword_1800B5B00 )
                    qword_1800B5B00();
                  callFinaliser(a1, 128);
                }
                return v5;
              }
            }
          }
LABEL_101:
          sqlite3DbFree(a1, v47);
          return v5;
        }
        if ( v46 == 1 )
          sqlite3_log(13, "MJ collide: %s", v48);
      }
      sqlite3_randomness(4, &v67);
      sqlite3_snprintf(13, &v48[v19], "-mj%06X9%02X", (unsigned int)v67 >> 8, (unsigned __int8)v67);
      v5 = (*(__int64 (__fastcall **)(__int64, const char *, _QWORD, int *))(v18 + 56))(v18, v48, 0, &v66);
      if ( v5 )
        goto LABEL_101;
      if ( !v66 )
        goto LABEL_92;
      ++v46;
    }
  }
  return 7;
}

```

## disassembly

```asm
0x180024f90  push    rbx
0x180024f92  push    rbp
0x180024f93  push    rsi
0x180024f94  push    rdi
0x180024f95  push    r13
0x180024f97  push    r14
0x180024f99  push    r15
0x180024f9b  sub     rsp, 30h
0x180024f9f  mov     rbx, [rcx+248h]
0x180024fa6  xor     r10d, r10d
0x180024fa9  mov     r13d, r10d
0x180024fac  mov     [rcx+248h], r10
0x180024fb3  mov     r14d, r10d
0x180024fb6  mov     [rsp+68h+arg_8], r12
0x180024fbb  mov     esi, r10d
0x180024fbe  mov     ebp, r10d
0x180024fc1  mov     r15, rdx
0x180024fc4  mov     rdi, rcx
0x180024fc7  cmp     ebp, [rdi+224h]
0x180024fcd  jl      loc_1800253B1
0x180024fd3  mov     [rdi+248h], rbx
0x180024fda  xor     ebx, ebx
0x180024fdc  test    esi, esi
0x180024fde  jz      loc_1800253F2
0x180024fe4  mov     eax, esi
0x180024fe6  mov     r12, [rsp+68h+arg_8]
0x180024feb  add     rsp, 30h
0x180024fef  pop     r15
0x180024ff1  pop     r14
0x180024ff3  pop     r13
0x180024ff5  pop     rdi
0x180024ff6  pop     rsi
0x180024ff7  pop     rbp
0x180024ff8  pop     rbx
0x180024ff9  retn
0x180024ffa  test    r14d, r14d
0x180024ffd  jnz     loc_180025214
0x180025003  mov     rax, [rdi+20h]
0x180025007  lea     r9, dword_18009E87C
0x18002500e  lea     r10, byte_1800B2000
0x180025015  mov     rcx, [rax+8]
0x180025019  mov     rax, [rcx+8]
0x18002501d  mov     r8, [rax]
0x180025020  movzx   edx, byte ptr [r8+13h]
0x180025025  test    dl, dl
0x180025027  jz      loc_180025143
0x18002502d  mov     rcx, r9
0x180025030  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180025037  mov     rax, rbx
0x18002503a  nop     word ptr [rax+rax+00h]
0x180025040  inc     rax
0x180025043  cmp     byte ptr [rcx+rax], 0
0x180025047  jnz     short loc_180025040
0x180025049  and     eax, 3FFFFFFFh
0x18002504e  jz      short loc_1800250AE
0x180025050  cmp     r13d, 1
0x180025054  jle     short loc_1800250AE
0x180025056  mov     r14, [rdi]
0x180025059  test    dl, dl
0x18002505b  jz      loc_180025161
0x180025061  xor     r10d, r10d
0x180025064  mov     [rsp+68h+arg_18], r10
0x18002506c  mov     [rsp+68h+arg_0], r10d
0x180025071  inc     rbx
0x180025074  cmp     byte ptr [r9+rbx], 0
0x180025079  jnz     short loc_180025071
0x18002507b  and     ebx, 3FFFFFFFh
0x180025081  xor     r8d, r8d
0x180025084  mov     [rsp+68h+var_48], r10
0x180025089  lea     rdx, a4cS16c; "%.4c%s%.16c"
0x180025090  mov     rcx, rdi
0x180025093  call    sqlite3MPrintf
0x180025098  mov     rbp, rax
0x18002509b  test    rax, rax
0x18002509e  jnz     loc_180025413
0x1800250a4  mov     eax, 7
0x1800250a9  jmp     loc_180024FE6
0x1800250ae  xor     r10d, r10d
0x1800250b1  mov     ebx, r10d
0x1800250b4  test    esi, esi
0x1800250b6  jnz     short loc_1800250DC
0x1800250b8  cmp     ebx, [rdi+28h]
0x1800250bb  jge     short loc_1800250DC
0x1800250bd  mov     rax, [rdi+20h]
0x1800250c1  movsxd  rcx, ebx
0x1800250c4  shl     rcx, 5
0x1800250c8  mov     rbp, [rcx+rax+8]
0x1800250cd  test    rbp, rbp
0x1800250d0  jnz     loc_180025192
0x1800250d6  inc     ebx
0x1800250d8  test    esi, esi
0x1800250da  jz      short loc_1800250B8
0x1800250dc  mov     ebp, r10d
0x1800250df  test    esi, esi
0x1800250e1  jnz     loc_180024FE4
0x1800250e7  cmp     ebp, [rdi+28h]
0x1800250ea  jge     loc_18002525B
0x1800250f0  mov     rax, [rdi+20h]
0x1800250f4  movsxd  rcx, ebp
0x1800250f7  shl     rcx, 5
0x1800250fb  mov     rbx, [rcx+rax+8]
0x180025100  test    rbx, rbx
0x180025103  jz      short loc_180025137
0x180025105  cmp     byte ptr [rbx+10h], 0
0x180025109  jz      short loc_180025134
0x18002510b  cmp     byte ptr [rbx+11h], 0
0x18002510f  jnz     loc_18002567D
0x180025115  cmp     byte ptr [rbx+10h], 2
0x180025119  jz      loc_1800251E0
0x18002511f  mov     rcx, rbx
0x180025122  call    btreeEndTransaction
0x180025127  cmp     byte ptr [rbx+11h], 0
0x18002512b  jnz     loc_1800256A7
0x180025131  xor     r10d, r10d
0x180025134  mov     esi, r10d
0x180025137  inc     ebp
0x180025139  test    esi, esi
0x18002513b  jnz     loc_180024FE4
0x180025141  jmp     short loc_1800250E7
0x180025143  cmp     [r8], r10
0x180025146  jz      loc_18002502D
0x18002514c  mov     rcx, [r8+0D8h]
0x180025153  test    rcx, rcx
0x180025156  jnz     loc_180025030
0x18002515c  jmp     loc_1800250AE
0x180025161  cmp     [r8], r10
0x180025164  jz      loc_180025061
0x18002516a  mov     r9, [r8+0D8h]
0x180025171  xor     r10d, r10d
0x180025174  mov     [rsp+68h+arg_18], r10
0x18002517c  mov     [rsp+68h+arg_0], r10d
0x180025181  test    r9, r9
0x180025184  jnz     loc_180025071
0x18002518a  mov     ebx, r10d
0x18002518d  jmp     loc_180025081
0x180025192  cmp     byte ptr [rbp+10h], 2
0x180025196  mov     esi, r10d
0x180025199  jnz     loc_1800250D6
0x18002519f  mov     r14, [rbp+8]
0x1800251a3  mov     rcx, rbp
0x1800251a6  call    sqlite3BtreeEnter
0x1800251ab  cmp     byte ptr [r14+21h], 0
0x1800251b0  jnz     loc_180025244
0x1800251b6  cmp     byte ptr [r14+23h], 0
0x1800251bb  jnz     loc_18002566E
0x1800251c1  mov     rcx, [r14]
0x1800251c4  xor     r8d, r8d
0x1800251c7  xor     edx, edx
0x1800251c9  call    sqlite3PagerCommitPhaseOne
0x1800251ce  mov     esi, eax
0x1800251d0  mov     rcx, rbp
0x1800251d3  call    sqlite3BtreeLeave
0x1800251d8  xor     r10d, r10d
0x1800251db  jmp     loc_1800250D6
0x1800251e0  mov     r14, [rbx+8]
0x1800251e4  mov     rcx, [r14]
0x1800251e7  call    sqlite3PagerCommitPhaseTwo
0x1800251ec  mov     esi, eax
0x1800251ee  test    eax, eax
0x1800251f0  jnz     loc_180025697
0x1800251f6  dec     dword ptr [rbx+1Ch]
0x1800251f9  mov     rcx, [r14+60h]
0x1800251fd  mov     byte ptr [r14+24h], 1
0x180025202  call    sqlite3BitvecDestroy
0x180025207  mov     qword ptr [r14+60h], 0
0x18002520f  jmp     loc_18002511F
0x180025214  mov     rax, [rdi+120h]
0x18002521b  test    rax, rax
0x18002521e  jz      loc_180025003
0x180025224  mov     rcx, [rdi+118h]
0x18002522b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025230  mov     esi, eax
0x180025232  test    eax, eax
0x180025234  jz      loc_180025003
0x18002523a  mov     eax, 213h
0x18002523f  jmp     loc_180024FE6
0x180025244  mov     rcx, rbp
0x180025247  call    autoVacuumCommit
0x18002524c  mov     esi, eax
0x18002524e  test    eax, eax
0x180025250  jnz     loc_1800251D0
0x180025256  jmp     loc_1800251B6
0x18002525b  mov     rbx, [rdi+248h]
0x180025262  test    rbx, rbx
0x180025265  jz      loc_180024FE4
0x18002526b  cmp     dword ptr [rdi+224h], 0
0x180025272  mov     ebp, r10d
0x180025275  mov     [rdi+248h], r10
0x18002527c  jle     short loc_1800252C1
0x18002527e  movsxd  rax, ebp
0x180025281  mov     r14, [rbx+rax*8]
0x180025285  mov     rcx, [r14+10h]
0x180025289  test    rcx, rcx
0x18002528c  jz      short loc_1800252A5
0x18002528e  mov     rax, [rcx]
0x180025291  mov     rax, [rax+80h]
0x180025298  test    rax, rax
0x18002529b  jz      short loc_1800252A5
0x18002529d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252a2  xor     r10d, r10d
0x1800252a5  mov     rcx, r14
0x1800252a8  mov     [r14+20h], r10d
0x1800252ac  call    sqlite3VtabUnlock
0x1800252b1  inc     ebp
0x1800252b3  mov     r10d, 0
0x1800252b9  cmp     ebp, [rdi+224h]
0x1800252bf  jl      short loc_18002527E
0x1800252c1  mov     rdx, rbx
0x1800252c4  mov     rcx, rdi
0x1800252c7  call    sqlite3DbFree
0x1800252cc  mov     dword ptr [rdi+224h], 0
0x1800252d6  jmp     loc_180024FE4
0x1800252e0  cmp     ebx, [rdi+28h]
0x1800252e3  jge     loc_180024FFA
0x1800252e9  mov     rax, [rdi+20h]
0x1800252ed  movsxd  rbp, ebx
0x1800252f0  shl     rbp, 5
0x1800252f4  mov     r15, [rax+rbp+8]
0x1800252f9  test    r15, r15
0x1800252fc  jz      short loc_180025305
0x1800252fe  cmp     byte ptr [r15+10h], 2
0x180025303  jz      short loc_180025311
0x180025305  inc     ebx
0x180025307  test    esi, esi
0x180025309  jnz     loc_180024FE4
0x18002530f  jmp     short loc_1800252E0
0x180025311  mov     rcx, r15
0x180025314  mov     r14d, 1
0x18002531a  call    sqlite3BtreeEnter
0x18002531f  mov     rax, [r15+8]
0x180025323  mov     rcx, [rax]
0x180025326  mov     rax, [rdi+20h]
0x18002532a  cmp     [rax+rbp+10h], r14b
0x18002532f  jz      short loc_180025340
0x180025331  movzx   eax, byte ptr [rcx+9]
0x180025335  cmp     byte ptr [rax+r12], 0
0x18002533a  jnz     loc_1800253FE
0x180025340  call    sqlite3PagerExclusiveLock
0x180025345  mov     rcx, r15
0x180025348  mov     esi, eax
0x18002534a  call    sqlite3BtreeLeave
0x18002534f  jmp     short loc_180025305
0x180025351  mov     rax, cs:qword_1800B5AF8
0x180025358  test    rax, rax
0x18002535b  jz      short loc_180025362
0x18002535d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025362  xor     ebx, ebx
0x180025364  cmp     [rdi+28h], ebx
0x180025367  jle     short loc_18002538F
0x180025369  mov     rax, [rdi+20h]
0x18002536d  movsxd  rcx, ebx
0x180025370  shl     rcx, 5
0x180025374  mov     rcx, [rcx+rax+8]
0x180025379  test    rcx, rcx
0x18002537c  jz      short loc_180025388
0x18002537e  mov     edx, 1
0x180025383  call    sqlite3BtreeCommitPhaseTwo
0x180025388  inc     ebx
0x18002538a  cmp     ebx, [rdi+28h]
0x18002538d  jl      short loc_180025369
0x18002538f  mov     rax, cs:qword_1800B5B00
0x180025396  test    rax, rax
0x180025399  jnz     loc_180025664
0x18002539f  mov     edx, 80h
0x1800253a4  mov     rcx, rdi
0x1800253a7  call    callFinaliser
0x1800253ac  jmp     loc_180024FE4
0x1800253b1  movsxd  rax, ebp
0x1800253b4  mov     rcx, [rbx+rax*8]
0x1800253b8  mov     r12, [rcx+10h]
0x1800253bc  test    r12, r12
0x1800253bf  jz      short loc_1800253E3
0x1800253c1  mov     rax, [r12]
0x1800253c5  mov     rax, [rax+78h]
0x1800253c9  test    rax, rax
0x1800253cc  jz      short loc_1800253E3
0x1800253ce  mov     rcx, r12
0x1800253d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253d6  mov     rdx, r12
0x1800253d9  mov     rcx, r15
0x1800253dc  mov     esi, eax
0x1800253de  call    sqlite3VtabImportErrmsg
0x1800253e3  inc     ebp
0x1800253e5  test    esi, esi
0x1800253e7  jz      loc_180024FC7
0x1800253ed  jmp     loc_180024FD3
0x1800253f2  lea     r12, qword_1800A7470
0x1800253f9  jmp     loc_1800252E0
0x1800253fe  call    sqlite3PagerIsMemdb
0x180025403  test    eax, eax
0x180025405  jnz     loc_180025340
0x18002540b  inc     r13d
0x18002540e  jmp     loc_180025340
0x180025413  xor     r15d, r15d
0x180025416  mov     r12, rbp
0x180025419  add     rbp, 4
0x18002541d  mov     dword ptr [rsp+68h+arg_10], 0
0x180025428  test    r15d, r15d
0x18002542b  jz      short loc_180025451
0x18002542d  cmp     r15d, 64h ; 'd'
  ... truncated ...
```
