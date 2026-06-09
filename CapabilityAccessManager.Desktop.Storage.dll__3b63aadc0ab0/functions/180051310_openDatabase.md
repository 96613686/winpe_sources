# openDatabase

- ea: `0x180051310`
- end: `0x180051be5`
- name: `openDatabase`
- size: `2261`
- prototype: ``
- caller_count: `3`
- callee_count: `23`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180005fc0`
- `0x180005fe0`
- `0x180006190`

## callees

- `0x180003a40`
- `0x180005980`
- `0x180016970`
- `0x18001ddb0`
- `0x1800217a0`
- `0x18002b330`
- `0x1800342c0`
- `0x180051310`
- `0x180061a00`
- `0x180069890`
- `0x18006bb90`
- `0x180074340`
- `0x180074530`
- `0x180088560`
- `0x180088c60`
- `0x180089210`
- `0x18008b950`
- `0x180094330`
- `0x180097010`
- `0x18009b7c0`
- `0x1800bf820`
- `0x1800c1b30`
- `0x18010d010`

## string_xrefs

- `0x1800519c3`: `automatic extension loading failed: %s`

## pseudocode

```c
__int64 __fastcall openDatabase(const char *a1, _QWORD *a2, int a3, char *a4)
{
  __int64 v5; // rsi
  __int64 v6; // rbp
  __int64 result; // rax
  int v9; // r13d
  int v10; // r14d
  unsigned int v11; // edi
  _QWORD *v12; // rax
  _QWORD *v13; // rbx
  _QWORD *v14; // rdi
  __int64 v15; // rax
  int v16; // eax
  int v17; // r8d
  int v18; // r8d
  unsigned int v19; // r12d
  unsigned int v20; // eax
  unsigned int v21; // r14d
  const char *v22; // r8
  int v23; // eax
  void (*v24)(void); // rax
  _QWORD *v25; // r14
  char v26; // al
  unsigned int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rdi
  __int64 v30; // rcx
  bool v31; // zf
  __int64 v32; // rdi
  char v33; // al
  unsigned int v34; // eax
  int v35; // ebp
  __int64 v36; // r15
  __int64 v37; // rbp
  __int64 v38; // rax
  __int64 (__fastcall *v39)(_QWORD *, __int64 *, __int64 (__fastcall **)()); // r14
  unsigned int v40; // eax
  __int64 v41; // rbp
  int v42; // eax
  void (*v43)(void); // rax
  char v44; // al
  __int64 v45; // rcx
  int v46; // r12d
  __int64 v47; // [rsp+20h] [rbp-58h]
  __int64 v48; // [rsp+30h] [rbp-48h] BYREF
  __int64 v49; // [rsp+38h] [rbp-40h] BYREF
  unsigned int v52; // [rsp+90h] [rbp+18h] BYREF

  v5 = 0;
  v48 = 0;
  v6 = 0;
  v49 = 0;
  *a2 = 0;
  result = sqlite3_initialize(a1, a2);
  if ( (_DWORD)result )
    return result;
  v9 = 1;
  if ( (_BYTE)word_18013C1B4 )
  {
    if ( (a3 & 0x8000) != 0 )
    {
      v10 = 0;
    }
    else
    {
      v10 = 1;
      if ( (a3 & 0x10000) == 0 )
        v10 = HIBYTE(word_18013C1B4);
    }
  }
  else
  {
    v10 = 0;
  }
  if ( (a3 & 0x40000) != 0 )
  {
    a3 &= ~0x20000u;
  }
  else if ( dword_18013C2FC )
  {
    a3 |= 0x20000u;
  }
  v11 = a3 & 0xFFF600E7;
  v52 = v11;
  v12 = (_QWORD *)sqlite3Malloc(824);
  v13 = v12;
  if ( !v12 )
  {
    v14 = 0;
    goto LABEL_114;
  }
  memset_0(v12, 0, 0x338u);
  if ( v10 )
  {
    if ( !(_BYTE)word_18013C1B4 )
    {
      v13[3] = 0;
      sqlite3_free(v13);
      v14 = 0;
      goto LABEL_114;
    }
    v15 = ((__int64 (__fastcall *)(__int64))xmmword_18013C220)(1);
    v13[3] = v15;
    if ( !v15 )
    {
      sqlite3_free(v13);
      v14 = 0;
      goto LABEL_114;
    }
  }
  if ( v13[3] )
    ((void (*)(void))xmmword_18013C230)();
  *((_DWORD *)v13 + 10) = 2;
  *((_BYTE *)v13 + 113) = 109;
  *((_DWORD *)v13 + 104) = 1;
  *((_WORD *)v13 + 210) = 0;
  v16 = 255;
  if ( (v11 & 0x2000000) != 0 )
    v16 = -1;
  *((_DWORD *)v13 + 22) = v16;
  v13[4] = v13 + 84;
  *(_OWORD *)(v13 + 17) = xmmword_180114078;
  *(_OWORD *)(v13 + 19) = xmmword_180114088;
  *((_BYTE *)v13 + 106) = -1;
  *((_BYTE *)v13 + 101) = 1;
  *(_OWORD *)(v13 + 21) = xmmword_180114098;
  *((_DWORD *)v13 + 45) = 0;
  v13[8] = qword_18013C2D8;
  v13[26] = off_18013C388;
  v13[6] |= 0xE00480E0uLL;
  *((_DWORD *)v13 + 29) = 0;
  v13[79] = 0;
  v13[78] = 0;
  v13[80] = 0;
  v13[70] = 0;
  v13[69] = 0;
  v13[71] = 0;
  createCollation((_DWORD)v13, (unsigned int)"BINARY", 1, 0, (__int64)&binCollFunc, 0);
  LOBYTE(v17) = 3;
  createCollation((_DWORD)v13, (unsigned int)"BINARY", v17, 0, (__int64)&binCollFunc, 0);
  LOBYTE(v18) = 2;
  createCollation((_DWORD)v13, (unsigned int)"BINARY", v18, 0, (__int64)&binCollFunc, 0);
  createCollation((_DWORD)v13, (unsigned int)"NOCASE", 1, 0, (__int64)nocaseCollatingFunc, 0);
  createCollation((_DWORD)v13, (unsigned int)"RTRIM", 1, 0, (__int64)&rtrimCollFunc, 0);
  v19 = 21;
  if ( *((_BYTE *)v13 + 103) )
    goto LABEL_38;
  *((_DWORD *)v13 + 19) = v11;
  if ( ((1 << (v11 & 7)) & 0x46) != 0 )
  {
    v20 = sqlite3ParseUri(a4, a1, &v52, v13, (char **)&v48, &v49);
    v11 = v52;
    v5 = v48;
    v6 = v49;
  }
  else
  {
    v20 = sqlite3MisuseError(179805);
  }
  v21 = v20;
  if ( v20 )
  {
    if ( v20 == 7 )
      sqlite3OomFault(v13);
    v22 = 0;
    if ( v6 )
      v22 = "%s";
    sqlite3ErrorWithMsg(v13, v21, v22, v6);
    if ( !v6 )
      goto LABEL_38;
    if ( dword_18013C1B0 )
    {
      if ( (_QWORD)xmmword_18013FC60 )
        ((void (*)(void))xmmword_18013C230)();
      v23 = ((__int64 (__fastcall *)(__int64))xmmword_18013C1E8)(v6);
      --qword_18013FBE8;
      qword_18013FBA0 -= v23;
      ((void (__fastcall *)(__int64))xmmword_18013C1D8)(v6);
      if ( !(_QWORD)xmmword_18013FC60 )
        goto LABEL_38;
      v24 = (void (*)(void))xmmword_18013C240;
    }
    else
    {
      v24 = (void (*)(void))xmmword_18013C1D8;
    }
    v24();
LABEL_38:
    v25 = v13;
    v14 = v13;
    goto LABEL_39;
  }
  LODWORD(v47) = 0;
  v27 = sqlite3BtreeOpen(*v13, v5, v13, v13[4] + 8LL, v47, v11 | 0x100);
  if ( v27 )
  {
    if ( v27 == 3082 )
      v27 = 7;
    *((_DWORD *)v13 + 20) = v27;
    sqlite3ErrorFinish(v13, v27);
    goto LABEL_38;
  }
  v28 = *(_QWORD *)(v13[4] + 8LL);
  if ( *(_BYTE *)(v28 + 17) )
  {
    ++*(_DWORD *)(v28 + 20);
    if ( !*(_BYTE *)(v28 + 18) )
      btreeLockCarefully(v28);
  }
  v29 = v13[4];
  *(_QWORD *)(v29 + 24) = sqlite3SchemaGet(v13, *(_QWORD *)(v29 + 8));
  if ( !*((_BYTE *)v13 + 103) )
    sqlite3SetTextEncoding(v13);
  v30 = *(_QWORD *)(v13[4] + 8LL);
  if ( *(_BYTE *)(v30 + 17) )
  {
    v31 = (*(_DWORD *)(v30 + 20))-- == 1;
    if ( v31 )
      unlockBtreeMutex(v30);
  }
  v32 = v13[4];
  *(_QWORD *)(v32 + 56) = sqlite3SchemaGet(v13, 0);
  *(_QWORD *)v13[4] = "main";
  *(_BYTE *)(v13[4] + 16LL) = 3;
  *(_QWORD *)(v13[4] + 32LL) = "temp";
  *(_BYTE *)(v13[4] + 48LL) = 1;
  v31 = *((_BYTE *)v13 + 103) == 0;
  *((_BYTE *)v13 + 113) = 118;
  if ( !v31 )
    goto LABEL_38;
  v31 = v13[50] == 0;
  *((_DWORD *)v13 + 20) = 0;
  if ( v31 )
    *((_DWORD *)v13 + 21) = -1;
  else
    sqlite3ErrorFinish(v13, 0);
  sqlite3RegisterPerConnectionBuiltinFunctions(v13);
  v33 = *((_BYTE *)v13 + 113);
  if ( v33 != -70 && v33 != 118 && v33 != 109 )
  {
    sqlite3_log(21, "API call with %s database connection pointer", "invalid");
    sqlite3_log(
      21,
      "%s at line %d of [%.10s]",
      "misuse",
      179076,
      "0f80b798b3f4b81a7bb4233c58294edd0f1156f36b6ecf5ab8e83631d468778c");
    v34 = 21;
    v14 = v13;
LABEL_103:
    v25 = v13;
LABEL_104:
    *((_DWORD *)v13 + 20) = v34;
    sqlite3ErrorFinish(v14, v34);
LABEL_105:
    setupLookaside(v14, 0, (unsigned int)dword_18013C1C4, (unsigned int)dword_18013C1C8);
    if ( v13[3] )
      ((void (*)(void))xmmword_18013C230)();
    v45 = v13[3];
    v14[45] = sqlite3WalDefaultHook;
    v14[46] = 1000;
    if ( v45 )
      ((void (*)(void))xmmword_18013C240)();
    goto LABEL_39;
  }
  v14 = v13;
  if ( *((_BYTE *)v13 + 103) )
  {
    v34 = 7;
    goto LABEL_103;
  }
  v35 = 0;
  v25 = v13;
  v34 = v13[10] & v13[11];
  if ( v34 )
    goto LABEL_104;
  while ( v35 < 2 )
  {
    v34 = ((__int64 (__fastcall *)(_QWORD *))funcs_180051905[v35++])(v13);
    if ( v34 )
      goto LABEL_104;
  }
  if ( dword_18013FEC0 )
  {
    v36 = 0;
    while ( 1 )
    {
      if ( (_BYTE)word_18013C1B4 )
      {
        v38 = ((__int64 (__fastcall *)(__int64))xmmword_18013C220)(2);
        v37 = v38;
        if ( v38 )
          ((void (__fastcall *)(__int64))xmmword_18013C230)(v38);
      }
      else
      {
        v37 = 0;
      }
      if ( (unsigned int)v36 < dword_18013FEC0 )
      {
        v39 = *(__int64 (__fastcall **)(_QWORD *, __int64 *, __int64 (__fastcall **)()))(qword_18013FEC8 + 8 * v36);
      }
      else
      {
        v39 = 0;
        v9 = 0;
      }
      if ( v37 )
        ((void (__fastcall *)(__int64))xmmword_18013C240)(v37);
      v48 = 0;
      if ( v39 )
      {
        v40 = v39(v13, &v48, off_18010E060);
        if ( v40 )
        {
          sqlite3ErrorWithMsg(v13, v40, "automatic extension loading failed: %s", (const char *)v48);
          v9 = 0;
        }
      }
      v41 = v48;
      if ( !v48 )
        goto LABEL_93;
      if ( dword_18013C1B0 )
      {
        if ( (_QWORD)xmmword_18013FC60 )
          ((void (*)(void))xmmword_18013C230)();
        v42 = ((__int64 (__fastcall *)(__int64))xmmword_18013C1E8)(v41);
        --qword_18013FBE8;
        qword_18013FBA0 -= v42;
        ((void (__fastcall *)(__int64))xmmword_18013C1D8)(v41);
        if ( !(_QWORD)xmmword_18013FC60 )
          goto LABEL_93;
        v43 = (void (*)(void))xmmword_18013C240;
      }
      else
      {
        v43 = (void (*)(void))xmmword_18013C1D8;
      }
      v43();
LABEL_93:
      v36 = (unsigned int)(v36 + 1);
      if ( !v9 )
      {
        v25 = v13;
        break;
      }
    }
  }
  v44 = *((_BYTE *)v13 + 113);
  if ( v44 != -70 && v44 != 118 && v44 != 109 )
  {
    sqlite3_log(21, "API call with %s database connection pointer", "invalid");
    sqlite3_log(
      21,
      "%s at line %d of [%.10s]",
      "misuse",
      179076,
      "0f80b798b3f4b81a7bb4233c58294edd0f1156f36b6ecf5ab8e83631d468778c");
    goto LABEL_39;
  }
  if ( !*((_BYTE *)v13 + 103) && ((_DWORD)v13[10] & (_DWORD)v13[11]) == 0 )
    goto LABEL_105;
LABEL_39:
  if ( v13[3] )
    ((void (*)(void))xmmword_18013C240)();
  v26 = *((_BYTE *)v13 + 113);
  if ( v26 == -70 || v26 == 118 || v26 == 109 )
  {
    if ( !*((_BYTE *)v13 + 103) )
    {
      v46 = *((_DWORD *)v14 + 20);
      v14 = v25;
      v19 = v13[11] & v46;
      if ( (_BYTE)v19 != 7 )
      {
        if ( v19 )
          *((_BYTE *)v25 + 113) = -70;
        goto LABEL_116;
      }
      goto LABEL_115;
    }
LABEL_114:
    v19 = 7;
LABEL_115:
    sqlite3Close(v14, 0);
    v14 = 0;
    goto LABEL_116;
  }
  sqlite3_log(21, "API call with %s database connection pointer", "invalid");
  sqlite3_log(
    21,
    "%s at line %d of [%.10s]",
    "misuse",
    179076,
    "0f80b798b3f4b81a7bb4233c58294edd0f1156f36b6ecf5ab8e83631d468778c");
  *((_BYTE *)v14 + 113) = -70;
LABEL_116:
  *a2 = v14;
  if ( v5 )
  {
    while ( *(_BYTE *)(v5 - 1) || *(_BYTE *)(v5 - 2) || *(_BYTE *)(v5 - 3) || *(_BYTE *)(v5 - 4) )
      --v5;
    sqlite3_free(v5 - 4);
  }
  return v19;
}

