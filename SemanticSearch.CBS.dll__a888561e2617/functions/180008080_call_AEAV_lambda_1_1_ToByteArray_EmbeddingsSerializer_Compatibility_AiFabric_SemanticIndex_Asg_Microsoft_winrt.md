# ??$call@AEAV_lambda_1_@?1??ToByteArray@EmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUEmbedding@456789@@Z@@?$factory_cache_entry@UEmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIEmbeddingsSerializerStatics2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??ToByteArray@EmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUEmbedding@6789Microsoft@2@@Z@@Z

- ea: `0x180008080`
- end: `0x18000829a`
- name: `??$call@AEAV_lambda_1_@?1??ToByteArray@EmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUEmbedding@456789@@Z@@?$factory_cache_entry@UEmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIEmbeddingsSerializerStatics2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??ToByteArray@EmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUEmbedding@6789Microsoft@2@@Z@@Z`
- size: `538`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180003260`

## callees

- `0x180002bb0`
- `0x180008080`
- `0x180008ac0`
- `0x180009580`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x1800080c3`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.EmbeddingsSerializer`
- `0x1800081a5`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x180008205`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`

## pseudocode

```c
__int64 __fastcall ___call_AEAV_lambda_1___1__ToByteArray_EmbeddingsSerializer_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUEmbedding_456789__Z____factory_cache_entry_UEmbeddingsSerializer_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UIEmbeddingsSerializerStatics2_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__ToByteArray_EmbeddingsSerializer_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUEmbedding_6789Microsoft_2__Z__Z(
        __int64 a1,
        __int64 a2,
        _QWORD **a3)
{
  void (__fastcall ***v5)(_QWORD, _QWORD, _QWORD); // rdi
  int v6; // eax
  int v7; // eax
  void (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // [rsp+30h] [rbp-29h] BYREF
  int v10; // [rsp+38h] [rbp-21h] BYREF
  const char *v11; // [rsp+40h] [rbp-19h]
  _QWORD v12[2]; // [rsp+50h] [rbp-9h] BYREF
  _DWORD *v13; // [rsp+60h] [rbp+7h] BYREF
  _DWORD v14[4]; // [rsp+68h] [rbp+Fh] BYREF
  const wchar_t *v15; // [rsp+78h] [rbp+1Fh]
  __int64 v16; // [rsp+80h] [rbp+27h] BYREF
  void (__fastcall ***v17)(_QWORD, __int64 *, __int64 *); // [rsp+88h] [rbp+2Fh] BYREF

  v9 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))a2;
  v14[0] = 1;
  v14[1] = 71;
  v15 = L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.EmbeddingsSerializer";
  v13 = v14;
  v17 = 0;
  LODWORD(v12[0]) = 6148;
  v12[1] = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\base.h";
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v16,
    &v13,
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics2>,
    (__int64)&v17);
  if ( (int)v16 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v16, v12);
  }
  v5 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v17;
  v9 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v17;
  if ( !v17 || (v16 = 0, (**v17)(v17, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v16), !v16) )
  {
    LODWORD(v16) = 0;
    v17 = 0;
    v10 = 229;
    v11 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
          "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    v7 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, _QWORD, _QWORD), _QWORD, __int64 *, void (__fastcall ****)(_QWORD, __int64 *, __int64 *)))(*v5)[6])(
           v5,
           **a3,
           &v16,
           &v17);
    if ( v7 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v7, &v10);
    }
    *(_QWORD *)a2 = v17;
    *(_DWORD *)(a2 + 8) = v16;
    goto LABEL_11;
  }
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v16);
  v12[0] = &qword_180086598;
  _InterlockedIncrement64(&qword_180086598);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics2>,
          (signed __int64)v17,
          0) )
  {
    v9 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_1800865A0);
    v5 = 0;
  }
  LODWORD(v16) = 0;
  v17 = 0;
  v10 = 229;
  v11 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\Mi"
        "crosoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, void (__fastcall ****)(_QWORD, __int64 *, __int64 *)))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics2> + 48LL))(
         winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics2>,
         **a3,
         &v16,
         &v17);
  if ( v6 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v6, &v10);
  }
  *(_QWORD *)a2 = v17;
  *(_DWORD *)(a2 + 8) = v16;
  _InterlockedDecrement64(&qword_180086598);
  if ( v5 )
LABEL_11:
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v9);
  return a2;
}

