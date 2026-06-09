# common_set_variable_in_environment_nolock<wchar_t>(wchar_t * const,int)

- ea: `0x140007d40`
- end: `0x1400080a3`
- name: `??$common_set_variable_in_environment_nolock@_W@@YAHQEA_WH@Z`
- size: `867`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140008194`

## callees

- `0x140004d8c`
- `0x140006564`
- `0x1400065b0`
- `0x14000689c`
- `0x1400068c0`
- `0x140006940`
- `0x140007d40`
- `0x1400080a4`
- `0x140009920`
- `0x14000b1e0`
- `0x14000cf1c`

## import_xrefs

- `KERNEL32!SetEnvironmentVariableW` at `0x14000801c`
- `KERNEL32!SetEnvironmentVariableW` at `0x14000801c`

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
    v6 = (_WORD *)sub_14000CF1C(Block, 61);
    v7 = v6;
    if ( !v6 || v6 == Block )
    {
      *(_DWORD *)sub_14000689C() = 22;
      free_base(Block);
      return -1;
    }
    v8 = (__int64 *)qword_14001A418;
    v9 = v6[1];
    if ( qword_14001A418 == qword_14001A420 )
    {
      v8 = (__int64 *)copy_environment<wchar_t>(qword_14001A418);
      qword_14001A418 = v8;
    }
    if ( !v8 )
    {
      if ( a2 && qword_14001A410 )
      {
        if ( !unknown_libname_12() )
        {
          *(_DWORD *)sub_14000689C() = 22;
LABEL_12:
          v10 = -1;
LABEL_13:
          free_base(Block);
          return v10;
        }
        v8 = (__int64 *)qword_14001A418;
        if ( qword_14001A418 == qword_14001A420 )
        {
          v8 = (__int64 *)copy_environment<wchar_t>(qword_14001A418);
          qword_14001A418 = v8;
        }
        goto LABEL_21;
      }
      if ( !v9 )
        goto LABEL_39;
      if ( qword_14001A410 )
        goto LABEL_20;
      qword_14001A410 = (__int64)calloc_base(1u, 8u);
      free_base(0);
      if ( !qword_14001A410 )
        goto LABEL_12;
      v8 = (__int64 *)qword_14001A418;
      if ( !qword_14001A418 )
      {
LABEL_20:
        qword_14001A418 = calloc_base(1u, 8u);
        free_base(0);
        v8 = (__int64 *)qword_14001A418;
        if ( !qword_14001A418 )
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
      if ( !(unsigned int)sub_14000B1E0(Block, v12, v13)
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
          qword_14001A418 = v16;
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
          if ( (unsigned int)sub_1400065B0(v22, v21, Block) )
            invoke_watson(0, 0, 0, 0, 0);
          v23[v13] = 0;
          if ( !SetEnvironmentVariableW(v23, (LPCWSTR)((unsigned __int64)&v23[v13 + 1] & -(__int64)(v9 != 0))) )
          {
            *(_DWORD *)sub_14000689C() = 42;
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
      qword_14001A418 = v19;
      goto LABEL_44;
    }
LABEL_39:
    v10 = 0;
    goto LABEL_13;
  }
  *(_DWORD *)sub_14000689C() = 22;
  return -1;
}

```

## disassembly

