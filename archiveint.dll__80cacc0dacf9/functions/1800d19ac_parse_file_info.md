# parse_file_info

- ea: `0x1800d19ac`
- end: `0x1800d1ec6`
- name: `parse_file_info`
- size: `1306`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x1800d06b4`
- `0x1800d2780`

## callees

- `0x180006c00`
- `0x18000a2d0`
- `0x1800aba54`
- `0x1800d13c0`
- `0x1800d146c`
- `0x1800d19ac`
- `0x1800d1ecc`
- `0x1800d2d0c`
- `0x180119956`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800d1aca`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800d1aca`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d1e6b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d1e7b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d1e6b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d1e7b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800d1b8c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800d1b8c`

## string_xrefs

- `0x1800d1e9f`: `Invalid length of directory record`
- `0x1800d1aac`: `Directory structure contains loop`
- `0x1800d1d65`: `rr_moved`
- `0x1800d1d78`: `.rr_moved`

## pseudocode

```c
char *__fastcall parse_file_info(__int64 a1, __int64 a2, unsigned __int8 *a3, unsigned __int64 a4)
{
  __int64 v6; // r14
  unsigned __int64 v7; // r10
  unsigned __int64 v8; // rsi
  __int64 v9; // r10
  unsigned int v10; // r8d
  __int64 v11; // r12
  __int64 v12; // r15
  _QWORD *v13; // r8
  int v14; // edx
  const char *v15; // r8
  __int64 v16; // rbp
  __int64 i; // rax
  __int64 v18; // rdx
  char *v19; // rax
  char *v20; // rbx
  __int64 v21; // rax
  unsigned __int8 *v22; // rbp
  unsigned __int64 v23; // rax
  size_t v24; // rsi
  void *v25; // rax
  int v26; // r12d
  __int64 v27; // rax
  int v28; // edx
  unsigned __int8 *v29; // rdx
  unsigned __int8 *v30; // r9
  int v31; // ecx
  const char *v32; // rbp
  __int64 v33; // rcx
  __int64 j; // rax
  void *v35; // rcx
  char *result; // rax
  unsigned __int64 v37; // [rsp+20h] [rbp-48h]
  int v38; // [rsp+70h] [rbp+8h]
  unsigned __int8 *v39; // [rsp+88h] [rbp+20h]

  v6 = a1;
  if ( !a4 || (v7 = *a3, v37 = v7, a4 < v7) || v7 < 0x22 )
  {
    v15 = "Invalid length of directory record";
LABEL_99:
    v18 = -1;
LABEL_100:
    archive_set_error(a1, v18, v15);
    return 0;
  }
  v8 = a3[32];
  v10 = toi(a3 + 10, 4);
  if ( v9 - 33 < v8 || !v8 )
  {
    v15 = "Invalid length of file identifier";
    goto LABEL_11;
  }
  v11 = v10;
  v12 = **(_QWORD **)(v6 + 2072);
  v13 = (_QWORD *)(v12 + 168);
  v14 = a3[2] | ((a3[3] | (*((unsigned __int16 *)a3 + 2) << 8)) << 8);
  v38 = v14;
  if ( v14 > 0 && v14 + (unsigned __int64)(v11 + *v13 - 1LL) / *v13 > *(unsigned int *)(v12 + 184) || v11 && v14 < 0 )
  {
    v15 = "Invalid location of extent of file";
LABEL_11:
    a1 = v6;
    goto LABEL_99;
  }
  v16 = *v13 * v14;
  for ( i = a2; i; i = *(_QWORD *)(i + 8) )
  {
    if ( *(_QWORD *)(i + 48) == v16 )
    {
      v15 = "Directory structure contains loop";
      v18 = 42;
LABEL_17:
      a1 = v6;
      goto LABEL_100;
    }
  }
  v19 = (char *)calloc(1u, 0x128u);
  v20 = v19;
  if ( !v19 )
  {
    v15 = "No memory for file entry";
    v18 = 12;
    goto LABEL_17;
  }
  *((_QWORD *)v19 + 1) = a2;
  *((_QWORD *)v19 + 6) = v16;
  *((_QWORD *)v19 + 7) = v11;
  if ( (unsigned int)isodate7_valid(a3 + 18) )
  {
    *((_DWORD *)v20 + 22) |= 0xEu;
    v21 = isodate7();
    *((_QWORD *)v20 + 13) = v21;
    *((_QWORD *)v20 + 14) = v21;
    *((_QWORD *)v20 + 15) = v21;
  }
  *((_QWORD *)v20 + 35) = 0;
  *((_QWORD *)v20 + 36) = v20 + 280;
  v22 = a3 + 33;
  v39 = &a3[((v8 & 1) == 0) + 33 + v8];
  if ( !*(_BYTE *)(v12 + 42) )
  {
    if ( v8 > 2 )
    {
      if ( v22[v8 - 2] != 59 || v22[v8 - 1] != 49 )
        goto LABEL_39;
      v8 -= 2LL;
    }
    if ( v8 <= 1 )
    {
LABEL_41:
      *((_QWORD *)v20 + 21) = 0;
      archive_strncat(v20 + 160, a3 + 33, v8);
      goto LABEL_42;
    }
LABEL_39:
    if ( v22[v8 - 1] == 46 )
      --v8;
    goto LABEL_41;
  }
  v23 = 206;
  if ( v8 <= 0xCE )
  {
    v23 = v8 & 0xFFFFFFFFFFFFFFFEuLL;
    v24 = v23;
    if ( v23 <= 4 )
      goto LABEL_31;
  }
  else
  {
    v24 = 206;
  }
  if ( !v22[v23 - 4] && v22[v23 - 3] == 59 && !v22[v23 - 2] && v22[v23 - 1] == 49 )
    v24 = v23 - 4;
LABEL_31:
  v25 = malloc(v24);
  *((_QWORD *)v20 + 23) = v25;
  if ( v25 )
  {
    memcpy_0(v25, a3 + 33, v24);
    *((_QWORD *)v20 + 24) = v24;
LABEL_42:
    v26 = a3[25] & 2;
    v27 = (unsigned int)v38;
    v28 = (a3[25] >> 7) & 1;
    *((_WORD *)v20 + 68) = v26 != 0 ? 16832 : -32512;
    *((_DWORD *)v20 + 64) = v28;
    if ( !*((_QWORD *)v20 + 7) && v38 >= 0 )
    {
      *((_QWORD *)v20 + 6) = -1;
      v27 = -1;
    }
    *((_QWORD *)v20 + 18) = v27;
    if ( *(_DWORD *)(v12 + 8) )
    {
      v29 = v39;
      v30 = &a3[v37];
      if ( !a2 && v30 - v39 >= 7 )
      {
        v31 = *(_DWORD *)v39 - 17256531;
        if ( *(_DWORD *)v39 == 17256531 )
          v31 = *((unsigned __int16 *)v39 + 2) - 61374;
        if ( !v31 )
        {
          v29 = v39 + 7;
          *(_BYTE *)(v12 + 43) = v39[6];
          *(_BYTE *)(v12 + 41) = 1;
        }
      }
      if ( *(_BYTE *)(v12 + 41) )
      {
        v20[200] = 0;
        v20[232] = 0;
        if ( (unsigned int)parse_rockridge(v6, v20, &v29[*(unsigned __int8 *)(v12 + 43)], v30) )
          goto LABEL_95;
        if ( *((_QWORD *)v20 + 7) && (*((_WORD *)v20 + 68) & 0xF000) == 0xA000 )
        {
          *((_QWORD *)v20 + 7) = 0;
          *((_QWORD *)v20 + 18) = -1;
          *((_QWORD *)v20 + 6) = -1;
        }
      }
      else
      {
        *(_DWORD *)(v12 + 8) = 0;
      }
    }
    *((_DWORD *)v20 + 38) = 1;
    if ( a2 && v26 )
      ++*(_DWORD *)(a2 + 32);
    if ( *(_BYTE *)(v12 + 40) )
    {
      if ( a2
        && !*(_QWORD *)(a2 + 8)
        && v26
        && !*(_QWORD *)(v12 + 48)
        && (v32 = (const char *)*((_QWORD *)v20 + 20)) != 0
        && (!strcmp_0(*((const char **)v20 + 20), "rr_moved") || !strcmp_0(v32, ".rr_moved")) )
      {
        *(_QWORD *)(v12 + 48) = v20;
        *((_WORD *)v20 + 36) = 257;
        v20[74] = 0;
        --*(_DWORD *)(a2 + 32);
      }
      else if ( v20[74] )
      {
        if ( !a2 || !*(_BYTE *)(a2 + 72) )
          goto LABEL_76;
        if ( *((_QWORD *)v20 + 10) )
        {
          archive_set_error(v6, 0xFFFFFFFFLL, "Invalid Rockridge RE and CL");
          goto LABEL_95;
        }
        if ( !v26 )
        {
LABEL_76:
          archive_set_error(v6, 0xFFFFFFFFLL, "Invalid Rockridge RE");
          goto LABEL_95;
        }
      }
      else if ( a2 )
      {
        if ( *(_BYTE *)(a2 + 72) )
        {
          v20[73] = 0;
        }
        else if ( v26 && (*(_BYTE *)(a2 + 74) || *(_BYTE *)(a2 + 75)) )
        {
          v20[75] = 1;
        }
      }
      if ( *((_QWORD *)v20 + 10) )
      {
        if ( !a2 || !*(_QWORD *)(a2 + 8) || v26 )
          goto LABEL_94;
        ++*(_DWORD *)(a2 + 32);
        v33 = *((_QWORD *)v20 + 10);
        *((_QWORD *)v20 + 18) = v33 + 1;
        *((_QWORD *)v20 + 6) = v33 + 1;
        for ( j = a2; j; j = *(_QWORD *)(j + 8) )
        {
          if ( *(_QWORD *)(j + 48) == v33 )
            goto LABEL_94;
        }
        if ( v33 == *((_QWORD *)v20 + 6) || *(_BYTE *)(a2 + 72) )
        {
LABEL_94:
          archive_set_error(v6, 0xFFFFFFFFLL, "Invalid Rockridge CL");
          goto LABEL_95;
        }
      }
    }
    *(_QWORD *)v20 = *(_QWORD *)(v12 + 104);
    result = v20;
    *(_QWORD *)(v12 + 104) = v20;
    return result;
  }
  archive_set_error(v6, 12, "No memory for file name");
LABEL_95:
  v35 = (void *)*((_QWORD *)v20 + 20);
  *((_QWORD *)v20 + 21) = 0;
  *((_QWORD *)v20 + 22) = 0;
  free(v35);
  *((_QWORD *)v20 + 20) = 0;
  free(v20);
  return 0;
}

```

