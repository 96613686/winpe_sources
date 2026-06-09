# sqlite3LoadExtension

- ea: `0x180087630`
- end: `0x180087cd0`
- name: `sqlite3LoadExtension`
- size: `1696`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000fbc0`
- `0x180020210`

## callees

- `0x180003a40`
- `0x180005450`
- `0x180005640`
- `0x180005980`
- `0x18004dba0`
- `0x180071400`
- `0x180087630`
- `0x180088560`
- `0x1800bf820`
- `0x1800e4dce`
- `0x1800e4dfe`
- `0x18010d010`

## string_xrefs

- `0x1800876ac`: `sqlite3_extension_init`
- `0x1800879de`: `error during initialization: %s`
- `0x180087c85`: `unable to open shared library [%.*s]`

## pseudocode

```c
__int64 __fastcall sqlite3LoadExtension(__int64 *a1, const char *a2, const char *a3, const char **a4)
{
  __int64 v4; // rbp
  __int64 v9; // rdx
  __int64 v10; // rcx
  size_t v11; // rsi
  const char *v12; // r13
  __int64 v13; // r14
  __int64 v14; // rdi
  __int64 v15; // rsi
  size_t v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 (__fastcall *v19)(__int64 *, const char **, __int64 (__fastcall **)()); // rdi
  char *v20; // rsi
  char *v21; // rax
  __int64 v22; // r8
  char v23; // cl
  const char *v24; // r9
  int v25; // edx
  int v26; // edx
  const char *v27; // r10
  int v28; // eax
  int v29; // edx
  int v30; // r8d
  unsigned int i; // ecx
  __int64 v32; // rax
  __int64 v33; // rcx
  int v34; // eax
  void (*v35)(void); // rax
  int v36; // eax
  size_t v38; // rbx
  __int64 v39; // rdx
  __int64 v40; // rcx
  size_t v41; // rbx
  const char *v42; // rax
  int v43; // eax
  size_t v44; // rsi
  void *v45; // rax
  void *v46; // rdi
  __int64 v47; // rax
  _QWORD *v48; // rcx
  __int64 v49; // rax
  const char *v50; // rax
  __int64 v51; // [rsp+30h] [rbp-48h]
  const char *v52; // [rsp+80h] [rbp+8h] BYREF
  const char *v53; // [rsp+90h] [rbp+18h]
  size_t v54; // [rsp+98h] [rbp+20h]

  v53 = a3;
  v4 = *a1;
  v52 = 0;
  v54 = strlen_0(a2);
  v11 = v54;
  if ( a4 )
    *a4 = 0;
  if ( (a1[6] & 0x10000) == 0 )
  {
    if ( a4 )
      *a4 = (const char *)sqlite3_mprintf("not authorized");
    return 1;
  }
  v12 = "sqlite3_extension_init";
  if ( a3 )
    v12 = a3;
  if ( v11 - 1 > 0x103 )
  {
LABEL_86:
    if ( a4 )
    {
      if ( (unsigned int)sqlite3_initialize(v10, v9) )
      {
        *a4 = 0;
      }
      else
      {
        v50 = (const char *)sqlite3Malloc(v11 + 300);
        v52 = v50;
        *a4 = v50;
        if ( v50 )
        {
          sqlite3_snprintf((unsigned int)(v11 + 300), v50, "unable to open shared library [%.*s]", 260, a2);
          (*(void (__fastcall **)(__int64, _QWORD, const char *))(v4 + 80))(v4, (unsigned int)(v11 + 299), v52);
        }
      }
    }
    return 1;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, const char *))(v4 + 72))(v4, a2);
  v51 = v13;
  v14 = 0;
  do
  {
    if ( v13 )
      goto LABEL_17;
    v15 = sqlite3_mprintf("%s.%s", a2, (&off_18013D218)[v14]);
    if ( !v15 )
      return 7;
    v16 = strlen_0((&off_18013D218)[v14]);
    if ( v16 + v54 + 1 > 0x104 )
    {
      v13 = v51;
    }
    else
    {
      v13 = (*(__int64 (__fastcall **)(__int64, __int64))(v4 + 72))(v4, v15);
      v51 = v13;
    }
    sqlite3_free(v15);
    v14 = (unsigned int)(v14 + 1);
  }
  while ( (int)v14 < 1 );
  if ( !v13 )
  {
    v11 = v54;
    goto LABEL_86;
  }
