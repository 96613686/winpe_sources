# sqlite3BtreeOpen

- ea: `0x1800379c8`
- end: `0x180037f93`
- name: `sqlite3BtreeOpen`
- size: `1483`
- prototype: ``
- caller_count: `4`
- callee_count: `20`
- tags: `file_ops, loader_planting`

## callers

- `0x1800204f0`
- `0x180021aa0`
- `0x180053c70`
- `0x180086a20`

## callees

- `0x180012470`
- `0x180020d70`
- `0x18002b81c`
- `0x180034900`
- `0x1800379c8`
- `0x18003ede0`
- `0x180041688`
- `0x180042078`
- `0x180042500`
- `0x1800449f0`
- `0x18007acd8`
- `0x180086758`
- `0x180086bc8`
- `0x180086f94`
- `0x1800875d8`
- `0x180087bcc`
- `0x180087f90`
- `0x1800a6cb4`
- `0x1800a6d08`
- `0x1800a8010`

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
  __int64 v14; // rdx
  __int64 v15; // rdi
  int v17; // eax
  __int64 v18; // r8
  int v19; // edx
  __int64 v20; // rbx
  unsigned int v21; // esi
  _BYTE *v22; // r14
  _BYTE *v23; // r12
  unsigned int Fileheader; // esi
  __int64 *i; // rbx
  unsigned int v26; // eax
  int v27; // edx
  __int64 v28; // r8
  __int64 *v29; // rax
  __int64 v30; // r9
  __int64 *v31; // r14
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
  v15 = v13;
  if ( !v13 )
    return 7;
  *(_QWORD *)v13 = v7;
  v55 = 0;
  *(_BYTE *)(v13 + 16) = 0;
  *(_QWORD *)(v13 + 48) = v13;
  *(_DWORD *)(v13 + 56) = 1;
  if ( v10 || v11 && (v6 & 0x40) == 0 || (v6 & 0x20000) == 0 )
    goto LABEL_47;
  v17 = sqlite3Strlen30(a2, v14, 1);
  v19 = *(_DWORD *)(v9 + 8);
  v20 = v17;
  v21 = v19 + 1;
  if ( v19 + 1 <= v17 + 1 )
    v19 = v17;
  v22 = (_BYTE *)sqlite3Malloc(v18 + v19);
  v23 = (_BYTE *)(v15 + 17);
  *(_BYTE *)(v15 + 17) = 1;
  if ( v22 )
  {
    if ( v11 )
    {
      Fileheader = 0;
      memcpy_0(v22, a2, v20 + 1);
    }
    else
    {
      *v22 = 0;
      v26 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, _BYTE *))(a1 + 64))(a1, a2, v21, v22);
      Fileheader = v26;
      if ( v26 )
      {
        if ( v26 != 512 )
        {
          sqlite3_free(v22);
          goto LABEL_38;
        }
        Fileheader = 0;
      }
    }
    v55 = sqlite3MutexAlloc(4);
    sqlite3_mutex_enter(v55);
    v56 = sqlite3MutexAlloc(2);
    sqlite3_mutex_enter(v56);
    for ( i = (__int64 *)qword_1800C78D8; i; i = (__int64 *)i[14] )
    {
      if ( !strcmp(v22, *(const char **)(*i + 216)) && *(_QWORD *)*i == a1 )
      {
        v27 = *(_DWORD *)(a3 + 40);
        while ( --v27 >= 0 )
        {
          v28 = *(_QWORD *)(32LL * v27 + *(_QWORD *)(a3 + 32) + 8);
          if ( v28 && *(__int64 **)(v28 + 8) == i )
          {
            sqlite3_mutex_leave(v56);
            sqlite3_mutex_leave(v55);
            sqlite3_free(v22);
            sqlite3_free(v15);
            return 19;
          }
        }
        *(_QWORD *)(v15 + 8) = i;
        ++*((_DWORD *)i + 26);
        break;
      }
    }
    sqlite3_mutex_leave(v56);
    sqlite3_free(v22);
    if ( i )
      goto LABEL_73;
    v7 = a3;
    v12 = v52;
    v9 = a1;
