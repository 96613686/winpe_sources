# SystemSettings::BatteryUsageHandlers::AppListEntry2::IsBackgroundTasksPolicyManageable(void)

- ea: `0x18004e11c`
- end: `0x18004e20a`
- name: `?IsBackgroundTasksPolicyManageable@AppListEntry2@BatteryUsageHandlers@SystemSettings@@AEAA_NXZ`
- size: `238`
- prototype: `bool __fastcall(SystemSettings::BatteryUsageHandlers::AppListEntry2 *__hidden this)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004cccc`
- `0x18004ce90`
- `0x18004e044`
- `0x18004e210`

## callees

- `0x1800028d0`
- `0x180013be0`
- `0x18001e360`
- `0x18001e5c8`
- `0x180023c30`
- `0x180036598`
- `0x180043770`
- `0x1800483dc`
- `0x18004e11c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e1e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e1e5`

## pseudocode

```c
bool __fastcall SystemSettings::BatteryUsageHandlers::AppListEntry2::IsBackgroundTasksPolicyManageable(
        SystemSettings::BatteryUsageHandlers::AppListEntry2 *this,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rax
  __int64 PackageFullNameFromFamilyName; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  char v8; // r8
  int v9; // eax
  SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *v10; // rcx
  int AppBackgroundCapable; // eax
  bool v12; // bl
  int v13[2]; // [rsp+20h] [rbp-60h] BYREF
  HSTRING string; // [rsp+28h] [rbp-58h] BYREF
  _BYTE v15[32]; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v16[32]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  if ( *((_DWORD *)this + 96) != 1 )
    return 0;
  string = 0;
  v4 = std::wstring::wstring((__int64)v15, (__int64)this + 352, a3);
  PackageFullNameFromFamilyName = SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFullNameFromFamilyName(
                                    (__int64)&SystemSettings::BatteryUsageHandlers::g_UsageDataSingleton2,
                                    (__int64)v16,
                                    v4);
  *(_QWORD *)v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(PackageFullNameFromFamilyName, v6, v7);
  v9 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(
         (Microsoft::WRL::Wrappers::HString *)&string,
         (__int64 *)v13,
         v8);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
      (const char *)(unsigned int)v9,
      v13[0]);
  std::wstring::_Tidy_deallocate(v16);
  v13[0] = 0;
  AppBackgroundCapable = SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetAppBackgroundCapable(
                           v10,
                           string,
                           v13);
  if ( AppBackgroundCapable < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
      (const char *)(unsigned int)AppBackgroundCapable,
      v13[0]);
  v12 = v13[0] != 0;
  WindowsDeleteString(string);
  return v12;
}

```

## disassembly

```asm
0x18004e11c  mov     [rsp-8+arg_8], rbx
0x18004e121  push    rbp
0x18004e122  mov     rbp, rsp
0x18004e125  sub     rsp, 80h
0x18004e12c  mov     rax, cs:__security_cookie
0x18004e133  xor     rax, rsp
0x18004e136  mov     [rbp+var_10], rax
0x18004e13a  lea     rdx, [rcx+160h]
0x18004e141  cmp     dword ptr [rdx+20h], 1
0x18004e145  jz      short loc_18004E14E
0x18004e147  xor     al, al
0x18004e149  jmp     loc_18004E1ED
0x18004e14e  xor     ebx, ebx
0x18004e150  mov     [rbp+string], rbx
0x18004e154  lea     rcx, [rbp+var_50]
0x18004e158  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004e15d  mov     r8, rax
0x18004e160  lea     rdx, [rbp+var_30]
0x18004e164  lea     rcx, ?g_UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@3VUsageDataSingleton2@12@A; SystemSettings::BatteryUsageHandlers::UsageDataSingleton2 SystemSettings::BatteryUsageHandlers::g_UsageDataSingleton2
0x18004e16b  call    ?GetPackageFullNameFromFamilyName@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V45@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFullNameFromFamilyName(std::wstring)
0x18004e170  nop
0x18004e171  mov     rcx, rax
0x18004e174  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004e179  mov     qword ptr [rbp+var_60], rax
0x18004e17d  lea     rdx, [rbp+var_60]
0x18004e181  lea     rcx, [rbp+string]
0x18004e185  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004e18a  mov     rcx, [rbp+8]; this
0x18004e18e  test    eax, eax
0x18004e190  jns     short loc_18004E1A5
0x18004e192  mov     r9d, eax; char *
0x18004e195  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\coresettinghandlers"...
0x18004e19c  lea     edx, [rbx+23h]; void *
0x18004e19f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004e1a5  lea     rcx, [rbp+var_30]
0x18004e1a9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004e1ae  mov     [rbp+var_60], ebx
0x18004e1b1  lea     r8, [rbp+var_60]; int *
0x18004e1b5  mov     rdx, [rbp+string]; HSTRING
0x18004e1b9  call    ?GetAppBackgroundCapable@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@QEAAJPEAUHSTRING__@@PEAH@Z; SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetAppBackgroundCapable(HSTRING__ *,int *)
0x18004e1be  mov     rcx, [rbp+8]; this
0x18004e1c2  test    eax, eax
0x18004e1c4  jns     short loc_18004E1DB
0x18004e1c6  mov     r9d, eax; char *
0x18004e1c9  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\coresettinghandlers"...
0x18004e1d0  mov     edx, 29h ; ')'; void *
0x18004e1d5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004e1db  cmp     [rbp+var_60], ebx
0x18004e1de  setnz   bl
0x18004e1e1  mov     rcx, [rbp+string]; string
0x18004e1e5  call    cs:__imp_WindowsDeleteString
0x18004e1eb  mov     al, bl
0x18004e1ed  mov     rcx, [rbp+var_10]
0x18004e1f1  xor     rcx, rsp; StackCookie
0x18004e1f4  call    __security_check_cookie
0x18004e1f9  mov     rbx, [rsp+80h+arg_8]
0x18004e201  add     rsp, 80h
0x18004e208  pop     rbp
0x18004e209  retn
```