LABEL_17:
  v19 = (__int64 (__fastcall *)(__int64 *, const char **, __int64 (__fastcall **)()))(*(__int64 (__fastcall **)(__int64, __int64, const char *))(v4 + 88))(
                                                                                       v4,
                                                                                       v13,
                                                                                       v12);
  if ( v19 )
    goto LABEL_51;
  v20 = 0;
  if ( v53 )
    goto LABEL_59;
  if ( a2 )
    v19 = (__int64 (__fastcall *)(__int64 *, const char **, __int64 (__fastcall **)()))(strlen_0(a2) & 0x3FFFFFFF);
  if ( (unsigned int)sqlite3_initialize(v18, v17)
    || (v21 = (char *)sqlite3Malloc((unsigned int)((_DWORD)v19 + 30)), (v20 = v21) == 0) )
  {
    (*(void (__fastcall **)(__int64, __int64))(v4 + 96))(v4, v13);
    return 7;
  }
  v12 = v21;
  v22 = (unsigned int)((_DWORD)v19 - 1);
  for ( *(_QWORD *)v21 = 0x5F336574696C7173LL; (int)v22 >= 0; v22 = (unsigned int)(v22 - 1) )
  {
    v23 = a2[v22];
    if ( v23 == 47 )
      break;
    if ( v23 == 92 )
      break;
  }
  v24 = &a2[(int)v22 + 1];
  if ( v24 )
  {
    v26 = 3;
    v27 = "lib";
    while ( 1 )
    {
      --v26;
      if ( !*v24
        || *((_BYTE *)qword_180114680 + *(unsigned __int8 *)v24) != *((_BYTE *)qword_180114680 + *(unsigned __int8 *)v27) )
      {
        break;
      }
      ++v24;
      ++v27;
      if ( v26 <= 0 )
      {
        --v26;
        break;
      }
    }
    v25 = v26 >= 0
        ? *((unsigned __int8 *)qword_180114680 + *(unsigned __int8 *)v24)
        - *((unsigned __int8 *)qword_180114680 + *(unsigned __int8 *)v27)
        : 0;
  }
  else
  {
    v25 = -1;
  }
  v28 = 4;
  if ( v25 )
    v28 = 1;
  v29 = v28 + v22;
  v30 = 8;
  for ( i = a2[v29]; a2[v29]; i = a2[++v29] )
  {
    if ( i == 46 )
      break;
    if ( (*((_BYTE *)&qword_1801147A0 + (unsigned __int8)i) & 2) != 0 )
    {
      v32 = i;
      v33 = v30++;
      v20[v33] = *((_BYTE *)qword_180114680 + v32);
    }
  }
  strcpy(&v20[v30], "_init");
  v19 = (__int64 (__fastcall *)(__int64 *, const char **, __int64 (__fastcall **)()))(*(__int64 (__fastcall **)(__int64, __int64, char *))(v4 + 88))(
                                                                                       v4,
                                                                                       v13,
                                                                                       v20);
  if ( !v19 )
  {
LABEL_59:
    if ( a4 )
    {
      v38 = strlen_0(v12);
      if ( (unsigned int)sqlite3_initialize(v40, v39) )
      {
        v52 = 0;
        *a4 = 0;
      }
      else
      {
        v41 = v54 + v38;
        v42 = (const char *)sqlite3Malloc(v41 + 300);
        v52 = v42;
        *a4 = v42;
        if ( v42 )
        {
          sqlite3_snprintf((unsigned int)(v41 + 300), v42, "no entry point [%s] in shared library [%s]", v12, a2);
          (*(void (__fastcall **)(__int64, _QWORD, const char *))(v4 + 80))(v4, (unsigned int)(v41 + 299), v52);
        }
      }
    }
    (*(void (__fastcall **)(__int64, __int64))(v4 + 96))(v4, v13);
    if ( v20 )
    {
      if ( dword_18013C1B0 )
      {
        if ( (_QWORD)xmmword_18013FC60 )
          ((void (*)(void))xmmword_18013C230)();
        v43 = ((__int64 (__fastcall *)(char *))xmmword_18013C1E8)(v20);
        --qword_18013FBE8;
        qword_18013FBA0 -= v43;
        ((void (__fastcall *)(char *))xmmword_18013C1D8)(v20);
        if ( (_QWORD)xmmword_18013FC60 )
          ((void (*)(void))xmmword_18013C240)();
      }
      else
      {
        ((void (__fastcall *)(char *))xmmword_18013C1D8)(v20);
      }
    }
    return 1;
  }
  if ( !dword_18013C1B0 )
  {
    v35 = (void (*)(void))xmmword_18013C1D8;
    goto LABEL_50;
  }
  if ( (_QWORD)xmmword_18013FC60 )
    ((void (*)(void))xmmword_18013C230)();
  v34 = ((__int64 (__fastcall *)(char *))xmmword_18013C1E8)(v20);
  --qword_18013FBE8;
  qword_18013FBA0 -= v34;
  ((void (__fastcall *)(char *))xmmword_18013C1D8)(v20);
  if ( (_QWORD)xmmword_18013FC60 )
  {
    v35 = (void (*)(void))xmmword_18013C240;
LABEL_50:
    v35();
  }
