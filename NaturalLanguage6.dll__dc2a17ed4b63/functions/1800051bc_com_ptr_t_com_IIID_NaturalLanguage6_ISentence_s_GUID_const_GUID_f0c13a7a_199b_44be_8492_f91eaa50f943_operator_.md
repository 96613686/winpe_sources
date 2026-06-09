# _com_ptr_t<_com_IIID<NaturalLanguage6::ISentence,&__s_GUID const _GUID_f0c13a7a_199b_44be_8492_f91eaa50f943>>::operator=<_variant_t>(_variant_t const &)

- ea: `0x1800051bc`
- end: `0x180005321`
- name: `??$?4V_variant_t@@@?$_com_ptr_t@V?$_com_IIID@UISentence@NaturalLanguage6@@$1?_GUID_f0c13a7a_199b_44be_8492_f91eaa50f943@@3U__s_GUID@@B@@@@QEAAAEAV0@AEBV_variant_t@@@Z`
- size: `357`
- prototype: `_QWORD *__fastcall(_QWORD *, const VARIANTARG *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005380`
- `0x18005c7e0`

## callees

- `0x180003894`
- `0x180005160`
- `0x1800051bc`
- `0x18002d6c0`
- `0x180036734`
- `0x1800367c0`
- `0x1800b0010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800052a6`
- `OLEAUT32!__imp_VariantInit` at `0x1800052e4`
- `OLEAUT32!__imp_VariantInit` at `0x1800052a6`
- `OLEAUT32!__imp_VariantInit` at `0x1800052e4`
- `OLEAUT32!__imp_VariantClear` at `0x180005316`
- `OLEAUT32!__imp_VariantClear` at `0x180005316`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800052ba`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800052f8`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800052ba`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800052f8`

## pseudocode

```c
_QWORD *__fastcall _com_ptr_t<_com_IIID<NaturalLanguage6::ISentence,&__s_GUID const _GUID_f0c13a7a_199b_44be_8492_f91eaa50f943>>::operator=<_variant_t>(
        _QWORD *a1,
        const VARIANTARG *a2)
{
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rbx
  __int64 (__fastcall ***llVal)(_QWORD, GUID *, __int64 *); // rcx
  HRESULT v6; // edi
  __int64 v7; // rbx
  VARIANTARG pvarg; // [rsp+20h] [rbp-38h] BYREF
  __int64 v10; // [rsp+68h] [rbp+10h] BYREF

  p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a2->llVal;
  if ( a2->vt == 9 )
  {
    v6 = _com_ptr_t<_com_IIID<NaturalLanguage6::ISentence,&__s_GUID const _GUID_f0c13a7a_199b_44be_8492_f91eaa50f943>>::_QueryInterface<IDispatch *>(
           a1,
           &a2->decVal.Lo32);
  }
  else if ( a2->vt == 13 )
  {
    llVal = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))p_llVal->llVal;
    if ( p_llVal->llVal )
    {
      v10 = 0;
      v6 = (**llVal)(llVal, &GUID_f0c13a7a_199b_44be_8492_f91eaa50f943, &v10);
      if ( v6 < 0 )
      {
        _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(a1);
        *a1 = 0;
      }
      else
      {
        v7 = v10;
        _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(a1);
        *a1 = v7;
      }
    }
    else
    {
      _com_ptr_t<_com_IIID<NaturalLanguage6::ISentence,&__s_GUID const _GUID_f0c13a7a_199b_44be_8492_f91eaa50f943>>::operator=(a1);
      v6 = -2147467262;
    }
  }
  else
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v6 = VariantChangeType(&pvarg, a2, 0, 9u);
    if ( v6 < 0
      || (v6 = _com_ptr_t<_com_IIID<NaturalLanguage6::ISentence,&__s_GUID const _GUID_f0c13a7a_199b_44be_8492_f91eaa50f943>>::_QueryInterface<IDispatch *>(
                 a1,
                 p_llVal),
          v6 < 0) )
    {
      if ( v6 == -2147467262 )
      {
        VariantInit(&pvarg);
        v6 = VariantChangeType(&pvarg, a2, 0, 0xDu);
        if ( v6 >= 0 )
          v6 = _com_ptr_t<_com_IIID<NaturalLanguage6::ISentence,&__s_GUID const _GUID_f0c13a7a_199b_44be_8492_f91eaa50f943>>::_QueryInterface<IUnknown *>(
                 a1,
                 p_llVal);
      }
    }
    VariantClear(&pvarg);
  }
  if ( (int)(v6 + 0x80000000) >= 0 && v6 != -2147467262 )
    _com_issue_error(v6);
  return a1;
}

```

