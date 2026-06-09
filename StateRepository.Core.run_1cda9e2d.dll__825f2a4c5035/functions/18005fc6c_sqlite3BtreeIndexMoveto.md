# sqlite3BtreeIndexMoveto

- ea: `0x18005fc6c`
- end: `0x1800600b6`
- name: `sqlite3BtreeIndexMoveto`
- size: `1098`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18001ed0c`
- `0x18002a050`
- `0x180066830`

## callees

- `0x18000aac0`
- `0x18000bd90`
- `0x1800203f0`
- `0x18002105c`
- `0x180024414`
- `0x1800259b0`
- `0x180026290`
- `0x1800275f0`
- `0x180056580`
- `0x18005fc6c`
- `0x1800600bc`
- `0x180060134`
- `0x18009a010`

## pseudocode

```c
__int64 __fastcall sqlite3BtreeIndexMoveto(__int64 a1, __int64 a2, int *a3)
{
  __int64 v6; // rcx
  __int64 v7; // r9
  int i; // r8d
  __int64 v9; // rdx
  int v10; // eax
  __int64 result; // rax
  _BYTE *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r15
  __int64 v15; // rbp
  int v16; // r13d
  int j; // r15d
  int v18; // r15d
  unsigned __int8 *v19; // rdx
  __int64 v20; // rcx
  char *v21; // r9
  unsigned __int8 *v22; // rdx
  int v23; // ebx
  signed int v24; // ebx
  char *v25; // rax
  unsigned __int8 *v26; // r13
  unsigned int inited; // ebx
  int v28; // r8d
  unsigned int v29; // edx
  bool v30; // cc
  __int64 v31; // rdx
  __int64 v32; // r9
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 (__fastcall *Compare)(__int64, unsigned __int8 *, __int64, char *); // [rsp+30h] [rbp-58h]
  int v37; // [rsp+90h] [rbp+8h]
  int v38; // [rsp+98h] [rbp+10h]
  signed int v40; // [rsp+A8h] [rbp+20h]

  Compare = (__int64 (__fastcall *)(__int64, unsigned __int8 *, __int64, char *))sqlite3VdbeFindCompare(a2);
  *(_BYTE *)(v6 + 31) = 0;
  if ( *(_BYTE *)a1 || (v7 = *(_QWORD *)(a1 + 136), !*(_BYTE *)(v7 + 8)) )
  {
LABEL_19:
    result = moveToRoot(a1);
    if ( (_DWORD)result )
    {
      if ( (_DWORD)result != 16 )
        return result;
      *a3 = -1;
      return 0;
    }
    goto LABEL_22;
  }
  for ( i = 0; i < *(char *)(a1 + 84); ++i )
  {
    if ( *(_WORD *)(a1 + 2LL * i + 88) < *(_WORD *)(*(_QWORD *)(a1 + 8LL * i + 144) + 24LL) )
      goto LABEL_19;
  }
  v9 = *(unsigned __int16 *)(a1 + 86);
  if ( (_DWORD)v9 == *(unsigned __int16 *)(v7 + 24) - 1 )
  {
    v10 = indexCellCompare(a1, v9, a2, Compare);
    if ( v10 <= 0 && !*(_BYTE *)(a2 + 31) )
    {
      *a3 = v10;
      return 0;
    }
  }
  if ( *(char *)(a1 + 84) <= 0 || (int)indexCellCompare(a1, 0, a2, Compare) > 0 || *(_BYTE *)(a2 + 31) )
  {
    *(_BYTE *)(a2 + 31) = 0;
    goto LABEL_19;
  }
  v12 = *(_BYTE **)(a1 + 136);
  *(_BYTE *)(a1 + 1) &= 0xF3u;
  if ( !*v12 )
  {
    v13 = 76678;
    return sqlite3ReportError(11, v13, "database corruption");
  }
LABEL_22:
  v14 = a1 + 136;
LABEL_23:
  v15 = *(_QWORD *)v14;
  v16 = 0;
  v37 = 0;
  v38 = *(unsigned __int16 *)(*(_QWORD *)v14 + 24LL) - 1;
  for ( j = v38; ; j = v28 + v16 )
  {
    v18 = j >> 1;
    v19 = (unsigned __int8 *)(*(_QWORD *)(v15 + 104)
                            + (unsigned __int16)(*(_WORD *)(v15 + 26)
                                               & __ROR2__(*(_WORD *)(2 * v18 + *(_QWORD *)(v15 + 96)), 8)));
    v20 = *v19;
    v21 = (char *)(v19 + 1);
    if ( (unsigned int)v20 <= *(unsigned __int8 *)(v15 + 11) )
    {
      v22 = v19 + 1;
LABEL_29:
      v23 = Compare(v20, v22, a2, v21);
      goto LABEL_35;
    }
    if ( *v21 >= 0 )
    {
      v20 = (unsigned __int8)*v21 + ((unsigned __int8)(v20 & 0x7F) << 7);
      if ( (unsigned int)v20 <= *(unsigned __int16 *)(v15 + 14) )
      {
        v22 = v19 + 2;
        goto LABEL_29;
      }
    }
    (*(void (__fastcall **)(__int64, unsigned __int8 *, __int64))(v15 + 128))(
      v15,
      &v19[-*(unsigned __int8 *)(v15 + 10)],
      a1 + 48);
    v24 = *(_DWORD *)(a1 + 48);
    v40 = v24;
    if ( v24 < 2
      || (unsigned int)v24 / *(_DWORD *)(*(_QWORD *)(a1 + 32) + 56LL) > *(_DWORD *)(*(_QWORD *)(a1 + 32) + 64LL) )
    {
      sqlite3_log(
        11,
        "%s at line %d of [%.10s]",
        "database corruption",
        76765,
        "2aabe05e2e8cae4847a802ee2daddc1d7413d8fc560254d93ee3e72c14685b6c");
      inited = 11;
      goto LABEL_58;
    }
    v25 = (char *)sqlite3Malloc(v24 + 18);
    v26 = (unsigned __int8 *)v25;
    if ( !v25 )
    {
      inited = 7;
      goto LABEL_58;
    }
    *(_WORD *)(a1 + 86) = v18;
    inited = accessPayload(a1, 0, v24, v25, 0);
    *(_OWORD *)&v26[v40] = 0;
    *(_WORD *)&v26[v40 + 16] = 0;
    *(_BYTE *)(a1 + 1) &= ~4u;
    if ( inited )
    {
      sqlite3_free(v26);
      goto LABEL_58;
    }
    v23 = sqlite3VdbeRecordCompareWithSkip(v40, v26, (__int64 *)a2, 0);
    sqlite3_free(v26);
    v16 = v37;
LABEL_35:
    if ( v23 < 0 )
    {
      v28 = v38;
      v16 = v18 + 1;
      v37 = v18 + 1;
      goto LABEL_39;
    }
    if ( v23 <= 0 )
      break;
    v28 = v18 - 1;
    v38 = v18 - 1;
LABEL_39:
    if ( v16 > v28 )
    {
      if ( *(_BYTE *)(v15 + 8) )
      {
        *(_WORD *)(a1 + 86) = v18;
        *a3 = v23;
        inited = 0;
        goto LABEL_58;
      }
      if ( v16 < *(unsigned __int16 *)(v15 + 24) )
        v29 = *(_DWORD *)((unsigned __int16)(*(_WORD *)(v15 + 26)
                                           & __ROR2__(*(_WORD *)(2 * v16 + *(_QWORD *)(v15 + 96)), 8))
                        + *(_QWORD *)(v15 + 80));
      else
        v29 = *(_DWORD *)(*(unsigned __int8 *)(v15 + 9) + *(_QWORD *)(v15 + 80) + 8LL);
      *(_BYTE *)(a1 + 1) &= 0xF9u;
      v30 = *(_BYTE *)(a1 + 84) < 19;
      v31 = _byteswap_ulong(v29);
      *(_WORD *)(a1 + 70) = 0;
      if ( !v30 )
      {
        v13 = 76828;
        return sqlite3ReportError(11, v13, "database corruption");
      }
      v14 = a1 + 136;
      *(_WORD *)(a1 + 2LL * *(char *)(a1 + 84) + 88) = v16;
      *(_QWORD *)(a1 + 8LL * *(char *)(a1 + 84) + 144) = *(_QWORD *)(a1 + 136);
      v32 = *(unsigned __int8 *)(a1 + 2);
      v33 = *(_QWORD *)(a1 + 32);
      *(_WORD *)(a1 + 86) = 0;
      ++*(_BYTE *)(a1 + 84);
      inited = getAndInitPage(v33, v31, a1 + 136, v32);
      if ( inited
        || ((v34 = *(_QWORD *)v14, !*(_WORD *)(*(_QWORD *)v14 + 24LL)) || *(_BYTE *)(v34 + 1) != *(_BYTE *)(a1 + 85))
        && (releasePage(v34), (inited = sqlite3ReportError(11, 76839, "database corruption")) != 0) )
      {
        v35 = (char)(*(_BYTE *)(a1 + 84))--;
        *(_QWORD *)v14 = *(_QWORD *)(a1 + 8 * v35 + 136);
        goto LABEL_58;
      }
      goto LABEL_23;
    }
  }
  inited = 0;
  *a3 = 0;
  *(_WORD *)(a1 + 86) = v18;
  if ( *(_BYTE *)(a2 + 31) )
    inited = sqlite3ReportError(11, 76797, "database corruption");
LABEL_58:
  *(_WORD *)(a1 + 70) = 0;
  return inited;
}

