# _anonymous_namespace_::PixelSemanticFilter::ReadValue

- ea: `0x140039ab0`
- end: `0x140039da9`
- name: `_anonymous_namespace_::PixelSemanticFilter::ReadValue`
- size: `761`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140005e88`
- `0x14000e19c`
- `0x1400155e0`
- `0x14003780c`
- `0x140037844`
- `0x140037960`
- `0x140039ab0`
- `0x14003a2f0`
- `0x14003a368`
- `0x14004f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140039bcd`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140039bcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140039c70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140039d52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140039c70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140039d52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140039b2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140039b9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140039c85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140039b2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140039b9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140039c85`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall anonymous_namespace_::PixelSemanticFilter::ReadValue(_QWORD *a1, _QWORD *a2)
{
  __int64 result; // rax
  _QWORD *v5; // r14
  __int64 v6; // rdi
  __int64 v7; // rdi
  void *v8; // rsi
  unsigned int i; // r15d
  __int64 v10; // r13
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
  __int128 v21; // [rsp+30h] [rbp-48h] BYREF
  __int64 v22; // [rsp+40h] [rbp-38h]
  unsigned __int64 v23; // [rsp+90h] [rbp+18h] BYREF
  __int64 v24; // [rsp+98h] [rbp+20h]

  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56182531>::GetImpl'::`2'::impl)
      || a2 )
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
        if ( v8 )
        {
          v21 = 0;
          v22 = 0;
          v23 = (unsigned int)v7;
          if ( (_DWORD)v7 )
            std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::_Reallocate<0>(
              &v21,
              &v23);
          for ( i = 0; i < (unsigned int)v7; ++i )
          {
            v10 = 32LL * i;
            v24 = *(_QWORD *)(*v5 + v10 + 16) + 1LL;
            v11 = CoTaskMemAlloc(2 * v24);
            v12 = v11;
            v23 = (unsigned __int64)v11;
            if ( !v11 )
            {
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&v23);
              if ( (_QWORD)v21 )
              {
                std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>>(
                  v21,
                  *((__int64 *)&v21 + 1));
                std::_Deallocate<16>((void *)v21, (v22 - v21) & 0xFFFFFFFFFFFFFFF8uLL);
                v21 = 0;
                v22 = 0;
              }
LABEL_21:
              CoTaskMemFree(v8);
              return 2147942414LL;
            }
            v13 = (_QWORD *)(v10 + *v5);
            if ( v13[3] > 7u )
              v13 = (_QWORD *)*v13;
            _o_wcscpy_s(v11, v24, v13);
            if ( *((_QWORD *)&v21 + 1) == v22 )
            {
              std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
                &v21,
                *((__int64 *)&v21 + 1),
                (__int64 *)&v23);
            }
            else
            {
              **((_QWORD **)&v21 + 1) = v12;
              v23 = 0;
              *((_QWORD *)&v21 + 1) += 8LL;
            }
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&v23);
          }
          v14 = CoTaskMemAlloc(0x18u);
          v17 = v14;
          if ( !v14 )
          {
            if ( (_QWORD)v21 )
            {
              std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>>(
                v21,
                *((__int64 *)&v21 + 1));
              std::_Deallocate<16>((void *)v21, (v22 - v21) & 0xFFFFFFFFFFFFFFF8uLL);
              v21 = 0;
              v22 = 0;
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
              v15 = v21;
              v19 = *(_QWORD *)(v21 + 8 * v16);
              *(_QWORD *)(v21 + 8 * v16) = 0;
              *((_QWORD *)v8 + v16) = v19;
              v18 = (unsigned int)(v18 + 1);
              ++v16;
            }
            while ( (unsigned int)v18 < (unsigned int)v7 );
          }
          *a2 = v17;
          std::vector<std::wstring>::clear(v5, v15, v16, v18, -2, v8);
          if ( (_QWORD)v21 )
          {
            std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>>(
              v21,
              *((__int64 *)&v21 + 1));
            std::_Deallocate<16>((void *)v21, (v22 - v21) & 0xFFFFFFFFFFFFFFF8uLL);
          }
          result = 0;
        }
        else
        {
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
    indexer::result::details::result_from_caught_exception<1>();
  }
  return result;
}

