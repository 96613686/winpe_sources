# SystemSettings::PenSettings::DevicesPenSetDesktopAppBase::SetPathToDesktopApp(Microsoft::WRL::ComPtr<Windows::Storage::IStorageFile> &)

- ea: `0x18002f4e8`
- end: `0x18002f732`
- name: `?SetPathToDesktopApp@DevicesPenSetDesktopAppBase@PenSettings@SystemSettings@@AEAAJAEAV?$ComPtr@UIStorageFile@Storage@Windows@@@WRL@Microsoft@@@Z`
- size: `586`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CSettingBase *this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002ba80`

## callees

- `0x180005f0c`
- `0x180008128`
- `0x18000a2bc`
- `0x18001033c`
- `0x180016d6c`
- `0x180019b90`
- `0x18001b5b0`
- `0x180027dcc`
- `0x18002f030`
- `0x18002f4e8`
- `0x18004c10c`
- `0x18004c334`
- `0x18004c494`
- `0x18004fe28`
- `0x180052e6c`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002f639`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002f639`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f59a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f5f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f685`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f6b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f6e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f59a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f5f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f685`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f6b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f6e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f549`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f589`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f707`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f549`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f589`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f707`

## string_xrefs

- `0x18002f601`: `CustomAppPath`
- `0x18002f51e`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x18002f578`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::PenSettings::DevicesPenSetDesktopAppBase::SetPathToDesktopApp(
        SystemSettings::DataModel::CSettingBase *this,
        __int64 a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, HSTRING *); // rbx
  int v7; // eax
  __int64 v8; // rdx
  PCWSTR StringRawBuffer; // rax
  const unsigned __int16 *v10; // rax
  HKEY v11; // rcx
  int v12; // eax
  PCWSTR v13; // rax
  PCWSTR v14; // rax
  PCWSTR v15; // rax
  int v17; // [rsp+20h] [rbp-40h]
  unsigned __int16 *v18; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v19[40]; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  HSTRING string; // [rsp+90h] [rbp+30h] BYREF
  __int64 v22; // [rsp+98h] [rbp+38h] BYREF

  v22 = 0;
  v3 = Microsoft::WRL::ComPtr<Windows::Storage::IStorageFile>::As<Windows::Storage::IStorageItem>(a2, &v22);
  v4 = v3;
  if ( v3 >= 0 )
  {
    string = 0;
    v5 = v22;
    v6 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v22 + 96LL);
    WindowsDeleteString(0);
    string = 0;
    v7 = v6(v5, &string);
    v4 = v7;
    if ( v7 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
             (char *)this + 248,
             StringRawBuffer,
             -1);
      v4 = v7;
      if ( v7 >= 0 )
      {
        v18 = 0;
        SystemSettings::PenSettings::ActionTypeOptionManager::GetPrimitiveSpecificParameters(
          *((_DWORD *)this + 68),
          (unsigned int)&v18,
          0,
          0,
          0,
          0);
        v10 = WindowsGetStringRawBuffer(string, 0);
        v7 = SHRegSetString(v11, v18, L"CustomAppPath", v10);
        v4 = v7;
        if ( v7 >= 0 )
        {
          SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionValueCache(
            *((unsigned int *)this + 68),
            *((_QWORD *)this + 31));
          AcquireSRWLockShared(&SystemSettings::PenSettings::PenSettingsCacheSingleton::m_penSettingsCacheLock);
          v18 = (unsigned __int16 *)&SystemSettings::PenSettings::PenSettingsCacheSingleton::m_penSettingsCacheLock;
          PenSettingsTelemetry::LogPenSettingsTelemetry(
            L"UserOverrideSetting",
            *((unsigned int *)this + 68),
            &SystemSettings::PenSettings::PenSettingsCacheSingleton::m_penSettingsCache);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v18);
          SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180067C70);
          v12 = *((_DWORD *)this + 68);
          switch ( v12 )
          {
            case 1:
              v13 = WindowsGetStringRawBuffer(string, 0);
              std::wstring::wstring(v19, v13);
              CloudDataPenSettings::SaveSingleClickShortcutAppAsync((SystemSettings::DataModel::CSettingBase *)((char *)this + 280));
              break;
            case 2:
              v14 = WindowsGetStringRawBuffer(string, 0);
              std::wstring::wstring(v19, v14);
              CloudDataPenSettings::SaveDoubleClickShortcutAppAsync((SystemSettings::DataModel::CSettingBase *)((char *)this + 280));
              break;
            case 3:
              v15 = WindowsGetStringRawBuffer(string, 0);
              std::wstring::wstring(v19, v15);
              CloudDataPenSettings::SaveLongPressShortcutAppAsync((SystemSettings::DataModel::CSettingBase *)((char *)this + 280));
              break;
          }
          WindowsDeleteString(string);
          v4 = 0;
          goto LABEL_17;
        }
        v8 = 2434;
      }
      else
      {
        v8 = 2429;
      }
    }
    else
    {
      v8 = 2428;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
      (const char *)(unsigned int)v7,
      v17);
    WindowsDeleteString(string);
