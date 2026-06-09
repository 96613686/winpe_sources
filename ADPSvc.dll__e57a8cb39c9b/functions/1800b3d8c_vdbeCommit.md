# vdbeCommit

- ea: `0x1800b3d8c`
- end: `0x1800b4320`
- name: `vdbeCommit`
- size: `1428`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180099c64`

## callees

- `0x18003ae40`
- `0x18003ba1c`
- `0x18005b318`
- `0x18006a9ec`
- `0x18006aa8c`
- `0x1800716fc`
- `0x180080b64`
- `0x180081e0c`
- `0x180081f6c`
- `0x18009e168`
- `0x1800a98a0`
- `0x1800aa3b0`
- `0x1800aaae0`
- `0x1800abbf0`
- `0x1800b2174`
- `0x1800b3d8c`
- `0x1800ca010`

## string_xrefs

- `0x1800b4069`: `MJ delete: %s`

## pseudocode

```c
__int64 __fastcall vdbeCommit(__int64 *a1, __int64 a2)
{
  __int64 v2; // r15
  unsigned int v3; // ebx
  int v4; // r13d
  int v5; // r12d
  int v7; // esi
  __int64 v9; // rcx
  __int64 v10; // r14
  __int64 (__fastcall *v11)(_QWORD); // rax
  int v12; // r14d
  __int64 v13; // rbp
  __int64 v14; // rsi
  __int64 v15; // rcx
  __int64 (__fastcall *v17)(__int64); // rax
  const char *v19; // r9
  __int64 *v20; // rax
  __int64 v21; // rcx
  char v22; // r8
  int *v23; // rdx
  int i; // esi
  __int64 v25; // rax
  __int64 v26; // r14
  __int64 v27; // r13
  int v28; // esi
  __int64 v29; // rsi
  __int64 v30; // rax
  int v31; // r15d
  const char *v32; // rbp
  void (__fastcall *v33)(__int64, const char *, _QWORD); // rax
  __int64 v34; // rdx
  __int64 v35; // rsi
  int v36; // r15d
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // r8
  __int64 v40; // rax
  int k; // r15d
  void (__fastcall *v42)(__int64, const char *, _QWORD); // rax
  __int64 v43; // rcx
  __int64 (__fastcall *v44)(__int64, const char *, __int64); // rax
  int m; // esi
  __int64 v46; // rcx
  __int64 v47; // rcx
  int v48; // esi
  __int64 v49; // rcx
  __int64 j; // [rsp+70h] [rbp+8h] BYREF
  int v51; // [rsp+80h] [rbp+18h] BYREF
  __int64 v52; // [rsp+88h] [rbp+20h] BYREF

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
  v12 = 0;
  a1[73] = v2;
  if ( v3 )
    return v3;
  while ( v12 < *((_DWORD *)a1 + 10) )
  {
    v13 = 32LL * v12;
    v14 = *(_QWORD *)(a1[4] + v13 + 8);
    if ( v14 && *(_BYTE *)(v14 + 16) == 2 )
    {
      v5 = 1;
      if ( *(_BYTE *)(v14 + 17) )
      {
        ++*(_DWORD *)(v14 + 20);
        if ( !*(_BYTE *)(v14 + 18) )
          btreeLockCarefully(v14);
      }
      v15 = **(_QWORD **)(v14 + 8);
      if ( *(_BYTE *)(a1[4] + v13 + 16) != 1
        && *((_BYTE *)&qword_1800FB4C0 + *(unsigned __int8 *)(v15 + 9))
        && !*(_BYTE *)(v15 + 16)
        && !*(_BYTE *)(v15 + 20) )
      {
        ++v4;
      }
      v3 = *(_DWORD *)(v15 + 48);
      if ( !v3 && !*(_QWORD *)(v15 + 328) )
        v3 = pager_wait_on_lock(v15, 4);
      if ( *(_BYTE *)(v14 + 17) )
      {
        if ( (*(_DWORD *)(v14 + 20))-- == 1 )
          unlockBtreeMutex(v14);
      }
    }
    ++v12;
    if ( v3 )
      return v3;
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
  v19 = (const char *)&dword_1800FAEFC;
  v20 = *(__int64 **)(*(_QWORD *)(a1[4] + 8) + 8LL);
  v21 = *v20;
  v22 = *(_BYTE *)(*v20 + 19);
  if ( v22 || *(char **)v21 == byte_18010B000 )
  {
    v23 = &dword_1800FAEFC;
  }
  else
  {
    v23 = *(int **)(v21 + 216);
    if ( !v23 )
    {
LABEL_34:
      for ( i = 0; !v3 && i < *((_DWORD *)a1 + 10); ++i )
      {
        v47 = *(_QWORD *)(32LL * i + a1[4] + 8);
        if ( v47 )
          v3 = sqlite3BtreeCommitPhaseOne(v47, 0);
      }
      v48 = 0;
      while ( !v3 )
      {
        if ( v48 >= *((_DWORD *)a1 + 10) )
          goto LABEL_97;
        v49 = *(_QWORD *)(32LL * v48 + a1[4] + 8);
        if ( v49 )
          v3 = sqlite3BtreeCommitPhaseTwo(v49, 0);
        ++v48;
      }
      return v3;
    }
  }
  v25 = -1;
  do
    ++v25;
  while ( *((_BYTE *)v23 + v25) );
  if ( (v25 & 0x3FFFFFFF) == 0 || v4 <= 1 )
    goto LABEL_34;
  v26 = *a1;
  LODWORD(v27) = 0;
  if ( !v22 && *(char **)v21 != byte_18010B000 )
    v19 = *(const char **)(v21 + 216);
  v52 = 0;
  v51 = 0;
  if ( v19 )
  {
    v29 = -1;
    do
      ++v29;
    while ( v19[v29] );
    v28 = v29 & 0x3FFFFFFF;
  }
  else
  {
    v28 = 0;
  }
  v30 = sqlite3MPrintf(a1, "%.4c%s%.16c", 0, v19, 0);
  if ( !v30 )
    return 7;
  v31 = 0;
  v32 = (const char *)(v30 + 4);
  while ( 1 )
  {
    LODWORD(j) = 0;
    if ( !v31 )
      goto LABEL_55;
    if ( v31 > 100 )
      break;
    if ( v31 == 1 )
      sqlite3_log(13, "MJ collide: %s", v32);
LABEL_55:
    sqlite3_randomness(4, &j);
    sqlite3_snprintf(13, &v32[v28], "-mj%06X9%02X", (unsigned int)j >> 8, (unsigned __int8)j);
    v3 = (*(__int64 (__fastcall **)(__int64, const char *, _QWORD, int *))(v26 + 56))(v26, v32, 0, &v51);
    if ( v3 )
      goto LABEL_78;
    if ( !v51 )
      goto LABEL_60;
    ++v31;
  }
  sqlite3_log(13, "MJ delete: %s", v32);
  v33 = *(void (__fastcall **)(__int64, const char *, _QWORD))(v26 + 48);
  if ( v33 )
    v33(v26, v32, 0);
LABEL_60:
  v3 = sqlite3OsOpenMalloc(v26, (_DWORD)v32, (unsigned int)&v52, 16406, 0);
  if ( v3 )
    goto LABEL_78;
  v34 = 0;
  v35 = v52;
  v36 = 0;
  for ( j = 0; v36 < *((_DWORD *)a1 + 10); ++v36 )
  {
    v37 = *(_QWORD *)(32LL * v36 + a1[4] + 8);
    if ( v37 )
    {
      if ( *(_BYTE *)(v37 + 16) == 2 )
      {
        v38 = *(_QWORD *)(v37 + 8);
        v27 = *(_QWORD *)(*(_QWORD *)v38 + 224LL);
        if ( v27 )
        {
          v39 = -1;
          do
            ++v39;
          while ( *(_BYTE *)(v39 + v27) );
          v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v35 + 24LL))(
                 v35,
                 *(_QWORD *)(*(_QWORD *)v38 + 224LL),
                 ((unsigned int)v39 & 0x3FFFFFFF) + 1,
                 v34);
          v40 = -1;
          do
            ++v40;
          while ( *(_BYTE *)(v40 + v27) );
          LODWORD(v27) = 0;
          if ( v3 )
            goto LABEL_76;
          v34 = (v40 & 0x3FFFFFFF) + j + 1;
          j = v34;
        }
      }
    }
  }
  if ( !*(_QWORD *)v35 || ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 96LL))(v35) & 0x400) == 0 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v35 + 40LL))(v35, 2);
    if ( v3 )
    {
LABEL_76:
      sqlite3OsClose(v35);
      sqlite3_free(v35);
      v42 = *(void (__fastcall **)(__int64, const char *, _QWORD))(v26 + 48);
      if ( v42 )
        v42(v26, v32, 0);
      goto LABEL_78;
    }
  }
  for ( k = v27; !v3 && k < *((_DWORD *)a1 + 10); ++k )
  {
    v43 = *(_QWORD *)(32LL * k + a1[4] + 8);
    if ( v43 )
      v3 = sqlite3BtreeCommitPhaseOne(v43, v32);
  }
  sqlite3OsClose(v35);
  sqlite3_free(v35);
  if ( v3 )
  {
LABEL_78:
    sqlite3DbFreeNN(a1);
    return v3;
  }
  v44 = *(__int64 (__fastcall **)(__int64, const char *, __int64))(v26 + 48);
  if ( v44 )
    v3 = v44(v26, v32, 1);
  else
    v3 = v27;
  sqlite3DbFreeNN(a1);
  if ( !v3 )
  {
    v3 = v27;
    if ( qword_18010F860 )
      qword_18010F860();
    for ( m = v27; m < *((_DWORD *)a1 + 10); ++m )
    {
      v46 = *(_QWORD *)(32LL * m + a1[4] + 8);
      if ( v46 )
        sqlite3BtreeCommitPhaseTwo(v46, 1);
    }
    if ( qword_18010F868 )
      qword_18010F868();
LABEL_97:
    callFinaliser(a1, 128);
  }
  return v3;
}

