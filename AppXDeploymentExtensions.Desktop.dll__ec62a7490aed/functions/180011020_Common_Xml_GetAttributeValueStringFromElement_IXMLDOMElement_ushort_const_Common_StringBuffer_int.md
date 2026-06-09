# Common::Xml::GetAttributeValueStringFromElement(IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)

- ea: `0x180011020`
- end: `0x180011575`
- name: `?GetAttributeValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@PEBGAEAVStringBuffer@2@PEAH@Z`
- size: `1365`
- prototype: `int(Common::Xml *__hidden this, struct IXMLDOMElement *, const unsigned __int16 *, struct Common::StringBuffer *, int *)`
- caller_count: `36`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180006c98`
- `0x18000d6dc`
- `0x18001db48`
- `0x18003807c`
- `0x180038540`
- `0x180052330`
- `0x1800571f0`
- `0x1800598f0`
- `0x18005c3a8`
- `0x1800770b0`
- `0x18007f318`
- `0x18008ad50`
- `0x18008d8dc`
- `0x18008f878`
- `0x180090d68`
- `0x1800957ac`
- `0x180095a84`
- `0x18009d574`
- `0x18009d698`
- `0x1800a8b80`
- `0x1800a9040`
- `0x1800aa10c`
- `0x1800aa478`
- `0x1800d9f24`
- `0x1800dd2dc`
- `0x1800df120`
- `0x1800e14d0`
- `0x1800e5c70`
- `0x1800e97c8`
- `0x1800e9aa4`
- `0x1800e9c30`
- `0x1800eabc8`
- `0x1800ec6f4`
- `0x1800ee118`
- `0x180118b3c`
- `0x180118c24`

## callees

- `0x180011020`
- `0x180012fc8`
- `0x18001adb4`
- `0x1800207a0`
- `0x180040230`
- `0x1800807b4`
- `0x1800af1bc`
- `0x1800af1fc`
- `0x1800ba45d`
- `0x1801ac010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800110d8`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800110d8`
- `OLEAUT32!__imp_SysFreeString` at `0x180011081`
- `OLEAUT32!__imp_SysFreeString` at `0x18001115b`
- `OLEAUT32!__imp_SysFreeString` at `0x180011081`
- `OLEAUT32!__imp_SysFreeString` at `0x18001115b`
- `OLEAUT32!__imp_VariantClear` at `0x18001116d`
- `OLEAUT32!__imp_VariantClear` at `0x18001116d`

## string_xrefs

