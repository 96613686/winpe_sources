# _anonymous_namespace_::GetTaskFolder

- ea: `0x140046694`
- end: `0x140046a5f`
- name: `_anonymous_namespace_::GetTaskFolder`
- size: `971`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140046344`
- `0x140046bd8`
- `0x140046e20`

## callees

- `0x14000a6e4`
- `0x14003d008`
- `0x140046694`
- `0x1400471e4`
- `0x14005890c`
- `0x14005d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1400466da`
- `OLEAUT32!__imp_SysAllocString` at `0x14004673e`
- `OLEAUT32!__imp_SysAllocString` at `0x1400467b3`
- `OLEAUT32!__imp_SysAllocString` at `0x1400467e1`
- `OLEAUT32!__imp_SysAllocString` at `0x1400468e4`
- `OLEAUT32!__imp_SysAllocString` at `0x1400466da`
- `OLEAUT32!__imp_SysAllocString` at `0x14004673e`
- `OLEAUT32!__imp_SysAllocString` at `0x1400467b3`
- `OLEAUT32!__imp_SysAllocString` at `0x1400467e1`
- `OLEAUT32!__imp_SysAllocString` at `0x1400468e4`
- `OLEAUT32!__imp_SysFreeString` at `0x14004671a`
- `OLEAUT32!__imp_SysFreeString` at `0x140046785`
- `OLEAUT32!__imp_SysFreeString` at `0x140046835`
- `OLEAUT32!__imp_SysFreeString` at `0x140046948`
- `OLEAUT32!__imp_SysFreeString` at `0x14004671a`
- `OLEAUT32!__imp_SysFreeString` at `0x140046785`
- `OLEAUT32!__imp_SysFreeString` at `0x140046835`
- `OLEAUT32!__imp_SysFreeString` at `0x140046948`
- `OLEAUT32!__imp_VariantClear` at `0x140046840`
- `OLEAUT32!__imp_VariantClear` at `0x140046935`
- `OLEAUT32!__imp_VariantClear` at `0x140046840`
- `OLEAUT32!__imp_VariantClear` at `0x140046935`

## string_xrefs

- `0x1400469b7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400469c9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400469fb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400469a5`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1400469de`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x140046a10`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x140046a2d`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x140046a4d`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 *__fastcall anonymous_namespace_::GetTaskFolder(__int64 *a1, __int64 *a2, __int64 a3)
{
  __int64 v6; // rdi
  BSTR v7; // rax
  const char *v8; // r9
  OLECHAR *v9; // r14
  int v10; // edi
  __int64 v11; // r14
  BSTR v12; // rax
  const char *v13; // r9
  OLECHAR *v14; // rdi
  int v15; // eax
  _QWORD *v16; // rsi
  __int64 v17; // r14
  __int64 *v18; // rcx
  BSTR v19; // rax
  BSTR v20; // rax
  const char *v21; // r9
  OLECHAR *v22; // rdi
  int v23; // eax
  HRESULT v24; // eax
  _QWORD *v25; // rcx
  int v26; // eax
  __int64 *v27; // rdi
  __int64 v28; // rsi
  __int64 v29; // rcx
  BSTR v30; // rax
  int v31; // eax
  HRESULT v32; // eax
  __int64 *v33; // rcx
  int v35; // [rsp+28h] [rbp-59h]
  BSTR bstrString; // [rsp+40h] [rbp-41h] BYREF
  BSTR v37; // [rsp+48h] [rbp-39h]
  VARIANTARG pvarg; // [rsp+50h] [rbp-31h] BYREF
  VARIANTARG v39[2]; // [rsp+68h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]
  __int64 *v41; // [rsp+F0h] [rbp+6Fh] BYREF
  _QWORD *v42; // [rsp+100h] [rbp+7Fh] BYREF

  v41 = 0;
  v6 = *a2;
  v7 = SysAllocString(L"\\Microsoft\\Windows\\EnterpriseMgmt");
  v9 = v7;
  v42 = v7;
  if ( !v7 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x15F3,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v8);
  v10 = (*(__int64 (__fastcall **)(__int64 *, BSTR, __int64 **))(v6 + 56))(a2, v7, &v41);
  SysFreeString(v9);
  if ( v10 == -2147024894 )
  {
    v42 = 0;
    v11 = *a2;
    v12 = SysAllocString(L"\\Microsoft\\Windows");
    v14 = v12;
    v37 = v12;
    if ( !v12 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x15F3,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v13);
    v15 = (*(__int64 (__fastcall **)(__int64 *, BSTR, _QWORD **))(v11 + 56))(a2, v12, &v42);
    if ( v15 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x4F,
        (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
        (const char *)(unsigned int)v15,
        v35);
    SysFreeString(v14);
    v16 = v42;
    v17 = *v42;
    v18 = v41;
    if ( v41 )
    {
      v41 = 0;
      (*(void (__fastcall **)(__int64 *))(*v18 + 16))(v18);
    }
    v19 = SysAllocString(L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)");
    if ( !v19 )
      _com_issue_error(-2147024882);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)v19;
    v20 = SysAllocString(L"EnterpriseMgmt");
    v22 = v20;
    v37 = v20;
    if ( !v20 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x15F3,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v21);
    v39[0] = pvarg;
    v23 = (*(__int64 (__fastcall **)(_QWORD *, BSTR, VARIANTARG *, __int64 **))(v17 + 88))(v16, v20, v39, &v41);
    if ( v23 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x50,
        (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
        (const char *)(unsigned int)v23,
        v35);
    SysFreeString(v22);
    v24 = VariantClear(&pvarg);
    if ( v24 < 0 )
      _com_issue_error(v24);
    v10 = 0;
    v25 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v25 + 16LL))(v25);
    }
  }
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x55,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v10,
      v35);
  wil::make_bstr(&bstrString, a3);
  *a1 = 0;
  v26 = (*(__int64 (__fastcall **)(__int64 *, BSTR, __int64 *))(*v41 + 72))(v41, bstrString, a1);
  if ( v26 == -2147024894 )
  {
    v27 = v41;
    v28 = *v41;
    v29 = *a1;
    if ( *a1 )
    {
      *a1 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v30 = SysAllocString(L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)");
    if ( !v30 )
      _com_issue_error(-2147024882);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)v30;
    v39[0] = pvarg;
    v31 = (*(__int64 (__fastcall **)(__int64 *, BSTR, VARIANTARG *, __int64 *))(v28 + 88))(v27, bstrString, v39, a1);
    if ( v31 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x5D,
        (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
        (const char *)(unsigned int)v31,
        v35);
    v32 = VariantClear(&pvarg);
    if ( v32 < 0 )
      _com_issue_error(v32);
  }
  else if ( v26 < 0 )
  {
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x61,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v26,
      v35);
  }
  if ( bstrString )
    SysFreeString(bstrString);
  v33 = v41;
  if ( v41 )
  {
    v41 = 0;
    (*(void (__fastcall **)(__int64 *))(*v33 + 16))(v33);
  }
  return a1;
}

```

