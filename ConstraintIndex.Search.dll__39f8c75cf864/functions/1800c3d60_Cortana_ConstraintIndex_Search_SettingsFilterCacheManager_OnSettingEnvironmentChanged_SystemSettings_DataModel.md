# Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::OnSettingEnvironmentChanged(SystemSettings::DataModel::ISettingsEnvironmentDatabase *,Platform::String *)

- ea: `0x1800c3d60`
- end: `0x1800c3e61`
- name: `?OnSettingEnvironmentChanged@SettingsFilterCacheManager@Search@ConstraintIndex@Cortana@@AEAAXPE$AAUISettingsEnvironmentDatabase@DataModel@SystemSettings@@PE$AAVString@Platform@@@Z`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800c37c0`

## callees

- `0x1800049e0`
- `0x180005e44`
- `0x180080010`
- `0x1800890e0`
- `0x18009c74c`
- `0x1800bd218`
- `0x1800c0440`
- `0x1800c3d60`
- `0x1800c4990`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3e35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3e35`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c3dc3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c3dc3`

## string_xrefs

- `0x1800c3d94`: `SettingsFilterCacheManager_OnSettingEnvironmentChanged`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::OnSettingEnvironmentChanged(__int64 a1)
{
  char v2; // dl
  _QWORD *v3; // rbx
  _QWORD *v4; // rbx
  _QWORD v5[42]; // [rsp+20h] [rbp-188h] BYREF

  memset_0(v5, 0, sizeof(v5));
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v5);
  v5[0] = &ConstraintIndexTelemetry::SettingsFilterCacheManager_OnSettingEnvironmentChanged::`vftable';
  ConstraintIndexTelemetry::SettingsFilterCacheManager_OnSettingEnvironmentChanged::StartActivity(
    (ConstraintIndexTelemetry::SettingsFilterCacheManager_OnSettingEnvironmentChanged *)v5,
    v2);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  v3 = *(_QWORD **)(a1 + 128);
  std::_Tree_val<std::_Tree_simple_types<std::pair<Platform::String __gc * const,enum Cortana::ConstraintIndex::Search::FilterState>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<Platform::String __gc * const,enum Cortana::ConstraintIndex::Search::FilterState>,void *>>>(
    a1 + 128,
    a1 + 128,
    v3[1]);
  v3[1] = v3;
  *v3 = v3;
  v3[2] = v3;
  *(_QWORD *)(a1 + 136) = 0;
  v4 = *(_QWORD **)(a1 + 144);
  std::_Tree_val<std::_Tree_simple_types<std::pair<Platform::String __gc * const,Cortana::ConstraintIndex::Search::SettingResultItem __gc *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<Platform::String __gc * const,Cortana::ConstraintIndex::Search::SettingResultItem __gc *>,void *>>>(
    a1 + 144,
    a1 + 144,
    v4[1]);
  v4[1] = v4;
  *v4 = v4;
  v4[2] = v4;
  *(_QWORD *)(a1 + 152) = 0;
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)v5, 0);
  if ( a1 != -40 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  ConstraintIndexTelemetry::SettingsFilterCacheManager_OnSettingEnvironmentChanged::~SettingsFilterCacheManager_OnSettingEnvironmentChanged((ConstraintIndexTelemetry::SettingsFilterCacheManager_OnSettingEnvironmentChanged *)v5);
}

