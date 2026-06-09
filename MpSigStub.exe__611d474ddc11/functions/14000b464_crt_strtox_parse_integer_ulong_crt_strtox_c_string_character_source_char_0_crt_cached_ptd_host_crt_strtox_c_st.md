# __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<char>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)

- ea: `0x14000b464`
- end: `0x14000b718`
- name: `??$parse_integer@KV?$c_string_character_source@D@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z`
- size: `692`
- prototype: `__int64 __fastcall(__crt_cached_ptd_host *, char **, unsigned int, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000d240`

## callees

- `0x140004614`
- `0x1400046cc`
- `0x14000b464`
- `0x14000fa6c`

## pseudocode

```c
__int64 __fastcall __crt_strtox::parse_integer<unsigned long,__crt_strtox::c_string_character_source<char>,0>(
        __crt_cached_ptd_host *a1,
        char **a2,
        unsigned int a3,
        unsigned __int8 a4)
{
  char *v4; // r12
  unsigned int v5; // ebp
  char **v6; // rbx
  char **v8; // rcx
  char v9; // si
  char *v10; // rcx
  unsigned int v11; // r14d
  int v12; // edi
  int v13; // eax
  int v14; // eax
  int v15; // eax
  char *v16; // r8
  __int64 v17; // rdx
  unsigned int v18; // r9d
  __int64 v19; // rcx
  BOOL v20; // ecx
  bool v21; // cf
  bool v22; // zf
  char **v23; // rax
  int v25; // eax
  int v26; // ecx
  char **v27; // rdx
  char **v28; // rax

  v4 = *a2;
  v5 = a3;
  v6 = a2;
  if ( !*a2 )
  {
    *(_DWORD *)sub_14000FA6C(a1, a2) = 22;
    invalid_parameter_noinfo();
    goto LABEL_6;
  }
  if ( a3 && a3 - 2 > 0x22 )
  {
    *((_BYTE *)a1 + 48) = 1;
    *((_DWORD *)a1 + 11) = 22;
    sub_140004614(0, 0, 0, 0, 0, a1);
LABEL_6:
    v8 = (char **)v6[1];
    if ( v8 )
      *v8 = *v6;
    return 0;
  }
  v9 = *v4;
  v10 = v4 + 1;
  v11 = 0;
  *a2 = v4 + 1;
  v12 = a4 | 2;
  if ( v9 == 45 || (v12 = a4, v9 == 43) )
  {
    v9 = *v10;
    v10 = v4 + 2;
    *a2 = v4 + 2;
  }
  if ( (a3 & 0xFFFFFFEF) == 0 )
  {
    if ( (unsigned __int8)(v9 - 48) > 9u )
    {
      if ( (unsigned __int8)(v9 - 97) > 0x19u )
      {
        if ( (unsigned __int8)(v9 - 65) > 0x19u )
          goto LABEL_26;
        v13 = v9 - 55;
      }
      else
      {
        v13 = v9 - 87;
      }
    }
    else
    {
      v13 = v9 - 48;
    }
    if ( !v13 )
    {
      LOBYTE(a2) = *v10;
      *v6 = v10 + 1;
      if ( (((_BYTE)a2 - 88) & 0xDF) != 0 )
      {
        *v6 = v10;
        v14 = 8;
        if ( a3 )
          v14 = a3;
        v5 = v14;
        if ( (_BYTE)a2 && *v10 != (_BYTE)a2 )
        {
          *(_DWORD *)sub_14000FA6C(v10, a2) = 22;
          invalid_parameter_noinfo();
        }
        goto LABEL_30;
      }
      v9 = v10[1];
      *v6 = v10 + 2;
      v15 = 16;
      goto LABEL_27;
    }
LABEL_26:
    v15 = 10;
LABEL_27:
    if ( a3 )
      v15 = a3;
    v5 = v15;
  }
LABEL_30:
  v16 = *v6;
  v17 = 0xFFFFFFFF % v5;
  v18 = 0xFFFFFFFF / v5;
  while ( 1 )
  {
    if ( (unsigned __int8)(v9 - 48) > 9u )
    {
      if ( (unsigned __int8)(v9 - 97) > 0x19u )
        v19 = (unsigned __int8)(v9 - 65) > 0x19u ? 0xFFFFFFFFLL : (unsigned int)(v9 - 55);
      else
        v19 = (unsigned int)(v9 - 87);
    }
    else
    {
      v19 = (unsigned int)(v9 - 48);
    }
    if ( (unsigned int)v19 >= v5 )
      break;
    v9 = *v16;
    v17 = v5 * v11 + (unsigned int)v19;
    v20 = (unsigned int)v17 < v5 * v11;
    v21 = v11 < v18;
    v22 = v11 == v18;
    v11 = v17;
    v12 |= (4 * (!v21 && !v22 || v20)) | 8;
    *v6 = ++v16;
  }
  *v6 = v16 - 1;
  if ( v9 && *(v16 - 1) != v9 )
  {
    *(_DWORD *)sub_14000FA6C(v19, v17) = 22;
    invalid_parameter_noinfo();
  }
  if ( (v12 & 8) == 0 )
  {
    v23 = (char **)v6[1];
    *v6 = v4;
    if ( v23 )
      *v23 = v4;
    return 0;
  }
  if ( (v12 & 4) != 0 )
  {
    v25 = 1;
    v26 = v12;
    goto LABEL_55;
  }
  if ( (v12 & 1) == 0 )
  {
    if ( (v12 & 2) == 0 )
      goto LABEL_66;
    goto LABEL_65;
  }
  if ( (v12 & 2) == 0 )
  {
    if ( v11 <= 0x7FFFFFFF )
    {
LABEL_66:
      v28 = (char **)v6[1];
      if ( v28 )
        *v28 = *v6;
      return v11;
    }
    goto LABEL_54;
  }
  if ( v11 <= 0x80000000 )
  {
LABEL_65:
    v11 = -v11;
    goto LABEL_66;
  }
LABEL_54:
  v26 = 1;
  v25 = v12;
LABEL_55:
  *((_BYTE *)a1 + 48) = 1;
  *((_DWORD *)a1 + 11) = 34;
  if ( (v26 & v25) == 0 )
  {
    v11 = -1;
    goto LABEL_66;
  }
  v27 = (char **)v6[1];
  if ( (v12 & 2) != 0 )
  {
    if ( v27 )
      *v27 = *v6;
    return 0x80000000LL;
  }
  else
  {
    if ( v27 )
      *v27 = *v6;
    return 0x7FFFFFFF;
  }
}

```

