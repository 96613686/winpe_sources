# StateRepository::DataType::ProgId::GenerateACID(ushort const *,ushort const *,ushort const *,ushort const *,StateRepository::RuntimeBehavior,StateRepository::SRTrustLevel,ushort const *,ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &)

- ea: `0x1800209b0`
- end: `0x180020c1a`
- name: `?GenerateACID@ProgId@DataType@StateRepository@@YAJPEBG000W4RuntimeBehavior@3@W4SRTrustLevel@3@00AEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@Z`
- size: `618`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180021294`

## callees

- `0x1800041cc`
- `0x18000a3c0`
- `0x18000a7c0`
- `0x180014ca0`
- `0x180020714`
- `0x1800209b0`
- `0x180020c78`

## string_xrefs

- `0x1800209e3`: `onecore\base\appmodel\staterepository\dataaccesslayer\datatype-progid.cpp`
- `0x180020b00`: `onecore\base\appmodel\staterepository\dataaccesslayer\datatype-progid.cpp`
- `0x180020b72`: `onecore\base\appmodel\staterepository\dataaccesslayer\datatype-progid.cpp`
- `0x180020bc9`: `onecore\base\appmodel\staterepository\dataaccesslayer\datatype-progid.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::DataType::ProgId::GenerateACID(
        unsigned __int16 *a1,
        _WORD *a2,
        _WORD *a3,
        __int64 a4,
        int a5,
        int a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        void **a9)
{
  __int64 v11; // rdx
  unsigned int v12; // ebx
  __int64 v14; // rbx
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // rax
  int v17; // eax
  unsigned int v18; // edi
  __int64 v19; // rax
  __int64 v20; // rcx
  void *v21; // rdi
  __int64 v22; // r14
  void *v23; // rbx
  int v24; // eax
  void *v25; // rcx
  int v26; // [rsp+20h] [rbp-20h]
  int v27; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  void *Block; // [rsp+70h] [rbp+30h] BYREF

  if ( !a1 )
  {
    v11 = 266;
LABEL_3:
    v12 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\datatype-progid.cpp",
      (const char *)0x80070057LL,
      v26);
    return v12;
  }
  if ( !*a1 )
  {
    v11 = 267;
    goto LABEL_3;
  }
  v14 = -1;
  v15 = -1;
  do
    ++v15;
  while ( a1[v15] );
  if ( v15 > 0x40 )
  {
    v11 = 269;
    goto LABEL_3;
  }
  if ( v15 < 0x11 )
  {
    v11 = 270;
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v11 = 271;
    goto LABEL_3;
  }
  if ( !*a2 )
  {
    v11 = 272;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v11 = 273;
    goto LABEL_3;
  }
  if ( !*a3 )
  {
    v11 = 274;
    goto LABEL_3;
  }
  v16 = -1;
  do
    ++v16;
  while ( a3[v16] );
  if ( v16 > 0x40 )
  {
    v11 = 276;
    goto LABEL_3;
  }
  if ( !v16 )
  {
    v11 = 277;
    goto LABEL_3;
  }
  if ( !a7 )
  {
    v11 = 278;
    goto LABEL_3;
  }
  if ( !*a7 )
  {
    v11 = 279;
    goto LABEL_3;
  }
  if ( a4 )
  {
    a5 = 0;
    a6 = 0;
  }
  Block = 0;
  v17 = StateRepository::DataType::ProgId::GenerateProgId(a1, a3, &a5, &a6, a7, a8, &Block);
  v18 = v17;
  if ( v17 >= 0 )
  {
    v19 = -1;
    do
      ++v19;
    while ( a3[v19] );
    v20 = -1;
    do
      ++v20;
    while ( a2[v20] );
    v21 = Block;
    do
      ++v14;
    while ( *((_WORD *)Block + v14) );
    v22 = v14 + v20 + v19;
    wil::make_unique_nothrow<unsigned short [0]>(&Block, v22 + 2);
    v23 = Block;
    if ( !Block )
    {
      v12 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x126,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\datatype-progid.cpp",
        (const char *)0x8007000ELL,
        v27);
      if ( v21 )
        operator delete(v21);
      return v12;
    }
    v24 = StringCchPrintfW((unsigned __int16 *)Block, v22 + 2, L"%s.%s%s", a3);
    if ( v24 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x128,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\datatype-progid.cpp",
        (const char *)(unsigned int)v24,
        (int)v21);
    v25 = *a9;
    *a9 = v23;
    if ( v25 )
      operator delete(v25);
    if ( v21 )
      operator delete(v21);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x122,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\datatype-progid.cpp",
      (const char *)(unsigned int)v17,
      v27);
    if ( Block )
      operator delete(Block);
    return v18;
  }
}

