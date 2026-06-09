# Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::_ResolveAndCacheClassicConditionals(Windows::Foundation::Collections::IVectorView<Platform::String *> *,Concurrency::cancellation_token const &)

- ea: `0x1800c809c`
- end: `0x1800c824e`
- name: `?_ResolveAndCacheClassicConditionals@SettingsFilterCacheManager@Search@ConstraintIndex@Cortana@@AEAAXPE$AAU?$IVectorView@PE$AAVString@Platform@@@Collections@Foundation@Windows@@AEBVcancellation_token@Concurrency@@@Z`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x1800c29e0`

## callees

- `0x1800049e0`
- `0x180005e44`
- `0x18000617a`
- `0x18003fee0`
- `0x18003ff8c`
- `0x180080010`
- `0x1800890e0`
- `0x180092508`
- `0x180093118`
- `0x1800a5168`
- `0x1800aa0cc`
- `0x1800be094`
- `0x1800c0498`
- `0x1800c31e8`
- `0x1800c4b40`
- `0x1800c5c34`
- `0x1800c809c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c81fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c81fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c816b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c816b`

## string_xrefs

- `0x1800c80e8`: `SettingsFilterCacheManager_ValidateClassicConditionals`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::_ResolveAndCacheClassicConditionals(
        struct _RTL_CRITICAL_SECTION *a1,
        HSTRING a2,
        const struct Concurrency::cancellation_token *a3)
{
  HSTRING v4; // rsi
  struct _RTL_CRITICAL_SECTION *v5; // r14
  char v6; // dl
  unsigned int v7; // r12d
  __int64 v8; // rbx
  unsigned int i; // r13d
  HSTRING v10; // rbx
  struct _RTL_CRITICAL_SECTION *v13; // [rsp+20h] [rbp-1C8h]
  _QWORD v14[2]; // [rsp+28h] [rbp-1C0h] BYREF
  _BYTE v15[16]; // [rsp+38h] [rbp-1B0h] BYREF
  __int64 v16; // [rsp+48h] [rbp-1A0h] BYREF
  HSTRING string; // [rsp+50h] [rbp-198h] BYREF
  __int64 v18; // [rsp+58h] [rbp-190h] BYREF
  _QWORD v19[42]; // [rsp+60h] [rbp-188h] BYREF

  v4 = a2;
  v5 = a1;
  string = a2;
  memset_0(v19, 0, sizeof(v19));
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v19);
  v19[0] = &ConstraintIndexTelemetry::SettingsFilterCacheManager_ValidateClassicConditionals::`vftable';
  ConstraintIndexTelemetry::SettingsFilterCacheManager_ValidateClassicConditionals::StartActivity(
    (ConstraintIndexTelemetry::SettingsFilterCacheManager_ValidateClassicConditionals *)v19,
    v6);
  v7 = 0;
  v16 = 0;
  try
  {
    throw_if_canceled(a3);
    v8 = Windows::Cortana::DesktopItem::ValidateClassicSettingConditions(v4);
    v18 = v8;
    __abi_winrt_ptr_assign(&v16, v8);
    __abi_winrt_ptr_dtor(v8);
  }
  catch ( Platform::Exception *v14 )
  {
    LODWORD(v18) = *(_DWORD *)(v14[0] + 64LL);
    v7 = v18;
    v4 = string;
    v5 = a1;
  }
  if ( v16 )
  {
    EnterCriticalSection(v5 + 1);
    v13 = v5 + 1;
    for ( i = 0;
          i < (unsigned int)Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue __gc *>::Size::get(v4);
          ++i )
    {
      v10 = (HSTRING)Windows::Foundation::Collections::IVectorView<Platform::String __gc *>::GetAt(v4, i);
      v14[1] = v10;
      string = (HSTRING)__abi_winrt_ptrto_string_ctor(v10);
      WindowsDeleteString_0(v10);
      LODWORD(v18) = (unsigned __int8)Windows::Foundation::Collections::IVectorView<bool>::GetAt(v16, i);
      std::_Tree<std::_Tmap_traits<Platform::String __gc *,enum Cortana::ConstraintIndex::Search::FilterState,Cortana::ConstraintIndex::Search::StringCaseInsensitiveLess,std::allocator<std::pair<Platform::String __gc * const,enum Cortana::ConstraintIndex::Search::FilterState>>,0>>::emplace<Platform::String __gc * &,enum Cortana::ConstraintIndex::Search::FilterState &>(
        &v5[2].SpinCount,
        v15,
        &string,
        &v18,
        v13);
      WindowsDeleteString_0(string);
    }
    if ( v5 != (struct _RTL_CRITICAL_SECTION *)-40LL )
      LeaveCriticalSection(v5 + 1);
  }
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)v19, v7);
  __abi_winrt_ptr_dtor(v16);
  ConstraintIndexTelemetry::SettingsFilterCacheManager_ValidateClassicConditionals::~SettingsFilterCacheManager_ValidateClassicConditionals((ConstraintIndexTelemetry::SettingsFilterCacheManager_ValidateClassicConditionals *)v19);
}