- `0x180011290`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x1800112a9`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x1800112c2`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x1800112db`: `onecore\base\appmodel\common\widestring.cpp`
- `0x1800112f4`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180011397`: `onecore\base\appmodel\common\widestring.cpp`
- `0x1800113e5`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180011417`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180011430`: `onecore\base\appmodel\common\widestring.cpp`
- `0x1800114a3`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180011500`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180011521`: `onecore\base\appmodel\common\widestring.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Common::Xml::GetAttributeValueStringFromElement(
        Common::Xml *this,
        const OLECHAR *a2,
        unsigned __int16 *a3,
        struct Common::StringBuffer *a4)
{
  struct Common::StringBuffer *v4; // r15
  unsigned __int16 *v5; // r12
  OLECHAR *v8; // rbx
  __int64 v9; // rcx
  const OLECHAR *v10; // rax
  int v11; // edi
  int v12; // eax
  const void *bstrVal; // r14
  __int64 v14; // rax
  bool v15; // zf
  __int64 v16; // rax
  _BYTE *v17; // rcx
  __int64 v19; // rdx
  BSTR v20; // rax
  unsigned int v21; // esi
  __int64 v22; // rbp
  unsigned int v23; // ecx
  int v24; // edx
  unsigned int v25; // ecx
  unsigned int i; // edi
  __int64 v27; // r15
  _WORD *v28; // r12
  _WORD *v29; // r14
  unsigned int v30; // eax
  int v31; // eax
  void *v32; // rcx
  unsigned __int64 v33; // rax
  _WORD *v34; // rax
  const struct std::nothrow_t *v35; // rdx
  errno_t v36; // ebp
  int v37; // [rsp+20h] [rbp-68h]
  int v38; // [rsp+20h] [rbp-68h]
  char *v39; // [rsp+28h] [rbp-60h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  LONGLONG llVal; // [rsp+90h] [rbp+8h]

  v4 = a4;
  v5 = a3;
  memset(&pvarg, 0, sizeof(pvarg));
  pvarg.vt = 0;
  v8 = 0;
  if ( !this || !a2 )
  {
    v11 = -2147024809;
    goto LABEL_16;
  }
  if ( a4 )
    *(_DWORD *)a4 = 0;
  SysFreeString(0);
  v8 = 0;
  v9 = 0x7FFFFFFF;
  v10 = a2;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  v11 = -2147024809;
  if ( v9 )
  {
    if ( (unsigned int)(0x7FFFFFFF - v9) > 0x3FFFFFFF )
    {
      v11 = -2147024809;
    }
    else
    {
      v8 = SysAllocStringLen(a2, 0x7FFFFFFF - (int)v9);
      v11 = 0;
      if ( !v8 )
        v11 = -2147024882;
    }
  }
  if ( v11 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x134,
      (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
      (const char *)(unsigned int)v11,
      v37);
    goto LABEL_16;
  }
  v12 = (*(__int64 (__fastcall **)(Common::Xml *, OLECHAR *, VARIANTARG *))(*(_QWORD *)this + 352LL))(this, v8, &pvarg);
  v11 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x135,
      (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
      (const char *)(unsigned int)v12,
      v37);
    goto LABEL_16;
  }
  bstrVal = pvarg.bstrVal;
  llVal = pvarg.llVal;
  if ( !pvarg.llVal )
  {
    v14 = *(unsigned int *)v5;
    v15 = 2 * v14 == 0;
    v16 = 2 * v14;
    v17 = (_BYTE *)*((_QWORD *)v5 + 1);
    if ( !v15 )
    {
      do
      {
        *v17++ = 0;
        --v16;
      }
      while ( v16 );
    }
    goto LABEL_16;
  }
  v19 = 1073741822;
  v20 = pvarg.bstrVal;
  do
  {
    if ( !*v20 )
      break;
    ++v20;
    --v19;
  }
  while ( v19 );
  v11 = -2147024809;
  if ( !v19 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x249,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)0x80070057LL,
      v37);
    goto LABEL_36;
  }
  v21 = 1073741822 - v19;
  v11 = 0;
  if ( (unsigned int)(1073741822 - v19) > 0x7FFFFFFF )
    v11 = -2147024362;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x22F,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)(unsigned int)v11,
      v37);
    goto LABEL_36;
  }
  v22 = *((unsigned int *)v5 + 4);
  v23 = 0;
  if ( (_DWORD)v22 )
    v23 = v22 - 1;
  if ( v21 <= v23 && v23 <= 0x20 )
    goto LABEL_28;
  if ( v21 > 0x20 )
  {
    i = 1073741822 - v19;
  }
  else
  {
    for ( i = 8; i < v21; i *= 2 )
      ;
  }
  if ( i > 0x3FFFFFFF )
  {
    v11 = -2147023613;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A9,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)0x80070503LL,
      v37);
    goto LABEL_59;
  }
  if ( !i )
  {
    v32 = (void *)*((_QWORD *)v5 + 1);
    if ( v32 )
    {
      operator delete(v32, (const struct std::nothrow_t *)v19);
      *((_QWORD *)v5 + 1) = 0;
      *(_DWORD *)v5 = 0;
    }
    *((_DWORD *)v5 + 4) = 0;
    goto LABEL_58;
  }
  v27 = i + 1;
  if ( (_DWORD)v27 != (_DWORD)v22 )
  {
    v28 = (_WORD *)*((_QWORD *)v5 + 1);
    if ( (unsigned int)v27 <= (unsigned int)v22 )
    {
      v29 = v28;
LABEL_52:
      v5 = a3;
      *((_DWORD *)a3 + 4) = v27;
      *((_QWORD *)a3 + 1) = v29;
      v30 = *(_DWORD *)a3;
      if ( *(_DWORD *)a3 > i )
      {
        *(_DWORD *)a3 = i;
        v29[i] = 0;
      }
      else if ( v30 < i && !v30 )
      {
        *v29 = 0;
      }
      bstrVal = (const void *)llVal;
      goto LABEL_57;
    }
    v33 = 2LL * (unsigned int)v27;
    if ( !is_mul_ok((unsigned int)v27, 2u) )
      v33 = -1;
    v34 = operator new[](v33, (const struct std::nothrow_t *)&std::nothrow);
    v29 = v34;
    if ( v34 )
    {
      v36 = memcpy_s(v34, 2 * v27, v28, 2 * v22);
      if ( !v36 )
      {
        operator delete(v28, v35);
        goto LABEL_52;
      }
      operator delete(v29, v35);
      LODWORD(v39) = v36;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x198,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)0x80070057LL,
        (int)"0x%08lx",
        v39);
      v11 = -2147024809;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x193,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)0x8007000ELL,
        v37);
      v11 = -2147024882;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C4,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)(unsigned int)v11,
      v38);
    bstrVal = (const void *)llVal;
    v4 = a4;
    v5 = a3;
    goto LABEL_59;
  }
LABEL_57:
  v4 = a4;
LABEL_58:
  v11 = 0;
LABEL_59:
  if ( v11 >= 0 )
  {
LABEL_28:
    v24 = *((_DWORD *)v5 + 4);
    v25 = 0;
    if ( v24 )
      v25 = v24 - 1;
    if ( v21 <= v25 || (v31 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)v5, v21), v11 = v31, v31 >= 0) )
    {
      *(_DWORD *)v5 = v21;
      if ( v21 )
        *(_WORD *)(*((_QWORD *)v5 + 1) + 2LL * v21) = 0;
      v11 = 0;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x20C,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)(unsigned int)v31,
        v37);
    }
    if ( v11 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x235,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)(unsigned int)v11,
        v37);
    }
    else
    {
      memcpy_0(*((void **)v5 + 1), bstrVal, 2 * v21);
      v11 = 0;
    }
    goto LABEL_36;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x232,
    (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
    (const char *)(unsigned int)v11,
    v37);
LABEL_36:
  if ( v11 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x13D,
      (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
      (const char *)(unsigned int)v11,
      v37);
  }
  else if ( v4 )
  {
    *(_DWORD *)v4 = 1;
  }
LABEL_16:
  SysFreeString(v8);
  VariantClear(&pvarg);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180011020  mov     [rsp+arg_8], rbx
0x180011025  mov     [rsp+arg_18], r9
0x18001102a  mov     [rsp+arg_10], r8
0x18001102f  push    rbp
0x180011030  push    rsi
0x180011031  push    rdi
0x180011032  push    r12
0x180011034  push    r13
0x180011036  push    r14
0x180011038  push    r15
0x18001103a  sub     rsp, 50h
0x18001103e  mov     r15, r9
0x180011041  mov     r12, r8
0x180011044  mov     rsi, rdx
0x180011047  mov     r14, rcx
0x18001104a  xorps   xmm0, xmm0
0x18001104d  xor     eax, eax
0x18001104f  movups  xmmword ptr [rsp+88h+pvarg], xmm0
0x180011054  mov     qword ptr [rsp+88h+pvarg+10h], rax
0x180011059  xor     r13d, r13d
0x18001105c  mov     word ptr [rsp+88h+pvarg], r13w
0x180011062  mov     ebx, r13d
0x180011065  test    rcx, rcx
0x180011068  jz      loc_1800113AD
0x18001106e  test    rdx, rdx
0x180011071  jz      loc_1800113AD
0x180011077  test    r9, r9
0x18001107a  jz      short loc_18001107F
0x18001107c  mov     [r9], r13d
0x18001107f  xor     ecx, ecx; bstrString
0x180011081  call    cs:__imp_SysFreeString
0x180011088  nop     dword ptr [rax+rax+00h]
0x18001108d  mov     rbx, r13
0x180011090  mov     [rsp+88h+arg_0], rbx
0x180011098  mov     ecx, 7FFFFFFFh
0x18001109d  mov     rax, rsi
0x1800110a0  cmp     [rax], bx
0x1800110a3  jz      short loc_1800110AF
0x1800110a5  add     rax, 2
0x1800110a9  sub     rcx, 1
0x1800110ad  jnz     short loc_1800110A0
0x1800110af  mov     edi, 80070057h
0x1800110b4  test    rcx, rcx
0x1800110b7  cmovnz  edi, r13d
0x1800110bb  mov     ebp, 8007000Eh
0x1800110c0  jz      short loc_1800110F8
0x1800110c2  mov     edx, 7FFFFFFFh
0x1800110c7  sub     edx, ecx; ui
0x1800110c9  cmp     edx, 3FFFFFFFh
0x1800110cf  ja      loc_1800113BE
0x1800110d5  mov     rcx, rsi; strIn
0x1800110d8  call    cs:__imp_SysAllocStringLen
0x1800110df  nop     dword ptr [rax+rax+00h]
0x1800110e4  mov     rbx, rax
0x1800110e7  mov     [rsp+88h+arg_0], rax
0x1800110ef  mov     edi, r13d
0x1800110f2  test    rax, rax
0x1800110f5  cmovz   edi, ebp
0x1800110f8  mov     rcx, [rsp+88h]; this
0x180011100  test    edi, edi
0x180011102  js      loc_18001128D
0x180011108  mov     rax, [r14]
0x18001110b  lea     r8, [rsp+88h+pvarg]
0x180011110  mov     rdx, rbx
0x180011113  mov     rcx, r14
0x180011116  mov     rax, [rax+160h]
0x18001111d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011122  mov     edi, eax
0x180011124  mov     rcx, [rsp+88h]; this
0x18001112c  test    eax, eax
0x18001112e  js      loc_1800112A6
0x180011134  mov     r14, qword ptr [rsp+88h+pvarg+8]
0x180011139  mov     [rsp+88h+arg_0], r14
0x180011141  test    r14, r14
0x180011144  jnz     short loc_180011194
0x180011146  mov     eax, [r12]
0x18001114a  add     rax, rax
0x18001114d  mov     rcx, [r12+8]
0x180011152  jnz     loc_180011562
0x180011158  mov     rcx, rbx; bstrString
0x18001115b  call    cs:__imp_SysFreeString
0x180011162  nop     dword ptr [rax+rax+00h]
0x180011167  nop
0x180011168  lea     rcx, [rsp+88h+pvarg]; pvarg
0x18001116d  call    cs:__imp_VariantClear
0x180011174  nop     dword ptr [rax+rax+00h]
0x180011179  mov     eax, edi
0x18001117b  mov     rbx, [rsp+88h+arg_8]
0x180011183  add     rsp, 50h
0x180011187  pop     r15
0x180011189  pop     r14
0x18001118b  pop     r13
0x18001118d  pop     r12
0x18001118f  pop     rdi
0x180011190  pop     rsi
0x180011191  pop     rbp
0x180011192  retn
0x180011194  mov     ecx, 3FFFFFFEh
0x180011199  mov     edx, ecx
0x18001119b  mov     rax, r14
0x18001119e  xchg    ax, ax
0x1800111a0  cmp     word ptr [rax], 0
0x1800111a4  jz      short loc_1800111B0
0x1800111a6  add     rax, 2
0x1800111aa  sub     rdx, 1; struct std::nothrow_t *
0x1800111ae  jnz     short loc_1800111A0
0x1800111b0  mov     edi, 80070057h
0x1800111b5  test    rdx, rdx
0x1800111b8  cmovnz  edi, r13d
0x1800111bc  sub     rcx, rdx
0x1800111bf  mov     rsi, r13
0x1800111c2  test    rdx, rdx
0x1800111c5  cmovnz  rsi, rcx
0x1800111c9  mov     rcx, [rsp+88h]; this
0x1800111d1  jz      loc_18001142D
0x1800111d7  mov     eax, 80070216h
0x1800111dc  mov     edi, r13d
0x1800111df  cmp     esi, 7FFFFFFFh
0x1800111e5  cmova   edi, eax
0x1800111e8  mov     rcx, [rsp+88h]; this
0x1800111f0  test    edi, edi
0x1800111f2  js      loc_1800112D8
0x1800111f8  mov     ebp, [r12+10h]
0x1800111fd  lea     eax, [rbp-1]
0x180011200  mov     ecx, r13d
0x180011203  test    ebp, ebp
0x180011205  cmovnz  ecx, eax
0x180011208  cmp     esi, ecx
0x18001120a  ja      loc_18001130A
0x180011210  cmp     ecx, 20h ; ' '
0x180011213  ja      loc_18001130A
0x180011219  mov     edx, [r12+10h]
0x18001121e  lea     eax, [rdx-1]
0x180011221  mov     ecx, r13d
0x180011224  test    edx, edx
0x180011226  cmovnz  ecx, eax
0x180011229  cmp     esi, ecx
0x18001122b  ja      loc_1800113F8
0x180011231  mov     [r12], esi
0x180011235  test    esi, esi
0x180011237  jz      short loc_180011245
0x180011239  mov     edx, esi
0x18001123b  mov     rcx, [r12+8]
0x180011240  mov     [rcx+rdx*2], r13w
0x180011245  mov     edi, r13d
0x180011248  mov     rcx, [rsp+88h]; this
0x180011250  test    edi, edi
0x180011252  js      loc_1800112F1
0x180011258  lea     r8d, [rsi+rsi]; Size
0x18001125c  mov     rdx, r14; Src
0x18001125f  mov     rcx, [r12+8]; void *
0x180011264  call    memcpy_0
0x180011269  mov     edi, r13d
0x18001126c  mov     rcx, [rsp+88h]; this
0x180011274  test    edi, edi
0x180011276  js      short loc_1800112BF
0x180011278  test    r15, r15
0x18001127b  jz      loc_180011158
0x180011281  mov     dword ptr [r15], 1
0x180011288  jmp     loc_180011158
0x18001128d  mov     r9d, edi; char *
0x180011290  lea     r8, aOnecoreAdminAp_120; "onecore\\admin\\appmodel\\common\\xmlto"...
0x180011297  mov     edx, 134h; void *
0x18001129c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800112a1  jmp     loc_180011158
0x1800112a6  mov     r9d, eax; char *
0x1800112a9  lea     r8, aOnecoreAdminAp_120; "onecore\\admin\\appmodel\\common\\xmlto"...
0x1800112b0  mov     edx, 135h; void *
0x1800112b5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800112ba  jmp     loc_180011158
0x1800112bf  mov     r9d, edi; char *
0x1800112c2  lea     r8, aOnecoreAdminAp_120; "onecore\\admin\\appmodel\\common\\xmlto"...
0x1800112c9  mov     edx, 13Dh; void *
0x1800112ce  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800112d3  jmp     loc_180011158
0x1800112d8  mov     r9d, edi; char *
0x1800112db  lea     r8, aOnecoreBaseApp_67; "onecore\\base\\appmodel\\common\\widest"...
0x1800112e2  mov     edx, 22Fh; void *
0x1800112e7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800112ec  jmp     loc_18001126C
0x1800112f1  mov     r9d, edi; char *
0x1800112f4  lea     r8, aOnecoreBaseApp_67; "onecore\\base\\appmodel\\common\\widest"...
0x1800112fb  mov     edx, 235h; void *
0x180011300  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180011305  jmp     loc_18001126C
0x18001130a  cmp     esi, 20h ; ' '
0x18001130d  ja      loc_1800113B7
0x180011313  mov     edi, 8
0x180011318  cmp     esi, edi
0x18001131a  jbe     short loc_180011322
0x18001131c  add     edi, edi
0x18001131e  cmp     edi, esi
0x180011320  jb      short loc_18001131C
0x180011322  cmp     edi, 3FFFFFFFh
0x180011328  ja      loc_1800113D5
0x18001132e  test    edi, edi
0x180011330  jz      loc_180011446
0x180011336  lea     r15d, [rdi+1]
0x18001133a  cmp     r15d, ebp
0x18001133d  jz      short loc_180011379
0x18001133f  mov     r12, [r12+8]
0x180011344  ja      loc_180011468
0x18001134a  mov     r14, r12
0x18001134d  mov     r12, [rsp+88h+arg_10]
0x180011355  mov     [r12+10h], r15d
0x18001135a  mov     [r12+8], r14
0x18001135f  mov     eax, [r12]
0x180011363  cmp     eax, edi
0x180011365  ja      short loc_1800113C8
0x180011367  jnb     short loc_180011371
0x180011369  test    eax, eax
0x18001136b  jnz     short loc_180011371
0x18001136d  mov     [r14], r13w
0x180011371  mov     r14, [rsp+88h+arg_0]
0x180011379  mov     r15, [rsp+88h+arg_18]
0x180011381  mov     edi, r13d
0x180011384  mov     rcx, [rsp+88h]; this
0x18001138c  test    edi, edi
0x18001138e  jns     loc_180011219
0x180011394  mov     r9d, edi; char *
0x180011397  lea     r8, aOnecoreBaseApp_67; "onecore\\base\\appmodel\\common\\widest"...
0x18001139e  mov     edx, 232h; void *
0x1800113a3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800113a8  jmp     loc_18001126C
0x1800113ad  mov     edi, 80070057h
0x1800113b2  jmp     loc_180011158
0x1800113b7  mov     edi, esi
0x1800113b9  jmp     loc_180011322
0x1800113be  mov     edi, 80070057h
0x1800113c3  jmp     loc_1800110F8
0x1800113c8  mov     [r12], edi
0x1800113cc  mov     ecx, edi
0x1800113ce  mov     [r14+rcx*2], r13w
0x1800113d3  jmp     short loc_180011371
0x1800113d5  mov     rcx, [rsp+88h]; this
0x1800113dd  mov     edi, 80070503h
0x1800113e2  mov     r9d, edi; char *
0x1800113e5  lea     r8, aOnecoreBaseApp_67; "onecore\\base\\appmodel\\common\\widest"...
0x1800113ec  mov     edx, 1A9h; void *
0x1800113f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800113f6  jmp     short loc_180011384
0x1800113f8  mov     edx, esi; unsigned int
0x1800113fa  mov     rcx, r12; this
0x1800113fd  call    ?SetCapacity@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetCapacity(ulong)
0x180011402  mov     edi, eax
0x180011404  mov     rcx, [rsp+88h]; this
0x18001140c  test    eax, eax
0x18001140e  jns     loc_180011231
0x180011414  mov     r9d, eax; char *
0x180011417  lea     r8, aOnecoreBaseApp_67; "onecore\\base\\appmodel\\common\\widest"...
0x18001141e  mov     edx, 20Ch; void *
0x180011423  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180011428  jmp     loc_180011248
0x18001142d  mov     r9d, edi; char *
0x180011430  lea     r8, aOnecoreBaseApp_67; "onecore\\base\\appmodel\\common\\widest"...
0x180011437  mov     edx, 249h; void *
0x18001143c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180011441  jmp     loc_18001126C
0x180011446  mov     rcx, [r12+8]; void *
0x18001144b  test    rcx, rcx
0x18001144e  jz      short loc_18001145E
0x180011450  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011455  mov     [r12+8], r13
0x18001145a  mov     [r12], r13d
0x18001145e  mov     [r12+10h], r13d
0x180011463  jmp     loc_180011381
0x180011468  mov     r13d, r15d
0x18001146b  mov     eax, 2
0x180011470  mul     r13
0x180011473  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001147a  cmovb   rax, rcx
0x18001147e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011485  mov     rcx, rax; unsigned __int64
0x180011488  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001148d  mov     r14, rax
0x180011490  test    rax, rax
0x180011493  jnz     short loc_1800114BB
0x180011495  mov     rcx, [rsp+88h]; this
0x18001149d  mov     r9d, 8007000Eh; char *
0x1800114a3  lea     r8, aOnecoreBaseApp_67; "onecore\\base\\appmodel\\common\\widest"...
0x1800114aa  mov     edx, 193h; void *
0x1800114af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800114b4  mov     edi, 8007000Eh
0x1800114b9  jmp     short loc_180011516
0x1800114bb  mov     r9, rbp
0x1800114be  add     r9, r9; SourceSize
0x1800114c1  lea     rdx, ds:0[r15*2]; DestinationSize
0x1800114c9  mov     r8, r12; Source
0x1800114cc  mov     rcx, r14; Destination
0x1800114cf  call    memcpy_s
0x1800114d4  mov     ebp, eax
0x1800114d6  test    eax, eax
0x1800114d8  jz      short loc_180011552
0x1800114da  mov     rcx, r14; void *
0x1800114dd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800114e2  mov     rcx, [rsp+88h]; this
0x1800114ea  mov     dword ptr [rsp+88h+var_60], ebp; char *
0x1800114ee  lea     rax, a0x08lx; "0x%08lx"
0x1800114f5  mov     qword ptr [rsp+88h+var_68], rax; int
0x1800114fa  mov     r9d, 80070057h; char *
  ... truncated ...
```
