# ??$call@AEAV_lambda_1_@?1??CreateAsync@TextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUIndexVectorSpaceIds@456789@@Z@@?$factory_cache_entry@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UITextEmbeddingsGeneratorStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateAsync@TextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUIndexVectorSpaceIds@6789Microsoft@2@@Z@@Z

- ea: `0x18003ea50`
- end: `0x18003ec6e`
- name: `??$call@AEAV_lambda_1_@?1??CreateAsync@TextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUIndexVectorSpaceIds@456789@@Z@@?$factory_cache_entry@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UITextEmbeddingsGeneratorStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateAsync@TextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUIndexVectorSpaceIds@6789Microsoft@2@@Z@@Z`
- size: `542`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int128 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18005b450`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x18003ea50`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x18003eb74`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18003ebd6`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18003ea93`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.TextEmbeddingsGenerator`

## pseudocode

```c
_QWORD *__fastcall ___call_AEAV_lambda_1___1__CreateAsync_TextEmbeddingsGenerator_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUIndexVectorSpaceIds_456789__Z____factory_cache_entry_UTextEmbeddingsGenerator_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UITextEmbeddingsGeneratorStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateAsync_TextEmbeddingsGenerator_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUIndexVectorSpaceIds_6789Microsoft_2__Z__Z(
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
  *((_QWORD *)&v14 + 1) = 0x4A00000001LL;
  *((_QWORD *)&v15 + 1) = L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.TextEmbeddingsGenerator";
  *(_QWORD *)&v14 = (char *)&v14 + 8;
  *(_QWORD *)&v17[0] = 0;
  LODWORD(v12) = 6148;
  v13 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\base.h";
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v11,
    &v14,
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsGeneratorStatics>,
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
    LODWORD(v12) = 1309;
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
  v12 = &qword_180086988;
  _InterlockedIncrement64(&qword_180086988);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsGeneratorStatics>,
          *(signed __int64 *)&v17[0],
          0) )
  {
    v11 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180086990);
    v5 = 0;
  }
  v6 = *a3;
  v16 = 0;
  LODWORD(v17[0]) = 1309;
  *((_QWORD *)&v17[0] + 1) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gener"
                             "ated Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v14 = *v6;
  v15 = v6[1];
  v7 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsGeneratorStatics>
                                                                 + 48LL))(
         winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsGeneratorStatics>,
         &v14,
         &v16);
  if ( v7 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v7, v17);
  }
  *a2 = v16;
  _InterlockedDecrement64(&qword_180086988);
  if ( v5 )
LABEL_11:
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v11);
  return a2;
}

```

## disassembly

