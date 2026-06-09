# SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::DoGetValueAsyncWork(void)

- ea: `0x1800bbc40`
- end: `0x1800bbd0c`
- name: `?DoGetValueAsyncWork@CAppStorageUsageSetting@StorageSenseHandlers@SystemSettings@@UEAAXXZ`
- size: `204`
- prototype: `void __fastcall(SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000ad60`
- `0x18001fc0c`
- `0x1800bbc40`
- `0x1800bd74c`
- `0x1800bdc38`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800bbc6d`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800bbc6d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bbcf0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bbcf0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bbc96`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bbc96`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::DoGetValueAsyncWork(
        struct _RTL_CRITICAL_SECTION *this)
{
  PTP_WORK ThreadpoolWork; // rax
  const unsigned __int16 *v3; // rdx
  struct _TP_WORK *DebugInfo; // rcx
  unsigned __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  this[6].SpinCount = 0;
  this[7].DebugInfo = 0;
  v5 = (unsigned __int64)&this[8] & -(__int64)TryEnterCriticalSection(this + 8);
  if ( v5 )
  {
    ThreadpoolWork = CreateThreadpoolWork(
                       SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::AsyncStartWorkCallback,
                       this,
                       0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
      &this[9],
      ThreadpoolWork);
    DebugInfo = (struct _TP_WORK *)this[9].DebugInfo;
    if ( DebugInfo )
    {
      SubmitThreadpoolWork(DebugInfo);
    }
    else
    {
      SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::UpdateAppUsage(
        (SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting *)this,
        v3);
      this[7].LockCount = 0;
      SystemSettings::DataModel::CSettingBase::OnValueChanged(
        (SystemSettings::DataModel::CSettingBase *)this,
        (const unsigned __int16 *)&stru_18011ABD0);
      SystemSettings::DataModel::CSettingBase::OnValueChanged(
        (SystemSettings::DataModel::CSettingBase *)this,
        (const unsigned __int16 *)&stru_18011ABE8);
      SystemSettings::DataModel::CSettingBase::OnValueChanged(
        (SystemSettings::DataModel::CSettingBase *)this,
        (const unsigned __int16 *)&stru_18011AC00);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v5);
}

```

## disassembly

```asm
0x1800bbc40  mov     [rsp+arg_8], rbx
0x1800bbc45  push    rdi
0x1800bbc46  sub     rsp, 20h
0x1800bbc4a  mov     rdi, rcx
0x1800bbc4d  mov     qword ptr [rcx+110h], 0
0x1800bbc58  mov     qword ptr [rcx+118h], 0
0x1800bbc63  lea     rbx, [rcx+140h]
0x1800bbc6a  mov     rcx, rbx; lpCriticalSection
0x1800bbc6d  call    cs:__imp_TryEnterCriticalSection
0x1800bbc73  neg     eax
0x1800bbc75  sbb     rdx, rdx
0x1800bbc78  and     rdx, rbx
0x1800bbc7b  mov     [rsp+28h+arg_0], rdx
0x1800bbc80  jz      short loc_1800BBCF7
0x1800bbc82  lea     rbx, [rdi+168h]
0x1800bbc89  xor     r8d, r8d; pcbe
0x1800bbc8c  mov     rdx, rdi; pv
0x1800bbc8f  lea     rcx, ?AsyncStartWorkCallback@CAppStorageUsageSetting@StorageSenseHandlers@SystemSettings@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800bbc96  call    cs:__imp_CreateThreadpoolWork
0x1800bbc9c  mov     rdx, rax
0x1800bbc9f  mov     rcx, rbx
0x1800bbca2  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x1800bbca7  mov     rcx, [rbx]; pwk
0x1800bbcaa  test    rcx, rcx
0x1800bbcad  jnz     short loc_1800BBCF0
0x1800bbcaf  mov     rcx, rdi; this
0x1800bbcb2  call    ?UpdateAppUsage@CAppStorageUsageSetting@StorageSenseHandlers@SystemSettings@@AEAAJXZ; SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::UpdateAppUsage(void)
0x1800bbcb7  mov     dword ptr [rdi+120h], 0
0x1800bbcc1  lea     rdx, stru_18011ABD0; unsigned __int16 *
0x1800bbcc8  mov     rcx, rdi; this
0x1800bbccb  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x1800bbcd0  lea     rdx, stru_18011ABE8; unsigned __int16 *
0x1800bbcd7  mov     rcx, rdi; this
0x1800bbcda  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x1800bbcdf  lea     rdx, stru_18011AC00; unsigned __int16 *
0x1800bbce6  mov     rcx, rdi; this
0x1800bbce9  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x1800bbcee  jmp     short loc_1800BBCF7
0x1800bbcf0  call    cs:__imp_SubmitThreadpoolWork
0x1800bbcf6  nop
0x1800bbcf7  lea     rcx, [rsp+28h+arg_0]
0x1800bbcfc  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800bbd01  mov     rbx, [rsp+28h+arg_8]
0x1800bbd06  add     rsp, 20h
0x1800bbd0a  pop     rdi
0x1800bbd0b  retn
```