```

## disassembly

```asm
0x180008080  mov     [rsp-8+arg_0], rbx
0x180008085  mov     [rsp-8+arg_18], rsi
0x18000808a  push    rbp
0x18000808b  push    rdi
0x18000808c  push    r14
0x18000808e  lea     rbp, [rsp-47h]
0x180008093  sub     rsp, 0A0h
0x18000809a  mov     rax, cs:__security_cookie
0x1800080a1  xor     rax, rsp
0x1800080a4  mov     [rbp+57h+var_20], rax
0x1800080a8  mov     rsi, r8
0x1800080ab  mov     rbx, rdx
0x1800080ae  mov     [rbp+57h+var_80], rdx
0x1800080b2  xor     r14d, r14d
0x1800080b5  mov     [rbp+57h+var_48], 1
0x1800080bc  mov     [rbp+57h+var_44], 47h ; 'G'
0x1800080c3  lea     rax, aMicrosoftAsgSe_5; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x1800080ca  mov     [rbp+57h+var_38], rax
0x1800080ce  lea     rax, [rbp+57h+var_48]
0x1800080d2  mov     [rbp+57h+var_50], rax
0x1800080d6  mov     [rbp+57h+var_28], r14
0x1800080da  mov     dword ptr [rbp+57h+var_60], 1804h
0x1800080e1  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x1800080e8  mov     [rbp+57h+var_58], rax
0x1800080ec  lea     r9, [rbp+57h+var_28]
0x1800080f0  lea     r8, ??$guid_v@UIEmbeddingsSerializerStatics2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics2>
0x1800080f7  lea     rdx, [rbp+57h+var_50]
0x1800080fb  lea     rcx, [rbp+57h+var_30]
0x1800080ff  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180008104  mov     ecx, dword ptr [rbp+57h+var_30]
0x180008107  test    ecx, ecx
0x180008109  js      loc_18000827E
0x18000810f  mov     rdi, [rbp+57h+var_28]
0x180008113  mov     [rbp+57h+var_80], rdi
0x180008117  test    rdi, rdi
0x18000811a  jz      loc_1800081F6
0x180008120  mov     [rbp+57h+var_30], r14
0x180008124  mov     rax, [rdi]
0x180008127  lea     r8, [rbp+57h+var_30]
0x18000812b  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180008132  mov     rcx, rdi
0x180008135  mov     rax, [rax]
0x180008138  call    cs:__guard_dispatch_icall_fptr
0x18000813e  mov     rax, [rbp+57h+var_30]
0x180008142  mov     [rbp+57h+var_30], rax
0x180008146  test    rax, rax
0x180008149  jz      loc_1800081F6
0x18000814f  lea     rcx, [rbp+57h+var_30]
0x180008153  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180008158  lea     rax, qword_180086598
0x18000815f  mov     [rbp+57h+var_60], rax
0x180008163  lock inc cs:qword_180086598
0x18000816b  mov     rcx, [rbp+57h+var_28]
0x18000816f  xor     eax, eax
0x180008171  lock cmpxchg cs:??$factory_cache_entry_v@UEmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIEmbeddingsSerializerStatics2@234567@@impl@winrt@@3U?$factory_cache_entry@UEmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIEmbeddingsSerializerStatics2@234567@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics2>
0x18000817a  jnz     short loc_180008196
0x18000817c  mov     [rbp+57h+var_80], r14
0x180008180  lea     rdx, stru_1800865A0; ListEntry
0x180008187  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000818e  call    WINRT_IMPL_InterlockedPushEntrySList
0x180008193  mov     edi, r14d
0x180008196  mov     dword ptr [rbp+57h+var_30], r14d
0x18000819a  mov     [rbp+57h+var_28], r14
0x18000819e  mov     [rbp+57h+var_78], 0E5h
0x1800081a5  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x1800081ac  mov     [rbp+57h+var_70], rax
0x1800081b0  mov     rcx, cs:??$factory_cache_entry_v@UEmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIEmbeddingsSerializerStatics2@234567@@impl@winrt@@3U?$factory_cache_entry@UEmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIEmbeddingsSerializerStatics2@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics2>
0x1800081b7  mov     rdx, [rsi]
0x1800081ba  mov     rax, [rcx]
0x1800081bd  lea     r9, [rbp+57h+var_28]
0x1800081c1  lea     r8, [rbp+57h+var_30]
0x1800081c5  mov     rdx, [rdx]
0x1800081c8  mov     rax, [rax+30h]
0x1800081cc  call    cs:__guard_dispatch_icall_fptr
0x1800081d2  test    eax, eax
0x1800081d4  js      loc_18000828B
0x1800081da  mov     rcx, [rbp+57h+var_28]
0x1800081de  mov     [rbx], rcx
0x1800081e1  mov     ecx, dword ptr [rbp+57h+var_30]
0x1800081e4  mov     [rbx+8], ecx
0x1800081e7  lock dec cs:qword_180086598
0x1800081ef  test    rdi, rdi
0x1800081f2  jz      short loc_180008248
0x1800081f4  jmp     short loc_18000823F
0x1800081f6  mov     dword ptr [rbp+57h+var_30], r14d
0x1800081fa  mov     [rbp+57h+var_28], r14
0x1800081fe  mov     [rbp+57h+var_78], 0E5h
0x180008205  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18000820c  mov     [rbp+57h+var_70], rax
0x180008210  mov     rdx, [rsi]
0x180008213  mov     rax, [rdi]
0x180008216  lea     r9, [rbp+57h+var_28]
0x18000821a  lea     r8, [rbp+57h+var_30]
0x18000821e  mov     rdx, [rdx]
0x180008221  mov     rcx, rdi
0x180008224  mov     rax, [rax+30h]
0x180008228  call    cs:__guard_dispatch_icall_fptr
0x18000822e  test    eax, eax
0x180008230  js      short loc_18000826F
0x180008232  mov     rax, [rbp+57h+var_28]
0x180008236  mov     [rbx], rax
0x180008239  mov     eax, dword ptr [rbp+57h+var_30]
0x18000823c  mov     [rbx+8], eax
0x18000823f  lea     rcx, [rbp+57h+var_80]
0x180008243  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180008248  mov     rax, rbx
0x18000824b  mov     rcx, [rbp+57h+var_20]
0x18000824f  xor     rcx, rsp; StackCookie
0x180008252  call    __security_check_cookie
0x180008257  lea     r11, [rsp+0B0h+var_10]
0x18000825f  mov     rbx, [r11+20h]
0x180008263  mov     rsi, [r11+38h]
0x180008267  mov     rsp, r11
0x18000826a  pop     r14
0x18000826c  pop     rdi
0x18000826d  pop     rbp
0x18000826e  retn
0x18000826f  lfence
0x180008272  lea     rdx, [rbp+57h+var_78]
0x180008276  mov     ecx, eax
0x180008278  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000827e  lfence
0x180008281  lea     rdx, [rbp+57h+var_60]
0x180008285  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000828b  lfence
0x18000828e  lea     rdx, [rbp+57h+var_78]
0x180008292  mov     ecx, eax
0x180008294  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
