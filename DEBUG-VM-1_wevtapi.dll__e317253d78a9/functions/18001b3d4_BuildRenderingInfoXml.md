# BuildRenderingInfoXml

- ea: `0x18001b3d4`
- end: `0x18001bbc4`
- name: `BuildRenderingInfoXml`
- size: `2032`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task`

## callers

- `0x180007fb8`

## callees

- `0x18000a0dc`
- `0x18000a4b4`
- `0x18000a978`
- `0x18000b638`
- `0x18000c034`
- `0x18000c10c`
- `0x18000c6c8`
- `0x18000c9b4`
- `0x18000e960`
- `0x18000eaf4`
- `0x18000f2b0`
- `0x18001b3d4`
- `0x18001bda4`
- `0x18001c43c`
- `0x1800249f0`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18001b447`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18001b447`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18001b431`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18001b431`

## string_xrefs

- `0x18001b6f8`: `<Task>`
- `0x18001b731`: `</Task>`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall BuildRenderingInfoXml(
        __int64 a1,
        __int64 a2,
        const struct Event *a3,
        __int64 a4,
        unsigned __int64 *a5,
        __int64 a6)
{
  int v6; // r12d
  int v8; // r14d
  int v9; // r15d
  LCID ThreadLocale; // eax
  __int64 LocaleInfoW; // rdi
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rdx
  bool v14; // di
  __int64 v15; // rsi
  __int64 *RenderedMessageFromService; // rax
  __int64 v17; // rsi
  __int64 *v18; // rax
  __int64 v19; // rsi
  __int64 *v20; // rax
  unsigned __int64 v21; // r13
  unsigned __int64 v22; // rdi
  __int64 v23; // r12
  _WORD *v24; // r14
  __int64 v25; // rsi
  unsigned __int64 *v26; // rax
  __int64 v27; // rsi
  unsigned __int64 *v28; // rax
  __int64 v29; // rsi
  unsigned __int64 *v30; // rax
  unsigned __int64 v31; // r14
  __int64 v32; // r15
  unsigned __int64 v33; // rsi
  unsigned __int64 v34; // r12
  unsigned __int64 v35; // rdi
  __int64 v37; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v38; // [rsp+48h] [rbp-B8h]
  _BYTE v39[16]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v40; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v41; // [rsp+68h] [rbp-98h]
  _BYTE v42[16]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v43[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v44; // [rsp+90h] [rbp-70h]
  __int64 v45; // [rsp+98h] [rbp-68h]
  __int64 v46; // [rsp+A0h] [rbp-60h]
  _DWORD v47[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v48; // [rsp+B0h] [rbp-50h]
  _BYTE v49[24]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v50[3]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v51; // [rsp+E8h] [rbp-18h] BYREF
  int v52; // [rsp+F0h] [rbp-10h]
  WCHAR LCData[56]; // [rsp+100h] [rbp+0h] BYREF

  v6 = a4;
  v45 = a4;
  v8 = a2;
  v44 = a2;
  v9 = a1;
  v46 = a6;
  if ( a1 )
    ThreadLocale = *(_DWORD *)(a1 + 64);
  else
    ThreadLocale = GetThreadLocale();
  LocaleInfoW = GetLocaleInfoW(ThreadLocale, 0x5Cu, LCData, 50);
  v12 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::capacity(
          a5,
          LocaleInfoW + ((__int64)(a5[1] - *a5) >> 1) + 244);
  if ( v13 > v12
    && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Grow()
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                           a5,
                           L"<RenderingInfo Culture='",
                           24)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                           a5,
                           LCData,
                           LocaleInfoW - 1)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                           a5,
                           L"'>",
                           2) )
  {
    return 0;
  }
  v14 = 0;
  v43[0] = 0;
  v43[1] = 0;
  SubstitutionValues::SubstitutionValues((SubstitutionValues *)v49, a3, 0, 0);
  v51 = 0;
  v52 = 0;
  v47[1] = 0;
  v47[0] = -1431655765 * ((__int64)(v50[1] - v50[0]) >> 3);
  v48 = v50[0];
  GetRenderedMessageFromService((unsigned int)&v37, v9, v8, v6, -1, (__int64)v47, 1, (__int64)&v51);
  v15 = v38;
  if ( v38 )
  {
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                            a5,
                            L"<Message>",
                            9) )
    {
      v40 = v37;
      v41 = v15;
      if ( (unsigned __int8)AppendEscapedXml(a5, &v40) )
        v14 = (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                 a5,
                                 L"</Message>",
                                 10) != 0;
    }
  }
  RenderedMessageFromService = (__int64 *)GetRenderedMessageFromService(
                                            (unsigned int)&v40,
                                            v9,
                                            v8,
                                            v6,
                                            -1,
                                            (__int64)v43,
                                            2,
                                            (__int64)&v51);
  v37 = *RenderedMessageFromService;
  v38 = RenderedMessageFromService[1];
  *RenderedMessageFromService = 0;
  RenderedMessageFromService[1] = 0;
  __4__unique_ptr___BY0A_EU__generic_delete___BY0A_EU__generic_deallocate__MP6AXPEAX_Z1_MIDL_user_free__YAX0_ZPEAX_tlx___tlx___utl__QEAAAEAV01___QEAV01__Z(
    v39,
    RenderedMessageFromService + 2);
  utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>(v42);
  v17 = v38;
  if ( v38 )
  {
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                            a5,
                            L"<Level>",
                            7) )
    {
      v40 = v37;
      v41 = v17;
      if ( (unsigned __int8)AppendEscapedXml(a5, &v40) )
      {
        if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                a5,
                                L"</Level>",
                                8) )
          v14 = 1;
      }
    }
  }
  v18 = (__int64 *)GetRenderedMessageFromService((unsigned int)&v40, v9, v8, v6, -1, (__int64)v43, 3, (__int64)&v51);
  v37 = *v18;
  v38 = v18[1];
  *v18 = 0;
  v18[1] = 0;
  __4__unique_ptr___BY0A_EU__generic_delete___BY0A_EU__generic_deallocate__MP6AXPEAX_Z1_MIDL_user_free__YAX0_ZPEAX_tlx___tlx___utl__QEAAAEAV01___QEAV01__Z(
    v39,
    v18 + 2);
  utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>(v42);
  v19 = v38;
  if ( v38 )
  {
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                            a5,
                            L"<Task>",
                            6) )
    {
      v40 = v37;
      v41 = v19;
      if ( (unsigned __int8)AppendEscapedXml(a5, &v40) )
      {
        if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                a5,
                                L"</Task>",
                                7) )
          v14 = 1;
      }
    }
  }
  v20 = (__int64 *)GetRenderedMessageFromService((unsigned int)&v40, v9, v8, v6, -1, (__int64)v43, 4, (__int64)&v51);
  v37 = *v20;
  v38 = v20[1];
  *v20 = 0;
  v20[1] = 0;
  __4__unique_ptr___BY0A_EU__generic_delete___BY0A_EU__generic_deallocate__MP6AXPEAX_Z1_MIDL_user_free__YAX0_ZPEAX_tlx___tlx___utl__QEAAAEAV01___QEAV01__Z(
    v39,
    v20 + 2);
  utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>(v42);
  v21 = v38;
  if ( v38 )
  {
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                             a5,
                             L"<Opcode>",
                             8) )
      goto LABEL_60;
    v22 = 0;
    v23 = v37;
    while ( v22 < v21 )
    {
      v24 = (_WORD *)(v23 + 2 * v22);
      if ( !*v24 )
        break;
      if ( v22
        && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                               a5,
                               32) )
      {
        goto LABEL_60;
      }
      v25 = -1;
      do
        ++v25;
      while ( v24[v25] );
      v40 = v23 + 2 * v22;
      v41 = v25;
      if ( !(unsigned __int8)AppendEscapedXml(a5, &v40) )
        goto LABEL_48;
      v22 += v25 + 1;
    }
    v21 = 0;
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                             a5,
                             L"</Opcode>",
                             9) )
      goto LABEL_60;
    v14 = 1;
    v8 = v44;
    v6 = v45;
  }
  v26 = (unsigned __int64 *)GetRenderedMessageFromService(
                              (unsigned int)&v40,
                              v9,
                              v8,
                              v6,
                              -1,
                              (__int64)v43,
                              6,
                              (__int64)&v51);
  v37 = *v26;
  v38 = v26[1];
  *v26 = v21;
  v26[1] = v21;
  __4__unique_ptr___BY0A_EU__generic_delete___BY0A_EU__generic_deallocate__MP6AXPEAX_Z1_MIDL_user_free__YAX0_ZPEAX_tlx___tlx___utl__QEAAAEAV01___QEAV01__Z(
    v39,
    v26 + 2);
  utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>(v42);
  v27 = v38;
  if ( v38 )
  {
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                            a5,
                            L"<Channel>",
                            9) )
    {
      v40 = v37;
      v41 = v27;
      if ( (unsigned __int8)AppendEscapedXml(a5, &v40) )
      {
        if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                a5,
                                L"</Channel>",
                                10) )
          v14 = 1;
      }
    }
  }
  v28 = (unsigned __int64 *)GetRenderedMessageFromService((unsigned int)&v40, v9, v8, v6, -1, (__int64)v43, 7, v46);
  v37 = *v28;
  v38 = v28[1];
  *v28 = v21;
  v28[1] = v21;
  __4__unique_ptr___BY0A_EU__generic_delete___BY0A_EU__generic_deallocate__MP6AXPEAX_Z1_MIDL_user_free__YAX0_ZPEAX_tlx___tlx___utl__QEAAAEAV01___QEAV01__Z(
    v39,
    v28 + 2);
  utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>(v42);
  v29 = v38;
  if ( v38 )
  {
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                            a5,
                            L"<Provider>",
                            10) )
    {
      v40 = v37;
      v41 = v29;
      if ( (unsigned __int8)AppendEscapedXml(a5, &v40) )
      {
        if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                a5,
                                L"</Provider>",
                                11) )
          v14 = 1;
      }
    }
  }
  v30 = (unsigned __int64 *)GetRenderedMessageFromService(
                              (unsigned int)&v40,
                              v9,
                              v8,
                              v6,
                              -1,
                              (__int64)v43,
                              5,
                              (__int64)&v51);
  v37 = *v30;
  v38 = v30[1];
  *v30 = v21;
  v30[1] = v21;
  __4__unique_ptr___BY0A_EU__generic_delete___BY0A_EU__generic_deallocate__MP6AXPEAX_Z1_MIDL_user_free__YAX0_ZPEAX_tlx___tlx___utl__QEAAAEAV01___QEAV01__Z(
    v39,
    v30 + 2);
  utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>(v42);
  if ( v38 == v21 )
  {
LABEL_58:
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                            a5,
                            L"</RenderingInfo>",
                            16) )
    {
      utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>(v39);
      SubstitutionValues::~SubstitutionValues((SubstitutionValues *)v49);
      return v14;
    }
    goto LABEL_60;
  }
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                          a5,
                          L"<Keywords>",
                          10) )
  {
    v31 = v21;
    v32 = v37;
    while ( v31 < v38 && (_WORD)v21 != *(_WORD *)(v32 + 2 * v31) )
    {
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                               a5,
                               L"<Keyword>",
                               9) )
        goto LABEL_60;
      v33 = a5[1];
      v34 = *a5;
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                               a5,
                               v32 + 2 * v31) )
        goto LABEL_60;
      v35 = a5[1];
      v21 = *a5;
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                               a5,
                               L"</Keyword>",
                               10) )
        goto LABEL_60;
      v31 += ((__int64)(v35 - v21) >> 1) - ((__int64)(v33 - v34) >> 1) + 1;
      LOWORD(v21) = 0;
    }
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                            a5,
                            L"</Keywords>",
                            11) )
    {
      v14 = 1;
      goto LABEL_58;
    }
LABEL_60:
    utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>(v39);
    SubstitutionValues::~SubstitutionValues((SubstitutionValues *)v49);
    return 0;
  }
LABEL_48:
  utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>(v39);
  utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(v50);
  utl::vector<BinXmlVariantHolder,utl::allocator<BinXmlVariantHolder>>::_Uninit(v49);
  return 0;
}

```

