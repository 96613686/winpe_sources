# SystemSettings::BatteryUsageHandlers::VideoQualityControl::SetValue(Windows::Foundation::IPropertyValue *)

- ea: `0x180036f90`
- end: `0x180037108`
- name: `?SetValue@VideoQualityControl@BatteryUsageHandlers@SystemSettings@@MEAAJPEAUIPropertyValue@Foundation@Windows@@@Z`
- size: `376`
- prototype: `__int64 __fastcall(SystemSettings::BatteryUsageHandlers::VideoQualityControl *__hidden this, struct Windows::Foundation::IPropertyValue *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800028d0`
- `0x18000a13c`
- `0x18000e8e8`
- `0x1800228bc`
- `0x18002c520`
- `0x180036f90`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800370bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800370eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800370bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800370eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036fc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800370a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800370d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036fc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800370a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800370d4`
- `POWRPROF!PowerGetActiveScheme` at `0x180037042`
- `POWRPROF!PowerGetActiveScheme` at `0x180037042`
- `POWRPROF!PowerWriteDCValueIndex` at `0x18003707b`
- `POWRPROF!PowerWriteDCValueIndex` at `0x18003707b`
- `POWRPROF!PowerSetActiveScheme` at `0x180037094`
- `POWRPROF!PowerSetActiveScheme` at `0x180037094`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::BatteryUsageHandlers::VideoQualityControl::SetValue(
        SystemSettings::BatteryUsageHandlers::VideoQualityControl *this,
        struct Windows::Foundation::IPropertyValue *a2)
{
  __int64 (__fastcall *v3)(struct Windows::Foundation::IPropertyValue *, HSTRING *); // rbx
  int v4; // eax
  signed int ActiveScheme; // ebx
  HSTRING v6; // r8
  int v7; // edi
  signed int active; // eax
  bool v9; // cc
  GUID *v10; // rcx
  GUID *v12; // rcx
  bool v13; // zf
  DWORD DcValueIndex; // [rsp+20h] [rbp-58h]
  HSTRING string; // [rsp+30h] [rbp-48h] BYREF
  GUID *SchemeGuid; // [rsp+38h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-38h] BYREF
  HSTRING v18; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  SchemeGuid = 0;
  string = 0;
  v3 = *(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, HSTRING *))(*(_QWORD *)a2 + 152LL);
  WindowsDeleteString(0);
  string = 0;
  v4 = v3(a2, &string);
  ActiveScheme = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\videoqualitycontrol.cpp",
      (const char *)(unsigned int)v4,
      DcValueIndex);
LABEL_15:
    WindowsDeleteString(string);
    string = 0;
    v12 = SchemeGuid;
    v13 = SchemeGuid == 0;
    SchemeGuid = 0;
    if ( !v13 )
      LocalFree(v12);
    return (unsigned int)ActiveScheme;
  }
  v18 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"SystemSettings_BatterySaver_VideoQuality_Video",
    0x2Fu,
    0x2Eu);
  v7 = Microsoft::WRL::Wrappers::Details::CompareStringOrdinal((Microsoft::WRL::Wrappers::Details *)string, v18, v6);
  hstringHeader.Reserved.Reserved1 = &SchemeGuid;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
  hstringHeader.Reserved.Reserved2[16] = 1;
  ActiveScheme = PowerGetActiveScheme(0, (GUID **)&hstringHeader.Reserved.Reserved2[8]);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&hstringHeader);
  if ( ActiveScheme )
  {
    if ( ActiveScheme <= 0 )
      goto LABEL_15;
    ActiveScheme = (unsigned __int16)ActiveScheme;
    goto LABEL_14;
  }
  if ( !SchemeGuid )
    goto LABEL_15;
  active = PowerWriteDCValueIndex(0, SchemeGuid, &GUID_MULTIMEDIA_SUBGROUP, &GUID_VIDEO_PLAYBACK_QUALITY_BIAS, v7 == 0);
  ActiveScheme = active;
  v9 = active <= 0;
  if ( active || (active = PowerSetActiveScheme(0, SchemeGuid), ActiveScheme = active, v9 = active <= 0, active) )
  {
    if ( v9 )
      goto LABEL_15;
    ActiveScheme = (unsigned __int16)active;
LABEL_14:
    ActiveScheme |= 0x80070000;
    goto LABEL_15;
  }
  WindowsDeleteString(string);
  string = 0;
  v10 = SchemeGuid;
  SchemeGuid = 0;
  if ( v10 )
    LocalFree(v10);
  return 0;
}

```

## disassembly

