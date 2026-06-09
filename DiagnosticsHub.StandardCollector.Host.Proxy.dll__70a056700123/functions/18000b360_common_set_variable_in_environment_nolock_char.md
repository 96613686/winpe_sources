# common_set_variable_in_environment_nolock_char_

- ea: `0x18000b360`
- end: `0x18000b6b8`
- name: `common_set_variable_in_environment_nolock_char_`
- size: `856`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18000be68`

## callees

- `0x1800052ac`
- `0x1800074f0`
- `0x180007788`
- `0x180007860`
- `0x1800078e0`
- `0x18000ae10`
- `0x18000b360`
- `0x18000ba1c`
- `0x18000be80`
- `0x1800138c0`
- `0x180013bf4`
- `0x1800239c0`

## pseudocode

```c
__int64 __fastcall common_set_variable_in_environment_nolock_char_(char *Block, int a2)
{
  unsigned int v2; // esi
  char *v5; // rdi
  char *v6; // rax
  char *v7; // r13
  _QWORD *v8; // r14
  char v9; // bp
  unsigned int v10; // ebp
  const char *v12; // rax
  signed __int64 v13; // r12
  const char **i; // rbx
  signed __int64 v15; // rbx
  void *v16; // rbx
  unsigned __int64 v17; // rbx
  size_t v18; // rdx
  _QWORD *v19; // r14
  __int64 v20; // r14
  char *v21; // rax
  char *v22; // rbx

  v2 = 0;
  if ( Block )
  {
    v5 = Block;
    v6 = strchr(Block, 61);
    v7 = v6;
    if ( !v6 || v6 == Block )
    {
      *errno() = 22;
      free_base(Block);
      return -1;
    }
    v8 = environ_table;
    v9 = v6[1];
    if ( environ_table == _dcrt_initial_narrow_environment )
    {
      v8 = (_QWORD *)copy_environment_char_(environ_table);
      environ_table = v8;
    }
    if ( !v8 )
    {
      if ( a2 && wenviron_table )
      {
        if ( !_dcrt_get_or_create_narrow_environment_nolock() )
        {
          *errno() = 22;
LABEL_12:
          v10 = -1;
LABEL_13:
          free_base(Block);
          return v10;
        }
        v8 = environ_table;
        if ( environ_table == _dcrt_initial_narrow_environment )
        {
          v8 = (_QWORD *)copy_environment_char_(environ_table);
          environ_table = v8;
        }
      }
      else
      {
        if ( !v9 )
          goto LABEL_39;
        environ_table = calloc_base(1u, 8u);
        free_base(0);
        v8 = environ_table;
        if ( !environ_table )
          goto LABEL_12;
        if ( !wenviron_table )
        {
          wenviron_table = calloc_base(1u, 8u);
          free_base(0);
          if ( !wenviron_table )
            goto LABEL_12;
          v8 = environ_table;
        }
      }
      if ( !v8 )
        goto LABEL_12;
    }
    v12 = (const char *)*v8;
    v13 = v7 - Block;
    for ( i = (const char **)v8; ; v12 = *i )
    {
      if ( !v12 )
      {
        v15 = -(i - (const char **)v8);
        goto LABEL_29;
      }
      if ( !strnicoll(Block, v12, v7 - Block) && ((*i)[v13] == 61 || !(*i)[v13]) )
        break;
      ++i;
    }
    v15 = i - (const char **)v8;
LABEL_29:
    if ( v15 >= 0 && *v8 )
    {
      free_base((void *)v8[v15]);
      if ( !v9 )
      {
        while ( v8[v15] )
        {
          v8[v15] = v8[v15 + 1];
          ++v15;
        }
        v16 = recalloc_base(v8, v15, 8u);
        free_base(0);
        if ( v16 )
          environ_table = v16;
LABEL_45:
        if ( a2 )
        {
          v20 = -1;
          do
            ++v20;
          while ( Block[v20] );
          v21 = (char *)calloc_base(v20 + 2, 1u);
          v22 = v21;
          if ( !v21 )
          {
            free_base(0);
LABEL_53:
            free_base(v5);
            return v2;
          }
          if ( strcpy_s(v21, v20 + 2, Block) )
            invoke_watson(0, 0, 0, 0, 0);
          v7[v22 - Block] = 0;
          if ( !(unsigned int)_acrt_SetEnvironmentVariableA(
                                v22,
                                (unsigned __int64)&v7[v22 - Block + 1] & -(__int64)(v9 != 0)) )
          {
            *errno() = 42;
            free_base(v22);
            v2 = -1;
            goto LABEL_53;
          }
          free_base(v22);
        }
        free_base(v5);
        return 0;
      }
      v8[v15] = Block;
LABEL_44:
      v5 = 0;
      goto LABEL_45;
    }
    if ( v9 )
    {
      v17 = -v15;
      v18 = v17 + 2;
      if ( v17 + 2 < v17 )
        goto LABEL_12;
      if ( v18 >= 0x1FFFFFFFFFFFFFFFLL )
        goto LABEL_12;
      v19 = recalloc_base(v8, v18, 8u);
      free_base(0);
      if ( !v19 )
        goto LABEL_12;
      v19[v17] = Block;
      v19[v17 + 1] = 0;
      environ_table = v19;
      goto LABEL_44;
    }
LABEL_39:
    v10 = 0;
    goto LABEL_13;
  }
  *errno() = 22;
  return -1;
}

