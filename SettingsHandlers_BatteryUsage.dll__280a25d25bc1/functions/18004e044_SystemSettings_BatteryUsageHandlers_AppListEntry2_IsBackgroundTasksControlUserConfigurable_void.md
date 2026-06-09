# SystemSettings::BatteryUsageHandlers::AppListEntry2::IsBackgroundTasksControlUserConfigurable(void)

- ea: `0x18004e044`
- end: `0x18004e115`
- name: `?IsBackgroundTasksControlUserConfigurable@AppListEntry2@BatteryUsageHandlers@SystemSettings@@AEAA_NXZ`
- size: `209`
- prototype: `bool __fastcall(SystemSettings::BatteryUsageHandlers::AppListEntry2 *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004ce90`
- `0x18004e210`
- `0x18004e2b0`

## callees

- `0x1800028d0`
- `0x180013be0`
- `0x18001e360`
- `0x18001e5c8`
- `0x180023c30`
- `0x180036598`
- `0x180043770`
- `0x180048b00`
- `0x18004e044`
- `0x18004e11c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e0f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e0f7`

## pseudocode

```c
bool __fastcall SystemSettings::BatteryUsageHandlers::AppListEntry2::IsBackgroundTasksControlUserConfigurable(
        SystemSettings::BatteryUsageHandlers::AppListEntry2 *this)
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

  result = SystemSettings::BatteryUsageHandlers::AppListEntry2::IsBackgroundTasksPolicyManageable(this);
  if ( result )
  {
    string = 0;
    v4 = std::wstring::wstring((__int64)v14, (__int64)this + 352, v3);
    PackageFullNameFromFamilyName = SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFullNameFromFamilyName(
                                      (__int64)&SystemSettings::BatteryUsageHandlers::g_UsageDataSingleton2,
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
        (void *)0x37,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
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
0x18004e044  push    rbx
0x18004e046  sub     rsp, 80h
0x18004e04d  mov     rax, cs:__security_cookie
0x18004e054  xor     rax, rsp
0x18004e057  mov     [rsp+88h+var_18], rax
0x18004e05c  mov     rbx, rcx
0x18004e05f  call    ?IsBackgroundTasksPolicyManageable@AppListEntry2@BatteryUsageHandlers@SystemSettings@@AEAA_NXZ; SystemSettings::BatteryUsageHandlers::AppListEntry2::IsBackgroundTasksPolicyManageable(void)
0x18004e064  test    al, al
0x18004e066  jz      loc_18004E0FF
0x18004e06c  mov     [rsp+88h+string], 0; int
0x18004e075  lea     rdx, [rbx+160h]
0x18004e07c  lea     rcx, [rsp+88h+var_58]
0x18004e081  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004e086  mov     r8, rax
0x18004e089  lea     rdx, [rsp+88h+var_38]
0x18004e08e  lea     rcx, ?g_UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@3VUsageDataSingleton2@12@A; SystemSettings::BatteryUsageHandlers::UsageDataSingleton2 SystemSettings::BatteryUsageHandlers::g_UsageDataSingleton2
0x18004e095  call    ?GetPackageFullNameFromFamilyName@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V45@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFullNameFromFamilyName(std::wstring)
0x18004e09a  nop
0x18004e09b  mov     rcx, rax
0x18004e09e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004e0a3  mov     [rsp+88h+var_60], rax
0x18004e0a8  lea     rdx, [rsp+88h+var_60]
0x18004e0ad  lea     rcx, [rsp+88h+string]
0x18004e0b2  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004e0b7  mov     rcx, [rsp+88h]; this
0x18004e0bf  test    eax, eax
0x18004e0c1  jns     short loc_18004E0D8
0x18004e0c3  mov     r9d, eax; char *
0x18004e0c6  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\coresettinghandlers"...
0x18004e0cd  mov     edx, 37h ; '7'; void *
0x18004e0d2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004e0d8  lea     rcx, [rsp+88h+var_38]
0x18004e0dd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004e0e2  mov     rdx, [rsp+88h+string]; HSTRING
0x18004e0e7  call    ?IsAppGPStateLocked@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@QEAAEPEAUHSTRING__@@@Z; SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::IsAppGPStateLocked(HSTRING__ *)
0x18004e0ec  nop
0x18004e0ed  test    al, al
0x18004e0ef  setz    bl
0x18004e0f2  mov     rcx, [rsp+88h+string]; string
0x18004e0f7  call    cs:__imp_WindowsDeleteString
0x18004e0fd  mov     al, bl
0x18004e0ff  mov     rcx, [rsp+88h+var_18]
0x18004e104  xor     rcx, rsp; StackCookie
0x18004e107  call    __security_check_cookie
0x18004e10c  add     rsp, 80h
0x18004e113  pop     rbx
0x18004e114  retn
```