```

## disassembly

```asm
0x1800209b0  mov     [rsp-28h+arg_8], rbx
0x1800209b5  mov     [rsp-28h+arg_10], rsi
0x1800209ba  push    rbp
0x1800209bb  push    rdi
0x1800209bc  push    r12
0x1800209be  push    r14
0x1800209c0  push    r15
0x1800209c2  mov     rbp, rsp
0x1800209c5  sub     rsp, 40h
0x1800209c9  xor     r12d, r12d
0x1800209cc  mov     rsi, r8
0x1800209cf  mov     r15, rdx
0x1800209d2  mov     r10, rcx
0x1800209d5  test    rcx, rcx
0x1800209d8  jnz     short loc_1800209FE
0x1800209da  mov     edx, 10Ah; void *
0x1800209df  mov     rcx, [rbp+28h]; this
0x1800209e3  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x1800209ea  mov     ebx, 80070057h
0x1800209ef  mov     r9d, ebx; char *
0x1800209f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800209f7  mov     eax, ebx
0x1800209f9  jmp     loc_180020C01
0x1800209fe  cmp     [rcx], r12w
0x180020a02  jnz     short loc_180020A0B
0x180020a04  mov     edx, 10Bh
0x180020a09  jmp     short loc_1800209DF
0x180020a0b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180020a0f  mov     rax, rbx
0x180020a12  inc     rax
0x180020a15  cmp     [rcx+rax*2], r12w
0x180020a1a  jnz     short loc_180020A12
0x180020a1c  cmp     rax, 40h ; '@'
0x180020a20  jbe     short loc_180020A29
0x180020a22  mov     edx, 10Dh
0x180020a27  jmp     short loc_1800209DF
0x180020a29  cmp     rax, 11h
0x180020a2d  jnb     short loc_180020A36
0x180020a2f  mov     edx, 10Eh
0x180020a34  jmp     short loc_1800209DF
0x180020a36  test    r15, r15
0x180020a39  jnz     short loc_180020A42
0x180020a3b  mov     edx, 10Fh
0x180020a40  jmp     short loc_1800209DF
0x180020a42  cmp     [rdx], r12w
0x180020a46  jnz     short loc_180020A4F
0x180020a48  mov     edx, 110h
0x180020a4d  jmp     short loc_1800209DF
0x180020a4f  test    rsi, rsi
0x180020a52  jnz     short loc_180020A5B
0x180020a54  mov     edx, 111h
0x180020a59  jmp     short loc_1800209DF
0x180020a5b  cmp     [r8], r12w
0x180020a5f  jnz     short loc_180020A6B
0x180020a61  mov     edx, 112h
0x180020a66  jmp     loc_1800209DF
0x180020a6b  mov     rax, rbx
0x180020a6e  inc     rax
0x180020a71  cmp     [r8+rax*2], r12w
0x180020a76  jnz     short loc_180020A6E
0x180020a78  cmp     rax, 40h ; '@'
0x180020a7c  jbe     short loc_180020A88
0x180020a7e  mov     edx, 114h
0x180020a83  jmp     loc_1800209DF
0x180020a88  cmp     rax, 1
0x180020a8c  jnb     short loc_180020A98
0x180020a8e  mov     edx, 115h
0x180020a93  jmp     loc_1800209DF
0x180020a98  mov     rcx, [rbp+arg_30]
0x180020a9c  test    rcx, rcx
0x180020a9f  jnz     short loc_180020AAB
0x180020aa1  mov     edx, 116h
0x180020aa6  jmp     loc_1800209DF
0x180020aab  cmp     [rcx], r12w
0x180020aaf  jnz     short loc_180020ABB
0x180020ab1  mov     edx, 117h
0x180020ab6  jmp     loc_1800209DF
0x180020abb  test    r9, r9
0x180020abe  jz      short loc_180020AC8
0x180020ac0  mov     [rbp+arg_20], r12d
0x180020ac4  mov     [rbp+arg_28], r12d
0x180020ac8  lea     rax, [rbp+Block]
0x180020acc  mov     [rbp+Block], r12
0x180020ad0  mov     [rsp+40h+var_10], rax; __int64
0x180020ad5  lea     r9, [rbp+arg_28]
0x180020ad9  mov     rax, [rbp+arg_38]
0x180020add  lea     r8, [rbp+arg_20]
0x180020ae1  mov     [rsp+40h+var_18], rax; unsigned __int16 *
0x180020ae6  mov     rdx, rsi; void *
0x180020ae9  mov     [rsp+40h+var_20], rcx; int
0x180020aee  mov     rcx, r10; unsigned __int16 *
0x180020af1  call    ?GenerateProgId@ProgId@DataType@StateRepository@@YAJPEBG0PEAW4RuntimeBehavior@3@PEAW4SRTrustLevel@3@00AEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@Z; StateRepository::DataType::ProgId::GenerateProgId(ushort const *,ushort const *,StateRepository::RuntimeBehavior *,StateRepository::SRTrustLevel *,ushort const *,ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &)
0x180020af6  mov     edi, eax
0x180020af8  test    eax, eax
0x180020afa  jns     short loc_180020B29
0x180020afc  mov     rcx, [rbp+28h]; this
0x180020b00  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x180020b07  mov     r9d, eax; char *
0x180020b0a  mov     edx, 122h; void *
0x180020b0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020b14  mov     rcx, [rbp+Block]; Block
0x180020b18  test    rcx, rcx
0x180020b1b  jz      short loc_180020B22
0x180020b1d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020b22  mov     eax, edi
0x180020b24  jmp     loc_180020C01
0x180020b29  mov     rax, rbx
0x180020b2c  inc     rax
0x180020b2f  cmp     [rsi+rax*2], r12w
0x180020b34  jnz     short loc_180020B2C
0x180020b36  mov     rcx, rbx
0x180020b39  inc     rcx
0x180020b3c  cmp     [r15+rcx*2], r12w
0x180020b41  jnz     short loc_180020B39
0x180020b43  mov     rdi, [rbp+Block]
0x180020b47  inc     rbx
0x180020b4a  cmp     [rdi+rbx*2], r12w
0x180020b4f  jnz     short loc_180020B47
0x180020b51  lea     r14, [rcx+rax]
0x180020b55  add     r14, rbx
0x180020b58  lea     rcx, [rbp+Block]
0x180020b5c  lea     rdx, [r14+2]
0x180020b60  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180020b65  mov     rbx, [rbp+Block]
0x180020b69  test    rbx, rbx
0x180020b6c  jnz     short loc_180020BA1
0x180020b6e  mov     rcx, [rbp+28h]; this
0x180020b72  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x180020b79  mov     ebx, 8007000Eh
0x180020b7e  mov     edx, 126h; void *
0x180020b83  mov     r9d, ebx; char *
0x180020b86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020b8b  test    rdi, rdi
0x180020b8e  jz      loc_1800209F7
0x180020b94  mov     rcx, rdi; Block
0x180020b97  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020b9c  jmp     loc_1800209F7
0x180020ba1  mov     [rsp+40h+var_18], r15
0x180020ba6  lea     r8, aSSS; "%s.%s%s"
0x180020bad  mov     r9, rsi
0x180020bb0  mov     [rsp+40h+var_20], rdi; int
0x180020bb5  lea     rdx, [r14+2]; unsigned __int64
0x180020bb9  mov     rcx, rbx; unsigned __int16 *
0x180020bbc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180020bc1  test    eax, eax
0x180020bc3  jns     short loc_180020BDE
0x180020bc5  mov     rcx, [rbp+28h]; this
0x180020bc9  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x180020bd0  mov     r9d, eax; char *
0x180020bd3  mov     edx, 128h; void *
0x180020bd8  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180020bde  mov     rax, [rbp+arg_40]
0x180020be2  mov     rcx, [rax]; Block
0x180020be5  mov     [rax], rbx
0x180020be8  test    rcx, rcx
0x180020beb  jz      short loc_180020BF2
0x180020bed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020bf2  test    rdi, rdi
0x180020bf5  jz      short loc_180020BFF
0x180020bf7  mov     rcx, rdi; Block
0x180020bfa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020bff  xor     eax, eax
0x180020c01  lea     r11, [rsp+40h+var_s0]
0x180020c06  mov     rbx, [r11+38h]
0x180020c0a  mov     rsi, [r11+40h]
0x180020c0e  mov     rsp, r11
0x180020c11  pop     r15
0x180020c13  pop     r14
0x180020c15  pop     r12
0x180020c17  pop     rdi
0x180020c18  pop     rbp
0x180020c19  retn
```
