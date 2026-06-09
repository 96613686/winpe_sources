# SystemSettings::BatteryUsageHandlers::AppListEntry::IsBackgroundTasksControlUserConfigurable(void)

- ea: `0x18004b824`
- end: `0x18004b8f5`
- name: `?IsBackgroundTasksControlUserConfigurable@AppListEntry@BatteryUsageHandlers@SystemSettings@@AEAA_NXZ`
- size: `209`
- prototype: `bool __fastcall(SystemSettings::BatteryUsageHandlers::AppListEntry *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004aab0`
- `0x18004b9f0`
- `0x18004bcb0`

## callees

- `0x1800028d0`
- `0x180013be0`
- `0x18001e360`
- `0x18001e5c8`
- `0x180023c30`
- `0x180036598`
- `0x180043908`
- `0x180048b00`
- `0x18004b824`
- `0x18004b8fc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b8d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b8d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall SystemSettings::BatteryUsageHandlers::AppListEntry::IsBackgroundTasksControlUserConfigurable(
        SystemSettings::BatteryUsageHandlers::AppListEntry *this)
{
  bool result; // al
  __int64 v3; // r8
  __int64 v4; // rax
  __int64 PackageFullNameFromFamilyName; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  char v8; // r8
  int v9; // eax
  SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *v10; // rcx
  bool v11; // bl
  HSTRING string; // [rsp+20h] [rbp-68h] BYREF
  __int64 v13; // [rsp+28h] [rbp-60h] BYREF
  _BYTE v14[32]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v15[32]; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  result = SystemSettings::BatteryUsageHandlers::AppListEntry::IsBackgroundTasksPolicyManageable(this);
  if ( result )
  {
    string = 0;
    v4 = std::wstring::wstring((__int64)v14, (__int64)this + 352, v3);
    PackageFullNameFromFamilyName = SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFullNameFromFamilyName(
                                      (__int64)&SystemSettings::BatteryUsageHandlers::g_UsageDataSingleton,
                                      (__int64)v15,
                                      v4);
    v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(PackageFullNameFromFamilyName, v6, v7);
    v9 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(
           (Microsoft::WRL::Wrappers::HString *)&string,
           &v13,
           v8);
    if ( v9 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
        (const char *)(unsigned int)v9,
        (int)string);
    std::wstring::_Tidy_deallocate(v15);
    v11 = !SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::IsAppGPStateLocked(v10, string);
    WindowsDeleteString(string);
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x18004b824  push    rbx
0x18004b826  sub     rsp, 80h
0x18004b82d  mov     rax, cs:__security_cookie
0x18004b834  xor     rax, rsp
0x18004b837  mov     [rsp+88h+var_18], rax
0x18004b83c  mov     rbx, rcx
0x18004b83f  call    ?IsBackgroundTasksPolicyManageable@AppListEntry@BatteryUsageHandlers@SystemSettings@@AEAA_NXZ; SystemSettings::BatteryUsageHandlers::AppListEntry::IsBackgroundTasksPolicyManageable(void)
0x18004b844  test    al, al
0x18004b846  jz      loc_18004B8DF
0x18004b84c  mov     [rsp+88h+string], 0; int
0x18004b855  lea     rdx, [rbx+160h]
0x18004b85c  lea     rcx, [rsp+88h+var_58]
0x18004b861  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004b866  mov     r8, rax
0x18004b869  lea     rdx, [rsp+88h+var_38]
0x18004b86e  lea     rcx, ?g_UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@3VUsageDataSingleton@12@A; SystemSettings::BatteryUsageHandlers::UsageDataSingleton SystemSettings::BatteryUsageHandlers::g_UsageDataSingleton
0x18004b875  call    ?GetPackageFullNameFromFamilyName@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V45@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFullNameFromFamilyName(std::wstring)
0x18004b87a  nop
0x18004b87b  mov     rcx, rax
0x18004b87e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004b883  mov     [rsp+88h+var_60], rax
0x18004b888  lea     rdx, [rsp+88h+var_60]
0x18004b88d  lea     rcx, [rsp+88h+string]
0x18004b892  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004b897  mov     rcx, [rsp+88h]; this
0x18004b89f  test    eax, eax
0x18004b8a1  jns     short loc_18004B8B8
0x18004b8a3  mov     r9d, eax; char *
0x18004b8a6  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\coresettinghandlers"...
0x18004b8ad  mov     edx, 35h ; '5'; void *
0x18004b8b2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004b8b8  lea     rcx, [rsp+88h+var_38]
0x18004b8bd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004b8c2  mov     rdx, [rsp+88h+string]; HSTRING
0x18004b8c7  call    ?IsAppGPStateLocked@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@QEAAEPEAUHSTRING__@@@Z; SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::IsAppGPStateLocked(HSTRING__ *)
0x18004b8cc  nop
0x18004b8cd  test    al, al
0x18004b8cf  setz    bl
0x18004b8d2  mov     rcx, [rsp+88h+string]; string
0x18004b8d7  call    cs:__imp_WindowsDeleteString
0x18004b8dd  mov     al, bl
0x18004b8df  mov     rcx, [rsp+88h+var_18]
0x18004b8e4  xor     rcx, rsp; StackCookie
0x18004b8e7  call    __security_check_cookie
0x18004b8ec  add     rsp, 80h
0x18004b8f3  pop     rbx
0x18004b8f4  retn
```
