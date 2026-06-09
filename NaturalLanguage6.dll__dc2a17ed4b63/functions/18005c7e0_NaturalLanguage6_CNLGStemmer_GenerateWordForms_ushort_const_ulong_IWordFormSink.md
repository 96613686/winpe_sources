# NaturalLanguage6::CNLGStemmer::GenerateWordForms(ushort const *,ulong,IWordFormSink *)

- ea: `0x18005c7e0`
- end: `0x18005caf5`
- name: `?GenerateWordForms@CNLGStemmer@NaturalLanguage6@@UEAAJPEBGKPEAUIWordFormSink@@@Z`
- size: `789`
- prototype: `int(NaturalLanguage6::CNLGStemmer *__hidden this, const unsigned __int16 *, unsigned int, struct IWordFormSink *)`
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003870`
- `0x180003e60`
- `0x180005160`
- `0x180005190`
- `0x1800051bc`
- `0x180005ad0`
- `0x18002bf50`
- `0x18002c2a0`
- `0x18002d9c0`
- `0x18005c7e0`
- `0x18005d41c`
- `0x1800b0010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18005c838`
- `OLEAUT32!__imp_VariantInit` at `0x18005c838`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall NaturalLanguage6::CNLGStemmer::GenerateWordForms(
        NaturalLanguage6::CNLGStemmer *this,
        unsigned __int16 *a2,
        int a3,
        struct IWordFormSink *a4)
{
  int v4; // esi
  __int64 result; // rax
  int v9; // r15d
  __int64 v10; // rax
  int v11; // r15d
  __int64 v12; // rax
  struct IUnknown *v13; // rax
  struct IUnknown *v14; // rax
  int Item; // eax
  int v16; // ebx
  _com_error *v17; // rbx
  __int64 v18; // [rsp+30h] [rbp-68h] BYREF
  __int64 v19; // [rsp+38h] [rbp-60h] BYREF
  _QWORD **v20; // [rsp+40h] [rbp-58h] BYREF
  _QWORD *v21; // [rsp+48h] [rbp-50h] BYREF
  __int64 v22; // [rsp+50h] [rbp-48h]
  VARIANTARG pvarg; // [rsp+58h] [rbp-40h] BYREF
  __int64 v24; // [rsp+70h] [rbp-28h]
  _com_error *v25; // [rsp+78h] [rbp-20h] BYREF
  void *retaddr; // [rsp+98h] [rbp+0h]
  int v27; // [rsp+B8h] [rbp+20h] BYREF

  v24 = -2;
  v4 = (int)a4;
  if ( !a4 )
    return 2147942487LL;
  if ( !*((_BYTE *)this + 56) )
    return 2147500037LL;
  try
  {
    v18 = 0;
    VariantInit(&pvarg);
    v27 = 0;
    v9 = NaturalLanguage6::ITextChunk::SetInputArray(*((struct IUnknown **)this + 4), a2, a3);
    if ( v9 < 0 )
    {
      _variant_t::~_variant_t(&pvarg);
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(&v18);
      return (unsigned int)v9;
    }
    LODWORD(v22) = 0;
    HIDWORD(v22) = a3;
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 4) + 80LL))(*((_QWORD *)this + 4), v22);
    NaturalLanguage6::ITextChunk::GetEnumerator(*((struct IUnknown **)this + 4));
    v10 = _com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>::operator->(&v19);
    v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 40LL))(v10);
    if ( v11 < 0 )
    {
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(&v19);
      _variant_t::~_variant_t(&pvarg);
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(&v18);
      return (unsigned int)v11;
    }
    v12 = _com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>::operator->(&v19);
    (*(void (__fastcall **)(__int64, __int64, VARIANTARG *, int *))(*(_QWORD *)v12 + 24LL))(v12, 1, &pvarg, &v27);
    if ( v27 )
    {
      _com_ptr_t<_com_IIID<NaturalLanguage6::ISentence,&__s_GUID const _GUID_f0c13a7a_199b_44be_8492_f91eaa50f943>>::operator=<_variant_t>(
        &v18,
        &pvarg);
      _variant_t::Clear((_variant_t *)&pvarg);
      v13 = (struct IUnknown *)_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>::operator->(&v18);
      if ( (unsigned int)NaturalLanguage6::ISentence::GetCount(v13) == 1 )
      {
        v21 = &v20;
        v14 = (struct IUnknown *)_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>::operator->(&v18);
        Item = NaturalLanguage6::ISentence::GetItem(v14);
        v16 = NaturalLanguage6::CNLGStemmer::PutSegment((_DWORD)this, (_DWORD)a2, a3, v4, Item, 1);
      }
      else
      {
        v20 = &v21;
        v21 = 0;
        v16 = NaturalLanguage6::CNLGStemmer::PutSegment((_DWORD)this, (_DWORD)a2, a3, v4, (unsigned int)&v21, 0);
      }
      goto LABEL_12;
    }
    v21 = &v20;
    v20 = 0;
    v16 = NaturalLanguage6::CNLGStemmer::PutSegment((_DWORD)this, (_DWORD)a2, a3, v4, (unsigned int)&v20, 0);
    if ( v16 >= 0 )
    {
LABEL_12:
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(&v19);
      _variant_t::~_variant_t(&pvarg);
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(&v18);
      return (unsigned int)v16;
    }
    _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(&v19);
    _variant_t::~_variant_t(&pvarg);
    _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(&v18);
    result = (unsigned int)v16;
  }
  catch ( _com_error *v25 )
  {
    v17 = v25;
    ImxTraceCatch(1, *((unsigned int *)v25 + 2), retaddr);
    return *((unsigned int *)v17 + 2);
  }
  catch ( exception )
  {
    ImxTraceCatch(2, 2147500037LL, retaddr);
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x18005c7e0  mov     rax, rsp
0x18005c7e3  push    rdi
0x18005c7e4  push    r14
0x18005c7e6  push    r15
0x18005c7e8  sub     rsp, 80h
0x18005c7ef  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x18005c7f7  mov     [rax+8], rbx
0x18005c7fb  mov     [rax+10h], rsi
0x18005c7ff  mov     rsi, r9
0x18005c802  mov     edi, r8d
0x18005c805  mov     r14, rdx
0x18005c808  mov     rbx, rcx
0x18005c80b  test    r9, r9
0x18005c80e  jnz     short loc_18005C81A
0x18005c810  mov     eax, 80070057h
0x18005c815  jmp     loc_18005CADB
0x18005c81a  cmp     byte ptr [rcx+38h], 0
0x18005c81e  jnz     short loc_18005C82A
0x18005c820  mov     eax, 80004005h
0x18005c825  jmp     loc_18005CADB
0x18005c82a  mov     [rsp+98h+var_68], 0
0x18005c833  lea     rcx, [rsp+98h+pvarg]; pvarg
0x18005c838  call    cs:__imp_VariantInit
0x18005c83e  nop
0x18005c83f  mov     [rsp+98h+arg_18], 0
0x18005c84a  mov     r8d, edi; int
0x18005c84d  mov     rdx, r14; unsigned __int16 *
0x18005c850  mov     rcx, [rbx+20h]; this
0x18005c854  call    ?SetInputArray@ITextChunk@NaturalLanguage6@@QEAAJPEAGJ@Z; NaturalLanguage6::ITextChunk::SetInputArray(ushort *,long)
0x18005c859  mov     r15d, eax
0x18005c85c  test    eax, eax
0x18005c85e  jns     short loc_18005C87D
0x18005c860  lea     rcx, [rsp+98h+pvarg]; this
0x18005c865  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005c86a  nop
0x18005c86b  lea     rcx, [rsp+98h+var_68]
0x18005c870  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18005c875  mov     eax, r15d
0x18005c878  jmp     loc_18005CADB
0x18005c87d  mov     [rsp+98h+var_48], 0
0x18005c886  mov     dword ptr [rsp+98h+var_48], 0
0x18005c88e  mov     dword ptr [rsp+98h+var_48+4], edi
0x18005c892  mov     rcx, [rbx+20h]
0x18005c896  mov     rax, [rcx]
0x18005c899  mov     rdx, [rsp+98h+var_48]
0x18005c89e  mov     rax, [rax+50h]
0x18005c8a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c8a7  lea     rdx, [rsp+98h+var_60]
0x18005c8ac  mov     rcx, [rbx+20h]; struct IUnknown *
0x18005c8b0  call    ?GetEnumerator@ITextChunk@NaturalLanguage6@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIEnumVARIANT@@$1?_GUID_00020404_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@XZ; NaturalLanguage6::ITextChunk::GetEnumerator(void)
0x18005c8b5  nop
0x18005c8b6  lea     rcx, [rsp+98h+var_60]
0x18005c8bb  call    ??C?$_com_ptr_t@V?$_com_IIID@UITextSegment@NaturalLanguage6@@$1?_GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56@@3U__s_GUID@@B@@@@QEBAPEAUITextSegment@NaturalLanguage6@@XZ; _com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>::operator->(void)
0x18005c8c0  mov     rdx, rax
0x18005c8c3  mov     rcx, [rax]
0x18005c8c6  mov     rax, [rcx+28h]
0x18005c8ca  mov     rcx, rdx
0x18005c8cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c8d2  mov     r15d, eax
0x18005c8d5  test    eax, eax
0x18005c8d7  jns     short loc_18005C901
0x18005c8d9  lea     rcx, [rsp+98h+var_60]
0x18005c8de  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18005c8e3  nop
0x18005c8e4  lea     rcx, [rsp+98h+pvarg]; this
0x18005c8e9  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005c8ee  nop
0x18005c8ef  lea     rcx, [rsp+98h+var_68]
0x18005c8f4  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18005c8f9  mov     eax, r15d
0x18005c8fc  jmp     loc_18005CADB
0x18005c901  lea     rcx, [rsp+98h+var_60]
0x18005c906  call    ??C?$_com_ptr_t@V?$_com_IIID@UITextSegment@NaturalLanguage6@@$1?_GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56@@3U__s_GUID@@B@@@@QEBAPEAUITextSegment@NaturalLanguage6@@XZ; _com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>::operator->(void)
0x18005c90b  mov     r10, rax
0x18005c90e  mov     rcx, [rax]
0x18005c911  mov     rax, [rcx+18h]
0x18005c915  lea     r9, [rsp+98h+arg_18]
0x18005c91d  lea     r8, [rsp+98h+pvarg]
0x18005c922  mov     r15d, 1
0x18005c928  mov     edx, r15d
0x18005c92b  mov     rcx, r10
0x18005c92e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c933  cmp     [rsp+98h+arg_18], 0
0x18005c93b  jz      loc_18005CA49
0x18005c941  lea     rdx, [rsp+98h+pvarg]
0x18005c946  lea     rcx, [rsp+98h+var_68]
0x18005c94b  call    ??$?4V_variant_t@@@?$_com_ptr_t@V?$_com_IIID@UISentence@NaturalLanguage6@@$1?_GUID_f0c13a7a_199b_44be_8492_f91eaa50f943@@3U__s_GUID@@B@@@@QEAAAEAV0@AEBV_variant_t@@@Z; _com_ptr_t<_com_IIID<NaturalLanguage6::ISentence,&__s_GUID const _GUID_f0c13a7a_199b_44be_8492_f91eaa50f943>>::operator=<_variant_t>(_variant_t const &)
0x18005c950  lea     rcx, [rsp+98h+pvarg]; this
0x18005c955  call    ?Clear@_variant_t@@QEAAXXZ; _variant_t::Clear(void)
0x18005c95a  lea     rcx, [rsp+98h+var_68]
0x18005c95f  call    ??C?$_com_ptr_t@V?$_com_IIID@UITextSegment@NaturalLanguage6@@$1?_GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56@@3U__s_GUID@@B@@@@QEBAPEAUITextSegment@NaturalLanguage6@@XZ; _com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>::operator->(void)
0x18005c964  mov     rcx, rax; this
0x18005c967  call    ?GetCount@ISentence@NaturalLanguage6@@QEAAJXZ; NaturalLanguage6::ISentence::GetCount(void)
0x18005c96c  cmp     eax, r15d
0x18005c96f  jnz     short loc_18005C9E2
0x18005c971  lea     rax, [rsp+98h+var_58]
0x18005c976  mov     [rsp+98h+var_50], rax
0x18005c97b  lea     rcx, [rsp+98h+var_68]
0x18005c980  call    ??C?$_com_ptr_t@V?$_com_IIID@UITextSegment@NaturalLanguage6@@$1?_GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56@@3U__s_GUID@@B@@@@QEBAPEAUITextSegment@NaturalLanguage6@@XZ; _com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>::operator->(void)
0x18005c985  xor     r8d, r8d
0x18005c988  lea     rdx, [rsp+98h+var_58]
0x18005c98d  mov     rcx, rax; struct IUnknown *
0x18005c990  call    ?GetItem@ISentence@NaturalLanguage6@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UITextSegment@NaturalLanguage6@@$1?_GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56@@3U__s_GUID@@B@@@@J@Z; NaturalLanguage6::ISentence::GetItem(long)
0x18005c995  nop
0x18005c996  mov     [rsp+98h+var_70], r15d
0x18005c99b  mov     [rsp+98h+var_78], rax
0x18005c9a0  mov     r9, rsi
0x18005c9a3  mov     r8d, edi
0x18005c9a6  mov     rdx, r14
0x18005c9a9  mov     rcx, rbx
0x18005c9ac  call    ?PutSegment@CNLGStemmer@NaturalLanguage6@@AEAAJPEBGKPEAUIWordFormSink@@V?$_com_ptr_t@V?$_com_IIID@UITextSegment@NaturalLanguage6@@$1?_GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56@@3U__s_GUID@@B@@@@J@Z; NaturalLanguage6::CNLGStemmer::PutSegment(ushort const *,ulong,IWordFormSink *,_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>,long)
0x18005c9b1  mov     ebx, eax
0x18005c9b3  test    eax, eax
0x18005c9b5  jns     loc_18005CAA9
0x18005c9bb  lea     rcx, [rsp+98h+var_60]
0x18005c9c0  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18005c9c5  nop
0x18005c9c6  lea     rcx, [rsp+98h+pvarg]; this
0x18005c9cb  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005c9d0  nop
0x18005c9d1  lea     rcx, [rsp+98h+var_68]
0x18005c9d6  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18005c9db  mov     eax, ebx
0x18005c9dd  jmp     loc_18005CADB
0x18005c9e2  lea     rax, [rsp+98h+var_50]
0x18005c9e7  mov     [rsp+98h+var_58], rax
0x18005c9ec  mov     [rsp+98h+var_50], 0
0x18005c9f5  mov     [rsp+98h+var_70], 0
0x18005c9fd  lea     rax, [rsp+98h+var_50]
0x18005ca02  mov     [rsp+98h+var_78], rax
0x18005ca07  mov     r9, rsi
0x18005ca0a  mov     r8d, edi
0x18005ca0d  mov     rdx, r14
0x18005ca10  mov     rcx, rbx
0x18005ca13  call    ?PutSegment@CNLGStemmer@NaturalLanguage6@@AEAAJPEBGKPEAUIWordFormSink@@V?$_com_ptr_t@V?$_com_IIID@UITextSegment@NaturalLanguage6@@$1?_GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56@@3U__s_GUID@@B@@@@J@Z; NaturalLanguage6::CNLGStemmer::PutSegment(ushort const *,ulong,IWordFormSink *,_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>,long)
0x18005ca18  mov     ebx, eax
0x18005ca1a  test    eax, eax
0x18005ca1c  jns     loc_18005CAA9
0x18005ca22  lea     rcx, [rsp+98h+var_60]
0x18005ca27  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18005ca2c  nop
0x18005ca2d  lea     rcx, [rsp+98h+pvarg]; this
0x18005ca32  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005ca37  nop
0x18005ca38  lea     rcx, [rsp+98h+var_68]
0x18005ca3d  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18005ca42  mov     eax, ebx
0x18005ca44  jmp     loc_18005CADB
0x18005ca49  lea     rax, [rsp+98h+var_58]
0x18005ca4e  mov     [rsp+98h+var_50], rax
0x18005ca53  mov     [rsp+98h+var_58], 0
0x18005ca5c  mov     [rsp+98h+var_70], 0
0x18005ca64  lea     rax, [rsp+98h+var_58]
0x18005ca69  mov     [rsp+98h+var_78], rax
0x18005ca6e  mov     r9, rsi
0x18005ca71  mov     r8d, edi
0x18005ca74  mov     rdx, r14
0x18005ca77  mov     rcx, rbx
0x18005ca7a  call    ?PutSegment@CNLGStemmer@NaturalLanguage6@@AEAAJPEBGKPEAUIWordFormSink@@V?$_com_ptr_t@V?$_com_IIID@UITextSegment@NaturalLanguage6@@$1?_GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56@@3U__s_GUID@@B@@@@J@Z; NaturalLanguage6::CNLGStemmer::PutSegment(ushort const *,ulong,IWordFormSink *,_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>,long)
0x18005ca7f  mov     ebx, eax
0x18005ca81  test    eax, eax
0x18005ca83  jns     short loc_18005CAA9
0x18005ca85  lea     rcx, [rsp+98h+var_60]
0x18005ca8a  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18005ca8f  nop
0x18005ca90  lea     rcx, [rsp+98h+pvarg]; this
0x18005ca95  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005ca9a  nop
0x18005ca9b  lea     rcx, [rsp+98h+var_68]
0x18005caa0  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18005caa5  mov     eax, ebx
0x18005caa7  jmp     short loc_18005CADB
0x18005caa9  lea     rcx, [rsp+98h+var_60]
0x18005caae  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18005cab3  nop
0x18005cab4  lea     rcx, [rsp+98h+pvarg]; this
0x18005cab9  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005cabe  nop
0x18005cabf  lea     rcx, [rsp+98h+var_68]
0x18005cac4  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18005cac9  mov     eax, ebx
0x18005cacb  jmp     short loc_18005CADB
0x18005cacd  mov     eax, [rsp+98h+arg_18]
0x18005cad4  jmp     short loc_18005CADB
0x18005cad6  mov     eax, 80004005h
0x18005cadb  lea     r11, [rsp+98h+var_18]
0x18005cae3  mov     rbx, [r11+20h]
0x18005cae7  mov     rsi, [r11+28h]
0x18005caeb  mov     rsp, r11
0x18005caee  pop     r15
0x18005caf0  pop     r14
0x18005caf2  pop     rdi
0x18005caf3  retn
```
