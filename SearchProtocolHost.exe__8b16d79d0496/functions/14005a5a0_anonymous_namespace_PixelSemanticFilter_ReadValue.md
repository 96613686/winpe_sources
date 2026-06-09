# _anonymous_namespace_::PixelSemanticFilter::ReadValue

- ea: `0x14005a5a0`
- end: `0x14005a8cf`
- name: `_anonymous_namespace_::PixelSemanticFilter::ReadValue`
- size: `815`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x14000a108`
- `0x14000f22c`
- `0x140047e48`
- `0x1400580a8`
- `0x1400580e0`
- `0x1400581fc`
- `0x14005a5a0`
- `0x14005ae2c`
- `0x14005af20`
- `0x14005afcc`
- `0x140070010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14005a6ba`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14005a6ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005a61b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005a68c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005a771`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005a61b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005a68c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005a771`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall anonymous_namespace_::PixelSemanticFilter::ReadValue(_QWORD *a1, _QWORD *a2)
{
  __int64 result; // rax
  _QWORD *v5; // rsi
  __int64 v6; // rdi
  __int64 v7; // rdi
  _QWORD *v8; // r13
  unsigned int i; // r14d
  __int64 v10; // r12
  LPVOID v11; // rax
  LPVOID v12; // rbx
  _QWORD *v13; // r8
  _DWORD *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  _DWORD *v17; // rcx
  __int64 v18; // r9
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // [rsp+20h] [rbp-58h]
  __int128 v22; // [rsp+30h] [rbp-48h] BYREF
  __int64 v23; // [rsp+40h] [rbp-38h]
  void *retaddr; // [rsp+78h] [rbp+0h]
  _QWORD *v25; // [rsp+90h] [rbp+18h] BYREF
  unsigned __int64 v26; // [rsp+98h] [rbp+20h] BYREF

  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531>::__private_IsEnabled() || a2 )
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57180361>::GetImpl'::`2'::impl)
        || (v5 = a1 + 13, v6 = a1[14], a1[13] == v6) )
      {
        v20 = a1[7];
        if ( v20 )
          result = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v20 + 48LL))(v20, a2);
        else
          result = 2147500033LL;
      }
      else
      {
        v7 = (v6 - *v5) >> 5;
        v8 = CoTaskMemAlloc(8LL * (unsigned int)v7);
        v25 = v8;
        if ( v8 )
        {
          v22 = 0;
          v23 = 0;
          v26 = (unsigned int)v7;
          if ( (_DWORD)v7 )
            std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::_Reallocate<0>(
              &v22,
              &v26);
          for ( i = 0; i < (unsigned int)v7; ++i )
          {
            v10 = 32LL * i;
            v21 = *(_QWORD *)(v10 + *v5 + 16) + 1LL;
            v11 = CoTaskMemAlloc(2 * v21);
            v12 = v11;
            v26 = (unsigned __int64)v11;
            if ( !v11 )
            {
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v26);
              if ( (_QWORD)v22 )
              {
                std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>>(
                  v22,
                  *((_QWORD *)&v22 + 1));
                std::_Deallocate<16>(v22, (v23 - v22) & 0xFFFFFFFFFFFFFFF8uLL);
                v22 = 0;
                v23 = 0;
              }
LABEL_21:
              wistd::unique_ptr<wchar_t *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&v25);
              return 2147942414LL;
            }
            v13 = (_QWORD *)(v10 + *v5);
            if ( v13[3] > 7u )
              v13 = (_QWORD *)*v13;
            _o_wcscpy_s(v11, v21, v13);
            if ( *((_QWORD *)&v22 + 1) == v23 )
            {
              std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
                &v22,
                *((_QWORD *)&v22 + 1),
                &v26);
            }
            else
            {
              **((_QWORD **)&v22 + 1) = v12;
              v26 = 0;
              *((_QWORD *)&v22 + 1) += 8LL;
            }
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v26);
          }
          v14 = CoTaskMemAlloc(0x18u);
          v17 = v14;
          if ( !v14 )
          {
            if ( (_QWORD)v22 )
            {
              std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>>(
                v22,
                *((_QWORD *)&v22 + 1));
              std::_Deallocate<16>(v22, (v23 - v22) & 0xFFFFFFFFFFFFFFF8uLL);
              v22 = 0;
              v23 = 0;
            }
            goto LABEL_21;
          }
          *(_OWORD *)v14 = 0;
          *(_WORD *)v14 = 4127;
          v14[2] = v7;
          *((_QWORD *)v14 + 2) = v8;
          v18 = 0;
          if ( (_DWORD)v7 )
          {
            v16 = 0;
            do
            {
              v15 = v22;
              v19 = *(_QWORD *)(v22 + 8 * v16);
              *(_QWORD *)(v22 + 8 * v16) = 0;
              v8[v16] = v19;
              v18 = (unsigned int)(v18 + 1);
              ++v16;
            }
            while ( (unsigned int)v18 < (unsigned int)v7 );
          }
          *a2 = v17;
          v25 = 0;
          std::vector<std::wstring>::clear(v5, v15, v16, v18);
          if ( (_QWORD)v22 )
          {
            std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>>(
              v22,
              *((_QWORD *)&v22 + 1));
            std::_Deallocate<16>(v22, (v23 - v22) & 0xFFFFFFFFFFFFFFF8uLL);
            v22 = 0;
            v23 = 0;
          }
          wistd::unique_ptr<wchar_t *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&v25);
          result = 0;
        }
        else
        {
          wistd::unique_ptr<wchar_t *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&v25);
          result = 2147942414LL;
        }
      }
    }
    else
    {
      result = 2147500035LL;
    }
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      624,
      "onecoreuap\\base\\appmodel\\search\\common\\filterpipeline\\pixelsemanticfilter.cpp");
  }
  return result;
}

