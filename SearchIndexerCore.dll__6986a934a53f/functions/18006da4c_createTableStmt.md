# createTableStmt

- ea: `0x18006da4c`
- end: `0x18006dc2a`
- name: `createTableStmt`
- size: `478`
- prototype: `__int64 __fastcall(__int64, __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800635fc`

## callees

- `0x18001eb90`
- `0x18003c510`
- `0x18004ae40`
- `0x18006da4c`
- `0x18006dc30`
- `0x18006dcc4`
- `0x180080e14`
- `0x1800af620`

## string_xrefs

- `0x18006db18`: `CREATE TABLE `

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
  int v20; // eax
  __int64 v21; // r8
  __int64 v22; // rcx
  int v23; // ecx
  int v24; // edi
  __int64 *v25; // r12
  int v26; // r13d
  const char *v27; // r15
  int v28; // eax
  __int64 v29; // r8
  int v30; // eax
  int v31; // ebx
  int v32; // edi
  const void *v33; // rdx
  const char *v34; // [rsp+20h] [rbp-48h]
  int v35; // [rsp+78h] [rbp+10h] BYREF
  const char *v36; // [rsp+80h] [rbp+18h]
  const char *v37; // [rsp+88h] [rbp+20h]

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
  v34 = v10;
  v37 = v13;
  v14 = (const char *)&Src;
  if ( v11 >= 50 )
    v14 = "\n  ";
  v36 = v14;
  v15 = v11 + 6 * v12;
  v16 = sqlite3Malloc(v15 + 35LL);
  v17 = v16;
  if ( v16 )
  {
    v19 = v15 + 35;
    sqlite3_snprintf(v19, v16, "CREATE TABLE ");
    v20 = sqlite3Strlen30(v17);
    v21 = *(_QWORD *)a2;
    v35 = v20;
    identPut(v22, &v35, v21);
    v23 = v35;
    *(_BYTE *)(v35 + v17) = 40;
    v24 = v23 + 1;
    if ( a2[27] > 0 )
    {
      v25 = (__int64 *)*((_QWORD *)a2 + 1);
      v26 = 0;
      v27 = v37;
      do
      {
        sqlite3_snprintf(v19 - v24, v17 + v24, v36);
        v28 = sqlite3Strlen30(v17 + v24);
        v29 = *v25;
        v36 = v27;
        v35 = v24 + v28;
        identPut(v17, &v35, v29);
        v30 = sqlite3Strlen30(*((_QWORD *)&off_1800B2BB0 + *((char *)v25 + 12) - 65));
        v31 = v35;
        v32 = v30;
        memcpy_0((void *)(v17 + v35), v33, v30);
        v25 += 3;
        v24 = v31 + v32;
        ++v26;
      }
      while ( v26 < a2[27] );
      v10 = v34;
    }
    sqlite3_snprintf(v19 - v24, v17 + v24, "%s", v10);
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
0x18006da4c  mov     [rsp+arg_0], rbx
0x18006da51  push    rbp
0x18006da52  push    rsi
0x18006da53  push    rdi
0x18006da54  push    r12
0x18006da56  push    r13
0x18006da58  push    r14
0x18006da5a  push    r15
0x18006da5c  sub     rsp, 30h
0x18006da60  movsx   r11d, word ptr [rdx+36h]
0x18006da65  xor     ebx, ebx
0x18006da67  mov     r9, [rdx+8]
0x18006da6b  xor     r10d, r10d
0x18006da6e  mov     r14, rdx
0x18006da71  mov     rdi, rcx
0x18006da74  test    r11d, r11d
0x18006da77  jle     short loc_18006DA92
0x18006da79  mov     rcx, [r9]
0x18006da7c  call    identLength
0x18006da81  add     ebx, 5
0x18006da84  lea     r9, [r9+18h]
0x18006da88  add     ebx, eax
0x18006da8a  inc     r10d
0x18006da8d  cmp     r10d, r11d
0x18006da90  jl      short loc_18006DA79
0x18006da92  mov     rcx, [r14]
0x18006da95  call    identLength
0x18006da9a  lea     rdx, asc_1800B6B10; ",\n  "
0x18006daa1  lea     r15, asc_1800B6B24; ")"
0x18006daa8  lea     ecx, [rax+rbx]
0x18006daab  cmp     ecx, 32h ; '2'
0x18006daae  lea     rax, asc_1800B6B18; "\n)"
0x18006dab5  cmovge  r15, rax
0x18006dab9  lea     rax, asc_1800B6B1C; ","
0x18006dac0  cmovge  rax, rdx
0x18006dac4  mov     [rsp+68h+var_48], r15
0x18006dac9  mov     [rsp+68h+arg_18], rax
0x18006dad1  lea     rdx, asc_1800B6B20; "\n  "
0x18006dad8  lea     rax, Src
0x18006dadf  cmovge  rax, rdx
0x18006dae3  mov     [rsp+68h+arg_10], rax
0x18006daeb  lea     eax, [r11+r11*2]
0x18006daef  lea     ebp, [rcx+rax*2]
0x18006daf2  movsxd  rcx, ebp
0x18006daf5  add     rcx, 23h ; '#'
0x18006daf9  call    sqlite3Malloc
0x18006dafe  mov     rsi, rax
0x18006db01  test    rax, rax
0x18006db04  jnz     short loc_18006DB15
0x18006db06  mov     rcx, rdi
0x18006db09  call    sqlite3OomFault
0x18006db0e  xor     eax, eax
0x18006db10  jmp     loc_18006DC15
0x18006db15  add     ebp, 23h ; '#'
0x18006db18  lea     r8, aCreateTable; "CREATE TABLE "
0x18006db1f  mov     ecx, ebp
0x18006db21  mov     rdx, rsi
0x18006db24  call    sqlite3_snprintf
0x18006db29  mov     rcx, rsi
0x18006db2c  call    sqlite3Strlen30
0x18006db31  mov     r8, [r14]
0x18006db34  lea     rdx, [rsp+68h+arg_8]
0x18006db39  mov     [rsp+68h+arg_8], eax
0x18006db3d  call    identPut
0x18006db42  movsxd  rcx, [rsp+68h+arg_8]
0x18006db47  xor     eax, eax
0x18006db49  mov     byte ptr [rcx+rsi], 28h ; '('
0x18006db4d  lea     edi, [rcx+1]
0x18006db50  cmp     ax, [r14+36h]
0x18006db55  jge     loc_18006DBF9
0x18006db5b  mov     r12, [r14+8]
0x18006db5f  xor     r13d, r13d
0x18006db62  mov     r15, [rsp+68h+arg_18]
0x18006db6a  mov     r8, [rsp+68h+arg_10]
0x18006db72  mov     ecx, ebp
0x18006db74  movsxd  rbx, edi
0x18006db77  sub     ecx, edi
0x18006db79  add     rbx, rsi
0x18006db7c  mov     rdx, rbx
0x18006db7f  call    sqlite3_snprintf
0x18006db84  mov     rcx, rbx
0x18006db87  call    sqlite3Strlen30
0x18006db8c  mov     r8, [r12]
0x18006db90  lea     rdx, [rsp+68h+arg_8]
0x18006db95  add     eax, edi
0x18006db97  mov     [rsp+68h+arg_10], r15
0x18006db9f  mov     rcx, rsi
0x18006dba2  mov     [rsp+68h+arg_8], eax
0x18006dba6  call    identPut
0x18006dbab  movsx   rax, byte ptr [r12+0Ch]
0x18006dbb1  lea     rdx, off_1800B2BB0
0x18006dbb8  mov     rdx, [rdx+rax*8-208h]
0x18006dbc0  mov     rcx, rdx
0x18006dbc3  call    sqlite3Strlen30
0x18006dbc8  movsxd  rbx, [rsp+68h+arg_8]
0x18006dbcd  movsxd  rdi, eax
0x18006dbd0  mov     r8, rdi; Size
0x18006dbd3  lea     rcx, [rsi+rbx]; void *
0x18006dbd7  call    memcpy_0
0x18006dbdc  movsx   eax, word ptr [r14+36h]
0x18006dbe1  lea     r12, [r12+18h]
0x18006dbe6  add     edi, ebx
0x18006dbe8  inc     r13d
0x18006dbeb  cmp     r13d, eax
0x18006dbee  jl      loc_18006DB6A
0x18006dbf4  mov     r15, [rsp+68h+var_48]
0x18006dbf9  sub     ebp, edi
0x18006dbfb  movsxd  rdx, edi
0x18006dbfe  add     rdx, rsi
0x18006dc01  lea     r8, aS_7; "%s"
0x18006dc08  mov     ecx, ebp
0x18006dc0a  mov     r9, r15
0x18006dc0d  call    sqlite3_snprintf
0x18006dc12  mov     rax, rsi
0x18006dc15  mov     rbx, [rsp+68h+arg_0]
0x18006dc1a  add     rsp, 30h
0x18006dc1e  pop     r15
0x18006dc20  pop     r14
0x18006dc22  pop     r13
0x18006dc24  pop     r12
0x18006dc26  pop     rdi
0x18006dc27  pop     rsi
0x18006dc28  pop     rbp
0x18006dc29  retn
```