LABEL_47:
    v58 = 0;
    v29 = (__int64 *)sqlite3MallocZero(0x98u);
    i = v29;
    if ( !v29 )
    {
      v31 = a4;
      Fileheader = 7;
      goto LABEL_68;
    }
    Fileheader = sqlite3PagerOpen(v9, v29, a2, v30, v12, v6, v50);
    if ( Fileheader )
      goto LABEL_65;
    *(_QWORD *)(*i + 160) = *(_QWORD *)(v7 + 64);
    pagerFixMaplimit();
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
    sqlite3OsFileControlHint(v35, 15);
    *(_QWORD *)(v15 + 8) = i;
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
    v23 = (_BYTE *)(v15 + 17);
    v41 = *v37 - v40;
    *((_DWORD *)i + 26) = 1;
    *((_DWORD *)i + 14) = v41;
    if ( !*(_BYTE *)(v15 + 17) )
    {
LABEL_89:
      v31 = a4;
      *a4 = v15;
      if ( !Fileheader )
      {
        if ( !sqlite3BtreeSchema(v15, 0, 0) )
          sqlite3BtreeSetCacheSize(v15, 4294965296LL);
        v49 = *(_QWORD **)(*i + 72);
        if ( *v49 )
          sqlite3OsFileControlHint(v49, 30);
        goto LABEL_69;
      }
      if ( !i )
      {
LABEL_68:
        sqlite3_free(i);
        sqlite3_free(v15);
        *v31 = 0;
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
    if ( (_BYTE)word_1800C6974 != (_BYTE)Fileheader )
    {
      v43 = sqlite3MutexAlloc(0);
      i[11] = v43;
      if ( !v43 )
      {
        Fileheader = 7;
LABEL_65:
        v31 = a4;
        goto LABEL_66;
      }
    }
    sqlite3_mutex_enter(v42);
    i[14] = qword_1800C78D8;
    qword_1800C78D8 = (__int64)i;
    sqlite3_mutex_leave(v42);
LABEL_73:
    if ( *v23 )
    {
      for ( j = 0; j < *(_DWORD *)(a3 + 40); ++j )
      {
        v45 = *(_QWORD *)(32LL * j + *(_QWORD *)(a3 + 32) + 8);
        if ( v45 && *(_BYTE *)(v45 + 17) )
        {
          while ( *(_QWORD *)(v45 + 40) )
            v45 = *(_QWORD *)(v45 + 40);
          v46 = *(_QWORD *)(v15 + 8);
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
            *(_QWORD *)(v15 + 32) = v48;
            *(_QWORD *)(v15 + 40) = v45;
            if ( v48 )
              *(_QWORD *)(v48 + 40) = v15;
            *(_QWORD *)(v45 + 32) = v15;
          }
          else
          {
            *(_QWORD *)(v15 + 32) = v45;
            *(_QWORD *)(v15 + 40) = 0;
            *(_QWORD *)(v45 + 40) = v15;
          }
          goto LABEL_89;
        }
      }
    }
    goto LABEL_89;
  }
  Fileheader = 7;
LABEL_38:
  sqlite3_free(v15);
  return Fileheader;
}

