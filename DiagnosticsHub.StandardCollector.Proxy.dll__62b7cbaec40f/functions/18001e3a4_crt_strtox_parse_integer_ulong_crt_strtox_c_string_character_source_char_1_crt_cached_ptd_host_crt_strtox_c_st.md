# __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<char>,1>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)

- ea: `0x18001e3a4`
- end: `0x18001e67d`
- name: `??$parse_integer@KV?$c_string_character_source@D@__crt_strtox@@$00@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z`
- size: `729`
- prototype: `__int64 __fastcall(__crt_cached_ptd_host *)`
- caller_count: `5`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001f87c`
- `0x180020238`
- `0x1800202f4`
- `0x180020b00`
- `0x180020bb0`

## callees

- `0x180007b48`
- `0x180007c00`
- `0x180007ee8`
- `0x18001512c`
- `0x18001e3a4`
- `0x1800204d0`

## pseudocode

```c
__int64 __fastcall __crt_strtox::parse_integer<unsigned long,__crt_strtox::c_string_character_source<char>,1>(
        __crt_cached_ptd_host *a1,
        unsigned __int8 **a2,
        unsigned int a3,
        char a4)
{
  unsigned __int8 *v4; // r12
  unsigned int v5; // esi
  unsigned __int8 *v9; // rcx
  int v10; // edi
  unsigned int v11; // r14d
  char v12; // bp
  int v13; // eax
  unsigned __int8 *v14; // rcx
  char v15; // dl
  unsigned __int8 *v16; // r8
  int v17; // eax
  int v18; // eax
  unsigned int v19; // r9d
  unsigned int v20; // ecx
  unsigned __int8 *v21; // r8
  unsigned int v22; // edx
  bool v23; // cl
  bool v24; // cf
  bool v25; // zf
  unsigned __int8 *v26; // rax
  __int64 result; // rax
  unsigned __int8 *v28; // rax
  unsigned __int8 *v29; // rdx

  v4 = *a2;
  v5 = a3;
  if ( !*a2 )
  {
    *errno() = 22;
    invalid_parameter_noinfo();
    goto LABEL_6;
  }
  if ( a3 && a3 - 2 > 0x22 )
  {
    *((_BYTE *)a1 + 48) = 1;
    *((_DWORD *)a1 + 11) = 22;
    invalid_parameter_internal(0, 0, 0, 0, 0, a1);
LABEL_6:
    v9 = a2[1];
    if ( v9 )
      *(_QWORD *)v9 = *a2;
    return 0;
  }
  v10 = *v4;
  v11 = 0;
  *a2 = v4 + 1;
  if ( !*((_BYTE *)a1 + 40) )
    __crt_cached_ptd_host::update_locale_slow(a1);
  while ( ischartype_l(v10, 8, (const _locale_t)((char *)a1 + 24)) )
    v10 = *(*a2)++;
  v12 = a4 | 2;
  if ( (_BYTE)v10 != 45 )
    v12 = a4;
  if ( (((_BYTE)v10 - 43) & 0xFD) == 0 )
    LOBYTE(v10) = *(*a2)++;
  if ( (v5 & 0xFFFFFFEF) == 0 )
  {
    if ( (unsigned __int8)(v10 - 48) > 9u )
    {
      if ( (unsigned __int8)(v10 - 97) > 0x19u )
      {
        if ( (unsigned __int8)(v10 - 65) > 0x19u )
          goto LABEL_31;
        v13 = (char)v10 - 55;
      }
      else
      {
        v13 = (char)v10 - 87;
      }
    }
    else
    {
      v13 = (char)v10 - 48;
    }
    if ( !v13 )
    {
      v14 = *a2;
      v15 = **a2;
      v16 = *a2 + 1;
      *a2 = v16;
      if ( ((v15 - 88) & 0xDF) != 0 )
      {
        *a2 = v14;
        v17 = 8;
        if ( v5 )
          v17 = v5;
        v5 = v17;
        if ( v15 && *v14 != v15 )
        {
          *errno() = 22;
          invalid_parameter_noinfo();
        }
        goto LABEL_35;
      }
      LOBYTE(v10) = *v16;
      *a2 = v16 + 1;
      v18 = 16;
      goto LABEL_32;
    }
LABEL_31:
    v18 = 10;
LABEL_32:
    if ( v5 )
      v18 = v5;
    v5 = v18;
  }
LABEL_35:
  v19 = 0xFFFFFFFF / v5;
  while ( 1 )
  {
    if ( (unsigned __int8)(v10 - 48) > 9u )
    {
      if ( (unsigned __int8)(v10 - 97) > 0x19u )
        v20 = (unsigned __int8)(v10 - 65) > 0x19u ? -1 : (char)v10 - 55;
      else
        v20 = (char)v10 - 87;
    }
    else
    {
      v20 = (char)v10 - 48;
    }
    v21 = *a2;
    if ( v20 >= v5 )
      break;
    LOBYTE(v10) = *v21;
    v22 = v5 * v11 + v20;
    v23 = v22 < v5 * v11;
    v24 = v11 < v19;
    v25 = v11 == v19;
    v11 = v22;
    *a2 = v21 + 1;
    v12 |= (4 * (!v24 && !v25 || v23)) | 8;
  }
  *a2 = v21 - 1;
  if ( (_BYTE)v10 && *(v21 - 1) != (_BYTE)v10 )
  {
    *errno() = 22;
    invalid_parameter_noinfo();
  }
  if ( (v12 & 8) == 0 )
  {
    v26 = a2[1];
    *a2 = v4;
    if ( v26 )
      *(_QWORD *)v26 = v4;
    return 0;
  }
  result = 0x7FFFFFFF;
  if ( (v12 & 4) == 0 )
  {
    if ( (v12 & 1) == 0 )
    {
      if ( (v12 & 2) == 0 )
        goto LABEL_58;
      goto LABEL_64;
    }
    if ( (v12 & 2) != 0 )
    {
      if ( v11 > 0x80000000 )
        goto LABEL_56;
LABEL_64:
      v11 = -v11;
      goto LABEL_58;
    }
    if ( v11 <= 0x7FFFFFFF )
      goto LABEL_58;
  }
LABEL_56:
  *((_BYTE *)a1 + 48) = 1;
  *((_DWORD *)a1 + 11) = 34;
  if ( (v12 & 1) == 0 )
  {
    v11 = -1;
LABEL_58:
    v28 = a2[1];
    if ( v28 )
      *(_QWORD *)v28 = *a2;
    return v11;
  }
  v29 = a2[1];
  if ( (v12 & 2) != 0 )
  {
    if ( v29 )
      *(_QWORD *)v29 = *a2;
    return 0x80000000LL;
  }
  else if ( v29 )
  {
    *(_QWORD *)v29 = *a2;
  }
  return result;
}