## disassembly

```asm
0x1800d19ac  mov     [rsp+arg_8], rbx
0x1800d19b1  push    rbp
0x1800d19b2  push    rsi
0x1800d19b3  push    rdi
0x1800d19b4  push    r12
0x1800d19b6  push    r13
0x1800d19b8  push    r14
0x1800d19ba  push    r15
0x1800d19bc  sub     rsp, 30h
0x1800d19c0  mov     r13, r8
0x1800d19c3  mov     rdi, rdx
0x1800d19c6  mov     r14, rcx
0x1800d19c9  test    r9, r9
0x1800d19cc  jz      loc_1800D1E9F
0x1800d19d2  movzx   r10d, byte ptr [r8]
0x1800d19d6  mov     [rsp+68h+var_48], r10
0x1800d19db  cmp     r9, r10
0x1800d19de  jb      loc_1800D1E9F
0x1800d19e4  cmp     r10, 22h ; '"'
0x1800d19e8  jb      loc_1800D1E9F
0x1800d19ee  movzx   esi, byte ptr [r8+20h]
0x1800d19f3  lea     rcx, [r8+0Ah]
0x1800d19f7  mov     edx, 4
0x1800d19fc  call    toi
0x1800d1a01  lea     rcx, [r10-21h]
0x1800d1a05  mov     r8d, eax
0x1800d1a08  cmp     rcx, rsi
0x1800d1a0b  jb      loc_1800D1E93
0x1800d1a11  test    rsi, rsi
0x1800d1a14  jz      loc_1800D1E93
0x1800d1a1a  mov     rcx, [r14+818h]
0x1800d1a21  mov     r12d, r8d
0x1800d1a24  movzx   eax, byte ptr [r13+3]
0x1800d1a29  movzx   edx, byte ptr [r13+5]
0x1800d1a2e  shl     edx, 8
0x1800d1a31  mov     r15, [rcx]
0x1800d1a34  movzx   ecx, byte ptr [r13+4]
0x1800d1a39  or      edx, ecx
0x1800d1a3b  shl     edx, 8
0x1800d1a3e  or      edx, eax
0x1800d1a40  lea     r8, [r15+0A8h]
0x1800d1a47  movzx   eax, byte ptr [r13+2]
0x1800d1a4c  shl     edx, 8
0x1800d1a4f  or      edx, eax
0x1800d1a51  mov     [rsp+68h+arg_0], edx
0x1800d1a55  movsxd  rbp, edx
0x1800d1a58  jle     short loc_1800D1A7C
0x1800d1a5a  mov     rcx, [r8]
0x1800d1a5d  xor     edx, edx
0x1800d1a5f  lea     rax, [rcx-1]
0x1800d1a63  add     rax, r12
0x1800d1a66  div     rcx
0x1800d1a69  mov     ecx, [r15+0B8h]
0x1800d1a70  add     rax, rbp
0x1800d1a73  cmp     rax, rcx
0x1800d1a76  ja      short loc_1800D1A85
0x1800d1a78  mov     edx, [rsp+68h+arg_0]
0x1800d1a7c  test    r12, r12
0x1800d1a7f  jz      short loc_1800D1A94
0x1800d1a81  test    edx, edx
0x1800d1a83  jns     short loc_1800D1A94
0x1800d1a85  lea     r8, aInvalidLocatio; "Invalid location of extent of file"
0x1800d1a8c  mov     rcx, r14
0x1800d1a8f  jmp     loc_1800D1EA6
0x1800d1a94  imul    rbp, [r8]
0x1800d1a98  mov     rax, rdi
0x1800d1a9b  test    rax, rax
0x1800d1a9e  jz      short loc_1800D1AC0
0x1800d1aa0  cmp     [rax+30h], rbp
0x1800d1aa4  jz      short loc_1800D1AAC
0x1800d1aa6  mov     rax, [rax+8]
0x1800d1aaa  jmp     short loc_1800D1A9B
0x1800d1aac  lea     r8, aDirectoryStruc; "Directory structure contains loop"
0x1800d1ab3  mov     edx, 2Ah ; '*'
0x1800d1ab8  mov     rcx, r14
0x1800d1abb  jmp     loc_1800D1EAA
0x1800d1ac0  mov     edx, 128h; Size
0x1800d1ac5  mov     ecx, 1; Count
0x1800d1aca  call    cs:__imp_calloc
0x1800d1ad0  mov     rbx, rax
0x1800d1ad3  test    rax, rax
0x1800d1ad6  jnz     short loc_1800D1AE4
0x1800d1ad8  lea     r8, aNoMemoryForFil; "No memory for file entry"
0x1800d1adf  lea     edx, [rax+0Ch]
0x1800d1ae2  jmp     short loc_1800D1AB8
0x1800d1ae4  lea     rcx, [r13+12h]
0x1800d1ae8  mov     [rax+8], rdi
0x1800d1aec  mov     [rax+30h], rbp
0x1800d1af0  mov     [rax+38h], r12
0x1800d1af4  call    isodate7_valid
0x1800d1af9  xor     r12d, r12d
0x1800d1afc  test    eax, eax
0x1800d1afe  jz      short loc_1800D1B15
0x1800d1b00  or      dword ptr [rbx+58h], 0Eh
0x1800d1b04  call    isodate7
0x1800d1b09  mov     [rbx+68h], rax
0x1800d1b0d  mov     [rbx+70h], rax
0x1800d1b11  mov     [rbx+78h], rax
0x1800d1b15  lea     rax, [rbx+118h]
0x1800d1b1c  mov     rcx, rsi
0x1800d1b1f  not     rcx
0x1800d1b22  mov     [rax], r12
0x1800d1b25  and     ecx, 1
0x1800d1b28  mov     [rbx+120h], rax
0x1800d1b2f  lea     rbp, [r13+21h]
0x1800d1b33  add     rcx, rbp
0x1800d1b36  add     rcx, rsi
0x1800d1b39  mov     [rsp+68h+arg_18], rcx
0x1800d1b41  cmp     [r15+2Ah], r12b
0x1800d1b45  jz      loc_1800D1BCF
0x1800d1b4b  mov     eax, 0CEh
0x1800d1b50  cmp     rsi, rax
0x1800d1b53  jbe     short loc_1800D1B59
0x1800d1b55  mov     esi, eax
0x1800d1b57  jmp     short loc_1800D1B69
0x1800d1b59  mov     rax, rsi
0x1800d1b5c  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800d1b60  mov     rsi, rax
0x1800d1b63  cmp     rax, 4
0x1800d1b67  jbe     short loc_1800D1B89
0x1800d1b69  cmp     [rax+rbp-4], r12b
0x1800d1b6e  jnz     short loc_1800D1B89
0x1800d1b70  cmp     byte ptr [rax+rbp-3], 3Bh ; ';'
0x1800d1b75  jnz     short loc_1800D1B89
0x1800d1b77  cmp     [rax+rbp-2], r12b
0x1800d1b7c  jnz     short loc_1800D1B89
0x1800d1b7e  cmp     byte ptr [rax+rbp-1], 31h ; '1'
0x1800d1b83  jnz     short loc_1800D1B89
0x1800d1b85  lea     rsi, [rax-4]
0x1800d1b89  mov     rcx, rsi; Size
0x1800d1b8c  call    cs:__imp_malloc
0x1800d1b92  mov     [rbx+0B8h], rax
0x1800d1b99  test    rax, rax
0x1800d1b9c  jnz     short loc_1800D1BB8
0x1800d1b9e  lea     r8, aNoMemoryForFil_0; "No memory for file name"
0x1800d1ba5  mov     rcx, r14
0x1800d1ba8  lea     edx, [rax+0Ch]
0x1800d1bab  call    archive_set_error
0x1800d1bb0  xor     r13d, r13d
0x1800d1bb3  jmp     loc_1800D1E56
0x1800d1bb8  mov     r8, rsi; Size
0x1800d1bbb  mov     rdx, rbp; Src
0x1800d1bbe  mov     rcx, rax; void *
0x1800d1bc1  call    memcpy_0
0x1800d1bc6  mov     [rbx+0C0h], rsi
0x1800d1bcd  jmp     short loc_1800D1C10
0x1800d1bcf  cmp     rsi, 2
0x1800d1bd3  jbe     short loc_1800D1BE7
0x1800d1bd5  cmp     byte ptr [rsi+rbp-2], 3Bh ; ';'
0x1800d1bda  jnz     short loc_1800D1BED
0x1800d1bdc  cmp     byte ptr [rsi+rbp-1], 31h ; '1'
0x1800d1be1  jnz     short loc_1800D1BED
0x1800d1be3  sub     rsi, 2
0x1800d1be7  cmp     rsi, 1
0x1800d1beb  jbe     short loc_1800D1BF7
0x1800d1bed  cmp     byte ptr [rsi+rbp-1], 2Eh ; '.'
0x1800d1bf2  jnz     short loc_1800D1BF7
0x1800d1bf4  dec     rsi
0x1800d1bf7  lea     rcx, [rbx+0A0h]
0x1800d1bfe  mov     [rbx+0A8h], r12
0x1800d1c05  mov     r8, rsi
0x1800d1c08  mov     rdx, rbp
0x1800d1c0b  call    archive_strncat
0x1800d1c10  movzx   edx, byte ptr [r13+19h]
0x1800d1c15  mov     r12d, edx
0x1800d1c18  and     r12d, 2
0x1800d1c1c  mov     eax, r12d
0x1800d1c1f  neg     eax
0x1800d1c21  mov     eax, [rsp+68h+arg_0]
0x1800d1c25  sbb     cx, cx
0x1800d1c28  shr     edx, 7
0x1800d1c2b  and     cx, 0C0C0h
0x1800d1c30  and     edx, 1
0x1800d1c33  add     cx, 8100h
0x1800d1c38  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800d1c3c  mov     [rbx+88h], cx
0x1800d1c43  mov     [rbx+100h], edx
0x1800d1c49  cmp     qword ptr [rbx+38h], 0
0x1800d1c4e  jnz     short loc_1800D1C5B
0x1800d1c50  test    eax, eax
0x1800d1c52  js      short loc_1800D1C5B
0x1800d1c54  mov     [rbx+30h], rsi
0x1800d1c58  mov     rax, rsi
0x1800d1c5b  mov     [rbx+90h], rax
0x1800d1c62  cmp     dword ptr [r15+8], 0
0x1800d1c67  jz      loc_1800D1D1F
0x1800d1c6d  mov     r9, [rsp+68h+var_48]
0x1800d1c72  mov     rdx, [rsp+68h+arg_18]
0x1800d1c7a  add     r9, r13
0x1800d1c7d  xor     r13d, r13d
0x1800d1c80  test    rdi, rdi
0x1800d1c83  jnz     short loc_1800D1CBA
0x1800d1c85  mov     rax, r9
0x1800d1c88  sub     rax, rdx
0x1800d1c8b  cmp     rax, 7
0x1800d1c8f  jl      short loc_1800D1CBA
0x1800d1c91  mov     ecx, [rdx]
0x1800d1c93  sub     ecx, 1075053h
0x1800d1c99  jnz     short loc_1800D1CA6
0x1800d1c9b  movzx   ecx, word ptr [rdx+4]
0x1800d1c9f  mov     eax, 0EFBEh
0x1800d1ca4  sub     ecx, eax
0x1800d1ca6  test    ecx, ecx
0x1800d1ca8  jnz     short loc_1800D1CBA
0x1800d1caa  mov     al, [rdx+6]
0x1800d1cad  add     rdx, 7
0x1800d1cb1  mov     [r15+2Bh], al
0x1800d1cb5  mov     byte ptr [r15+29h], 1
0x1800d1cba  cmp     [r15+29h], r13b
0x1800d1cbe  jz      short loc_1800D1D19
0x1800d1cc0  mov     [rbx+0C8h], r13b
0x1800d1cc7  mov     rcx, r14
0x1800d1cca  mov     [rbx+0E8h], r13b
0x1800d1cd1  movzx   r8d, byte ptr [r15+2Bh]
0x1800d1cd6  add     r8, rdx
0x1800d1cd9  mov     rdx, rbx
0x1800d1cdc  call    parse_rockridge
0x1800d1ce1  test    eax, eax
0x1800d1ce3  jnz     loc_1800D1E56
0x1800d1ce9  cmp     [rbx+38h], r13
0x1800d1ced  jbe     short loc_1800D1D22
0x1800d1cef  movzx   eax, word ptr [rbx+88h]
0x1800d1cf6  mov     ecx, 0F000h
0x1800d1cfb  and     ax, cx
0x1800d1cfe  mov     ecx, 0A000h
0x1800d1d03  cmp     ax, cx
0x1800d1d06  jnz     short loc_1800D1D22
0x1800d1d08  mov     [rbx+38h], r13
0x1800d1d0c  mov     [rbx+90h], rsi
0x1800d1d13  mov     [rbx+30h], rsi
0x1800d1d17  jmp     short loc_1800D1D22
0x1800d1d19  mov     [r15+8], r13d
0x1800d1d1d  jmp     short loc_1800D1D22
0x1800d1d1f  xor     r13d, r13d
0x1800d1d22  mov     dword ptr [rbx+98h], 1
0x1800d1d2c  test    rdi, rdi
0x1800d1d2f  jz      short loc_1800D1D39
0x1800d1d31  test    r12d, r12d
0x1800d1d34  jz      short loc_1800D1D39
0x1800d1d36  inc     dword ptr [rdi+20h]
0x1800d1d39  cmp     [r15+28h], r13b
0x1800d1d3d  jz      loc_1800D1E83
0x1800d1d43  test    rdi, rdi
0x1800d1d46  jz      short loc_1800D1D9E
0x1800d1d48  cmp     [rdi+8], r13
0x1800d1d4c  jnz     short loc_1800D1D9E
0x1800d1d4e  test    r12d, r12d
0x1800d1d51  jz      short loc_1800D1D9E
0x1800d1d53  cmp     [r15+30h], r13
0x1800d1d57  jnz     short loc_1800D1D9E
0x1800d1d59  mov     rbp, [rbx+0A0h]
0x1800d1d60  test    rbp, rbp
0x1800d1d63  jz      short loc_1800D1D9E
0x1800d1d65  lea     rdx, aRrMoved; "rr_moved"
0x1800d1d6c  mov     rcx, rbp; Str1
0x1800d1d6f  call    strcmp_0
0x1800d1d74  test    eax, eax
0x1800d1d76  jz      short loc_1800D1D8B
0x1800d1d78  lea     rdx, aRrMoved_0; ".rr_moved"
0x1800d1d7f  mov     rcx, rbp; Str1
0x1800d1d82  call    strcmp_0
0x1800d1d87  test    eax, eax
0x1800d1d89  jnz     short loc_1800D1D9E
0x1800d1d8b  mov     [r15+30h], rbx
0x1800d1d8f  mov     word ptr [rbx+48h], 101h
0x1800d1d95  mov     [rbx+4Ah], r13b
0x1800d1d99  add     [rdi+20h], esi
0x1800d1d9c  jmp     short loc_1800D1DF5
0x1800d1d9e  cmp     [rbx+4Ah], r13b
0x1800d1da2  jz      short loc_1800D1DCF
0x1800d1da4  test    rdi, rdi
0x1800d1da7  jz      short loc_1800D1DC6
0x1800d1da9  cmp     [rdi+48h], r13b
0x1800d1dad  jz      short loc_1800D1DC6
0x1800d1daf  cmp     [rbx+50h], r13
0x1800d1db3  jz      short loc_1800D1DC1
0x1800d1db5  lea     r8, aInvalidRockrid_1; "Invalid Rockridge RE and CL"
0x1800d1dbc  jmp     loc_1800D1E4C
0x1800d1dc1  test    r12d, r12d
0x1800d1dc4  jnz     short loc_1800D1DF5
0x1800d1dc6  lea     r8, aInvalidRockrid_0; "Invalid Rockridge RE"
0x1800d1dcd  jmp     short loc_1800D1E4C
0x1800d1dcf  test    rdi, rdi
0x1800d1dd2  jz      short loc_1800D1DF5
0x1800d1dd4  cmp     [rdi+48h], r13b
0x1800d1dd8  jz      short loc_1800D1DE0
0x1800d1dda  mov     [rbx+49h], r13b
0x1800d1dde  jmp     short loc_1800D1DF5
0x1800d1de0  test    r12d, r12d
0x1800d1de3  jz      short loc_1800D1DF5
0x1800d1de5  cmp     [rdi+4Ah], r13b
0x1800d1de9  jnz     short loc_1800D1DF1
0x1800d1deb  cmp     [rdi+4Bh], r13b
0x1800d1def  jz      short loc_1800D1DF5
0x1800d1df1  mov     byte ptr [rbx+4Bh], 1
0x1800d1df5  cmp     [rbx+50h], r13
0x1800d1df9  jz      loc_1800D1E83
0x1800d1dff  test    rdi, rdi
0x1800d1e02  jz      short loc_1800D1E45
0x1800d1e04  cmp     [rdi+8], r13
  ... truncated ...
```
