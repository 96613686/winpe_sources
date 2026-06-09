# StateRepository::DataType::ProgId::GenerateProgIdForExtension(ushort const *,ushort const *,ushort const *,ushort const *,StateRepository::RuntimeBehavior,StateRepository::SRTrustLevel,ushort const *,ushort const *,ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &)

- ea: `0x180021294`
- end: `0x180021514`
- name: `?GenerateProgIdForExtension@ProgId@DataType@StateRepository@@YAJPEBG000W4RuntimeBehavior@3@W4SRTrustLevel@3@000AEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@3@Z`
- size: `640`
- prototype: `__int64 __fastcall(unsigned __int16 *, _WORD *, _WORD *, __int64, int, int, _WORD *, _WORD *, unsigned __int16 *, int, __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x180021030`

## callees

- `0x1800041cc`
- `0x18000a3c0`
- `0x18000a7c0`
- `0x180014ca0`
- `0x180020714`
- `0x180020780`
- `0x1800209b0`
- `0x180020c20`
- `0x180021294`

## string_xrefs

- `0x1800212ca`: `onecore\base\appmodel\staterepository\dataaccesslayer\datatype-progid.cpp`
- `0x180021402`: `onecore\base\appmodel\staterepository\dataaccesslayer\datatype-progid.cpp`
- `0x18002146e`: `onecore\base\appmodel\staterepository\dataaccesslayer\datatype-progid.cpp`
- `0x1800214cf`: `onecore\base\appmodel\staterepository\dataaccesslayer\datatype-progid.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::DataType::ProgId::GenerateProgIdForExtension(
        unsigned __int16 *a1,
        _WORD *a2,
        _WORD *a3,
        __int64 a4,
        int a5,
        int a6,
        _WORD *a7,
        _WORD *a8,
        unsigned __int16 *a9,
        int a10,
        __int64 *a11)
{
  __int64 v13; // rdx
  unsigned int v14; // ebx
  _WORD *v16; // rdi
  _WORD *v17; // rbp
  unsigned __int16 *v18; // rsi
  unsigned __int16 *v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rbx
  __int64 unique; // rax
  void *v24; // rcx
  int v25; // eax
  int ACID; // eax
  unsigned int v27; // esi
  int ProgId; // eax
  unsigned int v29; // edi
  int v30; // [rsp+20h] [rbp-88h]
  int v31; // [rsp+20h] [rbp-88h]
  int v32; // [rsp+20h] [rbp-88h]
  unsigned __int16 *v33; // [rsp+50h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  void *Block; // [rsp+B0h] [rbp+8h] BYREF

  if ( !a1 )
  {
    v13 = 318;
LABEL_3:
    v14 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\datatype-progid.cpp",
      (const char *)v14,
      v30);
    return v14;
  }
  if ( !*a1 )
  {
    v13 = 319;
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v13 = 320;
    goto LABEL_3;
  }
  if ( !*a2 )
  {
    v13 = 321;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v13 = 322;
    goto LABEL_3;
  }
  if ( !*a3 )
  {
    v13 = 323;
    goto LABEL_3;
  }
  v16 = a7;
  if ( !a7 )
  {
    v13 = 324;
    goto LABEL_3;
  }
  if ( !*a7 )
  {
    v13 = 325;
    goto LABEL_3;
  }
  v17 = a8;
  v18 = a7;
  v33 = 0;
  v19 = 0;
  if ( a8 && *a8 )
  {
    v20 = -1;
    v21 = -1;
    do
      ++v21;
    while ( a8[v21] );
    do
      ++v20;
    while ( a7[v20] );
    v22 = v21 + v20;
    unique = wil::make_unique_nothrow<unsigned short [0]>(&Block, v21 + v20 + 2);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(&v33, unique);
    v24 = Block;
    Block = 0;
    if ( v24 )
      operator delete(v24);
    v18 = v33;
    if ( !v33 )
    {
      v14 = -2147024882;
      v13 = 333;
      goto LABEL_4;
    }
    v25 = StringCchPrintfW(v33, v22 + 2, L"%s.%s", v16);
    if ( v25 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x14E,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\datatype-progid.cpp",
        (const char *)(unsigned int)v25,
        (int)v17);
    v19 = v18;
  }
  ACID = StateRepository::DataType::ProgId::GenerateACID(a1, a5, a6, v18, a9, (__int64)a11);
  v27 = ACID;
  if ( ACID >= 0 )
  {
    if ( !a4 )
      a4 = *a11;
    v32 = a10;
    ProgId = StateRepository::DataType::ProgId::GenerateProgId(a1, a4, v16, v17);
    v29 = ProgId;
    if ( ProgId >= 0 )
    {
      if ( v19 )
        operator delete(v19);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x159,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\datatype-progid.cpp",
        (const char *)(unsigned int)ProgId,
        v32);
      if ( v19 )
        operator delete(v19);
      return v29;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x154,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\datatype-progid.cpp",
      (const char *)(unsigned int)ACID,
      v31);
    if ( v19 )
      operator delete(v19);
    return v27;
  }
}

```

