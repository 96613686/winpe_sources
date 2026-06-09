# ??$call@AEAV_lambda_1_@?1??CreateEmbeddingsGeneratorAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUguid@9@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateEmbeddingsGeneratorAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUguid@2@@Z@@Z

- ea: `0x180030380`
- end: `0x18003058e`
- name: `??$call@AEAV_lambda_1_@?1??CreateEmbeddingsGeneratorAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUguid@9@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateEmbeddingsGeneratorAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUguid@2@@Z@@Z`
- size: `526`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int128 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180056590`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x180030380`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x1800304a4`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x1800304fe`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x1800303c3`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticImageIndexStore`

## pseudocode

```c
_QWORD *__fastcall ___call_AEAV_lambda_1___1__CreateEmbeddingsGeneratorAsync_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUguid_9__Z____factory_cache_entry_USemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticImageIndexStoreStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateEmbeddingsGeneratorAsync_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUguid_2__Z__Z(
        __int64 a1,
        _QWORD *a2,
        __int128 **a3)
{
  signed __int64 v5; // rbx
  __int128 *v6; // rax
  int v7; // eax
  __int128 *v8; // rax
  int v9; // eax
  signed __int64 v11; // [rsp+20h] [rbp-29h] BYREF
  __int64 *v12; // [rsp+28h] [rbp-21h] BYREF
  const char *v13; // [rsp+30h] [rbp-19h]
  __int128 v14; // [rsp+40h] [rbp-9h] BYREF
  _DWORD *v15; // [rsp+50h] [rbp+7h] BYREF
  _DWORD v16[4]; // [rsp+58h] [rbp+Fh] BYREF
  const wchar_t *v17; // [rsp+68h] [rbp+1Fh]
  _QWORD *v18; // [rsp+70h] [rbp+27h] BYREF
  signed __int64 v19[2]; // [rsp+78h] [rbp+2Fh] BYREF

  v18 = a2;
  v16[0] = 1;
  v16[1] = 74;
  v17 = L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticImageIndexStore";
  v15 = v16;
  v19[0] = 0;
  LODWORD(v12) = 6148;
  v13 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\base.h";
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v11,
    &v15,
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>,
    (__int64)v19);
  if ( (int)v11 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v11, &v12);
  }
  v5 = v19[0];
  v11 = v19[0];
  if ( !v19[0]
    || (v18 = 0,
        (**(void (__fastcall ***)(signed __int64, __int64 *, _QWORD **))v19[0])(
          v19[0],
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v18),
        !v18) )
  {
    v8 = *a3;
    v18 = 0;
    LODWORD(v12) = 722;
    v13 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
          "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    v14 = *v8;
    v9 = (*(__int64 (__fastcall **)(signed __int64, __int128 *, _QWORD **))(*(_QWORD *)v5 + 112LL))(v5, &v14, &v18);
    if ( v9 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v9, &v12);
    }
    *a2 = v18;
    goto LABEL_11;
  }
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v18);
  v12 = &qword_180086938;
  _InterlockedIncrement64(&qword_180086938);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>,
          v19[0],
          0) )
  {
    v11 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180086940);
    v5 = 0;
  }
  v6 = *a3;
  v18 = 0;
  LODWORD(v19[0]) = 722;
  v19[1] = (signed __int64)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generat"
                           "ed Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v14 = *v6;
  v7 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
                                                                 + 112LL))(
         winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>,
         &v14,
         &v18);
  if ( v7 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v7, v19);
  }
  *a2 = v18;
  _InterlockedDecrement64(&qword_180086938);
  if ( v5 )
LABEL_11:
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v11);
  return a2;
}

```

## disassembly

