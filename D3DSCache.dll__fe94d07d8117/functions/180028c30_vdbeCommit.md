# vdbeCommit

- ea: `0x180028c30`
- end: `0x1800290b7`
- name: `vdbeCommit`
- size: `1159`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800286a0`

## callees

- `0x18001fbd8`
- `0x180020410`
- `0x180028c30`
- `0x18002b81c`
- `0x1800363c8`
- `0x180036770`
- `0x180038c94`
- `0x180038fd0`
- `0x18003af40`
- `0x18003c8d4`
- `0x18003f650`
- `0x1800421fc`
- `0x180042bb0`
- `0x1800572fc`
- `0x1800799e0`
- `0x180079a58`
- `0x180086ad4`
- `0x180086b5c`
- `0x180086b70`
- `0x180086be8`
- `0x180086c5c`
- `0x18008738c`
- `0x1800873b4`
- `0x18008fed8`
- `0x180096b00`
- `0x1800a8010`

## string_xrefs

- `0x180028e7e`: `MJ delete: %s`

## pseudocode

```c
__int64 __fastcall vdbeCommit(__int64 *a1, __int64 a2)
{
  __int64 v2; // r12
  unsigned int v3; // ebx
  int v4; // r15d
  int v5; // r13d
  int v7; // esi
  __int64 v9; // rcx
  __int64 v10; // r14
  __int64 (__fastcall *v11)(_QWORD); // rax
  int i; // esi
  __int64 v13; // rbp
  __int64 v14; // r14
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 (__fastcall *v17)(__int64); // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r13
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r14
  const char *v29; // rcx
  __int64 v30; // rax
  __int64 v31; // r15
  int v32; // ebp
  const char *v33; // rsi
  __int64 v34; // rbp
  int k; // r14d
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // rax
  int v40; // eax
  __int64 v41; // rdx
  __int64 v42; // rdx
  __int64 v43; // r8
  int v44; // eax
  int m; // r14d
  __int64 v46; // rcx
  int n; // esi
  __int64 v48; // rcx
  int j; // esi
  __int64 v50; // rcx
  int v51; // esi
  __int64 v52; // rcx
  __int64 v53; // [rsp+70h] [rbp+8h] BYREF
  int v54; // [rsp+80h] [rbp+18h] BYREF
  __int64 v55; // [rsp+88h] [rbp+20h] BYREF

  v2 = a1[73];
  v3 = 0;
  v4 = 0;
  a1[73] = 0;
  v5 = 0;
  v7 = 0;
  do
  {
    if ( v7 >= *((_DWORD *)a1 + 137) )
      break;
    v9 = *(_QWORD *)(v2 + 8LL * v7);
    v10 = *(_QWORD *)(v9 + 16);
    if ( v10 )
    {
      v11 = *(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v10 + 120LL);
      if ( v11 )
      {
        v3 = v11(*(_QWORD *)(v9 + 16));
        sqlite3VtabImportErrmsg(a2, v10);
      }
    }
    ++v7;
  }
  while ( !v3 );
  a1[73] = v2;
  LODWORD(v2) = 0;
  for ( i = 0; ; ++i )
  {
    if ( v3 )
      return v3;
    if ( i >= *((_DWORD *)a1 + 10) )
      break;
    v13 = 32LL * i;
    v14 = *(_QWORD *)(a1[4] + v13 + 8);
    if ( (unsigned int)sqlite3BtreeTxnState(v14) == 2 )
    {
      v5 = 1;
      sqlite3BtreeEnter(v15);
      v16 = **(_QWORD **)(v14 + 8);
      if ( *(_BYTE *)(a1[4] + v13 + 16) != 1
        && *((_BYTE *)&qword_1800B7140 + *(unsigned __int8 *)(v16 + 9))
        && !(unsigned int)sqlite3PagerIsMemdb() )
      {
        ++v4;
      }
      v3 = sqlite3PagerExclusiveLock(v16);
      sqlite3BtreeLeave(v14);
    }
  }
  if ( v5 )
  {
    v17 = (__int64 (__fastcall *)(__int64))a1[36];
    if ( v17 )
    {
      v3 = v17(a1[35]);
      if ( v3 )
        return 531;
    }
  }
  v19 = sqlite3PagerFilename(**(_QWORD **)(*(_QWORD *)(a1[4] + 8) + 8LL), 1);
  if ( !(unsigned int)sqlite3Strlen30(v19, v20, v21) || v4 <= (int)v22 )
  {
    for ( j = 0; !v3 && j < *((_DWORD *)a1 + 10); ++j )
    {
      v50 = *(_QWORD *)(32LL * j + a1[4] + 8);
      if ( v50 )
        v3 = sqlite3BtreeCommitPhaseOne(v50, 0);
    }
    v51 = 0;
    while ( !v3 )
    {
      if ( v51 >= *((_DWORD *)a1 + 10) )
        goto LABEL_60;
      v52 = *(_QWORD *)(32LL * v51 + a1[4] + 8);
      if ( v52 )
        v3 = sqlite3BtreeCommitPhaseTwo(v52, 0);
      ++v51;
    }
    return v3;
  }
  v24 = *a1;
  v25 = sqlite3PagerFilename(v23, v22);
  v55 = 0;
  v54 = 0;
  v28 = (int)sqlite3Strlen30(v25, v26, v27);
  v30 = sqlite3MPrintf(a1, "%.4c%s%.16c", 0, v29, 0);
  if ( !v30 )
    return 7;
  v31 = v30;
  v32 = 0;
  v33 = (const char *)(v30 + 4);
  while ( 1 )
  {
    LODWORD(v53) = 0;
    if ( !v32 )
      goto LABEL_31;
    if ( v32 > 100 )
      break;
    if ( v32 == 1 )
      sqlite3_log(13, "MJ collide: %s", v33);
LABEL_31:
    sqlite3_randomness(4, &v53);
    sqlite3_snprintf(13, &v33[v28], "-mj%06X9%02X", (unsigned int)v53 >> 8, (unsigned __int8)v53);
    v3 = (*(__int64 (__fastcall **)(__int64, const char *, _QWORD, int *))(v24 + 56))(v24, v33, 0, &v54);
    if ( v3 )
      goto LABEL_44;
    if ( !v54 )
      goto LABEL_35;
    ++v32;
  }
  sqlite3_log(13, "MJ delete: %s", v33);
  sqlite3OsDelete(v24, v33, 0);
LABEL_35:
  v3 = sqlite3OsOpenMalloc(v24, (_DWORD)v33, (unsigned int)&v55, 16406, 0);
  if ( v3 )
    goto LABEL_44;
  v34 = v55;
  v53 = 0;
  for ( k = 0; k < *((_DWORD *)a1 + 10); ++k )
  {
    if ( (unsigned int)sqlite3BtreeTxnState(*(_QWORD *)(32LL * k + a1[4] + 8)) == 2 )
    {
      v39 = *(_QWORD *)(v37 + 8);
      v2 = *(_QWORD *)(*(_QWORD *)v39 + 224LL);
      if ( v2 )
      {
        v40 = sqlite3Strlen30(*(_QWORD *)(*(_QWORD *)v39 + 224LL), v36, v38);
        v3 = sqlite3OsWrite(v34, v2, (unsigned int)(v40 + 1), v41);
        v44 = sqlite3Strlen30(v2, v42, v43);
        LODWORD(v2) = 0;
        if ( v3 )
          goto LABEL_43;
        v53 += v44 + 1;
      }
    }
  }
  if ( (sqlite3OsDeviceCharacteristics(v34) & 0x400) == 0 )
  {
    v3 = sqlite3OsSync(v34, 2);
    if ( v3 )
    {
LABEL_43:
      sqlite3OsCloseFree(v34);
      sqlite3OsDelete(v24, v33, 0);
      goto LABEL_44;
    }
  }
  for ( m = v2; !v3 && m < *((_DWORD *)a1 + 10); ++m )
  {
    v46 = *(_QWORD *)(32LL * m + a1[4] + 8);
    if ( v46 )
      v3 = sqlite3BtreeCommitPhaseOne(v46, v33);
  }
  sqlite3OsCloseFree(v34);
  if ( v3 )
  {
LABEL_44:
    sqlite3DbFree(a1, v31);
    return v3;
  }
  v3 = sqlite3OsDelete(v24, v33, 1);
  sqlite3DbFree(a1, v31);
  if ( !v3 )
  {
    sqlite3BeginBenignMalloc();
    for ( n = v2; n < *((_DWORD *)a1 + 10); ++n )
    {
      v48 = *(_QWORD *)(32LL * n + a1[4] + 8);
      if ( v48 )
        sqlite3BtreeCommitPhaseTwo(v48, 1);
    }
    sqlite3EndBenignMalloc();
LABEL_60:
    callFinaliser(a1, 128);
  }
  return v3;
}

