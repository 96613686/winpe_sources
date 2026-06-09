# ??$call@AEAV_lambda_1_@?1??CalculateSerializedSize@EmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUEmbedding@456789@@Z@@?$factory_cache_entry@UEmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIEmbeddingsSerializerStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CalculateSerializedSize@EmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUEmbedding@6789Microsoft@2@@Z@@Z

- ea: `0x180008ef0`
- end: `0x180009095`
- name: `??$call@AEAV_lambda_1_@?1??CalculateSerializedSize@EmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUEmbedding@456789@@Z@@?$factory_cache_entry@UEmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIEmbeddingsSerializerStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CalculateSerializedSize@EmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUEmbedding@6789Microsoft@2@@Z@@Z`
- size: `421`
- prototype: `__int64 __fastcall(__int64, _QWORD **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800034b0`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180008e70`
- `0x180008ef0`
- `0x180009580`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x180008f28`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.EmbeddingsSerializer`
- `0x18000901b`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`

## pseudocode

```c
__int64 __fastcall ___call_AEAV_lambda_1___1__CalculateSerializedSize_EmbeddingsSerializer_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUEmbedding_456789__Z____factory_cache_entry_UEmbeddingsSerializer_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UIEmbeddingsSerializerStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CalculateSerializedSize_EmbeddingsSerializer_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUEmbedding_6789Microsoft_2__Z__Z(
        __int64 a1,
        _QWORD **a2)
{
  signed __int64 v3; // rbx
  unsigned int v4; // edi
  int v5; // eax
  _QWORD v7[2]; // [rsp+20h] [rbp-50h] BYREF
  _DWORD *v8; // [rsp+30h] [rbp-40h] BYREF
  _DWORD v9[4]; // [rsp+38h] [rbp-38h] BYREF
  const wchar_t *v10; // [rsp+48h] [rbp-28h]
  __int64 *v11; // [rsp+50h] [rbp-20h] BYREF
  signed __int64 v12[2]; // [rsp+58h] [rbp-18h] BYREF

  v9[0] = 1;
  v9[1] = 71;
  v10 = L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.EmbeddingsSerializer";
  v8 = v9;
  v12[0] = 0;
  LODWORD(v7[0]) = 6148;
  v7[1] = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\base.h";
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v11,
    &v8,
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics>,
    (__int64)v12);
  if ( (int)v11 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v11, v7);
  }
  v3 = v12[0];
  v7[0] = v12[0];
  if ( v12[0]
    && (v11 = 0,
        (**(void (__fastcall ***)(signed __int64, __int64 *, __int64 **))v12[0])(
          v12[0],
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v11),
        v11) )
  {
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v11);
    v11 = &qword_1800865B8;
    _InterlockedIncrement64(&qword_1800865B8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics>,
            v12[0],
            0) )
    {
      v7[0] = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_1800865C0);
      v3 = 0;
    }
    v4 = `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer::CalculateSerializedSize'::`2'::_lambda_1_::operator()(
           a2,
           &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics>);
    _InterlockedDecrement64(&qword_1800865B8);
  }
  else
  {
    LODWORD(v11) = 0;
    LODWORD(v12[0]) = 222;
    v12[1] = (signed __int64)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gener"
                             "ated Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    v5 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, __int64 **))(*(_QWORD *)v3 + 48LL))(v3, **a2, &v11);
    if ( v5 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v5, v12);
    }
    v4 = (unsigned int)v11;
  }
  if ( v3 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v7);
  return v4;
}

