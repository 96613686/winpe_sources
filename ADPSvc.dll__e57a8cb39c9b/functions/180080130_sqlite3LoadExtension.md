# sqlite3LoadExtension

- ea: `0x180080130`
- end: `0x1800805bc`
- name: `sqlite3LoadExtension`
- size: `1164`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800aa330`

## callees

- `0x1800034f2`
- `0x1800716fc`
- `0x1800718ac`
- `0x180080130`
- `0x1800a98a0`
- `0x1800aa490`
- `0x1800aa540`
- `0x1800abbf0`
- `0x1800ada30`
- `0x1800ca010`

## string_xrefs

- `0x1800801a3`: `sqlite3_extension_init`
- `0x18008057f`: `unable to open shared library [%.*s]`
- `0x1800804ab`: `error during initialization: %s`

## pseudocode

```c
__int64 __fastcall sqlite3LoadExtension(__int64 *a1, const char *a2, const char *a3, const char **a4)
{
  __int64 v4; // rdi
  __int64 v8; // r15
  const char *v9; // r14
  __int64 v10; // r13
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rax
  _QWORD *v15; // r15
  int v16; // r14d
  __int64 v17; // r14
  int v19; // eax
  int v20; // r8d
  int v21; // edx
  unsigned int i; // ecx
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rcx
  int v26; // ebx
  const char *v27; // rax
  int v28; // eax
  void *v29; // rdi
  __int64 v30; // rax
  __int64 v31; // rax
  const char *v32; // rax
  __int64 v33; // [rsp+30h] [rbp-58h]
  __int64 v34; // [rsp+38h] [rbp-50h]
  __int64 v35; // [rsp+40h] [rbp-48h]
  int v36; // [rsp+90h] [rbp+8h]
  __int64 (__fastcall *v37)(__int64 *, const char **, __int64 (__fastcall **)()); // [rsp+90h] [rbp+8h]
  const char *v39; // [rsp+A8h] [rbp+20h] BYREF

  v4 = *a1;
  v39 = 0;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  v35 = v8;
  if ( a4 )
    *a4 = 0;
  if ( (a1[6] & 0x10000) != 0 )
  {
    v9 = a3;
    if ( !a3 )
      v9 = "sqlite3_extension_init";
    if ( (unsigned __int64)(v8 - 1) > 0x103 )
    {
LABEL_59:
      if ( a4 )
      {
        v32 = (const char *)sqlite3_malloc64(v8 + 300);
        v39 = v32;
        *a4 = v32;
        if ( v32 )
        {
          sqlite3_snprintf((unsigned int)(v8 + 300), v32, "unable to open shared library [%.*s]", 260, a2);
          (*(void (__fastcall **)(__int64, _QWORD, const char *))(v4 + 80))(v4, (unsigned int)(v8 + 299), v39);
        }
      }
      return 1;
    }
    v10 = (*(__int64 (__fastcall **)(__int64))(v4 + 72))(v4);
    v11 = 0;
    v36 = 0;
    while ( !v10 )
    {
      v33 = v11;
      v34 = sqlite3_mprintf("%s.%s", a2, off_1800CC978[v11]);
      v12 = v34;
      if ( !v34 )
        return 7;
      v13 = -1;
      do
        ++v13;
      while ( off_1800CC978[v33][v13] );
      if ( (unsigned __int64)(v13 + v8 + 1) <= 0x104 )
      {
        v14 = (*(__int64 (__fastcall **)(__int64, __int64))(v4 + 72))(v4, v34);
        v12 = v34;
        v10 = v14;
      }
      sqlite3_free(v12);
      v11 = (unsigned int)(v36 + 1);
      v36 = v11;
      if ( (int)v11 >= 1 )
      {
        if ( !v10 )
          goto LABEL_59;
        break;
      }
    }
    v15 = 0;
    v37 = (__int64 (__fastcall *)(__int64 *, const char **, __int64 (__fastcall **)()))(*(__int64 (__fastcall **)(__int64, __int64, const char *))(v4 + 88))(
                                                                                         v4,
                                                                                         v10,
                                                                                         v9);
    if ( !v37 )
    {
      if ( a3 )
        goto LABEL_41;
      if ( a2 )
      {
        v17 = -1;
        do
          ++v17;
        while ( a2[v17] );
        v16 = v17 & 0x3FFFFFFF;
      }
      else
      {
        v16 = 0;
      }
      v15 = (_QWORD *)sqlite3_malloc64((unsigned int)(v16 + 30));
      if ( !v15 )
      {
        (*(void (__fastcall **)(__int64, __int64))(v4 + 96))(v4, v10);
        return 7;
      }
      *v15 = 0x5F336574696C7173LL;
      do
        --v16;
      while ( v16 >= 0 && a2[v16] != 47 && a2[v16] != 92 );
      v19 = sqlite3_strnicmp(&a2[v16 + 1], "lib", 3);
      v20 = 8;
      v21 = v16 + (v19 != 0 ? 1 : 4);
      for ( i = a2[v21]; a2[v21]; i = a2[++v21] )
      {
        if ( i == 46 )
          break;
        if ( (*((_BYTE *)&qword_1800FB500 + (unsigned __int8)i) & 2) != 0 )
        {
          v23 = i;
          v24 = v20++;
          *((_BYTE *)v15 + v24) = *((_BYTE *)qword_1800FBAB0 + v23);
        }
      }
      strcpy((char *)v15 + v20, "_init");
      v37 = (__int64 (__fastcall *)(__int64 *, const char **, __int64 (__fastcall **)()))(*(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(v4 + 88))(
                                                                                           v4,
                                                                                           v10,
                                                                                           v15);
      if ( !v37 )
      {
        v9 = (const char *)v15;
LABEL_41:
        if ( a4 )
        {
          v25 = -1;
          do
            ++v25;
          while ( v9[v25] );
          v26 = v25 + v35;
          v27 = (const char *)sqlite3_malloc64(v25 + v35 + 300);
          v39 = v27;
          *a4 = v27;
          if ( v27 )
          {
            sqlite3_snprintf((unsigned int)(v26 + 300), v27, "no entry point [%s] in shared library [%s]", v9, a2);
            (*(void (__fastcall **)(__int64, _QWORD, const char *))(v4 + 80))(v4, (unsigned int)(v26 + 299), v39);
          }
        }
        (*(void (__fastcall **)(__int64, __int64))(v4 + 96))(v4, v10);
        sqlite3_free(v15);
        return 1;
      }
    }
    sqlite3_free(v15);
    v28 = v37(a1, &v39, off_1800CBC50);
    if ( v28 )
    {
      if ( v28 != 256 )
      {
        if ( a4 )
          *a4 = (const char *)sqlite3_mprintf("error during initialization: %s", v39);
        sqlite3_free(v39);
        (*(void (__fastcall **)(__int64, __int64))(v4 + 96))(v4, v10);
        return 1;
      }
    }
    else
    {
      v29 = (void *)sqlite3DbMallocZero(a1, 8LL * *((int *)a1 + 59) + 8);
      if ( !v29 )
        return 7;
      v30 = *((int *)a1 + 59);
      if ( (int)v30 > 0 )
        memcpy_0(v29, (const void *)a1[30], 8 * v30);
      if ( a1[30] )
        sqlite3DbFreeNN(a1);
      v31 = *((int *)a1 + 59);
      a1[30] = (__int64)v29;
      *((_QWORD *)v29 + v31) = v10;
      ++*((_DWORD *)a1 + 59);
    }
    return 0;
  }
  if ( a4 )
    *a4 = (const char *)sqlite3_mprintf("not authorized");
  return 1;
}

```

## disassembly

```asm
0x180080130  mov     rax, rsp
0x180080133  mov     [rax+18h], r8
0x180080137  push    rbx
0x180080138  push    rsi
0x180080139  push    rdi
0x18008013a  push    r12
0x18008013c  push    r13
0x18008013e  push    r14
0x180080140  push    r15
0x180080142  sub     rsp, 50h
0x180080146  mov     rdi, [rcx]
0x180080149  mov     rsi, r9
0x18008014c  mov     r12, rdx
0x18008014f  mov     qword ptr [rax+20h], 0
0x180080157  mov     rbx, rcx
0x18008015a  or      r15, 0FFFFFFFFFFFFFFFFh
0x18008015e  inc     r15
0x180080161  cmp     byte ptr [rdx+r15], 0
0x180080166  jnz     short loc_18008015E
0x180080168  mov     [rsp+88h+var_48], r15
0x18008016d  test    rsi, rsi
0x180080170  jz      short loc_180080179
0x180080172  mov     qword ptr [r9], 0
0x180080179  mov     eax, [rcx+30h]
0x18008017c  bt      rax, 10h
0x180080181  jb      short loc_1800801A0
0x180080183  test    rsi, rsi
0x180080186  jz      loc_1800805A7
0x18008018c  lea     rcx, aNotAuthorized; "not authorized"
0x180080193  call    sqlite3_mprintf
0x180080198  mov     [rsi], rax
0x18008019b  jmp     loc_1800805A7
0x1800801a0  test    r8, r8
0x1800801a3  lea     rax, aSqlite3Extensi; "sqlite3_extension_init"
0x1800801aa  mov     r14, r8
0x1800801ad  cmovz   r14, rax
0x1800801b1  lea     rax, [r15-1]
0x1800801b5  cmp     rax, 103h
0x1800801bb  ja      loc_180080550
0x1800801c1  mov     rax, [rdi+48h]
0x1800801c5  mov     rcx, rdi
0x1800801c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800801cd  mov     r13, rax
0x1800801d0  xor     eax, eax
0x1800801d2  mov     dword ptr [rsp+88h+arg_0], eax
0x1800801d9  lea     rcx, cs:180000000h
0x1800801e0  test    r13, r13
0x1800801e3  jnz     loc_180080285
0x1800801e9  mov     r8, ds:rva off_1800CC978[rcx+rax*8]; "dll" ...
0x1800801f1  mov     rdx, r12
0x1800801f4  lea     rcx, aSS_3; "%s.%s"
0x1800801fb  mov     [rsp+88h+var_58], rax
0x180080200  call    sqlite3_mprintf
0x180080205  mov     [rsp+88h+var_50], rax
0x18008020a  mov     rdx, rax
0x18008020d  test    rax, rax
0x180080210  jz      loc_1800802F7
0x180080216  mov     rax, [rsp+88h+var_58]
0x18008021b  lea     r8, cs:180000000h
0x180080222  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180080226  mov     r8, ds:rva off_1800CC978[r8+rax*8]; "dll" ...
0x18008022e  inc     rcx
0x180080231  cmp     byte ptr [r8+rcx], 0
0x180080236  jnz     short loc_18008022E
0x180080238  lea     rax, [r15+1]
0x18008023c  add     rax, rcx
0x18008023f  cmp     rax, 104h
0x180080245  ja      short loc_18008025B
0x180080247  mov     rax, [rdi+48h]
0x18008024b  mov     rcx, rdi
0x18008024e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080253  mov     rdx, [rsp+88h+var_50]
0x180080258  mov     r13, rax
0x18008025b  mov     rcx, rdx
0x18008025e  call    sqlite3_free
0x180080263  mov     eax, dword ptr [rsp+88h+arg_0]
0x18008026a  inc     eax
0x18008026c  mov     dword ptr [rsp+88h+arg_0], eax
0x180080273  cmp     eax, 1
0x180080276  jl      loc_1800801D9
0x18008027c  test    r13, r13
0x18008027f  jz      loc_180080550
0x180080285  mov     rax, [rdi+58h]
0x180080289  mov     r8, r14
0x18008028c  mov     rdx, r13
0x18008028f  mov     rcx, rdi
0x180080292  xor     r15d, r15d
0x180080295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008029a  mov     [rsp+88h+arg_0], rax
0x1800802a2  test    rax, rax
0x1800802a5  jnz     loc_180080465
0x1800802ab  cmp     [rsp+88h+arg_10], r15
0x1800802b3  jnz     loc_1800803DB
0x1800802b9  test    r12, r12
0x1800802bc  jnz     short loc_1800802C3
0x1800802be  xor     r14d, r14d
0x1800802c1  jmp     short loc_1800802D7
0x1800802c3  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800802c7  inc     r14
0x1800802ca  cmp     [r12+r14], r15b
0x1800802ce  jnz     short loc_1800802C7
0x1800802d0  and     r14d, 3FFFFFFFh
0x1800802d7  lea     ecx, [r14+1Eh]
0x1800802db  call    sqlite3_malloc64
0x1800802e0  mov     r15, rax
0x1800802e3  test    rax, rax
0x1800802e6  jnz     short loc_180080301
0x1800802e8  mov     rax, [rdi+60h]
0x1800802ec  mov     rdx, r13
0x1800802ef  mov     rcx, rdi
0x1800802f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800802f7  mov     eax, 7
0x1800802fc  jmp     loc_1800805AC
0x180080301  mov     rax, 5F336574696C7173h
0x18008030b  mov     [r15], rax
0x18008030e  jmp     short loc_18008031E
0x180080310  cmp     byte ptr [r14+r12], 2Fh ; '/'
0x180080315  jz      short loc_180080324
0x180080317  cmp     byte ptr [r14+r12], 5Ch ; '\'
0x18008031c  jz      short loc_180080324
0x18008031e  sub     r14d, 1
0x180080322  jns     short loc_180080310
0x180080324  lea     eax, [r14+1]
0x180080328  mov     r8d, 3
0x18008032e  movsxd  rcx, eax
0x180080331  lea     rdx, aLib; "lib"
0x180080338  add     rcx, r12
0x18008033b  call    sqlite3_strnicmp
0x180080340  neg     eax
0x180080342  mov     r8d, 8
0x180080348  sbb     ecx, ecx
0x18008034a  and     ecx, 0FFFFFFFDh
0x18008034d  lea     edx, [rcx+4]
0x180080350  add     edx, r14d
0x180080353  movsxd  rax, edx
0x180080356  movsx   ecx, byte ptr [rax+r12]
0x18008035b  test    ecx, ecx
0x18008035d  jz      short loc_18008039B
0x18008035f  lea     r9, cs:180000000h
0x180080366  cmp     ecx, 2Eh ; '.'
0x180080369  jz      short loc_18008039B
0x18008036b  movzx   eax, cl
0x18008036e  test    byte ptr [rax+r9+0FB500h], 2
0x180080377  jz      short loc_18008038D
0x180080379  mov     eax, ecx
0x18008037b  movsxd  rcx, r8d
0x18008037e  inc     r8d
0x180080381  mov     al, [rax+r9+0FBAB0h]
0x180080389  mov     [rcx+r15], al
0x18008038d  inc     edx
0x18008038f  movsxd  rax, edx
0x180080392  movsx   ecx, byte ptr [rax+r12]
0x180080397  test    ecx, ecx
0x180080399  jnz     short loc_180080366
0x18008039b  mov     eax, dword ptr cs:aInit; "_init"
0x1800803a1  mov     rdx, r13
0x1800803a4  movsxd  rcx, r8d
0x1800803a7  mov     r8, r15
0x1800803aa  mov     [rcx+r15], eax
0x1800803ae  movzx   eax, word ptr cs:aInit+4; "t"
0x1800803b5  mov     [rcx+r15+4], ax
0x1800803bb  mov     rcx, rdi
0x1800803be  mov     rax, [rdi+58h]
0x1800803c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800803c7  mov     [rsp+88h+arg_0], rax
0x1800803cf  test    rax, rax
0x1800803d2  jnz     loc_180080465
0x1800803d8  mov     r14, r15
0x1800803db  test    rsi, rsi
0x1800803de  jz      short loc_180080449
0x1800803e0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800803e4  inc     rcx
0x1800803e7  cmp     byte ptr [r14+rcx], 0
0x1800803ec  jnz     short loc_1800803E4
0x1800803ee  mov     rbx, [rsp+88h+var_48]
0x1800803f3  add     rbx, rcx
0x1800803f6  lea     rcx, [rbx+12Ch]
0x1800803fd  call    sqlite3_malloc64
0x180080402  mov     [rsp+88h+arg_18], rax
0x18008040a  mov     [rsi], rax
0x18008040d  test    rax, rax
0x180080410  jz      short loc_180080449
0x180080412  mov     r9, r14
0x180080415  mov     [rsp+88h+var_68], r12
0x18008041a  lea     r8, aNoEntryPointSI; "no entry point [%s] in shared library ["...
0x180080421  mov     rdx, rax
0x180080424  lea     ecx, [rbx+12Ch]
0x18008042a  call    sqlite3_snprintf
0x18008042f  mov     r8, [rsp+88h+arg_18]
0x180080437  lea     edx, [rbx+12Bh]
0x18008043d  mov     rax, [rdi+50h]
0x180080441  mov     rcx, rdi
0x180080444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080449  mov     rax, [rdi+60h]
0x18008044d  mov     rdx, r13
0x180080450  mov     rcx, rdi
0x180080453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080458  mov     rcx, r15
0x18008045b  call    sqlite3_free
0x180080460  jmp     loc_1800805A7
0x180080465  mov     rcx, r15
0x180080468  call    sqlite3_free
0x18008046d  mov     rax, [rsp+88h+arg_0]
0x180080475  lea     r8, off_1800CBC50
0x18008047c  lea     rdx, [rsp+88h+arg_18]
0x180080484  mov     rcx, rbx
0x180080487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008048c  test    eax, eax
0x18008048e  jz      short loc_1800804DB
0x180080490  cmp     eax, 100h
0x180080495  jnz     short loc_18008049E
0x180080497  xor     eax, eax
0x180080499  jmp     loc_1800805AC
0x18008049e  test    rsi, rsi
0x1800804a1  jz      short loc_1800804BA
0x1800804a3  mov     rdx, [rsp+88h+arg_18]
0x1800804ab  lea     rcx, aErrorDuringIni; "error during initialization: %s"
0x1800804b2  call    sqlite3_mprintf
0x1800804b7  mov     [rsi], rax
0x1800804ba  mov     rcx, [rsp+88h+arg_18]
0x1800804c2  call    sqlite3_free
0x1800804c7  mov     rax, [rdi+60h]
0x1800804cb  mov     rdx, r13
0x1800804ce  mov     rcx, rdi
0x1800804d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800804d6  jmp     loc_1800805A7
0x1800804db  movsxd  rdx, dword ptr [rbx+0ECh]
0x1800804e2  mov     rcx, rbx
0x1800804e5  lea     rdx, ds:8[rdx*8]
0x1800804ed  call    sqlite3DbMallocZero
0x1800804f2  mov     rdi, rax
0x1800804f5  test    rax, rax
0x1800804f8  jz      loc_1800802F7
0x1800804fe  movsxd  rax, dword ptr [rbx+0ECh]
0x180080505  test    eax, eax
0x180080507  jle     short loc_18008051F
0x180080509  mov     rdx, [rbx+0F0h]; Src
0x180080510  mov     r8, rax
0x180080513  shl     r8, 3; Size
0x180080517  mov     rcx, rdi; void *
0x18008051a  call    memcpy_0
0x18008051f  mov     rdx, [rbx+0F0h]
0x180080526  test    rdx, rdx
0x180080529  jz      short loc_180080533
0x18008052b  mov     rcx, rbx
0x18008052e  call    sqlite3DbFreeNN
0x180080533  movsxd  rax, dword ptr [rbx+0ECh]
0x18008053a  mov     [rbx+0F0h], rdi
0x180080541  mov     [rdi+rax*8], r13
0x180080545  inc     dword ptr [rbx+0ECh]
0x18008054b  jmp     loc_180080497
0x180080550  test    rsi, rsi
0x180080553  jz      short loc_1800805A7
0x180080555  lea     rbx, [r15+12Ch]
0x18008055c  mov     rcx, rbx
0x18008055f  call    sqlite3_malloc64
0x180080564  mov     [rsp+88h+arg_18], rax
0x18008056c  mov     [rsi], rax
0x18008056f  test    rax, rax
0x180080572  jz      short loc_1800805A7
0x180080574  mov     r9d, 104h
0x18008057a  mov     [rsp+88h+var_68], r12
0x18008057f  lea     r8, aUnableToOpenSh; "unable to open shared library [%.*s]"
0x180080586  mov     rdx, rax
0x180080589  mov     ecx, ebx
0x18008058b  call    sqlite3_snprintf
0x180080590  mov     r8, [rsp+88h+arg_18]
0x180080598  lea     edx, [rbx-1]
0x18008059b  mov     rax, [rdi+50h]
0x18008059f  mov     rcx, rdi
0x1800805a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800805a7  mov     eax, 1
0x1800805ac  add     rsp, 50h
0x1800805b0  pop     r15
0x1800805b2  pop     r14
0x1800805b4  pop     r13
0x1800805b6  pop     r12
0x1800805b8  pop     rdi
0x1800805b9  pop     rsi
0x1800805ba  pop     rbx
0x1800805bb  retn
```
