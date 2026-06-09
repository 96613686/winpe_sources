# _RadioManager::_LoadRadioManagers_::_39_::_lambda_4_::operator()

- ea: `0x18001d4b4`
- end: `0x18001d795`
- name: `_RadioManager::_LoadRadioManagers_::_39_::_lambda_4_::operator()`
- size: `737`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180020d30`

## callees

- `0x180006200`
- `0x180006a0c`
- `0x18000760c`
- `0x18000a6a0`
- `0x18000b4f0`
- `0x18000b814`
- `0x18000c17c`
- `0x18000c2a4`
- `0x18000d2a0`
- `0x180019f3c`
- `0x18001a64c`
- `0x18001d4b4`
- `0x180021f9c`
- `0x180022b3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d4f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d4f2`

## string_xrefs

- `0x18001d6d2`: `Removed a MediaRadioManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
ULONG __fastcall RadioManager::_LoadRadioManagers_::_39_::_lambda_4_::operator()(const wchar_t *a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v3; // rax
  __int64 *v4; // rbx
  char IsEnabled; // al
  __int64 v6; // rcx
  __int64 *v7; // rsi
  __int64 *v8; // r14
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // rsi
  __int64 v14; // r14
  const wchar_t *v15; // rax
  __int64 v16; // r14
  __int64 *v17; // r15
  __int64 *i; // rsi
  __int64 *v19; // rsi
  __int64 *v20; // r14
  __int64 v21; // rcx
  const wchar_t *v22; // rax
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  const wchar_t **v28; // rax
  unsigned __int8 *v29; // rdx
  ULONG result; // eax
  wil *v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  const wchar_t **v35; // [rsp+30h] [rbp-78h]
  const char *v36; // [rsp+40h] [rbp-68h] BYREF
  const wchar_t *v37; // [rsp+48h] [rbp-60h] BYREF
  const wchar_t *v38; // [rsp+50h] [rbp-58h] BYREF
  __int64 v39; // [rsp+58h] [rbp-50h] BYREF
  const wchar_t *v40; // [rsp+60h] [rbp-48h] BYREF
  __int128 v41; // [rsp+68h] [rbp-40h] BYREF
  __int64 v42; // [rsp+78h] [rbp-30h]

  v40 = a1;
  v2 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)a1 + 2) + 240LL);
  EnterCriticalSection(v2);
  v39 = (__int64)v2;
  v3 = *((_QWORD *)a1 + 2);
  v4 = *(__int64 **)(v3 + 280);
  try
  {
    while ( 1 )
    {
      if ( v4 == *(__int64 **)(v3 + 288) )
      {
        if ( (unsigned int)dword_180037050 <= 4 )
          goto LABEL_36;
        v37 = (const wchar_t *)RmGuidToMediaTypeString((const struct _GUID *)a1);
        v36 = "MediaRadioManager was not found, not removing";
        v35 = &v37;
        v28 = (const wchar_t **)&v36;
        v29 = (unsigned __int8 *)byte_18002FE93;
        goto LABEL_35;
      }
      if ( *(_QWORD *)(*v4 + 8) == *(_QWORD *)a1 && *(_QWORD *)(*v4 + 16) == *((_QWORD *)a1 + 1) )
        break;
      ++v4;
    }
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_RadioManager_Fix_NullRadioInstance>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RadioManager_Fix_NullRadioInstance>::GetImpl'::`2'::impl);
    v6 = *((_QWORD *)a1 + 2);
    if ( IsEnabled )
    {
      v41 = 0;
      v42 = 0;
      v7 = *(__int64 **)(v6 + 304);
      v8 = *(__int64 **)(v6 + 312);
      v9 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      while ( v7 != v8 )
      {
        v10 = *v7;
        if ( *(_QWORD *)(*v7 + 72) == *(_QWORD *)a1 && *(_QWORD *)(v10 + 80) == *((_QWORD *)a1 + 1) )
        {
          v11 = v10 + 40;
          if ( v9 == v42 )
          {
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v41, v9, v11);
            v9 = *((_QWORD *)&v41 + 1);
          }
          else
          {
            std::wstring::wstring(v9, v10 + 40, v11);
            v9 = *((_QWORD *)&v41 + 1) + 32LL;
            *((_QWORD *)&v41 + 1) += 32LL;
          }
        }
        ++v7;
      }
      v12 = v41;
      v13 = v41;
      v14 = v9;
      while ( v13 != v14 )
      {
        v15 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v13);
        RadioManager::_RemoveInstance(*((struct _RTL_CRITICAL_SECTION **)a1 + 2), v15);
        v13 += 32;
        v9 = *((_QWORD *)&v41 + 1);
        v12 = v41;
      }
      if ( v12 )
      {
        std::_Destroy_range<std::allocator<std::wstring>>(v12, v9);
        std::_Deallocate<16>(v41, (v42 - v41) & 0xFFFFFFFFFFFFFFE0uLL);
      }
    }
    else
    {
      v19 = *(__int64 **)(v6 + 304);
      v20 = *(__int64 **)(v6 + 312);
      while ( v19 != v20 )
      {
        v21 = *v19;
        if ( *(_QWORD *)(*v19 + 72) == *(_QWORD *)a1 && *(_QWORD *)(v21 + 80) == *((_QWORD *)a1 + 1) )
        {
          v22 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v21 + 40);
          RadioManager::_RemoveInstance(*((struct _RTL_CRITICAL_SECTION **)a1 + 2), v22);
        }
        ++v19;
      }
    }
    v16 = *((_QWORD *)a1 + 2);
    v17 = *(__int64 **)(v16 + 288);
    for ( i = v4 + 1; i != v17; ++i )
    {
      v23 = *i;
      *i = 0;
      v24 = *v4;
      *v4 = v23;
      if ( v24 )
        std::default_delete<MEDIA_RADIO_MANAGER>::operator()();
      ++v4;
    }
    std::unique_ptr<MEDIA_RADIO_MANAGER>::~unique_ptr<MEDIA_RADIO_MANAGER>(*(_QWORD *)(v16 + 288) - 8LL);
    *(_QWORD *)(v16 + 288) -= 8LL;
    if ( (unsigned int)dword_180037050 > 4 )
    {
      v36 = RmGuidToMediaTypeString((const struct _GUID *)a1);
      v37 = (const wchar_t *)"Removed a MediaRadioManager";
      v35 = (const wchar_t **)&v36;
      v28 = &v37;
      v29 = (unsigned __int8 *)&unk_18002FEE8;
LABEL_35:
      v38 = a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
        v25,
        v29,
        v26,
        v27,
        v28,
        (__int64 *)&v38,
        v35);
    }
