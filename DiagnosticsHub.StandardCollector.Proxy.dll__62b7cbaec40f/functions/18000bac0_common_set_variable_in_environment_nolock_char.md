# common_set_variable_in_environment_nolock_char_

- ea: `0x18000bac0`
- end: `0x18000be18`
- name: `common_set_variable_in_environment_nolock_char_`
- size: `856`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18000c5c8`

## callees

- `0x180005a08`
- `0x180007c50`
- `0x180007ee8`
- `0x180007fc0`
- `0x180008040`
- `0x18000b570`
- `0x18000bac0`
- `0x18000c17c`
- `0x18000c5e0`
- `0x180014020`
- `0x180014354`
- `0x180024120`

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
0x18000bac0  mov     [rsp+arg_10], rbx
0x18000bac5  mov     [rsp+arg_8], edx
0x18000bac9  push    rbp
0x18000baca  push    rsi
0x18000bacb  push    rdi
0x18000bacc  push    r12
0x18000bace  push    r13
0x18000bad0  push    r14
0x18000bad2  push    r15
0x18000bad4  sub     rsp, 30h
0x18000bad8  xor     esi, esi
0x18000bada  mov     ebx, edx
0x18000badc  mov     r15, rcx
0x18000badf  test    rcx, rcx
0x18000bae2  jnz     short loc_18000BAF4
0x18000bae4  call    _errno
0x18000bae9  mov     dword ptr [rax], 16h
0x18000baef  jmp     loc_18000BDE7
0x18000baf4  mov     edx, 3Dh ; '='; Val
0x18000baf9  mov     rdi, r15
0x18000bafc  call    strchr
0x18000bb01  mov     r13, rax
0x18000bb04  test    rax, rax
0x18000bb07  jz      loc_18000BDD4
0x18000bb0d  cmp     rax, r15
0x18000bb10  jz      loc_18000BDD4
0x18000bb16  mov     r14, cs:_environ_table
0x18000bb1d  cmp     r14, cs:__dcrt_initial_narrow_environment
0x18000bb24  mov     bpl, [rax+1]
0x18000bb28  mov     [rsp+68h+arg_0], bpl
0x18000bb2d  jnz     short loc_18000BB41
0x18000bb2f  mov     rcx, r14
0x18000bb32  call    copy_environment_char_
0x18000bb37  mov     r14, rax
0x18000bb3a  mov     cs:_environ_table, rax
0x18000bb41  mov     r12d, 1
0x18000bb47  test    r14, r14
0x18000bb4a  jnz     loc_18000BC1A
0x18000bb50  test    ebx, ebx
0x18000bb52  jz      short loc_18000BBA9
0x18000bb54  cmp     cs:_wenviron_table, rsi
0x18000bb5b  jz      short loc_18000BBA9
0x18000bb5d  call    __dcrt_get_or_create_narrow_environment_nolock
0x18000bb62  test    rax, rax
0x18000bb65  jnz     short loc_18000BB85
0x18000bb67  call    _errno
0x18000bb6c  mov     dword ptr [rax], 16h
0x18000bb72  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000bb76  mov     rcx, r15; Block
0x18000bb79  call    _free_base
0x18000bb7e  mov     eax, ebp
0x18000bb80  jmp     loc_18000BDEB
0x18000bb85  mov     r14, cs:_environ_table
0x18000bb8c  cmp     r14, cs:__dcrt_initial_narrow_environment
0x18000bb93  jnz     short loc_18000BC11
0x18000bb95  mov     rcx, r14
0x18000bb98  call    copy_environment_char_
0x18000bb9d  mov     r14, rax
0x18000bba0  mov     cs:_environ_table, rax
0x18000bba7  jmp     short loc_18000BC11
0x18000bba9  test    bpl, bpl
0x18000bbac  jz      loc_18000BCCA
0x18000bbb2  mov     edx, 8; Size
0x18000bbb7  mov     rcx, r12; Count
0x18000bbba  call    _calloc_base
0x18000bbbf  xor     ecx, ecx; Block
0x18000bbc1  mov     cs:_environ_table, rax
0x18000bbc8  call    _free_base
0x18000bbcd  mov     r14, cs:_environ_table
0x18000bbd4  test    r14, r14
0x18000bbd7  jz      short loc_18000BB72
0x18000bbd9  cmp     cs:_wenviron_table, rsi
0x18000bbe0  jnz     short loc_18000BC11
0x18000bbe2  mov     edx, 8; Size
0x18000bbe7  mov     rcx, r12; Count
0x18000bbea  call    _calloc_base
0x18000bbef  xor     ecx, ecx; Block
0x18000bbf1  mov     cs:_wenviron_table, rax
0x18000bbf8  call    _free_base
0x18000bbfd  cmp     cs:_wenviron_table, rsi
0x18000bc04  jz      loc_18000BB72
0x18000bc0a  mov     r14, cs:_environ_table
0x18000bc11  test    r14, r14
0x18000bc14  jz      loc_18000BB72
0x18000bc1a  mov     rax, [r14]
0x18000bc1d  mov     r12, r13
0x18000bc20  sub     r12, r15
0x18000bc23  mov     rbx, r14
0x18000bc26  jmp     short loc_18000BC51
0x18000bc28  mov     r8, r12; MaxCount
0x18000bc2b  mov     rdx, rax; String2
0x18000bc2e  mov     rcx, r15; String1
0x18000bc31  call    _strnicoll
0x18000bc36  test    eax, eax
0x18000bc38  jnz     short loc_18000BC4A
0x18000bc3a  mov     rax, [rbx]
0x18000bc3d  cmp     byte ptr [r12+rax], 3Dh ; '='
0x18000bc42  jz      short loc_18000BC81
0x18000bc44  cmp     [r12+rax], sil
0x18000bc48  jz      short loc_18000BC81
0x18000bc4a  add     rbx, 8
0x18000bc4e  mov     rax, [rbx]
0x18000bc51  test    rax, rax
0x18000bc54  jnz     short loc_18000BC28
0x18000bc56  sub     rbx, r14
0x18000bc59  sar     rbx, 3
0x18000bc5d  neg     rbx
0x18000bc60  test    rbx, rbx
0x18000bc63  js      short loc_18000BCC5
0x18000bc65  cmp     [r14], rsi
0x18000bc68  jz      short loc_18000BCC5
0x18000bc6a  mov     rcx, [r14+rbx*8]; Block
0x18000bc6e  call    _free_base
0x18000bc73  test    bpl, bpl
0x18000bc76  jz      short loc_18000BC96
0x18000bc78  mov     [r14+rbx*8], r15
0x18000bc7c  jmp     loc_18000BD25
0x18000bc81  sub     rbx, r14
0x18000bc84  sar     rbx, 3
0x18000bc88  jmp     short loc_18000BC60
0x18000bc8a  mov     rax, [r14+rbx*8+8]
0x18000bc8f  mov     [r14+rbx*8], rax
0x18000bc93  inc     rbx
0x18000bc96  cmp     [r14+rbx*8], rsi
0x18000bc9a  jnz     short loc_18000BC8A
0x18000bc9c  mov     r8d, 8; Size
0x18000bca2  mov     rdx, rbx; Count
0x18000bca5  mov     rcx, r14; Block
0x18000bca8  call    _recalloc_base
0x18000bcad  xor     ecx, ecx; Block
0x18000bcaf  mov     rbx, rax
0x18000bcb2  call    _free_base
0x18000bcb7  test    rbx, rbx
0x18000bcba  jz      short loc_18000BD28
0x18000bcbc  mov     cs:_environ_table, rbx
0x18000bcc3  jmp     short loc_18000BD28
0x18000bcc5  test    bpl, bpl
0x18000bcc8  jnz     short loc_18000BCD1
0x18000bcca  mov     ebp, esi
0x18000bccc  jmp     loc_18000BB76
0x18000bcd1  neg     rbx
0x18000bcd4  lea     rdx, [rbx+2]; Count
0x18000bcd8  cmp     rdx, rbx
0x18000bcdb  jb      loc_18000BB72
0x18000bce1  mov     rax, 1FFFFFFFFFFFFFFFh
0x18000bceb  cmp     rdx, rax
0x18000bcee  jnb     loc_18000BB72
0x18000bcf4  mov     r8d, 8; Size
0x18000bcfa  mov     rcx, r14; Block
0x18000bcfd  call    _recalloc_base
0x18000bd02  xor     ecx, ecx; Block
0x18000bd04  mov     r14, rax
0x18000bd07  call    _free_base
0x18000bd0c  test    r14, r14
0x18000bd0f  jz      loc_18000BB72
0x18000bd15  mov     [r14+rbx*8], r15
0x18000bd19  mov     [r14+rbx*8+8], rsi
0x18000bd1e  mov     cs:_environ_table, r14
0x18000bd25  mov     rdi, rsi
0x18000bd28  cmp     [rsp+68h+arg_8], esi
0x18000bd2c  jz      loc_18000BDC8
0x18000bd32  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000bd36  mov     r14, rbp
0x18000bd39  inc     r14
0x18000bd3c  cmp     [r15+r14], sil
0x18000bd40  jnz     short loc_18000BD39
0x18000bd42  mov     edx, 1; Size
0x18000bd47  lea     rcx, [r14+2]; Count
0x18000bd4b  call    _calloc_base
0x18000bd50  mov     rbx, rax
0x18000bd53  test    rax, rax
0x18000bd56  jnz     short loc_18000BD61
0x18000bd58  xor     ecx, ecx; Block
0x18000bd5a  call    _free_base
0x18000bd5f  jmp     short loc_18000BDB4
0x18000bd61  mov     r8, r15; Source
0x18000bd64  lea     rdx, [r14+2]; SizeInBytes
0x18000bd68  mov     rcx, rbx; Destination
0x18000bd6b  call    strcpy_s
0x18000bd70  test    eax, eax
0x18000bd72  jnz     loc_18000BE03
0x18000bd78  mov     rax, rbx
0x18000bd7b  lea     rcx, [r13+1]
0x18000bd7f  sub     rax, r15
0x18000bd82  add     rcx, rax
0x18000bd85  neg     [rsp+68h+arg_0]
0x18000bd89  sbb     rdx, rdx
0x18000bd8c  mov     [rax+r13], sil
0x18000bd90  and     rdx, rcx
0x18000bd93  mov     rcx, rbx
0x18000bd96  call    __acrt_SetEnvironmentVariableA
0x18000bd9b  test    eax, eax
0x18000bd9d  jnz     short loc_18000BDC0
0x18000bd9f  call    _errno
0x18000bda4  mov     rcx, rbx; Block
0x18000bda7  mov     dword ptr [rax], 2Ah ; '*'
0x18000bdad  call    _free_base
0x18000bdb2  mov     esi, ebp
0x18000bdb4  mov     rcx, rdi; Block
0x18000bdb7  call    _free_base
0x18000bdbc  mov     eax, esi
0x18000bdbe  jmp     short loc_18000BDEB
0x18000bdc0  mov     rcx, rbx; Block
0x18000bdc3  call    _free_base
0x18000bdc8  mov     rcx, rdi; Block
0x18000bdcb  call    _free_base
0x18000bdd0  xor     eax, eax
0x18000bdd2  jmp     short loc_18000BDEB
0x18000bdd4  call    _errno
0x18000bdd9  mov     rcx, r15; Block
0x18000bddc  mov     dword ptr [rax], 16h
0x18000bde2  call    _free_base
0x18000bde7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bdeb  mov     rbx, [rsp+68h+arg_10]
0x18000bdf3  add     rsp, 30h
0x18000bdf7  pop     r15
0x18000bdf9  pop     r14
0x18000bdfb  pop     r13
0x18000bdfd  pop     r12
0x18000bdff  pop     rdi
0x18000be00  pop     rsi
0x18000be01  pop     rbp
0x18000be02  retn
0x18000be03  xor     r9d, r9d; LineNo
0x18000be06  mov     [rsp+68h+Reserved], rsi; Reserved
0x18000be0b  xor     r8d, r8d; FileName
0x18000be0e  xor     edx, edx; FunctionName
0x18000be10  xor     ecx, ecx; Expression
0x18000be12  call    _invoke_watson
```