LABEL_51:
  v36 = v19(a1, &v52, off_18010E060);
  if ( !v36 )
  {
    v44 = 8LL * *((int *)a1 + 59) + 8;
    v45 = (void *)sqlite3DbMallocRawNN(a1, v44);
    v46 = v45;
    if ( v45 )
    {
      memset_0(v45, 0, v44);
      v47 = *((int *)a1 + 59);
      if ( (int)v47 > 0 )
        memcpy_0(v46, (const void *)a1[30], 8 * v47);
      v48 = (_QWORD *)a1[30];
      if ( !v48 )
        goto LABEL_83;
      if ( (unsigned __int64)v48 < a1[62] )
      {
        if ( (unsigned __int64)v48 >= a1[60] )
        {
          *v48 = a1[59];
          a1[59] = (__int64)v48;
LABEL_83:
          v49 = *((int *)a1 + 59);
          a1[30] = (__int64)v46;
          *((_QWORD *)v46 + v49) = v13;
          ++*((_DWORD *)a1 + 59);
          return 0;
        }
        if ( (unsigned __int64)v48 >= a1[61] )
        {
          *v48 = a1[57];
          a1[57] = (__int64)v48;
          goto LABEL_83;
        }
      }
      if ( a1[97] )
        measureAllocationSize(a1, a1[30]);
      else
        sqlite3_free(v48);
      goto LABEL_83;
    }
    return 7;
  }
  if ( v36 == 256 )
    return 0;
  if ( a4 )
    *a4 = (const char *)sqlite3_mprintf("error during initialization: %s", v52);
  sqlite3_free(v52);
  (*(void (__fastcall **)(__int64, __int64))(v4 + 96))(v4, v13);
  return 1;
}

