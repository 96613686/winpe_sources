# common_set_variable_in_environment_nolock<wchar_t>(wchar_t * const,int)

- ea: `0x14007b4d0`
- end: `0x14007b833`
- name: `??$common_set_variable_in_environment_nolock@_W@@YAHQEA_WH@Z`
- size: `867`
- prototype: `__int64 __fastcall(_WORD *Block, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14007b924`

## callees

- `0x140053d60`
- `0x140061554`
- `0x1400616b4`
- `0x14006c410`
- `0x140071058`
- `0x1400719e0`
- `0x140072280`
- `0x140073d10`
- `0x1400748f0`
- `0x14007b4d0`
- `0x14007b834`

## import_xrefs

- `KERNEL32!SetEnvironmentVariableW` at `0x14007b7ac`
- `KERNEL32!SetEnvironmentVariableW` at `0x14007b7ac`

## pseudocode

```c
__int64 __fastcall common_set_variable_in_environment_nolock<wchar_t>(_WORD *Block, int a2)
{
  unsigned int v2; // esi
  void *v5; // rdi
  _WORD *v6; // rax
  _WORD *v7; // r13
  __int64 *v8; // r14
  __int16 v9; // r12
  unsigned int v10; // ebp
  __int64 v12; // rax
  __int64 v13; // r13
  __int64 *i; // rbx
  signed __int64 v15; // rbx
  void *v16; // rbx
  unsigned __int64 v17; // rbx
  size_t v18; // rdx
  _QWORD *v19; // r14
  __int64 v20; // r14
  size_t v21; // r14
  _WORD *v22; // rax
  _WORD *v23; // rbx

  v2 = 0;
  if ( Block )
  {
    v5 = Block;
    v6 = (_WORD *)sub_140053D60(Block, 61);
    v7 = v6;
    if ( !v6 || v6 == Block )
    {
      *(_DWORD *)sub_1400616B4() = 22;
      free_base(Block);
      return -1;
    }
    v8 = (__int64 *)::Block;
    v9 = v6[1];
    if ( ::Block == qword_1400C4880 )
    {
      v8 = (__int64 *)copy_environment<wchar_t>(::Block);
      ::Block = v8;
    }
    if ( !v8 )
    {
      if ( a2 && qword_1400C4870 )
      {
        if ( !unknown_libname_91() )
        {
          *(_DWORD *)sub_1400616B4() = 22;
LABEL_12:
          v10 = -1;
LABEL_13:
          free_base(Block);
          return v10;
        }
        v8 = (__int64 *)::Block;
        if ( ::Block == qword_1400C4880 )
        {
          v8 = (__int64 *)copy_environment<wchar_t>(::Block);
          ::Block = v8;
        }
        goto LABEL_21;
      }
      if ( !v9 )
        goto LABEL_39;
      if ( qword_1400C4870 )
        goto LABEL_20;
      qword_1400C4870 = (__int64)calloc_base(1u, 8u);
      free_base(0);
      if ( !qword_1400C4870 )
        goto LABEL_12;
      v8 = (__int64 *)::Block;
      if ( !::Block )
      {
LABEL_20:
        ::Block = calloc_base(1u, 8u);
        free_base(0);
        v8 = (__int64 *)::Block;
        if ( !::Block )
          goto LABEL_12;
LABEL_21:
        if ( !v8 )
          goto LABEL_12;
      }
    }
    v12 = *v8;
    v13 = v7 - Block;
    for ( i = v8; ; v12 = *i )
    {
      if ( !v12 )
      {
        v15 = -(i - v8);
        goto LABEL_29;
      }
      if ( !(unsigned int)sub_1400748F0(Block, v12, v13)
        && (*(_WORD *)(*i + 2 * v13) == 61 || !*(_WORD *)(*i + 2 * v13)) )
      {
        break;
      }
      ++i;
    }
    v15 = i - v8;
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
          ::Block = v16;
LABEL_45:
        if ( a2 )
        {
          v20 = -1;
          do
            ++v20;
          while ( Block[v20] );
          v21 = v20 + 2;
          v22 = calloc_base(v21, 2u);
          v23 = v22;
          if ( !v22 )
          {
            free_base(0);
LABEL_53:
            free_base(v5);
            return v2;
          }
          if ( (unsigned int)sub_14006C410(v22, v21, Block) )
            invoke_watson(0, 0, 0, 0, 0);
          v23[v13] = 0;
          if ( !SetEnvironmentVariableW(v23, (LPCWSTR)((unsigned __int64)&v23[v13 + 1] & -(__int64)(v9 != 0))) )
          {
            *(_DWORD *)sub_1400616B4() = 42;
            free_base(v23);
            v2 = -1;
            goto LABEL_53;
          }
          free_base(v23);
        }
        free_base(v5);
        return 0;
      }
      v8[v15] = (__int64)Block;
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
      ::Block = v19;
      goto LABEL_44;
    }
LABEL_39:
    v10 = 0;
    goto LABEL_13;
  }
  *(_DWORD *)sub_1400616B4() = 22;
  return -1;
}

```