```

## disassembly

```asm
0x18005fc6c  mov     [rsp+arg_10], r8
0x18005fc71  push    rbx
0x18005fc72  push    rbp
0x18005fc73  push    rsi
0x18005fc74  push    rdi
0x18005fc75  push    r12
0x18005fc77  push    r13
0x18005fc79  push    r14
0x18005fc7b  push    r15
0x18005fc7d  sub     rsp, 48h
0x18005fc81  mov     rdi, rcx
0x18005fc84  mov     rbx, r8
0x18005fc87  mov     rcx, rdx
0x18005fc8a  mov     rsi, rdx
0x18005fc8d  call    sqlite3VdbeFindCompare
0x18005fc92  xor     r14d, r14d
0x18005fc95  mov     [rsp+88h+var_58], rax
0x18005fc9a  mov     [rcx+1Fh], r14b
0x18005fc9e  lea     r11d, [r14+1]
0x18005fca2  cmp     [rdi], r14b
0x18005fca5  jnz     loc_18005FD6D
0x18005fcab  mov     r9, [rdi+88h]
0x18005fcb2  cmp     [r9+8], r14b
0x18005fcb6  jz      loc_18005FD6D
0x18005fcbc  movsx   r10d, byte ptr [rdi+54h]
0x18005fcc1  mov     r8d, r14d
0x18005fcc4  cmp     r8d, r10d
0x18005fcc7  jge     short loc_18005FCE8
0x18005fcc9  movsxd  rdx, r8d
0x18005fccc  mov     rax, [rdi+rdx*8+90h]
0x18005fcd4  movzx   ecx, word ptr [rax+18h]
0x18005fcd8  cmp     [rdi+rdx*2+58h], cx
0x18005fcdd  jb      loc_18005FD6D
0x18005fce3  add     r8d, r11d
0x18005fce6  jmp     short loc_18005FCC4
0x18005fce8  movzx   eax, word ptr [r9+18h]
0x18005fced  movzx   edx, word ptr [rdi+56h]
0x18005fcf1  sub     eax, r11d
0x18005fcf4  mov     rbp, [rsp+88h+var_58]
0x18005fcf9  cmp     edx, eax
0x18005fcfb  jnz     short loc_18005FD1E
0x18005fcfd  mov     r9, rbp
0x18005fd00  mov     r8, rsi
0x18005fd03  mov     rcx, rdi
0x18005fd06  call    indexCellCompare
0x18005fd0b  test    eax, eax
0x18005fd0d  jg      short loc_18005FD1E
0x18005fd0f  cmp     [rsi+1Fh], r14b
0x18005fd13  jnz     short loc_18005FD1E
0x18005fd15  mov     [rbx], eax
0x18005fd17  xor     eax, eax
0x18005fd19  jmp     loc_1800600A5
0x18005fd1e  cmp     [rdi+54h], r14b
0x18005fd22  jle     short loc_18005FD69
0x18005fd24  mov     r9, rbp
0x18005fd27  mov     r8, rsi
0x18005fd2a  xor     edx, edx
0x18005fd2c  mov     rcx, rdi
0x18005fd2f  call    indexCellCompare
0x18005fd34  test    eax, eax
0x18005fd36  jg      short loc_18005FD69
0x18005fd38  cmp     [rsi+1Fh], r14b
0x18005fd3c  jnz     short loc_18005FD69
0x18005fd3e  mov     rax, [rdi+88h]
0x18005fd45  and     byte ptr [rdi+1], 0F3h
0x18005fd49  cmp     [rax], r14b
0x18005fd4c  jnz     short loc_18005FD8A
0x18005fd4e  lea     r8, aDatabaseCorrup; "database corruption"
0x18005fd55  mov     edx, 12B86h
0x18005fd5a  mov     ecx, 0Bh
0x18005fd5f  call    sqlite3ReportError
0x18005fd64  jmp     loc_1800600A5
0x18005fd69  mov     [rsi+1Fh], r14b
0x18005fd6d  mov     rcx, rdi
0x18005fd70  call    moveToRoot
0x18005fd75  test    eax, eax
0x18005fd77  jz      short loc_18005FD8A
0x18005fd79  cmp     eax, 10h
0x18005fd7c  jnz     loc_1800600A5
0x18005fd82  mov     dword ptr [rbx], 0FFFFFFFFh
0x18005fd88  jmp     short loc_18005FD17
0x18005fd8a  lea     r15, [rdi+88h]
0x18005fd91  mov     r14d, 0Bh
0x18005fd97  lea     r12, aDatabaseCorrup; "database corruption"
0x18005fd9e  mov     rbp, [r15]
0x18005fda1  xor     r13d, r13d
0x18005fda4  mov     [rsp+88h+arg_0], r13d
0x18005fdac  movzx   r8d, word ptr [rbp+18h]
0x18005fdb1  dec     r8d
0x18005fdb4  mov     [rsp+88h+arg_8], r8d
0x18005fdbc  mov     r15d, r8d
0x18005fdbf  sar     r15d, 1
0x18005fdc2  lea     eax, [r15+r15]
0x18005fdc6  movsxd  rcx, eax
0x18005fdc9  mov     rax, [rbp+60h]
0x18005fdcd  movzx   edx, word ptr [rcx+rax]
0x18005fdd1  movzx   eax, word ptr [rbp+1Ah]
0x18005fdd5  ror     dx, 8
0x18005fdd9  movzx   edx, dx
0x18005fddc  and     rdx, rax
0x18005fddf  movzx   eax, byte ptr [rbp+0Bh]
0x18005fde3  add     rdx, [rbp+68h]
0x18005fde7  movzx   ecx, byte ptr [rdx]
0x18005fdea  lea     r9, [rdx+1]
0x18005fdee  cmp     ecx, eax
0x18005fdf0  ja      short loc_18005FDF7
0x18005fdf2  mov     rdx, r9
0x18005fdf5  jmp     short loc_18005FE15
0x18005fdf7  cmp     byte ptr [r9], 0
0x18005fdfb  jl      short loc_18005FE29
0x18005fdfd  movzx   eax, byte ptr [r9]
0x18005fe01  and     ecx, 7Fh
0x18005fe04  shl     ecx, 7
0x18005fe07  add     ecx, eax
0x18005fe09  movzx   eax, word ptr [rbp+0Eh]
0x18005fe0d  cmp     ecx, eax
0x18005fe0f  ja      short loc_18005FE29
0x18005fe11  add     rdx, 2
0x18005fe15  mov     rax, [rsp+88h+var_58]
0x18005fe1a  mov     r8, rsi
0x18005fe1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fe22  mov     ebx, eax
0x18005fe24  jmp     loc_18005FEE4
0x18005fe29  movzx   eax, byte ptr [rbp+0Ah]
0x18005fe2d  lea     r8, [rdi+30h]
0x18005fe31  sub     rdx, rax
0x18005fe34  mov     rcx, rbp
0x18005fe37  mov     rax, [rbp+80h]
0x18005fe3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fe43  mov     ebx, [rdi+30h]
0x18005fe46  mov     [rsp+88h+arg_18], ebx
0x18005fe4d  cmp     ebx, 2
0x18005fe50  jl      loc_180060076
0x18005fe56  mov     rcx, [rdi+20h]
0x18005fe5a  xor     edx, edx
0x18005fe5c  mov     eax, ebx
0x18005fe5e  div     dword ptr [rcx+38h]
0x18005fe61  cmp     eax, [rcx+40h]
0x18005fe64  ja      loc_180060076
0x18005fe6a  lea     eax, [rbx+12h]
0x18005fe6d  movsxd  rcx, eax
0x18005fe70  call    sqlite3Malloc
0x18005fe75  mov     r13, rax
0x18005fe78  test    rax, rax
0x18005fe7b  jz      loc_18006006F
0x18005fe81  mov     r9, rax
0x18005fe84  mov     [rdi+56h], r15w
0x18005fe89  mov     r8d, ebx
0x18005fe8c  mov     dword ptr [rsp+88h+var_68], 0
0x18005fe94  xor     edx, edx
0x18005fe96  mov     rcx, rdi
0x18005fe99  call    accessPayload
0x18005fe9e  movsxd  rcx, [rsp+88h+arg_18]
0x18005fea6  mov     ebx, eax
0x18005fea8  xor     eax, eax
0x18005feaa  xorps   xmm0, xmm0
0x18005fead  movups  xmmword ptr [rcx+r13], xmm0
0x18005feb2  mov     [rcx+r13+10h], ax
0x18005feb8  and     byte ptr [rdi+1], 0FBh
0x18005febc  test    ebx, ebx
0x18005febe  jnz     loc_180060065
0x18005fec4  xor     r9d, r9d
0x18005fec7  mov     r8, rsi
0x18005feca  mov     rdx, r13
0x18005fecd  call    sqlite3VdbeRecordCompareWithSkip
0x18005fed2  mov     rcx, r13
0x18005fed5  mov     ebx, eax
0x18005fed7  call    sqlite3_free
0x18005fedc  mov     r13d, [rsp+88h+arg_0]
0x18005fee4  test    ebx, ebx
0x18005fee6  jns     short loc_18005FEFE
0x18005fee8  mov     r8d, [rsp+88h+arg_8]
0x18005fef0  lea     r13d, [r15+1]
0x18005fef4  mov     [rsp+88h+arg_0], r13d
0x18005fefc  jmp     short loc_18005FF10
0x18005fefe  jle     loc_180060037
0x18005ff04  lea     r8d, [r15-1]
0x18005ff08  mov     [rsp+88h+arg_8], r8d
0x18005ff10  cmp     r13d, r8d
0x18005ff13  jg      short loc_18005FF1E
0x18005ff15  lea     r15d, [r8+r13]
0x18005ff19  jmp     loc_18005FDBF
0x18005ff1e  cmp     byte ptr [rbp+8], 0
0x18005ff22  jnz     loc_180060024
0x18005ff28  movzx   eax, word ptr [rbp+18h]
0x18005ff2c  cmp     r13d, eax
0x18005ff2f  jl      short loc_18005FF3F
0x18005ff31  movzx   ecx, byte ptr [rbp+9]
0x18005ff35  mov     rax, [rbp+50h]
0x18005ff39  mov     edx, [rcx+rax+8]
0x18005ff3d  jmp     short loc_18005FF67
0x18005ff3f  lea     eax, ds:0[r13*2]
0x18005ff47  movsxd  rcx, eax
0x18005ff4a  mov     rax, [rbp+60h]
0x18005ff4e  movzx   edx, word ptr [rcx+rax]
0x18005ff52  movzx   eax, word ptr [rbp+1Ah]
0x18005ff56  ror     dx, 8
0x18005ff5a  movzx   ecx, dx
0x18005ff5d  and     rcx, rax
0x18005ff60  mov     rax, [rbp+50h]
0x18005ff64  mov     edx, [rcx+rax]
0x18005ff67  and     byte ptr [rdi+1], 0F9h
0x18005ff6b  xor     eax, eax
0x18005ff6d  cmp     byte ptr [rdi+54h], 13h
0x18005ff71  bswap   edx
0x18005ff73  mov     [rdi+46h], ax
0x18005ff77  jge     loc_180060014
0x18005ff7d  movsx   rax, byte ptr [rdi+54h]
0x18005ff82  lea     r15, [rdi+88h]
0x18005ff89  mov     r8, r15
0x18005ff8c  mov     [rdi+rax*2+58h], r13w
0x18005ff92  movsx   rcx, byte ptr [rdi+54h]
0x18005ff97  mov     rax, [r15]
0x18005ff9a  mov     [rdi+rcx*8+90h], rax
0x18005ffa2  xor     eax, eax
0x18005ffa4  movzx   r9d, byte ptr [rdi+2]
0x18005ffa9  mov     rcx, [rdi+20h]
0x18005ffad  mov     [rdi+56h], ax
0x18005ffb1  lea     ebp, [rax+1]
0x18005ffb4  add     [rdi+54h], bpl
0x18005ffb8  call    getAndInitPage
0x18005ffbd  mov     ebx, eax
0x18005ffbf  test    eax, eax
0x18005ffc1  jnz     short loc_18005FFF7
0x18005ffc3  mov     rcx, [r15]
0x18005ffc6  cmp     [rcx+18h], bp
0x18005ffca  jb      short loc_18005FFD8
0x18005ffcc  mov     al, [rdi+55h]
0x18005ffcf  cmp     [rcx+1], al
0x18005ffd2  jz      loc_18005FD9E
0x18005ffd8  call    releasePage
0x18005ffdd  mov     r8, r12
0x18005ffe0  mov     edx, 12C27h
0x18005ffe5  mov     ecx, r14d
0x18005ffe8  call    sqlite3ReportError
0x18005ffed  mov     ebx, eax
0x18005ffef  test    eax, eax
0x18005fff1  jz      loc_18005FD9E
0x18005fff7  movsx   rcx, byte ptr [rdi+54h]
0x18005fffc  mov     al, cl
0x18005fffe  sub     al, bpl
0x180060001  mov     [rdi+54h], al
0x180060004  mov     rcx, [rdi+rcx*8+88h]
0x18006000c  mov     [r15], rcx
0x18006000f  jmp     loc_18006009D
0x180060014  mov     r8, r12
0x180060017  mov     edx, 12C1Ch
0x18006001c  mov     ecx, r14d
0x18006001f  jmp     loc_18005FD5F
0x180060024  mov     rax, [rsp+88h+arg_10]
0x18006002c  mov     [rdi+56h], r15w
0x180060031  mov     [rax], ebx
0x180060033  xor     ebx, ebx
0x180060035  jmp     short loc_18006009D
0x180060037  mov     rax, [rsp+88h+arg_10]
0x18006003f  xor     ebx, ebx
0x180060041  mov     dword ptr [rax], 0
0x180060047  mov     [rdi+56h], r15w
0x18006004c  cmp     [rsi+1Fh], bl
0x18006004f  jz      short loc_18006009D
0x180060051  mov     r8, r12
0x180060054  mov     edx, 12BFDh
0x180060059  mov     ecx, r14d
0x18006005c  call    sqlite3ReportError
0x180060061  mov     ebx, eax
0x180060063  jmp     short loc_18006009D
0x180060065  mov     rcx, r13
0x180060068  call    sqlite3_free
0x18006006d  jmp     short loc_18006009D
0x18006006f  mov     ebx, 7
0x180060074  jmp     short loc_18006009D
0x180060076  lea     rax, a20241207203959+14h; "2aabe05e2e8cae4847a802ee2daddc1d7413d8f"...
0x18006007d  mov     r9d, 12BDDh
0x180060083  mov     r8, r12
0x180060086  mov     [rsp+88h+var_68], rax
0x18006008b  lea     rdx, aSAtLineDOf10s; "%s at line %d of [%.10s]"
0x180060092  mov     ecx, r14d
0x180060095  call    sqlite3_log
0x18006009a  mov     ebx, r14d
0x18006009d  xor     eax, eax
0x18006009f  mov     [rdi+46h], ax
0x1800600a3  mov     eax, ebx
0x1800600a5  add     rsp, 48h
0x1800600a9  pop     r15
0x1800600ab  pop     r14
0x1800600ad  pop     r13
0x1800600af  pop     r12
0x1800600b1  pop     rdi
0x1800600b2  pop     rsi
0x1800600b3  pop     rbp
0x1800600b4  pop     rbx
0x1800600b5  retn
```