## disassembly

```asm
0x180021294  push    rbx
0x180021296  push    rbp
0x180021297  push    rsi
0x180021298  push    rdi
0x180021299  push    r12
0x18002129b  push    r13
0x18002129d  push    r14
0x18002129f  push    r15
0x1800212a1  sub     rsp, 68h
0x1800212a5  mov     r13, rdx
0x1800212a8  mov     r14, r9
0x1800212ab  xor     edx, edx
0x1800212ad  mov     r12, r8
0x1800212b0  mov     r15, rcx
0x1800212b3  test    rcx, rcx
0x1800212b6  jnz     short loc_1800212E0
0x1800212b8  mov     edx, 13Eh; void *
0x1800212bd  mov     ebx, 80070057h
0x1800212c2  mov     rcx, [rsp+0A8h]; this
0x1800212ca  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x1800212d1  mov     r9d, ebx; char *
0x1800212d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800212d9  mov     eax, ebx
0x1800212db  jmp     loc_180021503
0x1800212e0  cmp     [rcx], dx
0x1800212e3  jnz     short loc_1800212EC
0x1800212e5  mov     edx, 13Fh
0x1800212ea  jmp     short loc_1800212BD
0x1800212ec  test    r13, r13
0x1800212ef  jnz     short loc_1800212F8
0x1800212f1  mov     edx, 140h
0x1800212f6  jmp     short loc_1800212BD
0x1800212f8  cmp     [r13+0], dx
0x1800212fd  jnz     short loc_180021306
0x1800212ff  mov     edx, 141h
0x180021304  jmp     short loc_1800212BD
0x180021306  test    r12, r12
0x180021309  jnz     short loc_180021312
0x18002130b  mov     edx, 142h
0x180021310  jmp     short loc_1800212BD
0x180021312  cmp     [r8], dx
0x180021316  jnz     short loc_18002131F
0x180021318  mov     edx, 143h
0x18002131d  jmp     short loc_1800212BD
0x18002131f  mov     rdi, [rsp+0A8h+arg_30]
0x180021327  test    rdi, rdi
0x18002132a  jnz     short loc_180021333
0x18002132c  mov     edx, 144h
0x180021331  jmp     short loc_1800212BD
0x180021333  cmp     [rdi], dx
0x180021336  jnz     short loc_180021342
0x180021338  mov     edx, 145h
0x18002133d  jmp     loc_1800212BD
0x180021342  mov     rbp, [rsp+0A8h+arg_38]
0x18002134a  mov     rsi, rdi
0x18002134d  mov     [rsp+0A8h+var_58], rdx
0x180021352  mov     rbx, rdx
0x180021355  test    rbp, rbp
0x180021358  jz      loc_18002141A
0x18002135e  cmp     [rbp+0], dx
0x180021362  jz      loc_18002141A
0x180021368  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002136c  mov     rcx, rax
0x18002136f  inc     rcx
0x180021372  cmp     [rbp+rcx*2+0], dx
0x180021377  jnz     short loc_18002136F
0x180021379  inc     rax
0x18002137c  cmp     [rdi+rax*2], dx
0x180021380  jnz     short loc_180021379
0x180021382  lea     rbx, [rcx+rax]
0x180021386  lea     rdx, [rbx+2]
0x18002138a  lea     rcx, [rsp+0A8h+Block]
0x180021392  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180021397  mov     rdx, rax
0x18002139a  lea     rcx, [rsp+0A8h+var_58]
0x18002139f  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x1800213a4  mov     rcx, [rsp+0A8h+Block]; Block
0x1800213ac  mov     [rsp+0A8h+Block], 0
0x1800213b8  test    rcx, rcx
0x1800213bb  jz      short loc_1800213C2
0x1800213bd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800213c2  mov     rsi, [rsp+0A8h+var_58]
0x1800213c7  test    rsi, rsi
0x1800213ca  jnz     short loc_1800213DB
0x1800213cc  mov     ebx, 8007000Eh
0x1800213d1  mov     edx, 14Dh
0x1800213d6  jmp     loc_1800212C2
0x1800213db  mov     r9, rdi
0x1800213de  mov     qword ptr [rsp+0A8h+var_88], rbp; int
0x1800213e3  lea     r8, aSS; "%s.%s"
0x1800213ea  mov     rcx, rsi; unsigned __int16 *
0x1800213ed  lea     rdx, [rbx+2]; unsigned __int64
0x1800213f1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800213f6  test    eax, eax
0x1800213f8  jns     short loc_180021417
0x1800213fa  mov     rcx, [rsp+0A8h]; this
0x180021402  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x180021409  mov     r9d, eax; char *
0x18002140c  mov     edx, 14Eh; void *
0x180021411  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180021417  mov     rbx, rsi
0x18002141a  mov     rax, [rsp+0A8h+arg_50]
0x180021422  mov     r9, r14
0x180021425  mov     [rsp+0A8h+var_68], rax
0x18002142a  mov     r8, r12
0x18002142d  mov     rax, [rsp+0A8h+arg_40]
0x180021435  mov     rdx, r13
0x180021438  mov     [rsp+0A8h+var_70], rax
0x18002143d  mov     rcx, r15
0x180021440  mov     eax, [rsp+0A8h+arg_28]
0x180021447  mov     [rsp+0A8h+var_78], rsi
0x18002144c  mov     [rsp+0A8h+var_80], eax
0x180021450  mov     eax, [rsp+0A8h+arg_20]
0x180021457  mov     [rsp+0A8h+var_88], eax; int
0x18002145b  call    ?GenerateACID@ProgId@DataType@StateRepository@@YAJPEBG000W4RuntimeBehavior@3@W4SRTrustLevel@3@00AEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@Z; StateRepository::DataType::ProgId::GenerateACID(ushort const *,ushort const *,ushort const *,ushort const *,StateRepository::RuntimeBehavior,StateRepository::SRTrustLevel,ushort const *,ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &)
0x180021460  mov     esi, eax
0x180021462  test    eax, eax
0x180021464  jns     short loc_180021493
0x180021466  mov     rcx, [rsp+0A8h]; this
0x18002146e  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x180021475  mov     r9d, eax; char *
0x180021478  mov     edx, 154h; void *
0x18002147d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021482  test    rbx, rbx
0x180021485  jz      short loc_18002148F
0x180021487  mov     rcx, rbx; Block
0x18002148a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002148f  mov     eax, esi
0x180021491  jmp     short loc_180021503
0x180021493  test    r14, r14
0x180021496  jnz     short loc_1800214A3
0x180021498  mov     rax, [rsp+0A8h+arg_50]
0x1800214a0  mov     r14, [rax]
0x1800214a3  mov     rax, qword ptr [rsp+0A8h+arg_48]
0x1800214ab  mov     r9, rbp
0x1800214ae  mov     r8, rdi
0x1800214b1  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x1800214b6  mov     rdx, r14
0x1800214b9  mov     rcx, r15
0x1800214bc  call    ?GenerateProgId@ProgId@DataType@StateRepository@@YAJPEBG000AEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@Z; StateRepository::DataType::ProgId::GenerateProgId(ushort const *,ushort const *,ushort const *,ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &)
0x1800214c1  mov     edi, eax
0x1800214c3  test    eax, eax
0x1800214c5  jns     short loc_1800214F4
0x1800214c7  mov     rcx, [rsp+0A8h]; this
0x1800214cf  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x1800214d6  mov     r9d, eax; char *
0x1800214d9  mov     edx, 159h; void *
0x1800214de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800214e3  test    rbx, rbx
0x1800214e6  jz      short loc_1800214F0
0x1800214e8  mov     rcx, rbx; Block
0x1800214eb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800214f0  mov     eax, edi
0x1800214f2  jmp     short loc_180021503
0x1800214f4  test    rbx, rbx
0x1800214f7  jz      short loc_180021501
0x1800214f9  mov     rcx, rbx; Block
0x1800214fc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021501  xor     eax, eax
0x180021503  add     rsp, 68h
0x180021507  pop     r15
0x180021509  pop     r14
0x18002150b  pop     r13
0x18002150d  pop     r12
0x18002150f  pop     rdi
0x180021510  pop     rsi
0x180021511  pop     rbp
0x180021512  pop     rbx
0x180021513  retn
```