```

## disassembly

```asm
0x180028c30  mov     [rsp+arg_8], rbx
0x180028c35  push    rbp
0x180028c36  push    rsi
0x180028c37  push    rdi
0x180028c38  push    r12
0x180028c3a  push    r13
0x180028c3c  push    r14
0x180028c3e  push    r15
0x180028c40  sub     rsp, 30h
0x180028c44  mov     r12, [rcx+248h]
0x180028c4b  xor     ebx, ebx
0x180028c4d  xor     r15d, r15d
0x180028c50  mov     [rcx+248h], rbx
0x180028c57  xor     r13d, r13d
0x180028c5a  mov     rbp, rdx
0x180028c5d  xor     esi, esi
0x180028c5f  mov     rdi, rcx
0x180028c62  cmp     esi, [rdi+224h]
0x180028c68  jge     short loc_180028CA1
0x180028c6a  movsxd  rax, esi
0x180028c6d  mov     rcx, [r12+rax*8]
0x180028c71  mov     r14, [rcx+10h]
0x180028c75  test    r14, r14
0x180028c78  jz      short loc_180028C9B
0x180028c7a  mov     rax, [r14]
0x180028c7d  mov     rax, [rax+78h]
0x180028c81  test    rax, rax
0x180028c84  jz      short loc_180028C9B
0x180028c86  mov     rcx, r14
0x180028c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c8e  mov     rdx, r14
0x180028c91  mov     rcx, rbp
0x180028c94  mov     ebx, eax
0x180028c96  call    sqlite3VtabImportErrmsg
0x180028c9b  inc     esi
0x180028c9d  test    ebx, ebx
0x180028c9f  jz      short loc_180028C62
0x180028ca1  mov     [rdi+248h], r12
0x180028ca8  xor     r12d, r12d
0x180028cab  mov     esi, r12d
0x180028cae  jmp     short loc_180028D1B
0x180028cb0  cmp     esi, [rdi+28h]
0x180028cb3  jge     short loc_180028D24
0x180028cb5  mov     rax, [rdi+20h]
0x180028cb9  movsxd  rbp, esi
0x180028cbc  shl     rbp, 5
0x180028cc0  mov     r14, [rax+rbp+8]
0x180028cc5  mov     rcx, r14
0x180028cc8  call    sqlite3BtreeTxnState
0x180028ccd  cmp     eax, 2
0x180028cd0  jnz     short loc_180028D19
0x180028cd2  lea     r13d, [rax-1]
0x180028cd6  call    sqlite3BtreeEnter
0x180028cdb  mov     rax, [r14+8]
0x180028cdf  mov     rcx, [rax]
0x180028ce2  mov     rax, [rdi+20h]
0x180028ce6  cmp     [rax+rbp+10h], r13b
0x180028ceb  jz      short loc_180028D0A
0x180028ced  movzx   eax, byte ptr [rcx+9]
0x180028cf1  lea     rdx, qword_1800B7140
0x180028cf8  cmp     [rax+rdx], r12b
0x180028cfc  jz      short loc_180028D0A
0x180028cfe  call    sqlite3PagerIsMemdb
0x180028d03  test    eax, eax
0x180028d05  jnz     short loc_180028D0A
0x180028d07  inc     r15d
0x180028d0a  call    sqlite3PagerExclusiveLock
0x180028d0f  mov     rcx, r14
0x180028d12  mov     ebx, eax
0x180028d14  call    sqlite3BtreeLeave
0x180028d19  inc     esi
0x180028d1b  test    ebx, ebx
0x180028d1d  jz      short loc_180028CB0
0x180028d1f  jmp     loc_180029042
0x180028d24  test    ebx, ebx
0x180028d26  jnz     loc_180029042
0x180028d2c  test    r13d, r13d
0x180028d2f  jz      short loc_180028D59
0x180028d31  mov     rax, [rdi+120h]
0x180028d38  test    rax, rax
0x180028d3b  jz      short loc_180028D59
0x180028d3d  mov     rcx, [rdi+118h]
0x180028d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d49  mov     ebx, eax
0x180028d4b  test    eax, eax
0x180028d4d  jz      short loc_180028D59
0x180028d4f  mov     eax, 213h
0x180028d54  jmp     loc_180029044
0x180028d59  mov     rax, [rdi+20h]
0x180028d5d  mov     edx, 1
0x180028d62  mov     rcx, [rax+8]
0x180028d66  mov     rax, [rcx+8]
0x180028d6a  mov     r8, [rax]
0x180028d6d  mov     rcx, r8
0x180028d70  call    sqlite3PagerFilename
0x180028d75  mov     rcx, rax
0x180028d78  call    sqlite3Strlen30
0x180028d7d  test    eax, eax
0x180028d7f  jz      loc_180029059
0x180028d85  cmp     r15d, edx
0x180028d88  jle     loc_180029059
0x180028d8e  mov     r13, [rdi]
0x180028d91  mov     rcx, r8
0x180028d94  call    sqlite3PagerFilename
0x180028d99  mov     rcx, rax
0x180028d9c  mov     [rsp+68h+arg_18], r12
0x180028da4  mov     [rsp+68h+arg_10], r12d
0x180028dac  call    sqlite3Strlen30
0x180028db1  mov     r9, rcx
0x180028db4  movsxd  r14, eax
0x180028db7  mov     rcx, rdi
0x180028dba  mov     [rsp+68h+var_48], r12
0x180028dbf  xor     r8d, r8d
0x180028dc2  lea     rdx, a4cS16c; "%.4c%s%.16c"
0x180028dc9  call    sqlite3MPrintf
0x180028dce  mov     rsi, rax
0x180028dd1  test    rax, rax
0x180028dd4  jnz     short loc_180028DDE
0x180028dd6  lea     eax, [rsi+7]
0x180028dd9  jmp     loc_180029044
0x180028dde  mov     r15, rsi
0x180028de1  mov     ebp, r12d
0x180028de4  add     rsi, 4
0x180028de8  mov     dword ptr [rsp+68h+arg_0], r12d
0x180028ded  test    ebp, ebp
0x180028def  jz      short loc_180028E11
0x180028df1  cmp     ebp, 64h ; 'd'
0x180028df4  jg      loc_180028E7B
0x180028dfa  cmp     ebp, 1
0x180028dfd  jnz     short loc_180028E11
0x180028dff  mov     r8, rsi
0x180028e02  lea     rdx, aMjCollideS; "MJ collide: %s"
0x180028e09  lea     ecx, [rbp+0Ch]
0x180028e0c  call    sqlite3_log
0x180028e11  lea     rdx, [rsp+68h+arg_0]
0x180028e16  mov     ecx, 4
0x180028e1b  call    sqlite3_randomness
0x180028e20  mov     r9d, dword ptr [rsp+68h+arg_0]
0x180028e25  lea     rdx, [rsi+r14]
0x180028e29  movzx   eax, r9b
0x180028e2d  lea     r8, aMj06x902x; "-mj%06X9%02X"
0x180028e34  shr     r9d, 8
0x180028e38  mov     ecx, 0Dh
0x180028e3d  mov     dword ptr [rsp+68h+var_48], eax
0x180028e41  call    sqlite3_snprintf
0x180028e46  mov     rax, [r13+38h]
0x180028e4a  lea     r9, [rsp+68h+arg_10]
0x180028e52  xor     r8d, r8d
0x180028e55  mov     rdx, rsi
0x180028e58  mov     rcx, r13
0x180028e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e60  mov     ebx, eax
0x180028e62  test    eax, eax
0x180028e64  jnz     loc_180028F6F
0x180028e6a  cmp     [rsp+68h+arg_10], r12d
0x180028e72  jz      short loc_180028EA5
0x180028e74  inc     ebp
0x180028e76  jmp     loc_180028DE8
0x180028e7b  mov     r8, rsi
0x180028e7e  lea     rdx, aMjDeleteS; "MJ delete: %s"
0x180028e85  mov     ecx, 0Dh
0x180028e8a  call    sqlite3_log
0x180028e8f  xor     r8d, r8d
0x180028e92  mov     rdx, rsi
0x180028e95  mov     rcx, r13
0x180028e98  call    sqlite3OsDelete
0x180028e9d  test    ebx, ebx
0x180028e9f  jnz     loc_180028F6F
0x180028ea5  mov     r9d, 4016h
0x180028eab  mov     [rsp+68h+var_48], r12
0x180028eb0  lea     r8, [rsp+68h+arg_18]
0x180028eb8  mov     rdx, rsi
0x180028ebb  mov     rcx, r13
0x180028ebe  call    sqlite3OsOpenMalloc
0x180028ec3  mov     ebx, eax
0x180028ec5  test    eax, eax
0x180028ec7  jnz     loc_180028F6F
0x180028ecd  mov     rbp, [rsp+68h+arg_18]
0x180028ed5  mov     rdx, r12
0x180028ed8  mov     [rsp+68h+arg_0], rdx
0x180028edd  mov     r14d, r12d
0x180028ee0  cmp     r14d, [rdi+28h]
0x180028ee4  jge     loc_180028F7F
0x180028eea  mov     rax, [rdi+20h]
0x180028eee  movsxd  rcx, r14d
0x180028ef1  shl     rcx, 5
0x180028ef5  mov     rcx, [rcx+rax+8]
0x180028efa  call    sqlite3BtreeTxnState
0x180028eff  cmp     eax, 2
0x180028f02  jnz     short loc_180028F54
0x180028f04  mov     rax, [rcx+8]
0x180028f08  mov     rcx, [rax]
0x180028f0b  mov     r12, [rcx+0E0h]
0x180028f12  test    r12, r12
0x180028f15  jz      short loc_180028F54
0x180028f17  mov     rcx, r12
0x180028f1a  call    sqlite3Strlen30
0x180028f1f  mov     r9, rdx
0x180028f22  mov     rcx, rbp
0x180028f25  mov     rdx, r12
0x180028f28  lea     r8d, [rax+1]
0x180028f2c  call    sqlite3OsWrite
0x180028f31  mov     rcx, r12
0x180028f34  mov     ebx, eax
0x180028f36  call    sqlite3Strlen30
0x180028f3b  xor     r12d, r12d
0x180028f3e  test    ebx, ebx
0x180028f40  jnz     short loc_180028F59
0x180028f42  mov     rdx, [rsp+68h+arg_0]
0x180028f47  inc     eax
0x180028f49  movsxd  rcx, eax
0x180028f4c  add     rdx, rcx
0x180028f4f  mov     [rsp+68h+arg_0], rdx
0x180028f54  inc     r14d
0x180028f57  jmp     short loc_180028EE0
0x180028f59  mov     rcx, rbp
0x180028f5c  call    sqlite3OsCloseFree
0x180028f61  xor     r8d, r8d
0x180028f64  mov     rdx, rsi
0x180028f67  mov     rcx, r13
0x180028f6a  call    sqlite3OsDelete
0x180028f6f  mov     rdx, r15
0x180028f72  mov     rcx, rdi
0x180028f75  call    sqlite3DbFree
0x180028f7a  jmp     loc_180029042
0x180028f7f  mov     rcx, rbp
0x180028f82  call    sqlite3OsDeviceCharacteristics
0x180028f87  bt      eax, 0Ah
0x180028f8b  jb      short loc_180028FA0
0x180028f8d  mov     edx, 2
0x180028f92  mov     rcx, rbp
0x180028f95  call    sqlite3OsSync
0x180028f9a  mov     ebx, eax
0x180028f9c  test    eax, eax
0x180028f9e  jnz     short loc_180028F59
0x180028fa0  mov     r14d, r12d
0x180028fa3  jmp     short loc_180028FCD
0x180028fa5  cmp     r14d, [rdi+28h]
0x180028fa9  jge     short loc_180028FD1
0x180028fab  mov     rax, [rdi+20h]
0x180028faf  movsxd  rcx, r14d
0x180028fb2  shl     rcx, 5
0x180028fb6  mov     rcx, [rcx+rax+8]
0x180028fbb  test    rcx, rcx
0x180028fbe  jz      short loc_180028FCA
0x180028fc0  mov     rdx, rsi
0x180028fc3  call    sqlite3BtreeCommitPhaseOne
0x180028fc8  mov     ebx, eax
0x180028fca  inc     r14d
0x180028fcd  test    ebx, ebx
0x180028fcf  jz      short loc_180028FA5
0x180028fd1  mov     rcx, rbp
0x180028fd4  call    sqlite3OsCloseFree
0x180028fd9  test    ebx, ebx
0x180028fdb  jnz     short loc_180028F6F
0x180028fdd  lea     ebp, [rbx+1]
0x180028fe0  mov     rdx, rsi
0x180028fe3  mov     r8d, ebp
0x180028fe6  mov     rcx, r13
0x180028fe9  call    sqlite3OsDelete
0x180028fee  mov     rdx, r15
0x180028ff1  mov     rcx, rdi
0x180028ff4  mov     ebx, eax
0x180028ff6  call    sqlite3DbFree
0x180028ffb  test    ebx, ebx
0x180028ffd  jnz     short loc_180029042
0x180028fff  call    sqlite3BeginBenignMalloc
0x180029004  mov     esi, r12d
0x180029007  cmp     [rdi+28h], r12d
0x18002900b  jle     short loc_180029030
0x18002900d  mov     rax, [rdi+20h]
0x180029011  movsxd  rcx, esi
0x180029014  shl     rcx, 5
0x180029018  mov     rcx, [rcx+rax+8]
0x18002901d  test    rcx, rcx
0x180029020  jz      short loc_180029029
0x180029022  mov     edx, ebp
0x180029024  call    sqlite3BtreeCommitPhaseTwo
0x180029029  add     esi, ebp
0x18002902b  cmp     esi, [rdi+28h]
0x18002902e  jl      short loc_18002900D
0x180029030  call    sqlite3EndBenignMalloc
0x180029035  mov     edx, 80h
0x18002903a  mov     rcx, rdi
0x18002903d  call    callFinaliser
0x180029042  mov     eax, ebx
0x180029044  mov     rbx, [rsp+68h+arg_8]
0x180029049  add     rsp, 30h
0x18002904d  pop     r15
0x18002904f  pop     r14
0x180029051  pop     r13
0x180029053  pop     r12
0x180029055  pop     rdi
0x180029056  pop     rsi
0x180029057  pop     rbp
0x180029058  retn
0x180029059  mov     esi, r12d
0x18002905c  jmp     short loc_180029083
0x18002905e  cmp     esi, [rdi+28h]
0x180029061  jge     short loc_180029087
  ... truncated ...
```
