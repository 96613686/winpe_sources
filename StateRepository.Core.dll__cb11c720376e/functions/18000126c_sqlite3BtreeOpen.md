# sqlite3BtreeOpen

- ea: `0x18000126c`
- end: `0x180001837`
- name: `sqlite3BtreeOpen`
- size: `1483`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `4`
- callee_count: `20`
- tags: `file_ops, loader_planting`

## callers

- `0x180001fbc`
- `0x18002a050`
- `0x180069970`
- `0x180085a44`

## callees

- `0x18000126c`
- `0x180001840`
- `0x180001d98`
- `0x180001db8`
- `0x180005810`
- `0x180005d14`
- `0x1800073ec`
- `0x1800084bc`
- `0x180008838`
- `0x180008f14`
- `0x180009f00`
- `0x18000aac0`
- `0x18000b220`
- `0x18000bd44`
- `0x18000bd90`
- `0x180024388`
- `0x180068880`
- `0x1800997e4`
- `0x180099814`
- `0x18009a010`

## pseudocode

```c
__int64 __fastcall sqlite3BtreeOpen(__int64 a1, char *a2, __int64 a3, __int64 *a4, char a5, unsigned int a6)
{
  unsigned int v6; // ebp
  __int64 v7; // r14
  __int64 v9; // rsi
  int v10; // ebx
  int v11; // r13d
  char v12; // r12
  __int64 v13; // rax
  __int64 v14; // rdi
  int v16; // eax
  __int64 v17; // r8
  int v18; // edx
  __int64 v19; // rbx
  unsigned int v20; // esi
  _BYTE *v21; // r14
  _BYTE *v22; // r12
  unsigned int Fileheader; // esi
  __int64 *i; // rbx
  unsigned int v25; // eax
  int v26; // edx
  __int64 v27; // r8
  __int64 *v28; // rax
  __int64 v29; // r9
  __int64 *v30; // r14
  __int64 v31; // rcx
  __int64 v32; // rdx
  _QWORD *v33; // rcx
  _QWORD *v34; // r8
  __int64 v35; // rcx
  __int64 v36; // r9
  _DWORD *v37; // r14
  int v38; // ecx
  unsigned __int8 v39; // cl
  int v40; // ebp
  int v41; // eax
  __int64 v42; // rbp
  __int64 v43; // rax
  int j; // r8d
  __int64 v45; // rdx
  unsigned __int64 v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rax
  _QWORD *v49; // rcx
  int v50; // [rsp+30h] [rbp-108h]
  char v52; // [rsp+48h] [rbp-F0h]
  __int64 v55; // [rsp+60h] [rbp-D8h]
  __int64 v56; // [rsp+68h] [rbp-D0h]
  char v57[16]; // [rsp+70h] [rbp-C8h] BYREF
  __int64 v58; // [rsp+80h] [rbp-B8h]
  unsigned int v59; // [rsp+A4h] [rbp-94h]
  unsigned int v60; // [rsp+B0h] [rbp-88h]

  v6 = a6;
  v7 = a3;
  v9 = a1;
  if ( a2 && *a2 )
  {
    v10 = 0;
  }
  else
  {
    v10 = 1;
    if ( !a2 )
    {
LABEL_7:
      if ( *(_BYTE *)(v7 + 102) == 2 )
        goto LABEL_10;
      goto LABEL_8;
    }
  }
  if ( !strcmp_0(a2, ":memory:") )
    goto LABEL_10;
  if ( v10 )
    goto LABEL_7;
LABEL_8:
  if ( (a6 & 0x80u) == 0 )
  {
    v11 = 0;
    goto LABEL_11;
  }
LABEL_10:
  v11 = 1;
LABEL_11:
  v12 = a5 | 2;
  if ( !v11 )
    v12 = a5;
  v52 = v12;
  if ( (a6 & 0x100) != 0 && (v11 || v10) )
    v6 = a6 & 0xFFFFFCFF | 0x200;
  v13 = sqlite3MallocZero(0x48u);
  v14 = v13;
  if ( !v13 )
    return 7;
  *(_QWORD *)v13 = v7;
  v55 = 0;
  *(_BYTE *)(v13 + 16) = 0;
  *(_QWORD *)(v13 + 48) = v13;
  *(_DWORD *)(v13 + 56) = 1;
  if ( v10 || v11 && (v6 & 0x40) == 0 || (v6 & 0x20000) == 0 )
    goto LABEL_47;
  v16 = sqlite3Strlen30(a2);
  v18 = *(_DWORD *)(v9 + 8);
  v19 = v16;
  v20 = v18 + 1;
  if ( v18 + 1 <= v16 + 1 )
    v18 = v16;
  v21 = (_BYTE *)sqlite3Malloc(v17 + v18);
  v22 = (_BYTE *)(v14 + 17);
  *(_BYTE *)(v14 + 17) = 1;
  if ( v21 )
  {
    if ( v11 )
    {
      Fileheader = 0;
      memcpy_0(v21, a2, v19 + 1);
    }
    else
    {
      *v21 = 0;
      v25 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, _BYTE *))(a1 + 64))(a1, a2, v20, v21);
      Fileheader = v25;
      if ( v25 )
      {
        if ( v25 != 512 )
        {
          sqlite3_free(v21);
          goto LABEL_38;
        }
        Fileheader = 0;
      }
    }
    v55 = sqlite3MutexAlloc(4);
    sqlite3_mutex_enter(v55);
    v56 = sqlite3MutexAlloc(2);
    sqlite3_mutex_enter(v56);
    for ( i = (__int64 *)qword_1800B5B08; i; i = (__int64 *)i[14] )
    {
      if ( !strcmp(v21, *(const char **)(*i + 216)) && *(_QWORD *)*i == a1 )
      {
        v26 = *(_DWORD *)(a3 + 40);
        while ( --v26 >= 0 )
        {
          v27 = *(_QWORD *)(32LL * v26 + *(_QWORD *)(a3 + 32) + 8);
          if ( v27 && *(__int64 **)(v27 + 8) == i )
          {
            sqlite3_mutex_leave(v56);
            sqlite3_mutex_leave(v55);
            sqlite3_free(v21);
            sqlite3_free(v14);
            return 19;
          }
        }
        *(_QWORD *)(v14 + 8) = i;
        ++*((_DWORD *)i + 26);
        break;
      }
    }
    sqlite3_mutex_leave(v56);
    sqlite3_free(v21);
    if ( i )
      goto LABEL_73;
    v7 = a3;
    v12 = v52;
    v9 = a1;
LABEL_47:
    v58 = 0;
    v28 = (__int64 *)sqlite3MallocZero(0x98u);
    i = v28;
    if ( !v28 )
    {
      v30 = a4;
      Fileheader = 7;
      goto LABEL_68;
    }
    Fileheader = sqlite3PagerOpen(v9, v28, a2, v29, v12, v6, v50);
    if ( Fileheader )
      goto LABEL_65;
    v31 = *i;
    *(_QWORD *)(v31 + 160) = *(_QWORD *)(v7 + 64);
    pagerFixMaplimit(v31);
    Fileheader = sqlite3PagerReadFileheader(*i, v32, v57);
    if ( Fileheader )
      goto LABEL_65;
    v33 = (_QWORD *)*i;
    *((_BYTE *)i + 32) = v12;
    i[1] = v7;
    v34 = v33 + 29;
    v33[30] = i;
    v35 = v33[9];
    *v34 = btreeInvokeBusyHandler;
    sqlite3OsFileControlHint(v35, 15, v34);
    *(_QWORD *)(v14 + 8) = i;
    v36 = *i;
    i[2] = 0;
    i[3] = 0;
    if ( *(_BYTE *)(v36 + 18) )
      *((_WORD *)i + 20) |= 1u;
    v37 = (_DWORD *)i + 13;
    v38 = (unsigned __int16)v58 << 8;
    *((_DWORD *)i + 13) = v38;
    if ( (unsigned int)(v38 - 512) > 0xFE00 || ((v38 - 1) & v38) != 0 )
    {
      *v37 = 0;
      if ( a2 && !v11 )
        *(_WORD *)((char *)i + 33) = 0;
      v39 = 0;
    }
    else
    {
      v39 = BYTE4(v58);
      *((_WORD *)i + 20) |= 2u;
      *((_BYTE *)i + 33) = _byteswap_ulong(v59) != 0;
      *((_BYTE *)i + 34) = _byteswap_ulong(v60) != 0;
    }
    v40 = v39;
    Fileheader = sqlite3PagerSetPagesize(v36, (char *)i + 52, v39);
    if ( Fileheader )
      goto LABEL_65;
    v22 = (_BYTE *)(v14 + 17);
    v41 = *v37 - v40;
    *((_DWORD *)i + 26) = 1;
    *((_DWORD *)i + 14) = v41;
    if ( !*(_BYTE *)(v14 + 17) )
    {
LABEL_89:
      v30 = a4;
      *a4 = v14;
      if ( !Fileheader )
      {
        if ( !sqlite3BtreeSchema(v14, 0, 0) )
          sqlite3BtreeSetCacheSize(v14, 4294965296LL);
        v49 = *(_QWORD **)(*i + 72);
        if ( *v49 )
          sqlite3OsFileControlHint(v49, 30, i + 1);
        goto LABEL_69;
      }
      if ( !i )
      {
LABEL_68:
        sqlite3_free(i);
        sqlite3_free(v14);
        *v30 = 0;
LABEL_69:
        if ( v55 )
          sqlite3_mutex_leave(v55);
        return Fileheader;
      }
LABEL_66:
      if ( *i )
        sqlite3PagerClose(*i, 0);
      goto LABEL_68;
    }
    v42 = sqlite3MutexAlloc(2);
    if ( (_BYTE)word_1800B5634 != (_BYTE)Fileheader )
    {
      v43 = sqlite3MutexAlloc(0);
      i[11] = v43;
      if ( !v43 )
      {
        Fileheader = 7;
LABEL_65:
        v30 = a4;
        goto LABEL_66;
      }
    }
    sqlite3_mutex_enter(v42);
    i[14] = qword_1800B5B08;
    qword_1800B5B08 = (__int64)i;
    sqlite3_mutex_leave(v42);
LABEL_73:
    if ( *v22 )
    {
      for ( j = 0; j < *(_DWORD *)(a3 + 40); ++j )
      {
        v45 = *(_QWORD *)(32LL * j + *(_QWORD *)(a3 + 32) + 8);
        if ( v45 && *(_BYTE *)(v45 + 17) )
        {
          while ( *(_QWORD *)(v45 + 40) )
            v45 = *(_QWORD *)(v45 + 40);
          v46 = *(_QWORD *)(v14 + 8);
          if ( v46 >= *(_QWORD *)(v45 + 8) )
          {
            if ( *(_QWORD *)(v45 + 32) )
            {
              do
              {
                v47 = *(_QWORD *)(v45 + 32);
                if ( *(_QWORD *)(v47 + 8) >= v46 )
                  break;
                v45 = *(_QWORD *)(v45 + 32);
              }
              while ( *(_QWORD *)(v47 + 32) );
            }
            v48 = *(_QWORD *)(v45 + 32);
            *(_QWORD *)(v14 + 32) = v48;
            *(_QWORD *)(v14 + 40) = v45;
            if ( v48 )
              *(_QWORD *)(v48 + 40) = v14;
            *(_QWORD *)(v45 + 32) = v14;
          }
          else
          {
            *(_QWORD *)(v14 + 32) = v45;
            *(_QWORD *)(v14 + 40) = 0;
            *(_QWORD *)(v45 + 40) = v14;
          }
          goto LABEL_89;
        }
      }
    }
    goto LABEL_89;
  }
  Fileheader = 7;
LABEL_38:
  sqlite3_free(v14);
  return Fileheader;
}

```

