# _anonymous_namespace_::PixelSemanticFilter::ItemType

- ea: `0x140038f90`
- end: `0x1400394f0`
- name: `_anonymous_namespace_::PixelSemanticFilter::ItemType`
- size: `1376`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400030a0`
- `0x140009f14`
- `0x14000e378`
- `0x1400155e0`
- `0x140015a7c`
- `0x14002dfb4`
- `0x140032644`
- `0x140033fb0`
- `0x1400342b8`
- `0x140037af0`
- `0x140037db0`
- `0x140037e14`
- `0x140037e4c`
- `0x14003805c`
- `0x140038f90`
- `0x140039db0`
- `0x14003a1fc`
- `0x14003a2f0`
- `0x14003a32c`
- `0x14003a368`
- `0x14003a6d8`
- `0x1400497e8`
- `0x140049ae0`
- `0x14004f010`

## string_xrefs

- `0x1400391db`: `onecoreuap\base\appmodel\search\common\filterpipeline\pixelsemanticfilter.cpp`
- `0x14003931a`: `onecoreuap\base\appmodel\search\common\filterpipeline\pixelsemanticfilter.cpp`
- `0x140039378`: `onecoreuap\base\appmodel\search\common\filterpipeline\pixelsemanticfilter.cpp`
- `0x1400393fa`: `onecoreuap\base\appmodel\search\common\filterpipeline\pixelsemanticfilter.cpp`
- `0x140039458`: `onecoreuap\base\appmodel\search\common\filterpipeline\pixelsemanticfilter.cpp`

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
  int v29; // [rsp+20h] [rbp-E8h]
  __int64 v30; // [rsp+20h] [rbp-E8h]
  __int64 v31; // [rsp+20h] [rbp-E8h]
  __int64 v32; // [rsp+28h] [rbp-E0h]
  __int64 v33; // [rsp+28h] [rbp-E0h]
  LPVOID pv; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v35; // [rsp+48h] [rbp-C0h] BYREF
  __int64 (__fastcall **v36)(); // [rsp+50h] [rbp-B8h] BYREF
  __int64 v37; // [rsp+58h] [rbp-B0h]
  _BYTE v38[64]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-68h]
  __int64 v40; // [rsp+A8h] [rbp-60h] BYREF
  int v41; // [rsp+B0h] [rbp-58h]
  __int128 v42; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v43; // [rsp+C8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v39 = -2;
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
        *(_QWORD *)(a1 + 144) = v36;
        *(_DWORD *)(a1 + 152) = v37;
        *(_BYTE *)(a1 + 156) = 0;
        *(_WORD *)(a1 + 157) = *(_WORD *)((char *)&v37 + 5);
        *(_BYTE *)(a1 + 159) = HIBYTE(v37);
        embedding::embedding((embedding *)v38);
        embedding::operator=(a1 + 160, v38);
        std::_Variant_base<std::vector<float>,std::vector<enum gsl::byte>>::_Destroy((__int64)v38);
        v40 = 0;
        v41 = 0;
        pv = 0;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60493341>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60493341>::GetImpl'::`2'::impl) )
        {
          v6 = *(volatile signed __int32 **)(tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>>((struct wil::details::IFailureCallback *)v38)
                                           + 56);
          pv = (LPVOID)v6;
          if ( v6 )
            _InterlockedIncrement(v6 + 78);
          tip2::test_watcher<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::~test_watcher<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>(v38);
          v7 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::operator->(
                           &pv,
                           &v35);
          std::wstring::operator=(*v7 + 272LL, a1 + 224);
          tip2::test_data_control<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::~test_data_control<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>(&v35);
        }
        v8 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 48) + 64LL))(*(_QWORD *)(a1 + 48), &v40);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60493341>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60493341>::GetImpl'::`2'::impl) )
        {
          *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::operator->(
                                   &pv,
                                   &v35)
                    + 304LL) = v8;
          tip2::test_data_control<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::~test_data_control<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>(&v35);
          v9 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::operator->(
                           &pv,
                           &v35);
          tip2::details::shared_data<0,0,0>::complete_helper(*v9 + 8LL, 2048, 10);
          tip2::test_data_control<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::~test_data_control<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>(&v35);
          if ( v8 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xE4,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\filterpipeline\\pixelsemanticfilter.cpp",
              (const char *)(unsigned int)v8,
              v29);
            wil::com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>(&pv);
            return (unsigned int)v8;
          }
        }
        else if ( v8 == -2147215602 )
        {
          wil::com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>(&pv);
          return 2147500037LL;
        }
        v10 = v41;
        *(_QWORD *)(a1 + 144) = v40;
        *(_DWORD *)(a1 + 152) = v10;
        if ( !*(_BYTE *)(a1 + 156) )
          *(_BYTE *)(a1 + 156) = 1;
        v11 = anonymous_namespace_::to_image_metadata(v38, a1 + 144);
        v42 = *(_OWORD *)v11;
        v43 = *(_QWORD *)(v11 + 16);
        v36 = off_140051050;
        v37 = *(_QWORD *)(a1 + 48);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57180361>::GetImpl'::`2'::impl) )
          std::vector<std::wstring>::clear(a1 + 120, v12, v13, v14);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56182531>::GetImpl'::`2'::impl) )
        {
          IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_48532826>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_48532826>::GetImpl'::`2'::impl);
          v16 = *(_QWORD *)(a1 + 192);
          v32 = a1 + 120;
          v30 = a1 + 88;
          v17 = IsEnabled == 0;
          v18 = *(__int64 (__fastcall **)(__int64, _BYTE *, __int128 *, __int64 (__fastcall ***)(), __int64, __int64))(*(_QWORD *)v16 + 8LL);
          if ( v17 )
          {
            v21 = v18(v16, v38, &v42, &v36, v30, v32);
            embedding::operator=(a1 + 160, v21);
            std::_Variant_base<std::vector<float>,std::vector<enum gsl::byte>>::_Destroy((__int64)v38);
            *(_QWORD *)(a1 + 104) = 0;
            if ( *(_QWORD *)(a1 + 112) > 7u )
              v5 = *(const wchar_t **)v5;
            *v5 = 0;
          }
          else
          {
            v19 = v18(v16, v38, &v42, &v36, v30, v32);
            embedding::operator=(a1 + 160, v19);
            std::_Variant_base<std::vector<float>,std::vector<enum gsl::byte>>::_Destroy((__int64)v38);
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
            v33 = a1 + 120;
            v31 = a1 + 88;
            v17 = v22 == 0;
            v24 = *(__int64 (__fastcall **)(__int64, _BYTE *, __int128 *, __int64 (__fastcall ***)(), __int64, __int64))(*(_QWORD *)v23 + 8LL);
            if ( v17 )
            {
              v27 = v24(v23, v38, &v42, &v36, v31, v33);
              embedding::operator=(a1 + 160, v27);
              std::_Variant_base<std::vector<float>,std::vector<enum gsl::byte>>::_Destroy((__int64)v38);
              *(_QWORD *)(a1 + 104) = 0;
              if ( *(_QWORD *)(a1 + 112) > 7u )
                v5 = *(const wchar_t **)v5;
              *v5 = 0;
            }
            else
            {
              v25 = v24(v23, v38, &v42, &v36, v31, v33);
              embedding::operator=(a1 + 160, v25);
              std::_Variant_base<std::vector<float>,std::vector<enum gsl::byte>>::_Destroy((__int64)v38);
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
              v35 = wil::details::in1diag3::Log_CaughtException(
                      retaddr,
                      (void *)0x11F,
                      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\filterpipeline\\pixelsemanticfilter.cpp",
                      v28);
              wil::com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>(&pv);
              return v35;
            }
            wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0x123,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\filterpipeline\\pixelsemanticfilter.cpp",
              v28);
            SemanticSearchTelemetryAggregated::ReportSemanticRequeueRequested(0);
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
    indexer::result::details::result_from_caught_exception<1>();
  }
  return result;
}

