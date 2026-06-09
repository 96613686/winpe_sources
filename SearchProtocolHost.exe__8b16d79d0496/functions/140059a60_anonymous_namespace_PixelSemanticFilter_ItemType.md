# _anonymous_namespace_::PixelSemanticFilter::ItemType

- ea: `0x140059a60`
- end: `0x140059fc0`
- name: `_anonymous_namespace_::PixelSemanticFilter::ItemType`
- size: `1376`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140005240`
- `0x1400104ec`
- `0x14001eb94`
- `0x140028044`
- `0x14003221c`
- `0x140032f70`
- `0x140050c1c`
- `0x14005109c`
- `0x14005472c`
- `0x14005838c`
- `0x1400586ac`
- `0x140058710`
- `0x140058748`
- `0x140058930`
- `0x140059a60`
- `0x14005a8d8`
- `0x14005adb0`
- `0x14005ae2c`
- `0x14005af20`
- `0x14005af5c`
- `0x14005afcc`
- `0x14005affc`
- `0x14005bb78`
- `0x140070010`

## string_xrefs

- `0x140059dea`: `onecoreuap\base\appmodel\search\common\filterpipeline\pixelsemanticfilter.cpp`
- `0x140059e48`: `onecoreuap\base\appmodel\search\common\filterpipeline\pixelsemanticfilter.cpp`
- `0x140059eca`: `onecoreuap\base\appmodel\search\common\filterpipeline\pixelsemanticfilter.cpp`
- `0x140059f28`: `onecoreuap\base\appmodel\search\common\filterpipeline\pixelsemanticfilter.cpp`
- `0x140059cab`: `onecoreuap\base\appmodel\search\common\filterpipeline\pixelsemanticfilter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::PixelSemanticFilter::ItemType(__int64 a1, _DWORD *a2)
{
  __int64 result; // rax
  const wchar_t *v5; // rbx
  volatile signed __int32 *v6; // rdx
  _QWORD *v7; // rax
  int v8; // r15d
  _QWORD *v9; // rax
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  char IsEnabled; // al
  __int64 v16; // rcx
  bool v17; // zf
  __int64 (__fastcall *v18)(__int64, _BYTE *, __int128 *, __int64 (__fastcall ***)(), __int64, __int64); // rax
  __int64 v19; // rax
  const wchar_t *v20; // r9
  __int64 v21; // rax
  char v22; // al
  __int64 v23; // rcx
  __int64 (__fastcall *v24)(__int64, _BYTE *, __int128 *, __int64 (__fastcall ***)(), __int64, __int64); // rax
  __int64 v25; // rax
  const wchar_t *v26; // r9
  __int64 v27; // rax
  const char *v28; // r9
  unsigned int v29; // eax
  int v30; // [rsp+20h] [rbp-E8h]
  __int64 v31; // [rsp+20h] [rbp-E8h]
  __int64 v32; // [rsp+20h] [rbp-E8h]
  __int64 v33; // [rsp+28h] [rbp-E0h]
  __int64 v34; // [rsp+28h] [rbp-E0h]
  LPVOID pv; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v36; // [rsp+48h] [rbp-C0h] BYREF
  __int64 (__fastcall **v37)(); // [rsp+50h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+58h] [rbp-B0h]
  _BYTE v39[64]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+A0h] [rbp-68h]
  __int64 v41; // [rsp+A8h] [rbp-60h] BYREF
  int v42; // [rsp+B0h] [rbp-58h]
  __int128 v43; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v44; // [rsp+C8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v40 = -2;
  try
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56182531>::GetImpl'::`2'::impl)
      && !a2 )
    {
      return 2147500035LL;
    }
    v5 = (const wchar_t *)(a1 + 88);
    if ( *(_QWORD *)(a1 + 104) )
    {
      *a2 = 4;
      *(_DWORD *)(a1 + 80) = 4;
      return 0;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57180361>::GetImpl'::`2'::impl)
      && *(_QWORD *)(a1 + 120) != *(_QWORD *)(a1 + 128) )
    {
      *a2 = 1;
      *(_DWORD *)(a1 + 80) = 1;
      return 0;
    }
    result = (*(__int64 (__fastcall **)(_QWORD, _DWORD *))(**(_QWORD **)(a1 + 56) + 40LL))(*(_QWORD *)(a1 + 56), a2);
    *(_DWORD *)(a1 + 80) = *a2;
    if ( !(_DWORD)result )
    {
      if ( *a2 == 3 )
      {
        ++*(_DWORD *)(a1 + 216);
        *(_QWORD *)(a1 + 144) = v37;
        *(_DWORD *)(a1 + 152) = v38;
        *(_BYTE *)(a1 + 156) = 0;
        *(_WORD *)(a1 + 157) = *(_WORD *)((char *)&v38 + 5);
        *(_BYTE *)(a1 + 159) = HIBYTE(v38);
        embedding::embedding((embedding *)v39);
        embedding::operator=(a1 + 160, v39);
        std::_Variant_base<std::vector<float>,std::vector<enum gsl::byte>>::_Destroy(v39);
        v41 = 0;
        v42 = 0;
        pv = 0;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60493341>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60493341>::GetImpl'::`2'::impl) )
        {
          v6 = *(volatile signed __int32 **)(tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>>((struct wil::details::IFailureCallback *)v39)
                                           + 56);
          pv = (LPVOID)v6;
          if ( v6 )
            _InterlockedIncrement(v6 + 78);
          tip2::test_watcher<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::~test_watcher<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>(v39);
          v7 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::operator->(
                           &pv,
                           &v36);
          std::wstring::operator=(*v7 + 272LL, a1 + 224);
          tip2::test_data_control<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::~test_data_control<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>(&v36);
        }
        v8 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 48) + 64LL))(*(_QWORD *)(a1 + 48), &v41);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60493341>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60493341>::GetImpl'::`2'::impl) )
        {
          *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::operator->(
                                   &pv,
                                   &v36)
                    + 304LL) = v8;
          tip2::test_data_control<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::~test_data_control<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>(&v36);
          v9 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::operator->(
                           &pv,
                           &v36);
          tip2::details::shared_data<0,0,0>::complete_helper(*v9 + 8LL, 2048, 10);
          tip2::test_data_control<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::~test_data_control<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>(&v36);
          if ( v8 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xE4,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\filterpipeline\\pixelsemanticfilter.cpp",
              (const char *)(unsigned int)v8,
              v30);
            wil::com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>(&pv);
            return (unsigned int)v8;
          }
        }
        else if ( v8 == -2147215602 )
        {
          wil::com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>(&pv);
          return 2147500037LL;
        }
        v10 = v42;
        *(_QWORD *)(a1 + 144) = v41;
        *(_DWORD *)(a1 + 152) = v10;
        if ( !*(_BYTE *)(a1 + 156) )
          *(_BYTE *)(a1 + 156) = 1;
        v11 = anonymous_namespace_::to_image_metadata(v39, a1 + 144);
        v43 = *(_OWORD *)v11;
        v44 = *(_QWORD *)(v11 + 16);
        v37 = off_1400726B0;
        v38 = *(_QWORD *)(a1 + 48);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57180361>::GetImpl'::`2'::impl) )
          std::vector<std::wstring>::clear(a1 + 120, v12, v13, v14);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56182531>::GetImpl'::`2'::impl) )
        {
          IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_48532826>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_48532826>::GetImpl'::`2'::impl);
          v16 = *(_QWORD *)(a1 + 192);
          v33 = a1 + 120;
          v31 = a1 + 88;
          v17 = IsEnabled == 0;
          v18 = *(__int64 (__fastcall **)(__int64, _BYTE *, __int128 *, __int64 (__fastcall ***)(), __int64, __int64))(*(_QWORD *)v16 + 8LL);
          if ( v17 )
          {
            v21 = v18(v16, v39, &v43, &v37, v31, v33);
            embedding::operator=(a1 + 160, v21);
            std::_Variant_base<std::vector<float>,std::vector<enum gsl::byte>>::_Destroy(v39);
            *(_QWORD *)(a1 + 104) = 0;
            if ( *(_QWORD *)(a1 + 112) > 7u )
              v5 = *(const wchar_t **)v5;
            *v5 = 0;
          }
          else
          {
            v19 = v18(v16, v39, &v43, &v37, v31, v33);
            embedding::operator=(a1 + 160, v19);
            std::_Variant_base<std::vector<float>,std::vector<enum gsl::byte>>::_Destroy(v39);
            if ( *(_QWORD *)(a1 + 112) > 7u )
              v5 = *(const wchar_t **)v5;
            SearchIndexerTrace::Information(
              (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\filterpipeline\\pixelsemanticfilter.cpp",
              (const wchar_t *)0xFC,
              (unsigned int)L"Extacted OCR Text: m_ocrText: %s",
              v5);
            *(_DWORD *)(a1 + 212) = *(_DWORD *)(a1 + 104);
            *(_DWORD *)(a1 + 208) = 0;
          }
          SearchIndexerDebug::Verbose(
            (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\filterpipeline\\pixelsemanticfilter.cpp",
            (const wchar_t *)0x105,
            (unsigned int)L"Image embedding generated in PixelSemanticFilter\n",
            v20);
        }
        else
        {
          try
          {
            v22 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_48532826>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_48532826>::GetImpl'::`2'::impl);
            v23 = *(_QWORD *)(a1 + 192);
            v34 = a1 + 120;
            v32 = a1 + 88;
            v17 = v22 == 0;
            v24 = *(__int64 (__fastcall **)(__int64, _BYTE *, __int128 *, __int64 (__fastcall ***)(), __int64, __int64))(*(_QWORD *)v23 + 8LL);
            if ( v17 )
            {
              v27 = v24(v23, v39, &v43, &v37, v32, v34);
              embedding::operator=(a1 + 160, v27);
              std::_Variant_base<std::vector<float>,std::vector<enum gsl::byte>>::_Destroy(v39);
              *(_QWORD *)(a1 + 104) = 0;
              if ( *(_QWORD *)(a1 + 112) > 7u )
                v5 = *(const wchar_t **)v5;
              *v5 = 0;
            }
            else
            {
              v25 = v24(v23, v39, &v43, &v37, v32, v34);
              embedding::operator=(a1 + 160, v25);
              std::_Variant_base<std::vector<float>,std::vector<enum gsl::byte>>::_Destroy(v39);
              if ( *(_QWORD *)(a1 + 112) > 7u )
                v5 = *(const wchar_t **)v5;
              SearchIndexerTrace::Information(
                (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\filterpipeline\\pixelsemanticfilter.cpp",
                (const wchar_t *)0x10E,
                (unsigned int)L"Extacted OCR Text: m_ocrText: %s",
                v5);
              *(_DWORD *)(a1 + 212) = *(_DWORD *)(a1 + 104);
              *(_DWORD *)(a1 + 208) = 0;
            }
            SearchIndexerDebug::Verbose(
              (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\filterpipeline\\pixelsemanticfilter.cpp",
              (const wchar_t *)0x117,
              (unsigned int)L"Image embedding generated in PixelSemanticFilter\n",
              v26);
          }
          catch ( ... )
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56631575>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56631575>::GetImpl'::`2'::impl) )
            {
              v36 = wil::details::in1diag3::Log_CaughtException(
                      retaddr,
                      (void *)0x11F,
                      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\filterpipeline\\pixelsemanticfilter.cpp",
                      v28);
              wil::com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>(&pv);
              return v36;
            }
            v29 = wil::details::in1diag3::Log_CaughtException(
                    retaddr,
                    (void *)0x123,
                    (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\filterpipeline\\pixelsemanticfilter.cpp",
                    v28);
            SemanticSearchTelemetryAggregated::ReportSemanticRequeueRequested(0, v29);
            wil::com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>(&pv);
            return 2147750438LL;
          }
        }
        if ( embedding::empty((embedding *)(a1 + 160)) )
        {
          *a2 = 0;
          wil::com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>(&pv);
          return 2147500037LL;
        }
        *a2 = 2;
        *(_DWORD *)(a1 + 80) = 2;
        wil::com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>(&pv);
      }
      result = 0;
    }
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      312,
      "onecoreuap\\base\\appmodel\\search\\common\\filterpipeline\\pixelsemanticfilter.cpp");
  }
  return result;
}

