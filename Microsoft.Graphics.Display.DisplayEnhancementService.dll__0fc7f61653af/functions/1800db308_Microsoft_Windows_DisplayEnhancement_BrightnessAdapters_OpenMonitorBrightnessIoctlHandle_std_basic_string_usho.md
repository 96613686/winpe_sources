# Microsoft::Windows::DisplayEnhancement::BrightnessAdapters::OpenMonitorBrightnessIoctlHandle(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800db308`
- end: `0x1800db443`
- name: `?OpenMonitorBrightnessIoctlHandle@BrightnessAdapters@DisplayEnhancement@Windows@Microsoft@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `315`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800dadac`
- `0x1800dbe28`
- `0x1800dbee8`

## callees

- `0x180005860`
- `0x18000fb14`
- `0x180011f7c`
- `0x180013138`
- `0x180013578`
- `0x18007dbdc`
- `0x1800da3c0`
- `0x1800da938`
- `0x1800db308`
- `0x1800dc200`
- `0x1800dc290`
- `0x1800dc560`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db3b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db3b4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800db398`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800db398`

## string_xrefs

- `0x1800db3de`: `onecoreuap\drivers\mobilepc\displayenhancement\service\brightnessadapters\nits\lib\nitsbrightnessadapter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Microsoft::Windows::DisplayEnhancement::BrightnessAdapters::OpenMonitorBrightnessIoctlHandle(
        _QWORD *a1,
        __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  const WCHAR *v7; // rax
  HANDLE FileW; // rax
  signed int LastError; // eax
  unsigned int v10; // ebx
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-D8h]
  _BYTE v13[40]; // [rsp+58h] [rbp-A0h] BYREF
  _BYTE v14[64]; // [rsp+80h] [rbp-78h] BYREF
  _BYTE v15[32]; // [rsp+C0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_BrightnessOpenMonitorHandleTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_BrightnessOpenMonitorHandleTest>>>(v14);
  v4 = std::wstring::wstring(v13, a2);
  Microsoft::Windows::DisplayEnhancement::Foundation::Utils::GetMonitorIoctlDevicePathFromMonitorDevicePath(v15, v4);
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15, v5, v6);
  FileW = CreateFileW(v7, 0xC0000000, 0, 0, 3u, 0x800000u, 0);
  *a1 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetryProvider::WriteOpenMonitorHandleEvent(a2, v10);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\brightnessadapters\\nits\\lib\\nitsbrigh"
                    "tnessadapter.cpp",
      (const char *)v10,
      dwCreationDisposition);
  }
  Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetryProvider::WriteOpenMonitorHandleSucceededEvent();
  tip2::test_watcher<tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_BrightnessOpenMonitorHandleTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_BrightnessOpenMonitorHandleTest>>::complete(v14);
  std::wstring::_Tidy_deallocate(v15);
  tip2::test_watcher<tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_BrightnessOpenMonitorHandleTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_BrightnessOpenMonitorHandleTest>>::~test_watcher<tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_BrightnessOpenMonitorHandleTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_BrightnessOpenMonitorHandleTest>>(v14);
  return a1;
}

```

## disassembly

