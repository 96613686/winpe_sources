# sqlite3_complete

- ea: `0x1800a7330`
- end: `0x1800a75d0`
- name: `sqlite3_complete`
- size: `672`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800a75e0`

## callees

- `0x1800a7330`
- `0x1800ada30`

## string_xrefs

- `0x1800a7487`: `temporary`
- `0x1800a74d8`: `create`

## pseudocode

```c
_BOOL8 __fastcall sqlite3_complete(unsigned __int8 *a1)
{
  signed __int8 v1; // r8
  unsigned __int8 v2; // si
  unsigned __int8 *v3; // rbx
  bool v4; // zf
  int i; // edi
  __int64 v6; // rdx
  __int64 v7; // r8
  const char *v8; // rdx
  int v9; // eax
  char v10; // al
  char v11; // al
  char *v13; // rbx
  char v14; // cl
  char *v15; // rax
  unsigned __int8 v16; // al

  v1 = *a1;
  v2 = 0;
  v3 = a1;
  if ( *a1 )
  {
    while ( 1 )
    {
      if ( v1 > 39 )
      {
        switch ( v1 )
        {
          case '-':
            if ( v3[1] == 45 )
            {
              v16 = *v3;
              if ( !*v3 )
                return v2 == 1;
              do
              {
                if ( v16 == 10 )
                  break;
                v16 = *++v3;
              }
              while ( *v3 );
              if ( !*v3 )
                return v2 == 1;
LABEL_67:
              v6 = 1;
              goto LABEL_68;
            }
            goto LABEL_55;
          case '/':
            if ( v3[1] == 42 )
            {
              v13 = (char *)(v3 + 2);
              v14 = *v13;
              if ( !*v13 )
                return 0;
              do
              {
                v15 = v13 + 1;
                if ( v14 == 42 && *v15 == 47 )
                  break;
                v14 = *v15;
                ++v13;
              }
              while ( *v15 );
              if ( !*v13 )
                return 0;
              v3 = (unsigned __int8 *)(v13 + 1);
              goto LABEL_67;
            }
            goto LABEL_55;
          case ';':
            v6 = 0;
            goto LABEL_68;
          case '[':
            v11 = *++v3;
            if ( !*v3 )
              return 0;
            do
            {
              if ( v11 == 93 )
                break;
              v11 = *++v3;
            }
            while ( *v3 );
            goto LABEL_51;
        }
        v4 = v1 == 96;
      }
      else
      {
        if ( v1 == 39 )
          goto LABEL_44;
        if ( v1 == 9 || v1 == 10 || v1 == 12 || v1 == 13 || v1 == 32 )
          goto LABEL_67;
        v4 = v1 == 34;
      }
      if ( v4 )
      {
LABEL_44:
        v10 = *++v3;
        if ( !*v3 )
          return 0;
        do
        {
          if ( v10 == v1 )
            break;
          v10 = *++v3;
        }
        while ( *v3 );
LABEL_51:
        if ( !*v3 )
          return 0;
LABEL_55:
        v6 = 2;
        goto LABEL_68;
      }
      if ( (*((_BYTE *)&qword_1800FB500 + *v3) & 0x46) == 0 )
        goto LABEL_55;
      for ( i = 1; (*((_BYTE *)&qword_1800FB500 + v3[i]) & 0x46) != 0; ++i )
        ;
      if ( v1 == 67 )
      {
LABEL_40:
        if ( i == 6 )
        {
          v9 = sqlite3_strnicmp(v3, "create", 6);
          v6 = 4;
          if ( !v9 )
            goto LABEL_43;
        }
LABEL_42:
        v6 = 2;
        goto LABEL_43;
      }
      if ( v1 != 69 )
      {
        if ( v1 == 84 )
          goto LABEL_25;
        if ( v1 == 99 )
          goto LABEL_40;
        if ( v1 != 101 )
          break;
      }
      if ( i == 3 )
      {
        if ( (unsigned int)sqlite3_strnicmp(v3, "end", 3) )
          goto LABEL_42;
        v6 = 7;
      }
      else
      {
        if ( i != 7 || (unsigned int)sqlite3_strnicmp(v3, "explain", 7) )
          goto LABEL_42;
        v6 = 3;
      }
LABEL_43:
      v3 += i - 1;
LABEL_68:
      v1 = *++v3;
      v2 = *((_BYTE *)&qword_1800FEC20[v2] + v6);
      if ( !*v3 )
        return v2 == 1;
    }
    if ( v1 != 116 )
      goto LABEL_42;
LABEL_25:
    if ( i == 7 )
    {
      if ( (unsigned int)sqlite3_strnicmp(v3, "trigger", 7) )
        goto LABEL_42;
      v6 = 6;
    }
    else
    {
      if ( i == 4 )
      {
        v7 = 4;
        v8 = "temp";
      }
      else
      {
        if ( i != 9 )
          goto LABEL_42;
        v7 = 9;
        v8 = "temporary";
      }
      if ( (unsigned int)sqlite3_strnicmp(v3, v8, v7) )
        goto LABEL_42;
      v6 = 5;
    }
    goto LABEL_43;
  }
  return v2 == 1;
}

