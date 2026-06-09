# sqlite3PagerOpen

- ea: `0x18003405c`
- end: `0x18003464a`
- name: `sqlite3PagerOpen`
- size: `1518`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180035d1c`

## callees

- `0x18000e818`
- `0x18001eb90`
- `0x18001fda8`
- `0x18002619c`
- `0x18003338c`
- `0x18003342c`
- `0x1800335cc`
- `0x18003405c`
- `0x180035c7c`
- `0x1800375e4`
- `0x180039ba0`
- `0x18003c510`
- `0x18003f4fc`
- `0x180041d10`
- `0x180041eb0`
- `0x18006ae48`
- `0x18006f6f0`
- `0x1800766a4`
- `0x1800af620`
- `0x1800b0010`

## string_xrefs

- `0x180034172`: `cannot open file`

## pseudocode

```c
__int64 __fastcall sqlite3PagerOpen(__int64 a1, __int64 *a2, _BYTE *a3, __int64 a4, __int64 a5, __int64 a6, __int64 a7)
{
  const void *v7; // r14
  int v8; // r12d
  _BYTE *v9; // rbp
  int v11; // edi
  int v12; // ebx
  bool v13; // zf
  int v14; // r15d
  unsigned int v15; // esi
  unsigned int v16; // ebx
  _BYTE *v17; // rax
  _BYTE *v18; // rax
  _BYTE *v19; // rbx
  __int64 result; // rax
  __int64 v21; // rax
  __int64 v22; // rdi
  __int64 v23; // rax
  unsigned __int64 v24; // rax
  unsigned __int64 v25; // rcx
  char *v26; // rax
  int v27; // ebp
  char v28; // bl
  char *v29; // rbx
  char *v30; // rbx
  char *v31; // rbx
  __int64 v32; // r8
  __int64 v33; // rdx
  __int64 (__fastcall *v34)(__int64, __int64, __int64, _QWORD, unsigned int *); // rax
  __int16 v35; // r14
  unsigned int v36; // ecx
  __int64 v37; // rbx
  __int64 v38; // rax
  __int64 v39; // rax
  char Boolean; // al
  __int64 v41; // rax
  __int64 v42; // rax
  int v43; // edx
  int v44; // r14d
  __int64 (__fastcall *v45)(); // r9
  char v46; // si
  unsigned __int8 v47; // al
  BOOL v48; // esi
  char v49; // bl
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rcx
  __int64 v53; // rax
  _BYTE *v54; // rcx
  signed int v55; // [rsp+30h] [rbp-58h]
  char *v56; // [rsp+30h] [rbp-58h]
  void *Src; // [rsp+38h] [rbp-50h]
  size_t Size; // [rsp+40h] [rbp-48h]
  unsigned int v59; // [rsp+90h] [rbp+8h] BYREF
  __int64 *v60; // [rsp+98h] [rbp+10h]
  int v61; // [rsp+A8h] [rbp+20h] BYREF

  v60 = a2;
  v61 = 4096;
  v7 = 0;
  LODWORD(a7) = 0;
  v8 = 0;
  v9 = a3;
  v11 = 80;
  v12 = 1;
  if ( *(int *)(a1 + 4) > 80 )
    v11 = *(_DWORD *)(a1 + 4);
  v13 = (a5 & 2) == 0;
  *a2 = 0;
  if ( !v13 )
  {
    LODWORD(a7) = 1;
    if ( a3 )
    {
      if ( *a3 )
      {
        v50 = sqlite3DbStrDup(0, a3);
        v7 = (const void *)v50;
        if ( !v50 )
          return 7;
        v8 = sqlite3Strlen30(v50);
        v9 = 0;
      }
    }
  }
  v14 = a6;
  v15 = 0;
  Src = 0;
  if ( !v9 || !*v9 )
    goto LABEL_14;
  v16 = *(_DWORD *)(a1 + 8) + 1;
  v17 = (_BYTE *)sqlite3Malloc((int)(2 * v16));
  v7 = v17;
  if ( !v17 )
    return 7;
  *v17 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, _BYTE *))(a1 + 64))(a1, v9, v16, v17);
  if ( v15 == 512 )
    v15 = (v14 & 0x1000000) != 0 ? 0x60E : 0;
  v8 = sqlite3Strlen30(v7);
  v18 = &v9[(int)sqlite3Strlen30(v9) + 1];
  Src = v18;
  v19 = v18;
  if ( *v18 )
  {
    do
    {
      v51 = -1;
      do
        ++v51;
      while ( v19[v51] );
      v52 = v51 + 1;
      v53 = -1;
      v54 = &v19[v52];
      do
        ++v53;
      while ( v54[v53] );
      v19 = &v54[v53 + 1];
    }
    while ( *v19 );
    LODWORD(v18) = (_DWORD)Src;
  }
  if ( v15 )
    goto LABEL_11;
  v12 = (_DWORD)v19 - (_DWORD)v18 + 1;
  if ( v8 + 8 > *(_DWORD *)(a1 + 8) )
  {
    v15 = sqlite3ReportError(14, 62088, "cannot open file");
    if ( v15 )
      goto LABEL_11;
  }