```

## disassembly

```asm
0x14005a5a0  mov     rax, rsp
0x14005a5a3  push    rdi
0x14005a5a4  push    r12
0x14005a5a6  push    r13
0x14005a5a8  push    r14
0x14005a5aa  push    r15
0x14005a5ac  sub     rsp, 50h
0x14005a5b0  mov     qword ptr [rax-50h], 0FFFFFFFFFFFFFFFEh
0x14005a5b8  mov     [rax+8], rbx
0x14005a5bc  mov     [rax+10h], rsi
0x14005a5c0  mov     r15, rdx
0x14005a5c3  mov     rbx, rcx
0x14005a5c6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56182531@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56182531@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531> `wil::Feature<__WilFeatureTraits_Feature_56182531>::GetImpl(void)'::`2'::impl
0x14005a5cd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56182531@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531>::__private_IsEnabled(void)
0x14005a5d2  test    al, al
0x14005a5d4  jnz     short loc_14005A5E5
0x14005a5d6  test    r15, r15
0x14005a5d9  jnz     short loc_14005A5E5
0x14005a5db  mov     eax, 80004003h
0x14005a5e0  jmp     loc_14005A8B4
0x14005a5e5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57180361@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57180361@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361> `wil::Feature<__WilFeatureTraits_Feature_57180361>::GetImpl(void)'::`2'::impl
0x14005a5ec  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57180361@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361>::__private_IsEnabled(void)
0x14005a5f1  test    al, al
0x14005a5f3  jz      loc_14005A88C
0x14005a5f9  lea     rsi, [rbx+68h]
0x14005a5fd  mov     rdi, [rsi+8]
0x14005a601  cmp     [rsi], rdi
0x14005a604  jz      loc_14005A88C
0x14005a60a  sub     rdi, [rsi]
0x14005a60d  sar     rdi, 5
0x14005a611  mov     ebx, edi
0x14005a613  lea     rcx, ds:0[rbx*8]; cb
0x14005a61b  call    cs:__imp_CoTaskMemAlloc
0x14005a621  mov     r13, rax
0x14005a624  mov     [rsp+78h+arg_10], rax
0x14005a62c  test    rax, rax
0x14005a62f  jz      loc_14005A878
0x14005a635  xorps   xmm0, xmm0
0x14005a638  movdqu  [rsp+78h+var_48], xmm0
0x14005a63e  mov     [rsp+78h+var_38], 0
0x14005a647  mov     [rsp+78h+arg_18], rbx
0x14005a64f  test    edi, edi
0x14005a651  jz      short loc_14005A665
0x14005a653  lea     rdx, [rsp+78h+arg_18]
0x14005a65b  lea     rcx, [rsp+78h+var_48]
0x14005a660  call    ??$_Reallocate@$0A@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAXAEA_K@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::_Reallocate<0>(unsigned __int64 &)
0x14005a665  xor     r14d, r14d
0x14005a668  cmp     r14d, edi
0x14005a66b  jnb     loc_14005A76C
0x14005a671  mov     r12d, r14d
0x14005a674  shl     r12, 5
0x14005a678  mov     rax, [rsi]
0x14005a67b  mov     rax, [r12+rax+10h]
0x14005a680  inc     rax
0x14005a683  mov     [rsp+78h+var_58], rax
0x14005a688  lea     rcx, [rax+rax]; cb
0x14005a68c  call    cs:__imp_CoTaskMemAlloc
0x14005a692  mov     rbx, rax
0x14005a695  mov     [rsp+78h+arg_18], rax
0x14005a69d  test    rax, rax
0x14005a6a0  jz      short loc_14005A70B
0x14005a6a2  mov     r8, [rsi]
0x14005a6a5  add     r8, r12
0x14005a6a8  cmp     qword ptr [r8+18h], 7
0x14005a6ad  jbe     short loc_14005A6B2
0x14005a6af  mov     r8, [r8]
0x14005a6b2  mov     rdx, [rsp+78h+var_58]
0x14005a6b7  mov     rcx, rbx
0x14005a6ba  call    cs:__imp__o_wcscpy_s
0x14005a6c0  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x14005a6c5  cmp     rdx, [rsp+78h+var_38]
0x14005a6ca  jz      short loc_14005A6E3
0x14005a6cc  mov     [rdx], rbx
0x14005a6cf  mov     [rsp+78h+arg_18], 0
0x14005a6db  add     qword ptr [rsp+78h+var_48+8], 8
0x14005a6e1  jmp     short loc_14005A6F6
0x14005a6e3  lea     r8, [rsp+78h+arg_18]
0x14005a6eb  lea     rcx, [rsp+78h+var_48]
0x14005a6f0  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x14005a6f5  nop
0x14005a6f6  lea     rcx, [rsp+78h+arg_18]
0x14005a6fe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14005a703  inc     r14d
0x14005a706  jmp     loc_14005A668
0x14005a70b  lea     rcx, [rsp+78h+arg_18]
0x14005a713  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14005a718  nop
0x14005a719  mov     rcx, qword ptr [rsp+78h+var_48]
0x14005a71e  test    rcx, rcx
0x14005a721  jz      short loc_14005A755
0x14005a723  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x14005a728  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>> &)
0x14005a72d  mov     rcx, qword ptr [rsp+78h+var_48]
0x14005a732  mov     rdx, [rsp+78h+var_38]
0x14005a737  sub     rdx, rcx
0x14005a73a  and     rdx, 0FFFFFFFFFFFFFFF8h
0x14005a73e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14005a743  xorps   xmm0, xmm0
0x14005a746  movdqu  [rsp+78h+var_48], xmm0
0x14005a74c  mov     [rsp+78h+var_38], 0
0x14005a755  lea     rcx, [rsp+78h+arg_10]
0x14005a75d  call    ?reset@?$unique_ptr@PEA_WU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAPEA_W@Z; wistd::unique_ptr<wchar_t *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(wchar_t * *)
0x14005a762  mov     eax, 8007000Eh
0x14005a767  jmp     loc_14005A8B4
0x14005a76c  mov     ecx, 18h; cb
0x14005a771  call    cs:__imp_CoTaskMemAlloc
0x14005a777  mov     rcx, rax
0x14005a77a  test    rax, rax
0x14005a77d  jz      loc_14005A828
0x14005a783  xorps   xmm0, xmm0
0x14005a786  movups  xmmword ptr [rax], xmm0
0x14005a789  mov     word ptr [rax], 101Fh
0x14005a78e  mov     [rax+8], edi
0x14005a791  mov     [rax+10h], r13
0x14005a795  xor     r9d, r9d
0x14005a798  test    edi, edi
0x14005a79a  jz      short loc_14005A7C0
0x14005a79c  xor     r8d, r8d
0x14005a79f  mov     rdx, qword ptr [rsp+78h+var_48]
0x14005a7a4  mov     rax, [rdx+r8*8]
0x14005a7a8  mov     qword ptr [rdx+r8*8], 0
0x14005a7b0  mov     [r13+r8*8+0], rax
0x14005a7b5  inc     r9d
0x14005a7b8  inc     r8
0x14005a7bb  cmp     r9d, edi
0x14005a7be  jb      short loc_14005A79F
0x14005a7c0  mov     [r15], rcx
0x14005a7c3  mov     [rsp+78h+arg_10], 0
0x14005a7cf  mov     rcx, rsi
0x14005a7d2  call    ?clear@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x14005a7d7  nop
0x14005a7d8  mov     rcx, qword ptr [rsp+78h+var_48]
0x14005a7dd  test    rcx, rcx
0x14005a7e0  jz      short loc_14005A814
0x14005a7e2  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x14005a7e7  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>> &)
0x14005a7ec  mov     rcx, qword ptr [rsp+78h+var_48]
0x14005a7f1  mov     rdx, [rsp+78h+var_38]
0x14005a7f6  sub     rdx, rcx
0x14005a7f9  and     rdx, 0FFFFFFFFFFFFFFF8h
0x14005a7fd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14005a802  xorps   xmm0, xmm0
0x14005a805  movdqu  [rsp+78h+var_48], xmm0
0x14005a80b  mov     [rsp+78h+var_38], 0
0x14005a814  lea     rcx, [rsp+78h+arg_10]
0x14005a81c  call    ?reset@?$unique_ptr@PEA_WU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAPEA_W@Z; wistd::unique_ptr<wchar_t *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(wchar_t * *)
0x14005a821  xor     eax, eax
0x14005a823  jmp     loc_14005A8B4
0x14005a828  mov     rcx, qword ptr [rsp+78h+var_48]
0x14005a82d  test    rcx, rcx
0x14005a830  jz      short loc_14005A864
0x14005a832  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x14005a837  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>> &)
0x14005a83c  mov     rcx, qword ptr [rsp+78h+var_48]
0x14005a841  mov     rdx, [rsp+78h+var_38]
0x14005a846  sub     rdx, rcx
0x14005a849  and     rdx, 0FFFFFFFFFFFFFFF8h
0x14005a84d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14005a852  xorps   xmm0, xmm0
0x14005a855  movdqu  [rsp+78h+var_48], xmm0
0x14005a85b  mov     [rsp+78h+var_38], 0
0x14005a864  lea     rcx, [rsp+78h+arg_10]
0x14005a86c  call    ?reset@?$unique_ptr@PEA_WU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAPEA_W@Z; wistd::unique_ptr<wchar_t *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(wchar_t * *)
0x14005a871  mov     eax, 8007000Eh
0x14005a876  jmp     short loc_14005A8B4
0x14005a878  lea     rcx, [rsp+78h+arg_10]
0x14005a880  call    ?reset@?$unique_ptr@PEA_WU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAPEA_W@Z; wistd::unique_ptr<wchar_t *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(wchar_t * *)
0x14005a885  mov     eax, 8007000Eh
0x14005a88a  jmp     short loc_14005A8B4
0x14005a88c  mov     rcx, [rbx+38h]
0x14005a890  test    rcx, rcx
0x14005a893  jz      short loc_14005A8A6
0x14005a895  mov     rax, [rcx]
0x14005a898  mov     rdx, r15
0x14005a89b  mov     rax, [rax+30h]
0x14005a89f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a8a4  jmp     short loc_14005A8B4
0x14005a8a6  mov     eax, 80004001h
0x14005a8ab  jmp     short loc_14005A8B4
0x14005a8ad  mov     eax, dword ptr [rsp+78h+arg_10]
0x14005a8b4  lea     r11, [rsp+78h+var_28]
0x14005a8b9  mov     rbx, [r11+30h]
0x14005a8bd  mov     rsi, [r11+38h]
0x14005a8c1  mov     rsp, r11
0x14005a8c4  pop     r15
0x14005a8c6  pop     r14
0x14005a8c8  pop     r13
0x14005a8ca  pop     r12
0x14005a8cc  pop     rdi
0x14005a8cd  retn
```
