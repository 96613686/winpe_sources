# common_set_variable_in_environment_nolock_wchar_t_

- ea: `0x140017230`
- end: `0x140017594`
- name: `common_set_variable_in_environment_nolock_wchar_t_`
- size: `868`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140017684`

## callees

- `0x140007960`
- `0x14000bf7c`
- `0x1400120dc`
- `0x14001294c`
- `0x140013e10`
- `0x140013ed0`
- `0x140013fe0`
- `0x140017230`
- `0x140017594`
- `0x140018130`
- `0x14001b230`

## import_xrefs

- `KERNEL32!SetEnvironmentVariableW` at `0x14001750c`
- `KERNEL32!SetEnvironmentVariableW` at `0x14001750c`

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
      environ_table = (__int64)calloc_base(1u, 8u);
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
0x140017230  mov     [rsp+arg_0], rbx
0x140017235  mov     [rsp+arg_8], rbp
0x14001723a  mov     [rsp+arg_10], rsi
0x14001723f  push    rdi
0x140017240  push    r12
0x140017242  push    r13
0x140017244  push    r14
0x140017246  push    r15
0x140017248  sub     rsp, 30h
0x14001724c  xor     esi, esi
0x14001724e  mov     ebp, edx
0x140017250  mov     r15, rcx
0x140017253  test    rcx, rcx
0x140017256  jnz     short loc_140017268
0x140017258  call    _errno
0x14001725d  mov     dword ptr [rax], 16h
0x140017263  jmp     loc_14001755E
0x140017268  mov     edx, 3Dh ; '='; Ch
0x14001726d  mov     rdi, r15
0x140017270  call    wcschr
0x140017275  mov     r13, rax
0x140017278  test    rax, rax
0x14001727b  jz      loc_14001754B
0x140017281  cmp     rax, r15
0x140017284  jz      loc_14001754B
0x14001728a  mov     r14, cs:_wenviron_table
0x140017291  cmp     r14, cs:__dcrt_initial_wide_environment
0x140017298  movzx   r12d, word ptr [rax+2]
0x14001729d  jnz     short loc_1400172B1
0x14001729f  mov     rcx, r14
0x1400172a2  call    copy_environment_wchar_t_
0x1400172a7  mov     r14, rax
0x1400172aa  mov     cs:_wenviron_table, rax
0x1400172b1  mov     ebx, 1
0x1400172b6  test    r14, r14
0x1400172b9  jnz     loc_14001738C
0x1400172bf  mov     rax, cs:_environ_table
0x1400172c6  test    ebp, ebp
0x1400172c8  jz      short loc_14001731B
0x1400172ca  test    rax, rax
0x1400172cd  jz      short loc_14001731B
0x1400172cf  call    __dcrt_get_or_create_wide_environment_nolock
0x1400172d4  test    rax, rax
0x1400172d7  jnz     short loc_1400172F7
0x1400172d9  call    _errno
0x1400172de  mov     dword ptr [rax], 16h
0x1400172e4  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1400172e8  mov     rcx, r15; Block
0x1400172eb  call    _free_base
0x1400172f0  mov     eax, ebp
0x1400172f2  jmp     loc_140017562
0x1400172f7  mov     r14, cs:_wenviron_table
0x1400172fe  cmp     r14, cs:__dcrt_initial_wide_environment
0x140017305  jnz     short loc_140017383
0x140017307  mov     rcx, r14
0x14001730a  call    copy_environment_wchar_t_
0x14001730f  mov     r14, rax
0x140017312  mov     cs:_wenviron_table, rax
0x140017319  jmp     short loc_140017383
0x14001731b  test    r12w, r12w
0x14001731f  jz      loc_140017444
0x140017325  test    rax, rax
0x140017328  jnz     short loc_140017358
0x14001732a  lea     edx, [rax+8]; Size
0x14001732d  mov     rcx, rbx; Count
0x140017330  call    _calloc_base
0x140017335  xor     ecx, ecx; Block
0x140017337  mov     cs:_environ_table, rax
0x14001733e  call    _free_base
0x140017343  cmp     cs:_environ_table, rsi
0x14001734a  jz      short loc_1400172E4
0x14001734c  mov     r14, cs:_wenviron_table
0x140017353  test    r14, r14
0x140017356  jnz     short loc_14001738C
0x140017358  mov     edx, 8; Size
0x14001735d  mov     rcx, rbx; Count
0x140017360  call    _calloc_base
0x140017365  xor     ecx, ecx; Block
0x140017367  mov     cs:_wenviron_table, rax
0x14001736e  call    _free_base
0x140017373  mov     r14, cs:_wenviron_table
0x14001737a  test    r14, r14
0x14001737d  jz      loc_1400172E4
0x140017383  test    r14, r14
0x140017386  jz      loc_1400172E4
0x14001738c  mov     rax, [r14]
0x14001738f  sub     r13, r15
0x140017392  sar     r13, 1
0x140017395  mov     rbx, r14
0x140017398  jmp     short loc_1400173C9
0x14001739a  mov     r8, r13; MaxCount
0x14001739d  mov     rdx, rax; String2
0x1400173a0  mov     rcx, r15; String1
0x1400173a3  call    _wcsnicoll
0x1400173a8  test    eax, eax
0x1400173aa  jnz     short loc_1400173C2
0x1400173ac  mov     rax, [rbx]
0x1400173af  mov     ecx, 3Dh ; '='
0x1400173b4  cmp     [rax+r13*2], cx
0x1400173b9  jz      short loc_1400173FA
0x1400173bb  cmp     [rax+r13*2], si
0x1400173c0  jz      short loc_1400173FA
0x1400173c2  add     rbx, 8
0x1400173c6  mov     rax, [rbx]
0x1400173c9  test    rax, rax
0x1400173cc  jnz     short loc_14001739A
0x1400173ce  sub     rbx, r14
0x1400173d1  sar     rbx, 3
0x1400173d5  neg     rbx
0x1400173d8  test    rbx, rbx
0x1400173db  js      short loc_14001743E
0x1400173dd  cmp     [r14], rsi
0x1400173e0  jz      short loc_14001743E
0x1400173e2  mov     rcx, [r14+rbx*8]; Block
0x1400173e6  call    _free_base
0x1400173eb  test    r12w, r12w
0x1400173ef  jz      short loc_14001740F
0x1400173f1  mov     [r14+rbx*8], r15
0x1400173f5  jmp     loc_14001749F
0x1400173fa  sub     rbx, r14
0x1400173fd  sar     rbx, 3
0x140017401  jmp     short loc_1400173D8
0x140017403  mov     rax, [r14+rbx*8+8]
0x140017408  mov     [r14+rbx*8], rax
0x14001740c  inc     rbx
0x14001740f  cmp     [r14+rbx*8], rsi
0x140017413  jnz     short loc_140017403
0x140017415  mov     r8d, 8; Size
0x14001741b  mov     rdx, rbx; Count
0x14001741e  mov     rcx, r14; Block
0x140017421  call    _recalloc_base
0x140017426  xor     ecx, ecx; Block
0x140017428  mov     rbx, rax
0x14001742b  call    _free_base
0x140017430  test    rbx, rbx
0x140017433  jz      short loc_1400174A2
0x140017435  mov     cs:_wenviron_table, rbx
0x14001743c  jmp     short loc_1400174A2
0x14001743e  test    r12w, r12w
0x140017442  jnz     short loc_14001744B
0x140017444  mov     ebp, esi
0x140017446  jmp     loc_1400172E8
0x14001744b  neg     rbx
0x14001744e  lea     rdx, [rbx+2]; Count
0x140017452  cmp     rdx, rbx
0x140017455  jb      loc_1400172E4
0x14001745b  mov     rax, 1FFFFFFFFFFFFFFFh
0x140017465  cmp     rdx, rax
0x140017468  jnb     loc_1400172E4
0x14001746e  mov     r8d, 8; Size
0x140017474  mov     rcx, r14; Block
0x140017477  call    _recalloc_base
0x14001747c  xor     ecx, ecx; Block
0x14001747e  mov     r14, rax
0x140017481  call    _free_base
0x140017486  test    r14, r14
0x140017489  jz      loc_1400172E4
0x14001748f  mov     [r14+rbx*8], r15
0x140017493  mov     [r14+rbx*8+8], rsi
0x140017498  mov     cs:_wenviron_table, r14
0x14001749f  mov     rdi, rsi
0x1400174a2  test    ebp, ebp
0x1400174a4  jz      loc_14001753F
0x1400174aa  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1400174ae  mov     r14, rbp
0x1400174b1  inc     r14
0x1400174b4  cmp     [r15+r14*2], si
0x1400174b9  jnz     short loc_1400174B1
0x1400174bb  mov     edx, 2; Size
0x1400174c0  add     r14, rdx
0x1400174c3  mov     rcx, r14; Count
0x1400174c6  call    _calloc_base
0x1400174cb  mov     rbx, rax
0x1400174ce  test    rax, rax
0x1400174d1  jnz     short loc_1400174DC
0x1400174d3  xor     ecx, ecx; Block
0x1400174d5  call    _free_base
0x1400174da  jmp     short loc_14001752B
0x1400174dc  mov     r8, r15; Source
0x1400174df  mov     rdx, r14; SizeInWords
0x1400174e2  mov     rcx, rbx; Destination
0x1400174e5  call    wcscpy_s
0x1400174ea  test    eax, eax
0x1400174ec  jnz     loc_14001757F
0x1400174f2  neg     r12w
0x1400174f6  mov     [rbx+r13*2], si
0x1400174fb  lea     rax, [r13+1]
0x1400174ff  mov     rcx, rbx; lpName
0x140017502  sbb     rdx, rdx
0x140017505  lea     rax, [rbx+rax*2]
0x140017509  and     rdx, rax; lpValue
0x14001750c  call    cs:__imp_SetEnvironmentVariableW
0x140017512  test    eax, eax
0x140017514  jnz     short loc_140017537
0x140017516  call    _errno
0x14001751b  mov     rcx, rbx; Block
0x14001751e  mov     dword ptr [rax], 2Ah ; '*'
0x140017524  call    _free_base
0x140017529  mov     esi, ebp
0x14001752b  mov     rcx, rdi; Block
0x14001752e  call    _free_base
0x140017533  mov     eax, esi
0x140017535  jmp     short loc_140017562
0x140017537  mov     rcx, rbx; Block
0x14001753a  call    _free_base
0x14001753f  mov     rcx, rdi; Block
0x140017542  call    _free_base
0x140017547  xor     eax, eax
0x140017549  jmp     short loc_140017562
0x14001754b  call    _errno
0x140017550  mov     rcx, r15; Block
0x140017553  mov     dword ptr [rax], 16h
0x140017559  call    _free_base
0x14001755e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140017562  mov     rbx, [rsp+58h+arg_0]
0x140017567  mov     rbp, [rsp+58h+arg_8]
0x14001756c  mov     rsi, [rsp+58h+arg_10]
0x140017571  add     rsp, 30h
0x140017575  pop     r15
0x140017577  pop     r14
0x140017579  pop     r13
0x14001757b  pop     r12
0x14001757d  pop     rdi
0x14001757e  retn
0x14001757f  xor     r9d, r9d; LineNo
0x140017582  mov     [rsp+58h+Reserved], rsi; Reserved
0x140017587  xor     r8d, r8d; FileName
0x14001758a  xor     edx, edx; FunctionName
0x14001758c  xor     ecx, ecx; Expression
0x14001758e  call    _invoke_watson
```
