# winGetTempname

- ea: `0x18006328c`
- end: `0x180063530`
- name: `winGetTempname`
- size: `676`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x180035850`
- `0x180059100`

## callees

- `0x18001eb90`
- `0x180035784`
- `0x1800375e4`
- `0x180038d00`
- `0x180041eb0`
- `0x180047100`
- `0x18004909c`
- `0x18004ae40`
- `0x18004b758`
- `0x18006328c`
- `0x18006ee8c`
- `0x1800b0010`

## string_xrefs

- `0x1800633b0`: `winGetTempname2`
- `0x1800634f8`: `winGetTempname4`
- `0x180063312`: `winGetTempname1`
- `0x180063444`: `winGetTempname5`

## pseudocode

```c
__int64 __fastcall winGetTempname(__int64 a1, __int64 *a2)
{
  __int64 v2; // rsi
  int v4; // r14d
  __int64 v5; // rbx
  int v6; // r15d
  int v7; // eax
  const char *v8; // r9
  __int64 v9; // rax
  const char *v10; // r8
  __int64 result; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rdi
  DWORD v15; // edx
  const char *v16; // rax
  const char *v17; // rbp
  int v18; // eax
  int v19; // eax
  __int64 v20; // rdi
  __int64 v21; // rsi
  DWORD v22; // r9d
  unsigned __int8 v23; // cl
  int v24; // [rsp+20h] [rbp-48h]

  v2 = *(int *)(a1 + 8);
  v4 = v2 + 2;
  v5 = sqlite3MallocZero((int)v2 + 2);
  if ( !v5 )
    return 3082;
  v6 = v2 - 22;
  if ( !(unsigned int)winTempDirDefined() )
  {
    v13 = sqlite3MallocZero(2 * v2);
    v14 = v13;
    if ( v13 )
    {
      if ( !(unsigned int)((__int64 (__fastcall *)(_QWORD, __int64))off_1800CE108)((unsigned int)v2, v13) )
      {
        sqlite3_free(v14);
        sqlite3_free(v5);
        v15 = off_1800CE078();
        return winLogErrorAtLine(6410, v15, (unsigned int)"winGetTempname2", 0, 51639);
      }
      v16 = (const char *)winUnicodeToUtf8(v14);
      v17 = v16;
      if ( v16 )
      {
        sqlite3_snprintf((unsigned int)v2, v5, "%s", v16);
        sqlite3_free(v17);
        sqlite3_free(v14);
        goto LABEL_18;
      }
      sqlite3_free(v14);
    }
    sqlite3_free(v5);
    return 3082;
  }
  v7 = sqlite3Strlen30(sqlite3_temp_directory);
  if ( v7 > 0 )
  {
    if ( v8[v7 - 1] != 47 && v8[v7 - 1] != 92 )
      ++v7;
    if ( v7 > v6 )
    {
      v9 = sqlite3MutexAlloc(11);
      sqlite3_mutex_leave(v9);
      sqlite3_free(v5);
      v10 = "winGetTempname1";
      v24 = 51538;
      return winLogErrorAtLine(1, 0, (_DWORD)v10, 0, v24);
    }
    sqlite3_snprintf((unsigned int)v2, v5, "%s", v8);
  }
  v12 = sqlite3MutexAlloc(11);
  sqlite3_mutex_leave(v12);
LABEL_18:
  v18 = sqlite3Strlen30(v5);
  if ( v18 <= 0 )
    goto LABEL_28;
  if ( *(_BYTE *)(v18 + v5 - 1) != 92 && *(_BYTE *)(v18 + v5 - 1) != 47 )
  {
    if ( v18 + 1 < v6 + 1 )
    {
      *(_WORD *)(v18 + v5) = 92;
      goto LABEL_23;
    }
LABEL_28:
    sqlite3_free(v5);
    v10 = "winGetTempname4";
    v24 = 51689;
    return winLogErrorAtLine(1, 0, (_DWORD)v10, 0, v24);
  }
LABEL_23:
  v19 = sqlite3Strlen30(v5);
  if ( v19 + 24 > v4 )
  {
    sqlite3_free(v5);
    v10 = "winGetTempname5";
    v24 = 51707;
    return winLogErrorAtLine(1, 0, (_DWORD)v10, 0, v24);
  }
  sqlite3_snprintf((unsigned int)(v4 - v19 - 16), v5 + v19, "etilqs_");
  v20 = (int)sqlite3Strlen30(v5);
  v21 = 15;
  sqlite3_randomness(15, v5 + v20);
  v22 = off_1800CDFA0();
  do
  {
    v23 = *(_BYTE *)(v5 + v20) + v22;
    v22 >>= 8;
    *(_BYTE *)(v5 + v20++) = aAbcdefghijklmn[v23 % 0x3EuLL];
    --v21;
  }
  while ( v21 );
  *(_WORD *)(v5 + v20) = 0;
  result = 0;
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x18006328c  push    rbx
0x18006328e  push    rbp
0x18006328f  push    rsi
0x180063290  push    rdi
0x180063291  push    r12
0x180063293  push    r14
0x180063295  push    r15
0x180063297  sub     rsp, 30h
0x18006329b  movsxd  rsi, dword ptr [rcx+8]
0x18006329f  mov     r12, rdx
0x1800632a2  lea     r14d, [rsi+2]
0x1800632a6  movsxd  rcx, r14d; Size
0x1800632a9  call    sqlite3MallocZero
0x1800632ae  mov     rbx, rax
0x1800632b1  test    rax, rax
0x1800632b4  jz      loc_18006351C
0x1800632ba  lea     r15d, [rsi-16h]
0x1800632be  call    winTempDirDefined
0x1800632c3  test    eax, eax
0x1800632c5  jz      loc_18006335B
0x1800632cb  mov     r9, cs:sqlite3_temp_directory
0x1800632d2  mov     rcx, r9
0x1800632d5  call    sqlite3Strlen30
0x1800632da  test    eax, eax
0x1800632dc  jle     short loc_180063344
0x1800632de  movsxd  rcx, eax
0x1800632e1  cmp     byte ptr [rcx+r9-1], 2Fh ; '/'
0x1800632e7  jz      short loc_1800632F3
0x1800632e9  cmp     byte ptr [rcx+r9-1], 5Ch ; '\'
0x1800632ef  jz      short loc_1800632F3
0x1800632f1  inc     eax
0x1800632f3  cmp     eax, r15d
0x1800632f6  jle     short loc_180063333
0x1800632f8  mov     ecx, 0Bh
0x1800632fd  call    sqlite3MutexAlloc
0x180063302  mov     rcx, rax
0x180063305  call    sqlite3_mutex_leave
0x18006330a  mov     rcx, rbx
0x18006330d  call    sqlite3_free
0x180063312  lea     r8, aWingettempname; "winGetTempname1"
0x180063319  mov     [rsp+68h+var_48], 0C952h
0x180063321  xor     r9d, r9d
0x180063324  xor     edx, edx
0x180063326  lea     ecx, [rdx+1]
0x180063329  call    winLogErrorAtLine
0x18006332e  jmp     loc_180063521
0x180063333  lea     r8, aS_7; "%s"
0x18006333a  mov     rdx, rbx
0x18006333d  mov     ecx, esi
0x18006333f  call    sqlite3_snprintf
0x180063344  mov     ecx, 0Bh
0x180063349  call    sqlite3MutexAlloc
0x18006334e  mov     rcx, rax
0x180063351  call    sqlite3_mutex_leave
0x180063356  jmp     loc_1800633F6
0x18006335b  mov     rcx, rsi
0x18006335e  add     rcx, rcx; Size
0x180063361  call    sqlite3MallocZero
0x180063366  mov     rdi, rax
0x180063369  test    rax, rax
0x18006336c  jz      loc_180063514
0x180063372  mov     rdx, rax
0x180063375  mov     ecx, esi
0x180063377  mov     rax, cs:off_1800CE108
0x18006337e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063383  mov     rcx, rdi
0x180063386  test    eax, eax
0x180063388  jnz     short loc_1800633C1
0x18006338a  call    sqlite3_free
0x18006338f  mov     rcx, rbx
0x180063392  call    sqlite3_free
0x180063397  mov     rax, cs:off_1800CE078
0x18006339e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800633a3  mov     edx, eax
0x1800633a5  mov     [rsp+68h+var_48], 0C9B7h
0x1800633ad  xor     r9d, r9d
0x1800633b0  lea     r8, aWingettempname_2; "winGetTempname2"
0x1800633b7  mov     ecx, 190Ah
0x1800633bc  jmp     loc_180063329
0x1800633c1  call    winUnicodeToUtf8
0x1800633c6  mov     rbp, rax
0x1800633c9  test    rax, rax
0x1800633cc  jz      loc_18006350C
0x1800633d2  mov     r9, rax
0x1800633d5  lea     r8, aS_7; "%s"
0x1800633dc  mov     rdx, rbx
0x1800633df  mov     ecx, esi
0x1800633e1  call    sqlite3_snprintf
0x1800633e6  mov     rcx, rbp
0x1800633e9  call    sqlite3_free
0x1800633ee  mov     rcx, rdi
0x1800633f1  call    sqlite3_free
0x1800633f6  mov     rcx, rbx
0x1800633f9  call    sqlite3Strlen30
0x1800633fe  test    eax, eax
0x180063400  jle     loc_1800634F0
0x180063406  movsxd  rdx, eax
0x180063409  cmp     byte ptr [rdx+rbx-1], 5Ch ; '\'
0x18006340e  jz      short loc_18006342C
0x180063410  cmp     byte ptr [rdx+rbx-1], 2Fh ; '/'
0x180063415  jz      short loc_18006342C
0x180063417  lea     ecx, [rax+1]
0x18006341a  lea     eax, [r15+1]
0x18006341e  cmp     ecx, eax
0x180063420  jge     loc_1800634F0
0x180063426  mov     word ptr [rdx+rbx], 5Ch ; '\'
0x18006342c  mov     rcx, rbx
0x18006342f  call    sqlite3Strlen30
0x180063434  lea     ecx, [rax+18h]
0x180063437  cmp     ecx, r14d
0x18006343a  jle     short loc_180063458
0x18006343c  mov     rcx, rbx
0x18006343f  call    sqlite3_free
0x180063444  lea     r8, aWingettempname_1; "winGetTempname5"
0x18006344b  mov     [rsp+68h+var_48], 0C9FBh
0x180063453  jmp     loc_180063321
0x180063458  sub     r14d, eax
0x18006345b  movsxd  rdx, eax
0x18006345e  add     rdx, rbx
0x180063461  lea     r8, aEtilqs; "etilqs_"
0x180063468  lea     ecx, [r14-10h]
0x18006346c  call    sqlite3_snprintf
0x180063471  mov     rcx, rbx
0x180063474  call    sqlite3Strlen30
0x180063479  movsxd  rdi, eax
0x18006347c  mov     esi, 0Fh
0x180063481  mov     ecx, esi
0x180063483  lea     rdx, [rbx+rdi]
0x180063487  call    sqlite3_randomness
0x18006348c  mov     rax, cs:off_1800CDFA0
0x180063493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063498  mov     r9d, eax
0x18006349b  mov     cl, r9b
0x18006349e  mov     rax, 842108421084211h
0x1800634a8  add     cl, [rbx+rdi]
0x1800634ab  movzx   r8d, cl
0x1800634af  mul     r8
0x1800634b2  mov     eax, r8d
0x1800634b5  shr     r9d, 8
0x1800634b9  sub     rax, rdx
0x1800634bc  shr     rax, 1
0x1800634bf  add     rax, rdx
0x1800634c2  shr     rax, 5
0x1800634c6  imul    rax, 3Eh ; '>'
0x1800634ca  sub     r8, rax
0x1800634cd  lea     rax, aAbcdefghijklmn; "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLM"...
0x1800634d4  mov     al, [r8+rax]
0x1800634d8  mov     [rbx+rdi], al
0x1800634db  inc     rdi
0x1800634de  sub     rsi, 1
0x1800634e2  jnz     short loc_18006349B
0x1800634e4  mov     [rbx+rdi], si
0x1800634e8  xor     eax, eax
0x1800634ea  mov     [r12], rbx
0x1800634ee  jmp     short loc_180063521
0x1800634f0  mov     rcx, rbx
0x1800634f3  call    sqlite3_free
0x1800634f8  lea     r8, aWingettempname_0; "winGetTempname4"
0x1800634ff  mov     [rsp+68h+var_48], 0C9E9h
0x180063507  jmp     loc_180063321
0x18006350c  mov     rcx, rdi
0x18006350f  call    sqlite3_free
0x180063514  mov     rcx, rbx
0x180063517  call    sqlite3_free
0x18006351c  mov     eax, 0C0Ah
0x180063521  add     rsp, 30h
0x180063525  pop     r15
0x180063527  pop     r14
0x180063529  pop     r12
0x18006352b  pop     rdi
0x18006352c  pop     rsi
0x18006352d  pop     rbp
0x18006352e  pop     rbx
0x18006352f  retn
```
