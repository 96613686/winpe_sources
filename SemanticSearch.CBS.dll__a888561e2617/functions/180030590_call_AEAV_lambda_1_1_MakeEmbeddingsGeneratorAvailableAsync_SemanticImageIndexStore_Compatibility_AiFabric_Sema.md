# ??$call@AEAV_lambda_1_@?1??MakeEmbeddingsGeneratorAvailableAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUguid@9@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??MakeEmbeddingsGeneratorAvailableAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUguid@2@@Z@@Z

- ea: `0x180030590`
- end: `0x18003079e`
- name: `??$call@AEAV_lambda_1_@?1??MakeEmbeddingsGeneratorAvailableAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUguid@9@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??MakeEmbeddingsGeneratorAvailableAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUguid@2@@Z@@Z`
- size: `526`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int128 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180020b40`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x180030590`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x1800306b4`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18003070e`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x1800305d3`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticImageIndexStore`

## pseudocode

```c
_QWORD *__fastcall ___call_AEAV_lambda_1___1__MakeEmbeddingsGeneratorAvailableAsync_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUguid_9__Z____factory_cache_entry_USemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticImageIndexStoreStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__MakeEmbeddingsGeneratorAvailableAsync_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUguid_2__Z__Z(
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
    LODWORD(v12) = 716;
    v13 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
          "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    v14 = *v8;
    v9 = (*(__int64 (__fastcall **)(signed __int64, __int128 *, _QWORD **))(*(_QWORD *)v5 + 104LL))(v5, &v14, &v18);
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
  LODWORD(v19[0]) = 716;
  v19[1] = (signed __int64)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generat"
                           "ed Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v14 = *v6;
  v7 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
                                                                 + 104LL))(
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
0x180030590  mov     [rsp-8+arg_0], rbx
0x180030595  mov     [rsp-8+arg_10], rsi
0x18003059a  push    rbp
0x18003059b  push    rdi
0x18003059c  push    r14
0x18003059e  lea     rbp, [rsp-47h]
0x1800305a3  sub     rsp, 90h
0x1800305aa  mov     rax, cs:__security_cookie
0x1800305b1  xor     rax, rsp
0x1800305b4  mov     [rbp+57h+var_18], rax
0x1800305b8  mov     rsi, r8
0x1800305bb  mov     rdi, rdx
0x1800305be  mov     [rbp+57h+var_30], rdx
0x1800305c2  xor     r14d, r14d
0x1800305c5  mov     [rbp+57h+var_48], 1
0x1800305cc  mov     [rbp+57h+var_44], 4Ah ; 'J'
0x1800305d3  lea     rax, aMicrosoftAsgSe_12; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x1800305da  mov     [rbp+57h+var_38], rax
0x1800305de  lea     rax, [rbp+57h+var_48]
0x1800305e2  mov     [rbp+57h+var_50], rax
0x1800305e6  mov     [rbp+57h+var_28], r14
0x1800305ea  mov     dword ptr [rbp+57h+var_78], 1804h
0x1800305f1  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x1800305f8  mov     [rbp+57h+var_70], rax
0x1800305fc  lea     r9, [rbp+57h+var_28]
0x180030600  lea     r8, ??$guid_v@UISemanticImageIndexStoreStatics@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x180030607  lea     rdx, [rbp+57h+var_50]
0x18003060b  lea     rcx, [rbp+57h+var_80]
0x18003060f  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180030614  mov     ecx, dword ptr [rbp+57h+var_80]
0x180030617  test    ecx, ecx
0x180030619  js      loc_180030782
0x18003061f  mov     rbx, [rbp+57h+var_28]
0x180030623  mov     [rbp+57h+var_80], rbx
0x180030627  test    rbx, rbx
0x18003062a  jz      loc_180030700
0x180030630  mov     [rbp+57h+var_30], r14
0x180030634  mov     rax, [rbx]
0x180030637  lea     r8, [rbp+57h+var_30]
0x18003063b  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180030642  mov     rcx, rbx
0x180030645  mov     rax, [rax]
0x180030648  call    cs:__guard_dispatch_icall_fptr
0x18003064e  mov     rax, [rbp+57h+var_30]
0x180030652  mov     [rbp+57h+var_30], rax
0x180030656  test    rax, rax
0x180030659  jz      loc_180030700
0x18003065f  lea     rcx, [rbp+57h+var_30]
0x180030663  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180030668  lea     rax, qword_180086938
0x18003066f  mov     [rbp+57h+var_78], rax
0x180030673  lock inc cs:qword_180086938
0x18003067b  mov     rcx, [rbp+57h+var_28]
0x18003067f  xor     eax, eax
0x180030681  lock cmpxchg cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x18003068a  jnz     short loc_1800306A6
0x18003068c  mov     [rbp+57h+var_80], r14
0x180030690  lea     rdx, stru_180086940; ListEntry
0x180030697  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18003069e  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800306a3  mov     ebx, r14d
0x1800306a6  mov     rax, [rsi]
0x1800306a9  mov     [rbp+57h+var_30], r14
0x1800306ad  mov     dword ptr [rbp+57h+var_28], 2CCh
0x1800306b4  lea     rcx, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x1800306bb  mov     [rbp+57h+var_20], rcx
0x1800306bf  mov     rcx, cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x1800306c6  movups  xmm0, xmmword ptr [rax]
0x1800306c9  movaps  [rbp+57h+var_60], xmm0
0x1800306cd  mov     rax, [rcx]
0x1800306d0  lea     r8, [rbp+57h+var_30]
0x1800306d4  lea     rdx, [rbp+57h+var_60]
0x1800306d8  mov     rax, [rax+68h]
0x1800306dc  call    cs:__guard_dispatch_icall_fptr
0x1800306e2  test    eax, eax
0x1800306e4  js      loc_18003078F
0x1800306ea  mov     rcx, [rbp+57h+var_30]
0x1800306ee  mov     [rdi], rcx
0x1800306f1  lock dec cs:qword_180086938
0x1800306f9  test    rbx, rbx
0x1800306fc  jz      short loc_18003074C
0x1800306fe  jmp     short loc_180030743
0x180030700  mov     rax, [rsi]
0x180030703  mov     [rbp+57h+var_30], r14
0x180030707  mov     dword ptr [rbp+57h+var_78], 2CCh
0x18003070e  lea     rcx, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180030715  mov     [rbp+57h+var_70], rcx
0x180030719  movups  xmm0, xmmword ptr [rax]
0x18003071c  movaps  [rbp+57h+var_60], xmm0
0x180030720  mov     rax, [rbx]
0x180030723  lea     r8, [rbp+57h+var_30]
0x180030727  lea     rdx, [rbp+57h+var_60]
0x18003072b  mov     rcx, rbx
0x18003072e  mov     rax, [rax+68h]
0x180030732  call    cs:__guard_dispatch_icall_fptr
0x180030738  test    eax, eax
0x18003073a  js      short loc_180030773
0x18003073c  mov     rax, [rbp+57h+var_30]
0x180030740  mov     [rdi], rax
0x180030743  lea     rcx, [rbp+57h+var_80]
0x180030747  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003074c  mov     rax, rdi
0x18003074f  mov     rcx, [rbp+57h+var_18]
0x180030753  xor     rcx, rsp; StackCookie
0x180030756  call    __security_check_cookie
0x18003075b  lea     r11, [rsp+0A0h+var_10]
0x180030763  mov     rbx, [r11+20h]
0x180030767  mov     rsi, [r11+30h]
0x18003076b  mov     rsp, r11
0x18003076e  pop     r14
0x180030770  pop     rdi
0x180030771  pop     rbp
0x180030772  retn
0x180030773  lfence
0x180030776  lea     rdx, [rbp+57h+var_78]
0x18003077a  mov     ecx, eax
0x18003077c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180030782  lfence
0x180030785  lea     rdx, [rbp+57h+var_78]
0x180030789  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003078f  lfence
0x180030792  lea     rdx, [rbp+57h+var_28]
0x180030796  mov     ecx, eax
0x180030798  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