```

## disassembly

```asm
0x1800b3d8c  mov     [rsp+arg_8], rbx
0x1800b3d91  push    rbp
0x1800b3d92  push    rsi
0x1800b3d93  push    rdi
0x1800b3d94  push    r12
0x1800b3d96  push    r13
0x1800b3d98  push    r14
0x1800b3d9a  push    r15
0x1800b3d9c  sub     rsp, 30h
0x1800b3da0  mov     r15, [rcx+248h]
0x1800b3da7  xor     ebx, ebx
0x1800b3da9  xor     r13d, r13d
0x1800b3dac  mov     [rcx+248h], rbx
0x1800b3db3  xor     r12d, r12d
0x1800b3db6  mov     rbp, rdx
0x1800b3db9  xor     esi, esi
0x1800b3dbb  mov     rdi, rcx
0x1800b3dbe  cmp     esi, [rdi+224h]
0x1800b3dc4  jge     short loc_1800B3DFD
0x1800b3dc6  movsxd  rax, esi
0x1800b3dc9  mov     rcx, [r15+rax*8]
0x1800b3dcd  mov     r14, [rcx+10h]
0x1800b3dd1  test    r14, r14
0x1800b3dd4  jz      short loc_1800B3DF7
0x1800b3dd6  mov     rax, [r14]
0x1800b3dd9  mov     rax, [rax+78h]
0x1800b3ddd  test    rax, rax
0x1800b3de0  jz      short loc_1800B3DF7
0x1800b3de2  mov     rcx, r14
0x1800b3de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3dea  mov     rdx, r14
0x1800b3ded  mov     rcx, rbp
0x1800b3df0  mov     ebx, eax
0x1800b3df2  call    sqlite3VtabImportErrmsg
0x1800b3df7  inc     esi
0x1800b3df9  test    ebx, ebx
0x1800b3dfb  jz      short loc_1800B3DBE
0x1800b3dfd  xor     r14d, r14d
0x1800b3e00  mov     [rdi+248h], r15
0x1800b3e07  test    ebx, ebx
0x1800b3e09  jnz     loc_1800B42B1
0x1800b3e0f  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800b3e13  cmp     r14d, [rdi+28h]
0x1800b3e17  jge     loc_1800B3ECA
0x1800b3e1d  mov     rax, [rdi+20h]
0x1800b3e21  movsxd  rbp, r14d
0x1800b3e24  shl     rbp, 5
0x1800b3e28  mov     rsi, [rax+rbp+8]
0x1800b3e2d  test    rsi, rsi
0x1800b3e30  jz      loc_1800B3EBA
0x1800b3e36  cmp     byte ptr [rsi+10h], 2
0x1800b3e3a  jnz     short loc_1800B3EBA
0x1800b3e3c  cmp     byte ptr [rsi+11h], 0
0x1800b3e40  mov     r12d, 1
0x1800b3e46  jz      short loc_1800B3E59
0x1800b3e48  inc     dword ptr [rsi+14h]
0x1800b3e4b  cmp     byte ptr [rsi+12h], 0
0x1800b3e4f  jnz     short loc_1800B3E59
0x1800b3e51  mov     rcx, rsi
0x1800b3e54  call    btreeLockCarefully
0x1800b3e59  mov     rax, [rsi+8]
0x1800b3e5d  mov     rcx, [rax]
0x1800b3e60  mov     rax, [rdi+20h]
0x1800b3e64  cmp     [rax+rbp+10h], r12b
0x1800b3e69  jz      short loc_1800B3E8B
0x1800b3e6b  movzx   eax, byte ptr [rcx+9]
0x1800b3e6f  lea     rdx, qword_1800FB4C0
0x1800b3e76  cmp     byte ptr [rax+rdx], 0
0x1800b3e7a  jz      short loc_1800B3E8B
0x1800b3e7c  cmp     byte ptr [rcx+10h], 0
0x1800b3e80  jnz     short loc_1800B3E8B
0x1800b3e82  cmp     byte ptr [rcx+14h], 0
0x1800b3e86  jnz     short loc_1800B3E8B
0x1800b3e88  inc     r13d
0x1800b3e8b  mov     ebx, [rcx+30h]
0x1800b3e8e  test    ebx, ebx
0x1800b3e90  jnz     short loc_1800B3EA6
0x1800b3e92  cmp     qword ptr [rcx+148h], 0
0x1800b3e9a  jnz     short loc_1800B3EA6
0x1800b3e9c  lea     edx, [rbx+4]
0x1800b3e9f  call    pager_wait_on_lock
0x1800b3ea4  mov     ebx, eax
0x1800b3ea6  cmp     byte ptr [rsi+11h], 0
0x1800b3eaa  jz      short loc_1800B3EBA
0x1800b3eac  add     [rsi+14h], r15d
0x1800b3eb0  jnz     short loc_1800B3EBA
0x1800b3eb2  mov     rcx, rsi
0x1800b3eb5  call    unlockBtreeMutex
0x1800b3eba  inc     r14d
0x1800b3ebd  test    ebx, ebx
0x1800b3ebf  jz      loc_1800B3E13
0x1800b3ec5  jmp     loc_1800B42B1
0x1800b3eca  test    ebx, ebx
0x1800b3ecc  jnz     loc_1800B42B1
0x1800b3ed2  test    r12d, r12d
0x1800b3ed5  jz      short loc_1800B3EFF
0x1800b3ed7  mov     rax, [rdi+120h]
0x1800b3ede  test    rax, rax
0x1800b3ee1  jz      short loc_1800B3EFF
0x1800b3ee3  mov     rcx, [rdi+118h]
0x1800b3eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3eef  mov     ebx, eax
0x1800b3ef1  test    eax, eax
0x1800b3ef3  jz      short loc_1800B3EFF
0x1800b3ef5  mov     eax, 213h
0x1800b3efa  jmp     loc_1800B42B3
0x1800b3eff  mov     rax, [rdi+20h]
0x1800b3f03  lea     r9, dword_1800FAEFC
0x1800b3f0a  lea     r10, byte_18010B000
0x1800b3f11  mov     rcx, [rax+8]
0x1800b3f15  mov     rax, [rcx+8]
0x1800b3f19  mov     rcx, [rax]
0x1800b3f1c  mov     r8b, [rcx+13h]
0x1800b3f20  test    r8b, r8b
0x1800b3f23  jnz     short loc_1800B3F3D
0x1800b3f25  cmp     [rcx], r10
0x1800b3f28  jz      short loc_1800B3F3D
0x1800b3f2a  mov     rdx, [rcx+0D8h]
0x1800b3f31  test    rdx, rdx
0x1800b3f34  jnz     short loc_1800B3F40
0x1800b3f36  xor     esi, esi
0x1800b3f38  jmp     loc_1800B42ED
0x1800b3f3d  mov     rdx, r9
0x1800b3f40  mov     rax, r15
0x1800b3f43  inc     rax
0x1800b3f46  cmp     byte ptr [rdx+rax], 0
0x1800b3f4a  jnz     short loc_1800B3F43
0x1800b3f4c  and     eax, 3FFFFFFFh
0x1800b3f51  jz      short loc_1800B3F36
0x1800b3f53  cmp     r13d, 1
0x1800b3f57  jle     short loc_1800B3F36
0x1800b3f59  mov     r14, [rdi]
0x1800b3f5c  xor     r13d, r13d
0x1800b3f5f  test    r8b, r8b
0x1800b3f62  jnz     short loc_1800B3F70
0x1800b3f64  cmp     [rcx], r10
0x1800b3f67  jz      short loc_1800B3F70
0x1800b3f69  mov     r9, [rcx+0D8h]
0x1800b3f70  mov     [rsp+68h+arg_18], r13
0x1800b3f78  mov     [rsp+68h+arg_10], r13d
0x1800b3f80  test    r9, r9
0x1800b3f83  jnz     short loc_1800B3F8A
0x1800b3f85  mov     esi, r13d
0x1800b3f88  jmp     short loc_1800B3F9C
0x1800b3f8a  mov     rsi, r15
0x1800b3f8d  inc     rsi
0x1800b3f90  cmp     [r9+rsi], r13b
0x1800b3f94  jnz     short loc_1800B3F8D
0x1800b3f96  and     esi, 3FFFFFFFh
0x1800b3f9c  xor     r8d, r8d
0x1800b3f9f  mov     [rsp+68h+var_48], r13
0x1800b3fa4  lea     rdx, a4cS16c; "%.4c%s%.16c"
0x1800b3fab  mov     rcx, rdi
0x1800b3fae  call    sqlite3MPrintf
0x1800b3fb3  mov     rbp, rax
0x1800b3fb6  test    rax, rax
0x1800b3fb9  jnz     short loc_1800B3FC3
0x1800b3fbb  lea     eax, [rbp+7]
0x1800b3fbe  jmp     loc_1800B42B3
0x1800b3fc3  mov     r12, rbp
0x1800b3fc6  mov     r15d, r13d
0x1800b3fc9  add     rbp, 4
0x1800b3fcd  mov     dword ptr [rsp+68h+arg_0], r13d
0x1800b3fd2  test    r15d, r15d
0x1800b3fd5  jz      short loc_1800B3FFA
0x1800b3fd7  cmp     r15d, 64h ; 'd'
0x1800b3fdb  jg      loc_1800B4066
0x1800b3fe1  cmp     r15d, 1
0x1800b3fe5  jnz     short loc_1800B3FFA
0x1800b3fe7  mov     r8, rbp
0x1800b3fea  lea     rdx, aMjCollideS; "MJ collide: %s"
0x1800b3ff1  lea     ecx, [r15+0Ch]
0x1800b3ff5  call    sqlite3_log
0x1800b3ffa  lea     rdx, [rsp+68h+arg_0]
0x1800b3fff  mov     ecx, 4
0x1800b4004  call    sqlite3_randomness
0x1800b4009  mov     r9d, dword ptr [rsp+68h+arg_0]
0x1800b400e  lea     r8, aMj06x902x; "-mj%06X9%02X"
0x1800b4015  movzx   eax, r9b
0x1800b4019  mov     ecx, 0Dh
0x1800b401e  mov     edx, esi
0x1800b4020  shr     r9d, 8
0x1800b4024  add     rdx, rbp
0x1800b4027  mov     dword ptr [rsp+68h+var_48], eax
0x1800b402b  call    sqlite3_snprintf
0x1800b4030  mov     rax, [r14+38h]
0x1800b4034  lea     r9, [rsp+68h+arg_10]
0x1800b403c  xor     r8d, r8d
0x1800b403f  mov     rdx, rbp
0x1800b4042  mov     rcx, r14
0x1800b4045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b404a  mov     ebx, eax
0x1800b404c  test    eax, eax
0x1800b404e  jnz     loc_1800B41D2
0x1800b4054  cmp     [rsp+68h+arg_10], r13d
0x1800b405c  jz      short loc_1800B4099
0x1800b405e  inc     r15d
0x1800b4061  jmp     loc_1800B3FCD
0x1800b4066  mov     r8, rbp
0x1800b4069  lea     rdx, aMjDeleteS; "MJ delete: %s"
0x1800b4070  mov     ecx, 0Dh
0x1800b4075  call    sqlite3_log
0x1800b407a  mov     rax, [r14+30h]
0x1800b407e  test    rax, rax
0x1800b4081  jz      short loc_1800B4091
0x1800b4083  xor     r8d, r8d
0x1800b4086  mov     rdx, rbp
0x1800b4089  mov     rcx, r14
0x1800b408c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4091  test    ebx, ebx
0x1800b4093  jnz     loc_1800B41D2
0x1800b4099  mov     r9d, 4016h
0x1800b409f  mov     [rsp+68h+var_48], r13
0x1800b40a4  lea     r8, [rsp+68h+arg_18]
0x1800b40ac  mov     rdx, rbp
0x1800b40af  mov     rcx, r14
0x1800b40b2  call    sqlite3OsOpenMalloc
0x1800b40b7  mov     ebx, eax
0x1800b40b9  test    eax, eax
0x1800b40bb  jnz     loc_1800B41D2
0x1800b40c1  mov     rdx, r13
0x1800b40c4  mov     rsi, [rsp+68h+arg_18]
0x1800b40cc  mov     r15d, r13d
0x1800b40cf  mov     [rsp+68h+arg_0], rdx
0x1800b40d4  cmp     [rdi+28h], r13d
0x1800b40d8  jle     loc_1800B4172
0x1800b40de  mov     rax, [rdi+20h]
0x1800b40e2  movsxd  rcx, r15d
0x1800b40e5  shl     rcx, 5
0x1800b40e9  mov     rax, [rcx+rax+8]
0x1800b40ee  test    rax, rax
0x1800b40f1  jz      short loc_1800B4165
0x1800b40f3  cmp     byte ptr [rax+10h], 2
0x1800b40f7  jnz     short loc_1800B4165
0x1800b40f9  mov     rax, [rax+8]
0x1800b40fd  mov     rcx, [rax]
0x1800b4100  mov     r13, [rcx+0E0h]
0x1800b4107  test    r13, r13
0x1800b410a  jz      short loc_1800B4165
0x1800b410c  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800b4110  inc     r8
0x1800b4113  cmp     byte ptr [r8+r13], 0
0x1800b4118  jnz     short loc_1800B4110
0x1800b411a  mov     rax, [rsi]
0x1800b411d  and     r8d, 3FFFFFFFh
0x1800b4124  mov     r9, rdx
0x1800b4127  inc     r8d
0x1800b412a  mov     rdx, r13
0x1800b412d  mov     rcx, rsi
0x1800b4130  mov     rax, [rax+18h]
0x1800b4134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4139  mov     ebx, eax
0x1800b413b  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b413f  inc     rax
0x1800b4142  cmp     byte ptr [rax+r13], 0
0x1800b4147  jnz     short loc_1800B413F
0x1800b4149  xor     r13d, r13d
0x1800b414c  test    ebx, ebx
0x1800b414e  jnz     short loc_1800B41AB
0x1800b4150  mov     rdx, [rsp+68h+arg_0]
0x1800b4155  and     eax, 3FFFFFFFh
0x1800b415a  inc     rdx
0x1800b415d  add     rdx, rax
0x1800b4160  mov     [rsp+68h+arg_0], rdx
0x1800b4165  inc     r15d
0x1800b4168  cmp     r15d, [rdi+28h]
0x1800b416c  jl      loc_1800B40DE
0x1800b4172  mov     rax, [rsi]
0x1800b4175  test    rax, rax
0x1800b4178  jz      short loc_1800B418C
0x1800b417a  mov     rax, [rax+60h]
0x1800b417e  mov     rcx, rsi
0x1800b4181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4186  bt      eax, 0Ah
0x1800b418a  jb      short loc_1800B41A6
0x1800b418c  mov     rax, [rsi]
0x1800b418f  mov     edx, 2
0x1800b4194  mov     rcx, rsi
0x1800b4197  mov     rax, [rax+28h]
0x1800b419b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b41a0  mov     ebx, eax
0x1800b41a2  test    eax, eax
0x1800b41a4  jnz     short loc_1800B41AB
0x1800b41a6  mov     r15d, r13d
0x1800b41a9  jmp     short loc_1800B420A
0x1800b41ab  mov     rcx, rsi
0x1800b41ae  call    sqlite3OsClose
0x1800b41b3  mov     rcx, rsi
0x1800b41b6  call    sqlite3_free
0x1800b41bb  mov     rax, [r14+30h]
0x1800b41bf  test    rax, rax
0x1800b41c2  jz      short loc_1800B41D2
0x1800b41c4  xor     r8d, r8d
0x1800b41c7  mov     rdx, rbp
0x1800b41ca  mov     rcx, r14
0x1800b41cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b41d2  mov     rdx, r12
0x1800b41d5  mov     rcx, rdi
0x1800b41d8  call    sqlite3DbFreeNN
0x1800b41dd  jmp     loc_1800B42B1
  ... truncated ...
```
