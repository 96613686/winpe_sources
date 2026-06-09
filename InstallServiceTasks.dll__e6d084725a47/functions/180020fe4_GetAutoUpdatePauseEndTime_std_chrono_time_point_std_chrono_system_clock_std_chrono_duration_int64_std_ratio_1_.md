# GetAutoUpdatePauseEndTime(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> &)

- ea: `0x180020fe4`
- end: `0x1800211cf`
- name: `?GetAutoUpdatePauseEndTime@@YA_NAEAV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z`
- size: `491`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180020a1c`
- `0x180028c50`

## callees

- `0x180003450`
- `0x18000d370`
- `0x180011544`
- `0x180012118`
- `0x180012f10`
- `0x180014a64`
- `0x18001f5c0`
- `0x180020fe4`
- `0x180028b44`
- `0x180029190`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x1800210fc`
- `msvcp_win!_Xtime_get_ticks` at `0x1800210fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002119d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002119d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800210cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800210cf`

## string_xrefs

- `0x180021024`: `SOFTWARE\Microsoft\Windows\CurrentVersion\InstallService\State`
- `0x180021164`: `SOFTWARE\Microsoft\Windows\CurrentVersion\InstallService\State`
- `0x180021073`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x1800210b9`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x180021153`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18002117c`: `AutoUpdatePauseEndTime`
- `0x180021066`: `GetAutoUpdatePauseEndTime`
- `0x1800210ac`: `GetAutoUpdatePauseEndTime`
- `0x180021146`: `GetAutoUpdatePauseEndTime`
- `0x180021052`: `Detected AutoUpdatePauseEndTime is missing`
- `0x180021098`: `Detected AutoUpdatePauseEndTime is empty`
- `0x180021132`: `Setting AutoUpdatePauseEndTime to: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall GetAutoUpdatePauseEndTime(
        struct Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem *a1)
{
  _QWORD *v1; // rsi
  char v2; // di
  const WCHAR *RegistryLocation; // rax
  __int64 v4; // rcx
  __int64 v5; // r8
  HSTRING v7; // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v9; // rax
  wchar_t *v10; // rax
  const WCHAR *v11; // rax
  __int64 v13; // [rsp+50h] [rbp-68h] BYREF
  HSTRING string; // [rsp+58h] [rbp-60h] BYREF
  _BYTE v15[8]; // [rsp+60h] [rbp-58h] BYREF
  wchar_t Buffer[28]; // [rsp+68h] [rbp-50h] BYREF

  v1 = a1;
  v13 = (__int64)a1;
  v2 = 0;
  if ( ShouldHonorAppUpdatePauseFlow(a1) )
  {
    string = 0;
    RegistryLocation = (const WCHAR *)_InitOnceAndGetRegistryLocation(
                                        &qword_18006A458,
                                        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\InstallService\\State");
    if ( Registry::TryGetValue<Microsoft::WRL::Wrappers::HString>(v4, RegistryLocation, v5, &string) )
    {
      v7 = string;
      if ( string )
      {
        try
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v9 = *(_QWORD *)time_point_iso8601::parse(v15, StringRawBuffer);
        }
        catch ( ... )
        {
          LogSimpleMessage(
            3u,
            "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
            0xF13u,
            "GetAutoUpdatePauseEndTime",
            -1,
            L"Detected AutoUpdatePauseEndTime is invalid",
            0,
            0);
          v2 = 0;
          v1 = (_QWORD *)v13;
          goto LABEL_7;
        }
        *v1 = v9;
        v2 = 1;
        goto LABEL_9;
      }
      LogSimpleMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
        0xF08u,
        "GetAutoUpdatePauseEndTime",
        -1,
        L"Detected AutoUpdatePauseEndTime is empty",
        0,
        0);
    }
    else
    {
      LogSimpleMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
        0xF03u,
        "GetAutoUpdatePauseEndTime",
        -1,
        L"Detected AutoUpdatePauseEndTime is missing",
        0,
        0);
LABEL_7:
      v7 = string;
    }
    v13 = _Xtime_get_ticks() + 30240000000000LL;
    v10 = time_point_iso8601::time_point_iso8601(Buffer, (__int64)&v13);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
      0xF1Bu,
      "GetAutoUpdatePauseEndTime",
      -1,
      L"Setting AutoUpdatePauseEndTime to: %s",
      0,
      0,
      v10);
    v11 = (const WCHAR *)_InitOnceAndGetRegistryLocation(
                           &qword_18006A458,
                           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\InstallService\\State");
    Registry::SetValue<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(
      HKEY_LOCAL_MACHINE,
      v11,
      L"AutoUpdatePauseEndTime");
    *v1 = v13;
LABEL_9:
    WindowsDeleteString(v7);
    return v2;
  }
  return 0;
}

