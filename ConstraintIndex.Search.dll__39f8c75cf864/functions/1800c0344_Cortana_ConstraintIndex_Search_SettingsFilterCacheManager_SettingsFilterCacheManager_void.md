# Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::~SettingsFilterCacheManager(void)

- ea: `0x1800c0344`
- end: `0x1800c03e2`
- name: `??1SettingsFilterCacheManager@Search@ConstraintIndex@Cortana@@QEAA@XZ`
- size: `158`
- prototype: `void __fastcall(Cortana::ConstraintIndex::Search::SettingsFilterCacheManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x1800c17d4`

## callees

- `0x18003fee0`
- `0x18008caac`
- `0x18009ad38`
- `0x1800c00d4`
- `0x1800c0104`
- `0x1800c0344`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c03b0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c03b0`

## pseudocode

```c
void __fastcall Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::~SettingsFilterCacheManager(
        struct _RTL_CRITICAL_SECTION *this)
{
  std::_Ref_count_base *v2; // rcx

  if ( this->SpinCount )
    SystemSettings::DataModel::ISettingsEnvironmentDatabase::SettingsEnvironmentChanged::remove(
      this->LockSemaphore,
      this->SpinCount);
  this->SpinCount = 0;
  __abi_winrt_ptr_dtor(*(_QWORD *)&this[4].LockCount);
  std::_Tree<std::_Tmap_traits<Platform::String __gc *,Cortana::ConstraintIndex::Search::SettingPath __gc *,Cortana::ConstraintIndex::Search::StringCaseInsensitiveLess,std::allocator<std::pair<Platform::String __gc * const,Cortana::ConstraintIndex::Search::SettingPath __gc *>>,0>>::~_Tree<std::_Tmap_traits<Platform::String __gc *,Cortana::ConstraintIndex::Search::SettingPath __gc *,Cortana::ConstraintIndex::Search::StringCaseInsensitiveLess,std::allocator<std::pair<Platform::String __gc * const,Cortana::ConstraintIndex::Search::SettingPath __gc *>>,0>>(&this[3].LockSemaphore);
  std::_Tree<std::_Tmap_traits<Platform::String __gc *,enum Cortana::ConstraintIndex::Search::FilterState,Cortana::ConstraintIndex::Search::StringCaseInsensitiveLess,std::allocator<std::pair<Platform::String __gc * const,enum Cortana::ConstraintIndex::Search::FilterState>>,0>>::~_Tree<std::_Tmap_traits<Platform::String __gc *,enum Cortana::ConstraintIndex::Search::FilterState,Cortana::ConstraintIndex::Search::StringCaseInsensitiveLess,std::allocator<std::pair<Platform::String __gc * const,enum Cortana::ConstraintIndex::Search::FilterState>>,0>>(&this[3].LockCount);
  std::_Tree<std::_Tmap_traits<Platform::String __gc *,enum Cortana::ConstraintIndex::Search::FilterState,Cortana::ConstraintIndex::Search::StringCaseInsensitiveLess,std::allocator<std::pair<Platform::String __gc * const,enum Cortana::ConstraintIndex::Search::FilterState>>,0>>::~_Tree<std::_Tmap_traits<Platform::String __gc *,enum Cortana::ConstraintIndex::Search::FilterState,Cortana::ConstraintIndex::Search::StringCaseInsensitiveLess,std::allocator<std::pair<Platform::String __gc * const,enum Cortana::ConstraintIndex::Search::FilterState>>,0>>(&this[2].SpinCount);
  __abi_winrt_ptr_dtor(this[2].LockSemaphore);
  __abi_winrt_ptr_dtor(*(_QWORD *)&this[2].LockCount);
  DeleteCriticalSection(this + 1);
  __abi_winrt_ptr_dtor(this->LockSemaphore);
  __abi_winrt_ptr_dtor(this->OwningThread);
  v2 = *(std::_Ref_count_base **)&this->LockCount;
  if ( v2 )
    std::_Ref_count_base::_Decwref(v2);
}

