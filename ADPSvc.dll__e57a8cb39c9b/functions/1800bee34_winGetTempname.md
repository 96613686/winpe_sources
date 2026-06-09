# winGetTempname

- ea: `0x1800bee34`
- end: `0x1800bf178`
- name: `winGetTempname`
- size: `836`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1800be750`
- `0x1800bf940`

## callees

- `0x180080cc8`
- `0x1800a98a0`
- `0x1800aaae0`
- `0x1800abbf0`
- `0x1800bee34`
- `0x1800bf47c`
- `0x1800c0c30`
- `0x1800ca010`

## string_xrefs

- `0x1800bf14b`: `winGetTempname4`
- `0x1800befed`: `winGetTempname1`
- `0x1800bef3d`: `winGetTempname2`
- `0x1800bf097`: `winGetTempname5`

## pseudocode

```c
__int64 __fastcall winGetTempname(__int64 a1, __int64 *a2)
{
  __int64 v2; // rbp
  int v4; // r15d
  __int64 v5; // rbx
  __int64 result; // rax
  char v7; // cl
  int v8; // r13d
  __int64 v9; // rax
  __int64 v10; // rdi
  __int64 v11; // rax
  __int64 v12; // rsi
  DWORD v13; // edx
  const char *v14; // rax
  const char *v15; // r14
  __int64 v16; // rdx
  unsigned int v17; // edx
  __int64 v18; // rax
  const char *v19; // r8
  __int64 v20; // rax
  __int64 v21; // rcx
  unsigned int v22; // ecx
  char v23; // al
  __int64 v24; // rcx
  unsigned int v25; // ecx
  __int64 v26; // rdi
  __int64 v27; // rsi
  DWORD v28; // r9d
  unsigned __int8 v29; // cl
  int v30; // [rsp+20h] [rbp-58h]

  v2 = *(int *)(a1 + 8);
  v4 = v2 + 2;
  v5 = sqlite3MallocZero((int)v2 + 2);
  if ( !v5 )
    return 3082;
  v7 = word_18010EE54;
  v8 = v2 - 22;
  if ( (_BYTE)word_18010EE54 )
  {
    v9 = ((__int64 (__fastcall *)(__int64))xmmword_18010EEC0)(11);
    if ( v9 )
      ((void (__fastcall *)(__int64))xmmword_18010EED0)(v9);
    v7 = word_18010EE54;
  }
  v10 = -1;
  if ( sqlite3_temp_directory )
  {
    v16 = -1;
    do
      ++v16;
    while ( *(_BYTE *)(sqlite3_temp_directory + v16) );
    v17 = v16 & 0x3FFFFFFF;
    if ( v17 )
    {
      if ( *(_BYTE *)(v17 + sqlite3_temp_directory - 1) != 47 && *(_BYTE *)(v17 + sqlite3_temp_directory - 1) != 92 )
        ++v17;
      if ( (int)v17 > v8 )
      {
        if ( v7 )
        {
          v18 = ((__int64 (__fastcall *)(__int64))xmmword_18010EEC0)(11);
          if ( v18 )
            ((void (__fastcall *)(__int64))xmmword_18010EEE0)(v18);
        }
        sqlite3_free(v5);
        v19 = "winGetTempname1";
        v30 = 51539;
        return winLogErrorAtLine(1, 0, (_DWORD)v19, 0, v30);
      }
      sqlite3_snprintf((unsigned int)v2, v5, "%s", (const char *)sqlite3_temp_directory);
      v7 = word_18010EE54;
    }
    if ( v7 )
    {
      v20 = ((__int64 (__fastcall *)(__int64))xmmword_18010EEC0)(11);
      if ( v20 )
        ((void (__fastcall *)(__int64))xmmword_18010EEE0)(v20);
    }
  }
  else
  {
    if ( v7 )
    {
      v11 = ((__int64 (__fastcall *)(__int64))xmmword_18010EEC0)(11);
      if ( v11 )
        ((void (__fastcall *)(__int64))xmmword_18010EEE0)(v11);
    }
    v12 = sqlite3MallocZero(2 * v2);
    if ( !v12 )
      goto LABEL_12;
    if ( !(unsigned int)((__int64 (__fastcall *)(_QWORD, __int64))off_18010C108)((unsigned int)v2, v12) )
    {
      sqlite3_free(v12);
      sqlite3_free(v5);
      v13 = off_18010C078();
      return winLogErrorAtLine(6410, v13, (unsigned int)"winGetTempname2", 0, 51640);
    }
    v14 = (const char *)winUnicodeToUtf8(v12);
    v15 = v14;
    if ( !v14 )
    {
      sqlite3_free(v12);
LABEL_12:
      sqlite3_free(v5);
      return 3082;
    }
    sqlite3_snprintf((unsigned int)v2, v5, "%s", v14);
    sqlite3_free(v15);
    sqlite3_free(v12);
  }
  v21 = -1;
  do
    ++v21;
  while ( *(_BYTE *)(v5 + v21) );
  v22 = v21 & 0x3FFFFFFF;
  if ( !v22 )
    goto LABEL_49;
  v23 = *(_BYTE *)(v22 + v5 - 1);
  if ( v23 != 47 && v23 != 92 )
  {
    if ( (int)(v22 + 1) < v8 + 1 )
    {
      *(_WORD *)(v22 + v5) = 92;
      goto LABEL_40;
    }
LABEL_49:
    sqlite3_free(v5);
    v19 = "winGetTempname4";
    v30 = 51690;
    return winLogErrorAtLine(1, 0, (_DWORD)v19, 0, v30);
  }
LABEL_40:
  v24 = -1;
  do
    ++v24;
  while ( *(_BYTE *)(v5 + v24) );
  v25 = v24 & 0x3FFFFFFF;
  if ( (int)(v25 + 24) > v4 )
  {
    sqlite3_free(v5);
    v19 = "winGetTempname5";
    v30 = 51708;
    return winLogErrorAtLine(1, 0, (_DWORD)v19, 0, v30);
  }
  sqlite3_snprintf(v4 - v25 - 16, v5 + v25, "etilqs_");
  do
    ++v10;
  while ( *(_BYTE *)(v5 + v10) );
  v26 = v10 & 0x3FFFFFFF;
  v27 = 15;
  sqlite3_randomness(15, v5 + v26);
  v28 = off_18010BFA0();
  do
  {
    v29 = *(_BYTE *)(v5 + v26) + v28;
    v28 >>= 8;
    *(_BYTE *)(v5 + v26++) = aAbcdefghijklmn[v29 % 0x3EuLL];
    --v27;
  }
  while ( v27 );
  *(_WORD *)(v5 + v26) = 0;
  result = 0;
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x1800bee34  push    rbx
0x1800bee36  push    rbp
0x1800bee37  push    rsi
0x1800bee38  push    rdi
0x1800bee39  push    r12
0x1800bee3b  push    r13
0x1800bee3d  push    r14
0x1800bee3f  push    r15
0x1800bee41  sub     rsp, 38h
0x1800bee45  movsxd  rbp, dword ptr [rcx+8]
0x1800bee49  mov     r12, rdx
0x1800bee4c  lea     r15d, [rbp+2]
0x1800bee50  movsxd  rcx, r15d; Size
0x1800bee53  call    sqlite3MallocZero
0x1800bee58  xor     r14d, r14d
0x1800bee5b  mov     rbx, rax
0x1800bee5e  test    rax, rax
0x1800bee61  jnz     short loc_1800BEE6D
0x1800bee63  mov     eax, 0C0Ah
0x1800bee68  jmp     loc_1800BF167
0x1800bee6d  mov     cl, byte ptr cs:word_18010EE54
0x1800bee73  lea     r13d, [rbp-16h]
0x1800bee77  mov     esi, 0Bh
0x1800bee7c  test    cl, cl
0x1800bee7e  jz      short loc_1800BEEA8
0x1800bee80  mov     rax, qword ptr cs:xmmword_18010EEC0
0x1800bee87  mov     ecx, esi
0x1800bee89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bee8e  test    rax, rax
0x1800bee91  jz      short loc_1800BEEA2
0x1800bee93  mov     rcx, rax
0x1800bee96  mov     rax, qword ptr cs:xmmword_18010EED0
0x1800bee9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beea2  mov     cl, byte ptr cs:word_18010EE54
0x1800beea8  mov     r9, cs:sqlite3_temp_directory
0x1800beeaf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800beeb3  test    r9, r9
0x1800beeb6  jnz     loc_1800BEF94
0x1800beebc  test    cl, cl
0x1800beebe  jz      short loc_1800BEEE2
0x1800beec0  mov     rax, qword ptr cs:xmmword_18010EEC0
0x1800beec7  mov     ecx, esi
0x1800beec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beece  test    rax, rax
0x1800beed1  jz      short loc_1800BEEE2
0x1800beed3  mov     rcx, rax
0x1800beed6  mov     rax, qword ptr cs:xmmword_18010EEE0
0x1800beedd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beee2  mov     rcx, rbp
0x1800beee5  add     rcx, rcx; Size
0x1800beee8  call    sqlite3MallocZero
0x1800beeed  mov     rsi, rax
0x1800beef0  test    rax, rax
0x1800beef3  jnz     short loc_1800BEF02
0x1800beef5  mov     rcx, rbx
0x1800beef8  call    sqlite3_free
0x1800beefd  jmp     loc_1800BEE63
0x1800bef02  mov     rax, cs:off_18010C108
0x1800bef09  mov     rdx, rsi
0x1800bef0c  mov     ecx, ebp
0x1800bef0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bef13  mov     rcx, rsi
0x1800bef16  test    eax, eax
0x1800bef18  jnz     short loc_1800BEF4E
0x1800bef1a  call    sqlite3_free
0x1800bef1f  mov     rcx, rbx
0x1800bef22  call    sqlite3_free
0x1800bef27  mov     rax, cs:off_18010C078
0x1800bef2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bef33  mov     edx, eax
0x1800bef35  mov     [rsp+78h+var_58], 0C9B8h
0x1800bef3d  lea     r8, aWingettempname_2; "winGetTempname2"
0x1800bef44  mov     ecx, 190Ah
0x1800bef49  jmp     loc_1800BF15F
0x1800bef4e  call    winUnicodeToUtf8
0x1800bef53  mov     r14, rax
0x1800bef56  test    rax, rax
0x1800bef59  jz      short loc_1800BEF87
0x1800bef5b  mov     r9, rax
0x1800bef5e  lea     r8, aS_7; "%s"
0x1800bef65  mov     rdx, rbx
0x1800bef68  mov     ecx, ebp
0x1800bef6a  call    sqlite3_snprintf
0x1800bef6f  mov     rcx, r14
0x1800bef72  call    sqlite3_free
0x1800bef77  mov     rcx, rsi
0x1800bef7a  call    sqlite3_free
0x1800bef7f  xor     r14d, r14d
0x1800bef82  jmp     loc_1800BF03E
0x1800bef87  mov     rcx, rsi
0x1800bef8a  call    sqlite3_free
0x1800bef8f  jmp     loc_1800BEEF5
0x1800bef94  mov     rdx, rdi
0x1800bef97  inc     rdx
0x1800bef9a  cmp     [r9+rdx], r14b
0x1800bef9e  jnz     short loc_1800BEF97
0x1800befa0  and     edx, 3FFFFFFFh
0x1800befa6  jbe     short loc_1800BF018
0x1800befa8  cmp     byte ptr [rdx+r9-1], 2Fh ; '/'
0x1800befae  jz      short loc_1800BEFBA
0x1800befb0  cmp     byte ptr [rdx+r9-1], 5Ch ; '\'
0x1800befb6  jz      short loc_1800BEFBA
0x1800befb8  inc     edx
0x1800befba  cmp     edx, r13d
0x1800befbd  jle     short loc_1800BF001
0x1800befbf  test    cl, cl
0x1800befc1  jz      short loc_1800BEFE5
0x1800befc3  mov     rax, qword ptr cs:xmmword_18010EEC0
0x1800befca  mov     ecx, esi
0x1800befcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800befd1  test    rax, rax
0x1800befd4  jz      short loc_1800BEFE5
0x1800befd6  mov     rcx, rax
0x1800befd9  mov     rax, qword ptr cs:xmmword_18010EEE0
0x1800befe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800befe5  mov     rcx, rbx
0x1800befe8  call    sqlite3_free
0x1800befed  lea     r8, aWingettempname; "winGetTempname1"
0x1800beff4  mov     [rsp+78h+var_58], 0C953h
0x1800beffc  jmp     loc_1800BF15A
0x1800bf001  lea     r8, aS_7; "%s"
0x1800bf008  mov     rdx, rbx
0x1800bf00b  mov     ecx, ebp
0x1800bf00d  call    sqlite3_snprintf
0x1800bf012  mov     cl, byte ptr cs:word_18010EE54
0x1800bf018  test    cl, cl
0x1800bf01a  jz      short loc_1800BF03E
0x1800bf01c  mov     rax, qword ptr cs:xmmword_18010EEC0
0x1800bf023  mov     ecx, esi
0x1800bf025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf02a  test    rax, rax
0x1800bf02d  jz      short loc_1800BF03E
0x1800bf02f  mov     rcx, rax
0x1800bf032  mov     rax, qword ptr cs:xmmword_18010EEE0
0x1800bf039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf03e  mov     rcx, rdi
0x1800bf041  inc     rcx
0x1800bf044  cmp     [rbx+rcx], r14b
0x1800bf048  jnz     short loc_1800BF041
0x1800bf04a  mov     esi, 3FFFFFFFh
0x1800bf04f  and     ecx, esi
0x1800bf051  jbe     loc_1800BF143
0x1800bf057  mov     al, [rcx+rbx-1]
0x1800bf05b  mov     edx, ecx
0x1800bf05d  cmp     al, 2Fh ; '/'
0x1800bf05f  jz      short loc_1800BF079
0x1800bf061  cmp     al, 5Ch ; '\'
0x1800bf063  jz      short loc_1800BF079
0x1800bf065  inc     ecx
0x1800bf067  lea     eax, [r13+1]
0x1800bf06b  cmp     ecx, eax
0x1800bf06d  jge     loc_1800BF143
0x1800bf073  mov     word ptr [rdx+rbx], 5Ch ; '\'
0x1800bf079  mov     rcx, rdi
0x1800bf07c  inc     rcx
0x1800bf07f  cmp     [rbx+rcx], r14b
0x1800bf083  jnz     short loc_1800BF07C
0x1800bf085  and     ecx, esi
0x1800bf087  lea     eax, [rcx+18h]
0x1800bf08a  cmp     eax, r15d
0x1800bf08d  jle     short loc_1800BF0AB
0x1800bf08f  mov     rcx, rbx
0x1800bf092  call    sqlite3_free
0x1800bf097  lea     r8, aWingettempname_1; "winGetTempname5"
0x1800bf09e  mov     [rsp+78h+var_58], 0C9FCh
0x1800bf0a6  jmp     loc_1800BF15A
0x1800bf0ab  mov     edx, ecx
0x1800bf0ad  lea     r8, aEtilqs; "etilqs_"
0x1800bf0b4  sub     r15d, ecx
0x1800bf0b7  add     rdx, rbx
0x1800bf0ba  lea     ecx, [r15-10h]
0x1800bf0be  call    sqlite3_snprintf
0x1800bf0c3  inc     rdi
0x1800bf0c6  cmp     [rbx+rdi], r14b
0x1800bf0ca  jnz     short loc_1800BF0C3
0x1800bf0cc  and     rdi, rsi
0x1800bf0cf  mov     esi, 0Fh
0x1800bf0d4  mov     ecx, esi
0x1800bf0d6  lea     rdx, [rbx+rdi]
0x1800bf0da  call    sqlite3_randomness
0x1800bf0df  mov     rax, cs:off_18010BFA0
0x1800bf0e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf0eb  mov     r9d, eax
0x1800bf0ee  mov     cl, r9b
0x1800bf0f1  mov     rax, 842108421084211h
0x1800bf0fb  add     cl, [rbx+rdi]
0x1800bf0fe  movzx   r8d, cl
0x1800bf102  mul     r8
0x1800bf105  mov     eax, r8d
0x1800bf108  shr     r9d, 8
0x1800bf10c  sub     rax, rdx
0x1800bf10f  shr     rax, 1
0x1800bf112  add     rax, rdx
0x1800bf115  shr     rax, 5
0x1800bf119  imul    rax, 3Eh ; '>'
0x1800bf11d  sub     r8, rax
0x1800bf120  lea     rax, aAbcdefghijklmn; "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLM"...
0x1800bf127  mov     al, [r8+rax]
0x1800bf12b  mov     [rbx+rdi], al
0x1800bf12e  inc     rdi
0x1800bf131  sub     rsi, 1
0x1800bf135  jnz     short loc_1800BF0EE
0x1800bf137  mov     [rbx+rdi], si
0x1800bf13b  xor     eax, eax
0x1800bf13d  mov     [r12], rbx
0x1800bf141  jmp     short loc_1800BF167
0x1800bf143  mov     rcx, rbx
0x1800bf146  call    sqlite3_free
0x1800bf14b  lea     r8, aWingettempname_0; "winGetTempname4"
0x1800bf152  mov     [rsp+78h+var_58], 0C9EAh
0x1800bf15a  xor     edx, edx
0x1800bf15c  lea     ecx, [rdx+1]
0x1800bf15f  xor     r9d, r9d
0x1800bf162  call    winLogErrorAtLine
0x1800bf167  add     rsp, 38h
0x1800bf16b  pop     r15
0x1800bf16d  pop     r14
0x1800bf16f  pop     r13
0x1800bf171  pop     r12
0x1800bf173  pop     rdi
0x1800bf174  pop     rsi
0x1800bf175  pop     rbp
0x1800bf176  pop     rbx
0x1800bf177  retn
```