## disassembly

```asm
0x1800051bc  mov     r11, rsp
0x1800051bf  mov     [r11+8], rbx
0x1800051c3  mov     [r11+18h], rsi
0x1800051c7  push    rdi
0x1800051c8  push    r14
0x1800051ca  push    r15
0x1800051cc  sub     rsp, 40h
0x1800051d0  mov     edi, 9
0x1800051d5  lea     rbx, [rdx+8]
0x1800051d9  mov     r14, rdx
0x1800051dc  mov     rsi, rcx
0x1800051df  cmp     [rdx], di
0x1800051e2  jz      loc_180005269
0x1800051e8  lea     r15d, [rdi+4]
0x1800051ec  cmp     [rdx], r15w
0x1800051f0  jnz     loc_180005292
0x1800051f6  mov     rcx, [rbx]
0x1800051f9  test    rcx, rcx
0x1800051fc  jz      loc_180005283
0x180005202  mov     qword ptr [r11+10h], 0
0x18000520a  lea     r8, [r11+10h]
0x18000520e  mov     rax, [rcx]
0x180005211  lea     rdx, _GUID_f0c13a7a_199b_44be_8492_f91eaa50f943
0x180005218  mov     rax, [rax]
0x18000521b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005220  mov     edi, eax
0x180005222  mov     rcx, rsi
0x180005225  test    eax, eax
0x180005227  js      short loc_180005275
0x180005229  mov     rbx, [rsp+58h+arg_8]
0x18000522e  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x180005233  mov     [rsi], rbx
0x180005236  mov     ecx, 80000000h
0x18000523b  lea     eax, [rdi+rcx]
0x18000523e  test    ecx, eax
0x180005240  jz      short loc_180005259
0x180005242  mov     rbx, [rsp+58h+arg_0]
0x180005247  mov     rax, rsi
0x18000524a  mov     rsi, [rsp+58h+arg_10]
0x18000524f  add     rsp, 40h
0x180005253  pop     r15
0x180005255  pop     r14
0x180005257  pop     rdi
0x180005258  retn
0x180005259  cmp     edi, 80004002h
0x18000525f  jz      short loc_180005242
0x180005261  mov     ecx, edi; int
0x180005263  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180005269  mov     rdx, rbx
0x18000526c  call    ??$_QueryInterface@PEAUIDispatch@@@?$_com_ptr_t@V?$_com_IIID@UISentence@NaturalLanguage6@@$1?_GUID_f0c13a7a_199b_44be_8492_f91eaa50f943@@3U__s_GUID@@B@@@@AEAAJAEBQEAUIDispatch@@@Z; _com_ptr_t<_com_IIID<NaturalLanguage6::ISentence,&__s_GUID const _GUID_f0c13a7a_199b_44be_8492_f91eaa50f943>>::_QueryInterface<IDispatch *>(IDispatch * const &)
0x180005271  mov     edi, eax
0x180005273  jmp     short loc_180005236
0x180005275  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18000527a  mov     qword ptr [rsi], 0
0x180005281  jmp     short loc_180005236
0x180005283  mov     rcx, rsi
0x180005286  call    ??4?$_com_ptr_t@V?$_com_IIID@UISentence@NaturalLanguage6@@$1?_GUID_f0c13a7a_199b_44be_8492_f91eaa50f943@@3U__s_GUID@@B@@@@QEAAAEAV0@PEAUISentence@NaturalLanguage6@@@Z; _com_ptr_t<_com_IIID<NaturalLanguage6::ISentence,&__s_GUID const _GUID_f0c13a7a_199b_44be_8492_f91eaa50f943>>::operator=(NaturalLanguage6::ISentence *)
0x18000528b  mov     edi, 80004002h
0x180005290  jmp     short loc_180005236
0x180005292  xorps   xmm0, xmm0
0x180005295  lea     rcx, [rsp+58h+pvarg]; pvarg
0x18000529a  xor     eax, eax
0x18000529c  movups  xmmword ptr [rsp+58h+pvarg], xmm0
0x1800052a1  mov     qword ptr [rsp+58h+pvarg+10h], rax
0x1800052a6  call    cs:__imp_VariantInit
0x1800052ac  mov     r9d, edi; vt
0x1800052af  lea     rcx, [rsp+58h+pvarg]; pvargDest
0x1800052b4  xor     r8d, r8d; wFlags
0x1800052b7  mov     rdx, r14; pvarSrc
0x1800052ba  call    cs:__imp_VariantChangeType
0x1800052c0  mov     edi, eax
0x1800052c2  test    eax, eax
0x1800052c4  js      short loc_1800052D7
0x1800052c6  mov     rdx, rbx
0x1800052c9  mov     rcx, rsi
0x1800052cc  call    ??$_QueryInterface@PEAUIDispatch@@@?$_com_ptr_t@V?$_com_IIID@UISentence@NaturalLanguage6@@$1?_GUID_f0c13a7a_199b_44be_8492_f91eaa50f943@@3U__s_GUID@@B@@@@AEAAJAEBQEAUIDispatch@@@Z; _com_ptr_t<_com_IIID<NaturalLanguage6::ISentence,&__s_GUID const _GUID_f0c13a7a_199b_44be_8492_f91eaa50f943>>::_QueryInterface<IDispatch *>(IDispatch * const &)
0x1800052d1  mov     edi, eax
0x1800052d3  test    eax, eax
0x1800052d5  jns     short loc_180005311
0x1800052d7  cmp     edi, 80004002h
0x1800052dd  jnz     short loc_180005311
0x1800052df  lea     rcx, [rsp+58h+pvarg]; pvarg
0x1800052e4  call    cs:__imp_VariantInit
0x1800052ea  mov     r9d, r15d; vt
0x1800052ed  lea     rcx, [rsp+58h+pvarg]; pvargDest
0x1800052f2  xor     r8d, r8d; wFlags
0x1800052f5  mov     rdx, r14; pvarSrc
0x1800052f8  call    cs:__imp_VariantChangeType
0x1800052fe  mov     edi, eax
0x180005300  test    eax, eax
0x180005302  js      short loc_180005311
0x180005304  mov     rdx, rbx
0x180005307  mov     rcx, rsi
0x18000530a  call    ??$_QueryInterface@PEAUIUnknown@@@?$_com_ptr_t@V?$_com_IIID@UISentence@NaturalLanguage6@@$1?_GUID_f0c13a7a_199b_44be_8492_f91eaa50f943@@3U__s_GUID@@B@@@@AEAAJAEBQEAUIUnknown@@@Z; _com_ptr_t<_com_IIID<NaturalLanguage6::ISentence,&__s_GUID const _GUID_f0c13a7a_199b_44be_8492_f91eaa50f943>>::_QueryInterface<IUnknown *>(IUnknown * const &)
0x18000530f  mov     edi, eax
0x180005311  lea     rcx, [rsp+58h+pvarg]; pvarg
0x180005316  call    cs:__imp_VariantClear
0x18000531c  jmp     loc_180005236
```