## disassembly

```asm
0x14000b464  mov     [rsp+arg_0], rbx
0x14000b469  mov     [rsp+arg_8], rbp
0x14000b46e  mov     [rsp+arg_10], rsi
0x14000b473  push    rdi
0x14000b474  push    r12
0x14000b476  push    r13
0x14000b478  push    r14
0x14000b47a  push    r15
0x14000b47c  sub     rsp, 30h
0x14000b480  mov     r12, [rdx]
0x14000b483  mov     ebp, r8d
0x14000b486  mov     rbx, rdx
0x14000b489  mov     r13, rcx
0x14000b48c  test    r12, r12
0x14000b48f  jnz     short loc_14000B4A3
0x14000b491  call    sub_14000FA6C
0x14000b496  mov     dword ptr [rax], 16h
0x14000b49c  call    _invalid_parameter_noinfo
0x14000b4a1  jmp     short loc_14000B4D5
0x14000b4a3  test    ebp, ebp
0x14000b4a5  jz      short loc_14000B4ED
0x14000b4a7  lea     eax, [r8-2]
0x14000b4ab  cmp     eax, 22h ; '"'
0x14000b4ae  jbe     short loc_14000B4ED
0x14000b4b0  mov     byte ptr [rcx+30h], 1
0x14000b4b4  xor     r9d, r9d; LineNo
0x14000b4b7  mov     dword ptr [rcx+2Ch], 16h
0x14000b4be  xor     r8d, r8d; FileName
0x14000b4c1  mov     [rsp+58h+var_30], r13; __crt_cached_ptd_host *
0x14000b4c6  xor     ecx, ecx; Expression
0x14000b4c8  and     [rsp+58h+var_38], 0
0x14000b4ce  xor     edx, edx; FunctionName
0x14000b4d0  call    sub_140004614
0x14000b4d5  mov     rcx, [rbx+8]
0x14000b4d9  test    rcx, rcx
0x14000b4dc  jz      loc_14000B660
0x14000b4e2  mov     rax, [rbx]
0x14000b4e5  mov     [rcx], rax
0x14000b4e8  jmp     loc_14000B660
0x14000b4ed  mov     sil, [r12]
0x14000b4f1  lea     rcx, [r12+1]
0x14000b4f6  xor     r14d, r14d
0x14000b4f9  movzx   eax, r9b
0x14000b4fd  mov     edi, eax
0x14000b4ff  mov     [rdx], rcx
0x14000b502  lea     r15d, [r14+2]
0x14000b506  or      edi, r15d
0x14000b509  cmp     sil, 2Dh ; '-'
0x14000b50d  cmovnz  edi, eax
0x14000b510  jz      short loc_14000B518
0x14000b512  cmp     sil, 2Bh ; '+'
0x14000b516  jnz     short loc_14000B521
0x14000b518  mov     sil, [rcx]
0x14000b51b  inc     rcx
0x14000b51e  mov     [rdx], rcx
0x14000b521  test    ebp, 0FFFFFFEFh
0x14000b527  jnz     loc_14000B5B5
0x14000b52d  lea     eax, [rsi-30h]
0x14000b530  cmp     al, 9
0x14000b532  ja      short loc_14000B53D
0x14000b534  movsx   eax, sil
0x14000b538  add     eax, 0FFFFFFD0h
0x14000b53b  jmp     short loc_14000B55B
0x14000b53d  lea     eax, [rsi-61h]
0x14000b540  cmp     al, 19h
0x14000b542  ja      short loc_14000B54D
0x14000b544  movsx   eax, sil
0x14000b548  add     eax, 0FFFFFFA9h
0x14000b54b  jmp     short loc_14000B55B
0x14000b54d  lea     eax, [rsi-41h]
0x14000b550  cmp     al, 19h
0x14000b552  ja      short loc_14000B5A9
0x14000b554  movsx   eax, sil
0x14000b558  add     eax, 0FFFFFFC9h
0x14000b55b  test    eax, eax
0x14000b55d  jnz     short loc_14000B5A9
0x14000b55f  mov     dl, [rcx]
0x14000b561  lea     r8, [rcx+1]
0x14000b565  mov     [rbx], r8
0x14000b568  lea     eax, [rdx-58h]
0x14000b56b  test    al, 0DFh
0x14000b56d  jz      short loc_14000B598
0x14000b56f  test    ebp, ebp
0x14000b571  mov     [rbx], rcx
0x14000b574  mov     eax, 8
0x14000b579  cmovnz  eax, ebp
0x14000b57c  mov     ebp, eax
0x14000b57e  test    dl, dl
0x14000b580  jz      short loc_14000B5B5
0x14000b582  cmp     [rcx], dl
0x14000b584  jz      short loc_14000B5B5
0x14000b586  call    sub_14000FA6C
0x14000b58b  mov     dword ptr [rax], 16h
0x14000b591  call    _invalid_parameter_noinfo
0x14000b596  jmp     short loc_14000B5B5
0x14000b598  mov     sil, [r8]
0x14000b59b  lea     rax, [r8+1]
0x14000b59f  mov     [rbx], rax
0x14000b5a2  mov     eax, 10h
0x14000b5a7  jmp     short loc_14000B5AE
0x14000b5a9  mov     eax, 0Ah
0x14000b5ae  test    ebp, ebp
0x14000b5b0  cmovnz  eax, ebp
0x14000b5b3  mov     ebp, eax
0x14000b5b5  mov     r8, [rbx]
0x14000b5b8  xor     edx, edx
0x14000b5ba  or      eax, 0FFFFFFFFh
0x14000b5bd  div     ebp
0x14000b5bf  mov     r9d, eax
0x14000b5c2  lea     ecx, [rsi-30h]
0x14000b5c5  cmp     cl, 9
0x14000b5c8  ja      short loc_14000B5D3
0x14000b5ca  movsx   ecx, sil
0x14000b5ce  add     ecx, 0FFFFFFD0h
0x14000b5d1  jmp     short loc_14000B5F6
0x14000b5d3  lea     eax, [rsi-61h]
0x14000b5d6  cmp     al, 19h
0x14000b5d8  ja      short loc_14000B5E3
0x14000b5da  movsx   ecx, sil
0x14000b5de  add     ecx, 0FFFFFFA9h
0x14000b5e1  jmp     short loc_14000B5F6
0x14000b5e3  lea     eax, [rsi-41h]
0x14000b5e6  cmp     al, 19h
0x14000b5e8  ja      short loc_14000B5F3
0x14000b5ea  movsx   ecx, sil
0x14000b5ee  add     ecx, 0FFFFFFC9h
0x14000b5f1  jmp     short loc_14000B5F6
0x14000b5f3  or      ecx, 0FFFFFFFFh
0x14000b5f6  cmp     ecx, ebp
0x14000b5f8  jnb     short loc_14000B62A
0x14000b5fa  mov     sil, [r8]
0x14000b5fd  mov     eax, r14d
0x14000b600  imul    eax, ebp
0x14000b603  lea     edx, [rax+rcx]
0x14000b606  xor     ecx, ecx
0x14000b608  cmp     edx, eax
0x14000b60a  setb    cl
0x14000b60d  xor     eax, eax
0x14000b60f  cmp     r14d, r9d
0x14000b612  mov     r14d, edx
0x14000b615  setnbe  al
0x14000b618  or      ecx, eax
0x14000b61a  shl     ecx, 2
0x14000b61d  or      ecx, 8
0x14000b620  or      edi, ecx
0x14000b622  inc     r8
0x14000b625  mov     [rbx], r8
0x14000b628  jmp     short loc_14000B5C2
0x14000b62a  lea     rax, [r8-1]
0x14000b62e  mov     [rbx], rax
0x14000b631  test    sil, sil
0x14000b634  jz      short loc_14000B64B
0x14000b636  cmp     [rax], sil
0x14000b639  jz      short loc_14000B64B
0x14000b63b  call    sub_14000FA6C
0x14000b640  mov     dword ptr [rax], 16h
0x14000b646  call    _invalid_parameter_noinfo
0x14000b64b  test    dil, 8
0x14000b64f  jnz     short loc_14000B667
0x14000b651  mov     rax, [rbx+8]
0x14000b655  mov     [rbx], r12
0x14000b658  test    rax, rax
0x14000b65b  jz      short loc_14000B660
0x14000b65d  mov     [rax], r12
0x14000b660  xor     eax, eax
0x14000b662  jmp     loc_14000B6FB
0x14000b667  mov     r8d, 80000000h
0x14000b66d  lea     r9d, [r8-1]
0x14000b671  test    dil, 4
0x14000b675  jz      short loc_14000B680
0x14000b677  mov     eax, 1
0x14000b67c  mov     ecx, edi
0x14000b67e  jmp     short loc_14000B69E
0x14000b680  test    dil, 1
0x14000b684  jz      short loc_14000B6E1
0x14000b686  test    r15b, dil
0x14000b689  jz      short loc_14000B692
0x14000b68b  cmp     r14d, r8d
0x14000b68e  jbe     short loc_14000B6E6
0x14000b690  jmp     short loc_14000B697
0x14000b692  cmp     r14d, r9d
0x14000b695  jbe     short loc_14000B6E9
0x14000b697  mov     ecx, 1
0x14000b69c  mov     eax, edi
0x14000b69e  and     r15d, edi
0x14000b6a1  mov     byte ptr [r13+30h], 1
0x14000b6a6  mov     dword ptr [r13+2Ch], 22h ; '"'
0x14000b6ae  test    eax, ecx
0x14000b6b0  jnz     short loc_14000B6B8
0x14000b6b2  or      r14d, 0FFFFFFFFh
0x14000b6b6  jmp     short loc_14000B6E9
0x14000b6b8  mov     rdx, [rbx+8]
0x14000b6bc  test    r15d, r15d
0x14000b6bf  jz      short loc_14000B6D1
0x14000b6c1  test    rdx, rdx
0x14000b6c4  jz      short loc_14000B6CC
0x14000b6c6  mov     rcx, [rbx]
0x14000b6c9  mov     [rdx], rcx
0x14000b6cc  mov     eax, r8d
0x14000b6cf  jmp     short loc_14000B6FB
0x14000b6d1  test    rdx, rdx
0x14000b6d4  jz      short loc_14000B6DC
0x14000b6d6  mov     rcx, [rbx]
0x14000b6d9  mov     [rdx], rcx
0x14000b6dc  mov     eax, r9d
0x14000b6df  jmp     short loc_14000B6FB
0x14000b6e1  test    r15b, dil
0x14000b6e4  jz      short loc_14000B6E9
0x14000b6e6  neg     r14d
0x14000b6e9  mov     rax, [rbx+8]
0x14000b6ed  test    rax, rax
0x14000b6f0  jz      short loc_14000B6F8
0x14000b6f2  mov     rcx, [rbx]
0x14000b6f5  mov     [rax], rcx
0x14000b6f8  mov     eax, r14d
0x14000b6fb  mov     rbx, [rsp+58h+arg_0]
0x14000b700  mov     rbp, [rsp+58h+arg_8]
0x14000b705  mov     rsi, [rsp+58h+arg_10]
0x14000b70a  add     rsp, 30h
0x14000b70e  pop     r15
0x14000b710  pop     r14
0x14000b712  pop     r13
0x14000b714  pop     r12
0x14000b716  pop     rdi
0x14000b717  retn
```