```

## disassembly

```asm
0x18001e3a4  mov     [rsp+arg_0], rbx
0x18001e3a9  mov     [rsp+arg_8], rbp
0x18001e3ae  mov     [rsp+arg_10], rsi
0x18001e3b3  push    rdi
0x18001e3b4  push    r12
0x18001e3b6  push    r13
0x18001e3b8  push    r14
0x18001e3ba  push    r15
0x18001e3bc  sub     rsp, 30h
0x18001e3c0  mov     r12, [rdx]
0x18001e3c3  mov     esi, r8d
0x18001e3c6  movzx   r13d, r9b
0x18001e3ca  mov     rbx, rdx
0x18001e3cd  mov     r15, rcx
0x18001e3d0  test    r12, r12
0x18001e3d3  jnz     short loc_18001E3E7
0x18001e3d5  call    _errno
0x18001e3da  mov     dword ptr [rax], 16h
0x18001e3e0  call    _invalid_parameter_noinfo
0x18001e3e5  jmp     short loc_18001E419
0x18001e3e7  test    esi, esi
0x18001e3e9  jz      short loc_18001E431
0x18001e3eb  lea     eax, [r8-2]
0x18001e3ef  cmp     eax, 22h ; '"'
0x18001e3f2  jbe     short loc_18001E431
0x18001e3f4  mov     byte ptr [rcx+30h], 1
0x18001e3f8  xor     r9d, r9d; LineNo
0x18001e3fb  mov     dword ptr [rcx+2Ch], 16h
0x18001e402  xor     r8d, r8d; FileName
0x18001e405  mov     [rsp+58h+var_30], r15; __crt_cached_ptd_host *
0x18001e40a  xor     ecx, ecx; Expression
0x18001e40c  and     [rsp+58h+var_38], 0
0x18001e412  xor     edx, edx; FunctionName
0x18001e414  call    _invalid_parameter_internal
0x18001e419  mov     rcx, [rbx+8]; this
0x18001e41d  test    rcx, rcx
0x18001e420  jz      loc_18001E5D6
0x18001e426  mov     rax, [rbx]
0x18001e429  mov     [rcx], rax
0x18001e42c  jmp     loc_18001E5D6
0x18001e431  movzx   edi, byte ptr [r12]
0x18001e436  lea     rax, [r12+1]
0x18001e43b  xor     r14d, r14d
0x18001e43e  mov     [rdx], rax
0x18001e441  cmp     [rcx+28h], r14b
0x18001e445  jnz     short loc_18001E45A
0x18001e447  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18001e44c  jmp     short loc_18001E45A
0x18001e44e  mov     rax, [rbx]
0x18001e451  movzx   edi, byte ptr [rax]
0x18001e454  inc     rax
0x18001e457  mov     [rbx], rax
0x18001e45a  lea     r8, [r15+18h]; Locale
0x18001e45e  mov     edx, 8; Mask
0x18001e463  mov     ecx, edi; C
0x18001e465  call    _ischartype_l
0x18001e46a  test    eax, eax
0x18001e46c  jnz     short loc_18001E44E
0x18001e46e  mov     ebp, r13d
0x18001e471  lea     eax, [rdi-2Bh]
0x18001e474  or      ebp, 2
0x18001e477  cmp     dil, 2Dh ; '-'
0x18001e47b  cmovnz  ebp, r13d
0x18001e47f  test    al, 0FDh
0x18001e481  jnz     short loc_18001E48F
0x18001e483  mov     rax, [rbx]
0x18001e486  mov     dil, [rax]
0x18001e489  inc     rax
0x18001e48c  mov     [rbx], rax
0x18001e48f  test    esi, 0FFFFFFEFh
0x18001e495  jnz     loc_18001E526
0x18001e49b  lea     eax, [rdi-30h]
0x18001e49e  cmp     al, 9
0x18001e4a0  ja      short loc_18001E4AB
0x18001e4a2  movsx   eax, dil
0x18001e4a6  add     eax, 0FFFFFFD0h
0x18001e4a9  jmp     short loc_18001E4C9
0x18001e4ab  lea     eax, [rdi-61h]
0x18001e4ae  cmp     al, 19h
0x18001e4b0  ja      short loc_18001E4BB
0x18001e4b2  movsx   eax, dil
0x18001e4b6  add     eax, 0FFFFFFA9h
0x18001e4b9  jmp     short loc_18001E4C9
0x18001e4bb  lea     eax, [rdi-41h]
0x18001e4be  cmp     al, 19h
0x18001e4c0  ja      short loc_18001E51A
0x18001e4c2  movsx   eax, dil
0x18001e4c6  add     eax, 0FFFFFFC9h
0x18001e4c9  test    eax, eax
0x18001e4cb  jnz     short loc_18001E51A
0x18001e4cd  mov     rcx, [rbx]
0x18001e4d0  mov     dl, [rcx]
0x18001e4d2  lea     r8, [rcx+1]
0x18001e4d6  mov     [rbx], r8
0x18001e4d9  lea     eax, [rdx-58h]
0x18001e4dc  test    al, 0DFh
0x18001e4de  jz      short loc_18001E509
0x18001e4e0  test    esi, esi
0x18001e4e2  mov     [rbx], rcx
0x18001e4e5  mov     eax, 8
0x18001e4ea  cmovnz  eax, esi
0x18001e4ed  mov     esi, eax
0x18001e4ef  test    dl, dl
0x18001e4f1  jz      short loc_18001E526
0x18001e4f3  cmp     [rcx], dl
0x18001e4f5  jz      short loc_18001E526
0x18001e4f7  call    _errno
0x18001e4fc  mov     dword ptr [rax], 16h
0x18001e502  call    _invalid_parameter_noinfo
0x18001e507  jmp     short loc_18001E526
0x18001e509  mov     dil, [r8]
0x18001e50c  lea     rax, [r8+1]
0x18001e510  mov     [rbx], rax
0x18001e513  mov     eax, 10h
0x18001e518  jmp     short loc_18001E51F
0x18001e51a  mov     eax, 0Ah
0x18001e51f  test    esi, esi
0x18001e521  cmovnz  eax, esi
0x18001e524  mov     esi, eax
0x18001e526  or      r13d, 0FFFFFFFFh
0x18001e52a  xor     edx, edx
0x18001e52c  mov     eax, r13d
0x18001e52f  div     esi
0x18001e531  mov     r9d, eax
0x18001e534  lea     ecx, [rdi-30h]
0x18001e537  cmp     cl, 9
0x18001e53a  ja      short loc_18001E545
0x18001e53c  movsx   ecx, dil
0x18001e540  add     ecx, 0FFFFFFD0h
0x18001e543  jmp     short loc_18001E568
0x18001e545  lea     eax, [rdi-61h]
0x18001e548  cmp     al, 19h
0x18001e54a  ja      short loc_18001E555
0x18001e54c  movsx   ecx, dil
0x18001e550  add     ecx, 0FFFFFFA9h
0x18001e553  jmp     short loc_18001E568
0x18001e555  lea     eax, [rdi-41h]
0x18001e558  cmp     al, 19h
0x18001e55a  ja      short loc_18001E565
0x18001e55c  movsx   ecx, dil
0x18001e560  add     ecx, 0FFFFFFC9h
0x18001e563  jmp     short loc_18001E568
0x18001e565  mov     ecx, r13d
0x18001e568  mov     r8, [rbx]
0x18001e56b  cmp     ecx, esi
0x18001e56d  jnb     short loc_18001E5A0
0x18001e56f  mov     dil, [r8]
0x18001e572  mov     eax, r14d
0x18001e575  imul    eax, esi
0x18001e578  lea     edx, [rax+rcx]
0x18001e57b  xor     ecx, ecx
0x18001e57d  cmp     edx, eax
0x18001e57f  setb    cl
0x18001e582  xor     eax, eax
0x18001e584  cmp     r14d, r9d
0x18001e587  mov     r14d, edx
0x18001e58a  setnbe  al
0x18001e58d  or      ecx, eax
0x18001e58f  lea     rax, [r8+1]
0x18001e593  shl     ecx, 2
0x18001e596  or      ecx, 8
0x18001e599  mov     [rbx], rax
0x18001e59c  or      ebp, ecx
0x18001e59e  jmp     short loc_18001E534
0x18001e5a0  lea     rax, [r8-1]
0x18001e5a4  mov     [rbx], rax
0x18001e5a7  test    dil, dil
0x18001e5aa  jz      short loc_18001E5C1
0x18001e5ac  cmp     [rax], dil
0x18001e5af  jz      short loc_18001E5C1
0x18001e5b1  call    _errno
0x18001e5b6  mov     dword ptr [rax], 16h
0x18001e5bc  call    _invalid_parameter_noinfo
0x18001e5c1  test    bpl, 8
0x18001e5c5  jnz     short loc_18001E5DD
0x18001e5c7  mov     rax, [rbx+8]
0x18001e5cb  mov     [rbx], r12
0x18001e5ce  test    rax, rax
0x18001e5d1  jz      short loc_18001E5D6
0x18001e5d3  mov     [rax], r12
0x18001e5d6  xor     eax, eax
0x18001e5d8  jmp     loc_18001E660
0x18001e5dd  mov     eax, 7FFFFFFFh
0x18001e5e2  mov     r8d, 80000000h
0x18001e5e8  test    bpl, 4
0x18001e5ec  jnz     short loc_18001E5FF
0x18001e5ee  test    bpl, 1
0x18001e5f2  jz      short loc_18001E630
0x18001e5f4  test    bpl, 2
0x18001e5f8  jz      short loc_18001E629
0x18001e5fa  cmp     r14d, r8d
0x18001e5fd  jbe     short loc_18001E636
0x18001e5ff  mov     byte ptr [r15+30h], 1
0x18001e604  mov     dword ptr [r15+2Ch], 22h ; '"'
0x18001e60c  test    bpl, 1
0x18001e610  jnz     short loc_18001E63B
0x18001e612  mov     r14d, r13d
0x18001e615  mov     rax, [rbx+8]
0x18001e619  test    rax, rax
0x18001e61c  jz      short loc_18001E624
0x18001e61e  mov     rcx, [rbx]
0x18001e621  mov     [rax], rcx
0x18001e624  mov     eax, r14d
0x18001e627  jmp     short loc_18001E660
0x18001e629  cmp     r14d, eax
0x18001e62c  jbe     short loc_18001E615
0x18001e62e  jmp     short loc_18001E5FF
0x18001e630  test    bpl, 2
0x18001e634  jz      short loc_18001E615
0x18001e636  neg     r14d
0x18001e639  jmp     short loc_18001E615
0x18001e63b  mov     rdx, [rbx+8]
0x18001e63f  test    bpl, 2
0x18001e643  jz      short loc_18001E655
0x18001e645  test    rdx, rdx
0x18001e648  jz      short loc_18001E650
0x18001e64a  mov     rcx, [rbx]
0x18001e64d  mov     [rdx], rcx
0x18001e650  mov     eax, r8d
0x18001e653  jmp     short loc_18001E660
0x18001e655  test    rdx, rdx
0x18001e658  jz      short loc_18001E660
0x18001e65a  mov     rcx, [rbx]
0x18001e65d  mov     [rdx], rcx
0x18001e660  mov     rbx, [rsp+58h+arg_0]
0x18001e665  mov     rbp, [rsp+58h+arg_8]
0x18001e66a  mov     rsi, [rsp+58h+arg_10]
0x18001e66f  add     rsp, 30h
0x18001e673  pop     r15
0x18001e675  pop     r14
0x18001e677  pop     r13
0x18001e679  pop     r12
0x18001e67b  pop     rdi
0x18001e67c  retn
```