```

## disassembly

```asm
0x18000b360  mov     [rsp+arg_10], rbx
0x18000b365  mov     [rsp+arg_8], edx
0x18000b369  push    rbp
0x18000b36a  push    rsi
0x18000b36b  push    rdi
0x18000b36c  push    r12
0x18000b36e  push    r13
0x18000b370  push    r14
0x18000b372  push    r15
0x18000b374  sub     rsp, 30h
0x18000b378  xor     esi, esi
0x18000b37a  mov     ebx, edx
0x18000b37c  mov     r15, rcx
0x18000b37f  test    rcx, rcx
0x18000b382  jnz     short loc_18000B394
0x18000b384  call    _errno
0x18000b389  mov     dword ptr [rax], 16h
0x18000b38f  jmp     loc_18000B687
0x18000b394  mov     edx, 3Dh ; '='; Val
0x18000b399  mov     rdi, r15
0x18000b39c  call    strchr
0x18000b3a1  mov     r13, rax
0x18000b3a4  test    rax, rax
0x18000b3a7  jz      loc_18000B674
0x18000b3ad  cmp     rax, r15
0x18000b3b0  jz      loc_18000B674
0x18000b3b6  mov     r14, cs:_environ_table
0x18000b3bd  cmp     r14, cs:__dcrt_initial_narrow_environment
0x18000b3c4  mov     bpl, [rax+1]
0x18000b3c8  mov     [rsp+68h+arg_0], bpl
0x18000b3cd  jnz     short loc_18000B3E1
0x18000b3cf  mov     rcx, r14
0x18000b3d2  call    copy_environment_char_
0x18000b3d7  mov     r14, rax
0x18000b3da  mov     cs:_environ_table, rax
0x18000b3e1  mov     r12d, 1
0x18000b3e7  test    r14, r14
0x18000b3ea  jnz     loc_18000B4BA
0x18000b3f0  test    ebx, ebx
0x18000b3f2  jz      short loc_18000B449
0x18000b3f4  cmp     cs:_wenviron_table, rsi
0x18000b3fb  jz      short loc_18000B449
0x18000b3fd  call    __dcrt_get_or_create_narrow_environment_nolock
0x18000b402  test    rax, rax
0x18000b405  jnz     short loc_18000B425
0x18000b407  call    _errno
0x18000b40c  mov     dword ptr [rax], 16h
0x18000b412  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000b416  mov     rcx, r15; Block
0x18000b419  call    _free_base
0x18000b41e  mov     eax, ebp
0x18000b420  jmp     loc_18000B68B
0x18000b425  mov     r14, cs:_environ_table
0x18000b42c  cmp     r14, cs:__dcrt_initial_narrow_environment
0x18000b433  jnz     short loc_18000B4B1
0x18000b435  mov     rcx, r14
0x18000b438  call    copy_environment_char_
0x18000b43d  mov     r14, rax
0x18000b440  mov     cs:_environ_table, rax
0x18000b447  jmp     short loc_18000B4B1
0x18000b449  test    bpl, bpl
0x18000b44c  jz      loc_18000B56A
0x18000b452  mov     edx, 8; Size
0x18000b457  mov     rcx, r12; Count
0x18000b45a  call    _calloc_base
0x18000b45f  xor     ecx, ecx; Block
0x18000b461  mov     cs:_environ_table, rax
0x18000b468  call    _free_base
0x18000b46d  mov     r14, cs:_environ_table
0x18000b474  test    r14, r14
0x18000b477  jz      short loc_18000B412
0x18000b479  cmp     cs:_wenviron_table, rsi
0x18000b480  jnz     short loc_18000B4B1
0x18000b482  mov     edx, 8; Size
0x18000b487  mov     rcx, r12; Count
0x18000b48a  call    _calloc_base
0x18000b48f  xor     ecx, ecx; Block
0x18000b491  mov     cs:_wenviron_table, rax
0x18000b498  call    _free_base
0x18000b49d  cmp     cs:_wenviron_table, rsi
0x18000b4a4  jz      loc_18000B412
0x18000b4aa  mov     r14, cs:_environ_table
0x18000b4b1  test    r14, r14
0x18000b4b4  jz      loc_18000B412
0x18000b4ba  mov     rax, [r14]
0x18000b4bd  mov     r12, r13
0x18000b4c0  sub     r12, r15
0x18000b4c3  mov     rbx, r14
0x18000b4c6  jmp     short loc_18000B4F1
0x18000b4c8  mov     r8, r12; MaxCount
0x18000b4cb  mov     rdx, rax; String2
0x18000b4ce  mov     rcx, r15; String1
0x18000b4d1  call    _strnicoll
0x18000b4d6  test    eax, eax
0x18000b4d8  jnz     short loc_18000B4EA
0x18000b4da  mov     rax, [rbx]
0x18000b4dd  cmp     byte ptr [r12+rax], 3Dh ; '='
0x18000b4e2  jz      short loc_18000B521
0x18000b4e4  cmp     [r12+rax], sil
0x18000b4e8  jz      short loc_18000B521
0x18000b4ea  add     rbx, 8
0x18000b4ee  mov     rax, [rbx]
0x18000b4f1  test    rax, rax
0x18000b4f4  jnz     short loc_18000B4C8
0x18000b4f6  sub     rbx, r14
0x18000b4f9  sar     rbx, 3
0x18000b4fd  neg     rbx
0x18000b500  test    rbx, rbx
0x18000b503  js      short loc_18000B565
0x18000b505  cmp     [r14], rsi
0x18000b508  jz      short loc_18000B565
0x18000b50a  mov     rcx, [r14+rbx*8]; Block
0x18000b50e  call    _free_base
0x18000b513  test    bpl, bpl
0x18000b516  jz      short loc_18000B536
0x18000b518  mov     [r14+rbx*8], r15
0x18000b51c  jmp     loc_18000B5C5
0x18000b521  sub     rbx, r14
0x18000b524  sar     rbx, 3
0x18000b528  jmp     short loc_18000B500
0x18000b52a  mov     rax, [r14+rbx*8+8]
0x18000b52f  mov     [r14+rbx*8], rax
0x18000b533  inc     rbx
0x18000b536  cmp     [r14+rbx*8], rsi
0x18000b53a  jnz     short loc_18000B52A
0x18000b53c  mov     r8d, 8; Size
0x18000b542  mov     rdx, rbx; Count
0x18000b545  mov     rcx, r14; Block
0x18000b548  call    _recalloc_base
0x18000b54d  xor     ecx, ecx; Block
0x18000b54f  mov     rbx, rax
0x18000b552  call    _free_base
0x18000b557  test    rbx, rbx
0x18000b55a  jz      short loc_18000B5C8
0x18000b55c  mov     cs:_environ_table, rbx
0x18000b563  jmp     short loc_18000B5C8
0x18000b565  test    bpl, bpl
0x18000b568  jnz     short loc_18000B571
0x18000b56a  mov     ebp, esi
0x18000b56c  jmp     loc_18000B416
0x18000b571  neg     rbx
0x18000b574  lea     rdx, [rbx+2]; Count
0x18000b578  cmp     rdx, rbx
0x18000b57b  jb      loc_18000B412
0x18000b581  mov     rax, 1FFFFFFFFFFFFFFFh
0x18000b58b  cmp     rdx, rax
0x18000b58e  jnb     loc_18000B412
0x18000b594  mov     r8d, 8; Size
0x18000b59a  mov     rcx, r14; Block
0x18000b59d  call    _recalloc_base
0x18000b5a2  xor     ecx, ecx; Block
0x18000b5a4  mov     r14, rax
0x18000b5a7  call    _free_base
0x18000b5ac  test    r14, r14
0x18000b5af  jz      loc_18000B412
0x18000b5b5  mov     [r14+rbx*8], r15
0x18000b5b9  mov     [r14+rbx*8+8], rsi
0x18000b5be  mov     cs:_environ_table, r14
0x18000b5c5  mov     rdi, rsi
0x18000b5c8  cmp     [rsp+68h+arg_8], esi
0x18000b5cc  jz      loc_18000B668
0x18000b5d2  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000b5d6  mov     r14, rbp
0x18000b5d9  inc     r14
0x18000b5dc  cmp     [r15+r14], sil
0x18000b5e0  jnz     short loc_18000B5D9
0x18000b5e2  mov     edx, 1; Size
0x18000b5e7  lea     rcx, [r14+2]; Count
0x18000b5eb  call    _calloc_base
0x18000b5f0  mov     rbx, rax
0x18000b5f3  test    rax, rax
0x18000b5f6  jnz     short loc_18000B601
0x18000b5f8  xor     ecx, ecx; Block
0x18000b5fa  call    _free_base
0x18000b5ff  jmp     short loc_18000B654
0x18000b601  mov     r8, r15; Source
0x18000b604  lea     rdx, [r14+2]; SizeInBytes
0x18000b608  mov     rcx, rbx; Destination
0x18000b60b  call    strcpy_s
0x18000b610  test    eax, eax
0x18000b612  jnz     loc_18000B6A3
0x18000b618  mov     rax, rbx
0x18000b61b  lea     rcx, [r13+1]
0x18000b61f  sub     rax, r15
0x18000b622  add     rcx, rax
0x18000b625  neg     [rsp+68h+arg_0]
0x18000b629  sbb     rdx, rdx
0x18000b62c  mov     [rax+r13], sil
0x18000b630  and     rdx, rcx
0x18000b633  mov     rcx, rbx
0x18000b636  call    __acrt_SetEnvironmentVariableA
0x18000b63b  test    eax, eax
0x18000b63d  jnz     short loc_18000B660
0x18000b63f  call    _errno
0x18000b644  mov     rcx, rbx; Block
0x18000b647  mov     dword ptr [rax], 2Ah ; '*'
0x18000b64d  call    _free_base
0x18000b652  mov     esi, ebp
0x18000b654  mov     rcx, rdi; Block
0x18000b657  call    _free_base
0x18000b65c  mov     eax, esi
0x18000b65e  jmp     short loc_18000B68B
0x18000b660  mov     rcx, rbx; Block
0x18000b663  call    _free_base
0x18000b668  mov     rcx, rdi; Block
0x18000b66b  call    _free_base
0x18000b670  xor     eax, eax
0x18000b672  jmp     short loc_18000B68B
0x18000b674  call    _errno
0x18000b679  mov     rcx, r15; Block
0x18000b67c  mov     dword ptr [rax], 16h
0x18000b682  call    _free_base
0x18000b687  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b68b  mov     rbx, [rsp+68h+arg_10]
0x18000b693  add     rsp, 30h
0x18000b697  pop     r15
0x18000b699  pop     r14
0x18000b69b  pop     r13
0x18000b69d  pop     r12
0x18000b69f  pop     rdi
0x18000b6a0  pop     rsi
0x18000b6a1  pop     rbp
0x18000b6a2  retn
0x18000b6a3  xor     r9d, r9d; LineNo
0x18000b6a6  mov     [rsp+68h+Reserved], rsi; Reserved
0x18000b6ab  xor     r8d, r8d; FileName
0x18000b6ae  xor     edx, edx; FunctionName
0x18000b6b0  xor     ecx, ecx; Expression
0x18000b6b2  call    _invoke_watson
```
