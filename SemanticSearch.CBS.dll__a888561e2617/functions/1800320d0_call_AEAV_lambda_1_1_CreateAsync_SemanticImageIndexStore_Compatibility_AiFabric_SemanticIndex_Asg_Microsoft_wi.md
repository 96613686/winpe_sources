# ??$call@AEAV_lambda_1_@?1??CreateAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticImageIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticImageIndexStoreOptions@6789Microsoft@2@@Z@@Z

- ea: `0x1800320d0`
- end: `0x1800322cc`
- name: `??$call@AEAV_lambda_1_@?1??CreateAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticImageIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticImageIndexStoreOptions@6789Microsoft@2@@Z@@Z`
- size: `508`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800322d0`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x1800320d0`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x1800321ef`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x180032241`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x180032111`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticImageIndexStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
_QWORD *__fastcall ___call_AEAV_lambda_1___1__CreateAsync_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUSemanticImageIndexStoreOptions_456789__Z____factory_cache_entry_USemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticImageIndexStoreStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateAsync_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUSemanticImageIndexStoreOptions_6789Microsoft_2__Z__Z(
        __int64 a1,
        _QWORD *a2,
        _QWORD **a3)
{
  signed __int64 v5; // rbx
  int v6; // eax
  int v7; // eax
  signed __int64 v9; // [rsp+20h] [rbp-60h] BYREF
  __int64 *v10; // [rsp+28h] [rbp-58h] BYREF
  const char *v11; // [rsp+30h] [rbp-50h]
  _DWORD *v12; // [rsp+40h] [rbp-40h] BYREF
  _DWORD v13[4]; // [rsp+48h] [rbp-38h] BYREF
  const wchar_t *v14; // [rsp+58h] [rbp-28h]
  _QWORD *v15; // [rsp+60h] [rbp-20h] BYREF
  signed __int64 v16[2]; // [rsp+68h] [rbp-18h] BYREF

  v15 = a2;
  v13[0] = 1;
  v13[1] = 74;
  v14 = L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticImageIndexStore";
  v12 = v13;
  v16[0] = 0;
  LODWORD(v10) = 6148;
  v11 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\base.h";
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v9,
    &v12,
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>,
    (__int64)v16);
  if ( (int)v9 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v9, &v10);
  }
  v5 = v16[0];
  v9 = v16[0];
  if ( !v16[0]
    || (v15 = 0,
        (**(void (__fastcall ***)(signed __int64, __int64 *, _QWORD **))v16[0])(
          v16[0],
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v15),
        !v15) )
  {
    v15 = 0;
    LODWORD(v10) = 686;
    v11 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
          "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, _QWORD **))(*(_QWORD *)v5 + 64LL))(v5, **a3, &v15);
    if ( v7 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v7, &v10);
    }
    *a2 = v15;
    goto LABEL_11;
  }
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v15);
  v10 = &qword_180086938;
  _InterlockedIncrement64(&qword_180086938);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>,
          v16[0],
          0) )
  {
    v9 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180086940);
    v5 = 0;
  }
  v15 = 0;
  LODWORD(v16[0]) = 686;
  v16[1] = (signed __int64)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generat"
                           "ed Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
                                                             + 64LL))(
         winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>,
         **a3,
         &v15);
  if ( v6 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v6, v16);
  }
  *a2 = v15;
  _InterlockedDecrement64(&qword_180086938);
  if ( v5 )
LABEL_11:
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v9);
  return a2;
}

```

## disassembly