LABEL_36:
    result = wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v39);
  }
  catch ( ... )
  {
    result = dword_180037050;
    if ( (unsigned int)dword_180037050 > 2 )
    {
      LODWORD(v36) = wil::ResultFromCaughtException(v31);
      v40 = (const wchar_t *)RmGuidToMediaTypeString((const struct _GUID *)v40);
      v39 = v32;
      v37 = (const wchar_t *)"Exception removing a MediaRadioManager";
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
               v32,
               (unsigned __int8 *)byte_18002FE35,
               v33,
               v34,
               &v37,
               &v39,
               &v40,
               (__int64)&v36);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001d4b4  mov     [rsp+arg_8], rbx
0x18001d4b9  mov     [rsp+arg_10], rsi
0x18001d4be  push    rdi
0x18001d4bf  push    r14
0x18001d4c1  push    r15
0x18001d4c3  sub     rsp, 90h
0x18001d4ca  mov     rax, cs:__security_cookie
0x18001d4d1  xor     rax, rsp
0x18001d4d4  mov     [rsp+0A8h+var_28], rax
0x18001d4dc  mov     rdi, rcx
0x18001d4df  mov     [rsp+0A8h+var_48], rcx
0x18001d4e4  mov     rbx, [rcx+10h]
0x18001d4e8  add     rbx, 0F0h
0x18001d4ef  mov     rcx, rbx; lpCriticalSection
0x18001d4f2  call    cs:__imp_EnterCriticalSection
0x18001d4f8  mov     [rsp+0A8h+var_50], rbx
0x18001d4fd  mov     rax, [rdi+10h]
0x18001d501  mov     rbx, [rax+118h]
0x18001d508  mov     rdx, [rax+120h]
0x18001d50f  jmp     loc_18001D704
0x18001d514  mov     rcx, [rbx]
0x18001d517  mov     rax, [rcx+8]
0x18001d51b  cmp     rax, [rdi]
0x18001d51e  jnz     loc_18001D700
0x18001d524  mov     rax, [rcx+10h]
0x18001d528  cmp     rax, [rdi+8]
0x18001d52c  jnz     loc_18001D700
0x18001d532  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RadioManager_Fix_NullRadioInstance@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RadioManager_Fix_NullRadioInstance@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RadioManager_Fix_NullRadioInstance> `wil::Feature<__WilFeatureTraits_Feature_RadioManager_Fix_NullRadioInstance>::GetImpl(void)'::`2'::impl
0x18001d539  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_RadioManager_Fix_NullRadioInstance@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RadioManager_Fix_NullRadioInstance>::__private_IsEnabled(void)
0x18001d53e  mov     rcx, [rdi+10h]
0x18001d542  test    al, al
0x18001d544  jz      loc_18001D633
0x18001d54a  xor     eax, eax
0x18001d54c  xorps   xmm1, xmm1
0x18001d54f  movdqu  [rsp+0A8h+var_40], xmm1
0x18001d555  mov     [rsp+0A8h+var_30], rax
0x18001d55a  mov     rsi, [rcx+130h]
0x18001d561  mov     r14, [rcx+138h]
0x18001d568  psrldq  xmm1, 8
0x18001d56d  movq    rcx, xmm1
0x18001d572  cmp     rsi, r14
0x18001d575  jz      short loc_18001D5C8
0x18001d577  mov     rdx, [rsi]
0x18001d57a  mov     rax, [rdx+48h]
0x18001d57e  cmp     rax, [rdi]
0x18001d581  jnz     short loc_18001D5C2
0x18001d583  mov     rax, [rdx+50h]
0x18001d587  cmp     rax, [rdi+8]
0x18001d58b  jnz     short loc_18001D5C2
0x18001d58d  lea     r8, [rdx+28h]
0x18001d591  cmp     rcx, [rsp+0A8h+var_30]
0x18001d596  jz      short loc_18001D5B0
0x18001d598  mov     rdx, r8
0x18001d59b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d5a0  mov     rcx, qword ptr [rsp+0A8h+var_40+8]
0x18001d5a5  add     rcx, 20h ; ' '
0x18001d5a9  mov     qword ptr [rsp+0A8h+var_40+8], rcx
0x18001d5ae  jmp     short loc_18001D5C2
0x18001d5b0  mov     rdx, rcx
0x18001d5b3  lea     rcx, [rsp+0A8h+var_40]
0x18001d5b8  call    ??$_Emplace_reallocate@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18001d5bd  mov     rcx, qword ptr [rsp+0A8h+var_40+8]
0x18001d5c2  add     rsi, 8
0x18001d5c6  jmp     short loc_18001D572
0x18001d5c8  mov     rax, qword ptr [rsp+0A8h+var_40]
0x18001d5cd  mov     rsi, rax
0x18001d5d0  mov     r14, rcx
0x18001d5d3  cmp     rsi, r14
0x18001d5d6  jz      short loc_18001D5FC
0x18001d5d8  mov     rcx, rsi
0x18001d5db  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001d5e0  mov     rdx, rax; wchar_t *
0x18001d5e3  mov     rcx, [rdi+10h]; this
0x18001d5e7  call    ?_RemoveInstance@RadioManager@@AEAAXPEB_W@Z; RadioManager::_RemoveInstance(wchar_t const *)
0x18001d5ec  add     rsi, 20h ; ' '
0x18001d5f0  mov     rcx, qword ptr [rsp+0A8h+var_40+8]
0x18001d5f5  mov     rax, qword ptr [rsp+0A8h+var_40]
0x18001d5fa  jmp     short loc_18001D5D3
0x18001d5fc  test    rax, rax
0x18001d5ff  jz      short loc_18001D622
0x18001d601  mov     rdx, rcx
0x18001d604  mov     rcx, rax
0x18001d607  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18001d60c  mov     rcx, qword ptr [rsp+0A8h+var_40]
0x18001d611  mov     rdx, [rsp+0A8h+var_30]
0x18001d616  sub     rdx, rcx
0x18001d619  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18001d61d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001d622  mov     r14, [rdi+10h]
0x18001d626  mov     r15, [r14+120h]
0x18001d62d  lea     rsi, [rbx+8]
0x18001d631  jmp     short loc_18001D699
0x18001d633  mov     rsi, [rcx+130h]
0x18001d63a  mov     r14, [rcx+138h]
0x18001d641  cmp     rsi, r14
0x18001d644  jz      short loc_18001D622
0x18001d646  mov     rcx, [rsi]
0x18001d649  mov     rax, [rcx+48h]
0x18001d64d  cmp     rax, [rdi]
0x18001d650  jnz     short loc_18001D671
0x18001d652  mov     rax, [rcx+50h]
0x18001d656  cmp     rax, [rdi+8]
0x18001d65a  jnz     short loc_18001D671
0x18001d65c  add     rcx, 28h ; '('
0x18001d660  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001d665  mov     rdx, rax; wchar_t *
0x18001d668  mov     rcx, [rdi+10h]; this
0x18001d66c  call    ?_RemoveInstance@RadioManager@@AEAAXPEB_W@Z; RadioManager::_RemoveInstance(wchar_t const *)
0x18001d671  add     rsi, 8
0x18001d675  jmp     short loc_18001D641
0x18001d677  mov     rax, [rsi]
0x18001d67a  mov     qword ptr [rsi], 0
0x18001d681  mov     rdx, [rbx]
0x18001d684  mov     [rbx], rax
0x18001d687  test    rdx, rdx
0x18001d68a  jz      short loc_18001D691
0x18001d68c  call    ??R?$default_delete@UMEDIA_RADIO_MANAGER@@@std@@QEBAXPEAUMEDIA_RADIO_MANAGER@@@Z; std::default_delete<MEDIA_RADIO_MANAGER>::operator()(MEDIA_RADIO_MANAGER *)
0x18001d691  add     rbx, 8
0x18001d695  add     rsi, 8
0x18001d699  cmp     rsi, r15
0x18001d69c  jnz     short loc_18001D677
0x18001d69e  mov     rcx, [r14+120h]
0x18001d6a5  sub     rcx, 8
0x18001d6a9  call    ??1?$unique_ptr@UMEDIA_RADIO_MANAGER@@U?$default_delete@UMEDIA_RADIO_MANAGER@@@std@@@std@@QEAA@XZ; std::unique_ptr<MEDIA_RADIO_MANAGER>::~unique_ptr<MEDIA_RADIO_MANAGER>(void)
0x18001d6ae  add     qword ptr [r14+120h], 0FFFFFFFFFFFFFFF8h
0x18001d6b6  mov     eax, cs:dword_180037050
0x18001d6bc  cmp     eax, 4
0x18001d6bf  jbe     loc_18001D761
0x18001d6c5  mov     rcx, rdi; struct _GUID *
0x18001d6c8  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x18001d6cd  mov     [rsp+0A8h+var_68], rax
0x18001d6d2  lea     rax, aRemovedAMediar; "Removed a MediaRadioManager"
0x18001d6d9  mov     [rsp+0A8h+var_60], rax
0x18001d6de  lea     rax, [rsp+0A8h+var_68]
0x18001d6e3  mov     [rsp+0A8h+var_78], rax
0x18001d6e8  lea     rax, [rsp+0A8h+var_58]
0x18001d6ed  mov     [rsp+0A8h+var_80], rax
0x18001d6f2  lea     rax, [rsp+0A8h+var_60]
0x18001d6f7  lea     rdx, unk_18002FEE8
0x18001d6fe  jmp     short loc_18001D751
0x18001d700  add     rbx, 8
0x18001d704  cmp     rbx, rdx
0x18001d707  jnz     loc_18001D514
0x18001d70d  mov     eax, cs:dword_180037050
0x18001d713  cmp     eax, 4
0x18001d716  jbe     short loc_18001D761
0x18001d718  mov     rcx, rdi; struct _GUID *
0x18001d71b  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x18001d720  mov     [rsp+0A8h+var_60], rax
0x18001d725  lea     rax, aMediaradiomana; "MediaRadioManager was not found, not re"...
0x18001d72c  mov     [rsp+0A8h+var_68], rax
0x18001d731  lea     rax, [rsp+0A8h+var_60]
0x18001d736  mov     [rsp+0A8h+var_78], rax
0x18001d73b  lea     rax, [rsp+0A8h+var_58]
0x18001d740  mov     [rsp+0A8h+var_80], rax
0x18001d745  lea     rax, [rsp+0A8h+var_68]
0x18001d74a  lea     rdx, byte_18002FE93
0x18001d751  mov     [rsp+0A8h+var_88], rax
0x18001d756  mov     [rsp+0A8h+var_58], rdi
0x18001d75b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x18001d760  nop
0x18001d761  lea     rcx, [rsp+0A8h+var_50]
0x18001d766  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001d76b  nop
0x18001d76c  mov     rcx, [rsp+0A8h+var_28]
0x18001d774  xor     rcx, rsp; StackCookie
0x18001d777  call    __security_check_cookie
0x18001d77c  lea     r11, [rsp+0A8h+var_18]
0x18001d784  mov     rbx, [r11+28h]
0x18001d788  mov     rsi, [r11+30h]
0x18001d78c  mov     rsp, r11
0x18001d78f  pop     r15
0x18001d791  pop     r14
0x18001d793  pop     rdi
0x18001d794  retn
```
