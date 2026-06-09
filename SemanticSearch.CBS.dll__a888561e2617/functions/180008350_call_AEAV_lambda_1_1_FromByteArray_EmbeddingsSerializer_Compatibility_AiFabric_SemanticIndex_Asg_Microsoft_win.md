# ??$call@AEAV_lambda_1_@?1??FromByteArray@EmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@U?$array_view@$$CBE@9@@Z@@?$factory_cache_entry@UEmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIEmbeddingsSerializerStatics2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??FromByteArray@EmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@U?$array_view@$$CBE@2@@Z@@Z

- ea: `0x180008350`
- end: `0x180008517`
- name: `??$call@AEAV_lambda_1_@?1??FromByteArray@EmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@U?$array_view@$$CBE@9@@Z@@?$factory_cache_entry@UEmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIEmbeddingsSerializerStatics2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??FromByteArray@EmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@U?$array_view@$$CBE@2@@Z@@Z`
- size: `455`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180003180`

## callees

- `0x180002bb0`
- `0x1800082a0`
- `0x180008350`
- `0x180008ac0`
- `0x180009580`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x180008394`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.EmbeddingsSerializer`
- `0x180008493`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`

## pseudocode

```c
_QWORD *__fastcall ___call_AEAV_lambda_1___1__FromByteArray_EmbeddingsSerializer_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_U__array_view___CBE_9__Z____factory_cache_entry_UEmbeddingsSerializer_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UIEmbeddingsSerializerStatics2_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__FromByteArray_EmbeddingsSerializer_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_U__array_view___CBE_2__Z__Z(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3)
{
  __int64 v5; // r14
  signed __int64 v6; // rbx
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v10[4]; // [rsp+30h] [rbp-29h] BYREF
  _DWORD *v11; // [rsp+40h] [rbp-19h] BYREF
  _DWORD v12[4]; // [rsp+48h] [rbp-11h] BYREF
  const wchar_t *v13; // [rsp+58h] [rbp-1h]
  _QWORD v14[2]; // [rsp+60h] [rbp+7h] BYREF
  signed __int64 v15[2]; // [rsp+70h] [rbp+17h] BYREF

  HIDWORD(v14[0]) = HIDWORD(a2);
  v5 = 1;
  v12[0] = 1;
  v12[1] = 71;
  v13 = L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.EmbeddingsSerializer";
  v11 = v12;
  v15[0] = 0;
  LODWORD(v14[0]) = 6148;
  v14[1] = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\base.h";
  winrt::impl::get_runtime_activation_factory_impl<0>(
    v10,
    &v11,
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics2>,
    (__int64)v15);
  if ( (v10[0] & 0x80000000) != 0 )
  {
    _mm_lfence();
    winrt::throw_hresult(v10[0], v14);
  }
  v6 = v15[0];
  *(_QWORD *)v10 = v15[0];
  if ( !v15[0]
    || (v14[0] = 0,
        (**(void (__fastcall ***)(signed __int64, __int64 *, _QWORD *))v15[0])(
          v15[0],
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          v14),
        !v14[0]) )
  {
    v7 = *a3;
    v14[0] = 0;
    LODWORD(v15[0]) = 235;
    v15[1] = (signed __int64)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gener"
                             "ated Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    if ( *(_DWORD *)(v7 + 8) )
      v5 = *(_QWORD *)v7;
    v8 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, __int64, _QWORD *))(*(_QWORD *)v6 + 56LL))(
           v6,
           *(_QWORD *)(v7 + 8),
           v5,
           v14);
    if ( v8 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v8, v15);
    }
    *a2 = v14[0];
    goto LABEL_12;
  }
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v14);
  v14[0] = &qword_180086598;
  _InterlockedIncrement64(&qword_180086598);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics2>,
          v15[0],
          0) )
  {
    *(_QWORD *)v10 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_1800865A0);
    v6 = 0;
  }
  `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer::FromByteArray'::`2'::_lambda_1_::operator()(
    a3,
    a2,
    &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics2>);
  _InterlockedDecrement64(&qword_180086598);
  if ( v6 )
LABEL_12:
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v10);
  return a2;
}