```

## disassembly

```asm
0x1800c3d60  push    rbx
0x1800c3d62  push    rbp
0x1800c3d63  push    rsi
0x1800c3d64  push    rdi
0x1800c3d65  sub     rsp, 188h
0x1800c3d6c  mov     rax, cs:__security_cookie
0x1800c3d73  xor     rax, rsp
0x1800c3d76  mov     [rsp+1A8h+var_38], rax
0x1800c3d7e  mov     rsi, rcx
0x1800c3d81  xor     edx, edx; Val
0x1800c3d83  mov     r8d, 150h; Size
0x1800c3d89  lea     rcx, [rsp+1A8h+var_188]; void *
0x1800c3d8e  call    memset_0
0x1800c3d93  nop
0x1800c3d94  lea     rdx, aSettingsfilter_2; "SettingsFilterCacheManager_OnSettingEnv"...
0x1800c3d9b  lea     rcx, [rsp+1A8h+var_188]; struct wil::details::IFailureCallback *
0x1800c3da0  call    ??0?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800c3da5  lea     rax, ??_7SettingsFilterCacheManager_OnSettingEnvironmentChanged@ConstraintIndexTelemetry@@6B@; const ConstraintIndexTelemetry::SettingsFilterCacheManager_OnSettingEnvironmentChanged::`vftable'
0x1800c3dac  mov     [rsp+1A8h+var_188], rax
0x1800c3db1  lea     rcx, [rsp+1A8h+var_188]; this
0x1800c3db6  call    ?StartActivity@SettingsFilterCacheManager_OnSettingEnvironmentChanged@ConstraintIndexTelemetry@@QEAAX_N@Z; ConstraintIndexTelemetry::SettingsFilterCacheManager_OnSettingEnvironmentChanged::StartActivity(bool)
0x1800c3dbb  nop
0x1800c3dbc  lea     rbp, [rsi+28h]
0x1800c3dc0  mov     rcx, rbp; lpCriticalSection
0x1800c3dc3  call    cs:__imp_EnterCriticalSection
0x1800c3dc9  lea     rdi, [rsi+80h]
0x1800c3dd0  mov     rbx, [rdi]
0x1800c3dd3  mov     r8, [rbx+8]
0x1800c3dd7  mov     rdx, rdi
0x1800c3dda  mov     rcx, rdi
0x1800c3ddd  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QE$AAVString@Platform@@W4FilterState@Search@ConstraintIndex@Cortana@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QE$AAVString@Platform@@W4FilterState@Search@ConstraintIndex@Cortana@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QE$AAVString@Platform@@W4FilterState@Search@ConstraintIndex@Cortana@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QE$AAVString@Platform@@W4FilterState@Search@ConstraintIndex@Cortana@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Platform::String * const,Cortana::ConstraintIndex::Search::FilterState>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<Platform::String * const,Cortana::ConstraintIndex::Search::FilterState>,void *>>>(std::allocator<std::_Tree_node<std::pair<Platform::String * const,Cortana::ConstraintIndex::Search::FilterState>,void *>> &,std::_Tree_node<std::pair<Platform::String * const,Cortana::ConstraintIndex::Search::FilterState>,void *> *)
0x1800c3de2  mov     [rbx+8], rbx
0x1800c3de6  mov     [rbx], rbx
0x1800c3de9  mov     [rbx+10h], rbx
0x1800c3ded  mov     qword ptr [rdi+8], 0
0x1800c3df5  lea     rdi, [rsi+90h]
0x1800c3dfc  mov     rbx, [rdi]
0x1800c3dff  mov     r8, [rbx+8]
0x1800c3e03  mov     rdx, rdi
0x1800c3e06  mov     rcx, rdi
0x1800c3e09  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QE$AAVString@Platform@@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QE$AAVString@Platform@@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QE$AAVString@Platform@@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QE$AAVString@Platform@@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Platform::String * const,Cortana::ConstraintIndex::Search::SettingResultItem *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<Platform::String * const,Cortana::ConstraintIndex::Search::SettingResultItem *>,void *>>>(std::allocator<std::_Tree_node<std::pair<Platform::String * const,Cortana::ConstraintIndex::Search::SettingResultItem *>,void *>> &,std::_Tree_node<std::pair<Platform::String * const,Cortana::ConstraintIndex::Search::SettingResultItem *>,void *> *)
0x1800c3e0e  mov     [rbx+8], rbx
0x1800c3e12  mov     [rbx], rbx
0x1800c3e15  mov     [rbx+10h], rbx
0x1800c3e19  mov     qword ptr [rdi+8], 0
0x1800c3e21  xor     edx, edx
0x1800c3e23  lea     rcx, [rsp+1A8h+var_188]
0x1800c3e28  call    ?Stop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800c3e2d  test    rbp, rbp
0x1800c3e30  jz      short loc_1800C3E3B
0x1800c3e32  mov     rcx, rbp; lpCriticalSection
0x1800c3e35  call    cs:__imp_LeaveCriticalSection
0x1800c3e3b  lea     rcx, [rsp+1A8h+var_188]; this
0x1800c3e40  call    ??1SettingsFilterCacheManager_OnSettingEnvironmentChanged@ConstraintIndexTelemetry@@QEAA@XZ; ConstraintIndexTelemetry::SettingsFilterCacheManager_OnSettingEnvironmentChanged::~SettingsFilterCacheManager_OnSettingEnvironmentChanged(void)
0x1800c3e45  mov     rcx, [rsp+1A8h+var_38]
0x1800c3e4d  xor     rcx, rsp; StackCookie
0x1800c3e50  call    __security_check_cookie
0x1800c3e55  add     rsp, 188h
0x1800c3e5c  pop     rdi
0x1800c3e5d  pop     rsi
0x1800c3e5e  pop     rbp
0x1800c3e5f  pop     rbx
0x1800c3e60  retn
```