```

## disassembly

```asm
0x1800379c8  push    rbx
0x1800379ca  push    rbp
0x1800379cb  push    rsi
0x1800379cc  push    rdi
0x1800379cd  push    r12
0x1800379cf  push    r13
0x1800379d1  push    r14
0x1800379d3  push    r15
0x1800379d5  sub     rsp, 0F8h
0x1800379dc  mov     rax, cs:__security_cookie
0x1800379e3  xor     rax, rsp
0x1800379e6  mov     [rsp+138h+var_58], rax
0x1800379ee  mov     ebp, [rsp+138h+arg_28]
0x1800379f5  mov     r14, r8
0x1800379f8  mov     [rsp+138h+var_F8], r9
0x1800379fd  mov     r15, rdx
0x180037a00  mov     [rsp+138h+var_E0], r8
0x180037a05  mov     rsi, rcx
0x180037a08  mov     [rsp+138h+var_E8], rcx
0x180037a0d  mov     edi, 1
0x180037a12  test    rdx, rdx
0x180037a15  jz      short loc_180037A20
0x180037a17  cmp     byte ptr [rdx], 0
0x180037a1a  jz      short loc_180037A20
0x180037a1c  xor     ebx, ebx
0x180037a1e  jmp     short loc_180037A27
0x180037a20  mov     ebx, edi
0x180037a22  test    r15, r15
0x180037a25  jz      short loc_180037A3E
0x180037a27  lea     rdx, aMemory; ":memory:"
0x180037a2e  mov     rcx, r15; Str1
0x180037a31  call    strcmp_0
0x180037a36  test    eax, eax
0x180037a38  jz      short loc_180037A4F
0x180037a3a  test    ebx, ebx
0x180037a3c  jz      short loc_180037A45
0x180037a3e  cmp     byte ptr [r14+66h], 2
0x180037a43  jz      short loc_180037A4F
0x180037a45  test    bpl, bpl
0x180037a48  js      short loc_180037A4F
0x180037a4a  xor     r13d, r13d
0x180037a4d  jmp     short loc_180037A52
0x180037a4f  mov     r13d, edi
0x180037a52  mov     r12d, dword ptr [rsp+138h+arg_20]
0x180037a5a  or      r12d, 2
0x180037a5e  test    r13d, r13d
0x180037a61  cmovz   r12d, dword ptr [rsp+138h+arg_20]
0x180037a6a  mov     dword ptr [rsp+138h+var_F0], r12d
0x180037a6f  bt      ebp, 8
0x180037a73  jnb     short loc_180037A86
0x180037a75  test    r13d, r13d
0x180037a78  jnz     short loc_180037A7E
0x180037a7a  test    ebx, ebx
0x180037a7c  jz      short loc_180037A86
0x180037a7e  btr     ebp, 8
0x180037a82  bts     ebp, 9
0x180037a86  mov     ecx, 48h ; 'H'; Size
0x180037a8b  call    sqlite3MallocZero
0x180037a90  mov     rdi, rax
0x180037a93  test    rax, rax
0x180037a96  jnz     short loc_180037AA0
0x180037a98  lea     eax, [rdi+7]
0x180037a9b  jmp     loc_180037E63
0x180037aa0  xor     ecx, ecx
0x180037aa2  mov     [rax], r14
0x180037aa5  mov     [rsp+138h+var_D8], rcx
0x180037aaa  mov     [rax+10h], cl
0x180037aad  mov     [rax+30h], rdi
0x180037ab1  lea     r8d, [rcx+1]
0x180037ab5  mov     [rax+38h], r8d
0x180037ab9  test    ebx, ebx
0x180037abb  jnz     loc_180037C83
0x180037ac1  test    r13d, r13d
0x180037ac4  jz      short loc_180037AD0
0x180037ac6  test    bpl, 40h
0x180037aca  jz      loc_180037C83
0x180037ad0  bt      ebp, 11h
0x180037ad4  jnb     loc_180037C83
0x180037ada  mov     rcx, r15
0x180037add  call    sqlite3Strlen30
0x180037ae2  mov     edx, [rsi+8]
0x180037ae5  movsxd  rbx, eax
0x180037ae8  lea     esi, [rdx+1]
0x180037aeb  lea     ecx, [rbx+1]
0x180037aee  cmp     esi, ecx
0x180037af0  cmovle  edx, ebx
0x180037af3  movsxd  rcx, edx
0x180037af6  add     rcx, r8
0x180037af9  call    sqlite3Malloc
0x180037afe  mov     r14, rax
0x180037b01  lea     r12, [rdi+11h]
0x180037b05  mov     eax, 1
0x180037b0a  mov     [r12], al
0x180037b0e  test    r14, r14
0x180037b11  jnz     short loc_180037B1B
0x180037b13  lea     esi, [rax+6]
0x180037b16  jmp     loc_180037BEB
0x180037b1b  mov     rdx, r15; Src
0x180037b1e  test    r13d, r13d
0x180037b21  jz      loc_180037BB0
0x180037b27  xor     esi, esi
0x180037b29  lea     r8, [rax+rbx]; Size
0x180037b2d  mov     rcx, r14; void *
0x180037b30  call    memcpy_0
0x180037b35  mov     ecx, 4
0x180037b3a  call    sqlite3MutexAlloc
0x180037b3f  mov     rcx, rax
0x180037b42  mov     [rsp+138h+var_D8], rax
0x180037b47  call    sqlite3_mutex_enter
0x180037b4c  mov     ecx, 2
0x180037b51  call    sqlite3MutexAlloc
0x180037b56  mov     rcx, rax
0x180037b59  mov     [rsp+138h+var_D0], rax
0x180037b5e  call    sqlite3_mutex_enter
0x180037b63  mov     r10, [rsp+138h+var_E8]
0x180037b68  mov     rbx, cs:qword_1800C78D8
0x180037b6f  test    rbx, rbx
0x180037b72  jz      loc_180037C59
0x180037b78  mov     r9, [rbx]
0x180037b7b  mov     rcx, r14
0x180037b7e  mov     r11d, 1
0x180037b84  mov     r8, [r9+0D8h]
0x180037b8b  sub     r8, r14
0x180037b8e  movzx   edx, byte ptr [rcx]
0x180037b91  movzx   eax, byte ptr [rcx+r8]
0x180037b96  sub     edx, eax
0x180037b98  jnz     short loc_180037BA1
0x180037b9a  add     rcx, r11
0x180037b9d  test    eax, eax
0x180037b9f  jnz     short loc_180037B8E
0x180037ba1  test    edx, edx
0x180037ba3  jnz     short loc_180037BAA
0x180037ba5  cmp     [r9], r10
0x180037ba8  jz      short loc_180037BF8
0x180037baa  mov     rbx, [rbx+70h]
0x180037bae  jmp     short loc_180037B6F
0x180037bb0  mov     rax, [rsp+138h+var_E8]
0x180037bb5  mov     r9, r14
0x180037bb8  mov     byte ptr [r14], 0
0x180037bbc  mov     rcx, rax
0x180037bbf  mov     r8d, esi
0x180037bc2  mov     rax, [rax+40h]
0x180037bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037bcb  mov     esi, eax
0x180037bcd  test    eax, eax
0x180037bcf  jz      loc_180037B35
0x180037bd5  cmp     eax, 200h
0x180037bda  jnz     short loc_180037BE3
0x180037bdc  xor     esi, esi
0x180037bde  jmp     loc_180037B35
0x180037be3  mov     rcx, r14
0x180037be6  call    sqlite3_free
0x180037beb  mov     rcx, rdi
0x180037bee  call    sqlite3_free
0x180037bf3  jmp     loc_180037E61
0x180037bf8  mov     r9, [rsp+138h+var_E0]
0x180037bfd  mov     edx, [r9+28h]
0x180037c01  sub     edx, r11d
0x180037c04  test    edx, edx
0x180037c06  js      short loc_180037C51
0x180037c08  mov     rax, [r9+20h]
0x180037c0c  movsxd  rcx, edx
0x180037c0f  shl     rcx, 5
0x180037c13  mov     r8, [rcx+rax+8]
0x180037c18  test    r8, r8
0x180037c1b  jz      short loc_180037C01
0x180037c1d  cmp     [r8+8], rbx
0x180037c21  jnz     short loc_180037C01
0x180037c23  mov     rcx, [rsp+138h+var_D0]
0x180037c28  call    sqlite3_mutex_leave
0x180037c2d  mov     rcx, [rsp+138h+var_D8]
0x180037c32  call    sqlite3_mutex_leave
0x180037c37  mov     rcx, r14
0x180037c3a  call    sqlite3_free
0x180037c3f  mov     rcx, rdi
0x180037c42  call    sqlite3_free
0x180037c47  mov     eax, 13h
0x180037c4c  jmp     loc_180037E63
0x180037c51  mov     [rdi+8], rbx
0x180037c55  add     [rbx+68h], r11d
0x180037c59  mov     rcx, [rsp+138h+var_D0]
0x180037c5e  call    sqlite3_mutex_leave
0x180037c63  mov     rcx, r14
0x180037c66  call    sqlite3_free
0x180037c6b  test    rbx, rbx
0x180037c6e  jnz     loc_180037EA9
0x180037c74  mov     r14, [rsp+138h+var_E0]
0x180037c79  mov     r12d, dword ptr [rsp+138h+var_F0]
0x180037c7e  mov     rsi, [rsp+138h+var_E8]
0x180037c83  xor     eax, eax
0x180037c85  mov     ecx, 98h; Size
0x180037c8a  mov     [rsp+138h+var_B8], rax
0x180037c92  call    sqlite3MallocZero
0x180037c97  mov     rbx, rax
0x180037c9a  test    rax, rax
0x180037c9d  jnz     short loc_180037CAE
0x180037c9f  mov     r14, [rsp+138h+var_F8]
0x180037ca4  lea     esi, [rax+7]
0x180037ca7  xor     ebp, ebp
0x180037ca9  jmp     loc_180037E3C
0x180037cae  mov     [rsp+138h+var_110], ebp
0x180037cb2  mov     r8, r15
0x180037cb5  mov     rdx, rbx
0x180037cb8  mov     [rsp+138h+var_118], r12d
0x180037cbd  mov     rcx, rsi
0x180037cc0  call    sqlite3PagerOpen
0x180037cc5  xor     ebp, ebp
0x180037cc7  mov     esi, eax
0x180037cc9  test    eax, eax
0x180037ccb  jnz     loc_180037E28
0x180037cd1  mov     rcx, [rbx]
0x180037cd4  mov     rax, [r14+40h]
0x180037cd8  mov     [rcx+0A0h], rax
0x180037cdf  call    pagerFixMaplimit
0x180037ce4  mov     rcx, [rbx]
0x180037ce7  lea     r8, [rsp+138h+var_C8]
0x180037cec  call    sqlite3PagerReadFileheader
0x180037cf1  mov     esi, eax
0x180037cf3  test    eax, eax
0x180037cf5  jnz     loc_180037E28
0x180037cfb  mov     rcx, [rbx]
0x180037cfe  lea     rax, btreeInvokeBusyHandler
0x180037d05  mov     [rbx+20h], r12b
0x180037d09  lea     edx, [rbp+0Fh]
0x180037d0c  mov     [rbx+8], r14
0x180037d10  lea     r8, [rcx+0E8h]
0x180037d17  mov     [rcx+0F0h], rbx
0x180037d1e  mov     rcx, [rcx+48h]
0x180037d22  mov     [r8], rax
0x180037d25  call    sqlite3OsFileControlHint
0x180037d2a  mov     [rdi+8], rbx
0x180037d2e  mov     r9, [rbx]
0x180037d31  mov     [rbx+10h], rbp
0x180037d35  mov     [rbx+18h], rbp
0x180037d39  cmp     [r9+12h], bpl
0x180037d3d  jz      short loc_180037D46
0x180037d3f  lea     eax, [rbp+1]
0x180037d42  or      [rbx+28h], ax
0x180037d46  movzx   eax, byte ptr [rsp+138h+var_B8]
0x180037d4e  lea     r14, [rbx+34h]
0x180037d52  movzx   ecx, byte ptr [rsp+138h+var_B8+1]
0x180037d5a  shl     ecx, 8
0x180037d5d  or      ecx, eax
0x180037d5f  shl     ecx, 8
0x180037d62  mov     [r14], ecx
0x180037d65  lea     eax, [rcx-200h]
0x180037d6b  cmp     eax, 0FE00h
0x180037d70  ja      short loc_180037DAF
0x180037d72  lea     eax, [rcx-1]
0x180037d75  test    ecx, eax
0x180037d77  jnz     short loc_180037DAF
0x180037d79  mov     cl, byte ptr [rsp+138h+var_B8+4]
0x180037d80  mov     r15d, 2
0x180037d86  or      [rbx+28h], r15w
0x180037d8b  mov     eax, [rsp+138h+var_94]
0x180037d92  bswap   eax
0x180037d94  test    eax, eax
0x180037d96  setnz   al
0x180037d99  mov     [rbx+21h], al
0x180037d9c  mov     eax, [rsp+138h+var_88]
0x180037da3  bswap   eax
0x180037da5  test    eax, eax
0x180037da7  setnz   al
0x180037daa  mov     [rbx+22h], al
0x180037dad  jmp     short loc_180037DC9
0x180037daf  mov     [r14], ebp
0x180037db2  test    r15, r15
0x180037db5  jz      short loc_180037DC0
0x180037db7  test    r13d, r13d
0x180037dba  jnz     short loc_180037DC0
0x180037dbc  mov     [rbx+21h], bp
0x180037dc0  mov     cl, bpl
0x180037dc3  mov     r15d, 2
0x180037dc9  movzx   ebp, cl
0x180037dcc  mov     rdx, r14
0x180037dcf  mov     r8d, ebp
0x180037dd2  mov     rcx, r9
0x180037dd5  call    sqlite3PagerSetPagesize
0x180037dda  mov     esi, eax
0x180037ddc  test    eax, eax
0x180037dde  jnz     short loc_180037E26
0x180037de0  mov     eax, [r14]
0x180037de3  lea     r12, [rdi+11h]
0x180037de7  sub     eax, ebp
0x180037de9  mov     dword ptr [rbx+68h], 1
0x180037df0  xor     ebp, ebp
0x180037df2  mov     [rbx+38h], eax
0x180037df5  cmp     [r12], bpl
0x180037df9  jz      loc_180037F37
0x180037dff  mov     ecx, r15d
0x180037e02  call    sqlite3MutexAlloc
0x180037e07  cmp     byte ptr cs:word_1800C6974, sil
0x180037e0e  mov     rbp, rax
0x180037e11  jz      short loc_180037E87
0x180037e13  xor     ecx, ecx
0x180037e15  call    sqlite3MutexAlloc
0x180037e1a  mov     [rbx+58h], rax
0x180037e1e  test    rax, rax
0x180037e21  jnz     short loc_180037E87
0x180037e23  lea     esi, [rax+7]
  ... truncated ...
```