```

## disassembly

```asm
0x140059a60  mov     rax, rsp
0x140059a63  push    rsi
0x140059a64  push    rdi
0x140059a65  push    r12
0x140059a67  push    r14
0x140059a69  push    r15
0x140059a6b  sub     rsp, 0E0h
0x140059a72  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x140059a7a  mov     [rax+18h], rbx
0x140059a7e  mov     rax, cs:__security_cookie
0x140059a85  xor     rax, rsp
0x140059a88  mov     [rsp+108h+var_38], rax
0x140059a90  mov     rsi, rdx
0x140059a93  mov     rdi, rcx
0x140059a96  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56182531@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56182531@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531> `wil::Feature<__WilFeatureTraits_Feature_56182531>::GetImpl(void)'::`2'::impl
0x140059a9d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56182531@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531>::__private_IsEnabled(void)
0x140059aa2  test    al, al
0x140059aa4  jnz     short loc_140059AB5
0x140059aa6  test    rsi, rsi
0x140059aa9  jnz     short loc_140059AB5
0x140059aab  mov     eax, 80004003h
0x140059ab0  jmp     loc_140059F97
0x140059ab5  lea     rbx, [rdi+58h]
0x140059ab9  cmp     qword ptr [rbx+10h], 0
0x140059abe  jz      short loc_140059AD1
0x140059ac0  mov     eax, 4
0x140059ac5  mov     [rsi], eax
0x140059ac7  mov     [rdi+50h], eax
0x140059aca  xor     eax, eax
0x140059acc  jmp     loc_140059F97
0x140059ad1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57180361@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57180361@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361> `wil::Feature<__WilFeatureTraits_Feature_57180361>::GetImpl(void)'::`2'::impl
0x140059ad8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57180361@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361>::__private_IsEnabled(void)
0x140059add  test    al, al
0x140059adf  jz      short loc_140059B02
0x140059ae1  mov     rax, [rdi+80h]
0x140059ae8  cmp     [rdi+78h], rax
0x140059aec  jz      short loc_140059B02
0x140059aee  mov     dword ptr [rsi], 1
0x140059af4  mov     dword ptr [rdi+50h], 1
0x140059afb  xor     eax, eax
0x140059afd  jmp     loc_140059F97
0x140059b02  mov     rcx, [rdi+38h]
0x140059b06  mov     rax, [rcx]
0x140059b09  mov     rdx, rsi
0x140059b0c  mov     rax, [rax+28h]
0x140059b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059b15  mov     ecx, [rsi]
0x140059b17  mov     [rdi+50h], ecx
0x140059b1a  test    eax, eax
0x140059b1c  jnz     loc_140059F97
0x140059b22  cmp     dword ptr [rsi], 3
0x140059b25  jnz     loc_140059F8F
0x140059b2b  inc     dword ptr [rdi+0D8h]
0x140059b31  lea     r14, [rdi+90h]
0x140059b38  movsd   xmm0, [rsp+108h+var_B8]
0x140059b3e  movsd   qword ptr [r14], xmm0
0x140059b43  mov     eax, dword ptr [rsp+108h+var_B0]
0x140059b47  mov     [r14+8], eax
0x140059b4b  mov     byte ptr [r14+0Ch], 0
0x140059b50  movzx   eax, word ptr [rsp+108h+var_B0+5]
0x140059b55  mov     [r14+0Dh], ax
0x140059b5a  mov     al, byte ptr [rsp+108h+var_B0+7]
0x140059b5e  mov     [r14+0Fh], al
0x140059b62  lea     rcx, [rsp+108h+var_A8]; this
0x140059b67  call    ??0embedding@@QEAA@XZ; embedding::embedding(void)
0x140059b6c  lea     r12, [rdi+0A0h]
0x140059b73  lea     rdx, [rsp+108h+var_A8]
0x140059b78  mov     rcx, r12
0x140059b7b  call    ??4embedding@@QEAAAEAU0@$$QEAU0@@Z; embedding::operator=(embedding &&)
0x140059b80  lea     rcx, [rsp+108h+var_A8]
0x140059b85  call    ?_Destroy@?$_Variant_base@V?$vector@MV?$allocator@M@std@@@std@@V?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@2@@std@@QEAAXXZ; std::_Variant_base<std::vector<float>,std::vector<gsl::byte>>::_Destroy(void)
0x140059b8a  xor     eax, eax
0x140059b8c  mov     [rsp+108h+var_60], rax
0x140059b94  mov     [rsp+108h+var_58], eax
0x140059b9b  mov     [rsp+108h+pv], rax
0x140059ba0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60493341@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60493341@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60493341> `wil::Feature<__WilFeatureTraits_Feature_60493341>::GetImpl(void)'::`2'::impl
0x140059ba7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60493341@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60493341>::__private_IsEnabled(void)
0x140059bac  test    al, al
0x140059bae  jz      short loc_140059C19
0x140059bb0  lea     rcx, [rsp+108h+var_A8]; struct wil::details::IFailureCallback *
0x140059bb5  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x140059bba  mov     rdx, [rax+38h]
0x140059bbe  mov     rcx, [rsp+108h+pv]; pv
0x140059bc3  mov     [rsp+108h+pv], rdx
0x140059bc8  test    rdx, rdx
0x140059bcb  jz      short loc_140059BD4
0x140059bcd  lock inc dword ptr [rdx+138h]
0x140059bd4  test    rcx, rcx
0x140059bd7  jz      short loc_140059BDE
0x140059bd9  call    ?Release@?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>::Release(void)
0x140059bde  lea     rcx, [rsp+108h+var_A8]
0x140059be3  call    ??1?$test_watcher@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::~test_watcher<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>(void)
0x140059be8  lea     rdx, [rsp+108h+var_C0]
0x140059bed  lea     rcx, [rsp+108h+pv]
0x140059bf2  call    ??C?$tip_test@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::operator->(void)
0x140059bf7  nop
0x140059bf8  lea     rdx, [rdi+0E0h]
0x140059bff  mov     rcx, [rax]
0x140059c02  add     rcx, 110h
0x140059c09  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x140059c0e  nop
0x140059c0f  lea     rcx, [rsp+108h+var_C0]
0x140059c14  call    ??1?$test_data_control@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::~test_data_control<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>(void)
0x140059c19  mov     rcx, [rdi+30h]
0x140059c1d  mov     rax, [rcx]
0x140059c20  lea     rdx, [rsp+108h+var_60]
0x140059c28  mov     rax, [rax+40h]
0x140059c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059c31  mov     r15d, eax
0x140059c34  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60493341@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60493341@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60493341> `wil::Feature<__WilFeatureTraits_Feature_60493341>::GetImpl(void)'::`2'::impl
0x140059c3b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60493341@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60493341>::__private_IsEnabled(void)
0x140059c40  test    al, al
0x140059c42  jz      loc_140059CCF
0x140059c48  lea     rdx, [rsp+108h+var_C0]
0x140059c4d  lea     rcx, [rsp+108h+pv]
0x140059c52  call    ??C?$tip_test@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::operator->(void)
0x140059c57  mov     rcx, [rax]
0x140059c5a  mov     [rcx+130h], r15d
0x140059c61  lea     rcx, [rsp+108h+var_C0]
0x140059c66  call    ??1?$test_data_control@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::~test_data_control<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>(void)
0x140059c6b  lea     rdx, [rsp+108h+var_C0]
0x140059c70  lea     rcx, [rsp+108h+pv]
0x140059c75  call    ??C?$tip_test@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::operator->(void)
0x140059c7a  mov     rcx, [rax]
0x140059c7d  add     rcx, 8
0x140059c81  mov     edx, 800h
0x140059c86  mov     r8d, 0Ah
0x140059c8c  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestFlags@@W4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestFlags,TestQueryOptions)
0x140059c91  lea     rcx, [rsp+108h+var_C0]
0x140059c96  call    ??1?$test_data_control@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::~test_data_control<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>(void)
0x140059c9b  test    r15d, r15d
0x140059c9e  jns     short loc_140059CEC
0x140059ca0  mov     rcx, [rsp+108h]; this
0x140059ca8  mov     r9d, r15d; char *
0x140059cab  lea     r8, aOnecoreuapBase_49; "onecoreuap\\base\\appmodel\\search\\com"...
0x140059cb2  mov     edx, 0E4h; void *
0x140059cb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140059cbc  nop
0x140059cbd  lea     rcx, [rsp+108h+pv]
0x140059cc2  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>(void)
0x140059cc7  mov     eax, r15d
0x140059cca  jmp     loc_140059F97
0x140059ccf  cmp     r15d, 8004170Eh
0x140059cd6  jnz     short loc_140059CEC
0x140059cd8  lea     rcx, [rsp+108h+pv]
0x140059cdd  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>(void)
0x140059ce2  mov     eax, 80004005h
0x140059ce7  jmp     loc_140059F97
0x140059cec  movsd   xmm0, [rsp+108h+var_60]
0x140059cf5  mov     eax, [rsp+108h+var_58]
0x140059cfc  movsd   qword ptr [r14], xmm0
0x140059d01  mov     [r14+8], eax
0x140059d05  cmp     byte ptr [r14+0Ch], 0
0x140059d0a  jnz     short loc_140059D11
0x140059d0c  mov     byte ptr [r14+0Ch], 1
0x140059d11  mov     rdx, r14
0x140059d14  lea     rcx, [rsp+108h+var_A8]
0x140059d19  call    _anonymous_namespace___to_image_metadata
0x140059d1e  movups  xmm0, xmmword ptr [rax]
0x140059d21  movups  [rsp+108h+var_50], xmm0
0x140059d29  movsd   xmm1, qword ptr [rax+10h]
0x140059d2e  movsd   [rsp+108h+var_40], xmm1
0x140059d37  lea     rax, off_1400726B0
0x140059d3e  mov     [rsp+108h+var_B8], rax
0x140059d43  mov     rax, [rdi+30h]
0x140059d47  mov     [rsp+108h+var_B0], rax
0x140059d4c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57180361@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57180361@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361> `wil::Feature<__WilFeatureTraits_Feature_57180361>::GetImpl(void)'::`2'::impl
0x140059d53  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57180361@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361>::__private_IsEnabled(void)
0x140059d58  test    al, al
0x140059d5a  jz      short loc_140059D65
0x140059d5c  lea     rcx, [rdi+78h]
0x140059d60  call    ?clear@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x140059d65  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56182531@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56182531@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531> `wil::Feature<__WilFeatureTraits_Feature_56182531>::GetImpl(void)'::`2'::impl
0x140059d6c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56182531@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531>::__private_IsEnabled(void)
0x140059d71  test    al, al
0x140059d73  jz      loc_140059E59
0x140059d79  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_48532826@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_48532826@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_48532826> `wil::Feature<__WilFeatureTraits_Feature_48532826>::GetImpl(void)'::`2'::impl
0x140059d80  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_48532826@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_48532826>::__private_IsEnabled(void)
0x140059d85  lea     rdx, [rdi+78h]
0x140059d89  mov     rcx, [rdi+0C0h]
0x140059d90  mov     [rsp+108h+var_E0], rdx
0x140059d95  lea     r9, [rsp+108h+var_B8]
0x140059d9a  lea     r8, [rsp+108h+var_50]
0x140059da2  mov     [rsp+108h+var_E8], rbx
0x140059da7  lea     rdx, [rsp+108h+var_A8]
0x140059dac  test    al, al
0x140059dae  mov     rax, [rcx]
0x140059db1  mov     rax, [rax+8]
0x140059db5  jz      short loc_140059E0B
0x140059db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059dbc  mov     rdx, rax
0x140059dbf  mov     rcx, r12
0x140059dc2  call    ??4embedding@@QEAAAEAU0@$$QEAU0@@Z; embedding::operator=(embedding &&)
0x140059dc7  lea     rcx, [rsp+108h+var_A8]
0x140059dcc  call    ?_Destroy@?$_Variant_base@V?$vector@MV?$allocator@M@std@@@std@@V?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@2@@std@@QEAAXXZ; std::_Variant_base<std::vector<float>,std::vector<gsl::byte>>::_Destroy(void)
0x140059dd1  cmp     qword ptr [rbx+18h], 7
0x140059dd6  jbe     short loc_140059DDB
0x140059dd8  mov     rbx, [rbx]
0x140059ddb  mov     r9, rbx; wchar_t *
0x140059dde  lea     r8, aExtactedOcrTex; "Extacted OCR Text: m_ocrText: %s"
0x140059de5  mov     edx, 0FCh; wchar_t *
0x140059dea  lea     rcx, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\com"...
0x140059df1  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x140059df6  mov     eax, [rdi+68h]
0x140059df9  mov     [rdi+0D4h], eax
0x140059dff  mov     dword ptr [rdi+0D0h], 0
0x140059e09  jmp     short loc_140059E3C
0x140059e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059e10  mov     rdx, rax
0x140059e13  mov     rcx, r12
0x140059e16  call    ??4embedding@@QEAAAEAU0@$$QEAU0@@Z; embedding::operator=(embedding &&)
0x140059e1b  lea     rcx, [rsp+108h+var_A8]
0x140059e20  call    ?_Destroy@?$_Variant_base@V?$vector@MV?$allocator@M@std@@@std@@V?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@2@@std@@QEAAXXZ; std::_Variant_base<std::vector<float>,std::vector<gsl::byte>>::_Destroy(void)
0x140059e25  mov     qword ptr [rbx+10h], 0
0x140059e2d  cmp     qword ptr [rbx+18h], 7
0x140059e32  jbe     short loc_140059E37
0x140059e34  mov     rbx, [rbx]
0x140059e37  xor     eax, eax
0x140059e39  mov     [rbx], ax
0x140059e3c  lea     r8, aImageEmbedding; "Image embedding generated in PixelSeman"...
0x140059e43  mov     edx, 105h; wchar_t *
0x140059e48  lea     rcx, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\com"...
0x140059e4f  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x140059e54  jmp     loc_140059F35
0x140059e59  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_48532826@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_48532826@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_48532826> `wil::Feature<__WilFeatureTraits_Feature_48532826>::GetImpl(void)'::`2'::impl
0x140059e60  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_48532826@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_48532826>::__private_IsEnabled(void)
0x140059e65  lea     rdx, [rdi+78h]
0x140059e69  mov     rcx, [rdi+0C0h]
0x140059e70  mov     [rsp+108h+var_E0], rdx
0x140059e75  lea     r9, [rsp+108h+var_B8]
0x140059e7a  lea     r8, [rsp+108h+var_50]
0x140059e82  mov     [rsp+108h+var_E8], rbx
0x140059e87  lea     rdx, [rsp+108h+var_A8]
0x140059e8c  test    al, al
0x140059e8e  mov     rax, [rcx]
0x140059e91  mov     rax, [rax+8]
0x140059e95  jz      short loc_140059EEB
0x140059e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059e9c  mov     rdx, rax
0x140059e9f  mov     rcx, r12
0x140059ea2  call    ??4embedding@@QEAAAEAU0@$$QEAU0@@Z; embedding::operator=(embedding &&)
0x140059ea7  lea     rcx, [rsp+108h+var_A8]
0x140059eac  call    ?_Destroy@?$_Variant_base@V?$vector@MV?$allocator@M@std@@@std@@V?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@2@@std@@QEAAXXZ; std::_Variant_base<std::vector<float>,std::vector<gsl::byte>>::_Destroy(void)
0x140059eb1  cmp     qword ptr [rbx+18h], 7
0x140059eb6  jbe     short loc_140059EBB
0x140059eb8  mov     rbx, [rbx]
0x140059ebb  mov     r9, rbx; wchar_t *
0x140059ebe  lea     r8, aExtactedOcrTex; "Extacted OCR Text: m_ocrText: %s"
0x140059ec5  mov     edx, 10Eh; wchar_t *
0x140059eca  lea     rcx, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\com"...
0x140059ed1  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x140059ed6  mov     eax, [rdi+68h]
0x140059ed9  mov     [rdi+0D4h], eax
0x140059edf  mov     dword ptr [rdi+0D0h], 0
0x140059ee9  jmp     short loc_140059F1C
0x140059eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059ef0  mov     rdx, rax
0x140059ef3  mov     rcx, r12
0x140059ef6  call    ??4embedding@@QEAAAEAU0@$$QEAU0@@Z; embedding::operator=(embedding &&)
0x140059efb  lea     rcx, [rsp+108h+var_A8]
0x140059f00  call    ?_Destroy@?$_Variant_base@V?$vector@MV?$allocator@M@std@@@std@@V?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@2@@std@@QEAAXXZ; std::_Variant_base<std::vector<float>,std::vector<gsl::byte>>::_Destroy(void)
0x140059f05  mov     qword ptr [rbx+10h], 0
0x140059f0d  cmp     qword ptr [rbx+18h], 7
0x140059f12  jbe     short loc_140059F17
0x140059f14  mov     rbx, [rbx]
0x140059f17  xor     eax, eax
0x140059f19  mov     [rbx], ax
0x140059f1c  lea     r8, aImageEmbedding; "Image embedding generated in PixelSeman"...
0x140059f23  mov     edx, 117h; wchar_t *
0x140059f28  lea     rcx, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\com"...
0x140059f2f  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x140059f34  nop
0x140059f35  mov     rcx, r12; this
0x140059f38  call    ?empty@embedding@@QEBA_NXZ; embedding::empty(void)
0x140059f3d  test    al, al
0x140059f3f  jz      short loc_140059F58
0x140059f41  mov     dword ptr [rsi], 0
0x140059f47  lea     rcx, [rsp+108h+pv]
0x140059f4c  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>(void)
0x140059f51  mov     eax, 80004005h
0x140059f56  jmp     short loc_140059F97
0x140059f58  mov     eax, 2
0x140059f5d  mov     [rsi], eax
0x140059f5f  mov     [rdi+50h], eax
0x140059f62  lea     rcx, [rsp+108h+pv]
0x140059f67  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>(void)
0x140059f6c  jmp     short loc_140059F8F
0x140059f6e  lea     rcx, [rsp+108h+pv]
0x140059f73  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>(void)
0x140059f78  mov     eax, [rsp+108h+var_C0]
0x140059f7c  jmp     short loc_140059F97
0x140059f7e  lea     rcx, [rsp+108h+pv]
0x140059f83  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>(void)
0x140059f88  mov     eax, 80041226h
0x140059f8d  jmp     short loc_140059F97
0x140059f8f  xor     eax, eax
0x140059f91  jmp     short loc_140059F97
0x140059f93  mov     eax, [rsp+108h+var_C0]
0x140059f97  mov     rcx, [rsp+108h+var_38]
0x140059f9f  xor     rcx, rsp; StackCookie
  ... truncated ...
```