LABEL_14:
  v55 = (v11 + 7) & 0xFFFFFFF8;
  Size = v12;
  v21 = sqlite3MallocZero(3LL * v8 + ((*(int *)(a1 + 4) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL) + 454 + v12 + (__int64)(2 * v55));
  v22 = v21;
  if ( !v21 )
  {
    v15 = 7;
LABEL_11:
    sqlite3DbFree(0, v7);
    return v15;
  }
  v23 = v21 + 344;
  *(_QWORD *)(v22 + 320) = v23;
  v59 = 0;
  *(_QWORD *)(v22 + 72) = v23 + 80;
  v24 = v23 + 80 + ((*(int *)(a1 + 4) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL);
  *(_QWORD *)(v22 + 88) = v24;
  v25 = v24 + v55;
  *(_QWORD *)(v22 + 80) = v25;
  v26 = (char *)(v25 + v55 + 12LL);
  *(_QWORD *)(v55 + v25) = v22;
  v56 = v26;
  *(_QWORD *)(v22 + 216) = v26;
  if ( v8 > 0 )
  {
    memcpy_0(v26, v7, v8);
    v29 = &v56[v8 + 1];
    if ( Src )
    {
      memcpy_0(&v56[v8 + 1], Src, Size);
      v30 = &v29[Size];
    }
    else
    {
      v30 = v29 + 1;
    }
    *(_QWORD *)(v22 + 224) = v30;
    memcpy_0(v30, v7, v8);
    *(_QWORD *)&v30[v8] = 0x6C616E72756F6A2DLL;
    v31 = &v30[v8 + 9];
    *(_QWORD *)(v22 + 336) = v31;
    memcpy_0(v31, v7, v8);
    *(_DWORD *)&v31[v8] = 1818326829;
  }
  else
  {
    *(_QWORD *)(v22 + 224) = 0;
    *(_QWORD *)(v22 + 336) = 0;
    if ( !v8 )
      goto LABEL_19;
  }
  if ( v7 )
    sqlite3_free(v7);
LABEL_19:
  *(_QWORD *)v22 = a1;
  *(_DWORD *)(v22 + 180) = v14;
  if ( !v9 || !*v9 )
  {
    v27 = v59;
LABEL_21:
    *(_WORD *)(v22 + 21) = 1025;
    LOBYTE(v14) = v14 & 1;
    *(_BYTE *)(v22 + 17) = 1;
    v28 = 1;
    goto LABEL_37;
  }
  v32 = *(_QWORD *)(v22 + 72);
  v33 = *(_QWORD *)(v22 + 216);
  v34 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, unsigned int *))(a1 + 40);
  v59 = 0;
  v15 = v34(a1, v33, v32, v14 & 0x1087F7F, &v59);
  v14 = v59 & 1;
  v27 = (v59 >> 7) & 1;
  *(_BYTE *)(v22 + 20) = (v59 & 0x80) != 0;
  if ( !v15 )
  {
    v35 = sqlite3OsDeviceCharacteristics(*(_QWORD *)(v22 + 72));
    if ( !v14 )
    {
      setSectorSize(v22);
      v36 = *(_DWORD *)(v22 + 184);
      if ( v36 > 0x1000 )
      {
        if ( v36 > 0x2000 )
          v36 = 0x2000;
        v61 = v36;
      }
    }
    v37 = *(_QWORD *)(v22 + 216);
    if ( v37 && (v38 = databaseName(*(_QWORD *)(v22 + 216)), (v39 = uriParameter(v38, "nolock")) != 0) )
      Boolean = sqlite3GetBoolean(v39, 0);
    else
      Boolean = 0;
    *(_BYTE *)(v22 + 17) = Boolean;
    if ( (v35 & 0x2000) != 0
      || v37
      && (v41 = databaseName(v37), (v42 = uriParameter(v41, "immutable")) != 0)
      && (unsigned __int8)sqlite3GetBoolean(v42, 0) )
    {
      LOBYTE(v14) = 1;
      goto LABEL_21;
    }
  }
  v28 = 0;
