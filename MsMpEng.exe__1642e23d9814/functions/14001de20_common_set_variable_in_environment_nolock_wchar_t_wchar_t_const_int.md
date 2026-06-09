# common_set_variable_in_environment_nolock<wchar_t>(wchar_t * const,int)

- ea: `0x14001de20`
- end: `0x14001e183`
- name: `??$common_set_variable_in_environment_nolock@_W@@YAHQEA_WH@Z`
- size: `867`
- prototype: `__int64 __fastcall(_WORD *Block, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14001e274`

## callees

- `0x14000bf74`
- `0x1400160bc`
- `0x140016ea0`
- `0x14001834c`
- `0x140019930`
- `0x14001b910`
- `0x14001d490`
- `0x14001de20`
- `0x14001e184`
- `0x14001ef20`
- `0x140022f30`

## import_xrefs

- `KERNEL32!SetEnvironmentVariableW` at `0x14001e0fc`
- `KERNEL32!SetEnvironmentVariableW` at `0x14001e0fc`

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
    v6 = (_WORD *)sub_14000BF74(Block, 61);
    v7 = v6;
    if ( !v6 || v6 == Block )
    {
      *(_DWORD *)sub_140016EA0() = 22;
      free_base(Block);
      return -1;
    }
    v8 = (__int64 *)qword_14003E4F8;
    v9 = v6[1];
    if ( qword_14003E4F8 == qword_14003E500 )
    {
      v8 = (__int64 *)copy_environment<wchar_t>(qword_14003E4F8);
      qword_14003E4F8 = v8;
    }
    if ( !v8 )
    {
      if ( a2 && qword_14003E4F0 )
      {
        if ( !unknown_libname_44() )
        {
          *(_DWORD *)sub_140016EA0() = 22;
LABEL_12:
          v10 = -1;
LABEL_13:
          free_base(Block);
          return v10;
        }
        v8 = (__int64 *)qword_14003E4F8;
        if ( qword_14003E4F8 == qword_14003E500 )
        {
          v8 = (__int64 *)copy_environment<wchar_t>(qword_14003E4F8);
          qword_14003E4F8 = v8;
        }
        goto LABEL_21;
      }
      if ( !v9 )
        goto LABEL_39;
      if ( qword_14003E4F0 )
        goto LABEL_20;
      qword_14003E4F0 = (__int64)calloc_base(1u, 8u);
      free_base(0);
      if ( !qword_14003E4F0 )
        goto LABEL_12;
      v8 = (__int64 *)qword_14003E4F8;
      if ( !qword_14003E4F8 )
      {
LABEL_20:
        qword_14003E4F8 = calloc_base(1u, 8u);
        free_base(0);
        v8 = (__int64 *)qword_14003E4F8;
        if ( !qword_14003E4F8 )
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
      if ( !(unsigned int)sub_140022F30(Block, v12, v13)
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
          qword_14003E4F8 = v16;
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
          if ( (unsigned int)sub_14001D490(v22, v21, Block) )
            invoke_watson(0, 0, 0, 0, 0);
          v23[v13] = 0;
          if ( !SetEnvironmentVariableW(v23, (LPCWSTR)((unsigned __int64)&v23[v13 + 1] & -(__int64)(v9 != 0))) )
          {
            *(_DWORD *)sub_140016EA0() = 42;
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
      qword_14003E4F8 = v19;
      goto LABEL_44;
    }
LABEL_39:
    v10 = 0;
    goto LABEL_13;
  }
  *(_DWORD *)sub_140016EA0() = 22;
  return -1;
}

```

## disassembly

```asm
0x14001de20  mov     [rsp+arg_0], rbx
0x14001de25  mov     [rsp+arg_8], rbp
0x14001de2a  mov     [rsp+arg_10], rsi
0x14001de2f  push    rdi
0x14001de30  push    r12
0x14001de32  push    r13
0x14001de34  push    r14
0x14001de36  push    r15
0x14001de38  sub     rsp, 30h
0x14001de3c  xor     esi, esi
0x14001de3e  mov     ebp, edx
0x14001de40  mov     r15, rcx
0x14001de43  test    rcx, rcx
0x14001de46  jnz     short loc_14001DE58
0x14001de48  call    sub_140016EA0
0x14001de4d  mov     dword ptr [rax], 16h
0x14001de53  jmp     loc_14001E14E
0x14001de58  mov     edx, 3Dh ; '='
0x14001de5d  mov     rdi, r15
0x14001de60  call    sub_14000BF74
0x14001de65  mov     r13, rax
0x14001de68  test    rax, rax
0x14001de6b  jz      loc_14001E13B
0x14001de71  cmp     rax, r15
0x14001de74  jz      loc_14001E13B
0x14001de7a  mov     r14, cs:qword_14003E4F8
0x14001de81  cmp     r14, cs:qword_14003E500
0x14001de88  movzx   r12d, word ptr [rax+2]
0x14001de8d  jnz     short loc_14001DEA1
0x14001de8f  mov     rcx, r14
0x14001de92  call    ??$copy_environment@_W@@YAPEAPEA_WQEAPEA_W@Z
0x14001de97  mov     r14, rax
0x14001de9a  mov     cs:qword_14003E4F8, rax
0x14001dea1  mov     ebx, 1
0x14001dea6  test    r14, r14
0x14001dea9  jnz     loc_14001DF7C
0x14001deaf  mov     rax, cs:qword_14003E4F0
0x14001deb6  test    ebp, ebp
0x14001deb8  jz      short loc_14001DF0B
0x14001deba  test    rax, rax
0x14001debd  jz      short loc_14001DF0B
0x14001debf  call    unknown_libname_44; Microsoft VisualC 64bit universal runtime
0x14001dec4  test    rax, rax
0x14001dec7  jnz     short loc_14001DEE7
0x14001dec9  call    sub_140016EA0
0x14001dece  mov     dword ptr [rax], 16h
0x14001ded4  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14001ded8  mov     rcx, r15; Block
0x14001dedb  call    _free_base
0x14001dee0  mov     eax, ebp
0x14001dee2  jmp     loc_14001E152
0x14001dee7  mov     r14, cs:qword_14003E4F8
0x14001deee  cmp     r14, cs:qword_14003E500
0x14001def5  jnz     short loc_14001DF73
0x14001def7  mov     rcx, r14
0x14001defa  call    ??$copy_environment@_W@@YAPEAPEA_WQEAPEA_W@Z
0x14001deff  mov     r14, rax
0x14001df02  mov     cs:qword_14003E4F8, rax
0x14001df09  jmp     short loc_14001DF73
0x14001df0b  test    r12w, r12w
0x14001df0f  jz      loc_14001E034
0x14001df15  test    rax, rax
0x14001df18  jnz     short loc_14001DF48
0x14001df1a  lea     edx, [rax+8]; Size
0x14001df1d  mov     rcx, rbx; Count
0x14001df20  call    _calloc_base
0x14001df25  xor     ecx, ecx; Block
0x14001df27  mov     cs:qword_14003E4F0, rax
0x14001df2e  call    _free_base
0x14001df33  cmp     cs:qword_14003E4F0, rsi
0x14001df3a  jz      short loc_14001DED4
0x14001df3c  mov     r14, cs:qword_14003E4F8
0x14001df43  test    r14, r14
0x14001df46  jnz     short loc_14001DF7C
0x14001df48  mov     edx, 8; Size
0x14001df4d  mov     rcx, rbx; Count
0x14001df50  call    _calloc_base
0x14001df55  xor     ecx, ecx; Block
0x14001df57  mov     cs:qword_14003E4F8, rax
0x14001df5e  call    _free_base
0x14001df63  mov     r14, cs:qword_14003E4F8
0x14001df6a  test    r14, r14
0x14001df6d  jz      loc_14001DED4
0x14001df73  test    r14, r14
0x14001df76  jz      loc_14001DED4
0x14001df7c  mov     rax, [r14]
0x14001df7f  sub     r13, r15
0x14001df82  sar     r13, 1
0x14001df85  mov     rbx, r14
0x14001df88  jmp     short loc_14001DFB9
0x14001df8a  mov     r8, r13
0x14001df8d  mov     rdx, rax
0x14001df90  mov     rcx, r15
0x14001df93  call    sub_140022F30
0x14001df98  test    eax, eax
0x14001df9a  jnz     short loc_14001DFB2
0x14001df9c  mov     rax, [rbx]
0x14001df9f  mov     ecx, 3Dh ; '='
0x14001dfa4  cmp     [rax+r13*2], cx
0x14001dfa9  jz      short loc_14001DFEA
0x14001dfab  cmp     [rax+r13*2], si
0x14001dfb0  jz      short loc_14001DFEA
0x14001dfb2  add     rbx, 8
0x14001dfb6  mov     rax, [rbx]
0x14001dfb9  test    rax, rax
0x14001dfbc  jnz     short loc_14001DF8A
0x14001dfbe  sub     rbx, r14
0x14001dfc1  sar     rbx, 3
0x14001dfc5  neg     rbx
0x14001dfc8  test    rbx, rbx
0x14001dfcb  js      short loc_14001E02E
0x14001dfcd  cmp     [r14], rsi
0x14001dfd0  jz      short loc_14001E02E
0x14001dfd2  mov     rcx, [r14+rbx*8]; Block
0x14001dfd6  call    _free_base
0x14001dfdb  test    r12w, r12w
0x14001dfdf  jz      short loc_14001DFFF
0x14001dfe1  mov     [r14+rbx*8], r15
0x14001dfe5  jmp     loc_14001E08F
0x14001dfea  sub     rbx, r14
0x14001dfed  sar     rbx, 3
0x14001dff1  jmp     short loc_14001DFC8
0x14001dff3  mov     rax, [r14+rbx*8+8]
0x14001dff8  mov     [r14+rbx*8], rax
0x14001dffc  inc     rbx
0x14001dfff  cmp     [r14+rbx*8], rsi
0x14001e003  jnz     short loc_14001DFF3
0x14001e005  mov     r8d, 8; Size
0x14001e00b  mov     rdx, rbx; Count
0x14001e00e  mov     rcx, r14; Block
0x14001e011  call    _recalloc_base
0x14001e016  xor     ecx, ecx; Block
0x14001e018  mov     rbx, rax
0x14001e01b  call    _free_base
0x14001e020  test    rbx, rbx
0x14001e023  jz      short loc_14001E092
0x14001e025  mov     cs:qword_14003E4F8, rbx
0x14001e02c  jmp     short loc_14001E092
0x14001e02e  test    r12w, r12w
0x14001e032  jnz     short loc_14001E03B
0x14001e034  mov     ebp, esi
0x14001e036  jmp     loc_14001DED8
0x14001e03b  neg     rbx
0x14001e03e  lea     rdx, [rbx+2]; Count
0x14001e042  cmp     rdx, rbx
0x14001e045  jb      loc_14001DED4
0x14001e04b  mov     rax, 1FFFFFFFFFFFFFFFh
0x14001e055  cmp     rdx, rax
0x14001e058  jnb     loc_14001DED4
0x14001e05e  mov     r8d, 8; Size
0x14001e064  mov     rcx, r14; Block
0x14001e067  call    _recalloc_base
0x14001e06c  xor     ecx, ecx; Block
0x14001e06e  mov     r14, rax
0x14001e071  call    _free_base
0x14001e076  test    r14, r14
0x14001e079  jz      loc_14001DED4
0x14001e07f  mov     [r14+rbx*8], r15
0x14001e083  mov     [r14+rbx*8+8], rsi
0x14001e088  mov     cs:qword_14003E4F8, r14
0x14001e08f  mov     rdi, rsi
0x14001e092  test    ebp, ebp
0x14001e094  jz      loc_14001E12F
0x14001e09a  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14001e09e  mov     r14, rbp
0x14001e0a1  inc     r14
0x14001e0a4  cmp     [r15+r14*2], si
0x14001e0a9  jnz     short loc_14001E0A1
0x14001e0ab  mov     edx, 2; Size
0x14001e0b0  add     r14, rdx
0x14001e0b3  mov     rcx, r14; Count
0x14001e0b6  call    _calloc_base
0x14001e0bb  mov     rbx, rax
0x14001e0be  test    rax, rax
0x14001e0c1  jnz     short loc_14001E0CC
0x14001e0c3  xor     ecx, ecx; Block
0x14001e0c5  call    _free_base
0x14001e0ca  jmp     short loc_14001E11B
0x14001e0cc  mov     r8, r15
0x14001e0cf  mov     rdx, r14
0x14001e0d2  mov     rcx, rbx
0x14001e0d5  call    sub_14001D490
0x14001e0da  test    eax, eax
0x14001e0dc  jnz     loc_14001E16F
0x14001e0e2  neg     r12w
0x14001e0e6  mov     [rbx+r13*2], si
0x14001e0eb  lea     rax, [r13+1]
0x14001e0ef  mov     rcx, rbx; lpName
0x14001e0f2  sbb     rdx, rdx
0x14001e0f5  lea     rax, [rbx+rax*2]
0x14001e0f9  and     rdx, rax; lpValue
0x14001e0fc  call    cs:SetEnvironmentVariableW
0x14001e102  test    eax, eax
0x14001e104  jnz     short loc_14001E127
0x14001e106  call    sub_140016EA0
0x14001e10b  mov     rcx, rbx; Block
0x14001e10e  mov     dword ptr [rax], 2Ah ; '*'
0x14001e114  call    _free_base
0x14001e119  mov     esi, ebp
0x14001e11b  mov     rcx, rdi; Block
0x14001e11e  call    _free_base
0x14001e123  mov     eax, esi
0x14001e125  jmp     short loc_14001E152
0x14001e127  mov     rcx, rbx; Block
0x14001e12a  call    _free_base
0x14001e12f  mov     rcx, rdi; Block
0x14001e132  call    _free_base
0x14001e137  xor     eax, eax
0x14001e139  jmp     short loc_14001E152
0x14001e13b  call    sub_140016EA0
0x14001e140  mov     rcx, r15; Block
0x14001e143  mov     dword ptr [rax], 16h
0x14001e149  call    _free_base
0x14001e14e  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001e152  mov     rbx, [rsp+58h+arg_0]
0x14001e157  mov     rbp, [rsp+58h+arg_8]
0x14001e15c  mov     rsi, [rsp+58h+arg_10]
0x14001e161  add     rsp, 30h
0x14001e165  pop     r15
0x14001e167  pop     r14
0x14001e169  pop     r13
0x14001e16b  pop     r12
0x14001e16d  pop     rdi
0x14001e16e  retn
0x14001e16f  xor     r9d, r9d; LineNo
0x14001e172  mov     [rsp+58h+Reserved], rsi; Reserved
0x14001e177  xor     r8d, r8d; FileName
0x14001e17a  xor     edx, edx; FunctionName
0x14001e17c  xor     ecx, ecx; Expression
0x14001e17e  call    _invoke_watson
```
