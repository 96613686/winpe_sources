# ??$call@AEAV_lambda_1_@?1??CreateAsync@ImageEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUIndexVectorSpaceIds@456789@@Z@@?$factory_cache_entry@UImageEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIImageEmbeddingsGeneratorStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateAsync@ImageEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUIndexVectorSpaceIds@6789Microsoft@2@@Z@@Z

- ea: `0x18003ef70`
- end: `0x18003f18e`
- name: `??$call@AEAV_lambda_1_@?1??CreateAsync@ImageEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUIndexVectorSpaceIds@456789@@Z@@?$factory_cache_entry@UImageEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIImageEmbeddingsGeneratorStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateAsync@ImageEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUIndexVectorSpaceIds@6789Microsoft@2@@Z@@Z`
- size: `542`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int128 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18005b870`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x18003ef70`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x18003f094`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18003f0f6`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18003efb3`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.ImageEmbeddingsGenerator`

## pseudocode

```c
_QWORD *__fastcall ___call_AEAV_lambda_1___1__CreateAsync_ImageEmbeddingsGenerator_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUIndexVectorSpaceIds_456789__Z____factory_cache_entry_UImageEmbeddingsGenerator_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UIImageEmbeddingsGeneratorStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateAsync_ImageEmbeddingsGenerator_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUIndexVectorSpaceIds_6789Microsoft_2__Z__Z(
        __int64 a1,
        _QWORD *a2,
        __int128 **a3)
{
  __int64 v5; // rbx
  __int128 *v6; // rax
  int v7; // eax
  __int128 *v8; // rax
  int v9; // eax
  __int64 v11; // [rsp+20h] [rbp-39h] BYREF
  __int64 *v12; // [rsp+28h] [rbp-31h] BYREF
  const char *v13; // [rsp+30h] [rbp-29h]
  __int128 v14; // [rsp+40h] [rbp-19h] BYREF
  __int128 v15; // [rsp+50h] [rbp-9h]
  _QWORD *v16; // [rsp+68h] [rbp+Fh] BYREF
  _OWORD v17[2]; // [rsp+70h] [rbp+17h] BYREF

  v16 = a2;
  *((_QWORD *)&v14 + 1) = 0x4B00000001LL;
  *((_QWORD *)&v15 + 1) = L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.ImageEmbeddingsGenerator";
  *(_QWORD *)&v14 = (char *)&v14 + 8;
  *(_QWORD *)&v17[0] = 0;
  LODWORD(v12) = 6148;
  v13 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\base.h";
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v11,
    &v14,
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsGeneratorStatics>,
    (__int64)v17);
  if ( (int)v11 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v11, &v12);
  }
  v5 = *(_QWORD *)&v17[0];
  v11 = *(_QWORD *)&v17[0];
  if ( !*(_QWORD *)&v17[0]
    || (v16 = 0,
        (***(void (__fastcall ****)(_QWORD, __int64 *, _QWORD **))&v17[0])(
          *(_QWORD *)&v17[0],
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v16),
        !v16) )
  {
    v8 = *a3;
    v16 = 0;
    LODWORD(v12) = 265;
    v13 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
          "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    v17[0] = *v8;
    v17[1] = v8[1];
    v9 = (*(__int64 (__fastcall **)(__int64, _OWORD *, _QWORD **))(*(_QWORD *)v5 + 48LL))(v5, v17, &v16);
    if ( v9 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v9, &v12);
    }
    *a2 = v16;
    goto LABEL_11;
  }
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v16);
  v12 = &qword_1800869A8;
  _InterlockedIncrement64(&qword_1800869A8);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsGeneratorStatics>,
          *(signed __int64 *)&v17[0],
          0) )
  {
    v11 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_1800869B0);
    v5 = 0;
  }
  v6 = *a3;
  v16 = 0;
  LODWORD(v17[0]) = 265;
  *((_QWORD *)&v17[0] + 1) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gener"
                             "ated Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v14 = *v6;
  v15 = v6[1];
  v7 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsGeneratorStatics>
                                                                 + 48LL))(
         winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsGeneratorStatics>,
         &v14,
         &v16);
  if ( v7 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v7, v17);
  }
  *a2 = v16;
  _InterlockedDecrement64(&qword_1800869A8);
  if ( v5 )
LABEL_11:
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v11);
  return a2;
}

```

