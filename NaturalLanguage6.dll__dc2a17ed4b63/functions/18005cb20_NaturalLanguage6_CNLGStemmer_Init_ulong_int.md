# NaturalLanguage6::CNLGStemmer::Init(ulong,int *)

- ea: `0x18005cb20`
- end: `0x18005d3b1`
- name: `?Init@CNLGStemmer@NaturalLanguage6@@UEAAJKPEAH@Z`
- size: `2193`
- prototype: `__int64 __fastcall(NaturalLanguage6::CNLGStemmer *__hidden this, unsigned int, int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180005160`
- `0x180005190`
- `0x180016380`
- `0x1800164fc`
- `0x18001681c`
- `0x180017910`
- `0x180019a6c`
- `0x180019ae8`
- `0x180030a3c`
- `0x180030c5c`
- `0x18005cb20`
- `0x1800b0010`

## string_xrefs

- `0x18005d112`: `IsComputingExpansions`
- `0x18005d092`: `IsComputingBases`

## pseudocode

```c
// Hidden C++ exception states: #wind=47
__int64 __fastcall NaturalLanguage6::CNLGStemmer::Init(NaturalLanguage6::CNLGStemmer *this, int a2, int *a3)
{
  int *v3; // r12
  NaturalLanguage6::CNLGStemmer *v4; // rsi
  __int64 result; // rax
  int v6; // eax
  struct IUnknown **v7; // rdi
  struct IUnknown *v8; // rax
  struct IUnknown *v9; // rcx
  __int64 *Options; // rax
  struct IUnknown *v11; // r14
  __int64 *v12; // rax
  struct IUnknown *v13; // r14
  __int64 *v14; // rax
  struct IUnknown *v15; // r14
  __int64 *v16; // rax
  struct IUnknown *v17; // r14
  __int64 *v18; // rax
  struct IUnknown *v19; // r14
  __int64 *v20; // rax
  struct IUnknown *v21; // r14
  __int64 *v22; // rax
  struct IUnknown *v23; // r14
  __int64 *v24; // rax
  struct IUnknown *v25; // r14
  __int64 *v26; // rax
  struct IUnknown *v27; // r14
  __int64 *v28; // rax
  struct IUnknown *v29; // r14
  __int64 *v30; // rax
  struct IUnknown *v31; // r14
  __int64 *v32; // rax
  struct IUnknown *v33; // r15
  __int64 *v34; // rax
  struct IUnknown *v35; // r15
  __int64 *v36; // rax
  struct IUnknown *v37; // r15
  __int64 *v38; // rax
  struct IUnknown *v39; // r15
  unsigned __int64 v40; // rcx
  struct IUnknown *v41; // rax
  __int64 v42; // rcx
  _com_error *v43; // rbx
  VARIANTARG v44; // [rsp+20h] [rbp-1C8h] BYREF
  VARIANTARG v45; // [rsp+38h] [rbp-1B0h] BYREF
  struct IUnknown **v46; // [rsp+50h] [rbp-198h]
  VARIANTARG v47; // [rsp+58h] [rbp-190h] BYREF
  VARIANTARG v48; // [rsp+70h] [rbp-178h] BYREF
  VARIANTARG v49; // [rsp+88h] [rbp-160h] BYREF
  VARIANTARG v50; // [rsp+A0h] [rbp-148h] BYREF
  VARIANTARG v51; // [rsp+B8h] [rbp-130h] BYREF
  VARIANTARG v52; // [rsp+D0h] [rbp-118h] BYREF
  VARIANTARG v53; // [rsp+E8h] [rbp-100h] BYREF
  VARIANTARG v54; // [rsp+100h] [rbp-E8h] BYREF
  VARIANTARG v55; // [rsp+118h] [rbp-D0h] BYREF
  VARIANTARG v56; // [rsp+130h] [rbp-B8h] BYREF
  VARIANTARG v57; // [rsp+148h] [rbp-A0h] BYREF
  VARIANTARG v58; // [rsp+160h] [rbp-88h] BYREF
  VARIANTARG v59; // [rsp+178h] [rbp-70h] BYREF
  __int64 v60; // [rsp+190h] [rbp-58h]
  _com_error *v61; // [rsp+198h] [rbp-50h] BYREF
  _com_error *v62; // [rsp+1A0h] [rbp-48h] BYREF
  void *retaddr; // [rsp+1E8h] [rbp+0h]
  struct IUnknown *v66; // [rsp+208h] [rbp+20h] BYREF

  v60 = -2;
  v3 = a3;
  v4 = this;
  if ( !a3 )
    return 2147942487LL;
  try
  {
    v6 = 1;
    if ( a2 )
      v6 = a2;
    *((_DWORD *)this + 5) = v6;
    v7 = (struct IUnknown **)((char *)this + 24);
    v46 = (struct IUnknown **)((char *)this + 24);
    if ( !*((_QWORD *)this + 3) )
    {
      v8 = (struct IUnknown *)NaturalLanguage6::TextContext::operator new((unsigned __int64)this);
      v66 = v8;
      if ( v8 )
        v9 = NaturalLanguage6::TextContext::TextContext(v8);
      else
        v9 = 0;
      *v7 = v9;
      ((void (__fastcall *)(struct IUnknown *))v9->lpVtbl->AddRef)(v9);
    }
    try
    {
      Options = (__int64 *)NaturalLanguage6::ITextContext::GetOptions(*v7);
      v11 = (struct IUnknown *)_com_ptr_t<_com_IIID<NaturalLanguage6::IProcessingOptions,&__s_GUID const _GUID_c090356b_a6a5_442a_a204_cfd5415b5902>>::operator->(Options);
      v47.vt = 11;
      v47.iVal = 0;
      _variant_t::_variant_t((_variant_t *)&v44, L"IsShowingGaps");
      NaturalLanguage6::IProcessingOptions::PutItem(
        v11,
        (const struct _variant_t *)&v44,
        (const struct _variant_t *)&v47);
      _variant_t::~_variant_t(&v44);
      _variant_t::~_variant_t(&v47);
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>((__int64 *)&v66);
      v12 = (__int64 *)NaturalLanguage6::ITextContext::GetOptions(*v7);
      v13 = (struct IUnknown *)_com_ptr_t<_com_IIID<NaturalLanguage6::IProcessingOptions,&__s_GUID const _GUID_c090356b_a6a5_442a_a204_cfd5415b5902>>::operator->(v12);
      v48.vt = 11;
      v48.iVal = 0;
      _variant_t::_variant_t((_variant_t *)&v44, L"IsShowingCharacterNormalizations");
      NaturalLanguage6::IProcessingOptions::PutItem(
        v13,
        (const struct _variant_t *)&v44,
        (const struct _variant_t *)&v48);
      _variant_t::~_variant_t(&v44);
      _variant_t::~_variant_t(&v48);
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>((__int64 *)&v66);
      v14 = (__int64 *)NaturalLanguage6::ITextContext::GetOptions(*v7);
      v15 = (struct IUnknown *)_com_ptr_t<_com_IIID<NaturalLanguage6::IProcessingOptions,&__s_GUID const _GUID_c090356b_a6a5_442a_a204_cfd5415b5902>>::operator->(v14);
      v49.vt = 11;
      v49.iVal = 0;
      _variant_t::_variant_t((_variant_t *)&v44, L"IsShowingWordNormalizations");
      NaturalLanguage6::IProcessingOptions::PutItem(
        v15,
        (const struct _variant_t *)&v44,
        (const struct _variant_t *)&v49);
      _variant_t::~_variant_t(&v44);
      _variant_t::~_variant_t(&v49);
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>((__int64 *)&v66);
      v16 = (__int64 *)NaturalLanguage6::ITextContext::GetOptions(*v7);
      v17 = (struct IUnknown *)_com_ptr_t<_com_IIID<NaturalLanguage6::IProcessingOptions,&__s_GUID const _GUID_c090356b_a6a5_442a_a204_cfd5415b5902>>::operator->(v16);
      v50.vt = 11;
      v50.iVal = 0;
      _variant_t::_variant_t((_variant_t *)&v44, L"IsSpellChecking");
      NaturalLanguage6::IProcessingOptions::PutItem(
        v17,
        (const struct _variant_t *)&v44,
        (const struct _variant_t *)&v50);
      _variant_t::~_variant_t(&v44);
      _variant_t::~_variant_t(&v50);
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>((__int64 *)&v66);
      v18 = (__int64 *)NaturalLanguage6::ITextContext::GetOptions(*v7);
      v19 = (struct IUnknown *)_com_ptr_t<_com_IIID<NaturalLanguage6::IProcessingOptions,&__s_GUID const _GUID_c090356b_a6a5_442a_a204_cfd5415b5902>>::operator->(v18);
      v51.vt = 11;
      v51.iVal = 0;
      _variant_t::_variant_t((_variant_t *)&v44, L"IsSpellSuggestingMWEs");
      NaturalLanguage6::IProcessingOptions::PutItem(
        v19,
        (const struct _variant_t *)&v44,
        (const struct _variant_t *)&v51);
      _variant_t::~_variant_t(&v44);
      _variant_t::~_variant_t(&v51);
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>((__int64 *)&v66);
      v20 = (__int64 *)NaturalLanguage6::ITextContext::GetOptions(*v7);
      v21 = (struct IUnknown *)_com_ptr_t<_com_IIID<NaturalLanguage6::IProcessingOptions,&__s_GUID const _GUID_c090356b_a6a5_442a_a204_cfd5415b5902>>::operator->(v20);
      v52.vt = 11;
      v52.iVal = 0;
      _variant_t::_variant_t((_variant_t *)&v44, L"IsIgnoreMixedDigits");
      NaturalLanguage6::IProcessingOptions::PutItem(
        v21,
        (const struct _variant_t *)&v44,
        (const struct _variant_t *)&v52);
      _variant_t::~_variant_t(&v44);
      _variant_t::~_variant_t(&v52);
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>((__int64 *)&v66);
      v22 = (__int64 *)NaturalLanguage6::ITextContext::GetOptions(*v7);
      v23 = (struct IUnknown *)_com_ptr_t<_com_IIID<NaturalLanguage6::IProcessingOptions,&__s_GUID const _GUID_c090356b_a6a5_442a_a204_cfd5415b5902>>::operator->(v22);
      v53.vt = 11;
      v53.iVal = 0;
      _variant_t::_variant_t((_variant_t *)&v44, L"IsFindingDateTimeMeasures");
      NaturalLanguage6::IProcessingOptions::PutItem(
        v23,
        (const struct _variant_t *)&v44,
        (const struct _variant_t *)&v53);
      _variant_t::~_variant_t(&v44);
      _variant_t::~_variant_t(&v53);
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>((__int64 *)&v66);
      v24 = (__int64 *)NaturalLanguage6::ITextContext::GetOptions(*v7);
      v25 = (struct IUnknown *)_com_ptr_t<_com_IIID<NaturalLanguage6::IProcessingOptions,&__s_GUID const _GUID_c090356b_a6a5_442a_a204_cfd5415b5902>>::operator->(v24);
      v54.vt = 11;
      v54.iVal = 0;
      _variant_t::_variant_t((_variant_t *)&v44, L"IsFindingLocations");
      NaturalLanguage6::IProcessingOptions::PutItem(
        v25,
        (const struct _variant_t *)&v44,
        (const struct _variant_t *)&v54);
      _variant_t::~_variant_t(&v44);
      _variant_t::~_variant_t(&v54);
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>((__int64 *)&v66);
      v26 = (__int64 *)NaturalLanguage6::ITextContext::GetOptions(*v7);
      v27 = (struct IUnknown *)_com_ptr_t<_com_IIID<NaturalLanguage6::IProcessingOptions,&__s_GUID const _GUID_c090356b_a6a5_442a_a204_cfd5415b5902>>::operator->(v26);
      v55.vt = 11;
      v55.iVal = 0;
      _variant_t::_variant_t((_variant_t *)&v44, L"IsFindingOrganizations");
      NaturalLanguage6::IProcessingOptions::PutItem(
        v27,
        (const struct _variant_t *)&v44,
        (const struct _variant_t *)&v55);
      _variant_t::~_variant_t(&v44);
      _variant_t::~_variant_t(&v55);
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>((__int64 *)&v66);
      v28 = (__int64 *)NaturalLanguage6::ITextContext::GetOptions(*v7);
      v29 = (struct IUnknown *)_com_ptr_t<_com_IIID<NaturalLanguage6::IProcessingOptions,&__s_GUID const _GUID_c090356b_a6a5_442a_a204_cfd5415b5902>>::operator->(v28);
      v56.vt = 11;
      v56.iVal = 0;
      _variant_t::_variant_t((_variant_t *)&v44, L"IsFindingPhrases");
      NaturalLanguage6::IProcessingOptions::PutItem(
        v29,
        (const struct _variant_t *)&v44,
        (const struct _variant_t *)&v56);
      _variant_t::~_variant_t(&v44);
      _variant_t::~_variant_t(&v56);
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>((__int64 *)&v66);
      v30 = (__int64 *)NaturalLanguage6::ITextContext::GetOptions(*v7);
      v31 = (struct IUnknown *)_com_ptr_t<_com_IIID<NaturalLanguage6::IProcessingOptions,&__s_GUID const _GUID_c090356b_a6a5_442a_a204_cfd5415b5902>>::operator->(v30);
      v57.vt = 11;
      v57.iVal = 0;
      _variant_t::_variant_t((_variant_t *)&v44, L"IsComputingBases");
      NaturalLanguage6::IProcessingOptions::PutItem(
        v31,
        (const struct _variant_t *)&v44,
        (const struct _variant_t *)&v57);
      _variant_t::~_variant_t(&v44);
      _variant_t::~_variant_t(&v57);
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>((__int64 *)&v66);
      v32 = (__int64 *)NaturalLanguage6::ITextContext::GetOptions(*v7);
      v33 = (struct IUnknown *)_com_ptr_t<_com_IIID<NaturalLanguage6::IProcessingOptions,&__s_GUID const _GUID_c090356b_a6a5_442a_a204_cfd5415b5902>>::operator->(v32);
      v58.vt = 11;
      v58.iVal = -1;
      _variant_t::_variant_t((_variant_t *)&v44, L"IsComputingExpansions");
      NaturalLanguage6::IProcessingOptions::PutItem(
        v33,
        (const struct _variant_t *)&v44,
        (const struct _variant_t *)&v58);
      _variant_t::~_variant_t(&v44);
      _variant_t::~_variant_t(&v58);
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>((__int64 *)&v66);
      v34 = (__int64 *)NaturalLanguage6::ITextContext::GetOptions(*v7);
      v35 = (struct IUnknown *)_com_ptr_t<_com_IIID<NaturalLanguage6::IProcessingOptions,&__s_GUID const _GUID_c090356b_a6a5_442a_a204_cfd5415b5902>>::operator->(v34);
      v59.vt = 11;
      v59.iVal = 0;
      _variant_t::_variant_t((_variant_t *)&v44, L"IsFindingPersons");
      NaturalLanguage6::IProcessingOptions::PutItem(
        v35,
        (const struct _variant_t *)&v44,
        (const struct _variant_t *)&v59);
      _variant_t::~_variant_t(&v44);
      _variant_t::~_variant_t(&v59);
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>((__int64 *)&v66);
      v36 = (__int64 *)NaturalLanguage6::ITextContext::GetOptions(*v7);
      v37 = (struct IUnknown *)_com_ptr_t<_com_IIID<NaturalLanguage6::IProcessingOptions,&__s_GUID const _GUID_c090356b_a6a5_442a_a204_cfd5415b5902>>::operator->(v36);
      v45.vt = 11;
      v45.iVal = -1;
      _variant_t::_variant_t((_variant_t *)&v44, L"IsSimpleWordBreaking");
      NaturalLanguage6::IProcessingOptions::PutItem(
        v37,
        (const struct _variant_t *)&v44,
        (const struct _variant_t *)&v45);
      _variant_t::~_variant_t(&v44);
      _variant_t::~_variant_t(&v45);
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>((__int64 *)&v66);
      v38 = (__int64 *)NaturalLanguage6::ITextContext::GetOptions(*v7);
      v39 = (struct IUnknown *)_com_ptr_t<_com_IIID<NaturalLanguage6::IProcessingOptions,&__s_GUID const _GUID_c090356b_a6a5_442a_a204_cfd5415b5902>>::operator->(v38);
      v44.vt = 11;
      v44.iVal = 0;
      _variant_t::_variant_t((_variant_t *)&v45, L"IgnorePunctuation");
      NaturalLanguage6::IProcessingOptions::PutItem(
        v39,
        (const struct _variant_t *)&v45,
        (const struct _variant_t *)&v44);
      _variant_t::~_variant_t(&v45);
      _variant_t::~_variant_t(&v44);
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>((__int64 *)&v66);
    }
    catch ( _com_error *v61 )
    {
      ImxTraceCatch(1, *((unsigned int *)v61 + 2), retaddr);
      v4 = this;
      v3 = a3;
      v7 = v46;
    }
    if ( !*((_QWORD *)v4 + 6)
      || (result = ((__int64 (__fastcall *)(struct IUnknown *))(*v7)->lpVtbl[5].AddRef)(*v7), (int)result >= 0) )
    {
      if ( !*((_QWORD *)v4 + 4) )
      {
        v41 = (struct IUnknown *)NaturalLanguage6::TextChunk::operator new(v40);
        if ( v41 )
          v42 = NaturalLanguage6::TextChunk::TextChunk(v41);
        else
          v42 = 0;
        *((_QWORD *)v4 + 4) = v42;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 8LL))(v42);
      }
      result = (*(__int64 (__fastcall **)(_QWORD, struct IUnknown *))(**((_QWORD **)v4 + 4) + 152LL))(
                 *((_QWORD *)v4 + 4),
                 *v7);
      if ( (int)result >= 0 )
      {
        result = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v4 + 4) + 168LL))(
                   *((_QWORD *)v4 + 4),
                   *((unsigned int *)v4 + 10));
        if ( (int)result >= 0 )
        {
          result = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v4 + 4) + 240LL))(
                     *((_QWORD *)v4 + 4),
                     0xFFFFFFFFLL);
          if ( (int)result >= 0 )
          {
            *v3 = 1;
            *((_BYTE *)v4 + 56) = 1;
          }
        }
      }
    }
  }
  catch ( _com_error *v62 )
  {
    v43 = v62;
    ImxTraceCatch(1, *((unsigned int *)v62 + 2), retaddr);
    return *((unsigned int *)v43 + 2);
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
0x18005cb20  mov     rax, rsp
0x18005cb23  mov     [rax+18h], r8
0x18005cb27  mov     [rax+8], rcx
0x18005cb2b  push    rbx
0x18005cb2c  push    rsi
0x18005cb2d  push    rdi
0x18005cb2e  push    r12
0x18005cb30  push    r13
0x18005cb32  push    r14
0x18005cb34  push    r15
0x18005cb36  sub     rsp, 1B0h
0x18005cb3d  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x18005cb45  mov     r12, r8
0x18005cb48  mov     rsi, rcx
0x18005cb4b  xor     ebx, ebx
0x18005cb4d  test    r8, r8
0x18005cb50  jnz     short loc_18005CB5C
0x18005cb52  mov     eax, 80070057h
0x18005cb57  jmp     loc_18005D39D
0x18005cb5c  mov     eax, 1
0x18005cb61  test    edx, edx
0x18005cb63  cmovnz  eax, edx
0x18005cb66  mov     [rcx+14h], eax
0x18005cb69  lea     rdi, [rcx+18h]
0x18005cb6d  mov     [rsp+1E8h+var_198], rdi
0x18005cb72  cmp     [rdi], rbx
0x18005cb75  jnz     short loc_18005CBA9
0x18005cb77  call    ??2TextContext@NaturalLanguage6@@SAPEAX_K@Z; NaturalLanguage6::TextContext::operator new(unsigned __int64)
0x18005cb7c  mov     [rsp+1E8h+arg_18], rax
0x18005cb84  test    rax, rax
0x18005cb87  jz      short loc_18005CB96
0x18005cb89  mov     rcx, rax; this
0x18005cb8c  call    ??0TextContext@NaturalLanguage6@@QEAA@XZ; NaturalLanguage6::TextContext::TextContext(void)
0x18005cb91  mov     rcx, rax
0x18005cb94  jmp     short loc_18005CB99
0x18005cb96  mov     rcx, rbx
0x18005cb99  mov     [rdi], rcx
0x18005cb9c  mov     rax, [rcx]
0x18005cb9f  mov     rax, [rax+8]
0x18005cba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cba8  nop
0x18005cba9  lea     rdx, [rsp+1E8h+arg_18]
0x18005cbb1  mov     rcx, [rdi]; struct IUnknown *
0x18005cbb4  call    ?GetOptions@ITextContext@NaturalLanguage6@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIProcessingOptions@NaturalLanguage6@@$1?_GUID_c090356b_a6a5_442a_a204_cfd5415b5902@@3U__s_GUID@@B@@@@XZ; NaturalLanguage6::ITextContext::GetOptions(void)
0x18005cbb9  nop
0x18005cbba  mov     rcx, rax
0x18005cbbd  call    ??C?$_com_ptr_t@V?$_com_IIID@UIProcessingOptions@NaturalLanguage6@@$1?_GUID_c090356b_a6a5_442a_a204_cfd5415b5902@@3U__s_GUID@@B@@@@QEBAPEAUIProcessingOptions@NaturalLanguage6@@XZ; _com_ptr_t<_com_IIID<NaturalLanguage6::IProcessingOptions,&__s_GUID const _GUID_c090356b_a6a5_442a_a204_cfd5415b5902>>::operator->(void)
0x18005cbc2  mov     r14, rax
0x18005cbc5  mov     r13d, 0Bh
0x18005cbcb  mov     [rsp+1E8h+var_190], r13w
0x18005cbd1  mov     [rsp+1E8h+var_188], bx
0x18005cbd6  lea     rdx, aIsshowinggaps; "IsShowingGaps"
0x18005cbdd  lea     rcx, [rsp+1E8h+var_1C8]; this
0x18005cbe2  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18005cbe7  nop
0x18005cbe8  lea     r8, [rsp+1E8h+var_190]; struct _variant_t *
0x18005cbed  lea     rdx, [rsp+1E8h+var_1C8]; struct _variant_t *
0x18005cbf2  mov     rcx, r14; this
0x18005cbf5  call    ?PutItem@IProcessingOptions@NaturalLanguage6@@QEAAXAEBV_variant_t@@0@Z; NaturalLanguage6::IProcessingOptions::PutItem(_variant_t const &,_variant_t const &)
0x18005cbfa  nop
0x18005cbfb  lea     rcx, [rsp+1E8h+var_1C8]; this
0x18005cc00  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005cc05  nop
0x18005cc06  lea     rcx, [rsp+1E8h+var_190]; this
0x18005cc0b  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005cc10  nop
0x18005cc11  lea     rcx, [rsp+1E8h+arg_18]
0x18005cc19  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18005cc1e  lea     rdx, [rsp+1E8h+arg_18]
0x18005cc26  mov     rcx, [rdi]; struct IUnknown *
0x18005cc29  call    ?GetOptions@ITextContext@NaturalLanguage6@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIProcessingOptions@NaturalLanguage6@@$1?_GUID_c090356b_a6a5_442a_a204_cfd5415b5902@@3U__s_GUID@@B@@@@XZ; NaturalLanguage6::ITextContext::GetOptions(void)
0x18005cc2e  nop
0x18005cc2f  mov     rcx, rax
0x18005cc32  call    ??C?$_com_ptr_t@V?$_com_IIID@UIProcessingOptions@NaturalLanguage6@@$1?_GUID_c090356b_a6a5_442a_a204_cfd5415b5902@@3U__s_GUID@@B@@@@QEBAPEAUIProcessingOptions@NaturalLanguage6@@XZ; _com_ptr_t<_com_IIID<NaturalLanguage6::IProcessingOptions,&__s_GUID const _GUID_c090356b_a6a5_442a_a204_cfd5415b5902>>::operator->(void)
0x18005cc37  mov     r14, rax
0x18005cc3a  mov     [rsp+1E8h+var_178], r13w
0x18005cc40  mov     [rsp+1E8h+var_170], bx
0x18005cc45  lea     rdx, aIsshowingchara; "IsShowingCharacterNormalizations"
0x18005cc4c  lea     rcx, [rsp+1E8h+var_1C8]; this
0x18005cc51  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18005cc56  nop
0x18005cc57  lea     r8, [rsp+1E8h+var_178]; struct _variant_t *
0x18005cc5c  lea     rdx, [rsp+1E8h+var_1C8]; struct _variant_t *
0x18005cc61  mov     rcx, r14; this
0x18005cc64  call    ?PutItem@IProcessingOptions@NaturalLanguage6@@QEAAXAEBV_variant_t@@0@Z; NaturalLanguage6::IProcessingOptions::PutItem(_variant_t const &,_variant_t const &)
0x18005cc69  nop
0x18005cc6a  lea     rcx, [rsp+1E8h+var_1C8]; this
0x18005cc6f  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005cc74  nop
0x18005cc75  lea     rcx, [rsp+1E8h+var_178]; this
0x18005cc7a  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005cc7f  nop
0x18005cc80  lea     rcx, [rsp+1E8h+arg_18]
0x18005cc88  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18005cc8d  lea     rdx, [rsp+1E8h+arg_18]
0x18005cc95  mov     rcx, [rdi]; struct IUnknown *
0x18005cc98  call    ?GetOptions@ITextContext@NaturalLanguage6@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIProcessingOptions@NaturalLanguage6@@$1?_GUID_c090356b_a6a5_442a_a204_cfd5415b5902@@3U__s_GUID@@B@@@@XZ; NaturalLanguage6::ITextContext::GetOptions(void)
0x18005cc9d  nop
0x18005cc9e  mov     rcx, rax
0x18005cca1  call    ??C?$_com_ptr_t@V?$_com_IIID@UIProcessingOptions@NaturalLanguage6@@$1?_GUID_c090356b_a6a5_442a_a204_cfd5415b5902@@3U__s_GUID@@B@@@@QEBAPEAUIProcessingOptions@NaturalLanguage6@@XZ; _com_ptr_t<_com_IIID<NaturalLanguage6::IProcessingOptions,&__s_GUID const _GUID_c090356b_a6a5_442a_a204_cfd5415b5902>>::operator->(void)
0x18005cca6  mov     r14, rax
0x18005cca9  mov     [rsp+1E8h+var_160], r13w
0x18005ccb2  mov     [rsp+1E8h+var_158], bx
0x18005ccba  lea     rdx, aIsshowingwordn; "IsShowingWordNormalizations"
0x18005ccc1  lea     rcx, [rsp+1E8h+var_1C8]; this
0x18005ccc6  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18005cccb  nop
0x18005cccc  lea     r8, [rsp+1E8h+var_160]; struct _variant_t *
0x18005ccd4  lea     rdx, [rsp+1E8h+var_1C8]; struct _variant_t *
0x18005ccd9  mov     rcx, r14; this
0x18005ccdc  call    ?PutItem@IProcessingOptions@NaturalLanguage6@@QEAAXAEBV_variant_t@@0@Z; NaturalLanguage6::IProcessingOptions::PutItem(_variant_t const &,_variant_t const &)
0x18005cce1  nop
0x18005cce2  lea     rcx, [rsp+1E8h+var_1C8]; this
0x18005cce7  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005ccec  nop
0x18005cced  lea     rcx, [rsp+1E8h+var_160]; this
0x18005ccf5  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005ccfa  nop
0x18005ccfb  lea     rcx, [rsp+1E8h+arg_18]
0x18005cd03  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18005cd08  lea     rdx, [rsp+1E8h+arg_18]
0x18005cd10  mov     rcx, [rdi]; struct IUnknown *
0x18005cd13  call    ?GetOptions@ITextContext@NaturalLanguage6@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIProcessingOptions@NaturalLanguage6@@$1?_GUID_c090356b_a6a5_442a_a204_cfd5415b5902@@3U__s_GUID@@B@@@@XZ; NaturalLanguage6::ITextContext::GetOptions(void)
0x18005cd18  nop
0x18005cd19  mov     rcx, rax
0x18005cd1c  call    ??C?$_com_ptr_t@V?$_com_IIID@UIProcessingOptions@NaturalLanguage6@@$1?_GUID_c090356b_a6a5_442a_a204_cfd5415b5902@@3U__s_GUID@@B@@@@QEBAPEAUIProcessingOptions@NaturalLanguage6@@XZ; _com_ptr_t<_com_IIID<NaturalLanguage6::IProcessingOptions,&__s_GUID const _GUID_c090356b_a6a5_442a_a204_cfd5415b5902>>::operator->(void)
0x18005cd21  mov     r14, rax
0x18005cd24  mov     [rsp+1E8h+var_148], r13w
0x18005cd2d  mov     [rsp+1E8h+var_140], bx
0x18005cd35  lea     rdx, aIsspellcheckin; "IsSpellChecking"
0x18005cd3c  lea     rcx, [rsp+1E8h+var_1C8]; this
0x18005cd41  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18005cd46  nop
0x18005cd47  lea     r8, [rsp+1E8h+var_148]; struct _variant_t *
0x18005cd4f  lea     rdx, [rsp+1E8h+var_1C8]; struct _variant_t *
0x18005cd54  mov     rcx, r14; this
0x18005cd57  call    ?PutItem@IProcessingOptions@NaturalLanguage6@@QEAAXAEBV_variant_t@@0@Z; NaturalLanguage6::IProcessingOptions::PutItem(_variant_t const &,_variant_t const &)
0x18005cd5c  nop
0x18005cd5d  lea     rcx, [rsp+1E8h+var_1C8]; this
0x18005cd62  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005cd67  nop
0x18005cd68  lea     rcx, [rsp+1E8h+var_148]; this
0x18005cd70  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005cd75  nop
0x18005cd76  lea     rcx, [rsp+1E8h+arg_18]
0x18005cd7e  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18005cd83  lea     rdx, [rsp+1E8h+arg_18]
0x18005cd8b  mov     rcx, [rdi]; struct IUnknown *
0x18005cd8e  call    ?GetOptions@ITextContext@NaturalLanguage6@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIProcessingOptions@NaturalLanguage6@@$1?_GUID_c090356b_a6a5_442a_a204_cfd5415b5902@@3U__s_GUID@@B@@@@XZ; NaturalLanguage6::ITextContext::GetOptions(void)
0x18005cd93  nop
0x18005cd94  mov     rcx, rax
0x18005cd97  call    ??C?$_com_ptr_t@V?$_com_IIID@UIProcessingOptions@NaturalLanguage6@@$1?_GUID_c090356b_a6a5_442a_a204_cfd5415b5902@@3U__s_GUID@@B@@@@QEBAPEAUIProcessingOptions@NaturalLanguage6@@XZ; _com_ptr_t<_com_IIID<NaturalLanguage6::IProcessingOptions,&__s_GUID const _GUID_c090356b_a6a5_442a_a204_cfd5415b5902>>::operator->(void)
0x18005cd9c  mov     r14, rax
0x18005cd9f  mov     [rsp+1E8h+var_130], r13w
0x18005cda8  mov     [rsp+1E8h+var_128], bx
0x18005cdb0  lea     rdx, aIsspellsuggest; "IsSpellSuggestingMWEs"
0x18005cdb7  lea     rcx, [rsp+1E8h+var_1C8]; this
0x18005cdbc  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18005cdc1  nop
0x18005cdc2  lea     r8, [rsp+1E8h+var_130]; struct _variant_t *
0x18005cdca  lea     rdx, [rsp+1E8h+var_1C8]; struct _variant_t *
0x18005cdcf  mov     rcx, r14; this
0x18005cdd2  call    ?PutItem@IProcessingOptions@NaturalLanguage6@@QEAAXAEBV_variant_t@@0@Z; NaturalLanguage6::IProcessingOptions::PutItem(_variant_t const &,_variant_t const &)
0x18005cdd7  nop
0x18005cdd8  lea     rcx, [rsp+1E8h+var_1C8]; this
0x18005cddd  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005cde2  nop
0x18005cde3  lea     rcx, [rsp+1E8h+var_130]; this
0x18005cdeb  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005cdf0  nop
0x18005cdf1  lea     rcx, [rsp+1E8h+arg_18]
0x18005cdf9  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18005cdfe  lea     rdx, [rsp+1E8h+arg_18]
0x18005ce06  mov     rcx, [rdi]; struct IUnknown *
0x18005ce09  call    ?GetOptions@ITextContext@NaturalLanguage6@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIProcessingOptions@NaturalLanguage6@@$1?_GUID_c090356b_a6a5_442a_a204_cfd5415b5902@@3U__s_GUID@@B@@@@XZ; NaturalLanguage6::ITextContext::GetOptions(void)
0x18005ce0e  nop
0x18005ce0f  mov     rcx, rax
0x18005ce12  call    ??C?$_com_ptr_t@V?$_com_IIID@UIProcessingOptions@NaturalLanguage6@@$1?_GUID_c090356b_a6a5_442a_a204_cfd5415b5902@@3U__s_GUID@@B@@@@QEBAPEAUIProcessingOptions@NaturalLanguage6@@XZ; _com_ptr_t<_com_IIID<NaturalLanguage6::IProcessingOptions,&__s_GUID const _GUID_c090356b_a6a5_442a_a204_cfd5415b5902>>::operator->(void)
0x18005ce17  mov     r14, rax
0x18005ce1a  mov     [rsp+1E8h+var_118], r13w
0x18005ce23  mov     [rsp+1E8h+var_110], bx
0x18005ce2b  lea     rdx, aIsignoremixedd; "IsIgnoreMixedDigits"
0x18005ce32  lea     rcx, [rsp+1E8h+var_1C8]; this
0x18005ce37  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18005ce3c  nop
0x18005ce3d  lea     r8, [rsp+1E8h+var_118]; struct _variant_t *
0x18005ce45  lea     rdx, [rsp+1E8h+var_1C8]; struct _variant_t *
0x18005ce4a  mov     rcx, r14; this
0x18005ce4d  call    ?PutItem@IProcessingOptions@NaturalLanguage6@@QEAAXAEBV_variant_t@@0@Z; NaturalLanguage6::IProcessingOptions::PutItem(_variant_t const &,_variant_t const &)
0x18005ce52  nop
0x18005ce53  lea     rcx, [rsp+1E8h+var_1C8]; this
0x18005ce58  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005ce5d  nop
0x18005ce5e  lea     rcx, [rsp+1E8h+var_118]; this
0x18005ce66  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005ce6b  nop
0x18005ce6c  lea     rcx, [rsp+1E8h+arg_18]
0x18005ce74  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18005ce79  lea     rdx, [rsp+1E8h+arg_18]
0x18005ce81  mov     rcx, [rdi]; struct IUnknown *
0x18005ce84  call    ?GetOptions@ITextContext@NaturalLanguage6@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIProcessingOptions@NaturalLanguage6@@$1?_GUID_c090356b_a6a5_442a_a204_cfd5415b5902@@3U__s_GUID@@B@@@@XZ; NaturalLanguage6::ITextContext::GetOptions(void)
0x18005ce89  nop
0x18005ce8a  mov     rcx, rax
0x18005ce8d  call    ??C?$_com_ptr_t@V?$_com_IIID@UIProcessingOptions@NaturalLanguage6@@$1?_GUID_c090356b_a6a5_442a_a204_cfd5415b5902@@3U__s_GUID@@B@@@@QEBAPEAUIProcessingOptions@NaturalLanguage6@@XZ; _com_ptr_t<_com_IIID<NaturalLanguage6::IProcessingOptions,&__s_GUID const _GUID_c090356b_a6a5_442a_a204_cfd5415b5902>>::operator->(void)
0x18005ce92  mov     r14, rax
0x18005ce95  mov     [rsp+1E8h+var_100], r13w
0x18005ce9e  mov     [rsp+1E8h+var_F8], bx
0x18005cea6  lea     rdx, aIsfindingdatet; "IsFindingDateTimeMeasures"
0x18005cead  lea     rcx, [rsp+1E8h+var_1C8]; this
0x18005ceb2  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18005ceb7  nop
0x18005ceb8  lea     r8, [rsp+1E8h+var_100]; struct _variant_t *
0x18005cec0  lea     rdx, [rsp+1E8h+var_1C8]; struct _variant_t *
0x18005cec5  mov     rcx, r14; this
0x18005cec8  call    ?PutItem@IProcessingOptions@NaturalLanguage6@@QEAAXAEBV_variant_t@@0@Z; NaturalLanguage6::IProcessingOptions::PutItem(_variant_t const &,_variant_t const &)
0x18005cecd  nop
0x18005cece  lea     rcx, [rsp+1E8h+var_1C8]; this
0x18005ced3  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005ced8  nop
0x18005ced9  lea     rcx, [rsp+1E8h+var_100]; this
0x18005cee1  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005cee6  nop
0x18005cee7  lea     rcx, [rsp+1E8h+arg_18]
0x18005ceef  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18005cef4  lea     rdx, [rsp+1E8h+arg_18]
0x18005cefc  mov     rcx, [rdi]; struct IUnknown *
0x18005ceff  call    ?GetOptions@ITextContext@NaturalLanguage6@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIProcessingOptions@NaturalLanguage6@@$1?_GUID_c090356b_a6a5_442a_a204_cfd5415b5902@@3U__s_GUID@@B@@@@XZ; NaturalLanguage6::ITextContext::GetOptions(void)
0x18005cf04  nop
0x18005cf05  mov     rcx, rax
0x18005cf08  call    ??C?$_com_ptr_t@V?$_com_IIID@UIProcessingOptions@NaturalLanguage6@@$1?_GUID_c090356b_a6a5_442a_a204_cfd5415b5902@@3U__s_GUID@@B@@@@QEBAPEAUIProcessingOptions@NaturalLanguage6@@XZ; _com_ptr_t<_com_IIID<NaturalLanguage6::IProcessingOptions,&__s_GUID const _GUID_c090356b_a6a5_442a_a204_cfd5415b5902>>::operator->(void)
0x18005cf0d  mov     r14, rax
0x18005cf10  mov     [rsp+1E8h+var_E8], r13w
0x18005cf19  mov     [rsp+1E8h+var_E0], bx
0x18005cf21  lea     rdx, aIsfindinglocat; "IsFindingLocations"
0x18005cf28  lea     rcx, [rsp+1E8h+var_1C8]; this
0x18005cf2d  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18005cf32  nop
0x18005cf33  lea     r8, [rsp+1E8h+var_E8]; struct _variant_t *
0x18005cf3b  lea     rdx, [rsp+1E8h+var_1C8]; struct _variant_t *
0x18005cf40  mov     rcx, r14; this
0x18005cf43  call    ?PutItem@IProcessingOptions@NaturalLanguage6@@QEAAXAEBV_variant_t@@0@Z; NaturalLanguage6::IProcessingOptions::PutItem(_variant_t const &,_variant_t const &)
0x18005cf48  nop
0x18005cf49  lea     rcx, [rsp+1E8h+var_1C8]; this
0x18005cf4e  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005cf53  nop
0x18005cf54  lea     rcx, [rsp+1E8h+var_E8]; this
0x18005cf5c  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005cf61  nop
0x18005cf62  lea     rcx, [rsp+1E8h+arg_18]
0x18005cf6a  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18005cf6f  lea     rdx, [rsp+1E8h+arg_18]
0x18005cf77  mov     rcx, [rdi]; struct IUnknown *
0x18005cf7a  call    ?GetOptions@ITextContext@NaturalLanguage6@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIProcessingOptions@NaturalLanguage6@@$1?_GUID_c090356b_a6a5_442a_a204_cfd5415b5902@@3U__s_GUID@@B@@@@XZ; NaturalLanguage6::ITextContext::GetOptions(void)
0x18005cf7f  nop
0x18005cf80  mov     rcx, rax
0x18005cf83  call    ??C?$_com_ptr_t@V?$_com_IIID@UIProcessingOptions@NaturalLanguage6@@$1?_GUID_c090356b_a6a5_442a_a204_cfd5415b5902@@3U__s_GUID@@B@@@@QEBAPEAUIProcessingOptions@NaturalLanguage6@@XZ; _com_ptr_t<_com_IIID<NaturalLanguage6::IProcessingOptions,&__s_GUID const _GUID_c090356b_a6a5_442a_a204_cfd5415b5902>>::operator->(void)
0x18005cf88  mov     r14, rax
0x18005cf8b  mov     [rsp+1E8h+var_D0], r13w
0x18005cf94  mov     [rsp+1E8h+var_C8], bx
0x18005cf9c  lea     rdx, aIsfindingorgan; "IsFindingOrganizations"
0x18005cfa3  lea     rcx, [rsp+1E8h+var_1C8]; this
0x18005cfa8  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18005cfad  nop
0x18005cfae  lea     r8, [rsp+1E8h+var_D0]; struct _variant_t *
0x18005cfb6  lea     rdx, [rsp+1E8h+var_1C8]; struct _variant_t *
0x18005cfbb  mov     rcx, r14; this
0x18005cfbe  call    ?PutItem@IProcessingOptions@NaturalLanguage6@@QEAAXAEBV_variant_t@@0@Z; NaturalLanguage6::IProcessingOptions::PutItem(_variant_t const &,_variant_t const &)
0x18005cfc3  nop
0x18005cfc4  lea     rcx, [rsp+1E8h+var_1C8]; this
0x18005cfc9  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005cfce  nop
0x18005cfcf  lea     rcx, [rsp+1E8h+var_D0]; this
0x18005cfd7  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005cfdc  nop
0x18005cfdd  lea     rcx, [rsp+1E8h+arg_18]
0x18005cfe5  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18005cfea  lea     rdx, [rsp+1E8h+arg_18]
0x18005cff2  mov     rcx, [rdi]; struct IUnknown *
0x18005cff5  call    ?GetOptions@ITextContext@NaturalLanguage6@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIProcessingOptions@NaturalLanguage6@@$1?_GUID_c090356b_a6a5_442a_a204_cfd5415b5902@@3U__s_GUID@@B@@@@XZ; NaturalLanguage6::ITextContext::GetOptions(void)
0x18005cffa  nop
0x18005cffb  mov     rcx, rax
0x18005cffe  call    ??C?$_com_ptr_t@V?$_com_IIID@UIProcessingOptions@NaturalLanguage6@@$1?_GUID_c090356b_a6a5_442a_a204_cfd5415b5902@@3U__s_GUID@@B@@@@QEBAPEAUIProcessingOptions@NaturalLanguage6@@XZ; _com_ptr_t<_com_IIID<NaturalLanguage6::IProcessingOptions,&__s_GUID const _GUID_c090356b_a6a5_442a_a204_cfd5415b5902>>::operator->(void)
0x18005d003  mov     r14, rax
0x18005d006  mov     [rsp+1E8h+var_B8], r13w
0x18005d00f  mov     [rsp+1E8h+var_B0], bx
0x18005d017  lea     rdx, aIsfindingphras; "IsFindingPhrases"
0x18005d01e  lea     rcx, [rsp+1E8h+var_1C8]; this
0x18005d023  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18005d028  nop
0x18005d029  lea     r8, [rsp+1E8h+var_B8]; struct _variant_t *
0x18005d031  lea     rdx, [rsp+1E8h+var_1C8]; struct _variant_t *
0x18005d036  mov     rcx, r14; this
0x18005d039  call    ?PutItem@IProcessingOptions@NaturalLanguage6@@QEAAXAEBV_variant_t@@0@Z; NaturalLanguage6::IProcessingOptions::PutItem(_variant_t const &,_variant_t const &)
0x18005d03e  nop
0x18005d03f  lea     rcx, [rsp+1E8h+var_1C8]; this
0x18005d044  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005d049  nop
0x18005d04a  lea     rcx, [rsp+1E8h+var_B8]; this
0x18005d052  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18005d057  nop
  ... truncated ...
```