```

## disassembly

```asm
0x180008ef0  mov     [rsp-8+arg_0], rbx
0x180008ef5  mov     [rsp-8+arg_10], rsi
0x180008efa  mov     [rsp-8+arg_18], rdi
0x180008eff  push    rbp
0x180008f00  mov     rbp, rsp
0x180008f03  sub     rsp, 70h
0x180008f07  mov     rax, cs:__security_cookie
0x180008f0e  xor     rax, rsp
0x180008f11  mov     [rbp+var_8], rax
0x180008f15  mov     rdi, rdx
0x180008f18  xor     esi, esi
0x180008f1a  mov     [rbp+var_38], 1
0x180008f21  mov     [rbp+var_34], 47h ; 'G'
0x180008f28  lea     rax, aMicrosoftAsgSe_5; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x180008f2f  mov     [rbp+var_28], rax
0x180008f33  lea     rax, [rbp+var_38]
0x180008f37  mov     [rbp+var_40], rax
0x180008f3b  mov     [rbp+var_18], rsi
0x180008f3f  mov     dword ptr [rbp+var_50], 1804h
0x180008f46  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180008f4d  mov     [rbp+var_48], rax
0x180008f51  lea     r9, [rbp+var_18]
0x180008f55  lea     r8, ??$guid_v@UIEmbeddingsSerializerStatics@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics>
0x180008f5c  lea     rdx, [rbp+var_40]
0x180008f60  lea     rcx, [rbp+var_20]
0x180008f64  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180008f69  mov     ecx, dword ptr [rbp+var_20]
0x180008f6c  test    ecx, ecx
0x180008f6e  js      loc_180009088
0x180008f74  mov     rbx, [rbp+var_18]
0x180008f78  mov     [rbp+var_50], rbx
0x180008f7c  test    rbx, rbx
0x180008f7f  jz      loc_180009011
0x180008f85  mov     [rbp+var_20], rsi
0x180008f89  mov     rax, [rbx]
0x180008f8c  lea     r8, [rbp+var_20]
0x180008f90  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180008f97  mov     rcx, rbx
0x180008f9a  mov     rax, [rax]
0x180008f9d  call    cs:__guard_dispatch_icall_fptr
0x180008fa3  mov     rax, [rbp+var_20]
0x180008fa7  mov     [rbp+var_20], rax
0x180008fab  test    rax, rax
0x180008fae  jz      short loc_180009011
0x180008fb0  lea     rcx, [rbp+var_20]
0x180008fb4  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180008fb9  lea     rax, qword_1800865B8
0x180008fc0  mov     [rbp+var_20], rax
0x180008fc4  lock inc cs:qword_1800865B8
0x180008fcc  mov     rdx, [rbp+var_18]
0x180008fd0  xor     eax, eax
0x180008fd2  lock cmpxchg cs:??$factory_cache_entry_v@UEmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIEmbeddingsSerializerStatics@234567@@impl@winrt@@3U?$factory_cache_entry@UEmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIEmbeddingsSerializerStatics@234567@@12@A, rdx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics>
0x180008fdb  jnz     short loc_180008FF6
0x180008fdd  mov     [rbp+var_50], rsi
0x180008fe1  lea     rdx, stru_1800865C0; ListEntry
0x180008fe8  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180008fef  call    WINRT_IMPL_InterlockedPushEntrySList
0x180008ff4  mov     ebx, esi
0x180008ff6  lea     rdx, ??$factory_cache_entry_v@UEmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIEmbeddingsSerializerStatics@234567@@impl@winrt@@3U?$factory_cache_entry@UEmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIEmbeddingsSerializerStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics>
0x180008ffd  mov     rcx, rdi
0x180009000  call    ??R_lambda_1_@?1??CalculateSerializedSize@EmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUEmbedding@345678@@Z@QEBA@AEBUIEmbeddingsSerializerStatics@345678@@Z; `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer::CalculateSerializedSize(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding const &)'::`2'::_lambda_1_::operator()(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics const &)
0x180009005  mov     edi, eax
0x180009007  lock dec cs:qword_1800865B8
0x18000900f  jmp     short loc_180009047
0x180009011  mov     dword ptr [rbp+var_20], esi
0x180009014  mov     dword ptr [rbp+var_18], 0DEh
0x18000901b  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180009022  mov     [rbp+var_10], rax
0x180009026  mov     rdx, [rdi]
0x180009029  mov     rax, [rbx]
0x18000902c  lea     r8, [rbp+var_20]
0x180009030  mov     rdx, [rdx]
0x180009033  mov     rcx, rbx
0x180009036  mov     rax, [rax+30h]
0x18000903a  call    cs:__guard_dispatch_icall_fptr
0x180009040  test    eax, eax
0x180009042  js      short loc_180009079
0x180009044  mov     edi, dword ptr [rbp+var_20]
0x180009047  test    rbx, rbx
0x18000904a  jz      short loc_180009055
0x18000904c  lea     rcx, [rbp+var_50]
0x180009050  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180009055  mov     eax, edi
0x180009057  mov     rcx, [rbp+var_8]
0x18000905b  xor     rcx, rsp; StackCookie
0x18000905e  call    __security_check_cookie
0x180009063  lea     r11, [rsp+70h+var_s0]
0x180009068  mov     rbx, [r11+10h]
0x18000906c  mov     rsi, [r11+20h]
0x180009070  mov     rdi, [r11+28h]
0x180009074  mov     rsp, r11
0x180009077  pop     rbp
0x180009078  retn
0x180009079  lfence
0x18000907c  lea     rdx, [rbp+var_18]
0x180009080  mov     ecx, eax
0x180009082  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180009088  lfence
0x18000908b  lea     rdx, [rbp+var_50]
0x18000908f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
