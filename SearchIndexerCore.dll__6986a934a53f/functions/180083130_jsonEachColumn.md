# jsonEachColumn

- ea: `0x180083130`
- end: `0x1800833bc`
- name: `jsonEachColumn`
- size: `652`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x1800501a0`
- `0x18007055c`
- `0x180081e68`
- `0x180083130`
- `0x1800839a8`
- `0x180085b84`
- `0x180086358`
- `0x18009d5a0`
- `0x18009d790`
- `0x18009d7b0`
- `0x18009d830`

## pseudocode

```c
__int64 __fastcall jsonEachColumn(__int64 a1, __int64 a2, int a3)
{
  int v5; // r8d
  int v6; // r8d
  int v7; // r8d
  int v8; // r8d
  int v9; // r8d
  int v10; // r8d
  int v11; // r8d
  __int64 v12; // r8
  __int64 v13; // r9
  char *v14; // rdx
  int v15; // eax
  __int64 v16; // rbx
  int v17; // eax
  __int64 v18; // rdx
  unsigned int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rdx
  unsigned int v22; // eax
  __int64 v23; // rbx
  int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // r8d
  __int64 v27; // r9
  _BYTE *v28; // rcx
  __int64 v30; // [rsp+40h] [rbp+8h] BYREF

  if ( !a3 )
  {
    v24 = *(_DWORD *)(a1 + 28);
    if ( !v24 )
    {
      if ( *(_DWORD *)(a1 + 20) == 1 )
        return 0;
      v25 = jsonEachPathLength();
      v26 = *(_DWORD *)(a1 + 20) - v25;
      if ( !v26 )
        return 0;
      v27 = *(_QWORD *)(a1 + 64);
      v28 = (_BYTE *)(v27 + v25 + 1);
      if ( *(_BYTE *)(v25 + v27) != 91 )
      {
        if ( *v28 == 34 )
        {
          v12 = v26 - 3;
          v14 = (char *)(v27 + v25 + 2);
        }
        else
        {
          v12 = v26 - 1;
          v14 = (char *)(v27 + v25 + 1);
        }
        v13 = -1;
        goto LABEL_14;
      }
      v30 = 0;
      LOBYTE(v27) = 1;
      sqlite3Atoi64(v28, &v30, v26 - 1, v27);
      v18 = v30;
LABEL_41:
      sqlite3_result_int64(a2, v18);
      return 0;
    }
    if ( *(_BYTE *)(a1 + 24) != 12 )
    {
      v18 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 24LL * (unsigned int)(v24 - 1) + 16);
      goto LABEL_41;
    }
    v21 = *(unsigned int *)(a1 + 12);
    v20 = a1 + 192;
LABEL_39:
    jsonReturnFromBlob(v20, v21, a2, 1);
    return 0;
  }
  v5 = a3 - 1;
  if ( !v5 )
  {
    v23 = (unsigned int)jsonSkipLabel();
    jsonReturnFromBlob(a1 + 192, v23, a2, 1);
    if ( (*(_BYTE *)(v23 + *(_QWORD *)(a1 + 192)) & 0xFu) >= 0xB )
      sqlite3_result_subtype(a2, 74);
    return 0;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v22 = jsonSkipLabel();
    v13 = 0;
    v14 = off_1800B2920[*(_BYTE *)(v22 + *(_QWORD *)(a1 + 192)) & 0xF];
    goto LABEL_13;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    v19 = jsonSkipLabel();
    v20 = a1 + 192;
    if ( (*(_BYTE *)(v19 + *(_QWORD *)(a1 + 192)) & 0xFu) >= 0xB )
      return 0;
    v21 = v19;
    goto LABEL_39;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v18 = *(unsigned int *)(a1 + 12);
    goto LABEL_41;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v17 = *(_DWORD *)(a1 + 28);
    if ( !v17 || !*(_BYTE *)(a1 + 25) )
      return 0;
    v18 = *(unsigned int *)(*(_QWORD *)(a1 + 40) + 24LL * (unsigned int)(v17 - 1));
    goto LABEL_41;
  }
  v10 = v9 - 1;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( !v11 )
    {
      v15 = jsonEachPathLength();
      sqlite3_result_text64(a2, *(_QWORD *)(a1 + 64), v15, -1, 1);
      return 0;
    }
    if ( v11 != 1 )
    {
      v12 = *(unsigned int *)(a1 + 20);
      v13 = 0;
      v14 = *(char **)(a1 + 64);
LABEL_14:
      sqlite3_result_text(a2, v14, v12, v13);
      return 0;
    }
    v14 = *(char **)(a1 + 208);
    v13 = -1;
    if ( !v14 )
    {
      sqlite3_result_blob(a2, *(_QWORD *)(a1 + 192), *(unsigned int *)(a1 + 200), -1);
      return 0;
    }