```

## disassembly

```asm
0x180008350  mov     [rsp-8+arg_0], rbx
0x180008355  push    rbp
0x180008356  push    rsi
0x180008357  push    rdi
0x180008358  push    r14
0x18000835a  push    r15
0x18000835c  lea     rbp, [rsp-37h]
0x180008361  sub     rsp, 90h
0x180008368  mov     rax, cs:__security_cookie
0x18000836f  xor     rax, rsp
0x180008372  mov     [rbp+57h+var_30], rax
0x180008376  mov     rsi, r8
0x180008379  mov     rdi, rdx
0x18000837c  mov     [rbp+57h+var_50], rdx
0x180008380  xor     r15d, r15d
0x180008383  mov     r14d, 1
0x180008389  mov     [rbp+57h+var_68], r14d
0x18000838d  mov     [rbp+57h+var_64], 47h ; 'G'
0x180008394  lea     rax, aMicrosoftAsgSe_5; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x18000839b  mov     [rbp+57h+var_58], rax
0x18000839f  lea     rax, [rbp+57h+var_68]
0x1800083a3  mov     [rbp+57h+var_70], rax
0x1800083a7  mov     [rbp+57h+var_40], r15
0x1800083ab  mov     dword ptr [rbp+57h+var_50], 1804h
0x1800083b2  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x1800083b9  mov     [rbp+57h+var_48], rax
0x1800083bd  lea     r9, [rbp+57h+var_40]
0x1800083c1  lea     r8, ??$guid_v@UIEmbeddingsSerializerStatics2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics2>
0x1800083c8  lea     rdx, [rbp+57h+var_70]
0x1800083cc  lea     rcx, [rbp+57h+var_80]
0x1800083d0  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x1800083d5  mov     ecx, [rbp+57h+var_80]
0x1800083d8  test    ecx, ecx
0x1800083da  js      loc_18000850A
0x1800083e0  mov     rbx, [rbp+57h+var_40]
0x1800083e4  mov     qword ptr [rbp+57h+var_80], rbx
0x1800083e8  test    rbx, rbx
0x1800083eb  jz      loc_180008485
0x1800083f1  mov     [rbp+57h+var_50], r15
0x1800083f5  mov     rax, [rbx]
0x1800083f8  lea     r8, [rbp+57h+var_50]
0x1800083fc  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180008403  mov     rcx, rbx
0x180008406  mov     rax, [rax]
0x180008409  call    cs:__guard_dispatch_icall_fptr
0x18000840f  mov     rax, [rbp+57h+var_50]
0x180008413  mov     [rbp+57h+var_50], rax
0x180008417  test    rax, rax
0x18000841a  jz      short loc_180008485
0x18000841c  lea     rcx, [rbp+57h+var_50]
0x180008420  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180008425  lea     rax, qword_180086598
0x18000842c  mov     [rbp+57h+var_50], rax
0x180008430  lock inc cs:qword_180086598
0x180008438  mov     rdx, [rbp+57h+var_40]
0x18000843c  xor     eax, eax
0x18000843e  lock cmpxchg cs:??$factory_cache_entry_v@UEmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIEmbeddingsSerializerStatics2@234567@@impl@winrt@@3U?$factory_cache_entry@UEmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIEmbeddingsSerializerStatics2@234567@@12@A, rdx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics2>
0x180008447  jnz     short loc_180008463
0x180008449  mov     qword ptr [rbp+57h+var_80], r15
0x18000844d  lea     rdx, stru_1800865A0; ListEntry
0x180008454  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000845b  call    WINRT_IMPL_InterlockedPushEntrySList
0x180008460  mov     ebx, r15d
0x180008463  lea     r8, ??$factory_cache_entry_v@UEmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIEmbeddingsSerializerStatics2@234567@@impl@winrt@@3U?$factory_cache_entry@UEmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIEmbeddingsSerializerStatics2@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics2>
0x18000846a  mov     rdx, rdi
0x18000846d  mov     rcx, rsi
0x180008470  call    ??R_lambda_1_@?1??FromByteArray@EmbeddingsSerializer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@U?$array_view@$$CBE@8@@Z@QEBA@AEBUIEmbeddingsSerializerStatics2@345678@@Z; `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EmbeddingsSerializer::FromByteArray(winrt::array_view<uchar const>)'::`2'::_lambda_1_::operator()(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics2 const &)
0x180008475  nop
0x180008476  lock dec cs:qword_180086598
0x18000847e  test    rbx, rbx
0x180008481  jz      short loc_1800084D5
0x180008483  jmp     short loc_1800084CC
0x180008485  mov     rcx, [rsi]
0x180008488  mov     [rbp+57h+var_50], r15
0x18000848c  mov     dword ptr [rbp+57h+var_40], 0EBh
0x180008493  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18000849a  mov     [rbp+57h+var_38], rax
0x18000849e  mov     rax, [rbx]
0x1800084a1  cmp     dword ptr [rcx+8], 0
0x1800084a5  cmovnz  r14, [rcx]
0x1800084a9  lea     r9, [rbp+57h+var_50]
0x1800084ad  mov     r8, r14
0x1800084b0  mov     rdx, [rcx+8]
0x1800084b4  mov     rcx, rbx
0x1800084b7  mov     rax, [rax+38h]
0x1800084bb  call    cs:__guard_dispatch_icall_fptr
0x1800084c1  test    eax, eax
0x1800084c3  js      short loc_1800084FB
0x1800084c5  mov     rax, [rbp+57h+var_50]
0x1800084c9  mov     [rdi], rax
0x1800084cc  lea     rcx, [rbp+57h+var_80]
0x1800084d0  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800084d5  mov     rax, rdi
0x1800084d8  mov     rcx, [rbp+57h+var_30]
0x1800084dc  xor     rcx, rsp; StackCookie
0x1800084df  call    __security_check_cookie
0x1800084e4  mov     rbx, [rsp+0B0h+arg_0]
0x1800084ec  add     rsp, 90h
0x1800084f3  pop     r15
0x1800084f5  pop     r14
0x1800084f7  pop     rdi
0x1800084f8  pop     rsi
0x1800084f9  pop     rbp
0x1800084fa  retn
0x1800084fb  lfence
0x1800084fe  lea     rdx, [rbp+57h+var_40]
0x180008502  mov     ecx, eax
0x180008504  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000850a  lfence
0x18000850d  lea     rdx, [rbp+57h+var_50]
0x180008511  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
