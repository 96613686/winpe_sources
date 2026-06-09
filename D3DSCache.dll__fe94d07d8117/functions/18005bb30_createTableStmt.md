# createTableStmt

- ea: `0x18005bb30`
- end: `0x18005bd0e`
- name: `createTableStmt`
- size: `478`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000ab80`

## callees

- `0x180020d70`
- `0x18002b81c`
- `0x18003b5b4`
- `0x18003f650`
- `0x18005bb30`
- `0x180063264`
- `0x18006328c`
- `0x1800a6d08`

## string_xrefs

- `0x18005bbfc`: `CREATE TABLE `

## pseudocode

```c
__int64 __fastcall createTableStmt(__int64 a1, __int16 *a2)
{
  int v2; // ebx
  _QWORD *v3; // r9
  int v6; // eax
  __int64 v7; // r9
  int v8; // r10d
  int v9; // r11d
  const char *v10; // r15
  int v11; // ecx
  int v12; // r11d
  const char *v13; // rax
  const char *v14; // rax
  int v15; // ebp
  __int64 v16; // rax
  __int64 v17; // rsi
  unsigned int v19; // ebp
  __int64 v20; // rdx
  __int64 v21; // r8
  int v22; // eax
  __int64 v23; // r8
  __int64 v24; // rcx
  int v25; // ecx
  int v26; // edi
  __int64 *v27; // r12
  int v28; // r13d
  const char *v29; // r15
  __int64 v30; // rdx
  __int64 v31; // r8
  int v32; // eax
  __int64 v33; // r8
  __int64 v34; // rcx
  __int64 v35; // r8
  int v36; // eax
  int v37; // ebx
  int v38; // edi
  const void *v39; // rdx
  const char *v40; // [rsp+20h] [rbp-48h]
  int v41; // [rsp+78h] [rbp+10h] BYREF
  const char *v42; // [rsp+80h] [rbp+18h]
  const char *v43; // [rsp+88h] [rbp+20h]

  v2 = 0;
  v3 = (_QWORD *)*((_QWORD *)a2 + 1);
  if ( a2[27] > 0 )
  {
    do
    {
      v6 = identLength(*v3);
      v3 = (_QWORD *)(v7 + 24);
      v2 += v6 + 5;
    }
    while ( v8 + 1 < v9 );
  }
  v10 = ")";
  v11 = identLength(*(_QWORD *)a2) + v2;
  if ( v11 >= 50 )
    v10 = "\n)";
  v13 = ",";
  if ( v11 >= 50 )
    v13 = ",\n  ";
  v40 = v10;
  v43 = v13;
  v14 = (const char *)&Src;
  if ( v11 >= 50 )
    v14 = "\n  ";
  v42 = v14;
  v15 = v11 + 6 * v12;
  v16 = sqlite3Malloc(v15 + 35LL);
  v17 = v16;
  if ( v16 )
  {
    v19 = v15 + 35;
    sqlite3_snprintf(v19, v16, "CREATE TABLE ");
    v22 = sqlite3Strlen30(v17, v20, v21);
    v23 = *(_QWORD *)a2;
    v41 = v22;
    identPut(v24, &v41, v23);
    v25 = v41;
    *(_BYTE *)(v41 + v17) = 40;
    v26 = v25 + 1;
    if ( a2[27] > 0 )
    {
      v27 = (__int64 *)*((_QWORD *)a2 + 1);
      v28 = 0;
      v29 = v43;
      do
      {
        sqlite3_snprintf(v19 - v26, v17 + v26, v42);
        v32 = sqlite3Strlen30(v17 + v26, v30, v31);
        v33 = *v27;
        v42 = v29;
        v41 = v26 + v32;
        identPut(v17, &v41, v33);
        v34 = (__int64)*(&off_1800AA690 + *((char *)v27 + 12) - 65);
        v36 = sqlite3Strlen30(v34, v34, v35);
        v37 = v41;
        v38 = v36;
        memcpy_0((void *)(v17 + v41), v39, v36);
        v27 += 3;
        v26 = v37 + v38;
        ++v28;
      }
      while ( v28 < a2[27] );
      v10 = v40;
    }
    sqlite3_snprintf(v19 - v26, v17 + v26, "%s", v10);
    return v17;
  }
  else
  {
    sqlite3OomFault(a1);
    return 0;
  }
}