## disassembly

```asm
0x18001b3d4  push    rbp
0x18001b3d6  push    rbx
0x18001b3d7  push    rsi
0x18001b3d8  push    rdi
0x18001b3d9  push    r12
0x18001b3db  push    r13
0x18001b3dd  push    r14
0x18001b3df  push    r15
0x18001b3e1  lea     rbp, [rsp-88h]
0x18001b3e9  sub     rsp, 188h
0x18001b3f0  mov     rax, cs:__security_cookie
0x18001b3f7  xor     rax, rsp
0x18001b3fa  mov     [rbp+0C0h+var_50], rax
0x18001b3fe  mov     r12, r9
0x18001b401  mov     [rbp+0C0h+var_128], r9
0x18001b405  mov     rsi, r8
0x18001b408  mov     r14, rdx
0x18001b40b  mov     [rbp+0C0h+var_130], rdx
0x18001b40f  mov     r15, rcx
0x18001b412  mov     rbx, [rbp+0C0h+arg_20]
0x18001b419  mov     rax, [rbp+0C0h+arg_28]
0x18001b420  mov     [rbp+0C0h+var_120], rax
0x18001b424  xor     r13d, r13d
0x18001b427  test    rcx, rcx
0x18001b42a  jz      short loc_18001B431
0x18001b42c  mov     eax, [rcx+40h]
0x18001b42f  jmp     short loc_18001B437
0x18001b431  call    cs:__imp_GetThreadLocale
0x18001b437  mov     r9d, 32h ; '2'; cchData
0x18001b43d  lea     r8, [rbp+0C0h+LCData]; lpLCData
0x18001b441  lea     edx, [r9+2Ah]; LCType
0x18001b445  mov     ecx, eax; Locale
0x18001b447  call    cs:__imp_GetLocaleInfoW
0x18001b44d  movsxd  rdi, eax
0x18001b450  mov     rdx, [rbx+8]
0x18001b454  sub     rdx, [rbx]
0x18001b457  sar     rdx, 1
0x18001b45a  add     rdx, 0F4h
0x18001b461  add     rdx, rdi
0x18001b464  mov     rcx, rbx
0x18001b467  call    ?capacity@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_KXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::capacity(void)
0x18001b46c  cmp     rdx, rax
0x18001b46f  jbe     short loc_18001B47E
0x18001b471  call    ?_Grow@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Grow(unsigned __int64)
0x18001b476  test    al, al
0x18001b478  jz      loc_18001BBA2
0x18001b47e  mov     r8d, 18h
0x18001b484  lea     rdx, aRenderinginfoC; "<RenderingInfo Culture='"
0x18001b48b  mov     rcx, rbx
0x18001b48e  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18001b493  test    al, al
0x18001b495  jz      loc_18001BBA2
0x18001b49b  lea     r8, [rdi-1]
0x18001b49f  lea     rdx, [rbp+0C0h+LCData]
0x18001b4a3  mov     rcx, rbx
0x18001b4a6  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18001b4ab  test    al, al
0x18001b4ad  jz      loc_18001BBA2
0x18001b4b3  mov     r8d, 2
0x18001b4b9  lea     rdx, asc_180040BE4; "'>"
0x18001b4c0  mov     rcx, rbx
0x18001b4c3  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18001b4c8  test    al, al
0x18001b4ca  jz      loc_18001BBA2
0x18001b4d0  movzx   edi, r13b
0x18001b4d4  mov     [rbp+0C0h+var_140], r13
0x18001b4d8  mov     [rbp+0C0h+var_138], r13
0x18001b4dc  xor     r9d, r9d; struct _EVT_VARIANT *
0x18001b4df  xor     r8d, r8d; unsigned int
0x18001b4e2  mov     rdx, rsi; struct Event *
0x18001b4e5  lea     rcx, [rbp+0C0h+var_108]; this
0x18001b4e9  call    ??0SubstitutionValues@@QEAA@PEBVEvent@@KPEAU_EVT_VARIANT@@@Z; SubstitutionValues::SubstitutionValues(Event const *,ulong,_EVT_VARIANT *)
0x18001b4ee  nop
0x18001b4ef  xor     eax, eax
0x18001b4f1  mov     [rbp+0C0h+var_D8], rax
0x18001b4f5  mov     [rbp+0C0h+var_D0], eax
0x18001b4f8  mov     [rbp+0C0h+var_114], r13d
0x18001b4fc  mov     rcx, [rbp+0C0h+var_E8]
0x18001b500  mov     rax, [rbp+0C0h+var_F0]
0x18001b504  sub     rcx, rax
0x18001b507  sar     rcx, 3
0x18001b50b  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18001b515  imul    rcx, rdx
0x18001b519  mov     [rbp+0C0h+var_118], ecx
0x18001b51c  mov     [rbp+0C0h+var_110], rax
0x18001b520  lea     rax, [rbp+0C0h+var_D8]
0x18001b524  mov     [rsp+1C0h+var_188], rax
0x18001b529  mov     [rsp+1C0h+var_190], 1
0x18001b531  lea     rax, [rbp+0C0h+var_118]
0x18001b535  mov     [rsp+1C0h+var_198], rax
0x18001b53a  mov     [rsp+1C0h+var_1A0], 0FFFFFFFFh
0x18001b542  mov     r9, r12
0x18001b545  mov     r8, r14
0x18001b548  mov     rdx, r15
0x18001b54b  lea     rcx, [rsp+1C0h+var_180]
0x18001b550  call    GetRenderedMessageFromService
0x18001b555  nop
0x18001b556  mov     rsi, [rsp+1C0h+var_178]
0x18001b55b  test    rsi, rsi
0x18001b55e  jz      short loc_18001B5B8
0x18001b560  mov     r8d, 9
0x18001b566  lea     rdx, aMessage_0; "<Message>"
0x18001b56d  mov     rcx, rbx
0x18001b570  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18001b575  test    al, al
0x18001b577  jz      short loc_18001B5B8
0x18001b579  mov     rax, [rsp+1C0h+var_180]
0x18001b57e  mov     [rsp+1C0h+var_160], rax
0x18001b583  mov     [rsp+1C0h+var_158], rsi
0x18001b588  lea     rdx, [rsp+1C0h+var_160]
0x18001b58d  mov     rcx, rbx
0x18001b590  call    AppendEscapedXml
0x18001b595  test    al, al
0x18001b597  jz      short loc_18001B5B8
0x18001b599  mov     r8d, 0Ah
0x18001b59f  lea     rdx, aMessage; "</Message>"
0x18001b5a6  mov     rcx, rbx
0x18001b5a9  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18001b5ae  test    al, al
0x18001b5b0  mov     eax, 1
0x18001b5b5  cmovnz  edi, eax
0x18001b5b8  lea     rax, [rbp+0C0h+var_D8]
0x18001b5bc  mov     [rsp+1C0h+var_188], rax
0x18001b5c1  mov     [rsp+1C0h+var_190], 2
0x18001b5c9  lea     rax, [rbp+0C0h+var_140]
0x18001b5cd  mov     [rsp+1C0h+var_198], rax
0x18001b5d2  mov     [rsp+1C0h+var_1A0], 0FFFFFFFFh
0x18001b5da  mov     r9, r12
0x18001b5dd  mov     r8, r14
0x18001b5e0  mov     rdx, r15
0x18001b5e3  lea     rcx, [rsp+1C0h+var_160]
0x18001b5e8  call    GetRenderedMessageFromService
0x18001b5ed  mov     rcx, [rax]
0x18001b5f0  mov     [rsp+1C0h+var_180], rcx
0x18001b5f5  mov     rcx, [rax+8]
0x18001b5f9  mov     [rsp+1C0h+var_178], rcx
0x18001b5fe  mov     [rax], r13
0x18001b601  mov     [rax+8], r13
0x18001b605  lea     rdx, [rax+10h]
0x18001b609  lea     rcx, [rsp+1C0h+var_170]
0x18001b60e  call    ??4?$unique_ptr@$$BY0A@EU?$generic_delete@$$BY0A@EU?$generic_deallocate@$MP6AXPEAX@Z1?MIDL_user_free@@YAX0@ZPEAX@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z
0x18001b613  lea     rcx, [rsp+1C0h+var_150]
0x18001b618  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@K@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>(void)
0x18001b61d  mov     rsi, [rsp+1C0h+var_178]
0x18001b622  test    rsi, rsi
0x18001b625  jz      short loc_18001B683
0x18001b627  mov     r8d, 7
0x18001b62d  lea     rdx, aLevel_0; "<Level>"
0x18001b634  mov     rcx, rbx
0x18001b637  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18001b63c  test    al, al
0x18001b63e  jz      short loc_18001B683
0x18001b640  mov     rax, [rsp+1C0h+var_180]
0x18001b645  mov     [rsp+1C0h+var_160], rax
0x18001b64a  mov     [rsp+1C0h+var_158], rsi
0x18001b64f  lea     rdx, [rsp+1C0h+var_160]
0x18001b654  mov     rcx, rbx
0x18001b657  call    AppendEscapedXml
0x18001b65c  test    al, al
0x18001b65e  jz      short loc_18001B683
0x18001b660  mov     r8d, 8
0x18001b666  lea     rdx, aLevel; "</Level>"
0x18001b66d  mov     rcx, rbx
0x18001b670  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18001b675  movzx   edi, dil
0x18001b679  test    al, al
0x18001b67b  mov     eax, 1
0x18001b680  cmovnz  edi, eax
0x18001b683  lea     rax, [rbp+0C0h+var_D8]
0x18001b687  mov     [rsp+1C0h+var_188], rax
0x18001b68c  mov     [rsp+1C0h+var_190], 3
0x18001b694  lea     rax, [rbp+0C0h+var_140]
0x18001b698  mov     [rsp+1C0h+var_198], rax
0x18001b69d  mov     [rsp+1C0h+var_1A0], 0FFFFFFFFh
0x18001b6a5  mov     r9, r12
0x18001b6a8  mov     r8, r14
0x18001b6ab  mov     rdx, r15
0x18001b6ae  lea     rcx, [rsp+1C0h+var_160]
0x18001b6b3  call    GetRenderedMessageFromService
0x18001b6b8  mov     rcx, [rax]
0x18001b6bb  mov     [rsp+1C0h+var_180], rcx
0x18001b6c0  mov     rcx, [rax+8]
0x18001b6c4  mov     [rsp+1C0h+var_178], rcx
0x18001b6c9  mov     [rax], r13
0x18001b6cc  mov     [rax+8], r13
0x18001b6d0  lea     rdx, [rax+10h]
0x18001b6d4  lea     rcx, [rsp+1C0h+var_170]
0x18001b6d9  call    ??4?$unique_ptr@$$BY0A@EU?$generic_delete@$$BY0A@EU?$generic_deallocate@$MP6AXPEAX@Z1?MIDL_user_free@@YAX0@ZPEAX@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z
0x18001b6de  lea     rcx, [rsp+1C0h+var_150]
0x18001b6e3  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@K@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>(void)
0x18001b6e8  mov     rsi, [rsp+1C0h+var_178]
0x18001b6ed  test    rsi, rsi
0x18001b6f0  jz      short loc_18001B74E
0x18001b6f2  mov     r8d, 6
0x18001b6f8  lea     rdx, aTask; "<Task>"
0x18001b6ff  mov     rcx, rbx
0x18001b702  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18001b707  test    al, al
0x18001b709  jz      short loc_18001B74E
0x18001b70b  mov     rax, [rsp+1C0h+var_180]
0x18001b710  mov     [rsp+1C0h+var_160], rax
0x18001b715  mov     [rsp+1C0h+var_158], rsi
0x18001b71a  lea     rdx, [rsp+1C0h+var_160]
0x18001b71f  mov     rcx, rbx
0x18001b722  call    AppendEscapedXml
0x18001b727  test    al, al
0x18001b729  jz      short loc_18001B74E
0x18001b72b  mov     r8d, 7
0x18001b731  lea     rdx, aTask_0; "</Task>"
0x18001b738  mov     rcx, rbx
0x18001b73b  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18001b740  movzx   edi, dil
0x18001b744  test    al, al
0x18001b746  mov     eax, 1
0x18001b74b  cmovnz  edi, eax
0x18001b74e  lea     rax, [rbp+0C0h+var_D8]
0x18001b752  mov     [rsp+1C0h+var_188], rax
0x18001b757  mov     [rsp+1C0h+var_190], 4
0x18001b75f  lea     rax, [rbp+0C0h+var_140]
0x18001b763  mov     [rsp+1C0h+var_198], rax
0x18001b768  mov     [rsp+1C0h+var_1A0], 0FFFFFFFFh
0x18001b770  mov     r9, r12
0x18001b773  mov     r8, r14
0x18001b776  mov     rdx, r15
0x18001b779  lea     rcx, [rsp+1C0h+var_160]
0x18001b77e  call    GetRenderedMessageFromService
0x18001b783  mov     rcx, [rax]
0x18001b786  mov     [rsp+1C0h+var_180], rcx
0x18001b78b  mov     rcx, [rax+8]
0x18001b78f  mov     [rsp+1C0h+var_178], rcx
0x18001b794  mov     [rax], r13
0x18001b797  mov     [rax+8], r13
0x18001b79b  lea     rdx, [rax+10h]
0x18001b79f  lea     rcx, [rsp+1C0h+var_170]
0x18001b7a4  call    ??4?$unique_ptr@$$BY0A@EU?$generic_delete@$$BY0A@EU?$generic_deallocate@$MP6AXPEAX@Z1?MIDL_user_free@@YAX0@ZPEAX@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z
0x18001b7a9  lea     rcx, [rsp+1C0h+var_150]
0x18001b7ae  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@K@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>(void)
0x18001b7b3  mov     r13, [rsp+1C0h+var_178]
0x18001b7b8  xor     esi, esi
0x18001b7ba  test    r13, r13
0x18001b7bd  jz      loc_18001B872
0x18001b7c3  lea     r8d, [rsi+8]
0x18001b7c7  lea     rdx, aOpcode; "<Opcode>"
0x18001b7ce  mov     rcx, rbx
0x18001b7d1  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18001b7d6  test    al, al
0x18001b7d8  jz      loc_18001BB8E
0x18001b7de  mov     edi, esi
0x18001b7e0  mov     r12, [rsp+1C0h+var_180]
0x18001b7e5  cmp     rdi, r13
0x18001b7e8  jnb     short loc_18001B847
0x18001b7ea  lea     r14, [r12+rdi*2]
0x18001b7ee  cmp     si, [r14]
0x18001b7f2  jz      short loc_18001B847
0x18001b7f4  test    rdi, rdi
0x18001b7f7  jz      short loc_18001B80E
0x18001b7f9  mov     edx, 20h ; ' '
0x18001b7fe  mov     rcx, rbx
0x18001b801  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x18001b806  test    al, al
0x18001b808  jz      loc_18001BB8E
0x18001b80e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001b812  xor     eax, eax
0x18001b814  inc     rsi
0x18001b817  cmp     [r14+rsi*2], ax
0x18001b81c  jnz     short loc_18001B814
0x18001b81e  mov     [rsp+1C0h+var_160], r14
0x18001b823  mov     [rsp+1C0h+var_158], rsi
0x18001b828  lea     rdx, [rsp+1C0h+var_160]
0x18001b82d  mov     rcx, rbx
0x18001b830  call    AppendEscapedXml
0x18001b835  test    al, al
0x18001b837  jz      loc_18001BA91
0x18001b83d  inc     rsi
0x18001b840  add     rdi, rsi
0x18001b843  xor     esi, esi
0x18001b845  jmp     short loc_18001B7E5
0x18001b847  mov     r8d, 9
0x18001b84d  lea     rdx, aOpcode_0; "</Opcode>"
0x18001b854  mov     rcx, rbx
0x18001b857  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18001b85c  xor     r13d, r13d
0x18001b85f  test    al, al
0x18001b861  jz      loc_18001BB8E
0x18001b867  mov     dil, 1
0x18001b86a  mov     r14, [rbp+0C0h+var_130]
0x18001b86e  mov     r12, [rbp+0C0h+var_128]
0x18001b872  lea     rax, [rbp+0C0h+var_D8]
0x18001b876  mov     [rsp+1C0h+var_188], rax
0x18001b87b  mov     [rsp+1C0h+var_190], 6
0x18001b883  lea     rax, [rbp+0C0h+var_140]
0x18001b887  mov     [rsp+1C0h+var_198], rax
0x18001b88c  mov     [rsp+1C0h+var_1A0], 0FFFFFFFFh
0x18001b894  mov     r9, r12
0x18001b897  mov     r8, r14
0x18001b89a  mov     rdx, r15
0x18001b89d  lea     rcx, [rsp+1C0h+var_160]
0x18001b8a2  call    GetRenderedMessageFromService
0x18001b8a7  mov     rcx, [rax]
0x18001b8aa  mov     [rsp+1C0h+var_180], rcx
  ... truncated ...
```