## disassembly

```asm
0x18000126c  push    rbx
0x18000126e  push    rbp
0x18000126f  push    rsi
0x180001270  push    rdi
0x180001271  push    r12
0x180001273  push    r13
0x180001275  push    r14
0x180001277  push    r15
0x180001279  sub     rsp, 0F8h
0x180001280  mov     rax, cs:__security_cookie
0x180001287  xor     rax, rsp
0x18000128a  mov     [rsp+138h+var_58], rax
0x180001292  mov     ebp, [rsp+138h+arg_28]
0x180001299  mov     r14, r8
0x18000129c  mov     [rsp+138h+var_F8], r9
0x1800012a1  mov     r15, rdx
0x1800012a4  mov     [rsp+138h+var_E0], r8
0x1800012a9  mov     rsi, rcx
0x1800012ac  mov     [rsp+138h+var_E8], rcx
0x1800012b1  mov     edi, 1
0x1800012b6  test    rdx, rdx
0x1800012b9  jz      short loc_1800012C4
0x1800012bb  cmp     byte ptr [rdx], 0
0x1800012be  jz      short loc_1800012C4
0x1800012c0  xor     ebx, ebx
0x1800012c2  jmp     short loc_1800012CB
0x1800012c4  mov     ebx, edi
0x1800012c6  test    r15, r15
0x1800012c9  jz      short loc_1800012E2
0x1800012cb  lea     rdx, Str2; ":memory:"
0x1800012d2  mov     rcx, r15; Str1
0x1800012d5  call    strcmp_0
0x1800012da  test    eax, eax
0x1800012dc  jz      short loc_1800012F3
0x1800012de  test    ebx, ebx
0x1800012e0  jz      short loc_1800012E9
0x1800012e2  cmp     byte ptr [r14+66h], 2
0x1800012e7  jz      short loc_1800012F3
0x1800012e9  test    bpl, bpl
0x1800012ec  js      short loc_1800012F3
0x1800012ee  xor     r13d, r13d
0x1800012f1  jmp     short loc_1800012F6
0x1800012f3  mov     r13d, edi
0x1800012f6  mov     r12d, dword ptr [rsp+138h+arg_20]
0x1800012fe  or      r12d, 2
0x180001302  test    r13d, r13d
0x180001305  cmovz   r12d, dword ptr [rsp+138h+arg_20]
0x18000130e  mov     dword ptr [rsp+138h+var_F0], r12d
0x180001313  bt      ebp, 8
0x180001317  jnb     short loc_18000132A
0x180001319  test    r13d, r13d
0x18000131c  jnz     short loc_180001322
0x18000131e  test    ebx, ebx
0x180001320  jz      short loc_18000132A
0x180001322  btr     ebp, 8
0x180001326  bts     ebp, 9
0x18000132a  mov     ecx, 48h ; 'H'; Size
0x18000132f  call    sqlite3MallocZero
0x180001334  mov     rdi, rax
0x180001337  test    rax, rax
0x18000133a  jnz     short loc_180001344
0x18000133c  lea     eax, [rdi+7]
0x18000133f  jmp     loc_180001707
0x180001344  xor     ecx, ecx
0x180001346  mov     [rax], r14
0x180001349  mov     [rsp+138h+var_D8], rcx
0x18000134e  mov     [rax+10h], cl
0x180001351  mov     [rax+30h], rdi
0x180001355  lea     r8d, [rcx+1]
0x180001359  mov     [rax+38h], r8d
0x18000135d  test    ebx, ebx
0x18000135f  jnz     loc_180001527
0x180001365  test    r13d, r13d
0x180001368  jz      short loc_180001374
0x18000136a  test    bpl, 40h
0x18000136e  jz      loc_180001527
0x180001374  bt      ebp, 11h
0x180001378  jnb     loc_180001527
0x18000137e  mov     rcx, r15
0x180001381  call    sqlite3Strlen30
0x180001386  mov     edx, [rsi+8]
0x180001389  movsxd  rbx, eax
0x18000138c  lea     esi, [rdx+1]
0x18000138f  lea     ecx, [rbx+1]
0x180001392  cmp     esi, ecx
0x180001394  cmovle  edx, ebx
0x180001397  movsxd  rcx, edx
0x18000139a  add     rcx, r8
0x18000139d  call    sqlite3Malloc
0x1800013a2  mov     r14, rax
0x1800013a5  lea     r12, [rdi+11h]
0x1800013a9  mov     eax, 1
0x1800013ae  mov     [r12], al
0x1800013b2  test    r14, r14
0x1800013b5  jnz     short loc_1800013BF
0x1800013b7  lea     esi, [rax+6]
0x1800013ba  jmp     loc_18000148F
0x1800013bf  mov     rdx, r15; Src
0x1800013c2  test    r13d, r13d
0x1800013c5  jz      loc_180001454
0x1800013cb  xor     esi, esi
0x1800013cd  lea     r8, [rax+rbx]; Size
0x1800013d1  mov     rcx, r14; void *
0x1800013d4  call    memcpy_0
0x1800013d9  mov     ecx, 4
0x1800013de  call    sqlite3MutexAlloc
0x1800013e3  mov     rcx, rax
0x1800013e6  mov     [rsp+138h+var_D8], rax
0x1800013eb  call    sqlite3_mutex_enter
0x1800013f0  mov     ecx, 2
0x1800013f5  call    sqlite3MutexAlloc
0x1800013fa  mov     rcx, rax
0x1800013fd  mov     [rsp+138h+var_D0], rax
0x180001402  call    sqlite3_mutex_enter
0x180001407  mov     r10, [rsp+138h+var_E8]
0x18000140c  mov     rbx, cs:qword_1800B5B08
0x180001413  test    rbx, rbx
0x180001416  jz      loc_1800014FD
0x18000141c  mov     r9, [rbx]
0x18000141f  mov     rcx, r14
0x180001422  mov     r11d, 1
0x180001428  mov     r8, [r9+0D8h]
0x18000142f  sub     r8, r14
0x180001432  movzx   edx, byte ptr [rcx]
0x180001435  movzx   eax, byte ptr [rcx+r8]
0x18000143a  sub     edx, eax
0x18000143c  jnz     short loc_180001445
0x18000143e  add     rcx, r11
0x180001441  test    eax, eax
0x180001443  jnz     short loc_180001432
0x180001445  test    edx, edx
0x180001447  jnz     short loc_18000144E
0x180001449  cmp     [r9], r10
0x18000144c  jz      short loc_18000149C
0x18000144e  mov     rbx, [rbx+70h]
0x180001452  jmp     short loc_180001413
0x180001454  mov     rax, [rsp+138h+var_E8]
0x180001459  mov     r9, r14
0x18000145c  mov     byte ptr [r14], 0
0x180001460  mov     rcx, rax
0x180001463  mov     r8d, esi
0x180001466  mov     rax, [rax+40h]
0x18000146a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000146f  mov     esi, eax
0x180001471  test    eax, eax
0x180001473  jz      loc_1800013D9
0x180001479  cmp     eax, 200h
0x18000147e  jnz     short loc_180001487
0x180001480  xor     esi, esi
0x180001482  jmp     loc_1800013D9
0x180001487  mov     rcx, r14
0x18000148a  call    sqlite3_free
0x18000148f  mov     rcx, rdi
0x180001492  call    sqlite3_free
0x180001497  jmp     loc_180001705
0x18000149c  mov     r9, [rsp+138h+var_E0]
0x1800014a1  mov     edx, [r9+28h]
0x1800014a5  sub     edx, r11d
0x1800014a8  test    edx, edx
0x1800014aa  js      short loc_1800014F5
0x1800014ac  mov     rax, [r9+20h]
0x1800014b0  movsxd  rcx, edx
0x1800014b3  shl     rcx, 5
0x1800014b7  mov     r8, [rcx+rax+8]
0x1800014bc  test    r8, r8
0x1800014bf  jz      short loc_1800014A5
0x1800014c1  cmp     [r8+8], rbx
0x1800014c5  jnz     short loc_1800014A5
0x1800014c7  mov     rcx, [rsp+138h+var_D0]
0x1800014cc  call    sqlite3_mutex_leave
0x1800014d1  mov     rcx, [rsp+138h+var_D8]
0x1800014d6  call    sqlite3_mutex_leave
0x1800014db  mov     rcx, r14
0x1800014de  call    sqlite3_free
0x1800014e3  mov     rcx, rdi
0x1800014e6  call    sqlite3_free
0x1800014eb  mov     eax, 13h
0x1800014f0  jmp     loc_180001707
0x1800014f5  mov     [rdi+8], rbx
0x1800014f9  add     [rbx+68h], r11d
0x1800014fd  mov     rcx, [rsp+138h+var_D0]
0x180001502  call    sqlite3_mutex_leave
0x180001507  mov     rcx, r14
0x18000150a  call    sqlite3_free
0x18000150f  test    rbx, rbx
0x180001512  jnz     loc_18000174D
0x180001518  mov     r14, [rsp+138h+var_E0]
0x18000151d  mov     r12d, dword ptr [rsp+138h+var_F0]
0x180001522  mov     rsi, [rsp+138h+var_E8]
0x180001527  xor     eax, eax
0x180001529  mov     ecx, 98h; Size
0x18000152e  mov     [rsp+138h+var_B8], rax
0x180001536  call    sqlite3MallocZero
0x18000153b  mov     rbx, rax
0x18000153e  test    rax, rax
0x180001541  jnz     short loc_180001552
0x180001543  mov     r14, [rsp+138h+var_F8]
0x180001548  lea     esi, [rax+7]
0x18000154b  xor     ebp, ebp
0x18000154d  jmp     loc_1800016E0
0x180001552  mov     [rsp+138h+var_110], ebp
0x180001556  mov     r8, r15
0x180001559  mov     rdx, rbx
0x18000155c  mov     [rsp+138h+var_118], r12d
0x180001561  mov     rcx, rsi
0x180001564  call    sqlite3PagerOpen
0x180001569  xor     ebp, ebp
0x18000156b  mov     esi, eax
0x18000156d  test    eax, eax
0x18000156f  jnz     loc_1800016CC
0x180001575  mov     rcx, [rbx]
0x180001578  mov     rax, [r14+40h]
0x18000157c  mov     [rcx+0A0h], rax
0x180001583  call    pagerFixMaplimit
0x180001588  mov     rcx, [rbx]
0x18000158b  lea     r8, [rsp+138h+var_C8]
0x180001590  call    sqlite3PagerReadFileheader
0x180001595  mov     esi, eax
0x180001597  test    eax, eax
0x180001599  jnz     loc_1800016CC
0x18000159f  mov     rcx, [rbx]
0x1800015a2  lea     rax, btreeInvokeBusyHandler
0x1800015a9  mov     [rbx+20h], r12b
0x1800015ad  lea     edx, [rbp+0Fh]
0x1800015b0  mov     [rbx+8], r14
0x1800015b4  lea     r8, [rcx+0E8h]
0x1800015bb  mov     [rcx+0F0h], rbx
0x1800015c2  mov     rcx, [rcx+48h]
0x1800015c6  mov     [r8], rax
0x1800015c9  call    sqlite3OsFileControlHint
0x1800015ce  mov     [rdi+8], rbx
0x1800015d2  mov     r9, [rbx]
0x1800015d5  mov     [rbx+10h], rbp
0x1800015d9  mov     [rbx+18h], rbp
0x1800015dd  cmp     [r9+12h], bpl
0x1800015e1  jz      short loc_1800015EA
0x1800015e3  lea     eax, [rbp+1]
0x1800015e6  or      [rbx+28h], ax
0x1800015ea  movzx   eax, byte ptr [rsp+138h+var_B8]
0x1800015f2  lea     r14, [rbx+34h]
0x1800015f6  movzx   ecx, byte ptr [rsp+138h+var_B8+1]
0x1800015fe  shl     ecx, 8
0x180001601  or      ecx, eax
0x180001603  shl     ecx, 8
0x180001606  mov     [r14], ecx
0x180001609  lea     eax, [rcx-200h]
0x18000160f  cmp     eax, 0FE00h
0x180001614  ja      short loc_180001653
0x180001616  lea     eax, [rcx-1]
0x180001619  test    ecx, eax
0x18000161b  jnz     short loc_180001653
0x18000161d  mov     cl, byte ptr [rsp+138h+var_B8+4]
0x180001624  mov     r15d, 2
0x18000162a  or      [rbx+28h], r15w
0x18000162f  mov     eax, [rsp+138h+var_94]
0x180001636  bswap   eax
0x180001638  test    eax, eax
0x18000163a  setnz   al
0x18000163d  mov     [rbx+21h], al
0x180001640  mov     eax, [rsp+138h+var_88]
0x180001647  bswap   eax
0x180001649  test    eax, eax
0x18000164b  setnz   al
0x18000164e  mov     [rbx+22h], al
0x180001651  jmp     short loc_18000166D
0x180001653  mov     [r14], ebp
0x180001656  test    r15, r15
0x180001659  jz      short loc_180001664
0x18000165b  test    r13d, r13d
0x18000165e  jnz     short loc_180001664
0x180001660  mov     [rbx+21h], bp
0x180001664  mov     cl, bpl
0x180001667  mov     r15d, 2
0x18000166d  movzx   ebp, cl
0x180001670  mov     rdx, r14
0x180001673  mov     r8d, ebp
0x180001676  mov     rcx, r9
0x180001679  call    sqlite3PagerSetPagesize
0x18000167e  mov     esi, eax
0x180001680  test    eax, eax
0x180001682  jnz     short loc_1800016CA
0x180001684  mov     eax, [r14]
0x180001687  lea     r12, [rdi+11h]
0x18000168b  sub     eax, ebp
0x18000168d  mov     dword ptr [rbx+68h], 1
0x180001694  xor     ebp, ebp
0x180001696  mov     [rbx+38h], eax
0x180001699  cmp     [r12], bpl
0x18000169d  jz      loc_1800017DB
0x1800016a3  mov     ecx, r15d
0x1800016a6  call    sqlite3MutexAlloc
0x1800016ab  cmp     byte ptr cs:word_1800B5634, sil
0x1800016b2  mov     rbp, rax
0x1800016b5  jz      short loc_18000172B
0x1800016b7  xor     ecx, ecx
0x1800016b9  call    sqlite3MutexAlloc
0x1800016be  mov     [rbx+58h], rax
0x1800016c2  test    rax, rax
0x1800016c5  jnz     short loc_18000172B
0x1800016c7  lea     esi, [rax+7]
  ... truncated ...
```