LABEL_17:
    string = 0;
    goto LABEL_18;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x978,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
    (const char *)(unsigned int)v3,
    v17);
LABEL_18:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  return v4;
}

```

## disassembly

```asm
0x18002f4e8  mov     [rsp-18h+arg_0], rbx
0x18002f4ed  push    rbp
0x18002f4ee  push    rsi
0x18002f4ef  push    rdi
0x18002f4f0  mov     rbp, rsp
0x18002f4f3  sub     rsp, 60h
0x18002f4f7  mov     rax, rdx
0x18002f4fa  mov     rsi, rcx
0x18002f4fd  mov     [rbp+arg_18], 0
0x18002f505  lea     rdx, [rbp+arg_18]
0x18002f509  mov     rcx, rax
0x18002f50c  call    ??$As@UIStorageItem@Storage@Windows@@@?$ComPtr@UIStorageFile@Storage@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIStorageItem@Storage@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Storage::IStorageFile>::As<Windows::Storage::IStorageItem>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::IStorageItem>>)
0x18002f511  mov     ebx, eax
0x18002f513  test    eax, eax
0x18002f515  jns     short loc_18002F534
0x18002f517  mov     rcx, [rbp+18h]; this
0x18002f51b  mov     r9d, eax; char *
0x18002f51e  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x18002f525  mov     edx, 978h; void *
0x18002f52a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f52f  jmp     loc_18002F717
0x18002f534  mov     [rbp+string], 0
0x18002f53c  mov     rdi, [rbp+arg_18]
0x18002f540  mov     rax, [rdi]
0x18002f543  mov     rbx, [rax+60h]
0x18002f547  xor     ecx, ecx; string
0x18002f549  call    cs:__imp_WindowsDeleteString
0x18002f54f  mov     [rbp+string], 0
0x18002f557  lea     rdx, [rbp+string]
0x18002f55b  mov     rcx, rdi
0x18002f55e  mov     rax, rbx
0x18002f561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f566  mov     ebx, eax
0x18002f568  test    eax, eax
0x18002f56a  jns     short loc_18002F594
0x18002f56c  mov     edx, 97Ch; void *
0x18002f571  mov     rcx, [rbp+18h]; this
0x18002f575  mov     r9d, eax; char *
0x18002f578  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x18002f57f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f584  nop
0x18002f585  mov     rcx, [rbp+string]; string
0x18002f589  call    cs:__imp_WindowsDeleteString
0x18002f58f  jmp     loc_18002F70F
0x18002f594  xor     edx, edx; length
0x18002f596  mov     rcx, [rbp+string]; string
0x18002f59a  call    cs:__imp_WindowsGetStringRawBuffer
0x18002f5a0  lea     rdi, [rsi+0F8h]
0x18002f5a7  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002f5ab  mov     rdx, rax
0x18002f5ae  mov     rcx, rdi
0x18002f5b1  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18002f5b6  mov     ebx, eax
0x18002f5b8  test    eax, eax
0x18002f5ba  jns     short loc_18002F5C3
0x18002f5bc  mov     edx, 97Dh
0x18002f5c1  jmp     short loc_18002F571
0x18002f5c3  mov     [rbp+var_30], 0
0x18002f5cb  mov     [rsp+60h+var_38], 0
0x18002f5d4  mov     [rsp+60h+var_40], 0
0x18002f5dd  xor     r9d, r9d
0x18002f5e0  xor     r8d, r8d
0x18002f5e3  lea     rdx, [rbp+var_30]
0x18002f5e7  mov     ecx, [rsi+110h]
0x18002f5ed  call    ?GetPrimitiveSpecificParameters@ActionTypeOptionManager@PenSettings@SystemSettings@@SAXW4PenClickType@@PEAPEBG1PEAPEAV?$vector@UPenActionTypeResourceMapping_@PenSettings@SystemSettings@@V?$allocator@UPenActionTypeResourceMapping_@PenSettings@SystemSettings@@@std@@@std@@11@Z; SystemSettings::PenSettings::ActionTypeOptionManager::GetPrimitiveSpecificParameters(PenClickType,ushort const * *,ushort const * *,std::vector<SystemSettings::PenSettings::PenActionTypeResourceMapping_> * *,ushort const * *,ushort const * *)
0x18002f5f2  xor     edx, edx; length
0x18002f5f4  mov     rcx, [rbp+string]; string
0x18002f5f8  call    cs:__imp_WindowsGetStringRawBuffer
0x18002f5fe  mov     r9, rax; unsigned __int16 *
0x18002f601  lea     r8, aCustomapppath; "CustomAppPath"
0x18002f608  mov     rdx, [rbp+var_30]; unsigned __int16 *
0x18002f60c  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18002f611  mov     ebx, eax
0x18002f613  test    eax, eax
0x18002f615  jns     short loc_18002F621
0x18002f617  mov     edx, 982h
0x18002f61c  jmp     loc_18002F571
0x18002f621  mov     rdx, [rdi]
0x18002f624  mov     ecx, [rsi+110h]
0x18002f62a  call    ?UpdateActionValueCache@PenSettingsCacheSingleton@PenSettings@SystemSettings@@SAXW4PenClickType@@PEBG@Z; SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionValueCache(PenClickType,ushort const *)
0x18002f62f  lea     rbx, ?m_penSettingsCacheLock@PenSettingsCacheSingleton@PenSettings@SystemSettings@@0Vsrwlock@wil@@A; wil::srwlock SystemSettings::PenSettings::PenSettingsCacheSingleton::m_penSettingsCacheLock
0x18002f636  mov     rcx, rbx; SRWLock
0x18002f639  call    cs:__imp_AcquireSRWLockShared
0x18002f63f  mov     [rbp+var_30], rbx
0x18002f643  lea     r8, ?m_penSettingsCache@PenSettingsCacheSingleton@PenSettings@SystemSettings@@0UPenSettingsCache@23@A; SystemSettings::PenSettings::PenSettingsCache SystemSettings::PenSettings::PenSettingsCacheSingleton::m_penSettingsCache
0x18002f64a  mov     edx, [rsi+110h]
0x18002f650  lea     rcx, aUseroverridese; "UserOverrideSetting"
0x18002f657  call    ?LogPenSettingsTelemetry@PenSettingsTelemetry@@SAXPEBGW4PenClickType@@AEAUPenSettingsCache@PenSettings@SystemSettings@@@Z; PenSettingsTelemetry::LogPenSettingsTelemetry(ushort const *,PenClickType,SystemSettings::PenSettings::PenSettingsCache &)
0x18002f65c  lea     rcx, [rbp+var_30]
0x18002f660  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002f665  lea     rdx, stru_180067C70; unsigned __int16 *
0x18002f66c  mov     rcx, rsi; this
0x18002f66f  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18002f674  mov     eax, [rsi+110h]
0x18002f67a  cmp     eax, 1
0x18002f67d  jnz     short loc_18002F6A8
0x18002f67f  xor     edx, edx; length
0x18002f681  mov     rcx, [rbp+string]; string
0x18002f685  call    cs:__imp_WindowsGetStringRawBuffer
0x18002f68b  mov     rdx, rax
0x18002f68e  lea     rcx, [rbp+var_28]
0x18002f692  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002f697  lea     rcx, [rsi+118h]; struct wil::cloud_store *
0x18002f69e  mov     rdx, rax
0x18002f6a1  call    ?SaveSingleClickShortcutAppAsync@CloudDataPenSettings@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CloudDataPenSettings::SaveSingleClickShortcutAppAsync(std::wstring)
0x18002f6a6  jmp     short loc_18002F703
0x18002f6a8  cmp     eax, 2
0x18002f6ab  jnz     short loc_18002F6D6
0x18002f6ad  xor     edx, edx; length
0x18002f6af  mov     rcx, [rbp+string]; string
0x18002f6b3  call    cs:__imp_WindowsGetStringRawBuffer
0x18002f6b9  mov     rdx, rax
0x18002f6bc  lea     rcx, [rbp+var_28]
0x18002f6c0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002f6c5  lea     rcx, [rsi+118h]; struct wil::cloud_store *
0x18002f6cc  mov     rdx, rax
0x18002f6cf  call    ?SaveDoubleClickShortcutAppAsync@CloudDataPenSettings@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CloudDataPenSettings::SaveDoubleClickShortcutAppAsync(std::wstring)
0x18002f6d4  jmp     short loc_18002F703
0x18002f6d6  cmp     eax, 3
0x18002f6d9  jnz     short loc_18002F703
0x18002f6db  xor     edx, edx; length
0x18002f6dd  mov     rcx, [rbp+string]; string
0x18002f6e1  call    cs:__imp_WindowsGetStringRawBuffer
0x18002f6e7  mov     rdx, rax
0x18002f6ea  lea     rcx, [rbp+var_28]
0x18002f6ee  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002f6f3  lea     rcx, [rsi+118h]; struct wil::cloud_store *
0x18002f6fa  mov     rdx, rax
0x18002f6fd  call    ?SaveLongPressShortcutAppAsync@CloudDataPenSettings@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CloudDataPenSettings::SaveLongPressShortcutAppAsync(std::wstring)
0x18002f702  nop
0x18002f703  mov     rcx, [rbp+string]; string
0x18002f707  call    cs:__imp_WindowsDeleteString
0x18002f70d  xor     ebx, ebx
0x18002f70f  mov     [rbp+string], 0
0x18002f717  lea     rcx, [rbp+arg_18]
0x18002f71b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002f720  mov     eax, ebx
0x18002f722  mov     rbx, [rsp+60h+arg_0]
0x18002f72a  add     rsp, 60h
0x18002f72e  pop     rdi
0x18002f72f  pop     rsi
0x18002f730  pop     rbp
0x18002f731  retn
```
