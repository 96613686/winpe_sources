# StateRepository::DataType::ProgId::GenerateProgId(ushort const *,ushort const *,StateRepository::RuntimeBehavior *,StateRepository::SRTrustLevel *,ushort const *,ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &)

- ea: `0x180020c78`
- end: `0x180021029`
- name: `?GenerateProgId@ProgId@DataType@StateRepository@@YAJPEBG0PEAW4RuntimeBehavior@3@PEAW4SRTrustLevel@3@00AEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@Z`
- size: `945`
- prototype: `__int64 __fastcall(unsigned __int16 *, _WORD *, int *, int *, unsigned __int16 *, unsigned __int16 *, void **)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800209b0`
- `0x180020c20`

## callees

- `0x1800041cc`
- `0x18000a3c0`
- `0x18000a77c`
- `0x1800148b8`
- `0x180014ca0`
- `0x180015270`
- `0x180020714`
- `0x180020858`
- `0x1800208a4`
- `0x180020958`
- `0x180020c78`
- `0x18002151c`
- `0x180021640`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180020f1c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180020f1c`

## string_xrefs

- `0x180020caf`: `onecore\base\appmodel\staterepository\dataaccesslayer\datatype-progid.cpp`
- `0x180020db7`: `onecore\base\appmodel\staterepository\dataaccesslayer\datatype-progid.cpp`
- `0x180020ecb`: `onecore\base\appmodel\staterepository\dataaccesslayer\datatype-progid.cpp`
- `0x180020f68`: `onecore\base\appmodel\staterepository\dataaccesslayer\datatype-progid.cpp`
- `0x180020fb8`: `onecore\base\appmodel\staterepository\dataaccesslayer\datatype-progid.cpp`
- `0x180020ff6`: `onecore\base\appmodel\staterepository\dataaccesslayer\datatype-progid.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::DataType::ProgId::GenerateProgId(
        unsigned __int16 *a1,
        _WORD *a2,
        int *a3,
        int *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        void **a7)
{
  __int64 v9; // rdx
  __int64 v11; // rdi
  unsigned __int64 v12; // rcx
  __int64 v13; // r14
  const unsigned __int16 *v14; // r15
  __int64 v15; // rdx
  __int64 v16; // rax
  void *v17; // rbx
  int v18; // esi
  __int64 v19; // rdx
  int ProgId; // eax
  const WCHAR *v21; // r14
  __int64 i; // rsi
  int v23; // eax
  void *v24; // r11
  void *v25; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-40h]
  LPCWCH lpString1[2]; // [rsp+30h] [rbp-30h] BYREF
  __int128 v28; // [rsp+40h] [rbp-20h] BYREF
  __int64 v29; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  void *Block; // [rsp+A0h] [rbp+40h] BYREF
  int *v32; // [rsp+B0h] [rbp+50h]
  int *v33; // [rsp+B8h] [rbp+58h]

  v33 = a4;
  v32 = a3;
  if ( !a1 )
  {
    v9 = 186;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\datatype-progid.cpp",
      (const char *)0x80070057LL,
      bIgnoreCase);
    return 2147942487LL;
  }
  if ( !*a1 )
  {
    v9 = 187;
    goto LABEL_3;
  }
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( a1[v12] );
  if ( v12 > 0x7F )
  {
    v9 = 189;
    goto LABEL_3;
  }
  if ( v12 < 0x11 )
  {
    v9 = 190;
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v9 = 191;
    goto LABEL_3;
  }
  if ( !*a2 )
  {
    v9 = 192;
    goto LABEL_3;
  }
  v13 = -1;
  do
    ++v13;
  while ( a2[v13] );
  if ( !a5 )
  {
    v9 = 195;
    goto LABEL_3;
  }
  if ( !*a5 )
  {
    v9 = 196;
    goto LABEL_3;
  }
  v14 = a6;
  if ( a6 )
  {
    v15 = -1;
    do
      ++v15;
    while ( a6[v15] );
  }
  else
  {
    v15 = 0;
  }
  v16 = -1;
  do
    ++v16;
  while ( a5[v16] );
  wil::make_unique_nothrow<unsigned short [0]>(&Block, v12 + 1 + v13 + v16 + v15);
  v17 = Block;
  if ( !Block )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\datatype-progid.cpp",
      (const char *)0x8007000ELL,
      bIgnoreCase);
    return 2147942414LL;
  }
  v29 = 0;
  v28 = 0;
  v18 = StateRepository::DataType::ProgId::Hasher::Start((StateRepository::DataType::ProgId::Hasher *)&v28);
  if ( v18 < 0 )
  {
    v19 = 216;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\datatype-progid.cpp",
      (const char *)(unsigned int)v18,
      bIgnoreCase);