```

## disassembly

```asm
0x180087630  mov     [rsp+arg_10], r8
0x180087635  push    rbx
0x180087636  push    rbp
0x180087637  push    rsi
0x180087638  push    rdi
0x180087639  push    r12
0x18008763b  push    r14
0x18008763d  push    r15
0x18008763f  sub     rsp, 40h
0x180087643  mov     rbp, [rcx]
0x180087646  mov     rbx, rcx
0x180087649  xor     r14d, r14d
0x18008764c  mov     rcx, rdx; Str
0x18008764f  mov     [rsp+78h+arg_0], r14
0x180087657  mov     r12, r9
0x18008765a  mov     rdi, r8
0x18008765d  mov     r15, rdx
0x180087660  call    strlen_0
0x180087665  mov     [rsp+78h+arg_18], rax
0x18008766d  mov     rsi, rax
0x180087670  test    r12, r12
0x180087673  jz      short loc_180087679
0x180087675  mov     [r12], r14
0x180087679  mov     eax, [rbx+30h]
0x18008767c  mov     [rsp+78h+arg_8], r13
0x180087684  bt      rax, 10h
0x180087689  jb      short loc_1800876A9
0x18008768b  test    r12, r12
0x18008768e  jz      loc_180087CB4
0x180087694  lea     rcx, aNotAuthorized; "not authorized"
0x18008769b  call    sqlite3_mprintf
0x1800876a0  mov     [r12], rax
0x1800876a4  jmp     loc_180087CB4
0x1800876a9  test    rdi, rdi
0x1800876ac  lea     r13, aSqlite3Extensi; "sqlite3_extension_init"
0x1800876b3  lea     rax, [rsi-1]
0x1800876b7  cmovnz  r13, rdi
0x1800876bb  cmp     rax, 103h
0x1800876c1  ja      loc_180087C49
0x1800876c7  mov     rax, [rbp+48h]
0x1800876cb  mov     rdx, r15
0x1800876ce  mov     rcx, rbp
0x1800876d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800876d6  mov     r14, rax
0x1800876d9  mov     [rsp+78h+var_48], rax
0x1800876de  lea     rax, cs:180000000h
0x1800876e5  xor     edi, edi
0x1800876e7  test    r14, r14
0x1800876ea  jnz     loc_18008777A
0x1800876f0  lea     r14, rva off_18013D218[rax]; "dll" ...
0x1800876f7  mov     rdx, r15
0x1800876fa  mov     r8, [r14+rdi*8]
0x1800876fe  lea     r14, [r14+rdi*8]
0x180087702  lea     rcx, aSS_2; "%s.%s"
0x180087709  call    sqlite3_mprintf
0x18008770e  mov     rsi, rax
0x180087711  test    rax, rax
0x180087714  jz      loc_180087A2F
0x18008771a  mov     rcx, [r14]; Str
0x18008771d  call    strlen_0
0x180087722  mov     rcx, [rsp+78h+arg_18]
0x18008772a  inc     rcx
0x18008772d  add     rcx, rax
0x180087730  cmp     rcx, 104h
0x180087737  ja      short loc_180087752
0x180087739  mov     rax, [rbp+48h]
0x18008773d  mov     rdx, rsi
0x180087740  mov     rcx, rbp
0x180087743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087748  mov     r14, rax
0x18008774b  mov     [rsp+78h+var_48], rax
0x180087750  jmp     short loc_180087757
0x180087752  mov     r14, [rsp+78h+var_48]
0x180087757  mov     rcx, rsi
0x18008775a  call    sqlite3_free
0x18008775f  inc     edi
0x180087761  lea     rax, cs:180000000h
0x180087768  cmp     edi, 1
0x18008776b  jl      loc_1800876E7
0x180087771  test    r14, r14
0x180087774  jz      loc_180087C3E
0x18008777a  mov     rax, [rbp+58h]
0x18008777e  mov     r8, r13
0x180087781  mov     rdx, r14
0x180087784  mov     rcx, rbp
0x180087787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008778c  mov     rdi, rax
0x18008778f  mov     esi, 1
0x180087794  test    rax, rax
0x180087797  jnz     loc_1800879A4
0x18008779d  xor     esi, esi
0x18008779f  cmp     [rsp+78h+arg_10], rsi
0x1800877a7  jnz     loc_180087A39
0x1800877ad  test    r15, r15
0x1800877b0  jz      short loc_1800877C3
0x1800877b2  mov     rcx, r15; Str
0x1800877b5  call    strlen_0
0x1800877ba  mov     rdi, rax
0x1800877bd  and     edi, 3FFFFFFFh
0x1800877c3  call    sqlite3_initialize
0x1800877c8  test    eax, eax
0x1800877ca  jnz     loc_180087A20
0x1800877d0  lea     ecx, [rdi+1Eh]
0x1800877d3  call    sqlite3Malloc
0x1800877d8  mov     rsi, rax
0x1800877db  test    rax, rax
0x1800877de  jz      loc_180087A20
0x1800877e4  mov     r13, rax
0x1800877e7  lea     r8d, [rdi-1]
0x1800877eb  mov     rax, 5F336574696C7173h
0x1800877f5  mov     [r13+0], rax
0x1800877f9  test    r8d, r8d
0x1800877fc  js      short loc_180087815
0x1800877fe  xchg    ax, ax
0x180087800  movzx   ecx, byte ptr [r8+r15]
0x180087805  cmp     cl, 2Fh ; '/'
0x180087808  jz      short loc_180087815
0x18008780a  cmp     cl, 5Ch ; '\'
0x18008780d  jz      short loc_180087815
0x18008780f  sub     r8d, 1
0x180087813  jns     short loc_180087800
0x180087815  lea     eax, [r8+1]
0x180087819  movsxd  r9, eax
0x18008781c  add     r9, r15
0x18008781f  jnz     short loc_18008782F
0x180087821  mov     edx, 0FFFFFFFFh
0x180087826  lea     r10, cs:180000000h
0x18008782d  jmp     short loc_1800878A3
0x18008782f  mov     edx, 3
0x180087834  lea     r10, aLib; "lib"
0x18008783b  lea     r11, cs:180000000h
0x180087842  movzx   eax, byte ptr [r9]
0x180087846  dec     edx
0x180087848  test    al, al
0x18008784a  jz      short loc_180087871
0x18008784c  mov     ecx, eax
0x18008784e  movzx   eax, byte ptr [r10]
0x180087852  movzx   eax, byte ptr [rax+r11+114680h]
0x18008785b  cmp     [rcx+r11+114680h], al
0x180087863  jnz     short loc_180087871
0x180087865  inc     r9
0x180087868  inc     r10
0x18008786b  test    edx, edx
0x18008786d  jg      short loc_180087842
0x18008786f  dec     edx
0x180087871  test    edx, edx
0x180087873  jns     short loc_180087880
0x180087875  xor     edx, edx
0x180087877  lea     r10, cs:180000000h
0x18008787e  jmp     short loc_1800878A3
0x180087880  movzx   eax, byte ptr [r10]
0x180087884  lea     r10, cs:180000000h
0x18008788b  movzx   ecx, byte ptr [rax+r10+114680h]
0x180087894  movzx   eax, byte ptr [r9]
0x180087898  movzx   edx, byte ptr [rax+r10+114680h]
0x1800878a1  sub     edx, ecx
0x1800878a3  test    edx, edx
0x1800878a5  mov     eax, 4
0x1800878aa  mov     ecx, 1
0x1800878af  cmovnz  eax, ecx
0x1800878b2  lea     edx, [rax+r8]
0x1800878b6  mov     r8d, 8
0x1800878bc  movsxd  rax, edx
0x1800878bf  movsx   ecx, byte ptr [rax+r15]
0x1800878c4  test    ecx, ecx
0x1800878c6  jz      short loc_1800878FD
0x1800878c8  cmp     ecx, 2Eh ; '.'
0x1800878cb  jz      short loc_1800878FD
0x1800878cd  movzx   eax, cl
0x1800878d0  test    byte ptr [rax+r10+1147A0h], 2
0x1800878d9  jz      short loc_1800878EF
0x1800878db  mov     eax, ecx
0x1800878dd  movsxd  rcx, r8d
0x1800878e0  inc     r8d
0x1800878e3  movzx   eax, byte ptr [rax+r10+114680h]
0x1800878ec  mov     [rcx+rsi], al
0x1800878ef  inc     edx
0x1800878f1  movsxd  rax, edx
0x1800878f4  movsx   ecx, byte ptr [rax+r15]
0x1800878f9  test    ecx, ecx
0x1800878fb  jnz     short loc_1800878C8
0x1800878fd  mov     eax, dword ptr cs:aInit; "_init"
0x180087903  mov     rdx, r14
0x180087906  movsxd  rcx, r8d
0x180087909  mov     r8, rsi
0x18008790c  mov     [rcx+rsi], eax
0x18008790f  movzx   eax, word ptr cs:aInit+4; "t"
0x180087916  mov     [rcx+rsi+4], ax
0x18008791b  mov     rcx, rbp
0x18008791e  mov     rax, [rbp+58h]
0x180087922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087927  mov     rdi, rax
0x18008792a  test    rax, rax
0x18008792d  jz      loc_180087A39
0x180087933  cmp     cs:dword_18013C1B0, 0
0x18008793a  jz      loc_180087A11
0x180087940  mov     rcx, qword ptr cs:xmmword_18013FC60
0x180087947  test    rcx, rcx
0x18008794a  jz      short loc_180087958
0x18008794c  mov     rax, qword ptr cs:xmmword_18013C230
0x180087953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087958  mov     rax, qword ptr cs:xmmword_18013C1E8
0x18008795f  mov     rcx, rsi
0x180087962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087967  dec     cs:qword_18013FBE8
0x18008796e  movsxd  rcx, eax
0x180087971  sub     cs:qword_18013FBA0, rcx
0x180087978  mov     rcx, rsi
0x18008797b  mov     rax, qword ptr cs:xmmword_18013C1D8
0x180087982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087987  mov     rcx, qword ptr cs:xmmword_18013FC60
0x18008798e  test    rcx, rcx
0x180087991  jz      short loc_18008799F
0x180087993  mov     rax, qword ptr cs:xmmword_18013C240
0x18008799a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008799f  mov     esi, 1
0x1800879a4  lea     r8, off_18010E060
0x1800879ab  mov     rcx, rbx
0x1800879ae  lea     rdx, [rsp+78h+arg_0]
0x1800879b6  mov     rax, rdi
0x1800879b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800879be  test    eax, eax
0x1800879c0  jz      loc_180087B65
0x1800879c6  cmp     eax, 100h
0x1800879cb  jz      loc_180087C3A
0x1800879d1  test    r12, r12
0x1800879d4  jz      short loc_1800879EE
0x1800879d6  mov     rdx, [rsp+78h+arg_0]
0x1800879de  lea     rcx, aErrorDuringIni; "error during initialization: %s"
0x1800879e5  call    sqlite3_mprintf
0x1800879ea  mov     [r12], rax
0x1800879ee  mov     rcx, [rsp+78h+arg_0]
0x1800879f6  call    sqlite3_free
0x1800879fb  mov     rax, [rbp+60h]
0x1800879ff  mov     rdx, r14
0x180087a02  mov     rcx, rbp
0x180087a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087a0a  mov     eax, esi
0x180087a0c  jmp     loc_180087CB9
0x180087a11  mov     rax, qword ptr cs:xmmword_18013C1D8
0x180087a18  mov     rcx, rsi
0x180087a1b  jmp     loc_18008799A
0x180087a20  mov     rax, [rbp+60h]
0x180087a24  mov     rdx, r14
0x180087a27  mov     rcx, rbp
0x180087a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087a2f  mov     eax, 7
0x180087a34  jmp     loc_180087CB9
0x180087a39  test    r12, r12
0x180087a3c  jz      loc_180087AC8
0x180087a42  mov     rcx, r13; Str
0x180087a45  call    strlen_0
0x180087a4a  mov     rbx, rax
0x180087a4d  call    sqlite3_initialize
0x180087a52  test    eax, eax
0x180087a54  jz      short loc_180087A6C
0x180087a56  mov     [rsp+78h+arg_0], 0
0x180087a62  mov     qword ptr [r12], 0
0x180087a6a  jmp     short loc_180087AC8
0x180087a6c  add     rbx, [rsp+78h+arg_18]
0x180087a74  lea     rcx, [rbx+12Ch]
0x180087a7b  call    sqlite3Malloc
0x180087a80  mov     [rsp+78h+arg_0], rax
0x180087a88  mov     [r12], rax
0x180087a8c  test    rax, rax
0x180087a8f  jz      short loc_180087AC8
0x180087a91  mov     r9, r13
0x180087a94  mov     [rsp+78h+var_58], r15
0x180087a99  lea     r8, aNoEntryPointSI; "no entry point [%s] in shared library ["...
0x180087aa0  mov     rdx, rax
0x180087aa3  lea     ecx, [rbx+12Ch]
0x180087aa9  call    sqlite3_snprintf
0x180087aae  mov     r8, [rsp+78h+arg_0]
0x180087ab6  lea     edx, [rbx+12Bh]
0x180087abc  mov     rax, [rbp+50h]
0x180087ac0  mov     rcx, rbp
0x180087ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087ac8  mov     rax, [rbp+60h]
0x180087acc  mov     rdx, r14
0x180087acf  mov     rcx, rbp
0x180087ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087ad7  test    rsi, rsi
0x180087ada  jz      loc_180087CB4
0x180087ae0  cmp     cs:dword_18013C1B0, 0
0x180087ae7  jz      short loc_180087B51
0x180087ae9  mov     rcx, qword ptr cs:xmmword_18013FC60
0x180087af0  test    rcx, rcx
0x180087af3  jz      short loc_180087B01
0x180087af5  mov     rax, qword ptr cs:xmmword_18013C230
0x180087afc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087b01  mov     rax, qword ptr cs:xmmword_18013C1E8
0x180087b08  mov     rcx, rsi
0x180087b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087b10  dec     cs:qword_18013FBE8
0x180087b17  mov     rcx, rsi
0x180087b1a  movsxd  rdx, eax
0x180087b1d  mov     rax, qword ptr cs:xmmword_18013C1D8
0x180087b24  sub     cs:qword_18013FBA0, rdx
0x180087b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087b30  mov     rcx, qword ptr cs:xmmword_18013FC60
  ... truncated ...
```