```asm
0x1800320d0  mov     [rsp-18h+arg_0], rbx
0x1800320d5  mov     [rsp-18h+arg_18], rsi
0x1800320da  push    rbp
0x1800320db  push    rdi
0x1800320dc  push    r14
0x1800320de  mov     rbp, rsp
0x1800320e1  sub     rsp, 80h
0x1800320e8  mov     rax, cs:__security_cookie
0x1800320ef  xor     rax, rsp
0x1800320f2  mov     [rbp+var_8], rax
0x1800320f6  mov     rsi, r8
0x1800320f9  mov     rdi, rdx
0x1800320fc  mov     [rbp+var_20], rdx
0x180032100  xor     r14d, r14d
0x180032103  mov     [rbp+var_38], 1
0x18003210a  mov     [rbp+var_34], 4Ah ; 'J'
0x180032111  lea     rax, aMicrosoftAsgSe_12; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x180032118  mov     [rbp+var_28], rax
0x18003211c  lea     rax, [rbp+var_38]
0x180032120  mov     [rbp+var_40], rax
0x180032124  mov     [rbp+var_18], r14
0x180032128  mov     dword ptr [rbp+var_58], 1804h
0x18003212f  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180032136  mov     [rbp+var_50], rax
0x18003213a  lea     r9, [rbp+var_18]
0x18003213e  lea     r8, ??$guid_v@UISemanticImageIndexStoreStatics@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x180032145  lea     rdx, [rbp+var_40]
0x180032149  lea     rcx, [rbp+var_60]
0x18003214d  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180032152  mov     ecx, dword ptr [rbp+var_60]
0x180032155  test    ecx, ecx
0x180032157  js      loc_1800322B0
0x18003215d  mov     rbx, [rbp+var_18]
0x180032161  mov     [rbp+var_60], rbx
0x180032165  test    rbx, rbx
0x180032168  jz      loc_180032236
0x18003216e  mov     [rbp+var_20], r14
0x180032172  mov     rax, [rbx]
0x180032175  lea     r8, [rbp+var_20]
0x180032179  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180032180  mov     rcx, rbx
0x180032183  mov     rax, [rax]
0x180032186  call    cs:__guard_dispatch_icall_fptr
0x18003218c  mov     rax, [rbp+var_20]
0x180032190  mov     [rbp+var_20], rax
0x180032194  test    rax, rax
0x180032197  jz      loc_180032236
0x18003219d  lea     rcx, [rbp+var_20]
0x1800321a1  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800321a6  lea     rax, qword_180086938
0x1800321ad  mov     [rbp+var_58], rax
0x1800321b1  lock inc cs:qword_180086938
0x1800321b9  mov     rcx, [rbp+var_18]
0x1800321bd  xor     eax, eax
0x1800321bf  lock cmpxchg cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x1800321c8  jnz     short loc_1800321E4
0x1800321ca  mov     [rbp+var_60], r14
0x1800321ce  lea     rdx, stru_180086940; ListEntry
0x1800321d5  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800321dc  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800321e1  mov     ebx, r14d
0x1800321e4  mov     [rbp+var_20], r14
0x1800321e8  mov     dword ptr [rbp+var_18], 2AEh
0x1800321ef  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x1800321f6  mov     [rbp+var_10], rax
0x1800321fa  mov     rcx, cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x180032201  mov     rdx, [rsi]
0x180032204  mov     rax, [rcx]
0x180032207  lea     r8, [rbp+var_20]
0x18003220b  mov     rdx, [rdx]
0x18003220e  mov     rax, [rax+40h]
0x180032212  call    cs:__guard_dispatch_icall_fptr
0x180032218  test    eax, eax
0x18003221a  js      loc_1800322BD
0x180032220  mov     rcx, [rbp+var_20]
0x180032224  mov     [rdi], rcx
0x180032227  lock dec cs:qword_180086938
0x18003222f  test    rbx, rbx
0x180032232  jz      short loc_18003227A
0x180032234  jmp     short loc_180032271
0x180032236  mov     [rbp+var_20], r14
0x18003223a  mov     dword ptr [rbp+var_58], 2AEh
0x180032241  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180032248  mov     [rbp+var_50], rax
0x18003224c  mov     rdx, [rsi]
0x18003224f  mov     rax, [rbx]
0x180032252  lea     r8, [rbp+var_20]
0x180032256  mov     rdx, [rdx]
0x180032259  mov     rcx, rbx
0x18003225c  mov     rax, [rax+40h]
0x180032260  call    cs:__guard_dispatch_icall_fptr
0x180032266  test    eax, eax
0x180032268  js      short loc_1800322A1
0x18003226a  mov     rax, [rbp+var_20]
0x18003226e  mov     [rdi], rax
0x180032271  lea     rcx, [rbp+var_60]
0x180032275  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003227a  mov     rax, rdi
0x18003227d  mov     rcx, [rbp+var_8]
0x180032281  xor     rcx, rsp; StackCookie
0x180032284  call    __security_check_cookie
0x180032289  lea     r11, [rsp+80h+var_s0]
0x180032291  mov     rbx, [r11+20h]
0x180032295  mov     rsi, [r11+38h]
0x180032299  mov     rsp, r11
0x18003229c  pop     r14
0x18003229e  pop     rdi
0x18003229f  pop     rbp
0x1800322a0  retn
0x1800322a1  lfence
0x1800322a4  lea     rdx, [rbp+var_58]
0x1800322a8  mov     ecx, eax
0x1800322aa  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800322b0  lfence
0x1800322b3  lea     rdx, [rbp+var_58]
0x1800322b7  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800322bd  lfence
0x1800322c0  lea     rdx, [rbp+var_18]
0x1800322c4  mov     ecx, eax
0x1800322c6  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