```asm
0x1800db308  mov     r11, rsp
0x1800db30b  mov     [r11+18h], rbx
0x1800db30f  push    rdi
0x1800db310  sub     rsp, 0F0h
0x1800db317  mov     rax, cs:__security_cookie
0x1800db31e  xor     rax, rsp
0x1800db321  mov     [rsp+0F8h+var_18], rax
0x1800db329  mov     rdi, rdx
0x1800db32c  mov     rbx, rcx
0x1800db32f  mov     [rsp+0F8h+var_B0], rcx
0x1800db334  mov     [rsp+0F8h+var_B8], 0
0x1800db33c  lea     rcx, [r11-78h]
0x1800db340  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_BrightnessOpenMonitorHandleTest@Telemetry@DisplayEnhancement@Windows@Microsoft@@U12345@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x1800db345  nop
0x1800db346  mov     rdx, rdi
0x1800db349  lea     rcx, [rsp+0F8h+var_A0]
0x1800db34e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800db353  mov     rdx, rax
0x1800db356  lea     rcx, [rsp+0F8h+var_38]
0x1800db35e  call    ?GetMonitorIoctlDevicePathFromMonitorDevicePath@Utils@Foundation@DisplayEnhancement@Windows@Microsoft@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V67@@Z; Microsoft::Windows::DisplayEnhancement::Foundation::Utils::GetMonitorIoctlDevicePathFromMonitorDevicePath(std::wstring)
0x1800db363  nop
0x1800db364  lea     rcx, [rsp+0F8h+var_38]
0x1800db36c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800db371  mov     rcx, rax; lpFileName
0x1800db374  mov     [rsp+0F8h+hTemplateFile], 0; hTemplateFile
0x1800db37d  mov     [rsp+0F8h+dwFlagsAndAttributes], 800000h; dwFlagsAndAttributes
0x1800db385  mov     [rsp+0F8h+dwCreationDisposition], 3; int
0x1800db38d  xor     r9d, r9d; lpSecurityAttributes
0x1800db390  xor     r8d, r8d; dwShareMode
0x1800db393  mov     edx, 0C0000000h; dwDesiredAccess
0x1800db398  call    cs:__imp_CreateFileW
0x1800db39e  mov     [rbx], rax
0x1800db3a1  mov     [rsp+0F8h+var_B8], 1
0x1800db3a9  inc     rax
0x1800db3ac  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800db3b2  jnz     short loc_1800DB3F0
0x1800db3b4  call    cs:__imp_GetLastError
0x1800db3ba  mov     ebx, eax
0x1800db3bc  test    eax, eax
0x1800db3be  jle     short loc_1800DB3C9
0x1800db3c0  movzx   ebx, ax
0x1800db3c3  or      ebx, 80070000h
0x1800db3c9  mov     edx, ebx
0x1800db3cb  mov     rcx, rdi
0x1800db3ce  call    ?WriteOpenMonitorHandleEvent@DesTelemetryProvider@Telemetry@DisplayEnhancement@Windows@Microsoft@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@Z; Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetryProvider::WriteOpenMonitorHandleEvent(std::wstring const &,long)
0x1800db3d3  mov     rcx, [rsp+0F8h]; this
0x1800db3db  mov     r9d, ebx; char *
0x1800db3de  lea     r8, aOnecoreuapDriv_1; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800db3e5  mov     edx, 33h ; '3'; void *
0x1800db3ea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800db3f0  call    ?WriteOpenMonitorHandleSucceededEvent@DesTelemetryProvider@Telemetry@DisplayEnhancement@Windows@Microsoft@@SAXXZ; Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetryProvider::WriteOpenMonitorHandleSucceededEvent(void)
0x1800db3f5  lea     rcx, [rsp+0F8h+var_78]
0x1800db3fd  call    ?complete@?$test_watcher@V?$merged_data@U_tip_BrightnessOpenMonitorHandleTest@Telemetry@DisplayEnhancement@Windows@Microsoft@@U12345@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_watcher<tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_BrightnessOpenMonitorHandleTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_BrightnessOpenMonitorHandleTest>>::complete(void)
0x1800db402  nop
0x1800db403  lea     rcx, [rsp+0F8h+var_38]
0x1800db40b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800db410  nop
0x1800db411  lea     rcx, [rsp+0F8h+var_78]
0x1800db419  call    ??1?$test_watcher@V?$merged_data@U_tip_BrightnessOpenMonitorHandleTest@Telemetry@DisplayEnhancement@Windows@Microsoft@@U12345@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_BrightnessOpenMonitorHandleTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_BrightnessOpenMonitorHandleTest>>::~test_watcher<tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_BrightnessOpenMonitorHandleTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_BrightnessOpenMonitorHandleTest>>(void)
0x1800db41e  mov     rax, rbx
0x1800db421  mov     rcx, [rsp+0F8h+var_18]
0x1800db429  xor     rcx, rsp; StackCookie
0x1800db42c  call    __security_check_cookie
0x1800db431  mov     rbx, [rsp+0F8h+arg_10]
0x1800db439  add     rsp, 0F0h
0x1800db440  pop     rdi
0x1800db441  retn
```
