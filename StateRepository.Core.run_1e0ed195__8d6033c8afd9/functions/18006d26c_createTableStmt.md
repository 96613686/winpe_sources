# createTableStmt

- ea: `0x18006d26c`
- end: `0x18006d44a`
- name: `createTableStmt`
- size: `478`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000d770`

## callees

- `0x180005810`
- `0x18000bd90`
- `0x180064ef0`
- `0x180067b40`
- `0x18006d26c`
- `0x1800719e4`
- `0x180071a0c`
- `0x180099814`

## string_xrefs

- `0x18006d338`: `CREATE TABLE `

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
  v14 = (const char *)qword_18009EEF0;
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
        v34 = (__int64)*(&off_18009C2E0 + *((char *)v27 + 12) - 65);
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
0x18006d26c  mov     [rsp+arg_0], rbx
0x18006d271  push    rbp
0x18006d272  push    rsi
0x18006d273  push    rdi
0x18006d274  push    r12
0x18006d276  push    r13
0x18006d278  push    r14
0x18006d27a  push    r15
0x18006d27c  sub     rsp, 30h
0x18006d280  movsx   r11d, word ptr [rdx+36h]
0x18006d285  xor     ebx, ebx
0x18006d287  mov     r9, [rdx+8]
0x18006d28b  xor     r10d, r10d
0x18006d28e  mov     r14, rdx
0x18006d291  mov     rdi, rcx
0x18006d294  test    r11d, r11d
0x18006d297  jle     short loc_18006D2B2
0x18006d299  mov     rcx, [r9]
0x18006d29c  call    identLength
0x18006d2a1  add     ebx, 5
0x18006d2a4  lea     r9, [r9+18h]
0x18006d2a8  add     ebx, eax
0x18006d2aa  inc     r10d
0x18006d2ad  cmp     r10d, r11d
0x18006d2b0  jl      short loc_18006D299
0x18006d2b2  mov     rcx, [r14]
0x18006d2b5  call    identLength
0x18006d2ba  lea     rdx, asc_1800A3270; ",\n  "
0x18006d2c1  lea     r15, asc_1800A1320; ")"
0x18006d2c8  lea     ecx, [rax+rbx]
0x18006d2cb  cmp     ecx, 32h ; '2'
0x18006d2ce  lea     rax, asc_1800A3278; "\n)"
0x18006d2d5  cmovge  r15, rax
0x18006d2d9  lea     rax, asc_1800A3268; ","
0x18006d2e0  cmovge  rax, rdx
0x18006d2e4  mov     [rsp+68h+var_48], r15
0x18006d2e9  mov     [rsp+68h+arg_18], rax
0x18006d2f1  lea     rdx, asc_1800A326C; "\n  "
0x18006d2f8  lea     rax, qword_18009EEF0
0x18006d2ff  cmovge  rax, rdx
0x18006d303  mov     [rsp+68h+arg_10], rax
0x18006d30b  lea     eax, [r11+r11*2]
0x18006d30f  lea     ebp, [rcx+rax*2]
0x18006d312  movsxd  rcx, ebp
0x18006d315  add     rcx, 23h ; '#'
0x18006d319  call    sqlite3Malloc
0x18006d31e  mov     rsi, rax
0x18006d321  test    rax, rax
0x18006d324  jnz     short loc_18006D335
0x18006d326  mov     rcx, rdi
0x18006d329  call    sqlite3OomFault
0x18006d32e  xor     eax, eax
0x18006d330  jmp     loc_18006D435
0x18006d335  add     ebp, 23h ; '#'
0x18006d338  lea     r8, aCreateTable; "CREATE TABLE "
0x18006d33f  mov     ecx, ebp
0x18006d341  mov     rdx, rsi
0x18006d344  call    sqlite3_snprintf
0x18006d349  mov     rcx, rsi
0x18006d34c  call    sqlite3Strlen30
0x18006d351  mov     r8, [r14]
0x18006d354  lea     rdx, [rsp+68h+arg_8]
0x18006d359  mov     [rsp+68h+arg_8], eax
0x18006d35d  call    identPut
0x18006d362  movsxd  rcx, [rsp+68h+arg_8]
0x18006d367  xor     eax, eax
0x18006d369  mov     byte ptr [rcx+rsi], 28h ; '('
0x18006d36d  lea     edi, [rcx+1]
0x18006d370  cmp     ax, [r14+36h]
0x18006d375  jge     loc_18006D419
0x18006d37b  mov     r12, [r14+8]
0x18006d37f  xor     r13d, r13d
0x18006d382  mov     r15, [rsp+68h+arg_18]
0x18006d38a  mov     r8, [rsp+68h+arg_10]
0x18006d392  mov     ecx, ebp
0x18006d394  movsxd  rbx, edi
0x18006d397  sub     ecx, edi
0x18006d399  add     rbx, rsi
0x18006d39c  mov     rdx, rbx
0x18006d39f  call    sqlite3_snprintf
0x18006d3a4  mov     rcx, rbx
0x18006d3a7  call    sqlite3Strlen30
0x18006d3ac  mov     r8, [r12]
0x18006d3b0  lea     rdx, [rsp+68h+arg_8]
0x18006d3b5  add     eax, edi
0x18006d3b7  mov     [rsp+68h+arg_10], r15
0x18006d3bf  mov     rcx, rsi
0x18006d3c2  mov     [rsp+68h+arg_8], eax
0x18006d3c6  call    identPut
0x18006d3cb  movsx   rax, byte ptr [r12+0Ch]
0x18006d3d1  lea     rdx, off_18009C2E0
0x18006d3d8  mov     rdx, [rdx+rax*8-208h]
0x18006d3e0  mov     rcx, rdx
0x18006d3e3  call    sqlite3Strlen30
0x18006d3e8  movsxd  rbx, [rsp+68h+arg_8]
0x18006d3ed  movsxd  rdi, eax
0x18006d3f0  mov     r8, rdi; Size
0x18006d3f3  lea     rcx, [rsi+rbx]; void *
0x18006d3f7  call    memcpy_0
0x18006d3fc  movsx   eax, word ptr [r14+36h]
0x18006d401  lea     r12, [r12+18h]
0x18006d406  add     edi, ebx
0x18006d408  inc     r13d
0x18006d40b  cmp     r13d, eax
0x18006d40e  jl      loc_18006D38A
0x18006d414  mov     r15, [rsp+68h+var_48]
0x18006d419  sub     ebp, edi
0x18006d41b  movsxd  rdx, edi
0x18006d41e  add     rdx, rsi
0x18006d421  lea     r8, aS_7; "%s"
0x18006d428  mov     ecx, ebp
0x18006d42a  mov     r9, r15
0x18006d42d  call    sqlite3_snprintf
0x18006d432  mov     rax, rsi
0x18006d435  mov     rbx, [rsp+68h+arg_0]
0x18006d43a  add     rsp, 30h
0x18006d43e  pop     r15
0x18006d440  pop     r14
0x18006d442  pop     r13
0x18006d444  pop     r12
0x18006d446  pop     rdi
0x18006d447  pop     rsi
0x18006d448  pop     rbp
0x18006d449  retn
```