```

## disassembly

```asm
0x140038f90  mov     rax, rsp
0x140038f93  push    rsi
0x140038f94  push    rdi
0x140038f95  push    r12
0x140038f97  push    r14
0x140038f99  push    r15
0x140038f9b  sub     rsp, 0E0h
0x140038fa2  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x140038faa  mov     [rax+18h], rbx
0x140038fae  mov     rax, cs:__security_cookie
0x140038fb5  xor     rax, rsp
0x140038fb8  mov     [rsp+108h+var_38], rax
0x140038fc0  mov     rsi, rdx
0x140038fc3  mov     rdi, rcx
0x140038fc6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56182531@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56182531@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531> `wil::Feature<__WilFeatureTraits_Feature_56182531>::GetImpl(void)'::`2'::impl
0x140038fcd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56182531@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531>::__private_IsEnabled(void)
0x140038fd2  test    al, al
0x140038fd4  jnz     short loc_140038FE5
0x140038fd6  test    rsi, rsi
0x140038fd9  jnz     short loc_140038FE5
0x140038fdb  mov     eax, 80004003h
0x140038fe0  jmp     loc_1400394C7
0x140038fe5  lea     rbx, [rdi+58h]
0x140038fe9  cmp     qword ptr [rbx+10h], 0
0x140038fee  jz      short loc_140039001
0x140038ff0  mov     eax, 4
0x140038ff5  mov     [rsi], eax
0x140038ff7  mov     [rdi+50h], eax
0x140038ffa  xor     eax, eax
0x140038ffc  jmp     loc_1400394C7
0x140039001  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57180361@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57180361@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361> `wil::Feature<__WilFeatureTraits_Feature_57180361>::GetImpl(void)'::`2'::impl
0x140039008  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57180361@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361>::__private_IsEnabled(void)
0x14003900d  test    al, al
0x14003900f  jz      short loc_140039032
0x140039011  mov     rax, [rdi+80h]
0x140039018  cmp     [rdi+78h], rax
0x14003901c  jz      short loc_140039032
0x14003901e  mov     dword ptr [rsi], 1
0x140039024  mov     dword ptr [rdi+50h], 1
0x14003902b  xor     eax, eax
0x14003902d  jmp     loc_1400394C7
0x140039032  mov     rcx, [rdi+38h]
0x140039036  mov     rax, [rcx]
0x140039039  mov     rdx, rsi
0x14003903c  mov     rax, [rax+28h]
0x140039040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039045  mov     ecx, [rsi]
0x140039047  mov     [rdi+50h], ecx
0x14003904a  test    eax, eax
0x14003904c  jnz     loc_1400394C7
0x140039052  cmp     dword ptr [rsi], 3
0x140039055  jnz     loc_1400394BF
0x14003905b  inc     dword ptr [rdi+0D8h]
0x140039061  lea     r14, [rdi+90h]
0x140039068  movsd   xmm0, [rsp+108h+var_B8]
0x14003906e  movsd   qword ptr [r14], xmm0
0x140039073  mov     eax, dword ptr [rsp+108h+var_B0]
0x140039077  mov     [r14+8], eax
0x14003907b  mov     byte ptr [r14+0Ch], 0
0x140039080  movzx   eax, word ptr [rsp+108h+var_B0+5]
0x140039085  mov     [r14+0Dh], ax
0x14003908a  mov     al, byte ptr [rsp+108h+var_B0+7]
0x14003908e  mov     [r14+0Fh], al
0x140039092  lea     rcx, [rsp+108h+var_A8]; this
0x140039097  call    ??0embedding@@QEAA@XZ; embedding::embedding(void)
0x14003909c  lea     r12, [rdi+0A0h]
0x1400390a3  lea     rdx, [rsp+108h+var_A8]
0x1400390a8  mov     rcx, r12
0x1400390ab  call    ??4embedding@@QEAAAEAU0@$$QEAU0@@Z; embedding::operator=(embedding &&)
0x1400390b0  lea     rcx, [rsp+108h+var_A8]
0x1400390b5  call    ?_Destroy@?$_Variant_base@V?$vector@MV?$allocator@M@std@@@std@@V?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@2@@std@@QEAAXXZ; std::_Variant_base<std::vector<float>,std::vector<gsl::byte>>::_Destroy(void)
0x1400390ba  xor     eax, eax
0x1400390bc  mov     [rsp+108h+var_60], rax
0x1400390c4  mov     [rsp+108h+var_58], eax
0x1400390cb  mov     [rsp+108h+pv], rax
0x1400390d0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60493341@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60493341@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60493341> `wil::Feature<__WilFeatureTraits_Feature_60493341>::GetImpl(void)'::`2'::impl
0x1400390d7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60493341@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60493341>::__private_IsEnabled(void)
0x1400390dc  test    al, al
0x1400390de  jz      short loc_140039149
0x1400390e0  lea     rcx, [rsp+108h+var_A8]; struct wil::details::IFailureCallback *
0x1400390e5  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x1400390ea  mov     rdx, [rax+38h]
0x1400390ee  mov     rcx, [rsp+108h+pv]; pv
0x1400390f3  mov     [rsp+108h+pv], rdx
0x1400390f8  test    rdx, rdx
0x1400390fb  jz      short loc_140039104
0x1400390fd  lock inc dword ptr [rdx+138h]
0x140039104  test    rcx, rcx
0x140039107  jz      short loc_14003910E
0x140039109  call    ?Release@?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>::Release(void)
0x14003910e  lea     rcx, [rsp+108h+var_A8]
0x140039113  call    ??1?$test_watcher@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::~test_watcher<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>(void)
0x140039118  lea     rdx, [rsp+108h+var_C0]
0x14003911d  lea     rcx, [rsp+108h+pv]
0x140039122  call    ??C?$tip_test@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::operator->(void)
0x140039127  nop
0x140039128  lea     rdx, [rdi+0E0h]
0x14003912f  mov     rcx, [rax]
0x140039132  add     rcx, 110h
0x140039139  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14003913e  nop
0x14003913f  lea     rcx, [rsp+108h+var_C0]
0x140039144  call    ??1?$test_data_control@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::~test_data_control<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>(void)
0x140039149  mov     rcx, [rdi+30h]
0x14003914d  mov     rax, [rcx]
0x140039150  lea     rdx, [rsp+108h+var_60]
0x140039158  mov     rax, [rax+40h]
0x14003915c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039161  mov     r15d, eax
0x140039164  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60493341@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60493341@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60493341> `wil::Feature<__WilFeatureTraits_Feature_60493341>::GetImpl(void)'::`2'::impl
0x14003916b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60493341@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60493341>::__private_IsEnabled(void)
0x140039170  test    al, al
0x140039172  jz      loc_1400391FF
0x140039178  lea     rdx, [rsp+108h+var_C0]
0x14003917d  lea     rcx, [rsp+108h+pv]
0x140039182  call    ??C?$tip_test@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::operator->(void)
0x140039187  mov     rcx, [rax]
0x14003918a  mov     [rcx+130h], r15d
0x140039191  lea     rcx, [rsp+108h+var_C0]
0x140039196  call    ??1?$test_data_control@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::~test_data_control<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>(void)
0x14003919b  lea     rdx, [rsp+108h+var_C0]
0x1400391a0  lea     rcx, [rsp+108h+pv]
0x1400391a5  call    ??C?$tip_test@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::operator->(void)
0x1400391aa  mov     rcx, [rax]
0x1400391ad  add     rcx, 8
0x1400391b1  mov     edx, 800h
0x1400391b6  mov     r8d, 0Ah
0x1400391bc  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestFlags@@W4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestFlags,TestQueryOptions)
0x1400391c1  lea     rcx, [rsp+108h+var_C0]
0x1400391c6  call    ??1?$test_data_control@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::~test_data_control<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>(void)
0x1400391cb  test    r15d, r15d
0x1400391ce  jns     short loc_14003921C
0x1400391d0  mov     rcx, [rsp+108h]; this
0x1400391d8  mov     r9d, r15d; char *
0x1400391db  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\appmodel\\search\\com"...
0x1400391e2  mov     edx, 0E4h; void *
0x1400391e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400391ec  nop
0x1400391ed  lea     rcx, [rsp+108h+pv]
0x1400391f2  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>(void)
0x1400391f7  mov     eax, r15d
0x1400391fa  jmp     loc_1400394C7
0x1400391ff  cmp     r15d, 8004170Eh
0x140039206  jnz     short loc_14003921C
0x140039208  lea     rcx, [rsp+108h+pv]
0x14003920d  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>(void)
0x140039212  mov     eax, 80004005h
0x140039217  jmp     loc_1400394C7
0x14003921c  movsd   xmm0, [rsp+108h+var_60]
0x140039225  mov     eax, [rsp+108h+var_58]
0x14003922c  movsd   qword ptr [r14], xmm0
0x140039231  mov     [r14+8], eax
0x140039235  cmp     byte ptr [r14+0Ch], 0
0x14003923a  jnz     short loc_140039241
0x14003923c  mov     byte ptr [r14+0Ch], 1
0x140039241  mov     rdx, r14
0x140039244  lea     rcx, [rsp+108h+var_A8]
0x140039249  call    _anonymous_namespace___to_image_metadata
0x14003924e  movups  xmm0, xmmword ptr [rax]
0x140039251  movups  [rsp+108h+var_50], xmm0
0x140039259  movsd   xmm1, qword ptr [rax+10h]
0x14003925e  movsd   [rsp+108h+var_40], xmm1
0x140039267  lea     rax, off_140051050
0x14003926e  mov     [rsp+108h+var_B8], rax
0x140039273  mov     rax, [rdi+30h]
0x140039277  mov     [rsp+108h+var_B0], rax
0x14003927c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57180361@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57180361@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361> `wil::Feature<__WilFeatureTraits_Feature_57180361>::GetImpl(void)'::`2'::impl
0x140039283  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57180361@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361>::__private_IsEnabled(void)
0x140039288  test    al, al
0x14003928a  jz      short loc_140039295
0x14003928c  lea     rcx, [rdi+78h]
0x140039290  call    ?clear@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x140039295  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56182531@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56182531@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531> `wil::Feature<__WilFeatureTraits_Feature_56182531>::GetImpl(void)'::`2'::impl
0x14003929c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56182531@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531>::__private_IsEnabled(void)
0x1400392a1  test    al, al
0x1400392a3  jz      loc_140039389
0x1400392a9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_48532826@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_48532826@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_48532826> `wil::Feature<__WilFeatureTraits_Feature_48532826>::GetImpl(void)'::`2'::impl
0x1400392b0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_48532826@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_48532826>::__private_IsEnabled(void)
0x1400392b5  lea     rdx, [rdi+78h]
0x1400392b9  mov     rcx, [rdi+0C0h]
0x1400392c0  mov     [rsp+108h+var_E0], rdx
0x1400392c5  lea     r9, [rsp+108h+var_B8]
0x1400392ca  lea     r8, [rsp+108h+var_50]
0x1400392d2  mov     [rsp+108h+var_E8], rbx
0x1400392d7  lea     rdx, [rsp+108h+var_A8]
0x1400392dc  test    al, al
0x1400392de  mov     rax, [rcx]
0x1400392e1  mov     rax, [rax+8]
0x1400392e5  jz      short loc_14003933B
0x1400392e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400392ec  mov     rdx, rax
0x1400392ef  mov     rcx, r12
0x1400392f2  call    ??4embedding@@QEAAAEAU0@$$QEAU0@@Z; embedding::operator=(embedding &&)
0x1400392f7  lea     rcx, [rsp+108h+var_A8]
0x1400392fc  call    ?_Destroy@?$_Variant_base@V?$vector@MV?$allocator@M@std@@@std@@V?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@2@@std@@QEAAXXZ; std::_Variant_base<std::vector<float>,std::vector<gsl::byte>>::_Destroy(void)
0x140039301  cmp     qword ptr [rbx+18h], 7
0x140039306  jbe     short loc_14003930B
0x140039308  mov     rbx, [rbx]
0x14003930b  mov     r9, rbx; wchar_t *
0x14003930e  lea     r8, aExtactedOcrTex; "Extacted OCR Text: m_ocrText: %s"
0x140039315  mov     edx, 0FCh; wchar_t *
0x14003931a  lea     rcx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\search\\com"...
0x140039321  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x140039326  mov     eax, [rdi+68h]
0x140039329  mov     [rdi+0D4h], eax
0x14003932f  mov     dword ptr [rdi+0D0h], 0
0x140039339  jmp     short loc_14003936C
0x14003933b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039340  mov     rdx, rax
0x140039343  mov     rcx, r12
0x140039346  call    ??4embedding@@QEAAAEAU0@$$QEAU0@@Z; embedding::operator=(embedding &&)
0x14003934b  lea     rcx, [rsp+108h+var_A8]
0x140039350  call    ?_Destroy@?$_Variant_base@V?$vector@MV?$allocator@M@std@@@std@@V?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@2@@std@@QEAAXXZ; std::_Variant_base<std::vector<float>,std::vector<gsl::byte>>::_Destroy(void)
0x140039355  mov     qword ptr [rbx+10h], 0
0x14003935d  cmp     qword ptr [rbx+18h], 7
0x140039362  jbe     short loc_140039367
0x140039364  mov     rbx, [rbx]
0x140039367  xor     eax, eax
0x140039369  mov     [rbx], ax
0x14003936c  lea     r8, aImageEmbedding; "Image embedding generated in PixelSeman"...
0x140039373  mov     edx, 105h; wchar_t *
0x140039378  lea     rcx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\search\\com"...
0x14003937f  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x140039384  jmp     loc_140039465
0x140039389  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_48532826@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_48532826@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_48532826> `wil::Feature<__WilFeatureTraits_Feature_48532826>::GetImpl(void)'::`2'::impl
0x140039390  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_48532826@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_48532826>::__private_IsEnabled(void)
0x140039395  lea     rdx, [rdi+78h]
0x140039399  mov     rcx, [rdi+0C0h]
0x1400393a0  mov     [rsp+108h+var_E0], rdx
0x1400393a5  lea     r9, [rsp+108h+var_B8]
0x1400393aa  lea     r8, [rsp+108h+var_50]
0x1400393b2  mov     [rsp+108h+var_E8], rbx
0x1400393b7  lea     rdx, [rsp+108h+var_A8]
0x1400393bc  test    al, al
0x1400393be  mov     rax, [rcx]
0x1400393c1  mov     rax, [rax+8]
0x1400393c5  jz      short loc_14003941B
0x1400393c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400393cc  mov     rdx, rax
0x1400393cf  mov     rcx, r12
0x1400393d2  call    ??4embedding@@QEAAAEAU0@$$QEAU0@@Z; embedding::operator=(embedding &&)
0x1400393d7  lea     rcx, [rsp+108h+var_A8]
0x1400393dc  call    ?_Destroy@?$_Variant_base@V?$vector@MV?$allocator@M@std@@@std@@V?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@2@@std@@QEAAXXZ; std::_Variant_base<std::vector<float>,std::vector<gsl::byte>>::_Destroy(void)
0x1400393e1  cmp     qword ptr [rbx+18h], 7
0x1400393e6  jbe     short loc_1400393EB
0x1400393e8  mov     rbx, [rbx]
0x1400393eb  mov     r9, rbx; wchar_t *
0x1400393ee  lea     r8, aExtactedOcrTex; "Extacted OCR Text: m_ocrText: %s"
0x1400393f5  mov     edx, 10Eh; wchar_t *
0x1400393fa  lea     rcx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\search\\com"...
0x140039401  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x140039406  mov     eax, [rdi+68h]
0x140039409  mov     [rdi+0D4h], eax
0x14003940f  mov     dword ptr [rdi+0D0h], 0
0x140039419  jmp     short loc_14003944C
0x14003941b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039420  mov     rdx, rax
0x140039423  mov     rcx, r12
0x140039426  call    ??4embedding@@QEAAAEAU0@$$QEAU0@@Z; embedding::operator=(embedding &&)
0x14003942b  lea     rcx, [rsp+108h+var_A8]
0x140039430  call    ?_Destroy@?$_Variant_base@V?$vector@MV?$allocator@M@std@@@std@@V?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@2@@std@@QEAAXXZ; std::_Variant_base<std::vector<float>,std::vector<gsl::byte>>::_Destroy(void)
0x140039435  mov     qword ptr [rbx+10h], 0
0x14003943d  cmp     qword ptr [rbx+18h], 7
0x140039442  jbe     short loc_140039447
0x140039444  mov     rbx, [rbx]
0x140039447  xor     eax, eax
0x140039449  mov     [rbx], ax
0x14003944c  lea     r8, aImageEmbedding; "Image embedding generated in PixelSeman"...
0x140039453  mov     edx, 117h; wchar_t *
0x140039458  lea     rcx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\search\\com"...
0x14003945f  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x140039464  nop
0x140039465  mov     rcx, r12; this
0x140039468  call    ?empty@embedding@@QEBA_NXZ; embedding::empty(void)
0x14003946d  test    al, al
0x14003946f  jz      short loc_140039488
0x140039471  mov     dword ptr [rsi], 0
0x140039477  lea     rcx, [rsp+108h+pv]
0x14003947c  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>(void)
0x140039481  mov     eax, 80004005h
0x140039486  jmp     short loc_1400394C7
0x140039488  mov     eax, 2
0x14003948d  mov     [rsi], eax
0x14003948f  mov     [rdi+50h], eax
0x140039492  lea     rcx, [rsp+108h+pv]
0x140039497  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>(void)
0x14003949c  jmp     short loc_1400394BF
0x14003949e  lea     rcx, [rsp+108h+pv]
0x1400394a3  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>(void)
0x1400394a8  mov     eax, [rsp+108h+var_C0]
0x1400394ac  jmp     short loc_1400394C7
0x1400394ae  lea     rcx, [rsp+108h+pv]
0x1400394b3  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>,wil::err_returncode_policy>(void)
0x1400394b8  mov     eax, 80041226h
0x1400394bd  jmp     short loc_1400394C7
0x1400394bf  xor     eax, eax
0x1400394c1  jmp     short loc_1400394C7
0x1400394c3  mov     eax, [rsp+108h+var_C0]
0x1400394c7  mov     rcx, [rsp+108h+var_38]
0x1400394cf  xor     rcx, rsp; StackCookie
  ... truncated ...
```