LABEL_32:
    StateRepository::DataType::Hasher::~Hasher((StateRepository::DataType::Hasher *)&v28);
    if ( v17 )
      operator delete(v17);
    return (unsigned int)v18;
  }
  v18 = StateRepository::DataType::ProgId::Hasher::Digest((StateRepository::DataType::ProgId::Hasher *)&v28, a1);
  if ( v18 < 0 )
  {
    v19 = 217;
    goto LABEL_31;
  }
  v18 = StateRepository::DataType::ProgId::Hasher::Digest(
          (StateRepository::DataType::ProgId::Hasher *)&v28,
          2 * v13,
          a2);
  if ( v18 < 0 )
  {
    v19 = 218;
    goto LABEL_31;
  }
  if ( v32 )
  {
    if ( *v32 != 1 )
    {
      v18 = StateRepository::DataType::ProgId::Hasher::Digest((StateRepository::DataType::ProgId::Hasher *)&v28, *v32);
      if ( v18 < 0 )
      {
        v19 = 222;
        goto LABEL_31;
      }
    }
  }
  if ( v33 )
  {
    if ( *v33 != 1 )
    {
      v18 = StateRepository::DataType::ProgId::Hasher::Digest((StateRepository::DataType::ProgId::Hasher *)&v28, *v33);
      if ( v18 < 0 )
      {
        v19 = 226;
        goto LABEL_31;
      }
    }
  }
  v18 = StateRepository::DataType::ProgId::Hasher::Digest((StateRepository::DataType::ProgId::Hasher *)&v28, a5);
  if ( v18 < 0 )
  {
    v19 = 228;
    goto LABEL_31;
  }
  if ( v14 )
  {
    v18 = StateRepository::DataType::ProgId::Hasher::Digest((StateRepository::DataType::ProgId::Hasher *)&v28, v14);
    if ( v18 < 0 )
    {
      v19 = 231;
      goto LABEL_31;
    }
  }
  lpString1[0] = 0;
  lpString1[1] = 0;
  ProgId = StateRepository::DataType::ProgId::Hasher::GetProgId(
             (StateRepository::DataType::ProgId::Hasher *)&v28,
             (struct StateRepository::Text *)lpString1);
  v18 = ProgId;
  if ( ProgId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEA,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\datatype-progid.cpp",
      (const char *)(unsigned int)ProgId,
      bIgnoreCase);
    StateRepository::Text::Reset((StateRepository::Text *)lpString1);
    goto LABEL_32;
  }
  v21 = lpString1[0];
  for ( i = 0; !i; i = 1 )
  {
    if ( CompareStringOrdinal(
           v21,
           -1,
           (LPCWCH)StateRepository::DataType::ProgId::ProgIdToPreserve::c_progIdsToPreserve,
           -1,
           1) == 2 )
    {
      v21 = L"AppXqj98qxeaynz6dv4459ayz6bnqxbyaqcs";
      goto LABEL_59;
    }
  }
  do