```

## disassembly

```asm
0x180051310  mov     [rsp+arg_8], rdx
0x180051315  mov     [rsp+Src], rcx
0x18005131a  push    rbp
0x18005131b  push    rsi
0x18005131c  push    rdi
0x18005131d  push    r12
0x18005131f  push    r15
0x180051321  sub     rsp, 50h
0x180051325  xor     r12d, r12d
0x180051328  mov     r15, r9
0x18005132b  mov     esi, r12d
0x18005132e  mov     [rsp+78h+var_48], r12
0x180051333  mov     ebp, r12d
0x180051336  mov     [rsp+78h+var_40], r12
0x18005133b  mov     [rdx], r12
0x18005133e  mov     edi, r8d
0x180051341  call    sqlite3_initialize
0x180051346  test    eax, eax
0x180051348  jnz     loc_180051BD9
0x18005134e  cmp     byte ptr cs:word_18013C1B4, sil
0x180051355  mov     [rsp+78h+arg_18], rbx
0x18005135d  mov     [rsp+78h+var_30], r13
0x180051362  mov     r13d, 1
0x180051368  mov     [rsp+78h+var_38], r14
0x18005136d  jnz     short loc_180051374
0x18005136f  mov     r14d, r12d
0x180051372  jmp     short loc_180051390
0x180051374  bt      edi, 0Fh
0x180051378  jnb     short loc_18005137F
0x18005137a  mov     r14d, r12d
0x18005137d  jmp     short loc_180051390
0x18005137f  mov     r14d, r13d
0x180051382  bt      edi, 10h
0x180051386  jb      short loc_180051390
0x180051388  movzx   r14d, byte ptr cs:word_18013C1B4+1
0x180051390  bt      edi, 12h
0x180051394  jnb     short loc_18005139C
0x180051396  btr     edi, 11h
0x18005139a  jmp     short loc_1800513A8
0x18005139c  cmp     cs:dword_18013C2FC, esi
0x1800513a2  jz      short loc_1800513A8
0x1800513a4  bts     edi, 11h
0x1800513a8  and     edi, 0FFF600E7h
0x1800513ae  mov     ecx, 338h
0x1800513b3  mov     [rsp+78h+arg_10], edi
0x1800513ba  call    sqlite3Malloc
0x1800513bf  mov     rbx, rax
0x1800513c2  test    rax, rax
0x1800513c5  jz      loc_180051B79
0x1800513cb  xor     edx, edx; Val
0x1800513cd  mov     r8d, 338h; Size
0x1800513d3  mov     rcx, rax; void *
0x1800513d6  call    memset_0
0x1800513db  test    r14d, r14d
0x1800513de  jz      short loc_180051425
0x1800513e0  cmp     byte ptr cs:word_18013C1B4, sil
0x1800513e7  jnz     short loc_1800513FD
0x1800513e9  mov     rcx, rbx
0x1800513ec  mov     [rbx+18h], r12
0x1800513f0  call    sqlite3_free
0x1800513f5  mov     rdi, r12
0x1800513f8  jmp     loc_180051B7C
0x1800513fd  mov     rax, qword ptr cs:xmmword_18013C220
0x180051404  mov     ecx, r13d
0x180051407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005140c  mov     [rbx+18h], rax
0x180051410  test    rax, rax
0x180051413  jnz     short loc_180051425
0x180051415  mov     rcx, rbx
0x180051418  call    sqlite3_free
0x18005141d  mov     rdi, r12
0x180051420  jmp     loc_180051B7C
0x180051425  mov     rcx, [rbx+18h]
0x180051429  test    rcx, rcx
0x18005142c  jz      short loc_18005143A
0x18005142e  mov     rax, qword ptr cs:xmmword_18013C230
0x180051435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005143a  mov     dword ptr [rbx+28h], 2
0x180051441  lea     r14, binCollFunc
0x180051448  mov     byte ptr [rbx+71h], 6Dh ; 'm'
0x18005144c  lea     rdx, aBinary_0; "BINARY"
0x180051453  mov     [rbx+1A0h], r13d
0x18005145a  mov     ecx, 0FFFFFFFFh
0x18005145f  mov     [rbx+1A4h], r12w
0x180051467  mov     eax, 0FFh
0x18005146c  bt      edi, 19h
0x180051470  mov     [rsp+78h+var_50], r12
0x180051475  movzx   r8d, r13b
0x180051479  mov     [rsp+78h+var_58], r14
0x18005147e  cmovb   eax, ecx
0x180051481  xor     r9d, r9d
0x180051484  mov     [rbx+58h], eax
0x180051487  lea     rax, [rbx+2A0h]
0x18005148e  mov     [rbx+20h], rax
0x180051492  movups  xmm0, cs:xmmword_180114078
0x180051499  movups  xmmword ptr [rbx+88h], xmm0
0x1800514a0  movups  xmm1, cs:xmmword_180114088
0x1800514a7  movups  xmmword ptr [rbx+98h], xmm1
0x1800514ae  movups  xmm0, cs:xmmword_180114098
0x1800514b5  mov     [rbx+6Ah], cl
0x1800514b8  mov     rcx, rbx
0x1800514bb  mov     [rbx+65h], r13b
0x1800514bf  movups  xmmword ptr [rbx+0A8h], xmm0
0x1800514c6  mov     [rbx+0B4h], r12d
0x1800514cd  mov     rax, cs:qword_18013C2D8
0x1800514d4  mov     [rbx+40h], rax
0x1800514d8  lea     rax, off_18013C388; "ANY"
0x1800514df  mov     [rbx+0D0h], rax
0x1800514e6  mov     eax, 0E00480E0h
0x1800514eb  or      [rbx+30h], rax
0x1800514ef  mov     [rbx+74h], r12d
0x1800514f3  mov     [rbx+278h], r12
0x1800514fa  mov     [rbx+270h], r12
0x180051501  mov     [rbx+280h], r12
0x180051508  mov     [rbx+230h], r12
0x18005150f  mov     [rbx+228h], r12
0x180051516  mov     [rbx+238h], r12
0x18005151d  call    createCollation
0x180051522  xor     r9d, r9d
0x180051525  mov     [rsp+78h+var_50], r12
0x18005152a  mov     r8b, 3
0x18005152d  mov     [rsp+78h+var_58], r14
0x180051532  lea     rdx, aBinary_0; "BINARY"
0x180051539  mov     rcx, rbx
0x18005153c  call    createCollation
0x180051541  xor     r9d, r9d
0x180051544  mov     [rsp+78h+var_50], r12
0x180051549  mov     r8b, 2
0x18005154c  mov     [rsp+78h+var_58], r14
0x180051551  lea     rdx, aBinary_0; "BINARY"
0x180051558  mov     rcx, rbx
0x18005155b  call    createCollation
0x180051560  lea     rax, nocaseCollatingFunc
0x180051567  mov     [rsp+78h+var_50], r12
0x18005156c  xor     r9d, r9d
0x18005156f  mov     [rsp+78h+var_58], rax
0x180051574  movzx   r8d, r13b
0x180051578  lea     rdx, aNocase; "NOCASE"
0x18005157f  mov     rcx, rbx
0x180051582  call    createCollation
0x180051587  lea     rax, rtrimCollFunc
0x18005158e  mov     [rsp+78h+var_50], r12
0x180051593  xor     r9d, r9d
0x180051596  mov     [rsp+78h+var_58], rax
0x18005159b  movzx   r8d, r13b
0x18005159f  lea     rdx, aRtrim_0; "RTRIM"
0x1800515a6  mov     rcx, rbx
0x1800515a9  call    createCollation
0x1800515ae  mov     r12d, 15h
0x1800515b4  cmp     [rbx+67h], sil
0x1800515b8  jnz     loc_1800516C3
0x1800515be  mov     ecx, edi
0x1800515c0  mov     [rbx+4Ch], edi
0x1800515c3  and     ecx, 7
0x1800515c6  mov     eax, r13d
0x1800515c9  shl     eax, cl
0x1800515cb  test    al, 46h
0x1800515cd  jnz     short loc_1800515DB
0x1800515cf  mov     ecx, 2BE5Dh
0x1800515d4  call    sqlite3MisuseError
0x1800515d9  jmp     short loc_18005161B
0x1800515db  mov     rdx, [rsp+78h+Src]; Src
0x1800515e3  lea     rax, [rsp+78h+var_40]
0x1800515e8  mov     [rsp+78h+var_50], rax; __int64
0x1800515ed  lea     r8, [rsp+78h+arg_10]
0x1800515f5  lea     rax, [rsp+78h+var_48]
0x1800515fa  mov     r9, rbx
0x1800515fd  mov     rcx, r15; Str1
0x180051600  mov     [rsp+78h+var_58], rax; __int64
0x180051605  call    sqlite3ParseUri
0x18005160a  mov     edi, [rsp+78h+arg_10]
0x180051611  mov     rsi, [rsp+78h+var_48]
0x180051616  mov     rbp, [rsp+78h+var_40]
0x18005161b  mov     r14d, eax
0x18005161e  test    eax, eax
0x180051620  jz      loc_180051750
0x180051626  cmp     eax, 7
0x180051629  jnz     short loc_180051633
0x18005162b  mov     rcx, rbx
0x18005162e  call    sqlite3OomFault
0x180051633  xor     r8d, r8d
0x180051636  lea     rax, aS_7; "%s"
0x18005163d  test    rbp, rbp
0x180051640  mov     r9, rbp
0x180051643  mov     edx, r14d
0x180051646  mov     rcx, rbx
0x180051649  cmovnz  r8, rax
0x18005164d  call    sqlite3ErrorWithMsg
0x180051652  test    rbp, rbp
0x180051655  jz      short loc_1800516C3
0x180051657  cmp     cs:dword_18013C1B0, 0
0x18005165e  jz      loc_180051741
0x180051664  mov     rcx, qword ptr cs:xmmword_18013FC60
0x18005166b  test    rcx, rcx
0x18005166e  jz      short loc_18005167C
0x180051670  mov     rax, qword ptr cs:xmmword_18013C230
0x180051677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005167c  mov     rax, qword ptr cs:xmmword_18013C1E8
0x180051683  mov     rcx, rbp
0x180051686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005168b  dec     cs:qword_18013FBE8
0x180051692  mov     rcx, rbp
0x180051695  movsxd  rdx, eax
0x180051698  mov     rax, qword ptr cs:xmmword_18013C1D8
0x18005169f  sub     cs:qword_18013FBA0, rdx
0x1800516a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800516ab  mov     rcx, qword ptr cs:xmmword_18013FC60
0x1800516b2  test    rcx, rcx
0x1800516b5  jz      short loc_1800516C3
0x1800516b7  mov     rax, qword ptr cs:xmmword_18013C240
0x1800516be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800516c3  mov     r14, rbx
0x1800516c6  mov     rdi, rbx
0x1800516c9  lea     rbp, a20230824123659+14h; "0f80b798b3f4b81a7bb4233c58294edd0f1156f"...
0x1800516d0  mov     rcx, [rbx+18h]
0x1800516d4  test    rcx, rcx
0x1800516d7  jz      short loc_1800516E5
0x1800516d9  mov     rax, qword ptr cs:xmmword_18013C240
0x1800516e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800516e5  movzx   eax, byte ptr [rbx+71h]
0x1800516e9  cmp     al, 0BAh
0x1800516eb  jz      loc_180051B56
0x1800516f1  cmp     al, 76h ; 'v'
0x1800516f3  jz      loc_180051B56
0x1800516f9  cmp     al, 6Dh ; 'm'
0x1800516fb  jz      loc_180051B56
0x180051701  lea     r8, aInvalid; "invalid"
0x180051708  mov     ecx, r12d
0x18005170b  lea     rdx, aApiCallWithSDa; "API call with %s database connection po"...
0x180051712  call    sqlite3_log
0x180051717  mov     r9d, 2BB84h
0x18005171d  mov     [rsp+78h+var_58], rbp
0x180051722  lea     r8, aMisuse; "misuse"
0x180051729  mov     ecx, r12d
0x18005172c  lea     rdx, aSAtLineDOf10s; "%s at line %d of [%.10s]"
0x180051733  call    sqlite3_log
0x180051738  mov     byte ptr [rdi+71h], 0BAh
0x18005173c  jmp     loc_180051B8E
0x180051741  mov     rax, qword ptr cs:xmmword_18013C1D8
0x180051748  mov     rcx, rbp
0x18005174b  jmp     loc_1800516BE
0x180051750  mov     r9, [rbx+20h]
0x180051754  bts     edi, 8
0x180051758  mov     rcx, [rbx]
0x18005175b  add     r9, 8
0x18005175f  mov     dword ptr [rsp+78h+var_50], edi
0x180051763  mov     r8, rbx
0x180051766  mov     rdx, rsi
0x180051769  mov     dword ptr [rsp+78h+var_58], 0
0x180051771  call    sqlite3BtreeOpen
0x180051776  test    eax, eax
0x180051778  jz      short loc_18005179A
0x18005177a  cmp     eax, 0C0Ah
0x18005177f  jnz     short loc_180051786
0x180051781  mov     eax, 7
0x180051786  mov     ecx, eax
0x180051788  mov     [rbx+50h], eax
0x18005178b  mov     rcx, rbx
0x18005178e  mov     edx, eax
0x180051790  call    sqlite3ErrorFinish
0x180051795  jmp     loc_1800516C3
0x18005179a  mov     rax, [rbx+20h]
0x18005179e  mov     rcx, [rax+8]
0x1800517a2  cmp     byte ptr [rcx+11h], 0
0x1800517a6  jz      short loc_1800517B6
0x1800517a8  inc     dword ptr [rcx+14h]
0x1800517ab  cmp     byte ptr [rcx+12h], 0
0x1800517af  jnz     short loc_1800517B6
0x1800517b1  call    btreeLockCarefully
0x1800517b6  mov     rdi, [rbx+20h]
0x1800517ba  mov     rcx, rbx
0x1800517bd  mov     rdx, rdi
0x1800517c0  mov     rdx, [rdx+8]
0x1800517c4  call    sqlite3SchemaGet
0x1800517c9  mov     [rdi+18h], rax
0x1800517cd  cmp     byte ptr [rbx+67h], 0
0x1800517d1  jnz     short loc_1800517E7
0x1800517d3  mov     rax, [rbx+20h]
0x1800517d7  mov     rcx, rbx
0x1800517da  mov     rdx, [rax+18h]
0x1800517de  movzx   edx, byte ptr [rdx+71h]
0x1800517e2  call    sqlite3SetTextEncoding
0x1800517e7  mov     rax, [rbx+20h]
0x1800517eb  mov     rcx, [rax+8]
0x1800517ef  cmp     byte ptr [rcx+11h], 0
0x1800517f3  jz      short loc_180051800
0x1800517f5  sub     [rcx+14h], r13d
0x1800517f9  jnz     short loc_180051800
0x1800517fb  call    unlockBtreeMutex
0x180051800  mov     rdi, [rbx+20h]
0x180051804  xor     edx, edx
0x180051806  mov     rcx, rbx
0x180051809  call    sqlite3SchemaGet
0x18005180e  mov     [rdi+38h], rax
0x180051812  lea     rcx, aMain; "main"
0x180051819  mov     rax, [rbx+20h]
0x18005181d  mov     [rax], rcx
0x180051820  lea     rcx, aTemp; "temp"
0x180051827  mov     rax, [rbx+20h]
0x18005182b  mov     byte ptr [rax+10h], 3
  ... truncated ...
```