## disassembly

```asm
0x140046694  mov     rax, rsp
0x140046697  mov     [rax+8], rcx
0x14004669b  push    rbp
0x14004669c  push    rbx
0x14004669d  push    rsi
0x14004669e  push    rdi
0x14004669f  push    r12
0x1400466a1  push    r14
0x1400466a3  push    r15
0x1400466a5  lea     rbp, [rax-5Fh]
0x1400466a9  sub     rsp, 0A0h
0x1400466b0  movaps  xmmword ptr [rax-48h], xmm6
0x1400466b4  movaps  xmmword ptr [rax-58h], xmm7
0x1400466b8  mov     r12, r8
0x1400466bb  mov     rsi, rdx
0x1400466be  mov     rbx, rcx
0x1400466c1  mov     [rbp+57h+var_A0], 0
0x1400466c8  mov     [rbp+57h+arg_8], 0
0x1400466d0  mov     rdi, [rdx]
0x1400466d3  lea     rcx, aMicrosoftWindo_4; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x1400466da  call    cs:__imp_SysAllocString
0x1400466e0  mov     r14, rax
0x1400466e3  mov     [rbp+57h+arg_18], rax
0x1400466e7  mov     [rbp+57h+var_A0], 2
0x1400466ee  mov     rcx, [rbp+5Fh]; this
0x1400466f2  test    rax, rax
0x1400466f5  jz      loc_1400469B7
0x1400466fb  lea     r8, [rbp+57h+arg_8]
0x1400466ff  mov     rdx, rax
0x140046702  mov     rcx, rsi
0x140046705  mov     rax, [rdi+38h]
0x140046709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004670e  mov     edi, eax
0x140046710  xor     r15d, r15d
0x140046713  mov     [rbp+57h+var_A0], r15d
0x140046717  mov     rcx, r14; bstrString
0x14004671a  call    cs:__imp_SysFreeString
0x140046720  lea     r14d, [r15+8]
0x140046724  cmp     edi, 80070002h
0x14004672a  jnz     loc_140046870
0x140046730  mov     [rbp+57h+arg_18], r15
0x140046734  mov     r14, [rsi]
0x140046737  lea     rcx, aMicrosoftWindo; "\\Microsoft\\Windows"
0x14004673e  call    cs:__imp_SysAllocString
0x140046744  mov     rdi, rax
0x140046747  mov     [rbp+57h+var_90], rax
0x14004674b  mov     [rbp+57h+var_A0], 4
0x140046752  mov     rcx, [rbp+5Fh]; this
0x140046756  test    rax, rax
0x140046759  jz      loc_1400469C9
0x14004675f  lea     r8, [rbp+57h+arg_18]
0x140046763  mov     rdx, rax
0x140046766  mov     rcx, rsi
0x140046769  mov     rax, [r14+38h]
0x14004676d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046772  mov     rcx, [rbp+5Fh]; this
0x140046776  test    eax, eax
0x140046778  js      loc_1400469DB
0x14004677e  mov     [rbp+57h+var_A0], r15d
0x140046782  mov     rcx, rdi; bstrString
0x140046785  call    cs:__imp_SysFreeString
0x14004678b  mov     rsi, [rbp+57h+arg_18]
0x14004678f  mov     r14, [rsi]
0x140046792  mov     rcx, [rbp+57h+arg_8]
0x140046796  test    rcx, rcx
0x140046799  jz      short loc_1400467AC
0x14004679b  mov     [rbp+57h+arg_8], r15
0x14004679f  mov     rax, [rcx]
0x1400467a2  mov     rax, [rax+10h]
0x1400467a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400467ab  nop
0x1400467ac  lea     rcx, aDAOiciGaBaAOic_0; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x1400467b3  call    cs:__imp_SysAllocString
0x1400467b9  test    rax, rax
0x1400467bc  jz      loc_1400469F0
0x1400467c2  mov     r15d, 8
0x1400467c8  mov     word ptr [rbp+57h+pvarg], r15w
0x1400467cd  mov     qword ptr [rbp+57h+pvarg+8], rax
0x1400467d1  movups  xmm6, xmmword ptr [rbp+57h+pvarg]
0x1400467d5  movsd   xmm7, qword ptr [rbp+57h+pvarg+10h]
0x1400467da  lea     rcx, aEnterprisemgmt; "EnterpriseMgmt"
0x1400467e1  call    cs:__imp_SysAllocString
0x1400467e7  mov     rdi, rax
0x1400467ea  mov     [rbp+57h+var_90], rax
0x1400467ee  mov     [rbp+57h+var_A0], r15d
0x1400467f2  mov     rcx, [rbp+5Fh]; this
0x1400467f6  test    rax, rax
0x1400467f9  jz      loc_1400469FB
0x1400467ff  movaps  [rbp+57h+var_70], xmm6
0x140046803  movsd   [rbp+57h+var_60], xmm7
0x140046808  lea     r9, [rbp+57h+arg_8]
0x14004680c  lea     r8, [rbp+57h+var_70]
0x140046810  mov     rdx, rax
0x140046813  mov     rcx, rsi
0x140046816  mov     rax, [r14+58h]
0x14004681a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004681f  mov     rcx, [rbp+5Fh]; this
0x140046823  test    eax, eax
0x140046825  js      loc_140046A0D
0x14004682b  xor     r15d, r15d
0x14004682e  mov     [rbp+57h+var_A0], r15d
0x140046832  mov     rcx, rdi; bstrString
0x140046835  call    cs:__imp_SysFreeString
0x14004683b  nop
0x14004683c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x140046840  call    cs:__imp_VariantClear
0x140046846  test    eax, eax
0x140046848  js      loc_140046A22
0x14004684e  xor     edi, edi
0x140046850  mov     rcx, [rbp+57h+arg_18]
0x140046854  test    rcx, rcx
0x140046857  jz      short loc_14004686A
0x140046859  mov     [rbp+57h+arg_18], rdi
0x14004685d  mov     rax, [rcx]
0x140046860  mov     rax, [rax+10h]
0x140046864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046869  nop
0x14004686a  mov     r14d, 8
0x140046870  mov     rcx, [rbp+5Fh]; this
0x140046874  test    edi, edi
0x140046876  js      loc_140046A2A
0x14004687c  mov     rdx, r12
0x14004687f  lea     rcx, [rbp+57h+bstrString]
0x140046883  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x140046888  nop
0x140046889  mov     qword ptr [rbx], 0
0x140046890  or      r15d, 1
0x140046894  mov     [rbp+57h+var_A0], r15d
0x140046898  mov     rcx, [rbp+57h+arg_8]
0x14004689c  mov     rax, [rcx]
0x14004689f  mov     r8, rbx
0x1400468a2  mov     rdx, [rbp+57h+bstrString]
0x1400468a6  mov     rax, [rax+48h]
0x1400468aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400468af  cmp     eax, 80070002h
0x1400468b4  jnz     loc_140046990
0x1400468ba  mov     rdi, [rbp+57h+arg_8]
0x1400468be  mov     rsi, [rdi]
0x1400468c1  mov     rcx, [rbx]
0x1400468c4  test    rcx, rcx
0x1400468c7  jz      short loc_1400468DD
0x1400468c9  mov     qword ptr [rbx], 0
0x1400468d0  mov     rax, [rcx]
0x1400468d3  mov     rax, [rax+10h]
0x1400468d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400468dc  nop
0x1400468dd  lea     rcx, aDAOiciGaBaAOic_0; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x1400468e4  call    cs:__imp_SysAllocString
0x1400468ea  test    rax, rax
0x1400468ed  jz      loc_140046A3F
0x1400468f3  mov     word ptr [rbp+57h+pvarg], r14w
0x1400468f8  mov     qword ptr [rbp+57h+pvarg+8], rax
0x1400468fc  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x140046900  movaps  [rbp+57h+var_70], xmm0
0x140046904  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x140046909  movsd   [rbp+57h+var_60], xmm1
0x14004690e  mov     r9, rbx
0x140046911  lea     r8, [rbp+57h+var_70]
0x140046915  mov     rdx, [rbp+57h+bstrString]
0x140046919  mov     rcx, rdi
0x14004691c  mov     rax, [rsi+58h]
0x140046920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046925  mov     rcx, [rbp+5Fh]; this
0x140046929  test    eax, eax
0x14004692b  js      loc_140046A4A
0x140046931  lea     rcx, [rbp+57h+pvarg]; pvarg
0x140046935  call    cs:__imp_VariantClear
0x14004693b  test    eax, eax
0x14004693d  js      short loc_14004699A
0x14004693f  mov     rcx, [rbp+57h+bstrString]; bstrString
0x140046943  test    rcx, rcx
0x140046946  jz      short loc_14004694F
0x140046948  call    cs:__imp_SysFreeString
0x14004694e  nop
0x14004694f  mov     rcx, [rbp+57h+arg_8]
0x140046953  test    rcx, rcx
0x140046956  jz      short loc_14004696D
0x140046958  mov     [rbp+57h+arg_8], 0
0x140046960  mov     rax, [rcx]
0x140046963  mov     rax, [rax+10h]
0x140046967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004696c  nop
0x14004696d  mov     rax, rbx
0x140046970  lea     r11, [rsp+0D0h+var_30]
0x140046978  movaps  xmm6, xmmword ptr [r11-10h]
0x14004697d  movaps  xmm7, xmmword ptr [r11-20h]
0x140046982  mov     rsp, r11
0x140046985  pop     r15
0x140046987  pop     r14
0x140046989  pop     r12
0x14004698b  pop     rdi
0x14004698c  pop     rsi
0x14004698d  pop     rbx
0x14004698e  pop     rbp
0x14004698f  retn
0x140046990  mov     rcx, [rbp+5Fh]; this
0x140046994  test    eax, eax
0x140046996  js      short loc_1400469A2
0x140046998  jmp     short loc_14004693F
0x14004699a  mov     ecx, eax; int
0x14004699c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400469a2  mov     r9d, eax; char *
0x1400469a5  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400469ac  mov     edx, 61h ; 'a'; void *
0x1400469b1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400469b7  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400469be  mov     edx, 15F3h; void *
0x1400469c3  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1400469c9  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400469d0  mov     edx, 15F3h; void *
0x1400469d5  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1400469db  mov     r9d, eax; char *
0x1400469de  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400469e5  mov     edx, 4Fh ; 'O'; void *
0x1400469ea  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400469f0  mov     ecx, 8007000Eh; int
0x1400469f5  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400469fb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140046a02  mov     edx, 15F3h; void *
0x140046a07  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x140046a0d  mov     r9d, eax; char *
0x140046a10  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140046a17  mov     edx, 50h ; 'P'; void *
0x140046a1c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140046a22  mov     ecx, eax; int
0x140046a24  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140046a2a  mov     r9d, edi; char *
0x140046a2d  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140046a34  mov     edx, 55h ; 'U'; void *
0x140046a39  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140046a3f  mov     ecx, 8007000Eh; int
0x140046a44  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140046a4a  mov     r9d, eax; char *
0x140046a4d  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140046a54  mov     edx, 5Dh ; ']'; void *
0x140046a59  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