LABEL_59:
    ++v11;
  while ( v21[v11] );
  wil::make_unique_nothrow<unsigned short [0]>(&Block, v11 + 1);
  if ( !Block )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF2,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\datatype-progid.cpp",
      (const char *)0x8007000ELL,
      bIgnoreCase);
    StateRepository::Text::Reset((StateRepository::Text *)lpString1);
    StateRepository::DataType::Hasher::~Hasher((StateRepository::DataType::Hasher *)&v28);
    if ( v17 )
      operator delete(v17);
    return 2147942414LL;
  }
  v23 = StringCchCopyW((unsigned __int16 *)Block, v11 + 1, v21);
  if ( v23 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xF3,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\datatype-progid.cpp",
      (const char *)(unsigned int)v23,
      bIgnoreCase);
  v25 = *a7;
  *a7 = v24;
  if ( v25 )
    operator delete(v25);
  StateRepository::Text::Reset((StateRepository::Text *)lpString1);
  StateRepository::DataType::Hasher::~Hasher((StateRepository::DataType::Hasher *)&v28);
  if ( v17 )
    operator delete(v17);
  return 0;
}

```

## disassembly

```asm
0x180020c78  mov     [rsp-38h+arg_8], rbx
0x180020c7d  mov     [rsp-38h+arg_18], r9
0x180020c82  mov     [rsp-38h+arg_10], r8
0x180020c87  push    rbp
0x180020c88  push    rsi
0x180020c89  push    rdi
0x180020c8a  push    r12
0x180020c8c  push    r13
0x180020c8e  push    r14
0x180020c90  push    r15
0x180020c92  mov     rbp, rsp
0x180020c95  sub     rsp, 60h
0x180020c99  xor     esi, esi
0x180020c9b  mov     r13, rdx
0x180020c9e  mov     r12, rcx
0x180020ca1  test    rcx, rcx
0x180020ca4  jnz     short loc_180020CCA
0x180020ca6  mov     edx, 0BAh; void *
0x180020cab  mov     rcx, [rbp+38h]; this
0x180020caf  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x180020cb6  mov     ebx, 80070057h
0x180020cbb  mov     r9d, ebx; char *
0x180020cbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020cc3  mov     eax, ebx
0x180020cc5  jmp     loc_180021011
0x180020cca  cmp     [rcx], si
0x180020ccd  jnz     short loc_180020CD6
0x180020ccf  mov     edx, 0BBh
0x180020cd4  jmp     short loc_180020CAB
0x180020cd6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180020cda  mov     rcx, rdi
0x180020cdd  inc     rcx
0x180020ce0  cmp     [r12+rcx*2], si
0x180020ce5  jnz     short loc_180020CDD
0x180020ce7  cmp     rcx, 7Fh
0x180020ceb  jbe     short loc_180020CF4
0x180020ced  mov     edx, 0BDh
0x180020cf2  jmp     short loc_180020CAB
0x180020cf4  cmp     rcx, 11h
0x180020cf8  jnb     short loc_180020D01
0x180020cfa  mov     edx, 0BEh
0x180020cff  jmp     short loc_180020CAB
0x180020d01  test    r13, r13
0x180020d04  jnz     short loc_180020D0D
0x180020d06  mov     edx, 0BFh
0x180020d0b  jmp     short loc_180020CAB
0x180020d0d  cmp     [rdx], si
0x180020d10  jnz     short loc_180020D19
0x180020d12  mov     edx, 0C0h
0x180020d17  jmp     short loc_180020CAB
0x180020d19  mov     r14, rdi
0x180020d1c  inc     r14
0x180020d1f  cmp     [rdx+r14*2], si
0x180020d24  jnz     short loc_180020D1C
0x180020d26  mov     r8, [rbp+arg_20]
0x180020d2a  test    r8, r8
0x180020d2d  jnz     short loc_180020D39
0x180020d2f  mov     edx, 0C3h
0x180020d34  jmp     loc_180020CAB
0x180020d39  cmp     [r8], si
0x180020d3d  jnz     short loc_180020D49
0x180020d3f  mov     edx, 0C4h
0x180020d44  jmp     loc_180020CAB
0x180020d49  mov     r15, [rbp+arg_28]
0x180020d4d  test    r15, r15
0x180020d50  jnz     short loc_180020D57
0x180020d52  mov     rdx, rsi
0x180020d55  jmp     short loc_180020D64
0x180020d57  mov     rdx, rdi
0x180020d5a  inc     rdx
0x180020d5d  cmp     [r15+rdx*2], si
0x180020d62  jnz     short loc_180020D5A
0x180020d64  mov     rax, rdi
0x180020d67  inc     rax
0x180020d6a  cmp     [r8+rax*2], si
0x180020d6f  jnz     short loc_180020D67
0x180020d71  inc     rcx
0x180020d74  add     rax, r14
0x180020d77  add     rax, rcx
0x180020d7a  lea     rcx, [rbp+Block]
0x180020d7e  add     rdx, rax
0x180020d81  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180020d86  mov     rbx, [rbp+Block]
0x180020d8a  test    rbx, rbx
0x180020d8d  jz      loc_180020FF2
0x180020d93  xorps   xmm0, xmm0
0x180020d96  mov     [rbp+var_10], rsi
0x180020d9a  lea     rcx, [rbp+var_20]; this
0x180020d9e  movdqu  [rbp+var_20], xmm0
0x180020da3  call    ?Start@Hasher@ProgId@DataType@StateRepository@@QEAAJXZ; StateRepository::DataType::ProgId::Hasher::Start(void)
0x180020da8  mov     esi, eax
0x180020daa  test    eax, eax
0x180020dac  jns     short loc_180020DE3
0x180020dae  mov     edx, 0D8h; void *
0x180020db3  mov     rcx, [rbp+38h]; this
0x180020db7  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x180020dbe  mov     r9d, esi; char *
0x180020dc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020dc6  lea     rcx, [rbp+var_20]; this
0x180020dca  call    ??1Hasher@DataType@StateRepository@@QEAA@XZ; StateRepository::DataType::Hasher::~Hasher(void)
0x180020dcf  test    rbx, rbx
0x180020dd2  jz      short loc_180020DDC
0x180020dd4  mov     rcx, rbx; Block
0x180020dd7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020ddc  mov     eax, esi
0x180020dde  jmp     loc_180021011
0x180020de3  mov     rdx, r12; unsigned __int16 *
0x180020de6  lea     rcx, [rbp+var_20]; this
0x180020dea  call    ?Digest@Hasher@ProgId@DataType@StateRepository@@QEAAJPEBG@Z; StateRepository::DataType::ProgId::Hasher::Digest(ushort const *)
0x180020def  xor     r12d, r12d
0x180020df2  mov     esi, eax
0x180020df4  test    eax, eax
0x180020df6  jns     short loc_180020DFF
0x180020df8  mov     edx, 0D9h
0x180020dfd  jmp     short loc_180020DB3
0x180020dff  lea     rdx, [r14+r14]; unsigned __int64
0x180020e03  mov     r8, r13; void *
0x180020e06  lea     rcx, [rbp+var_20]; this
0x180020e0a  call    ?Digest@Hasher@ProgId@DataType@StateRepository@@QEAAJ_KPEBX@Z; StateRepository::DataType::ProgId::Hasher::Digest(unsigned __int64,void const *)
0x180020e0f  mov     esi, eax
0x180020e11  test    eax, eax
0x180020e13  jns     short loc_180020E1C
0x180020e15  mov     edx, 0DAh
0x180020e1a  jmp     short loc_180020DB3
0x180020e1c  mov     rax, [rbp+arg_10]
0x180020e20  test    rax, rax
0x180020e23  jz      short loc_180020E45
0x180020e25  cmp     dword ptr [rax], 1
0x180020e28  jz      short loc_180020E45
0x180020e2a  mov     edx, [rax]; int
0x180020e2c  lea     rcx, [rbp+var_20]; this
0x180020e30  call    ?Digest@Hasher@ProgId@DataType@StateRepository@@QEAAJH@Z; StateRepository::DataType::ProgId::Hasher::Digest(int)
0x180020e35  mov     esi, eax
0x180020e37  test    eax, eax
0x180020e39  jns     short loc_180020E45
0x180020e3b  mov     edx, 0DEh
0x180020e40  jmp     loc_180020DB3
0x180020e45  mov     rax, [rbp+arg_18]
0x180020e49  test    rax, rax
0x180020e4c  jz      short loc_180020E6E
0x180020e4e  cmp     dword ptr [rax], 1
0x180020e51  jz      short loc_180020E6E
0x180020e53  mov     edx, [rax]; int
0x180020e55  lea     rcx, [rbp+var_20]; this
0x180020e59  call    ?Digest@Hasher@ProgId@DataType@StateRepository@@QEAAJH@Z; StateRepository::DataType::ProgId::Hasher::Digest(int)
0x180020e5e  mov     esi, eax
0x180020e60  test    eax, eax
0x180020e62  jns     short loc_180020E6E
0x180020e64  mov     edx, 0E2h
0x180020e69  jmp     loc_180020DB3
0x180020e6e  mov     rdx, [rbp+arg_20]; unsigned __int16 *
0x180020e72  lea     rcx, [rbp+var_20]; this
0x180020e76  call    ?Digest@Hasher@ProgId@DataType@StateRepository@@QEAAJPEBG@Z; StateRepository::DataType::ProgId::Hasher::Digest(ushort const *)
0x180020e7b  mov     esi, eax
0x180020e7d  test    eax, eax
0x180020e7f  jns     short loc_180020E8B
0x180020e81  mov     edx, 0E4h
0x180020e86  jmp     loc_180020DB3
0x180020e8b  test    r15, r15
0x180020e8e  jz      short loc_180020EAC
0x180020e90  mov     rdx, r15; unsigned __int16 *
0x180020e93  lea     rcx, [rbp+var_20]; this
0x180020e97  call    ?Digest@Hasher@ProgId@DataType@StateRepository@@QEAAJPEBG@Z; StateRepository::DataType::ProgId::Hasher::Digest(ushort const *)
0x180020e9c  mov     esi, eax
0x180020e9e  test    eax, eax
0x180020ea0  jns     short loc_180020EAC
0x180020ea2  mov     edx, 0E7h
0x180020ea7  jmp     loc_180020DB3
0x180020eac  lea     rdx, [rbp+lpString1]; struct StateRepository::Text *
0x180020eb0  mov     [rbp+lpString1], r12
0x180020eb4  lea     rcx, [rbp+var_20]; this
0x180020eb8  mov     [rbp+var_28], r12
0x180020ebc  call    ?GetProgId@Hasher@ProgId@DataType@StateRepository@@QEAAJAEAVText@4@@Z; StateRepository::DataType::ProgId::Hasher::GetProgId(StateRepository::Text &)
0x180020ec1  mov     esi, eax
0x180020ec3  test    eax, eax
0x180020ec5  jns     short loc_180020EED
0x180020ec7  mov     rcx, [rbp+38h]; this
0x180020ecb  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x180020ed2  mov     r9d, eax; char *
0x180020ed5  mov     edx, 0EAh; void *
0x180020eda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020edf  lea     rcx, [rbp+lpString1]; this
0x180020ee3  call    ?Reset@Text@StateRepository@@QEAAXXZ; StateRepository::Text::Reset(void)
0x180020ee8  jmp     loc_180020DC6
0x180020eed  mov     r14, [rbp+lpString1]
0x180020ef1  lea     r13, ?c_progIdsToPreserve@ProgIdToPreserve@ProgId@DataType@StateRepository@@0QBU1234@B; StateRepository::DataType::ProgId::ProgIdToPreserve const near * const StateRepository::DataType::ProgId::ProgIdToPreserve::c_progIdsToPreserve
0x180020ef8  mov     rsi, r12
0x180020efb  cmp     rsi, 1
0x180020eff  jnb     short loc_180020F31
0x180020f01  mov     r15, rsi
0x180020f04  mov     [rsp+60h+bIgnoreCase], 1; int
0x180020f0c  add     r15, r15
0x180020f0f  mov     r9d, edi; cchCount2
0x180020f12  mov     edx, edi; cchCount1
0x180020f14  mov     rcx, r14; lpString1
0x180020f17  mov     r8, [r13+r15*8+0]; lpString2
0x180020f1c  call    cs:__imp_CompareStringOrdinal
0x180020f22  cmp     eax, 2
0x180020f25  jz      short loc_180020F2C
0x180020f27  inc     rsi
0x180020f2a  jmp     short loc_180020EFB
0x180020f2c  mov     r14, [r13+r15*8+8]
0x180020f31  inc     rdi
0x180020f34  cmp     [r14+rdi*2], r12w
0x180020f39  jnz     short loc_180020F31
0x180020f3b  lea     rdx, [rdi+1]
0x180020f3f  lea     rcx, [rbp+Block]
0x180020f43  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180020f48  mov     r11, [rbp+Block]
0x180020f4c  test    r11, r11
0x180020f4f  jz      short loc_180020FB4
0x180020f51  mov     r8, r14; unsigned __int16 *
0x180020f54  lea     rdx, [rdi+1]; unsigned __int64
0x180020f58  mov     rcx, r11; unsigned __int16 *
0x180020f5b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180020f60  test    eax, eax
0x180020f62  jns     short loc_180020F7D
0x180020f64  mov     rcx, [rbp+38h]; this
0x180020f68  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x180020f6f  mov     r9d, eax; char *
0x180020f72  mov     edx, 0F3h; void *
0x180020f77  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180020f7d  mov     rax, [rbp+arg_30]
0x180020f81  mov     rcx, [rax]; Block
0x180020f84  mov     [rax], r11
0x180020f87  test    rcx, rcx
0x180020f8a  jz      short loc_180020F91
0x180020f8c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020f91  lea     rcx, [rbp+lpString1]; this
0x180020f95  call    ?Reset@Text@StateRepository@@QEAAXXZ; StateRepository::Text::Reset(void)
0x180020f9a  lea     rcx, [rbp+var_20]; this
0x180020f9e  call    ??1Hasher@DataType@StateRepository@@QEAA@XZ; StateRepository::DataType::Hasher::~Hasher(void)
0x180020fa3  test    rbx, rbx
0x180020fa6  jz      short loc_180020FB0
0x180020fa8  mov     rcx, rbx; Block
0x180020fab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020fb0  xor     eax, eax
0x180020fb2  jmp     short loc_180021011
0x180020fb4  mov     rcx, [rbp+38h]; this
0x180020fb8  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x180020fbf  mov     edi, 8007000Eh
0x180020fc4  mov     edx, 0F2h; void *
0x180020fc9  mov     r9d, edi; char *
0x180020fcc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020fd1  lea     rcx, [rbp+lpString1]; this
0x180020fd5  call    ?Reset@Text@StateRepository@@QEAAXXZ; StateRepository::Text::Reset(void)
0x180020fda  lea     rcx, [rbp+var_20]; this
0x180020fde  call    ??1Hasher@DataType@StateRepository@@QEAA@XZ; StateRepository::DataType::Hasher::~Hasher(void)
0x180020fe3  test    rbx, rbx
0x180020fe6  jz      short loc_18002100F
0x180020fe8  mov     rcx, rbx; Block
0x180020feb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020ff0  jmp     short loc_18002100F
0x180020ff2  mov     rcx, [rbp+38h]; this
0x180020ff6  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x180020ffd  mov     edi, 8007000Eh
0x180021002  mov     edx, 0CDh; void *
0x180021007  mov     r9d, edi; char *
0x18002100a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002100f  mov     eax, edi
0x180021011  mov     rbx, [rsp+60h+arg_8]
0x180021019  add     rsp, 60h
0x18002101d  pop     r15
0x18002101f  pop     r14
0x180021021  pop     r13
0x180021023  pop     r12
0x180021025  pop     rdi
0x180021026  pop     rsi
0x180021027  pop     rbp
0x180021028  retn
```
