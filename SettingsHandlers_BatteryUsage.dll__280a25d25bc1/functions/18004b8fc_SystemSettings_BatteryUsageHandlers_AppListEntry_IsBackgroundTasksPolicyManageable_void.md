# SystemSettings::BatteryUsageHandlers::AppListEntry::IsBackgroundTasksPolicyManageable(void)

- ea: `0x18004b8fc`
- end: `0x18004b9ea`
- name: `?IsBackgroundTasksPolicyManageable@AppListEntry@BatteryUsageHandlers@SystemSettings@@AEAA_NXZ`
- size: `238`
- prototype: `bool __fastcall(SystemSettings::BatteryUsageHandlers::AppListEntry *__hidden this)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004a814`
- `0x18004aab0`
- `0x18004b824`
- `0x18004b9f0`

## callees

- `0x1800028d0`
- `0x180013be0`
- `0x18001e360`
- `0x18001e5c8`
- `0x180023c30`
- `0x180036598`
- `0x180043908`
- `0x1800483dc`
- `0x18004b8fc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b9c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b9c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall SystemSettings::BatteryUsageHandlers::AppListEntry::IsBackgroundTasksPolicyManageable(
        SystemSettings::BatteryUsageHandlers::AppListEntry *this,
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
  PackageFullNameFromFamilyName = SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFullNameFromFamilyName(
                                    (__int64)&SystemSettings::BatteryUsageHandlers::g_UsageDataSingleton,
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
      (void *)0x21,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
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
      (void *)0x27,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
      (const char *)(unsigned int)AppBackgroundCapable,
      v13[0]);
  v12 = v13[0] != 0;
  WindowsDeleteString(string);
  return v12;
}

```

## disassembly

```asm
0x18004b8fc  mov     [rsp-8+arg_8], rbx
0x18004b901  push    rbp
0x18004b902  mov     rbp, rsp
0x18004b905  sub     rsp, 80h
0x18004b90c  mov     rax, cs:__security_cookie
0x18004b913  xor     rax, rsp
0x18004b916  mov     [rbp+var_10], rax
0x18004b91a  lea     rdx, [rcx+160h]
0x18004b921  cmp     dword ptr [rdx+20h], 1
0x18004b925  jz      short loc_18004B92E
0x18004b927  xor     al, al
0x18004b929  jmp     loc_18004B9CD
0x18004b92e  xor     ebx, ebx
0x18004b930  mov     [rbp+string], rbx
0x18004b934  lea     rcx, [rbp+var_50]
0x18004b938  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004b93d  mov     r8, rax
0x18004b940  lea     rdx, [rbp+var_30]
0x18004b944  lea     rcx, ?g_UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@3VUsageDataSingleton@12@A; SystemSettings::BatteryUsageHandlers::UsageDataSingleton SystemSettings::BatteryUsageHandlers::g_UsageDataSingleton
0x18004b94b  call    ?GetPackageFullNameFromFamilyName@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V45@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFullNameFromFamilyName(std::wstring)
0x18004b950  nop
0x18004b951  mov     rcx, rax
0x18004b954  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004b959  mov     qword ptr [rbp+var_60], rax
0x18004b95d  lea     rdx, [rbp+var_60]
0x18004b961  lea     rcx, [rbp+string]
0x18004b965  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004b96a  mov     rcx, [rbp+8]; this
0x18004b96e  test    eax, eax
0x18004b970  jns     short loc_18004B985
0x18004b972  mov     r9d, eax; char *
0x18004b975  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\coresettinghandlers"...
0x18004b97c  lea     edx, [rbx+21h]; void *
0x18004b97f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004b985  lea     rcx, [rbp+var_30]
0x18004b989  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004b98e  mov     [rbp+var_60], ebx
0x18004b991  lea     r8, [rbp+var_60]; int *
0x18004b995  mov     rdx, [rbp+string]; HSTRING
0x18004b999  call    ?GetAppBackgroundCapable@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@QEAAJPEAUHSTRING__@@PEAH@Z; SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetAppBackgroundCapable(HSTRING__ *,int *)
0x18004b99e  mov     rcx, [rbp+8]; this
0x18004b9a2  test    eax, eax
0x18004b9a4  jns     short loc_18004B9BB
0x18004b9a6  mov     r9d, eax; char *
0x18004b9a9  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\coresettinghandlers"...
0x18004b9b0  mov     edx, 27h ; '''; void *
0x18004b9b5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004b9bb  cmp     [rbp+var_60], ebx
0x18004b9be  setnz   bl
0x18004b9c1  mov     rcx, [rbp+string]; string
0x18004b9c5  call    cs:__imp_WindowsDeleteString
0x18004b9cb  mov     al, bl
0x18004b9cd  mov     rcx, [rbp+var_10]
0x18004b9d1  xor     rcx, rsp; StackCookie
0x18004b9d4  call    __security_check_cookie
0x18004b9d9  mov     rbx, [rsp+80h+arg_8]
0x18004b9e1  add     rsp, 80h
0x18004b9e8  pop     rbp
0x18004b9e9  retn
```