```

## disassembly

```asm
0x1800a7330  push    rbx
0x1800a7332  push    rsi
0x1800a7333  push    rdi
0x1800a7334  push    r14
0x1800a7336  push    r15
0x1800a7338  sub     rsp, 20h
0x1800a733c  mov     r8b, [rcx]
0x1800a733f  xor     sil, sil
0x1800a7342  mov     rbx, rcx
0x1800a7345  mov     r14d, 1
0x1800a734b  test    r8b, r8b
0x1800a734e  jz      loc_1800A75BC
0x1800a7354  lea     r15d, [r14+1]
0x1800a7358  lea     r9, cs:180000000h
0x1800a735f  movsx   edx, r8b
0x1800a7363  cmp     edx, 27h ; '''
0x1800a7366  jg      short loc_1800A73A2
0x1800a7368  jz      loc_1800A7506
0x1800a736e  mov     ecx, edx
0x1800a7370  sub     ecx, 9
0x1800a7373  jz      loc_1800A759A
0x1800a7379  sub     ecx, r14d
0x1800a737c  jz      loc_1800A759A
0x1800a7382  sub     ecx, r15d
0x1800a7385  jz      loc_1800A759A
0x1800a738b  sub     ecx, r14d
0x1800a738e  jz      loc_1800A759A
0x1800a7394  sub     ecx, 13h
0x1800a7397  jz      loc_1800A759A
0x1800a739d  cmp     ecx, r15d
0x1800a73a0  jmp     short loc_1800A73C9
0x1800a73a2  cmp     edx, 2Dh ; '-'
0x1800a73a5  jz      loc_1800A757C
0x1800a73ab  cmp     edx, 2Fh ; '/'
0x1800a73ae  jz      loc_1800A7547
0x1800a73b4  cmp     edx, 3Bh ; ';'
0x1800a73b7  jz      loc_1800A7543
0x1800a73bd  cmp     edx, 5Bh ; '['
0x1800a73c0  jz      loc_1800A7521
0x1800a73c6  cmp     edx, 60h ; '`'
0x1800a73c9  jz      loc_1800A7506
0x1800a73cf  movzx   eax, byte ptr [rbx]
0x1800a73d2  test    byte ptr [rax+r9+0FB500h], 46h
0x1800a73db  jz      loc_1800A754D
0x1800a73e1  movzx   eax, byte ptr [rbx+1]
0x1800a73e5  mov     edi, r14d
0x1800a73e8  test    byte ptr [rax+r9+0FB500h], 46h
0x1800a73f1  jz      short loc_1800A7408
0x1800a73f3  add     edi, r14d
0x1800a73f6  movsxd  rax, edi
0x1800a73f9  movzx   ecx, byte ptr [rax+rbx]
0x1800a73fd  test    byte ptr [rcx+r9+0FB500h], 46h
0x1800a7406  jnz     short loc_1800A73F3
0x1800a7408  cmp     r8b, 43h ; 'C'
0x1800a740c  jz      loc_1800A74D0
0x1800a7412  cmp     r8b, 45h ; 'E'
0x1800a7416  jz      short loc_1800A7490
0x1800a7418  cmp     r8b, 54h ; 'T'
0x1800a741c  jz      short loc_1800A7438
0x1800a741e  cmp     r8b, 63h ; 'c'
0x1800a7422  jz      loc_1800A74D0
0x1800a7428  cmp     r8b, 65h ; 'e'
0x1800a742c  jz      short loc_1800A7490
0x1800a742e  cmp     r8b, 74h ; 't'
0x1800a7432  jnz     loc_1800A74EE
0x1800a7438  cmp     edi, 7
0x1800a743b  jnz     short loc_1800A745F
0x1800a743d  mov     r8d, edi
0x1800a7440  lea     rdx, aTrigger; "trigger"
0x1800a7447  mov     rcx, rbx
0x1800a744a  call    sqlite3_strnicmp
0x1800a744f  test    eax, eax
0x1800a7451  jnz     loc_1800A74EE
0x1800a7457  lea     edx, [rdi-1]
0x1800a745a  jmp     loc_1800A74F1
0x1800a745f  cmp     edi, 4
0x1800a7462  jnz     short loc_1800A747F
0x1800a7464  mov     r8d, edi
0x1800a7467  lea     rdx, aTemp; "temp"
0x1800a746e  mov     rcx, rbx
0x1800a7471  call    sqlite3_strnicmp
0x1800a7476  test    eax, eax
0x1800a7478  jnz     short loc_1800A74EE
0x1800a747a  lea     edx, [rax+5]
0x1800a747d  jmp     short loc_1800A74F1
0x1800a747f  cmp     edi, 9
0x1800a7482  jnz     short loc_1800A74EE
0x1800a7484  mov     r8d, edi
0x1800a7487  lea     rdx, aTemporary; "temporary"
0x1800a748e  jmp     short loc_1800A746E
0x1800a7490  cmp     edi, 3
0x1800a7493  jnz     short loc_1800A74B0
0x1800a7495  mov     r8d, edi
0x1800a7498  lea     rdx, aEnd; "end"
0x1800a749f  mov     rcx, rbx
0x1800a74a2  call    sqlite3_strnicmp
0x1800a74a7  test    eax, eax
0x1800a74a9  jnz     short loc_1800A74EE
0x1800a74ab  lea     edx, [rdi+4]
0x1800a74ae  jmp     short loc_1800A74F1
0x1800a74b0  cmp     edi, 7
0x1800a74b3  jnz     short loc_1800A74EE
0x1800a74b5  mov     r8d, edi
0x1800a74b8  lea     rdx, aExplain_0; "explain"
0x1800a74bf  mov     rcx, rbx
0x1800a74c2  call    sqlite3_strnicmp
0x1800a74c7  test    eax, eax
0x1800a74c9  jnz     short loc_1800A74EE
0x1800a74cb  lea     edx, [rdi-4]
0x1800a74ce  jmp     short loc_1800A74F1
0x1800a74d0  cmp     edi, 6
0x1800a74d3  jnz     short loc_1800A74EE
0x1800a74d5  mov     r8d, edi
0x1800a74d8  lea     rdx, aCreate_0; "create"
0x1800a74df  mov     rcx, rbx
0x1800a74e2  call    sqlite3_strnicmp
0x1800a74e7  lea     edx, [rdi-2]
0x1800a74ea  test    eax, eax
0x1800a74ec  jz      short loc_1800A74F1
0x1800a74ee  mov     rdx, r15
0x1800a74f1  lea     eax, [rdi-1]
0x1800a74f4  movsxd  rcx, eax
0x1800a74f7  lea     r9, cs:180000000h
0x1800a74fe  add     rbx, rcx
0x1800a7501  jmp     loc_1800A759D
0x1800a7506  add     rbx, r14
0x1800a7509  mov     al, [rbx]
0x1800a750b  test    al, al
0x1800a750d  jz      short loc_1800A753C
0x1800a750f  movsx   eax, al
0x1800a7512  cmp     eax, edx
0x1800a7514  jz      short loc_1800A7537
0x1800a7516  add     rbx, r14
0x1800a7519  mov     al, [rbx]
0x1800a751b  test    al, al
0x1800a751d  jnz     short loc_1800A750F
0x1800a751f  jmp     short loc_1800A7537
0x1800a7521  add     rbx, r14
0x1800a7524  mov     al, [rbx]
0x1800a7526  test    al, al
0x1800a7528  jz      short loc_1800A753C
0x1800a752a  cmp     al, 5Dh ; ']'
0x1800a752c  jz      short loc_1800A7537
0x1800a752e  add     rbx, r14
0x1800a7531  mov     al, [rbx]
0x1800a7533  test    al, al
0x1800a7535  jnz     short loc_1800A752A
0x1800a7537  cmp     byte ptr [rbx], 0
0x1800a753a  jnz     short loc_1800A754D
0x1800a753c  xor     eax, eax
0x1800a753e  jmp     loc_1800A75C4
0x1800a7543  xor     edx, edx
0x1800a7545  jmp     short loc_1800A759D
0x1800a7547  cmp     byte ptr [rbx+1], 2Ah ; '*'
0x1800a754b  jz      short loc_1800A7552
0x1800a754d  mov     rdx, r15
0x1800a7550  jmp     short loc_1800A759D
0x1800a7552  add     rbx, r15
0x1800a7555  mov     cl, [rbx]
0x1800a7557  test    cl, cl
0x1800a7559  jz      short loc_1800A753C
0x1800a755b  lea     rax, [rbx+1]
0x1800a755f  cmp     cl, 2Ah ; '*'
0x1800a7562  jnz     short loc_1800A7569
0x1800a7564  cmp     byte ptr [rax], 2Fh ; '/'
0x1800a7567  jz      short loc_1800A7572
0x1800a7569  mov     cl, [rax]
0x1800a756b  mov     rbx, rax
0x1800a756e  test    cl, cl
0x1800a7570  jnz     short loc_1800A755B
0x1800a7572  cmp     byte ptr [rbx], 0
0x1800a7575  jz      short loc_1800A753C
0x1800a7577  add     rbx, r14
0x1800a757a  jmp     short loc_1800A759A
0x1800a757c  cmp     byte ptr [rbx+1], 2Dh ; '-'
0x1800a7580  jnz     short loc_1800A754D
0x1800a7582  mov     al, [rbx]
0x1800a7584  test    al, al
0x1800a7586  jz      short loc_1800A75BC
0x1800a7588  cmp     al, 0Ah
0x1800a758a  jz      short loc_1800A7595
0x1800a758c  add     rbx, r14
0x1800a758f  mov     al, [rbx]
0x1800a7591  test    al, al
0x1800a7593  jnz     short loc_1800A7588
0x1800a7595  cmp     byte ptr [rbx], 0
0x1800a7598  jz      short loc_1800A75BC
0x1800a759a  mov     rdx, r14
0x1800a759d  add     rbx, r14
0x1800a75a0  movzx   eax, sil
0x1800a75a4  mov     r8b, [rbx]
0x1800a75a7  lea     rcx, [rdx+rax*8]
0x1800a75ab  mov     sil, [rcx+r9+0FEC20h]
0x1800a75b3  test    r8b, r8b
0x1800a75b6  jnz     loc_1800A735F
0x1800a75bc  xor     eax, eax
0x1800a75be  cmp     sil, r14b
0x1800a75c1  setz    al
0x1800a75c4  add     rsp, 20h
0x1800a75c8  pop     r15
0x1800a75ca  pop     r14
0x1800a75cc  pop     rdi
0x1800a75cd  pop     rsi
0x1800a75ce  pop     rbx
0x1800a75cf  retn
```
