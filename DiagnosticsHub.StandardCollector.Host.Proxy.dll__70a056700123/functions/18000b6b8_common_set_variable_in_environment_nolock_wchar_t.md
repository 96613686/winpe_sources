# common_set_variable_in_environment_nolock_wchar_t_

- ea: `0x18000b6b8`
- end: `0x18000ba1c`
- name: `common_set_variable_in_environment_nolock_wchar_t_`
- size: `868`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000be70`

## callees

- `0x1800052e8`
- `0x1800074f0`
- `0x180007788`
- `0x180007860`
- `0x1800078e0`
- `0x18000ad00`
- `0x18000b6b8`
- `0x18000bb04`
- `0x18000be80`
- `0x1800135a0`
- `0x180023a40`

## import_xrefs

- `KERNEL32!SetEnvironmentVariableW` at `0x18000b994`
- `KERNEL32!SetEnvironmentVariableW` at `0x18000b994`

## pseudocode

```c
__int64 __fastcall common_set_variable_in_environment_nolock_wchar_t_(wchar_t *Block, int a2)
{
  unsigned int v2; // esi
  wchar_t *v5; // rdi
  wchar_t *v6; // rax
  wchar_t *v7; // r13
  _QWORD *v8; // r14
  wchar_t v9; // r12
  unsigned int v10; // ebp
  const wchar_t *v12; // rax
  size_t v13; // r13
  const wchar_t **i; // rbx
  signed __int64 v15; // rbx
  void *v16; // rbx
  unsigned __int64 v17; // rbx
  size_t v18; // rdx
  _QWORD *v19; // r14
  __int64 v20; // r14
  size_t v21; // r14
  wchar_t *v22; // rax
  wchar_t *v23; // rbx

  v2 = 0;
  if ( Block )
  {
    v5 = Block;
    v6 = wcschr(Block, 0x3Du);
    v7 = v6;
    if ( !v6 || v6 == Block )
    {
      *errno() = 22;
      free_base(Block);
      return -1;
    }
    v8 = wenviron_table;
    v9 = v6[1];
    if ( wenviron_table == _dcrt_initial_wide_environment )
    {
      v8 = (_QWORD *)copy_environment_wchar_t_(wenviron_table);
      wenviron_table = v8;
    }
    if ( !v8 )
    {
      if ( a2 && environ_table )
      {
        if ( !_dcrt_get_or_create_wide_environment_nolock() )
        {
          *errno() = 22;
LABEL_12:
          v10 = -1;
LABEL_13:
          free_base(Block);
          return v10;
        }
        v8 = wenviron_table;
        if ( wenviron_table == _dcrt_initial_wide_environment )
        {
          v8 = (_QWORD *)copy_environment_wchar_t_(wenviron_table);
          wenviron_table = v8;
        }
        goto LABEL_21;
      }
      if ( !v9 )
        goto LABEL_39;
      if ( environ_table )
        goto LABEL_20;
      environ_table = calloc_base(1u, 8u);
      free_base(0);
      if ( !environ_table )
        goto LABEL_12;
      v8 = wenviron_table;
      if ( !wenviron_table )
      {
LABEL_20:
        wenviron_table = calloc_base(1u, 8u);
        free_base(0);
        v8 = wenviron_table;
        if ( !wenviron_table )
          goto LABEL_12;
LABEL_21:
        if ( !v8 )
          goto LABEL_12;
      }
    }
    v12 = (const wchar_t *)*v8;
    v13 = v7 - Block;
    for ( i = (const wchar_t **)v8; ; v12 = *i )
    {
      if ( !v12 )
      {
        v15 = -(i - (const wchar_t **)v8);
        goto LABEL_29;
      }
      if ( !wcsnicoll(Block, v12, v13) && ((*i)[v13] == 61 || !(*i)[v13]) )
        break;
      ++i;
    }
    v15 = i - (const wchar_t **)v8;
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
          wenviron_table = v16;
LABEL_45:
        if ( a2 )
        {
          v20 = -1;
          do
            ++v20;
          while ( Block[v20] );
          v21 = v20 + 2;
          v22 = (wchar_t *)calloc_base(v21, 2u);
          v23 = v22;
          if ( !v22 )
          {
            free_base(0);
LABEL_53:
            free_base(v5);
            return v2;
          }
          if ( wcscpy_s(v22, v21, Block) )
            invoke_watson(0, 0, 0, 0, 0);
          v23[v13] = 0;
          if ( !SetEnvironmentVariableW(v23, (LPCWSTR)((unsigned __int64)&v23[v13 + 1] & -(__int64)(v9 != 0))) )
          {
            *errno() = 42;
            free_base(v23);
            v2 = -1;
            goto LABEL_53;
          }
          free_base(v23);
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
      wenviron_table = v19;
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
0x18000b6b8  mov     [rsp+arg_0], rbx
0x18000b6bd  mov     [rsp+arg_8], rbp
0x18000b6c2  mov     [rsp+arg_10], rsi
0x18000b6c7  push    rdi
0x18000b6c8  push    r12
0x18000b6ca  push    r13
0x18000b6cc  push    r14
0x18000b6ce  push    r15
0x18000b6d0  sub     rsp, 30h
0x18000b6d4  xor     esi, esi
0x18000b6d6  mov     ebp, edx
0x18000b6d8  mov     r15, rcx
0x18000b6db  test    rcx, rcx
0x18000b6de  jnz     short loc_18000B6F0
0x18000b6e0  call    _errno
0x18000b6e5  mov     dword ptr [rax], 16h
0x18000b6eb  jmp     loc_18000B9E6
0x18000b6f0  mov     edx, 3Dh ; '='; Ch
0x18000b6f5  mov     rdi, r15
0x18000b6f8  call    wcschr
0x18000b6fd  mov     r13, rax
0x18000b700  test    rax, rax
0x18000b703  jz      loc_18000B9D3
0x18000b709  cmp     rax, r15
0x18000b70c  jz      loc_18000B9D3
0x18000b712  mov     r14, cs:_wenviron_table
0x18000b719  cmp     r14, cs:__dcrt_initial_wide_environment
0x18000b720  movzx   r12d, word ptr [rax+2]
0x18000b725  jnz     short loc_18000B739
0x18000b727  mov     rcx, r14
0x18000b72a  call    copy_environment_wchar_t_
0x18000b72f  mov     r14, rax
0x18000b732  mov     cs:_wenviron_table, rax
0x18000b739  mov     ebx, 1
0x18000b73e  test    r14, r14
0x18000b741  jnz     loc_18000B814
0x18000b747  mov     rax, cs:_environ_table
0x18000b74e  test    ebp, ebp
0x18000b750  jz      short loc_18000B7A3
0x18000b752  test    rax, rax
0x18000b755  jz      short loc_18000B7A3
0x18000b757  call    __dcrt_get_or_create_wide_environment_nolock
0x18000b75c  test    rax, rax
0x18000b75f  jnz     short loc_18000B77F
0x18000b761  call    _errno
0x18000b766  mov     dword ptr [rax], 16h
0x18000b76c  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000b770  mov     rcx, r15; Block
0x18000b773  call    _free_base
0x18000b778  mov     eax, ebp
0x18000b77a  jmp     loc_18000B9EA
0x18000b77f  mov     r14, cs:_wenviron_table
0x18000b786  cmp     r14, cs:__dcrt_initial_wide_environment
0x18000b78d  jnz     short loc_18000B80B
0x18000b78f  mov     rcx, r14
0x18000b792  call    copy_environment_wchar_t_
0x18000b797  mov     r14, rax
0x18000b79a  mov     cs:_wenviron_table, rax
0x18000b7a1  jmp     short loc_18000B80B
0x18000b7a3  test    r12w, r12w
0x18000b7a7  jz      loc_18000B8CC
0x18000b7ad  test    rax, rax
0x18000b7b0  jnz     short loc_18000B7E0
0x18000b7b2  lea     edx, [rax+8]; Size
0x18000b7b5  mov     rcx, rbx; Count
0x18000b7b8  call    _calloc_base
0x18000b7bd  xor     ecx, ecx; Block
0x18000b7bf  mov     cs:_environ_table, rax
0x18000b7c6  call    _free_base
0x18000b7cb  cmp     cs:_environ_table, rsi
0x18000b7d2  jz      short loc_18000B76C
0x18000b7d4  mov     r14, cs:_wenviron_table
0x18000b7db  test    r14, r14
0x18000b7de  jnz     short loc_18000B814
0x18000b7e0  mov     edx, 8; Size
0x18000b7e5  mov     rcx, rbx; Count
0x18000b7e8  call    _calloc_base
0x18000b7ed  xor     ecx, ecx; Block
0x18000b7ef  mov     cs:_wenviron_table, rax
0x18000b7f6  call    _free_base
0x18000b7fb  mov     r14, cs:_wenviron_table
0x18000b802  test    r14, r14
0x18000b805  jz      loc_18000B76C
0x18000b80b  test    r14, r14
0x18000b80e  jz      loc_18000B76C
0x18000b814  mov     rax, [r14]
0x18000b817  sub     r13, r15
0x18000b81a  sar     r13, 1
0x18000b81d  mov     rbx, r14
0x18000b820  jmp     short loc_18000B851
0x18000b822  mov     r8, r13; MaxCount
0x18000b825  mov     rdx, rax; String2
0x18000b828  mov     rcx, r15; String1
0x18000b82b  call    _wcsnicoll
0x18000b830  test    eax, eax
0x18000b832  jnz     short loc_18000B84A
0x18000b834  mov     rax, [rbx]
0x18000b837  mov     ecx, 3Dh ; '='
0x18000b83c  cmp     [rax+r13*2], cx
0x18000b841  jz      short loc_18000B882
0x18000b843  cmp     [rax+r13*2], si
0x18000b848  jz      short loc_18000B882
0x18000b84a  add     rbx, 8
0x18000b84e  mov     rax, [rbx]
0x18000b851  test    rax, rax
0x18000b854  jnz     short loc_18000B822
0x18000b856  sub     rbx, r14
0x18000b859  sar     rbx, 3
0x18000b85d  neg     rbx
0x18000b860  test    rbx, rbx
0x18000b863  js      short loc_18000B8C6
0x18000b865  cmp     [r14], rsi
0x18000b868  jz      short loc_18000B8C6
0x18000b86a  mov     rcx, [r14+rbx*8]; Block
0x18000b86e  call    _free_base
0x18000b873  test    r12w, r12w
0x18000b877  jz      short loc_18000B897
0x18000b879  mov     [r14+rbx*8], r15
0x18000b87d  jmp     loc_18000B927
0x18000b882  sub     rbx, r14
0x18000b885  sar     rbx, 3
0x18000b889  jmp     short loc_18000B860
0x18000b88b  mov     rax, [r14+rbx*8+8]
0x18000b890  mov     [r14+rbx*8], rax
0x18000b894  inc     rbx
0x18000b897  cmp     [r14+rbx*8], rsi
0x18000b89b  jnz     short loc_18000B88B
0x18000b89d  mov     r8d, 8; Size
0x18000b8a3  mov     rdx, rbx; Count
0x18000b8a6  mov     rcx, r14; Block
0x18000b8a9  call    _recalloc_base
0x18000b8ae  xor     ecx, ecx; Block
0x18000b8b0  mov     rbx, rax
0x18000b8b3  call    _free_base
0x18000b8b8  test    rbx, rbx
0x18000b8bb  jz      short loc_18000B92A
0x18000b8bd  mov     cs:_wenviron_table, rbx
0x18000b8c4  jmp     short loc_18000B92A
0x18000b8c6  test    r12w, r12w
0x18000b8ca  jnz     short loc_18000B8D3
0x18000b8cc  mov     ebp, esi
0x18000b8ce  jmp     loc_18000B770
0x18000b8d3  neg     rbx
0x18000b8d6  lea     rdx, [rbx+2]; Count
0x18000b8da  cmp     rdx, rbx
0x18000b8dd  jb      loc_18000B76C
0x18000b8e3  mov     rax, 1FFFFFFFFFFFFFFFh
0x18000b8ed  cmp     rdx, rax
0x18000b8f0  jnb     loc_18000B76C
0x18000b8f6  mov     r8d, 8; Size
0x18000b8fc  mov     rcx, r14; Block
0x18000b8ff  call    _recalloc_base
0x18000b904  xor     ecx, ecx; Block
0x18000b906  mov     r14, rax
0x18000b909  call    _free_base
0x18000b90e  test    r14, r14
0x18000b911  jz      loc_18000B76C
0x18000b917  mov     [r14+rbx*8], r15
0x18000b91b  mov     [r14+rbx*8+8], rsi
0x18000b920  mov     cs:_wenviron_table, r14
0x18000b927  mov     rdi, rsi
0x18000b92a  test    ebp, ebp
0x18000b92c  jz      loc_18000B9C7
0x18000b932  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000b936  mov     r14, rbp
0x18000b939  inc     r14
0x18000b93c  cmp     [r15+r14*2], si
0x18000b941  jnz     short loc_18000B939
0x18000b943  mov     edx, 2; Size
0x18000b948  add     r14, rdx
0x18000b94b  mov     rcx, r14; Count
0x18000b94e  call    _calloc_base
0x18000b953  mov     rbx, rax
0x18000b956  test    rax, rax
0x18000b959  jnz     short loc_18000B964
0x18000b95b  xor     ecx, ecx; Block
0x18000b95d  call    _free_base
0x18000b962  jmp     short loc_18000B9B3
0x18000b964  mov     r8, r15; Source
0x18000b967  mov     rdx, r14; SizeInWords
0x18000b96a  mov     rcx, rbx; Destination
0x18000b96d  call    wcscpy_s
0x18000b972  test    eax, eax
0x18000b974  jnz     loc_18000BA07
0x18000b97a  neg     r12w
0x18000b97e  mov     [rbx+r13*2], si
0x18000b983  lea     rax, [r13+1]
0x18000b987  mov     rcx, rbx; lpName
0x18000b98a  sbb     rdx, rdx
0x18000b98d  lea     rax, [rbx+rax*2]
0x18000b991  and     rdx, rax; lpValue
0x18000b994  call    cs:__imp_SetEnvironmentVariableW
0x18000b99a  test    eax, eax
0x18000b99c  jnz     short loc_18000B9BF
0x18000b99e  call    _errno
0x18000b9a3  mov     rcx, rbx; Block
0x18000b9a6  mov     dword ptr [rax], 2Ah ; '*'
0x18000b9ac  call    _free_base
0x18000b9b1  mov     esi, ebp
0x18000b9b3  mov     rcx, rdi; Block
0x18000b9b6  call    _free_base
0x18000b9bb  mov     eax, esi
0x18000b9bd  jmp     short loc_18000B9EA
0x18000b9bf  mov     rcx, rbx; Block
0x18000b9c2  call    _free_base
0x18000b9c7  mov     rcx, rdi; Block
0x18000b9ca  call    _free_base
0x18000b9cf  xor     eax, eax
0x18000b9d1  jmp     short loc_18000B9EA
0x18000b9d3  call    _errno
0x18000b9d8  mov     rcx, r15; Block
0x18000b9db  mov     dword ptr [rax], 16h
0x18000b9e1  call    _free_base
0x18000b9e6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b9ea  mov     rbx, [rsp+58h+arg_0]
0x18000b9ef  mov     rbp, [rsp+58h+arg_8]
0x18000b9f4  mov     rsi, [rsp+58h+arg_10]
0x18000b9f9  add     rsp, 30h
0x18000b9fd  pop     r15
0x18000b9ff  pop     r14
0x18000ba01  pop     r13
0x18000ba03  pop     r12
0x18000ba05  pop     rdi
0x18000ba06  retn
0x18000ba07  xor     r9d, r9d; LineNo
0x18000ba0a  mov     [rsp+58h+Reserved], rsi; Reserved
0x18000ba0f  xor     r8d, r8d; FileName
0x18000ba12  xor     edx, edx; FunctionName
0x18000ba14  xor     ecx, ecx; Expression
0x18000ba16  call    _invoke_watson
```