```asm
0x18003ea50  mov     [rsp-8+arg_0], rbx
0x18003ea55  mov     [rsp-8+arg_10], rsi
0x18003ea5a  push    rbp
0x18003ea5b  push    rdi
0x18003ea5c  push    r14
0x18003ea5e  lea     rbp, [rsp-47h]
0x18003ea63  sub     rsp, 0A0h
0x18003ea6a  mov     rax, cs:__security_cookie
0x18003ea71  xor     rax, rsp
0x18003ea74  mov     [rbp+57h+var_20], rax
0x18003ea78  mov     rsi, r8
0x18003ea7b  mov     rdi, rdx
0x18003ea7e  mov     [rbp+57h+var_48], rdx
0x18003ea82  xor     r14d, r14d
0x18003ea85  mov     dword ptr [rbp+57h+var_70+8], 1
0x18003ea8c  mov     dword ptr [rbp+57h+var_70+0Ch], 4Ah ; 'J'
0x18003ea93  lea     rax, aMicrosoftAsgSe_10; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x18003ea9a  mov     [rbp+57h+var_58], rax
0x18003ea9e  lea     rax, [rbp+57h+var_70+8]
0x18003eaa2  mov     qword ptr [rbp+57h+var_70], rax
0x18003eaa6  mov     qword ptr [rbp+57h+var_40], r14
0x18003eaaa  mov     dword ptr [rbp+57h+var_88], 1804h
0x18003eab1  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003eab8  mov     [rbp+57h+var_80], rax
0x18003eabc  lea     r9, [rbp+57h+var_40]
0x18003eac0  lea     r8, ??$guid_v@UITextEmbeddingsGeneratorStatics@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsGeneratorStatics>
0x18003eac7  lea     rdx, [rbp+57h+var_70]
0x18003eacb  lea     rcx, [rbp+57h+var_90]
0x18003eacf  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18003ead4  mov     ecx, dword ptr [rbp+57h+var_90]
0x18003ead7  test    ecx, ecx
0x18003ead9  js      loc_18003EC52
0x18003eadf  mov     rbx, qword ptr [rbp+57h+var_40]
0x18003eae3  mov     [rbp+57h+var_90], rbx
0x18003eae7  test    rbx, rbx
0x18003eaea  jz      loc_18003EBC8
0x18003eaf0  mov     [rbp+57h+var_48], r14
0x18003eaf4  mov     rax, [rbx]
0x18003eaf7  lea     r8, [rbp+57h+var_48]
0x18003eafb  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18003eb02  mov     rcx, rbx
0x18003eb05  mov     rax, [rax]
0x18003eb08  call    cs:__guard_dispatch_icall_fptr
0x18003eb0e  mov     rax, [rbp+57h+var_48]
0x18003eb12  mov     [rbp+57h+var_48], rax
0x18003eb16  test    rax, rax
0x18003eb19  jz      loc_18003EBC8
0x18003eb1f  lea     rcx, [rbp+57h+var_48]
0x18003eb23  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003eb28  lea     rax, qword_180086988
0x18003eb2f  mov     [rbp+57h+var_88], rax
0x18003eb33  lock inc cs:qword_180086988
0x18003eb3b  mov     rcx, qword ptr [rbp+57h+var_40]
0x18003eb3f  xor     eax, eax
0x18003eb41  lock cmpxchg cs:??$factory_cache_entry_v@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UITextEmbeddingsGeneratorStatics@234567@@impl@winrt@@3U?$factory_cache_entry@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UITextEmbeddingsGeneratorStatics@234567@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsGeneratorStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsGeneratorStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsGeneratorStatics>
0x18003eb4a  jnz     short loc_18003EB66
0x18003eb4c  mov     [rbp+57h+var_90], r14
0x18003eb50  lea     rdx, stru_180086990; ListEntry
0x18003eb57  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18003eb5e  call    WINRT_IMPL_InterlockedPushEntrySList
0x18003eb63  mov     ebx, r14d
0x18003eb66  mov     rax, [rsi]
0x18003eb69  mov     [rbp+57h+var_48], r14
0x18003eb6d  mov     dword ptr [rbp+57h+var_40], 51Dh
0x18003eb74  lea     rcx, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003eb7b  mov     qword ptr [rbp+57h+var_40+8], rcx
0x18003eb7f  mov     rcx, cs:??$factory_cache_entry_v@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UITextEmbeddingsGeneratorStatics@234567@@impl@winrt@@3U?$factory_cache_entry@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UITextEmbeddingsGeneratorStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsGeneratorStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsGeneratorStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsGeneratorStatics>
0x18003eb86  movups  xmm0, xmmword ptr [rax]
0x18003eb89  movaps  [rbp+57h+var_70], xmm0
0x18003eb8d  movups  xmm1, xmmword ptr [rax+10h]
0x18003eb91  movaps  xmmword ptr [rbp-9], xmm1
0x18003eb95  mov     rax, [rcx]
0x18003eb98  lea     r8, [rbp+57h+var_48]
0x18003eb9c  lea     rdx, [rbp+57h+var_70]
0x18003eba0  mov     rax, [rax+30h]
0x18003eba4  call    cs:__guard_dispatch_icall_fptr
0x18003ebaa  test    eax, eax
0x18003ebac  js      loc_18003EC5F
0x18003ebb2  mov     rcx, [rbp+57h+var_48]
0x18003ebb6  mov     [rdi], rcx
0x18003ebb9  lock dec cs:qword_180086988
0x18003ebc1  test    rbx, rbx
0x18003ebc4  jz      short loc_18003EC1C
0x18003ebc6  jmp     short loc_18003EC13
0x18003ebc8  mov     rax, [rsi]
0x18003ebcb  mov     [rbp+57h+var_48], r14
0x18003ebcf  mov     dword ptr [rbp+57h+var_88], 51Dh
0x18003ebd6  lea     rcx, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003ebdd  mov     [rbp+57h+var_80], rcx
0x18003ebe1  movups  xmm0, xmmword ptr [rax]
0x18003ebe4  movaps  [rbp+57h+var_40], xmm0
0x18003ebe8  movups  xmm1, xmmword ptr [rax+10h]
0x18003ebec  movaps  [rbp+57h+var_30], xmm1
0x18003ebf0  mov     rax, [rbx]
0x18003ebf3  lea     r8, [rbp+57h+var_48]
0x18003ebf7  lea     rdx, [rbp+57h+var_40]
0x18003ebfb  mov     rcx, rbx
0x18003ebfe  mov     rax, [rax+30h]
0x18003ec02  call    cs:__guard_dispatch_icall_fptr
0x18003ec08  test    eax, eax
0x18003ec0a  js      short loc_18003EC43
0x18003ec0c  mov     rax, [rbp+57h+var_48]
0x18003ec10  mov     [rdi], rax
0x18003ec13  lea     rcx, [rbp+57h+var_90]
0x18003ec17  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003ec1c  mov     rax, rdi
0x18003ec1f  mov     rcx, [rbp+57h+var_20]
0x18003ec23  xor     rcx, rsp; StackCookie
0x18003ec26  call    __security_check_cookie
0x18003ec2b  lea     r11, [rsp+0B0h+var_10]
0x18003ec33  mov     rbx, [r11+20h]
0x18003ec37  mov     rsi, [r11+30h]
0x18003ec3b  mov     rsp, r11
0x18003ec3e  pop     r14
0x18003ec40  pop     rdi
0x18003ec41  pop     rbp
0x18003ec42  retn
0x18003ec43  lfence
0x18003ec46  lea     rdx, [rbp+57h+var_88]
0x18003ec4a  mov     ecx, eax
0x18003ec4c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003ec52  lfence
0x18003ec55  lea     rdx, [rbp+57h+var_88]
0x18003ec59  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003ec5f  lfence
0x18003ec62  lea     rdx, [rbp+57h+var_40]
0x18003ec66  mov     ecx, eax
0x18003ec68  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
