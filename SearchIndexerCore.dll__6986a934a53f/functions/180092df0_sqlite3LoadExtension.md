# sqlite3LoadExtension

- ea: `0x180092df0`
- end: `0x180093266`
- name: `sqlite3LoadExtension`
- size: `1142`
- prototype: `__int64 __fastcall(__int64 *, const char *, const char *, const char **)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18009ce80`

## callees

- `0x18001eb90`
- `0x1800310a0`
- `0x18003d380`
- `0x18003d760`
- `0x180041d10`
- `0x180041eb0`
- `0x180047da0`
- `0x18004ae40`
- `0x180092df0`
- `0x1800af620`
- `0x1800b0010`

## string_xrefs

- `0x180092e63`: `sqlite3_extension_init`
- `0x18009315a`: `error during initialization: %s`
- `0x180093229`: `unable to open shared library [%.*s]`

## pseudocode

```c
__int64 __fastcall sqlite3LoadExtension(__int64 *a1, const char *a2, const char *a3, const char **a4)
{
  __int64 v4; // rdi
  __int64 v8; // r14
  const char *v9; // r13
  __int64 v10; // r15
  int i; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rax
  _QWORD *v15; // r14
  __int64 v16; // r13
  int v18; // eax
  int v19; // r8d
  int v20; // edx
  unsigned int j; // ecx
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rcx
  int v25; // ebx
  const char *v26; // rax
  int v27; // eax
  void *v28; // rdi
  __int64 v29; // rax
  __int64 v30; // rax
  const char *v31; // rax
  __int64 v32; // [rsp+30h] [rbp-58h]
  __int64 v33; // [rsp+38h] [rbp-50h]
  __int64 v34; // [rsp+40h] [rbp-48h]
  int v35; // [rsp+90h] [rbp+8h]
  __int64 (__fastcall *v36)(__int64 *, const char **, __int64 (__fastcall **)()); // [rsp+90h] [rbp+8h]
  const char *v38; // [rsp+A8h] [rbp+20h] BYREF

  v4 = *a1;
  v38 = 0;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  v34 = v8;
  if ( a4 )
    *a4 = 0;
  if ( (a1[6] & 0x10000) != 0 )
  {
    v9 = a3;
    if ( !a3 )
      v9 = "sqlite3_extension_init";
    if ( (unsigned __int64)(v8 - 1) > 0x103 )
    {
LABEL_53:
      if ( a4 )
      {
        v31 = (const char *)sqlite3_malloc64(v8 + 300);
        v38 = v31;
        *a4 = v31;
        if ( v31 )
        {
          sqlite3_snprintf((unsigned int)(v8 + 300), v31, "unable to open shared library [%.*s]", 260, a2);
          (*(void (__fastcall **)(__int64, _QWORD, const char *))(v4 + 80))(v4, (unsigned int)(v8 + 299), v38);
        }
      }
      return 1;
    }
    v10 = (*(__int64 (__fastcall **)(__int64))(v4 + 72))(v4);
    for ( i = 0; ; i = v35 + 1 )
    {
      v35 = i;
      if ( i >= 1 )
        break;
      if ( v10 )
        goto LABEL_21;
      v32 = i;
      v33 = sqlite3_mprintf("%s.%s", a2, off_1800B29A8[i]);
      v12 = v33;
      if ( !v33 )
        return 7;
      v13 = -1;
      do
        ++v13;
      while ( off_1800B29A8[v32][v13] );
      if ( (unsigned __int64)(v13 + v8 + 1) <= 0x104 )
      {
        v14 = (*(__int64 (__fastcall **)(__int64, __int64))(v4 + 72))(v4, v33);
        v12 = v33;
        v10 = v14;
      }
      sqlite3_free(v12);
    }
    if ( !v10 )
      goto LABEL_53;
LABEL_21:
    v15 = 0;
    v36 = (__int64 (__fastcall *)(__int64 *, const char **, __int64 (__fastcall **)()))(*(__int64 (__fastcall **)(__int64, __int64, const char *))(v4 + 88))(
                                                                                         v4,
                                                                                         v10,
                                                                                         v9);
    if ( !v36 )
    {
      if ( a3 )
        goto LABEL_37;
      v16 = (int)sqlite3Strlen30(a2);
      v15 = (_QWORD *)sqlite3_malloc64(v16 + 30);
      if ( !v15 )
      {
        (*(void (__fastcall **)(__int64, __int64))(v4 + 96))(v4, v10);
        return 7;
      }
      *v15 = 0x5F336574696C7173LL;
      do
        LODWORD(v16) = v16 - 1;
      while ( (int)v16 >= 0 && a2[(unsigned int)v16] != 47 && a2[(unsigned int)v16] != 92 );
      v18 = sqlite3_strnicmp(&a2[(int)v16 + 1], "lib", 3);
      v19 = 8;
      v20 = v16 + (v18 != 0 ? 1 : 4);
      for ( j = a2[v20]; a2[v20]; j = a2[++v20] )
      {
        if ( j == 46 )
          break;
        if ( (*((_BYTE *)&qword_1800B4FF0 + (unsigned __int8)j) & 2) != 0 )
        {
          v22 = j;
          v23 = v19++;
          *((_BYTE *)v15 + v23) = *((_BYTE *)qword_1800B4ED0 + v22);
        }
      }
      strcpy((char *)v15 + v19, "_init");
      v36 = (__int64 (__fastcall *)(__int64 *, const char **, __int64 (__fastcall **)()))(*(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(v4 + 88))(
                                                                                           v4,
                                                                                           v10,
                                                                                           v15);
      if ( !v36 )
      {
        v9 = (const char *)v15;
LABEL_37:
        if ( a4 )
        {
          v24 = -1;
          do
            ++v24;
          while ( v9[v24] );
          v25 = v24 + v34;
          v26 = (const char *)sqlite3_malloc64(v24 + v34 + 300);
          v38 = v26;
          *a4 = v26;
          if ( v26 )
          {
            sqlite3_snprintf((unsigned int)(v25 + 300), v26, "no entry point [%s] in shared library [%s]", v9, a2);
            (*(void (__fastcall **)(__int64, _QWORD, const char *))(v4 + 80))(v4, (unsigned int)(v25 + 299), v38);
          }
        }
        (*(void (__fastcall **)(__int64, __int64))(v4 + 96))(v4, v10);
        sqlite3_free(v15);
        return 1;
      }
    }
    sqlite3_free(v15);
    v27 = v36(a1, &v38, off_1800B1DA0);
    if ( v27 )
    {
      if ( v27 != 256 )
      {
        if ( a4 )
          *a4 = (const char *)sqlite3_mprintf("error during initialization: %s", v38);
        sqlite3_free(v38);
        (*(void (__fastcall **)(__int64, __int64))(v4 + 96))(v4, v10);
        return 1;
      }
    }
    else
    {
      v28 = (void *)sqlite3DbMallocZero(a1, 8LL * *((int *)a1 + 59) + 8);
      if ( !v28 )
        return 7;
      v29 = *((int *)a1 + 59);
      if ( (int)v29 > 0 )
        memcpy_0(v28, (const void *)a1[30], 8 * v29);
      sqlite3DbFree(a1, a1[30]);
      v30 = *((int *)a1 + 59);
      a1[30] = (__int64)v28;
      *((_QWORD *)v28 + v30) = v10;
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
0x180092df0  mov     rax, rsp
0x180092df3  mov     [rax+18h], r8
0x180092df7  push    rbx
0x180092df8  push    rsi
0x180092df9  push    rdi
0x180092dfa  push    r12
0x180092dfc  push    r13
0x180092dfe  push    r14
0x180092e00  push    r15
0x180092e02  sub     rsp, 50h
0x180092e06  mov     rdi, [rcx]
0x180092e09  mov     rsi, r9
0x180092e0c  mov     r12, rdx
0x180092e0f  mov     qword ptr [rax+20h], 0
0x180092e17  mov     rbx, rcx
0x180092e1a  or      r14, 0FFFFFFFFFFFFFFFFh
0x180092e1e  inc     r14
0x180092e21  cmp     byte ptr [rdx+r14], 0
0x180092e26  jnz     short loc_180092E1E
0x180092e28  mov     [rsp+88h+var_48], r14
0x180092e2d  test    rsi, rsi
0x180092e30  jz      short loc_180092E39
0x180092e32  mov     qword ptr [r9], 0
0x180092e39  mov     eax, [rcx+30h]
0x180092e3c  bt      rax, 10h
0x180092e41  jb      short loc_180092E60
0x180092e43  test    rsi, rsi
0x180092e46  jz      loc_180093251
0x180092e4c  lea     rcx, aNotAuthorized; "not authorized"
0x180092e53  call    sqlite3_mprintf
0x180092e58  mov     [rsi], rax
0x180092e5b  jmp     loc_180093251
0x180092e60  test    r8, r8
0x180092e63  lea     rax, aSqlite3Extensi; "sqlite3_extension_init"
0x180092e6a  mov     r13, r8
0x180092e6d  cmovz   r13, rax
0x180092e71  lea     rax, [r14-1]
0x180092e75  cmp     rax, 103h
0x180092e7b  ja      loc_1800931FA
0x180092e81  mov     rax, [rdi+48h]
0x180092e85  mov     rcx, rdi
0x180092e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092e8d  mov     r15, rax
0x180092e90  xor     eax, eax
0x180092e92  mov     dword ptr [rsp+88h+arg_0], eax
0x180092e99  lea     rcx, __ImageBase
0x180092ea0  cmp     eax, 1
0x180092ea3  jge     loc_180092F3C
0x180092ea9  test    r15, r15
0x180092eac  jnz     loc_180092F45
0x180092eb2  cdqe
0x180092eb4  mov     rdx, r12
0x180092eb7  mov     [rsp+88h+var_58], rax
0x180092ebc  mov     r8, ds:rva off_1800B29A8[rcx+rax*8]; "dll" ...
0x180092ec4  lea     rcx, aSS_2; "%s.%s"
0x180092ecb  call    sqlite3_mprintf
0x180092ed0  mov     [rsp+88h+var_50], rax
0x180092ed5  mov     rdx, rax
0x180092ed8  test    rax, rax
0x180092edb  jz      loc_180092FA4
0x180092ee1  mov     rax, [rsp+88h+var_58]
0x180092ee6  lea     r9, __ImageBase
0x180092eed  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180092ef1  mov     r8, ds:rva off_1800B29A8[r9+rax*8]; "dll" ...
0x180092ef9  inc     rcx
0x180092efc  cmp     byte ptr [r8+rcx], 0
0x180092f01  jnz     short loc_180092EF9
0x180092f03  lea     rax, [r14+1]
0x180092f07  add     rax, rcx
0x180092f0a  cmp     rax, 104h
0x180092f10  ja      short loc_180092F26
0x180092f12  mov     rax, [rdi+48h]
0x180092f16  mov     rcx, rdi
0x180092f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092f1e  mov     rdx, [rsp+88h+var_50]
0x180092f23  mov     r15, rax
0x180092f26  mov     rcx, rdx
0x180092f29  call    sqlite3_free
0x180092f2e  mov     eax, dword ptr [rsp+88h+arg_0]
0x180092f35  inc     eax
0x180092f37  jmp     loc_180092E92
0x180092f3c  test    r15, r15
0x180092f3f  jz      loc_1800931FA
0x180092f45  mov     rax, [rdi+58h]
0x180092f49  mov     r8, r13
0x180092f4c  mov     rdx, r15
0x180092f4f  mov     rcx, rdi
0x180092f52  xor     r14d, r14d
0x180092f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092f5a  mov     [rsp+88h+arg_0], rax
0x180092f62  test    rax, rax
0x180092f65  jnz     loc_180093114
0x180092f6b  cmp     [rsp+88h+arg_10], r14
0x180092f73  jnz     loc_18009308A
0x180092f79  mov     rcx, r12
0x180092f7c  call    sqlite3Strlen30
0x180092f81  movsxd  r13, eax
0x180092f84  lea     rcx, [r13+1Eh]
0x180092f88  call    sqlite3_malloc64
0x180092f8d  mov     r14, rax
0x180092f90  test    rax, rax
0x180092f93  jnz     short loc_180092FAE
0x180092f95  mov     rax, [rdi+60h]
0x180092f99  mov     rdx, r15
0x180092f9c  mov     rcx, rdi
0x180092f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092fa4  mov     eax, 7
0x180092fa9  jmp     loc_180093256
0x180092fae  mov     rax, 5F336574696C7173h
0x180092fb8  mov     [r14], rax
0x180092fbb  jmp     short loc_180092FCD
0x180092fbd  cmp     byte ptr [r13+r12+0], 2Fh ; '/'
0x180092fc3  jz      short loc_180092FD3
0x180092fc5  cmp     byte ptr [r13+r12+0], 5Ch ; '\'
0x180092fcb  jz      short loc_180092FD3
0x180092fcd  sub     r13d, 1
0x180092fd1  jns     short loc_180092FBD
0x180092fd3  lea     eax, [r13+1]
0x180092fd7  mov     r8d, 3
0x180092fdd  movsxd  rcx, eax
0x180092fe0  lea     rdx, aLib; "lib"
0x180092fe7  add     rcx, r12
0x180092fea  call    sqlite3_strnicmp
0x180092fef  neg     eax
0x180092ff1  mov     r8d, 8
0x180092ff7  sbb     ecx, ecx
0x180092ff9  and     ecx, 0FFFFFFFDh
0x180092ffc  lea     edx, [rcx+4]
0x180092fff  add     edx, r13d
0x180093002  movsxd  rax, edx
0x180093005  movsx   ecx, byte ptr [rax+r12]
0x18009300a  test    ecx, ecx
0x18009300c  jz      short loc_18009304A
0x18009300e  lea     r9, __ImageBase
0x180093015  cmp     ecx, 2Eh ; '.'
0x180093018  jz      short loc_18009304A
0x18009301a  movzx   eax, cl
0x18009301d  test    byte ptr [rax+r9+0B4FF0h], 2
0x180093026  jz      short loc_18009303C
0x180093028  mov     eax, ecx
0x18009302a  movsxd  rcx, r8d
0x18009302d  inc     r8d
0x180093030  mov     al, [rax+r9+0B4ED0h]
0x180093038  mov     [rcx+r14], al
0x18009303c  inc     edx
0x18009303e  movsxd  rax, edx
0x180093041  movsx   ecx, byte ptr [rax+r12]
0x180093046  test    ecx, ecx
0x180093048  jnz     short loc_180093015
0x18009304a  mov     eax, dword ptr cs:aInit; "_init"
0x180093050  mov     rdx, r15
0x180093053  movsxd  rcx, r8d
0x180093056  mov     r8, r14
0x180093059  mov     [rcx+r14], eax
0x18009305d  movzx   eax, word ptr cs:aInit+4; "t"
0x180093064  mov     [rcx+r14+4], ax
0x18009306a  mov     rcx, rdi
0x18009306d  mov     rax, [rdi+58h]
0x180093071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093076  mov     [rsp+88h+arg_0], rax
0x18009307e  test    rax, rax
0x180093081  jnz     loc_180093114
0x180093087  mov     r13, r14
0x18009308a  test    rsi, rsi
0x18009308d  jz      short loc_1800930F8
0x18009308f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180093093  inc     rcx
0x180093096  cmp     byte ptr [rcx+r13], 0
0x18009309b  jnz     short loc_180093093
0x18009309d  mov     rbx, [rsp+88h+var_48]
0x1800930a2  add     rbx, rcx
0x1800930a5  lea     rcx, [rbx+12Ch]
0x1800930ac  call    sqlite3_malloc64
0x1800930b1  mov     [rsp+88h+arg_18], rax
0x1800930b9  mov     [rsi], rax
0x1800930bc  test    rax, rax
0x1800930bf  jz      short loc_1800930F8
0x1800930c1  mov     r9, r13
0x1800930c4  mov     [rsp+88h+var_68], r12
0x1800930c9  lea     r8, aNoEntryPointSI; "no entry point [%s] in shared library ["...
0x1800930d0  mov     rdx, rax
0x1800930d3  lea     ecx, [rbx+12Ch]
0x1800930d9  call    sqlite3_snprintf
0x1800930de  mov     r8, [rsp+88h+arg_18]
0x1800930e6  lea     edx, [rbx+12Bh]
0x1800930ec  mov     rax, [rdi+50h]
0x1800930f0  mov     rcx, rdi
0x1800930f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800930f8  mov     rax, [rdi+60h]
0x1800930fc  mov     rdx, r15
0x1800930ff  mov     rcx, rdi
0x180093102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093107  mov     rcx, r14
0x18009310a  call    sqlite3_free
0x18009310f  jmp     loc_180093251
0x180093114  mov     rcx, r14
0x180093117  call    sqlite3_free
0x18009311c  mov     rax, [rsp+88h+arg_0]
0x180093124  lea     r8, off_1800B1DA0
0x18009312b  lea     rdx, [rsp+88h+arg_18]
0x180093133  mov     rcx, rbx
0x180093136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009313b  test    eax, eax
0x18009313d  jz      short loc_18009318A
0x18009313f  cmp     eax, 100h
0x180093144  jnz     short loc_18009314D
0x180093146  xor     eax, eax
0x180093148  jmp     loc_180093256
0x18009314d  test    rsi, rsi
0x180093150  jz      short loc_180093169
0x180093152  mov     rdx, [rsp+88h+arg_18]
0x18009315a  lea     rcx, aErrorDuringIni; "error during initialization: %s"
0x180093161  call    sqlite3_mprintf
0x180093166  mov     [rsi], rax
0x180093169  mov     rcx, [rsp+88h+arg_18]
0x180093171  call    sqlite3_free
0x180093176  mov     rax, [rdi+60h]
0x18009317a  mov     rdx, r15
0x18009317d  mov     rcx, rdi
0x180093180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093185  jmp     loc_180093251
0x18009318a  movsxd  rdx, dword ptr [rbx+0ECh]
0x180093191  mov     rcx, rbx
0x180093194  lea     rdx, ds:8[rdx*8]
0x18009319c  call    sqlite3DbMallocZero
0x1800931a1  mov     rdi, rax
0x1800931a4  test    rax, rax
0x1800931a7  jz      loc_180092FA4
0x1800931ad  movsxd  rax, dword ptr [rbx+0ECh]
0x1800931b4  test    eax, eax
0x1800931b6  jle     short loc_1800931CE
0x1800931b8  mov     rdx, [rbx+0F0h]; Src
0x1800931bf  mov     r8, rax
0x1800931c2  shl     r8, 3; Size
0x1800931c6  mov     rcx, rdi; void *
0x1800931c9  call    memcpy_0
0x1800931ce  mov     rdx, [rbx+0F0h]
0x1800931d5  mov     rcx, rbx
0x1800931d8  call    sqlite3DbFree
0x1800931dd  movsxd  rax, dword ptr [rbx+0ECh]
0x1800931e4  mov     [rbx+0F0h], rdi
0x1800931eb  mov     [rdi+rax*8], r15
0x1800931ef  inc     dword ptr [rbx+0ECh]
0x1800931f5  jmp     loc_180093146
0x1800931fa  test    rsi, rsi
0x1800931fd  jz      short loc_180093251
0x1800931ff  lea     rbx, [r14+12Ch]
0x180093206  mov     rcx, rbx
0x180093209  call    sqlite3_malloc64
0x18009320e  mov     [rsp+88h+arg_18], rax
0x180093216  mov     [rsi], rax
0x180093219  test    rax, rax
0x18009321c  jz      short loc_180093251
0x18009321e  mov     r9d, 104h
0x180093224  mov     [rsp+88h+var_68], r12
0x180093229  lea     r8, aUnableToOpenSh; "unable to open shared library [%.*s]"
0x180093230  mov     rdx, rax
0x180093233  mov     ecx, ebx
0x180093235  call    sqlite3_snprintf
0x18009323a  mov     r8, [rsp+88h+arg_18]
0x180093242  lea     edx, [rbx-1]
0x180093245  mov     rax, [rdi+50h]
0x180093249  mov     rcx, rdi
0x18009324c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093251  mov     eax, 1
0x180093256  add     rsp, 50h
0x18009325a  pop     r15
0x18009325c  pop     r14
0x18009325e  pop     r13
0x180093260  pop     r12
0x180093262  pop     rdi
0x180093263  pop     rsi
0x180093264  pop     rbx
0x180093265  retn
```