```

## disassembly

```asm
0x1800c809c  mov     [rsp+arg_18], rbx
0x1800c80a1  push    rsi
0x1800c80a2  push    rdi
0x1800c80a3  push    r12
0x1800c80a5  push    r13
0x1800c80a7  push    r14
0x1800c80a9  sub     rsp, 1C0h
0x1800c80b0  mov     rax, cs:__security_cookie
0x1800c80b7  xor     rax, rsp
0x1800c80ba  mov     [rsp+1E8h+var_38], rax
0x1800c80c2  mov     rbx, r8
0x1800c80c5  mov     rsi, rdx
0x1800c80c8  mov     r14, rcx
0x1800c80cb  mov     [rsp+1E8h+var_1C8], rcx
0x1800c80d0  mov     [rsp+1E8h+string], rdx
0x1800c80d5  xor     edx, edx; Val
0x1800c80d7  mov     r8d, 150h; Size
0x1800c80dd  lea     rcx, [rsp+1E8h+var_188]; void *
0x1800c80e2  call    memset_0
0x1800c80e7  nop
0x1800c80e8  lea     rdx, aSettingsfilter_3; "SettingsFilterCacheManager_ValidateClas"...
0x1800c80ef  lea     rcx, [rsp+1E8h+var_188]; struct wil::details::IFailureCallback *
0x1800c80f4  call    ??0?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800c80f9  lea     rax, ??_7SettingsFilterCacheManager_ValidateClassicConditionals@ConstraintIndexTelemetry@@6B@; const ConstraintIndexTelemetry::SettingsFilterCacheManager_ValidateClassicConditionals::`vftable'
0x1800c8100  mov     [rsp+1E8h+var_188], rax
0x1800c8105  lea     rcx, [rsp+1E8h+var_188]; this
0x1800c810a  call    ?StartActivity@SettingsFilterCacheManager_ValidateClassicConditionals@ConstraintIndexTelemetry@@QEAAX_N@Z; ConstraintIndexTelemetry::SettingsFilterCacheManager_ValidateClassicConditionals::StartActivity(bool)
0x1800c810f  nop
0x1800c8110  xor     r12d, r12d
0x1800c8113  mov     [rsp+1E8h+var_1A0], r12
0x1800c8118  mov     rcx, rbx; struct Concurrency::cancellation_token *
0x1800c811b  call    ?throw_if_canceled@@YAXAEBVcancellation_token@Concurrency@@@Z; throw_if_canceled(Concurrency::cancellation_token const &)
0x1800c8120  mov     rcx, rsi
0x1800c8123  call    ?ValidateClassicSettingConditions@DesktopItem@Cortana@Windows@@SAPE$AAU?$IVectorView@_N@Collections@Foundation@3@PE$AAU?$IVectorView@PE$AAVString@Platform@@@563@@Z; Windows::Cortana::DesktopItem::ValidateClassicSettingConditions(Windows::Foundation::Collections::IVectorView<Platform::String *> *)
0x1800c8128  mov     rbx, rax
0x1800c812b  mov     [rsp+1E8h+var_190], rax
0x1800c8130  mov     rdx, rax
0x1800c8133  lea     rcx, [rsp+1E8h+var_1A0]
0x1800c8138  call    ?__abi_winrt_ptr_assign@@YAPEAXPEAPEAXPE$ADVObject@Platform@@@Z; __abi_winrt_ptr_assign(void * *,Platform::Object const volatile *)
0x1800c813d  nop
0x1800c813e  mov     rcx, rbx
0x1800c8141  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c8146  nop
0x1800c8147  jmp     short loc_1800C8158
0x1800c8149  mov     r12d, dword ptr [rsp+1E8h+var_190]
0x1800c814e  mov     rsi, [rsp+1E8h+string]
0x1800c8153  mov     r14, [rsp+1E8h+var_1C8]
0x1800c8158  cmp     [rsp+1E8h+var_1A0], 0
0x1800c815e  jz      loc_1800C8203
0x1800c8164  lea     rdi, [r14+28h]
0x1800c8168  mov     rcx, rdi; lpCriticalSection
0x1800c816b  call    cs:__imp_EnterCriticalSection
0x1800c8171  mov     [rsp+1E8h+var_1C8], rdi
0x1800c8176  xor     r13d, r13d
0x1800c8179  mov     rcx, rsi
0x1800c817c  call    ?get@Size@?$IVector@PE$AAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@UE$AAAIXZ; Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>::Size::get(void)
0x1800c8181  test    eax, eax
0x1800c8183  jz      short loc_1800C81F5
0x1800c8185  mov     edx, r13d
0x1800c8188  mov     rcx, rsi
0x1800c818b  call    ?GetAt@?$IVectorView@PE$AAVString@Platform@@@Collections@Foundation@Windows@@UE$AAAPE$AAVString@Platform@@I@Z; Windows::Foundation::Collections::IVectorView<Platform::String *>::GetAt(uint)
0x1800c8190  mov     rbx, rax
0x1800c8193  mov     [rsp+1E8h+var_1B8], rax
0x1800c8198  mov     rcx, rax
0x1800c819b  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x1800c81a0  mov     [rsp+1E8h+string], rax
0x1800c81a5  mov     rcx, rbx; string
0x1800c81a8  call    WindowsDeleteString_0
0x1800c81ad  nop
0x1800c81ae  mov     edx, r13d
0x1800c81b1  mov     rcx, [rsp+1E8h+var_1A0]
0x1800c81b6  call    ?GetAt@?$IVectorView@_N@Collections@Foundation@Windows@@UE$AAA_NI@Z; Windows::Foundation::Collections::IVectorView<bool>::GetAt(uint)
0x1800c81bb  movzx   eax, al
0x1800c81be  mov     dword ptr [rsp+1E8h+var_190], eax
0x1800c81c2  lea     r9, [rsp+1E8h+var_190]
0x1800c81c7  lea     r8, [rsp+1E8h+string]
0x1800c81cc  lea     rdx, [rsp+1E8h+var_1B0]
0x1800c81d1  lea     rcx, [r14+70h]
0x1800c81d5  call    ??$emplace@AEAPE$AAVString@Platform@@AEAW4FilterState@Search@ConstraintIndex@Cortana@@@?$_Tree@V?$_Tmap_traits@PE$AAVString@Platform@@W4FilterState@Search@ConstraintIndex@Cortana@@UStringCaseInsensitiveLess@456@V?$allocator@U?$pair@QE$AAVString@Platform@@W4FilterState@Search@ConstraintIndex@Cortana@@@std@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QE$AAVString@Platform@@W4FilterState@Search@ConstraintIndex@Cortana@@@std@@@std@@@std@@@std@@_N@1@AEAPE$AAVString@Platform@@AEAW4FilterState@Search@ConstraintIndex@Cortana@@@Z; std::_Tree<std::_Tmap_traits<Platform::String *,Cortana::ConstraintIndex::Search::FilterState,Cortana::ConstraintIndex::Search::StringCaseInsensitiveLess,std::allocator<std::pair<Platform::String * const,Cortana::ConstraintIndex::Search::FilterState>>,0>>::emplace<Platform::String * &,Cortana::ConstraintIndex::Search::FilterState &>(Platform::String * &,Cortana::ConstraintIndex::Search::FilterState &)
0x1800c81da  nop
0x1800c81db  mov     rcx, [rsp+1E8h+string]; string
0x1800c81e0  call    WindowsDeleteString_0
0x1800c81e5  inc     r13d
0x1800c81e8  mov     rcx, rsi
0x1800c81eb  call    ?get@Size@?$IVector@PE$AAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@UE$AAAIXZ; Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>::Size::get(void)
0x1800c81f0  cmp     r13d, eax
0x1800c81f3  jb      short loc_1800C8185
0x1800c81f5  test    rdi, rdi
0x1800c81f8  jz      short loc_1800C8203
0x1800c81fa  mov     rcx, rdi; lpCriticalSection
0x1800c81fd  call    cs:__imp_LeaveCriticalSection
0x1800c8203  mov     edx, r12d
0x1800c8206  lea     rcx, [rsp+1E8h+var_188]
0x1800c820b  call    ?Stop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800c8210  nop
0x1800c8211  mov     rcx, [rsp+1E8h+var_1A0]
0x1800c8216  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c821b  nop
0x1800c821c  lea     rcx, [rsp+1E8h+var_188]; this
0x1800c8221  call    ??1SettingsFilterCacheManager_ValidateClassicConditionals@ConstraintIndexTelemetry@@QEAA@XZ; ConstraintIndexTelemetry::SettingsFilterCacheManager_ValidateClassicConditionals::~SettingsFilterCacheManager_ValidateClassicConditionals(void)
0x1800c8226  mov     rcx, [rsp+1E8h+var_38]
0x1800c822e  xor     rcx, rsp; StackCookie
0x1800c8231  call    __security_check_cookie
0x1800c8236  mov     rbx, [rsp+1E8h+arg_18]
0x1800c823e  add     rsp, 1C0h
0x1800c8245  pop     r14
0x1800c8247  pop     r13
0x1800c8249  pop     r12
0x1800c824b  pop     rdi
0x1800c824c  pop     rsi
0x1800c824d  retn
```