```

## disassembly

```asm
0x180020fe4  mov     [rsp+arg_8], rbx
0x180020fe9  mov     [rsp+arg_10], rsi
0x180020fee  push    rdi
0x180020fef  sub     rsp, 0B0h
0x180020ff6  mov     rax, cs:__security_cookie
0x180020ffd  xor     rax, rsp
0x180021000  mov     [rsp+0B8h+var_18], rax
0x180021008  mov     rsi, rcx
0x18002100b  mov     [rsp+0B8h+var_68], rcx
0x180021010  call    ?ShouldHonorAppUpdatePauseFlow@@YA_NPEAUIAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Z; ShouldHonorAppUpdatePauseFlow(Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem *)
0x180021015  xor     edi, edi
0x180021017  test    al, al
0x180021019  jz      loc_1800211A8
0x18002101f  mov     [rsp+0B8h+string], rdi
0x180021024  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002102b  lea     rcx, qword_18006A458
0x180021032  call    ?_InitOnceAndGetRegistryLocation@@YAPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; _InitOnceAndGetRegistryLocation(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *)
0x180021037  lea     r9, [rsp+0B8h+string]
0x18002103c  mov     rdx, rax
0x18002103f  call    ??$TryGetValue@VHString@Wrappers@WRL@Microsoft@@@Registry@@YA_NPEAUHKEY__@@PEBG1AEAVHString@Wrappers@WRL@Microsoft@@@Z; Registry::TryGetValue<Microsoft::WRL::Wrappers::HString>(HKEY__ *,ushort const *,ushort const *,Microsoft::WRL::Wrappers::HString &)
0x180021044  test    al, al
0x180021046  jnz     short loc_180021084
0x180021048  mov     [rsp+0B8h+var_80], rdi; unsigned __int16 *
0x18002104d  mov     [rsp+0B8h+var_88], rdi; char *
0x180021052  lea     rax, aDetectedAutoup; "Detected AutoUpdatePauseEndTime is miss"...
0x180021059  mov     [rsp+0B8h+var_90], rax; unsigned __int16 *
0x18002105e  mov     [rsp+0B8h+var_98], 0FFFFFFFFh; int
0x180021066  lea     r9, aGetautoupdatep; "GetAutoUpdatePauseEndTime"
0x18002106d  mov     r8d, 0F03h; unsigned int
0x180021073  lea     rdx, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x18002107a  lea     ecx, [rdi+3]; unsigned int
0x18002107d  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x180021082  jmp     short loc_1800210F7
0x180021084  mov     rbx, [rsp+0B8h+string]
0x180021089  test    rbx, rbx
0x18002108c  jnz     short loc_1800210CA
0x18002108e  mov     [rsp+0B8h+var_80], rdi; unsigned __int16 *
0x180021093  mov     [rsp+0B8h+var_88], rdi; char *
0x180021098  lea     rax, aDetectedAutoup_0; "Detected AutoUpdatePauseEndTime is empt"...
0x18002109f  mov     [rsp+0B8h+var_90], rax; unsigned __int16 *
0x1800210a4  mov     [rsp+0B8h+var_98], 0FFFFFFFFh; int
0x1800210ac  lea     r9, aGetautoupdatep; "GetAutoUpdatePauseEndTime"
0x1800210b3  mov     r8d, 0F08h; unsigned int
0x1800210b9  lea     rdx, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x1800210c0  lea     ecx, [rbx+3]; unsigned int
0x1800210c3  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x1800210c8  jmp     short loc_1800210FC
0x1800210ca  xor     edx, edx; length
0x1800210cc  mov     rcx, rbx; string
0x1800210cf  call    cs:__imp_WindowsGetStringRawBuffer
0x1800210d5  mov     rdx, rax
0x1800210d8  lea     rcx, [rsp+0B8h+var_58]
0x1800210dd  call    ?parse@time_point_iso8601@@SA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@PEBG@Z; time_point_iso8601::parse(ushort const *)
0x1800210e2  mov     rax, [rax]
0x1800210e5  mov     [rsi], rax
0x1800210e8  mov     dil, 1
0x1800210eb  jmp     loc_18002119A
0x1800210f0  xor     edi, edi
0x1800210f2  mov     rsi, [rsp+0B8h+var_68]
0x1800210f7  mov     rbx, [rsp+0B8h+string]
0x1800210fc  call    cs:__imp__Xtime_get_ticks
0x180021102  mov     rcx, 1B80CC754000h
0x18002110c  add     rcx, rax
0x18002110f  mov     [rsp+0B8h+var_68], rcx
0x180021114  lea     rdx, [rsp+0B8h+var_68]
0x180021119  lea     rcx, [rsp+0B8h+Buffer]; Buffer
0x18002111e  call    ??0time_point_iso8601@@QEAA@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; time_point_iso8601::time_point_iso8601(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x180021123  mov     [rsp+0B8h+var_78], rax
0x180021128  mov     [rsp+0B8h+var_80], rdi; unsigned __int16 *
0x18002112d  mov     [rsp+0B8h+var_88], rdi; char *
0x180021132  lea     rax, aSettingAutoupd; "Setting AutoUpdatePauseEndTime to: %s"
0x180021139  mov     [rsp+0B8h+var_90], rax; unsigned __int16 *
0x18002113e  mov     [rsp+0B8h+var_98], 0FFFFFFFFh; int
0x180021146  lea     r9, aGetautoupdatep; "GetAutoUpdatePauseEndTime"
0x18002114d  mov     r8d, 0F1Bh; unsigned int
0x180021153  lea     rdx, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x18002115a  mov     ecx, 3; unsigned int
0x18002115f  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180021164  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002116b  lea     rcx, qword_18006A458
0x180021172  call    ?_InitOnceAndGetRegistryLocation@@YAPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; _InitOnceAndGetRegistryLocation(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *)
0x180021177  lea     r9, [rsp+0B8h+var_68]
0x18002117c  lea     r8, ValueName; "AutoUpdatePauseEndTime"
0x180021183  mov     rdx, rax; lpSubKey
0x180021186  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002118d  call    ??$SetValue@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Registry@@YAXPEAUHKEY__@@PEBG1AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; Registry::SetValue<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(HKEY__ *,ushort const *,ushort const *,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x180021192  mov     rcx, [rsp+0B8h+var_68]
0x180021197  mov     [rsi], rcx
0x18002119a  mov     rcx, rbx; string
0x18002119d  call    cs:__imp_WindowsDeleteString
0x1800211a3  mov     al, dil
0x1800211a6  jmp     short loc_1800211AA
0x1800211a8  xor     al, al
0x1800211aa  mov     rcx, [rsp+0B8h+var_18]
0x1800211b2  xor     rcx, rsp; StackCookie
0x1800211b5  call    __security_check_cookie
0x1800211ba  lea     r11, [rsp+0B8h+var_8]
0x1800211c2  mov     rbx, [r11+18h]
0x1800211c6  mov     rsi, [r11+20h]
0x1800211ca  mov     rsp, r11
0x1800211cd  pop     rdi
0x1800211ce  retn
```