## disassembly

```asm
0x14007b4d0  mov     [rsp+arg_0], rbx
0x14007b4d5  mov     [rsp+arg_8], rbp
0x14007b4da  mov     [rsp+arg_10], rsi
0x14007b4df  push    rdi
0x14007b4e0  push    r12
0x14007b4e2  push    r13
0x14007b4e4  push    r14
0x14007b4e6  push    r15
0x14007b4e8  sub     rsp, 30h
0x14007b4ec  xor     esi, esi
0x14007b4ee  mov     ebp, edx
0x14007b4f0  mov     r15, rcx
0x14007b4f3  test    rcx, rcx
0x14007b4f6  jnz     short loc_14007B508
0x14007b4f8  call    sub_1400616B4
0x14007b4fd  mov     dword ptr [rax], 16h
0x14007b503  jmp     loc_14007B7FE
0x14007b508  mov     edx, 3Dh ; '='
0x14007b50d  mov     rdi, r15
0x14007b510  call    sub_140053D60
0x14007b515  mov     r13, rax
0x14007b518  test    rax, rax
0x14007b51b  jz      loc_14007B7EB
0x14007b521  cmp     rax, r15
0x14007b524  jz      loc_14007B7EB
0x14007b52a  mov     r14, cs:Block
0x14007b531  cmp     r14, cs:qword_1400C4880
0x14007b538  movzx   r12d, word ptr [rax+2]
0x14007b53d  jnz     short loc_14007B551
0x14007b53f  mov     rcx, r14
0x14007b542  call    ??$copy_environment@_W@@YAPEAPEA_WQEAPEA_W@Z
0x14007b547  mov     r14, rax
0x14007b54a  mov     cs:Block, rax
0x14007b551  mov     ebx, 1
0x14007b556  test    r14, r14
0x14007b559  jnz     loc_14007B62C
0x14007b55f  mov     rax, cs:qword_1400C4870
0x14007b566  test    ebp, ebp
0x14007b568  jz      short loc_14007B5BB
0x14007b56a  test    rax, rax
0x14007b56d  jz      short loc_14007B5BB
0x14007b56f  call    unknown_libname_91; Microsoft VisualC 64bit universal runtime
0x14007b574  test    rax, rax
0x14007b577  jnz     short loc_14007B597
0x14007b579  call    sub_1400616B4
0x14007b57e  mov     dword ptr [rax], 16h
0x14007b584  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14007b588  mov     rcx, r15; Block
0x14007b58b  call    _free_base
0x14007b590  mov     eax, ebp
0x14007b592  jmp     loc_14007B802
0x14007b597  mov     r14, cs:Block
0x14007b59e  cmp     r14, cs:qword_1400C4880
0x14007b5a5  jnz     short loc_14007B623
0x14007b5a7  mov     rcx, r14
0x14007b5aa  call    ??$copy_environment@_W@@YAPEAPEA_WQEAPEA_W@Z
0x14007b5af  mov     r14, rax
0x14007b5b2  mov     cs:Block, rax
0x14007b5b9  jmp     short loc_14007B623
0x14007b5bb  test    r12w, r12w
0x14007b5bf  jz      loc_14007B6E4
0x14007b5c5  test    rax, rax
0x14007b5c8  jnz     short loc_14007B5F8
0x14007b5ca  lea     edx, [rax+8]; Size
0x14007b5cd  mov     rcx, rbx; Count
0x14007b5d0  call    _calloc_base
0x14007b5d5  xor     ecx, ecx; Block
0x14007b5d7  mov     cs:qword_1400C4870, rax
0x14007b5de  call    _free_base
0x14007b5e3  cmp     cs:qword_1400C4870, rsi
0x14007b5ea  jz      short loc_14007B584
0x14007b5ec  mov     r14, cs:Block
0x14007b5f3  test    r14, r14
0x14007b5f6  jnz     short loc_14007B62C
0x14007b5f8  mov     edx, 8; Size
0x14007b5fd  mov     rcx, rbx; Count
0x14007b600  call    _calloc_base
0x14007b605  xor     ecx, ecx; Block
0x14007b607  mov     cs:Block, rax
0x14007b60e  call    _free_base
0x14007b613  mov     r14, cs:Block
0x14007b61a  test    r14, r14
0x14007b61d  jz      loc_14007B584
0x14007b623  test    r14, r14
0x14007b626  jz      loc_14007B584
0x14007b62c  mov     rax, [r14]
0x14007b62f  sub     r13, r15
0x14007b632  sar     r13, 1
0x14007b635  mov     rbx, r14
0x14007b638  jmp     short loc_14007B669
0x14007b63a  mov     r8, r13
0x14007b63d  mov     rdx, rax
0x14007b640  mov     rcx, r15
0x14007b643  call    sub_1400748F0
0x14007b648  test    eax, eax
0x14007b64a  jnz     short loc_14007B662
0x14007b64c  mov     rax, [rbx]
0x14007b64f  mov     ecx, 3Dh ; '='
0x14007b654  cmp     [rax+r13*2], cx
0x14007b659  jz      short loc_14007B69A
0x14007b65b  cmp     [rax+r13*2], si
0x14007b660  jz      short loc_14007B69A
0x14007b662  add     rbx, 8
0x14007b666  mov     rax, [rbx]
0x14007b669  test    rax, rax
0x14007b66c  jnz     short loc_14007B63A
0x14007b66e  sub     rbx, r14
0x14007b671  sar     rbx, 3
0x14007b675  neg     rbx
0x14007b678  test    rbx, rbx
0x14007b67b  js      short loc_14007B6DE
0x14007b67d  cmp     [r14], rsi
0x14007b680  jz      short loc_14007B6DE
0x14007b682  mov     rcx, [r14+rbx*8]; Block
0x14007b686  call    _free_base
0x14007b68b  test    r12w, r12w
0x14007b68f  jz      short loc_14007B6AF
0x14007b691  mov     [r14+rbx*8], r15
0x14007b695  jmp     loc_14007B73F
0x14007b69a  sub     rbx, r14
0x14007b69d  sar     rbx, 3
0x14007b6a1  jmp     short loc_14007B678
0x14007b6a3  mov     rax, [r14+rbx*8+8]
0x14007b6a8  mov     [r14+rbx*8], rax
0x14007b6ac  inc     rbx
0x14007b6af  cmp     [r14+rbx*8], rsi
0x14007b6b3  jnz     short loc_14007B6A3
0x14007b6b5  mov     r8d, 8; Size
0x14007b6bb  mov     rdx, rbx; Count
0x14007b6be  mov     rcx, r14; Block
0x14007b6c1  call    _recalloc_base
0x14007b6c6  xor     ecx, ecx; Block
0x14007b6c8  mov     rbx, rax
0x14007b6cb  call    _free_base
0x14007b6d0  test    rbx, rbx
0x14007b6d3  jz      short loc_14007B742
0x14007b6d5  mov     cs:Block, rbx
0x14007b6dc  jmp     short loc_14007B742
0x14007b6de  test    r12w, r12w
0x14007b6e2  jnz     short loc_14007B6EB
0x14007b6e4  mov     ebp, esi
0x14007b6e6  jmp     loc_14007B588
0x14007b6eb  neg     rbx
0x14007b6ee  lea     rdx, [rbx+2]; Count
0x14007b6f2  cmp     rdx, rbx
0x14007b6f5  jb      loc_14007B584
0x14007b6fb  mov     rax, 1FFFFFFFFFFFFFFFh
0x14007b705  cmp     rdx, rax
0x14007b708  jnb     loc_14007B584
0x14007b70e  mov     r8d, 8; Size
0x14007b714  mov     rcx, r14; Block
0x14007b717  call    _recalloc_base
0x14007b71c  xor     ecx, ecx; Block
0x14007b71e  mov     r14, rax
0x14007b721  call    _free_base
0x14007b726  test    r14, r14
0x14007b729  jz      loc_14007B584
0x14007b72f  mov     [r14+rbx*8], r15
0x14007b733  mov     [r14+rbx*8+8], rsi
0x14007b738  mov     cs:Block, r14
0x14007b73f  mov     rdi, rsi
0x14007b742  test    ebp, ebp
0x14007b744  jz      loc_14007B7DF
0x14007b74a  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14007b74e  mov     r14, rbp
0x14007b751  inc     r14
0x14007b754  cmp     [r15+r14*2], si
0x14007b759  jnz     short loc_14007B751
0x14007b75b  mov     edx, 2; Size
0x14007b760  add     r14, rdx
0x14007b763  mov     rcx, r14; Count
0x14007b766  call    _calloc_base
0x14007b76b  mov     rbx, rax
0x14007b76e  test    rax, rax
0x14007b771  jnz     short loc_14007B77C
0x14007b773  xor     ecx, ecx; Block
0x14007b775  call    _free_base
0x14007b77a  jmp     short loc_14007B7CB
0x14007b77c  mov     r8, r15
0x14007b77f  mov     rdx, r14
0x14007b782  mov     rcx, rbx
0x14007b785  call    sub_14006C410
0x14007b78a  test    eax, eax
0x14007b78c  jnz     loc_14007B81F
0x14007b792  neg     r12w
0x14007b796  mov     [rbx+r13*2], si
0x14007b79b  lea     rax, [r13+1]
0x14007b79f  mov     rcx, rbx; lpName
0x14007b7a2  sbb     rdx, rdx
0x14007b7a5  lea     rax, [rbx+rax*2]
0x14007b7a9  and     rdx, rax; lpValue
0x14007b7ac  call    cs:SetEnvironmentVariableW
0x14007b7b2  test    eax, eax
0x14007b7b4  jnz     short loc_14007B7D7
0x14007b7b6  call    sub_1400616B4
0x14007b7bb  mov     rcx, rbx; Block
0x14007b7be  mov     dword ptr [rax], 2Ah ; '*'
0x14007b7c4  call    _free_base
0x14007b7c9  mov     esi, ebp
0x14007b7cb  mov     rcx, rdi; Block
0x14007b7ce  call    _free_base
0x14007b7d3  mov     eax, esi
0x14007b7d5  jmp     short loc_14007B802
0x14007b7d7  mov     rcx, rbx; Block
0x14007b7da  call    _free_base
0x14007b7df  mov     rcx, rdi; Block
0x14007b7e2  call    _free_base
0x14007b7e7  xor     eax, eax
0x14007b7e9  jmp     short loc_14007B802
0x14007b7eb  call    sub_1400616B4
0x14007b7f0  mov     rcx, r15; Block
0x14007b7f3  mov     dword ptr [rax], 16h
0x14007b7f9  call    _free_base
0x14007b7fe  or      rax, 0FFFFFFFFFFFFFFFFh
0x14007b802  mov     rbx, [rsp+58h+arg_0]
0x14007b807  mov     rbp, [rsp+58h+arg_8]
0x14007b80c  mov     rsi, [rsp+58h+arg_10]
0x14007b811  add     rsp, 30h
0x14007b815  pop     r15
0x14007b817  pop     r14
0x14007b819  pop     r13
0x14007b81b  pop     r12
0x14007b81d  pop     rdi
0x14007b81e  retn
0x14007b81f  xor     r9d, r9d; LineNo
0x14007b822  mov     [rsp+58h+Reserved], rsi; Reserved
0x14007b827  xor     r8d, r8d; FileName
0x14007b82a  xor     edx, edx; FunctionName
0x14007b82c  xor     ecx, ecx; Expression
0x14007b82e  call    _invoke_watson
```