LABEL_13:
    v12 = 0xFFFFFFFFLL;
    goto LABEL_14;
  }
  v16 = *(_QWORD *)(a1 + 80);
  if ( *(_DWORD *)(a1 + 28) )
    jsonAppendPathName(a1);
  sqlite3_result_text64(a2, *(_QWORD *)(a1 + 64), *(_QWORD *)(a1 + 80), -1, 1);
  *(_QWORD *)(a1 + 80) = v16;
  return 0;
}

```

## disassembly

```asm
0x180083130  mov     [rsp+arg_8], rbx
0x180083135  mov     [rsp+arg_10], rsi
0x18008313a  push    rdi
0x18008313b  sub     rsp, 30h
0x18008313f  mov     rsi, rdx
0x180083142  mov     rdi, rcx
0x180083145  test    r8d, r8d
0x180083148  jz      loc_1800832F6
0x18008314e  sub     r8d, 1
0x180083152  jz      loc_1800832B0
0x180083158  sub     r8d, 1
0x18008315c  jz      loc_180083288
0x180083162  sub     r8d, 1
0x180083166  jz      loc_18008325D
0x18008316c  sub     r8d, 1
0x180083170  jz      loc_180083255
0x180083176  sub     r8d, 1
0x18008317a  jz      loc_18008322E
0x180083180  sub     r8d, 1
0x180083184  jz      short loc_1800831FD
0x180083186  sub     r8d, 1
0x18008318a  jz      short loc_1800831DB
0x18008318c  cmp     r8d, 1
0x180083190  jz      short loc_18008319F
0x180083192  mov     r8d, [rcx+14h]
0x180083196  xor     r9d, r9d
0x180083199  mov     rdx, [rcx+40h]
0x18008319d  jmp     short loc_1800831CE
0x18008319f  mov     rdx, [rcx+0D0h]
0x1800831a6  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800831aa  test    rdx, rdx
0x1800831ad  jnz     short loc_1800831CA
0x1800831af  mov     r8d, [rcx+0C8h]
0x1800831b6  mov     rdx, [rcx+0C0h]
0x1800831bd  mov     rcx, rsi
0x1800831c0  call    sqlite3_result_blob
0x1800831c5  jmp     loc_1800833AA
0x1800831ca  or      r8d, 0FFFFFFFFh
0x1800831ce  mov     rcx, rsi
0x1800831d1  call    sqlite3_result_text
0x1800831d6  jmp     loc_1800833AA
0x1800831db  call    jsonEachPathLength
0x1800831e0  mov     rdx, [rdi+40h]
0x1800831e4  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800831e8  mov     r8d, eax
0x1800831eb  mov     rcx, rsi
0x1800831ee  mov     [rsp+38h+var_18], 1
0x1800831f3  call    sqlite3_result_text64
0x1800831f8  jmp     loc_1800833AA
0x1800831fd  cmp     dword ptr [rcx+1Ch], 0
0x180083201  mov     rbx, [rcx+50h]
0x180083205  jz      short loc_18008320C
0x180083207  call    jsonAppendPathName
0x18008320c  mov     r8, [rdi+50h]
0x180083210  or      r9, 0FFFFFFFFFFFFFFFFh
0x180083214  mov     rdx, [rdi+40h]
0x180083218  mov     rcx, rsi
0x18008321b  mov     [rsp+38h+var_18], 1
0x180083220  call    sqlite3_result_text64
0x180083225  mov     [rdi+50h], rbx
0x180083229  jmp     loc_1800833AA
0x18008322e  mov     eax, [rcx+1Ch]
0x180083231  test    eax, eax
0x180083233  jz      loc_1800833AA
0x180083239  cmp     byte ptr [rcx+19h], 0
0x18008323d  jz      loc_1800833AA
0x180083243  dec     eax
0x180083245  lea     rdx, [rax+rax*2]
0x180083249  mov     rax, [rcx+28h]
0x18008324d  mov     edx, [rax+rdx*8]
0x180083250  jmp     loc_1800833A2
0x180083255  mov     edx, [rcx+0Ch]
0x180083258  jmp     loc_1800833A2
0x18008325d  call    jsonSkipLabel
0x180083262  lea     rcx, [rdi+0C0h]
0x180083269  mov     r8d, eax
0x18008326c  mov     rdx, [rcx]
0x18008326f  mov     r9b, [r8+rdx]
0x180083273  and     r9b, 0Fh
0x180083277  cmp     r9b, 0Bh
0x18008327b  jnb     loc_1800833AA
0x180083281  mov     edx, eax
0x180083283  jmp     loc_180083383
0x180083288  call    jsonSkipLabel
0x18008328d  mov     ecx, eax
0x18008328f  mov     rax, [rdi+0C0h]
0x180083296  movzx   edx, byte ptr [rcx+rax]
0x18008329a  lea     rax, off_1800B2920; "null"
0x1800832a1  and     edx, 0Fh
0x1800832a4  xor     r9d, r9d
0x1800832a7  mov     rdx, [rax+rdx*8]
0x1800832ab  jmp     loc_1800831CA
0x1800832b0  call    jsonSkipLabel
0x1800832b5  mov     r9d, 1
0x1800832bb  mov     ebx, eax
0x1800832bd  mov     r8, rsi
0x1800832c0  lea     rcx, [rdi+0C0h]
0x1800832c7  mov     edx, eax
0x1800832c9  call    jsonReturnFromBlob
0x1800832ce  mov     rax, [rdi+0C0h]
0x1800832d5  mov     dl, [rbx+rax]
0x1800832d8  and     dl, 0Fh
0x1800832db  cmp     dl, 0Bh
0x1800832de  jb      loc_1800833AA
0x1800832e4  mov     edx, 4Ah ; 'J'
0x1800832e9  mov     rcx, rsi
0x1800832ec  call    sqlite3_result_subtype
0x1800832f1  jmp     loc_1800833AA
0x1800832f6  mov     eax, [rcx+1Ch]
0x1800832f9  test    eax, eax
0x1800832fb  jnz     short loc_180083373
0x1800832fd  cmp     dword ptr [rcx+14h], 1
0x180083301  jz      loc_1800833AA
0x180083307  call    jsonEachPathLength
0x18008330c  mov     r8d, [rdi+14h]
0x180083310  sub     r8d, eax
0x180083313  jz      loc_1800833AA
0x180083319  mov     r9, [rdi+40h]
0x18008331d  lea     ecx, [rax+1]
0x180083320  mov     edx, eax
0x180083322  add     rcx, r9
0x180083325  cmp     byte ptr [rdx+r9], 5Bh ; '['
0x18008332a  jnz     short loc_18008334C
0x18008332c  dec     r8d
0x18008332f  mov     [rsp+38h+arg_0], 0
0x180083338  mov     r9b, 1
0x18008333b  lea     rdx, [rsp+38h+arg_0]
0x180083340  call    sqlite3Atoi64
0x180083345  mov     rdx, [rsp+38h+arg_0]
0x18008334a  jmp     short loc_1800833A2
0x18008334c  cmp     byte ptr [rcx], 22h ; '"'
0x18008334f  jnz     short loc_180083364
0x180083351  lea     edx, [rax+2]
0x180083354  add     r8d, 0FFFFFFFDh
0x180083358  add     rdx, r9
0x18008335b  or      r9, 0FFFFFFFFFFFFFFFFh
0x18008335f  jmp     loc_1800831CE
0x180083364  dec     r8d
0x180083367  mov     rdx, rcx
0x18008336a  or      r9, 0FFFFFFFFFFFFFFFFh
0x18008336e  jmp     loc_1800831CE
0x180083373  cmp     byte ptr [rcx+18h], 0Ch
0x180083377  jnz     short loc_180083393
0x180083379  mov     edx, [rdi+0Ch]
0x18008337c  add     rcx, 0C0h
0x180083383  mov     r8, rsi
0x180083386  mov     r9d, 1
0x18008338c  call    jsonReturnFromBlob
0x180083391  jmp     short loc_1800833AA
0x180083393  mov     rdx, [rcx+28h]
0x180083397  dec     eax
0x180083399  lea     rax, [rax+rax*2]
0x18008339d  mov     rdx, [rdx+rax*8+10h]
0x1800833a2  mov     rcx, rsi
0x1800833a5  call    sqlite3_result_int64
0x1800833aa  mov     rbx, [rsp+38h+arg_8]
0x1800833af  xor     eax, eax
0x1800833b1  mov     rsi, [rsp+38h+arg_10]
0x1800833b6  add     rsp, 30h
0x1800833ba  pop     rdi
0x1800833bb  retn
```