```asm
0x180036f90  push    rbp
0x180036f92  push    rbx
0x180036f93  push    rsi
0x180036f94  push    rdi
0x180036f95  mov     rbp, rsp
0x180036f98  sub     rsp, 78h
0x180036f9c  mov     rax, cs:__security_cookie
0x180036fa3  xor     rax, rsp
0x180036fa6  mov     [rbp+var_18], rax
0x180036faa  mov     rdi, rdx
0x180036fad  xor     esi, esi
0x180036faf  mov     [rbp+SchemeGuid], rsi
0x180036fb3  mov     [rbp+string], rsi
0x180036fb7  mov     rax, [rdx]
0x180036fba  mov     rbx, [rax+98h]
0x180036fc1  xor     ecx, ecx; string
0x180036fc3  call    cs:__imp_WindowsDeleteString
0x180036fc9  mov     [rbp+string], rsi
0x180036fcd  lea     rdx, [rbp+string]
0x180036fd1  mov     rcx, rdi
0x180036fd4  mov     rax, rbx
0x180036fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036fdc  mov     ebx, eax
0x180036fde  test    eax, eax
0x180036fe0  jns     short loc_180036FFF
0x180036fe2  mov     rcx, [rbp+20h]; this
0x180036fe6  mov     r9d, eax; char *
0x180036fe9  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\coresettinghandlers"...
0x180036ff0  mov     edx, 92h; void *
0x180036ff5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036ffa  jmp     loc_1800370D0
0x180036fff  mov     [rbp+var_20], rsi
0x180037003  mov     r9d, 2Eh ; '.'; unsigned int
0x180037009  lea     r8d, [r9+1]; unsigned int
0x18003700d  lea     rdx, aSystemsettings_19; "SystemSettings_BatterySaver_VideoQualit"...
0x180037014  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180037018  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003701d  mov     rdx, [rbp+var_20]; HSTRING
0x180037021  mov     rcx, [rbp+string]; this
0x180037025  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18003702a  mov     edi, eax
0x18003702c  lea     rax, [rbp+SchemeGuid]
0x180037030  mov     qword ptr [rbp+hstringHeader.Reserved], rax
0x180037034  mov     qword ptr [rbp+hstringHeader.Reserved+8], rsi
0x180037038  mov     byte ptr [rbp+hstringHeader.Reserved+10h], 1
0x18003703c  lea     rdx, [rbp+hstringHeader.Reserved+8]; ActivePolicyGuid
0x180037040  xor     ecx, ecx; UserRootPowerKey
0x180037042  call    cs:__imp_PowerGetActiveScheme
0x180037048  mov     ebx, eax
0x18003704a  lea     rcx, [rbp+hstringHeader]
0x18003704e  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180037053  test    ebx, ebx
0x180037055  jnz     short loc_1800370C5
0x180037057  mov     rdx, [rbp+SchemeGuid]; SchemeGuid
0x18003705b  test    rdx, rdx
0x18003705e  jz      short loc_1800370D0
0x180037060  mov     eax, esi
0x180037062  test    edi, edi
0x180037064  setz    al
0x180037067  mov     [rsp+78h+DcValueIndex], eax; DcValueIndex
0x18003706b  lea     r9, GUID_VIDEO_PLAYBACK_QUALITY_BIAS; PowerSettingGuid
0x180037072  lea     r8, GUID_MULTIMEDIA_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180037079  xor     ecx, ecx; RootPowerKey
0x18003707b  call    cs:__imp_PowerWriteDCValueIndex
0x180037081  mov     ebx, eax
0x180037083  test    eax, eax
0x180037085  jz      short loc_18003708E
0x180037087  jle     short loc_1800370D0
0x180037089  movzx   ebx, ax
0x18003708c  jmp     short loc_1800370CA
0x18003708e  mov     rdx, [rbp+SchemeGuid]; SchemeGuid
0x180037092  xor     ecx, ecx; UserRootPowerKey
0x180037094  call    cs:__imp_PowerSetActiveScheme
0x18003709a  mov     ebx, eax
0x18003709c  test    eax, eax
0x18003709e  jnz     short loc_180037087
0x1800370a0  mov     rcx, [rbp+string]; string
0x1800370a4  call    cs:__imp_WindowsDeleteString
0x1800370aa  mov     [rbp+string], rsi
0x1800370ae  mov     rcx, [rbp+SchemeGuid]; hMem
0x1800370b2  mov     [rbp+SchemeGuid], rsi
0x1800370b6  test    rcx, rcx
0x1800370b9  jz      short loc_1800370C1
0x1800370bb  call    cs:__imp_LocalFree
0x1800370c1  xor     eax, eax
0x1800370c3  jmp     short loc_1800370F3
0x1800370c5  jle     short loc_1800370D0
0x1800370c7  movzx   ebx, bx
0x1800370ca  or      ebx, 80070000h
0x1800370d0  mov     rcx, [rbp+string]; string
0x1800370d4  call    cs:__imp_WindowsDeleteString
0x1800370da  mov     [rbp+string], rsi
0x1800370de  mov     rcx, [rbp+SchemeGuid]; hMem
0x1800370e2  test    rcx, rcx
0x1800370e5  mov     [rbp+SchemeGuid], rsi
0x1800370e9  jz      short loc_1800370F1
0x1800370eb  call    cs:__imp_LocalFree
0x1800370f1  mov     eax, ebx
0x1800370f3  mov     rcx, [rbp+var_18]
0x1800370f7  xor     rcx, rsp; StackCookie
0x1800370fa  call    __security_check_cookie
0x1800370ff  add     rsp, 78h
0x180037103  pop     rdi
0x180037104  pop     rsi
0x180037105  pop     rbx
0x180037106  pop     rbp
0x180037107  retn
```