LABEL_37:
  if ( v15 )
    goto LABEL_39;
  v15 = sqlite3PagerSetPagesize(v22, &v61, 0xFFFFFFFFLL);
  if ( v15 )
    goto LABEL_39;
  v44 = a7;
  v45 = pagerStress;
  if ( (_DWORD)a7 )
    LODWORD(v45) = 0;
  v15 = sqlite3PcacheOpen(v61, v43, (unsigned int)a7 ^ 1, (int)v45, v22, *(void **)(v22 + 320));
  if ( v15 )
  {
LABEL_39:
    sqlite3OsClose(*(_QWORD *)(v22 + 72));
    pcache1Free(*(_QWORD *)(v22 + 312));
    sqlite3_free(v22);
    return v15;
  }
  v46 = a5;
  *(_BYTE *)(v22 + 16) = v28;
  v47 = v28 ^ 1;
  *(_BYTE *)(v22 + 8) = v28;
  *(_BYTE *)(v22 + 23) = v28;
  v48 = (v46 & 1) == 0;
  *(_BYTE *)(v22 + 10) = v48;
  *(_DWORD *)(v22 + 188) = -2;
  *(_BYTE *)(v22 + 19) = v44;
  *(_BYTE *)(v22 + 18) = v14;
  *(_BYTE *)(v22 + 11) = v28;
  v49 = 2 * (v28 ^ 1);
  *(_WORD *)(v22 + 12) = v47;
  *(_BYTE *)(v22 + 14) = v49;
  *(_BYTE *)(v22 + 15) = 4 * v49;
  if ( v47 )
    *(_BYTE *)(v22 + 15) = (4 * v49) | v49;
  *(_BYTE *)(v22 + 25) &= ~1u;
  *(_WORD *)(v22 + 176) = 136;
  *(_QWORD *)(v22 + 208) = -1;
  setSectorSize(v22);
  if ( v48 )
  {
    if ( v44 || v27 )
      *(_BYTE *)(v22 + 9) = 4;
  }
  else
  {
    *(_BYTE *)(v22 + 9) = 2;
  }
  *(_QWORD *)(v22 + 264) = pageReinit;
  setGetterMethod(v22);
  result = 0;
  *v60 = v22;
  return result;
}