```

## disassembly

```asm
0x1800c0344  mov     [rsp+arg_0], rbx
0x1800c0349  push    rdi
0x1800c034a  sub     rsp, 20h
0x1800c034e  mov     rbx, rcx
0x1800c0351  cmp     qword ptr [rcx+20h], 0
0x1800c0356  jz      short loc_1800C0365
0x1800c0358  mov     rdx, [rcx+20h]
0x1800c035c  mov     rcx, [rcx+18h]
0x1800c0360  call    ?remove@SettingsEnvironmentChanged@ISettingsEnvironmentDatabase@DataModel@SystemSettings@@UE$AAAXVEventRegistrationToken@Foundation@Windows@@@Z; SystemSettings::DataModel::ISettingsEnvironmentDatabase::SettingsEnvironmentChanged::remove(Windows::Foundation::EventRegistrationToken)
0x1800c0365  mov     qword ptr [rbx+20h], 0
0x1800c036d  mov     rcx, [rbx+0A8h]
0x1800c0374  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c0379  lea     rcx, [rbx+90h]
0x1800c0380  call    ??1?$_Tree@V?$_Tmap_traits@PE$AAVString@Platform@@PE$AAUSettingPath@Search@ConstraintIndex@Cortana@@UStringCaseInsensitiveLess@456@V?$allocator@U?$pair@QE$AAVString@Platform@@PE$AAUSettingPath@Search@ConstraintIndex@Cortana@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<Platform::String *,Cortana::ConstraintIndex::Search::SettingPath *,Cortana::ConstraintIndex::Search::StringCaseInsensitiveLess,std::allocator<std::pair<Platform::String * const,Cortana::ConstraintIndex::Search::SettingPath *>>,0>>::~_Tree<std::_Tmap_traits<Platform::String *,Cortana::ConstraintIndex::Search::SettingPath *,Cortana::ConstraintIndex::Search::StringCaseInsensitiveLess,std::allocator<std::pair<Platform::String * const,Cortana::ConstraintIndex::Search::SettingPath *>>,0>>(void)
0x1800c0385  lea     rcx, [rbx+80h]
0x1800c038c  call    ??1?$_Tree@V?$_Tmap_traits@PE$AAVString@Platform@@W4FilterState@Search@ConstraintIndex@Cortana@@UStringCaseInsensitiveLess@456@V?$allocator@U?$pair@QE$AAVString@Platform@@W4FilterState@Search@ConstraintIndex@Cortana@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<Platform::String *,Cortana::ConstraintIndex::Search::FilterState,Cortana::ConstraintIndex::Search::StringCaseInsensitiveLess,std::allocator<std::pair<Platform::String * const,Cortana::ConstraintIndex::Search::FilterState>>,0>>::~_Tree<std::_Tmap_traits<Platform::String *,Cortana::ConstraintIndex::Search::FilterState,Cortana::ConstraintIndex::Search::StringCaseInsensitiveLess,std::allocator<std::pair<Platform::String * const,Cortana::ConstraintIndex::Search::FilterState>>,0>>(void)
0x1800c0391  lea     rcx, [rbx+70h]
0x1800c0395  call    ??1?$_Tree@V?$_Tmap_traits@PE$AAVString@Platform@@W4FilterState@Search@ConstraintIndex@Cortana@@UStringCaseInsensitiveLess@456@V?$allocator@U?$pair@QE$AAVString@Platform@@W4FilterState@Search@ConstraintIndex@Cortana@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<Platform::String *,Cortana::ConstraintIndex::Search::FilterState,Cortana::ConstraintIndex::Search::StringCaseInsensitiveLess,std::allocator<std::pair<Platform::String * const,Cortana::ConstraintIndex::Search::FilterState>>,0>>::~_Tree<std::_Tmap_traits<Platform::String *,Cortana::ConstraintIndex::Search::FilterState,Cortana::ConstraintIndex::Search::StringCaseInsensitiveLess,std::allocator<std::pair<Platform::String * const,Cortana::ConstraintIndex::Search::FilterState>>,0>>(void)
0x1800c039a  mov     rcx, [rbx+68h]
0x1800c039e  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c03a3  mov     rcx, [rbx+58h]
0x1800c03a7  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c03ac  lea     rcx, [rbx+28h]; lpCriticalSection
0x1800c03b0  call    cs:__imp_DeleteCriticalSection
0x1800c03b6  mov     rcx, [rbx+18h]
0x1800c03ba  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c03bf  mov     rcx, [rbx+10h]
0x1800c03c3  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c03c8  mov     rcx, [rbx+8]; this
0x1800c03cc  test    rcx, rcx
0x1800c03cf  jz      short loc_1800C03D7
0x1800c03d1  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800c03d6  nop
0x1800c03d7  mov     rbx, [rsp+28h+arg_0]
0x1800c03dc  add     rsp, 20h
0x1800c03e0  pop     rdi
0x1800c03e1  retn
```