```asm
0x180030380  mov     [rsp-8+arg_0], rbx
0x180030385  mov     [rsp-8+arg_10], rsi
0x18003038a  push    rbp
0x18003038b  push    rdi
0x18003038c  push    r14
0x18003038e  lea     rbp, [rsp-47h]
0x180030393  sub     rsp, 90h
0x18003039a  mov     rax, cs:__security_cookie
0x1800303a1  xor     rax, rsp
0x1800303a4  mov     [rbp+57h+var_18], rax
0x1800303a8  mov     rsi, r8
0x1800303ab  mov     rdi, rdx
0x1800303ae  mov     [rbp+57h+var_30], rdx
0x1800303b2  xor     r14d, r14d
0x1800303b5  mov     [rbp+57h+var_48], 1
0x1800303bc  mov     [rbp+57h+var_44], 4Ah ; 'J'
0x1800303c3  lea     rax, aMicrosoftAsgSe_12; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x1800303ca  mov     [rbp+57h+var_38], rax
0x1800303ce  lea     rax, [rbp+57h+var_48]
0x1800303d2  mov     [rbp+57h+var_50], rax
0x1800303d6  mov     [rbp+57h+var_28], r14
0x1800303da  mov     dword ptr [rbp+57h+var_78], 1804h
0x1800303e1  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x1800303e8  mov     [rbp+57h+var_70], rax
0x1800303ec  lea     r9, [rbp+57h+var_28]
0x1800303f0  lea     r8, ??$guid_v@UISemanticImageIndexStoreStatics@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x1800303f7  lea     rdx, [rbp+57h+var_50]
0x1800303fb  lea     rcx, [rbp+57h+var_80]
0x1800303ff  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180030404  mov     ecx, dword ptr [rbp+57h+var_80]
0x180030407  test    ecx, ecx
0x180030409  js      loc_180030572
0x18003040f  mov     rbx, [rbp+57h+var_28]
0x180030413  mov     [rbp+57h+var_80], rbx
0x180030417  test    rbx, rbx
0x18003041a  jz      loc_1800304F0
0x180030420  mov     [rbp+57h+var_30], r14
0x180030424  mov     rax, [rbx]
0x180030427  lea     r8, [rbp+57h+var_30]
0x18003042b  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180030432  mov     rcx, rbx
0x180030435  mov     rax, [rax]
0x180030438  call    cs:__guard_dispatch_icall_fptr
0x18003043e  mov     rax, [rbp+57h+var_30]
0x180030442  mov     [rbp+57h+var_30], rax
0x180030446  test    rax, rax
0x180030449  jz      loc_1800304F0
0x18003044f  lea     rcx, [rbp+57h+var_30]
0x180030453  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180030458  lea     rax, qword_180086938
0x18003045f  mov     [rbp+57h+var_78], rax
0x180030463  lock inc cs:qword_180086938
0x18003046b  mov     rcx, [rbp+57h+var_28]
0x18003046f  xor     eax, eax
0x180030471  lock cmpxchg cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x18003047a  jnz     short loc_180030496
0x18003047c  mov     [rbp+57h+var_80], r14
0x180030480  lea     rdx, stru_180086940; ListEntry
0x180030487  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18003048e  call    WINRT_IMPL_InterlockedPushEntrySList
0x180030493  mov     ebx, r14d
0x180030496  mov     rax, [rsi]
0x180030499  mov     [rbp+57h+var_30], r14
0x18003049d  mov     dword ptr [rbp+57h+var_28], 2D2h
0x1800304a4  lea     rcx, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x1800304ab  mov     [rbp+57h+var_20], rcx
0x1800304af  mov     rcx, cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x1800304b6  movups  xmm0, xmmword ptr [rax]
0x1800304b9  movaps  [rbp+57h+var_60], xmm0
0x1800304bd  mov     rax, [rcx]
0x1800304c0  lea     r8, [rbp+57h+var_30]
0x1800304c4  lea     rdx, [rbp+57h+var_60]
0x1800304c8  mov     rax, [rax+70h]
0x1800304cc  call    cs:__guard_dispatch_icall_fptr
0x1800304d2  test    eax, eax
0x1800304d4  js      loc_18003057F
0x1800304da  mov     rcx, [rbp+57h+var_30]
0x1800304de  mov     [rdi], rcx
0x1800304e1  lock dec cs:qword_180086938
0x1800304e9  test    rbx, rbx
0x1800304ec  jz      short loc_18003053C
0x1800304ee  jmp     short loc_180030533
0x1800304f0  mov     rax, [rsi]
0x1800304f3  mov     [rbp+57h+var_30], r14
0x1800304f7  mov     dword ptr [rbp+57h+var_78], 2D2h
0x1800304fe  lea     rcx, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180030505  mov     [rbp+57h+var_70], rcx
0x180030509  movups  xmm0, xmmword ptr [rax]
0x18003050c  movaps  [rbp+57h+var_60], xmm0
0x180030510  mov     rax, [rbx]
0x180030513  lea     r8, [rbp+57h+var_30]
0x180030517  lea     rdx, [rbp+57h+var_60]
0x18003051b  mov     rcx, rbx
0x18003051e  mov     rax, [rax+70h]
0x180030522  call    cs:__guard_dispatch_icall_fptr
0x180030528  test    eax, eax
0x18003052a  js      short loc_180030563
0x18003052c  mov     rax, [rbp+57h+var_30]
0x180030530  mov     [rdi], rax
0x180030533  lea     rcx, [rbp+57h+var_80]
0x180030537  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003053c  mov     rax, rdi
0x18003053f  mov     rcx, [rbp+57h+var_18]
0x180030543  xor     rcx, rsp; StackCookie
0x180030546  call    __security_check_cookie
0x18003054b  lea     r11, [rsp+0A0h+var_10]
0x180030553  mov     rbx, [r11+20h]
0x180030557  mov     rsi, [r11+30h]
0x18003055b  mov     rsp, r11
0x18003055e  pop     r14
0x180030560  pop     rdi
0x180030561  pop     rbp
0x180030562  retn
0x180030563  lfence
0x180030566  lea     rdx, [rbp+57h+var_78]
0x18003056a  mov     ecx, eax
0x18003056c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180030572  lfence
0x180030575  lea     rdx, [rbp+57h+var_78]
0x180030579  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003057f  lfence
0x180030582  lea     rdx, [rbp+57h+var_28]
0x180030586  mov     ecx, eax
0x180030588  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