```

## disassembly

```asm
0x18005bb30  mov     [rsp+arg_0], rbx
0x18005bb35  push    rbp
0x18005bb36  push    rsi
0x18005bb37  push    rdi
0x18005bb38  push    r12
0x18005bb3a  push    r13
0x18005bb3c  push    r14
0x18005bb3e  push    r15
0x18005bb40  sub     rsp, 30h
0x18005bb44  movsx   r11d, word ptr [rdx+36h]
0x18005bb49  xor     ebx, ebx
0x18005bb4b  mov     r9, [rdx+8]
0x18005bb4f  xor     r10d, r10d
0x18005bb52  mov     r14, rdx
0x18005bb55  mov     rdi, rcx
0x18005bb58  test    r11d, r11d
0x18005bb5b  jle     short loc_18005BB76
0x18005bb5d  mov     rcx, [r9]
0x18005bb60  call    identLength
0x18005bb65  add     ebx, 5
0x18005bb68  lea     r9, [r9+18h]
0x18005bb6c  add     ebx, eax
0x18005bb6e  inc     r10d
0x18005bb71  cmp     r10d, r11d
0x18005bb74  jl      short loc_18005BB5D
0x18005bb76  mov     rcx, [r14]
0x18005bb79  call    identLength
0x18005bb7e  lea     rdx, asc_1800B2B10; ",\n  "
0x18005bb85  lea     r15, asc_1800B09E0; ")"
0x18005bb8c  lea     ecx, [rax+rbx]
0x18005bb8f  cmp     ecx, 32h ; '2'
0x18005bb92  lea     rax, asc_1800B2B18; "\n)"
0x18005bb99  cmovge  r15, rax
0x18005bb9d  lea     rax, asc_1800B2B08; ","
0x18005bba4  cmovge  rax, rdx
0x18005bba8  mov     [rsp+68h+var_48], r15
0x18005bbad  mov     [rsp+68h+arg_18], rax
0x18005bbb5  lea     rdx, asc_1800B2B0C; "\n  "
0x18005bbbc  lea     rax, Src
0x18005bbc3  cmovge  rax, rdx
0x18005bbc7  mov     [rsp+68h+arg_10], rax
0x18005bbcf  lea     eax, [r11+r11*2]
0x18005bbd3  lea     ebp, [rcx+rax*2]
0x18005bbd6  movsxd  rcx, ebp
0x18005bbd9  add     rcx, 23h ; '#'
0x18005bbdd  call    sqlite3Malloc
0x18005bbe2  mov     rsi, rax
0x18005bbe5  test    rax, rax
0x18005bbe8  jnz     short loc_18005BBF9
0x18005bbea  mov     rcx, rdi
0x18005bbed  call    sqlite3OomFault
0x18005bbf2  xor     eax, eax
0x18005bbf4  jmp     loc_18005BCF9
0x18005bbf9  add     ebp, 23h ; '#'
0x18005bbfc  lea     r8, aCreateTable; "CREATE TABLE "
0x18005bc03  mov     ecx, ebp
0x18005bc05  mov     rdx, rsi
0x18005bc08  call    sqlite3_snprintf
0x18005bc0d  mov     rcx, rsi
0x18005bc10  call    sqlite3Strlen30
0x18005bc15  mov     r8, [r14]
0x18005bc18  lea     rdx, [rsp+68h+arg_8]
0x18005bc1d  mov     [rsp+68h+arg_8], eax
0x18005bc21  call    identPut
0x18005bc26  movsxd  rcx, [rsp+68h+arg_8]
0x18005bc2b  xor     eax, eax
0x18005bc2d  mov     byte ptr [rcx+rsi], 28h ; '('
0x18005bc31  lea     edi, [rcx+1]
0x18005bc34  cmp     ax, [r14+36h]
0x18005bc39  jge     loc_18005BCDD
0x18005bc3f  mov     r12, [r14+8]
0x18005bc43  xor     r13d, r13d
0x18005bc46  mov     r15, [rsp+68h+arg_18]
0x18005bc4e  mov     r8, [rsp+68h+arg_10]
0x18005bc56  mov     ecx, ebp
0x18005bc58  movsxd  rbx, edi
0x18005bc5b  sub     ecx, edi
0x18005bc5d  add     rbx, rsi
0x18005bc60  mov     rdx, rbx
0x18005bc63  call    sqlite3_snprintf
0x18005bc68  mov     rcx, rbx
0x18005bc6b  call    sqlite3Strlen30
0x18005bc70  mov     r8, [r12]
0x18005bc74  lea     rdx, [rsp+68h+arg_8]
0x18005bc79  add     eax, edi
0x18005bc7b  mov     [rsp+68h+arg_10], r15
0x18005bc83  mov     rcx, rsi
0x18005bc86  mov     [rsp+68h+arg_8], eax
0x18005bc8a  call    identPut
0x18005bc8f  movsx   rax, byte ptr [r12+0Ch]
0x18005bc95  lea     rdx, off_1800AA690
0x18005bc9c  mov     rdx, [rdx+rax*8-208h]
0x18005bca4  mov     rcx, rdx
0x18005bca7  call    sqlite3Strlen30
0x18005bcac  movsxd  rbx, [rsp+68h+arg_8]
0x18005bcb1  movsxd  rdi, eax
0x18005bcb4  mov     r8, rdi; Size
0x18005bcb7  lea     rcx, [rsi+rbx]; void *
0x18005bcbb  call    memcpy_0
0x18005bcc0  movsx   eax, word ptr [r14+36h]
0x18005bcc5  lea     r12, [r12+18h]
0x18005bcca  add     edi, ebx
0x18005bccc  inc     r13d
0x18005bccf  cmp     r13d, eax
0x18005bcd2  jl      loc_18005BC4E
0x18005bcd8  mov     r15, [rsp+68h+var_48]
0x18005bcdd  sub     ebp, edi
0x18005bcdf  movsxd  rdx, edi
0x18005bce2  add     rdx, rsi
0x18005bce5  lea     r8, aS_10; "%s"
0x18005bcec  mov     ecx, ebp
0x18005bcee  mov     r9, r15
0x18005bcf1  call    sqlite3_snprintf
0x18005bcf6  mov     rax, rsi
0x18005bcf9  mov     rbx, [rsp+68h+arg_0]
0x18005bcfe  add     rsp, 30h
0x18005bd02  pop     r15
0x18005bd04  pop     r14
0x18005bd06  pop     r13
0x18005bd08  pop     r12
0x18005bd0a  pop     rdi
0x18005bd0b  pop     rsi
0x18005bd0c  pop     rbp
0x18005bd0d  retn
```