```asm
0x140007d40  mov     [rsp+arg_0], rbx
0x140007d45  mov     [rsp+arg_8], rbp
0x140007d4a  mov     [rsp+arg_10], rsi
0x140007d4f  push    rdi
0x140007d50  push    r12
0x140007d52  push    r13
0x140007d54  push    r14
0x140007d56  push    r15
0x140007d58  sub     rsp, 30h
0x140007d5c  xor     esi, esi
0x140007d5e  mov     ebp, edx
0x140007d60  mov     r15, rcx
0x140007d63  test    rcx, rcx
0x140007d66  jnz     short loc_140007D78
0x140007d68  call    sub_14000689C
0x140007d6d  mov     dword ptr [rax], 16h
0x140007d73  jmp     loc_14000806E
0x140007d78  mov     edx, 3Dh ; '='
0x140007d7d  mov     rdi, r15
0x140007d80  call    sub_14000CF1C
0x140007d85  mov     r13, rax
0x140007d88  test    rax, rax
0x140007d8b  jz      loc_14000805B
0x140007d91  cmp     rax, r15
0x140007d94  jz      loc_14000805B
0x140007d9a  mov     r14, cs:qword_14001A418
0x140007da1  cmp     r14, cs:qword_14001A420
0x140007da8  movzx   r12d, word ptr [rax+2]
0x140007dad  jnz     short loc_140007DC1
0x140007daf  mov     rcx, r14
0x140007db2  call    ??$copy_environment@_W@@YAPEAPEA_WQEAPEA_W@Z
0x140007db7  mov     r14, rax
0x140007dba  mov     cs:qword_14001A418, rax
0x140007dc1  mov     ebx, 1
0x140007dc6  test    r14, r14
0x140007dc9  jnz     loc_140007E9C
0x140007dcf  mov     rax, cs:qword_14001A410
0x140007dd6  test    ebp, ebp
0x140007dd8  jz      short loc_140007E2B
0x140007dda  test    rax, rax
0x140007ddd  jz      short loc_140007E2B
0x140007ddf  call    unknown_libname_12; Microsoft VisualC 64bit universal runtime
0x140007de4  test    rax, rax
0x140007de7  jnz     short loc_140007E07
0x140007de9  call    sub_14000689C
0x140007dee  mov     dword ptr [rax], 16h
0x140007df4  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140007df8  mov     rcx, r15; Block
0x140007dfb  call    _free_base
0x140007e00  mov     eax, ebp
0x140007e02  jmp     loc_140008072
0x140007e07  mov     r14, cs:qword_14001A418
0x140007e0e  cmp     r14, cs:qword_14001A420
0x140007e15  jnz     short loc_140007E93
0x140007e17  mov     rcx, r14
0x140007e1a  call    ??$copy_environment@_W@@YAPEAPEA_WQEAPEA_W@Z
0x140007e1f  mov     r14, rax
0x140007e22  mov     cs:qword_14001A418, rax
0x140007e29  jmp     short loc_140007E93
0x140007e2b  test    r12w, r12w
0x140007e2f  jz      loc_140007F54
0x140007e35  test    rax, rax
0x140007e38  jnz     short loc_140007E68
0x140007e3a  lea     edx, [rax+8]; Size
0x140007e3d  mov     rcx, rbx; Count
0x140007e40  call    _calloc_base
0x140007e45  xor     ecx, ecx; Block
0x140007e47  mov     cs:qword_14001A410, rax
0x140007e4e  call    _free_base
0x140007e53  cmp     cs:qword_14001A410, rsi
0x140007e5a  jz      short loc_140007DF4
0x140007e5c  mov     r14, cs:qword_14001A418
0x140007e63  test    r14, r14
0x140007e66  jnz     short loc_140007E9C
0x140007e68  mov     edx, 8; Size
0x140007e6d  mov     rcx, rbx; Count
0x140007e70  call    _calloc_base
0x140007e75  xor     ecx, ecx; Block
0x140007e77  mov     cs:qword_14001A418, rax
0x140007e7e  call    _free_base
0x140007e83  mov     r14, cs:qword_14001A418
0x140007e8a  test    r14, r14
0x140007e8d  jz      loc_140007DF4
0x140007e93  test    r14, r14
0x140007e96  jz      loc_140007DF4
0x140007e9c  mov     rax, [r14]
0x140007e9f  sub     r13, r15
0x140007ea2  sar     r13, 1
0x140007ea5  mov     rbx, r14
0x140007ea8  jmp     short loc_140007ED9
0x140007eaa  mov     r8, r13
0x140007ead  mov     rdx, rax
0x140007eb0  mov     rcx, r15
0x140007eb3  call    sub_14000B1E0
0x140007eb8  test    eax, eax
0x140007eba  jnz     short loc_140007ED2
0x140007ebc  mov     rax, [rbx]
0x140007ebf  mov     ecx, 3Dh ; '='
0x140007ec4  cmp     [rax+r13*2], cx
0x140007ec9  jz      short loc_140007F0A
0x140007ecb  cmp     [rax+r13*2], si
0x140007ed0  jz      short loc_140007F0A
0x140007ed2  add     rbx, 8
0x140007ed6  mov     rax, [rbx]
0x140007ed9  test    rax, rax
0x140007edc  jnz     short loc_140007EAA
0x140007ede  sub     rbx, r14
0x140007ee1  sar     rbx, 3
0x140007ee5  neg     rbx
0x140007ee8  test    rbx, rbx
0x140007eeb  js      short loc_140007F4E
0x140007eed  cmp     [r14], rsi
0x140007ef0  jz      short loc_140007F4E
0x140007ef2  mov     rcx, [r14+rbx*8]; Block
0x140007ef6  call    _free_base
0x140007efb  test    r12w, r12w
0x140007eff  jz      short loc_140007F1F
0x140007f01  mov     [r14+rbx*8], r15
0x140007f05  jmp     loc_140007FAF
0x140007f0a  sub     rbx, r14
0x140007f0d  sar     rbx, 3
0x140007f11  jmp     short loc_140007EE8
0x140007f13  mov     rax, [r14+rbx*8+8]
0x140007f18  mov     [r14+rbx*8], rax
0x140007f1c  inc     rbx
0x140007f1f  cmp     [r14+rbx*8], rsi
0x140007f23  jnz     short loc_140007F13
0x140007f25  mov     r8d, 8; Size
0x140007f2b  mov     rdx, rbx; Count
0x140007f2e  mov     rcx, r14; Block
0x140007f31  call    _recalloc_base
0x140007f36  xor     ecx, ecx; Block
0x140007f38  mov     rbx, rax
0x140007f3b  call    _free_base
0x140007f40  test    rbx, rbx
0x140007f43  jz      short loc_140007FB2
0x140007f45  mov     cs:qword_14001A418, rbx
0x140007f4c  jmp     short loc_140007FB2
0x140007f4e  test    r12w, r12w
0x140007f52  jnz     short loc_140007F5B
0x140007f54  mov     ebp, esi
0x140007f56  jmp     loc_140007DF8
0x140007f5b  neg     rbx
0x140007f5e  lea     rdx, [rbx+2]; Count
0x140007f62  cmp     rdx, rbx
0x140007f65  jb      loc_140007DF4
0x140007f6b  mov     rax, 1FFFFFFFFFFFFFFFh
0x140007f75  cmp     rdx, rax
0x140007f78  jnb     loc_140007DF4
0x140007f7e  mov     r8d, 8; Size
0x140007f84  mov     rcx, r14; Block
0x140007f87  call    _recalloc_base
0x140007f8c  xor     ecx, ecx; Block
0x140007f8e  mov     r14, rax
0x140007f91  call    _free_base
0x140007f96  test    r14, r14
0x140007f99  jz      loc_140007DF4
0x140007f9f  mov     [r14+rbx*8], r15
0x140007fa3  mov     [r14+rbx*8+8], rsi
0x140007fa8  mov     cs:qword_14001A418, r14
0x140007faf  mov     rdi, rsi
0x140007fb2  test    ebp, ebp
0x140007fb4  jz      loc_14000804F
0x140007fba  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140007fbe  mov     r14, rbp
0x140007fc1  inc     r14
0x140007fc4  cmp     [r15+r14*2], si
0x140007fc9  jnz     short loc_140007FC1
0x140007fcb  mov     edx, 2; Size
0x140007fd0  add     r14, rdx
0x140007fd3  mov     rcx, r14; Count
0x140007fd6  call    _calloc_base
0x140007fdb  mov     rbx, rax
0x140007fde  test    rax, rax
0x140007fe1  jnz     short loc_140007FEC
0x140007fe3  xor     ecx, ecx; Block
0x140007fe5  call    _free_base
0x140007fea  jmp     short loc_14000803B
0x140007fec  mov     r8, r15
0x140007fef  mov     rdx, r14
0x140007ff2  mov     rcx, rbx
0x140007ff5  call    sub_1400065B0
0x140007ffa  test    eax, eax
0x140007ffc  jnz     loc_14000808F
0x140008002  neg     r12w
0x140008006  mov     [rbx+r13*2], si
0x14000800b  lea     rax, [r13+1]
0x14000800f  mov     rcx, rbx; lpName
0x140008012  sbb     rdx, rdx
0x140008015  lea     rax, [rbx+rax*2]
0x140008019  and     rdx, rax; lpValue
0x14000801c  call    cs:SetEnvironmentVariableW
0x140008022  test    eax, eax
0x140008024  jnz     short loc_140008047
0x140008026  call    sub_14000689C
0x14000802b  mov     rcx, rbx; Block
0x14000802e  mov     dword ptr [rax], 2Ah ; '*'
0x140008034  call    _free_base
0x140008039  mov     esi, ebp
0x14000803b  mov     rcx, rdi; Block
0x14000803e  call    _free_base
0x140008043  mov     eax, esi
0x140008045  jmp     short loc_140008072
0x140008047  mov     rcx, rbx; Block
0x14000804a  call    _free_base
0x14000804f  mov     rcx, rdi; Block
0x140008052  call    _free_base
0x140008057  xor     eax, eax
0x140008059  jmp     short loc_140008072
0x14000805b  call    sub_14000689C
0x140008060  mov     rcx, r15; Block
0x140008063  mov     dword ptr [rax], 16h
0x140008069  call    _free_base
0x14000806e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140008072  mov     rbx, [rsp+58h+arg_0]
0x140008077  mov     rbp, [rsp+58h+arg_8]
0x14000807c  mov     rsi, [rsp+58h+arg_10]
0x140008081  add     rsp, 30h
0x140008085  pop     r15
0x140008087  pop     r14
0x140008089  pop     r13
0x14000808b  pop     r12
0x14000808d  pop     rdi
0x14000808e  retn
0x14000808f  xor     r9d, r9d; LineNo
0x140008092  mov     [rsp+58h+Reserved], rsi; Reserved
0x140008097  xor     r8d, r8d; FileName
0x14000809a  xor     edx, edx; FunctionName
0x14000809c  xor     ecx, ecx; Expression
0x14000809e  call    _invoke_watson
```