```

## disassembly

```asm
0x18003405c  mov     r11, rsp
0x18003405f  mov     [r11+18h], rbx
0x180034063  mov     [r11+20h], r9d
0x180034067  mov     [r11+10h], rdx
0x18003406b  push    rbp
0x18003406c  push    rsi
0x18003406d  push    rdi
0x18003406e  push    r12
0x180034070  push    r13
0x180034072  push    r14
0x180034074  push    r15
0x180034076  sub     rsp, 50h
0x18003407a  xor     eax, eax
0x18003407c  mov     dword ptr [r11+20h], 1000h
0x180034084  xor     r14d, r14d
0x180034087  mov     dword ptr [rsp+88h+arg_30], eax
0x18003408e  xor     r12d, r12d
0x180034091  mov     rbp, r8
0x180034094  mov     r13, rcx
0x180034097  lea     edi, [rax+50h]
0x18003409a  cmp     [rcx+4], edi
0x18003409d  lea     ebx, [rax+1]
0x1800340a0  cmovg   edi, [rcx+4]
0x1800340a4  test    byte ptr [rsp+88h+arg_20], 2
0x1800340ac  mov     [rdx], rax
0x1800340af  jnz     loc_180034585
0x1800340b5  mov     r15d, dword ptr [rsp+88h+arg_28]
0x1800340bd  xor     esi, esi
0x1800340bf  mov     [rsp+88h+Src], rsi
0x1800340c4  test    rbp, rbp
0x1800340c7  jz      loc_18003418E
0x1800340cd  cmp     [rbp+0], sil
0x1800340d1  jz      loc_18003418E
0x1800340d7  mov     ebx, [r13+8]
0x1800340db  inc     ebx
0x1800340dd  lea     eax, [rbx+rbx]
0x1800340e0  movsxd  rcx, eax
0x1800340e3  call    sqlite3Malloc
0x1800340e8  mov     r14, rax
0x1800340eb  test    rax, rax
0x1800340ee  jz      loc_1800345C2
0x1800340f4  mov     [rax], sil
0x1800340f7  mov     r9, rax
0x1800340fa  mov     rax, [r13+40h]
0x1800340fe  mov     r8d, ebx
0x180034101  mov     rdx, rbp
0x180034104  mov     rcx, r13
0x180034107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003410c  mov     esi, eax
0x18003410e  cmp     eax, 200h
0x180034113  jz      loc_1800345CC
0x180034119  mov     rcx, r14
0x18003411c  call    sqlite3Strlen30
0x180034121  mov     rcx, rbp
0x180034124  mov     r12d, eax
0x180034127  call    sqlite3Strlen30
0x18003412c  cdqe
0x18003412e  xor     edx, edx
0x180034130  inc     rax
0x180034133  add     rax, rbp
0x180034136  mov     [rsp+88h+Src], rax
0x18003413b  mov     rbx, rax
0x18003413e  cmp     [rax], dl
0x180034140  jnz     loc_1800345E3
0x180034146  test    esi, esi
0x180034148  jz      loc_18003456D
0x18003414e  mov     rdx, r14
0x180034151  xor     ecx, ecx
0x180034153  call    sqlite3DbFree
0x180034158  mov     eax, esi
0x18003415a  mov     rbx, [rsp+88h+arg_10]
0x180034162  add     rsp, 50h
0x180034166  pop     r15
0x180034168  pop     r14
0x18003416a  pop     r13
0x18003416c  pop     r12
0x18003416e  pop     rdi
0x18003416f  pop     rsi
0x180034170  pop     rbp
0x180034171  retn
0x180034172  lea     r8, aCannotOpenFile; "cannot open file"
0x180034179  mov     edx, 0F288h
0x18003417e  mov     ecx, 0Eh
0x180034183  call    sqlite3ReportError
0x180034188  mov     esi, eax
0x18003418a  test    eax, eax
0x18003418c  jnz     short loc_18003414E
0x18003418e  movsxd  rdx, dword ptr [r13+4]
0x180034192  lea     eax, [rdi+7]
0x180034195  and     eax, 0FFFFFFF8h
0x180034198  movsxd  r8, ebx
0x18003419b  mov     dword ptr [rsp+88h+var_58], eax
0x18003419f  add     rdx, 7
0x1800341a3  add     eax, eax
0x1800341a5  movsxd  rbx, r12d
0x1800341a8  movsxd  rcx, eax
0x1800341ab  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800341af  add     rcx, r8
0x1800341b2  mov     [rsp+88h+Size], r8
0x1800341b7  add     rdx, 1C6h
0x1800341be  mov     [rsp+88h+var_40], rbx
0x1800341c3  add     rcx, rdx
0x1800341c6  lea     rax, [rbx+rbx*2]
0x1800341ca  add     rcx, rax; Size
0x1800341cd  call    sqlite3MallocZero
0x1800341d2  xor     r8d, r8d
0x1800341d5  mov     rdi, rax
0x1800341d8  test    rax, rax
0x1800341db  jz      loc_180034619
0x1800341e1  movsxd  rdx, dword ptr [rsp+88h+var_58]
0x1800341e6  add     rax, 158h
0x1800341ec  mov     [rdi+140h], rax
0x1800341f3  mov     [rsp+88h+arg_0], r8d
0x1800341fb  lea     rcx, [rax+50h]
0x1800341ff  mov     [rdi+48h], rcx
0x180034203  movsxd  rax, dword ptr [r13+4]
0x180034207  add     rax, 7
0x18003420b  and     rax, 0FFFFFFFFFFFFFFF8h
0x18003420f  add     rax, rcx
0x180034212  mov     [rdi+58h], rax
0x180034216  lea     rcx, [rax+rdx]
0x18003421a  lea     rax, [rdx+0Ch]
0x18003421e  mov     [rdi+50h], rcx
0x180034222  add     rax, rcx
0x180034225  mov     [rdx+rcx], rdi
0x180034229  mov     [rsp+88h+var_58], rax
0x18003422e  mov     [rdi+0D8h], rax
0x180034235  test    r12d, r12d
0x180034238  jg      short loc_180034289
0x18003423a  mov     [rdi+0E0h], r8
0x180034241  mov     [rdi+150h], r8
0x180034248  test    r12d, r12d
0x18003424b  jz      short loc_18003425A
0x18003424d  test    r14, r14
0x180034250  jz      short loc_18003425A
0x180034252  mov     rcx, r14
0x180034255  call    sqlite3_free
0x18003425a  mov     [rdi], r13
0x18003425d  mov     [rdi+0B4h], r15d
0x180034264  test    rbp, rbp
0x180034267  jnz     loc_180034318
0x18003426d  mov     ebp, [rsp+88h+arg_0]
0x180034274  mov     word ptr [rdi+15h], 401h
0x18003427a  and     r15d, 1
0x18003427e  mov     byte ptr [rdi+11h], 1
0x180034282  mov     bl, 1
0x180034284  jmp     loc_18003441E
0x180034289  mov     r8, rbx; Size
0x18003428c  mov     rdx, r14; Src
0x18003428f  mov     rcx, rax; void *
0x180034292  call    memcpy_0
0x180034297  lea     eax, [r12+1]
0x18003429c  movsxd  rbx, eax
0x18003429f  add     rbx, [rsp+88h+var_58]
0x1800342a4  mov     rax, [rsp+88h+Src]
0x1800342a9  test    rax, rax
0x1800342ac  jz      loc_180034556
0x1800342b2  mov     r8, [rsp+88h+Size]; Size
0x1800342b7  mov     rdx, rax; Src
0x1800342ba  mov     rcx, rbx; void *
0x1800342bd  call    memcpy_0
0x1800342c2  add     rbx, [rsp+88h+Size]
0x1800342c7  mov     r12, [rsp+88h+var_40]
0x1800342cc  mov     rdx, r14; Src
0x1800342cf  mov     r8, r12; Size
0x1800342d2  mov     [rdi+0E0h], rbx
0x1800342d9  mov     rcx, rbx; void *
0x1800342dc  call    memcpy_0
0x1800342e1  mov     rax, 6C616E72756F6A2Dh
0x1800342eb  mov     r8, r12; Size
0x1800342ee  mov     [r12+rbx], rax
0x1800342f2  mov     rdx, r14; Src
0x1800342f5  add     rbx, 9
0x1800342f9  add     rbx, r12
0x1800342fc  mov     rcx, rbx; void *
0x1800342ff  mov     [rdi+150h], rbx
0x180034306  call    memcpy_0
0x18003430b  mov     dword ptr [rbx+r12], 6C61772Dh
0x180034313  jmp     loc_18003424D
0x180034318  cmp     byte ptr [rbp+0], 0
0x18003431c  jz      loc_18003426D
0x180034322  mov     r8, [rdi+48h]
0x180034326  lea     rax, [rsp+88h+arg_0]
0x18003432e  mov     rdx, [rdi+0D8h]
0x180034335  and     r15d, 1087F7Fh
0x18003433c  mov     [rsp+88h+var_68], rax
0x180034341  mov     r9d, r15d
0x180034344  mov     rax, [r13+28h]
0x180034348  mov     rcx, r13
0x18003434b  mov     [rsp+88h+arg_0], 0
0x180034356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003435b  mov     r15d, [rsp+88h+arg_0]
0x180034363  mov     esi, eax
0x180034365  mov     ebp, r15d
0x180034368  and     r15d, 1
0x18003436c  shr     ebp, 7
0x18003436f  and     ebp, 1
0x180034372  mov     [rdi+14h], bpl
0x180034376  test    eax, eax
0x180034378  jnz     loc_18003441C
0x18003437e  mov     rcx, [rdi+48h]
0x180034382  call    sqlite3OsDeviceCharacteristics
0x180034387  mov     r14d, eax
0x18003438a  mov     r12d, 2000h
0x180034390  test    r15d, r15d
0x180034393  jnz     short loc_1800343AF
0x180034395  mov     rcx, rdi
0x180034398  call    setSectorSize
0x18003439d  mov     ecx, [rdi+0B8h]
0x1800343a3  cmp     ecx, 1000h
0x1800343a9  ja      loc_180034623
0x1800343af  mov     rbx, [rdi+0D8h]
0x1800343b6  test    rbx, rbx
0x1800343b9  jz      short loc_1800343DB
0x1800343bb  mov     rcx, rbx
0x1800343be  call    databaseName
0x1800343c3  lea     rdx, aNolock; "nolock"
0x1800343ca  mov     rcx, rax
0x1800343cd  call    uriParameter
0x1800343d2  test    rax, rax
0x1800343d5  jnz     loc_18003455E
0x1800343db  xor     al, al
0x1800343dd  mov     [rdi+11h], al
0x1800343e0  test    r12d, r14d
0x1800343e3  jnz     loc_180034636
0x1800343e9  test    rbx, rbx
0x1800343ec  jz      short loc_18003441C
0x1800343ee  mov     rcx, rbx
0x1800343f1  call    databaseName
0x1800343f6  lea     rdx, aImmutable; "immutable"
0x1800343fd  mov     rcx, rax
0x180034400  call    uriParameter
0x180034405  test    rax, rax
0x180034408  jz      short loc_18003441C
0x18003440a  xor     edx, edx
0x18003440c  mov     rcx, rax
0x18003440f  call    sqlite3GetBoolean
0x180034414  test    al, al
0x180034416  jnz     loc_180034636
0x18003441c  xor     bl, bl
0x18003441e  test    esi, esi
0x180034420  jnz     short loc_18003443F
0x180034422  or      r12, 0FFFFFFFFFFFFFFFFh
0x180034426  lea     rdx, [rsp+88h+arg_18]
0x18003442e  mov     r8d, r12d
0x180034431  mov     rcx, rdi
0x180034434  call    sqlite3PagerSetPagesize
0x180034439  mov     esi, eax
0x18003443b  test    eax, eax
0x18003443d  jz      short loc_180034461
0x18003443f  mov     rcx, [rdi+48h]
0x180034443  call    sqlite3OsClose
0x180034448  mov     rcx, [rdi+138h]
0x18003444f  call    pcache1Free
0x180034454  mov     rcx, rdi
0x180034457  call    sqlite3_free
0x18003445c  jmp     loc_180034158
0x180034461  mov     r14d, dword ptr [rsp+88h+arg_30]
0x180034469  lea     r9, pagerStress
0x180034470  mov     ecx, [rsp+88h+arg_18]; int
0x180034477  xor     eax, eax
0x180034479  mov     r8d, r14d
0x18003447c  test    r14d, r14d
0x18003447f  cmovnz  r9, rax; int
0x180034483  mov     rax, [rdi+140h]
0x18003448a  mov     [rsp+88h+var_60], rax; void *
0x18003448f  xor     r8d, 1; int
0x180034493  mov     [rsp+88h+var_68], rdi; __int64
0x180034498  call    sqlite3PcacheOpen
0x18003449d  mov     esi, eax
0x18003449f  test    eax, eax
0x1800344a1  jnz     short loc_18003443F
0x1800344a3  mov     esi, dword ptr [rsp+88h+arg_20]
0x1800344aa  mov     al, bl
0x1800344ac  mov     [rdi+10h], bl
0x1800344af  xor     al, 1
0x1800344b1  mov     [rdi+8], bl
0x1800344b4  not     esi
0x1800344b6  mov     [rdi+17h], bl
0x1800344b9  and     esi, 1
0x1800344bc  mov     [rdi+0Ah], sil
0x1800344c0  mov     dword ptr [rdi+0BCh], 0FFFFFFFEh
0x1800344ca  mov     [rdi+13h], r14b
0x1800344ce  mov     [rdi+12h], r15b
0x1800344d2  mov     [rdi+0Bh], bl
0x1800344d5  xor     bl, 1
0x1800344d8  add     bl, bl
0x1800344da  mov     [rdi+0Ch], al
0x1800344dd  mov     byte ptr [rdi+0Dh], 0
0x1800344e1  mov     cl, bl
0x1800344e3  shl     cl, 2
0x1800344e6  mov     [rdi+0Eh], bl
0x1800344e9  mov     [rdi+0Fh], cl
0x1800344ec  test    al, al
0x1800344ee  jnz     short loc_18003454F
0x1800344f0  and     byte ptr [rdi+19h], 0FEh
0x1800344f4  mov     rcx, rdi
0x1800344f7  mov     word ptr [rdi+0B0h], 88h
0x180034500  mov     [rdi+0D0h], r12
0x180034507  call    setSectorSize
  ... truncated ...
```
