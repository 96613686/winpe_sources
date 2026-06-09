# common_set_variable_in_environment_nolock_wchar_t_

- ea: `0x18000be18`
- end: `0x18000c17c`
- name: `common_set_variable_in_environment_nolock_wchar_t_`
- size: `868`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000c5d0`

## callees

- `0x180005a44`
- `0x180007c50`
- `0x180007ee8`
- `0x180007fc0`
- `0x180008040`
- `0x18000b460`
- `0x18000be18`
- `0x18000c264`
- `0x18000c5e0`
- `0x180013d00`
- `0x1800241a0`

## import_xrefs

- `KERNEL32!SetEnvironmentVariableW` at `0x18000c0f4`
- `KERNEL32!SetEnvironmentVariableW` at `0x18000c0f4`

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
0x18000be18  mov     [rsp+arg_0], rbx
0x18000be1d  mov     [rsp+arg_8], rbp
0x18000be22  mov     [rsp+arg_10], rsi
0x18000be27  push    rdi
0x18000be28  push    r12
0x18000be2a  push    r13
0x18000be2c  push    r14
0x18000be2e  push    r15
0x18000be30  sub     rsp, 30h
0x18000be34  xor     esi, esi
0x18000be36  mov     ebp, edx
0x18000be38  mov     r15, rcx
0x18000be3b  test    rcx, rcx
0x18000be3e  jnz     short loc_18000BE50
0x18000be40  call    _errno
0x18000be45  mov     dword ptr [rax], 16h
0x18000be4b  jmp     loc_18000C146
0x18000be50  mov     edx, 3Dh ; '='; Ch
0x18000be55  mov     rdi, r15
0x18000be58  call    wcschr
0x18000be5d  mov     r13, rax
0x18000be60  test    rax, rax
0x18000be63  jz      loc_18000C133
0x18000be69  cmp     rax, r15
0x18000be6c  jz      loc_18000C133
0x18000be72  mov     r14, cs:_wenviron_table
0x18000be79  cmp     r14, cs:__dcrt_initial_wide_environment
0x18000be80  movzx   r12d, word ptr [rax+2]
0x18000be85  jnz     short loc_18000BE99
0x18000be87  mov     rcx, r14
0x18000be8a  call    copy_environment_wchar_t_
0x18000be8f  mov     r14, rax
0x18000be92  mov     cs:_wenviron_table, rax
0x18000be99  mov     ebx, 1
0x18000be9e  test    r14, r14
0x18000bea1  jnz     loc_18000BF74
0x18000bea7  mov     rax, cs:_environ_table
0x18000beae  test    ebp, ebp
0x18000beb0  jz      short loc_18000BF03
0x18000beb2  test    rax, rax
0x18000beb5  jz      short loc_18000BF03
0x18000beb7  call    __dcrt_get_or_create_wide_environment_nolock
0x18000bebc  test    rax, rax
0x18000bebf  jnz     short loc_18000BEDF
0x18000bec1  call    _errno
0x18000bec6  mov     dword ptr [rax], 16h
0x18000becc  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000bed0  mov     rcx, r15; Block
0x18000bed3  call    _free_base
0x18000bed8  mov     eax, ebp
0x18000beda  jmp     loc_18000C14A
0x18000bedf  mov     r14, cs:_wenviron_table
0x18000bee6  cmp     r14, cs:__dcrt_initial_wide_environment
0x18000beed  jnz     short loc_18000BF6B
0x18000beef  mov     rcx, r14
0x18000bef2  call    copy_environment_wchar_t_
0x18000bef7  mov     r14, rax
0x18000befa  mov     cs:_wenviron_table, rax
0x18000bf01  jmp     short loc_18000BF6B
0x18000bf03  test    r12w, r12w
0x18000bf07  jz      loc_18000C02C
0x18000bf0d  test    rax, rax
0x18000bf10  jnz     short loc_18000BF40
0x18000bf12  lea     edx, [rax+8]; Size
0x18000bf15  mov     rcx, rbx; Count
0x18000bf18  call    _calloc_base
0x18000bf1d  xor     ecx, ecx; Block
0x18000bf1f  mov     cs:_environ_table, rax
0x18000bf26  call    _free_base
0x18000bf2b  cmp     cs:_environ_table, rsi
0x18000bf32  jz      short loc_18000BECC
0x18000bf34  mov     r14, cs:_wenviron_table
0x18000bf3b  test    r14, r14
0x18000bf3e  jnz     short loc_18000BF74
0x18000bf40  mov     edx, 8; Size
0x18000bf45  mov     rcx, rbx; Count
0x18000bf48  call    _calloc_base
0x18000bf4d  xor     ecx, ecx; Block
0x18000bf4f  mov     cs:_wenviron_table, rax
0x18000bf56  call    _free_base
0x18000bf5b  mov     r14, cs:_wenviron_table
0x18000bf62  test    r14, r14
0x18000bf65  jz      loc_18000BECC
0x18000bf6b  test    r14, r14
0x18000bf6e  jz      loc_18000BECC
0x18000bf74  mov     rax, [r14]
0x18000bf77  sub     r13, r15
0x18000bf7a  sar     r13, 1
0x18000bf7d  mov     rbx, r14
0x18000bf80  jmp     short loc_18000BFB1
0x18000bf82  mov     r8, r13; MaxCount
0x18000bf85  mov     rdx, rax; String2
0x18000bf88  mov     rcx, r15; String1
0x18000bf8b  call    _wcsnicoll
0x18000bf90  test    eax, eax
0x18000bf92  jnz     short loc_18000BFAA
0x18000bf94  mov     rax, [rbx]
0x18000bf97  mov     ecx, 3Dh ; '='
0x18000bf9c  cmp     [rax+r13*2], cx
0x18000bfa1  jz      short loc_18000BFE2
0x18000bfa3  cmp     [rax+r13*2], si
0x18000bfa8  jz      short loc_18000BFE2
0x18000bfaa  add     rbx, 8
0x18000bfae  mov     rax, [rbx]
0x18000bfb1  test    rax, rax
0x18000bfb4  jnz     short loc_18000BF82
0x18000bfb6  sub     rbx, r14
0x18000bfb9  sar     rbx, 3
0x18000bfbd  neg     rbx
0x18000bfc0  test    rbx, rbx
0x18000bfc3  js      short loc_18000C026
0x18000bfc5  cmp     [r14], rsi
0x18000bfc8  jz      short loc_18000C026
0x18000bfca  mov     rcx, [r14+rbx*8]; Block
0x18000bfce  call    _free_base
0x18000bfd3  test    r12w, r12w
0x18000bfd7  jz      short loc_18000BFF7
0x18000bfd9  mov     [r14+rbx*8], r15
0x18000bfdd  jmp     loc_18000C087
0x18000bfe2  sub     rbx, r14
0x18000bfe5  sar     rbx, 3
0x18000bfe9  jmp     short loc_18000BFC0
0x18000bfeb  mov     rax, [r14+rbx*8+8]
0x18000bff0  mov     [r14+rbx*8], rax
0x18000bff4  inc     rbx
0x18000bff7  cmp     [r14+rbx*8], rsi
0x18000bffb  jnz     short loc_18000BFEB
0x18000bffd  mov     r8d, 8; Size
0x18000c003  mov     rdx, rbx; Count
0x18000c006  mov     rcx, r14; Block
0x18000c009  call    _recalloc_base
0x18000c00e  xor     ecx, ecx; Block
0x18000c010  mov     rbx, rax
0x18000c013  call    _free_base
0x18000c018  test    rbx, rbx
0x18000c01b  jz      short loc_18000C08A
0x18000c01d  mov     cs:_wenviron_table, rbx
0x18000c024  jmp     short loc_18000C08A
0x18000c026  test    r12w, r12w
0x18000c02a  jnz     short loc_18000C033
0x18000c02c  mov     ebp, esi
0x18000c02e  jmp     loc_18000BED0
0x18000c033  neg     rbx
0x18000c036  lea     rdx, [rbx+2]; Count
0x18000c03a  cmp     rdx, rbx
0x18000c03d  jb      loc_18000BECC
0x18000c043  mov     rax, 1FFFFFFFFFFFFFFFh
0x18000c04d  cmp     rdx, rax
0x18000c050  jnb     loc_18000BECC
0x18000c056  mov     r8d, 8; Size
0x18000c05c  mov     rcx, r14; Block
0x18000c05f  call    _recalloc_base
0x18000c064  xor     ecx, ecx; Block
0x18000c066  mov     r14, rax
0x18000c069  call    _free_base
0x18000c06e  test    r14, r14
0x18000c071  jz      loc_18000BECC
0x18000c077  mov     [r14+rbx*8], r15
0x18000c07b  mov     [r14+rbx*8+8], rsi
0x18000c080  mov     cs:_wenviron_table, r14
0x18000c087  mov     rdi, rsi
0x18000c08a  test    ebp, ebp
0x18000c08c  jz      loc_18000C127
0x18000c092  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000c096  mov     r14, rbp
0x18000c099  inc     r14
0x18000c09c  cmp     [r15+r14*2], si
0x18000c0a1  jnz     short loc_18000C099
0x18000c0a3  mov     edx, 2; Size
0x18000c0a8  add     r14, rdx
0x18000c0ab  mov     rcx, r14; Count
0x18000c0ae  call    _calloc_base
0x18000c0b3  mov     rbx, rax
0x18000c0b6  test    rax, rax
0x18000c0b9  jnz     short loc_18000C0C4
0x18000c0bb  xor     ecx, ecx; Block
0x18000c0bd  call    _free_base
0x18000c0c2  jmp     short loc_18000C113
0x18000c0c4  mov     r8, r15; Source
0x18000c0c7  mov     rdx, r14; SizeInWords
0x18000c0ca  mov     rcx, rbx; Destination
0x18000c0cd  call    wcscpy_s
0x18000c0d2  test    eax, eax
0x18000c0d4  jnz     loc_18000C167
0x18000c0da  neg     r12w
0x18000c0de  mov     [rbx+r13*2], si
0x18000c0e3  lea     rax, [r13+1]
0x18000c0e7  mov     rcx, rbx; lpName
0x18000c0ea  sbb     rdx, rdx
0x18000c0ed  lea     rax, [rbx+rax*2]
0x18000c0f1  and     rdx, rax; lpValue
0x18000c0f4  call    cs:__imp_SetEnvironmentVariableW
0x18000c0fa  test    eax, eax
0x18000c0fc  jnz     short loc_18000C11F
0x18000c0fe  call    _errno
0x18000c103  mov     rcx, rbx; Block
0x18000c106  mov     dword ptr [rax], 2Ah ; '*'
0x18000c10c  call    _free_base
0x18000c111  mov     esi, ebp
0x18000c113  mov     rcx, rdi; Block
0x18000c116  call    _free_base
0x18000c11b  mov     eax, esi
0x18000c11d  jmp     short loc_18000C14A
0x18000c11f  mov     rcx, rbx; Block
0x18000c122  call    _free_base
0x18000c127  mov     rcx, rdi; Block
0x18000c12a  call    _free_base
0x18000c12f  xor     eax, eax
0x18000c131  jmp     short loc_18000C14A
0x18000c133  call    _errno
0x18000c138  mov     rcx, r15; Block
0x18000c13b  mov     dword ptr [rax], 16h
0x18000c141  call    _free_base
0x18000c146  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c14a  mov     rbx, [rsp+58h+arg_0]
0x18000c14f  mov     rbp, [rsp+58h+arg_8]
0x18000c154  mov     rsi, [rsp+58h+arg_10]
0x18000c159  add     rsp, 30h
0x18000c15d  pop     r15
0x18000c15f  pop     r14
0x18000c161  pop     r13
0x18000c163  pop     r12
0x18000c165  pop     rdi
0x18000c166  retn
0x18000c167  xor     r9d, r9d; LineNo
0x18000c16a  mov     [rsp+58h+Reserved], rsi; Reserved
0x18000c16f  xor     r8d, r8d; FileName
0x18000c172  xor     edx, edx; FunctionName
0x18000c174  xor     ecx, ecx; Expression
0x18000c176  call    _invoke_watson
```