## disassembly

```asm
0x18003ef70  mov     [rsp-8+arg_0], rbx
0x18003ef75  mov     [rsp-8+arg_10], rsi
0x18003ef7a  push    rbp
0x18003ef7b  push    rdi
0x18003ef7c  push    r14
0x18003ef7e  lea     rbp, [rsp-47h]
0x18003ef83  sub     rsp, 0A0h
0x18003ef8a  mov     rax, cs:__security_cookie
0x18003ef91  xor     rax, rsp
0x18003ef94  mov     [rbp+57h+var_20], rax
0x18003ef98  mov     rsi, r8
0x18003ef9b  mov     rdi, rdx
0x18003ef9e  mov     [rbp+57h+var_48], rdx
0x18003efa2  xor     r14d, r14d
0x18003efa5  mov     dword ptr [rbp+57h+var_70+8], 1
0x18003efac  mov     dword ptr [rbp+57h+var_70+0Ch], 4Bh ; 'K'
0x18003efb3  lea     rax, aMicrosoftAsgSe_11; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x18003efba  mov     [rbp+57h+var_58], rax
0x18003efbe  lea     rax, [rbp+57h+var_70+8]
0x18003efc2  mov     qword ptr [rbp+57h+var_70], rax
0x18003efc6  mov     qword ptr [rbp+57h+var_40], r14
0x18003efca  mov     dword ptr [rbp+57h+var_88], 1804h
0x18003efd1  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003efd8  mov     [rbp+57h+var_80], rax
0x18003efdc  lea     r9, [rbp+57h+var_40]
0x18003efe0  lea     r8, ??$guid_v@UIImageEmbeddingsGeneratorStatics@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsGeneratorStatics>
0x18003efe7  lea     rdx, [rbp+57h+var_70]
0x18003efeb  lea     rcx, [rbp+57h+var_90]
0x18003efef  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18003eff4  mov     ecx, dword ptr [rbp+57h+var_90]
0x18003eff7  test    ecx, ecx
0x18003eff9  js      loc_18003F172
0x18003efff  mov     rbx, qword ptr [rbp+57h+var_40]
0x18003f003  mov     [rbp+57h+var_90], rbx
0x18003f007  test    rbx, rbx
0x18003f00a  jz      loc_18003F0E8
0x18003f010  mov     [rbp+57h+var_48], r14
0x18003f014  mov     rax, [rbx]
0x18003f017  lea     r8, [rbp+57h+var_48]
0x18003f01b  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18003f022  mov     rcx, rbx
0x18003f025  mov     rax, [rax]
0x18003f028  call    cs:__guard_dispatch_icall_fptr
0x18003f02e  mov     rax, [rbp+57h+var_48]
0x18003f032  mov     [rbp+57h+var_48], rax
0x18003f036  test    rax, rax
0x18003f039  jz      loc_18003F0E8
0x18003f03f  lea     rcx, [rbp+57h+var_48]
0x18003f043  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003f048  lea     rax, qword_1800869A8
0x18003f04f  mov     [rbp+57h+var_88], rax
0x18003f053  lock inc cs:qword_1800869A8
0x18003f05b  mov     rcx, qword ptr [rbp+57h+var_40]
0x18003f05f  xor     eax, eax
0x18003f061  lock cmpxchg cs:??$factory_cache_entry_v@UImageEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIImageEmbeddingsGeneratorStatics@234567@@impl@winrt@@3U?$factory_cache_entry@UImageEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIImageEmbeddingsGeneratorStatics@234567@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsGeneratorStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsGeneratorStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsGeneratorStatics>
0x18003f06a  jnz     short loc_18003F086
0x18003f06c  mov     [rbp+57h+var_90], r14
0x18003f070  lea     rdx, stru_1800869B0; ListEntry
0x18003f077  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18003f07e  call    WINRT_IMPL_InterlockedPushEntrySList
0x18003f083  mov     ebx, r14d
0x18003f086  mov     rax, [rsi]
0x18003f089  mov     [rbp+57h+var_48], r14
0x18003f08d  mov     dword ptr [rbp+57h+var_40], 109h
0x18003f094  lea     rcx, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003f09b  mov     qword ptr [rbp+57h+var_40+8], rcx
0x18003f09f  mov     rcx, cs:??$factory_cache_entry_v@UImageEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIImageEmbeddingsGeneratorStatics@234567@@impl@winrt@@3U?$factory_cache_entry@UImageEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIImageEmbeddingsGeneratorStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsGeneratorStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsGeneratorStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsGeneratorStatics>
0x18003f0a6  movups  xmm0, xmmword ptr [rax]
0x18003f0a9  movaps  [rbp+57h+var_70], xmm0
0x18003f0ad  movups  xmm1, xmmword ptr [rax+10h]
0x18003f0b1  movaps  xmmword ptr [rbp-9], xmm1
0x18003f0b5  mov     rax, [rcx]
0x18003f0b8  lea     r8, [rbp+57h+var_48]
0x18003f0bc  lea     rdx, [rbp+57h+var_70]
0x18003f0c0  mov     rax, [rax+30h]
0x18003f0c4  call    cs:__guard_dispatch_icall_fptr
0x18003f0ca  test    eax, eax
0x18003f0cc  js      loc_18003F17F
0x18003f0d2  mov     rcx, [rbp+57h+var_48]
0x18003f0d6  mov     [rdi], rcx
0x18003f0d9  lock dec cs:qword_1800869A8
0x18003f0e1  test    rbx, rbx
0x18003f0e4  jz      short loc_18003F13C
0x18003f0e6  jmp     short loc_18003F133
0x18003f0e8  mov     rax, [rsi]
0x18003f0eb  mov     [rbp+57h+var_48], r14
0x18003f0ef  mov     dword ptr [rbp+57h+var_88], 109h
0x18003f0f6  lea     rcx, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003f0fd  mov     [rbp+57h+var_80], rcx
0x18003f101  movups  xmm0, xmmword ptr [rax]
0x18003f104  movaps  [rbp+57h+var_40], xmm0
0x18003f108  movups  xmm1, xmmword ptr [rax+10h]
0x18003f10c  movaps  [rbp+57h+var_30], xmm1
0x18003f110  mov     rax, [rbx]
0x18003f113  lea     r8, [rbp+57h+var_48]
0x18003f117  lea     rdx, [rbp+57h+var_40]
0x18003f11b  mov     rcx, rbx
0x18003f11e  mov     rax, [rax+30h]
0x18003f122  call    cs:__guard_dispatch_icall_fptr
0x18003f128  test    eax, eax
0x18003f12a  js      short loc_18003F163
0x18003f12c  mov     rax, [rbp+57h+var_48]
0x18003f130  mov     [rdi], rax
0x18003f133  lea     rcx, [rbp+57h+var_90]
0x18003f137  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003f13c  mov     rax, rdi
0x18003f13f  mov     rcx, [rbp+57h+var_20]
0x18003f143  xor     rcx, rsp; StackCookie
0x18003f146  call    __security_check_cookie
0x18003f14b  lea     r11, [rsp+0B0h+var_10]
0x18003f153  mov     rbx, [r11+20h]
0x18003f157  mov     rsi, [r11+30h]
0x18003f15b  mov     rsp, r11
0x18003f15e  pop     r14
0x18003f160  pop     rdi
0x18003f161  pop     rbp
0x18003f162  retn
0x18003f163  lfence
0x18003f166  lea     rdx, [rbp+57h+var_88]
0x18003f16a  mov     ecx, eax
0x18003f16c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003f172  lfence
0x18003f175  lea     rdx, [rbp+57h+var_88]
0x18003f179  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003f17f  lfence
0x18003f182  lea     rdx, [rbp+57h+var_40]
0x18003f186  mov     ecx, eax
0x18003f188  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