```

## disassembly

```asm
0x140039ab0  mov     rax, rsp
0x140039ab3  push    rdi
0x140039ab4  push    r12
0x140039ab6  push    r13
0x140039ab8  push    r14
0x140039aba  push    r15
0x140039abc  sub     rsp, 50h
0x140039ac0  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x140039ac8  mov     [rax+8], rbx
0x140039acc  mov     [rax+10h], rsi
0x140039ad0  mov     r12, rdx
0x140039ad3  mov     rbx, rcx
0x140039ad6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56182531@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56182531@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531> `wil::Feature<__WilFeatureTraits_Feature_56182531>::GetImpl(void)'::`2'::impl
0x140039add  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56182531@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531>::__private_IsEnabled(void)
0x140039ae2  test    al, al
0x140039ae4  jnz     short loc_140039AF5
0x140039ae6  test    r12, r12
0x140039ae9  jnz     short loc_140039AF5
0x140039aeb  mov     eax, 80004003h
0x140039af0  jmp     loc_140039D8E
0x140039af5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57180361@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57180361@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361> `wil::Feature<__WilFeatureTraits_Feature_57180361>::GetImpl(void)'::`2'::impl
0x140039afc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57180361@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361>::__private_IsEnabled(void)
0x140039b01  test    al, al
0x140039b03  jz      loc_140039D66
0x140039b09  lea     r14, [rbx+68h]
0x140039b0d  mov     rdi, [r14+8]
0x140039b11  cmp     [r14], rdi
0x140039b14  jz      loc_140039D66
0x140039b1a  sub     rdi, [r14]
0x140039b1d  sar     rdi, 5
0x140039b21  mov     ebx, edi
0x140039b23  lea     rcx, ds:0[rbx*8]; cb
0x140039b2b  call    cs:__imp_CoTaskMemAlloc
0x140039b31  mov     rsi, rax
0x140039b34  mov     [rsp+78h+var_50], rax
0x140039b39  test    rax, rax
0x140039b3c  jz      loc_140039D5F
0x140039b42  xorps   xmm0, xmm0
0x140039b45  movdqu  [rsp+78h+var_48], xmm0
0x140039b4b  mov     [rsp+78h+var_38], 0
0x140039b54  mov     [rsp+78h+arg_10], rbx
0x140039b5c  test    edi, edi
0x140039b5e  jz      short loc_140039B72
0x140039b60  lea     rdx, [rsp+78h+arg_10]
0x140039b68  lea     rcx, [rsp+78h+var_48]
0x140039b6d  call    ??$_Reallocate@$0A@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAXAEA_K@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::_Reallocate<0>(unsigned __int64 &)
0x140039b72  xor     r15d, r15d
0x140039b75  cmp     r15d, edi
0x140039b78  jnb     loc_140039C80
0x140039b7e  mov     r13d, r15d
0x140039b81  shl     r13, 5
0x140039b85  mov     rax, [r14]
0x140039b88  mov     rax, [rax+r13+10h]
0x140039b8d  inc     rax
0x140039b90  mov     [rsp+78h+arg_18], rax
0x140039b98  lea     rcx, [rax+rax]; cb
0x140039b9c  call    cs:__imp_CoTaskMemAlloc
0x140039ba2  mov     rbx, rax
0x140039ba5  mov     [rsp+78h+arg_10], rax
0x140039bad  test    rax, rax
0x140039bb0  jz      short loc_140039C1E
0x140039bb2  mov     r8, [r14]
0x140039bb5  add     r8, r13
0x140039bb8  cmp     qword ptr [r8+18h], 7
0x140039bbd  jbe     short loc_140039BC2
0x140039bbf  mov     r8, [r8]
0x140039bc2  mov     rdx, [rsp+78h+arg_18]
0x140039bca  mov     rcx, rbx
0x140039bcd  call    cs:__imp__o_wcscpy_s
0x140039bd3  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x140039bd8  cmp     rdx, [rsp+78h+var_38]
0x140039bdd  jz      short loc_140039BF6
0x140039bdf  mov     [rdx], rbx
0x140039be2  mov     [rsp+78h+arg_10], 0
0x140039bee  add     qword ptr [rsp+78h+var_48+8], 8
0x140039bf4  jmp     short loc_140039C09
0x140039bf6  lea     r8, [rsp+78h+arg_10]
0x140039bfe  lea     rcx, [rsp+78h+var_48]
0x140039c03  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x140039c08  nop
0x140039c09  lea     rcx, [rsp+78h+arg_10]
0x140039c11  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140039c16  inc     r15d
0x140039c19  jmp     loc_140039B75
0x140039c1e  lea     rcx, [rsp+78h+arg_10]
0x140039c26  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140039c2b  nop
0x140039c2c  mov     rcx, qword ptr [rsp+78h+var_48]
0x140039c31  test    rcx, rcx
0x140039c34  jz      short loc_140039C68
0x140039c36  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x140039c3b  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>> &)
0x140039c40  mov     rcx, qword ptr [rsp+78h+var_48]
0x140039c45  mov     rdx, [rsp+78h+var_38]
0x140039c4a  sub     rdx, rcx
0x140039c4d  and     rdx, 0FFFFFFFFFFFFFFF8h
0x140039c51  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140039c56  xorps   xmm0, xmm0
0x140039c59  movdqu  [rsp+78h+var_48], xmm0
0x140039c5f  mov     [rsp+78h+var_38], 0
0x140039c68  test    rsi, rsi
0x140039c6b  jz      short loc_140039C76
0x140039c6d  mov     rcx, rsi; pv
0x140039c70  call    cs:__imp_CoTaskMemFree
0x140039c76  mov     eax, 8007000Eh
0x140039c7b  jmp     loc_140039D8E
0x140039c80  mov     ecx, 18h; cb
0x140039c85  call    cs:__imp_CoTaskMemAlloc
0x140039c8b  mov     rcx, rax
0x140039c8e  test    rax, rax
0x140039c91  jz      short loc_140039D0E
0x140039c93  xorps   xmm0, xmm0
0x140039c96  movups  xmmword ptr [rax], xmm0
0x140039c99  mov     word ptr [rax], 101Fh
0x140039c9e  mov     [rax+8], edi
0x140039ca1  mov     [rax+10h], rsi
0x140039ca5  xor     r9d, r9d
0x140039ca8  test    edi, edi
0x140039caa  jz      short loc_140039CCF
0x140039cac  xor     r8d, r8d
0x140039caf  mov     rdx, qword ptr [rsp+78h+var_48]
0x140039cb4  mov     rax, [rdx+r8*8]
0x140039cb8  mov     qword ptr [rdx+r8*8], 0
0x140039cc0  mov     [rsi+r8*8], rax
0x140039cc4  inc     r9d
0x140039cc7  inc     r8
0x140039cca  cmp     r9d, edi
0x140039ccd  jb      short loc_140039CAF
0x140039ccf  mov     [r12], rcx
0x140039cd3  mov     rcx, r14
0x140039cd6  call    ?clear@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x140039cdb  nop
0x140039cdc  mov     rcx, qword ptr [rsp+78h+var_48]
0x140039ce1  test    rcx, rcx
0x140039ce4  jz      short loc_140039D07
0x140039ce6  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x140039ceb  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>> &)
0x140039cf0  mov     rcx, qword ptr [rsp+78h+var_48]
0x140039cf5  mov     rdx, [rsp+78h+var_38]
0x140039cfa  sub     rdx, rcx
0x140039cfd  and     rdx, 0FFFFFFFFFFFFFFF8h
0x140039d01  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140039d06  nop
0x140039d07  xor     eax, eax
0x140039d09  jmp     loc_140039D8E
0x140039d0e  mov     rcx, qword ptr [rsp+78h+var_48]
0x140039d13  test    rcx, rcx
0x140039d16  jz      short loc_140039D4A
0x140039d18  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x140039d1d  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>> &)
0x140039d22  mov     rcx, qword ptr [rsp+78h+var_48]
0x140039d27  mov     rdx, [rsp+78h+var_38]
0x140039d2c  sub     rdx, rcx
0x140039d2f  and     rdx, 0FFFFFFFFFFFFFFF8h
0x140039d33  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140039d38  xorps   xmm0, xmm0
0x140039d3b  movdqu  [rsp+78h+var_48], xmm0
0x140039d41  mov     [rsp+78h+var_38], 0
0x140039d4a  test    rsi, rsi
0x140039d4d  jz      short loc_140039D58
0x140039d4f  mov     rcx, rsi; pv
0x140039d52  call    cs:__imp_CoTaskMemFree
0x140039d58  mov     eax, 8007000Eh
0x140039d5d  jmp     short loc_140039D8E
0x140039d5f  mov     eax, 8007000Eh
0x140039d64  jmp     short loc_140039D8E
0x140039d66  mov     rcx, [rbx+38h]
0x140039d6a  test    rcx, rcx
0x140039d6d  jz      short loc_140039D80
0x140039d6f  mov     rax, [rcx]
0x140039d72  mov     rdx, r12
0x140039d75  mov     rax, [rax+30h]
0x140039d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039d7e  jmp     short loc_140039D8E
0x140039d80  mov     eax, 80004001h
0x140039d85  jmp     short loc_140039D8E
0x140039d87  mov     eax, dword ptr [rsp+78h+arg_10]
0x140039d8e  lea     r11, [rsp+78h+var_28]
0x140039d93  mov     rbx, [r11+30h]
0x140039d97  mov     rsi, [r11+38h]
0x140039d9b  mov     rsp, r11
0x140039d9e  pop     r15
0x140039da0  pop     r14
0x140039da2  pop     r13
0x140039da4  pop     r12
0x140039da6  pop     rdi
0x140039da7  retn
```
