# Microsoft::Windows::Autopilot::HardwareInfo::StoreNextContactTime(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001c894`
- end: `0x18001ca51`
- name: `?StoreNextContactTime@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `445`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18001bcf8`

## callees

- `0x1800045b0`
- `0x1800105f4`
- `0x1800132d8`
- `0x180013a40`
- `0x180013be0`
- `0x180015ed0`
- `0x1800174f0`
- `0x180019230`
- `0x18001b938`
- `0x18001c894`
- `0x18001ca58`
- `0x180020810`
- `0x180020ec0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001c961`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001c961`

## string_xrefs

- `0x18001c93c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001ca11`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::StoreNextContactTime(__int64 a1)
{
  int v2; // eax
  __int64 v3; // rcx
  unsigned int v4; // ebx
  int v5; // eax
  int v6; // ebx
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  __int128 v10; // [rsp+20h] [rbp-29h] BYREF
  __int64 v11; // [rsp+30h] [rbp-19h]
  __int64 v12; // [rsp+38h] [rbp-11h]
  __int128 *v13; // [rsp+40h] [rbp-9h]
  __int128 v14; // [rsp+48h] [rbp-1h] BYREF
  __int64 v15; // [rsp+58h] [rbp+Fh]
  __int64 v16; // [rsp+60h] [rbp+17h]
  struct _SYSTEMTIME SystemTime; // [rsp+68h] [rbp+1Fh] BYREF
  _OWORD v18[2]; // [rsp+78h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v14 = 0;
  v15 = 0;
  v16 = 7;
  LOWORD(v14) = 0;
  if ( *(_QWORD *)(a1 + 16) )
  {
    SystemTime = 0;
    v2 = Microsoft::Windows::Autopilot::AutoPilotStateUtils::ISO8601StringToSystemTime(a1, &SystemTime);
    v4 = v2;
    if ( v2 < 0 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
        McTemplateU0dz_EventWriteTransfer(
          v3,
          AutopilotRestorationHardwareProcessRemediationFailure,
          (unsigned int)v2,
          L"ConvertContactTime");
      Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(
        L"Microsoft::Windows::Autopilot::HardwareInfo::StoreNextContactTime",
        L"ConvertContactTime",
        v4);
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x310,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
        (const char *)v4,
        v10);
    }
    else
    {
      std::wstring::operator=(&v14, a1);
    }
    if ( v15 )
      goto LABEL_10;
  }
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  v5 = Microsoft::Windows::Autopilot::AutoPilotStateUtils::SystemTimeToISO8601String(&SystemTime, &v14);
  v6 = v5;
  if ( v5 >= 0 )
  {
LABEL_10:
    v13 = &v10;
    v10 = 0;
    v11 = 0;
    v12 = 0;
    std::wstring::_Construct<2,unsigned short const *>(&v10);
    memset(v18, 0, sizeof(v18));
    std::wstring::_Construct<1,unsigned short const *>(v18, L"NextAllowedContactTime", 22);
    v6 = Microsoft::Windows::Autopilot::HardwareInfo::WriteStringToStorage(
           1,
           (__int64)v18,
           (const unsigned __int16 *)&v10);
    std::wstring::_Tidy_deallocate(v18);
    if ( v6 >= 0 )
    {
      v6 = 0;
      goto LABEL_14;
    }
    v7 = (unsigned int)v6;
    v8 = 795;
  }
  else
  {
    v7 = (unsigned int)v5;
    v8 = 792;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
    (const char *)v7,
    v10);
LABEL_14:
  std::wstring::_Tidy_deallocate(&v14);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001c894  mov     [rsp-8+arg_8], rbx
0x18001c899  mov     [rsp-8+arg_10], rdi
0x18001c89e  push    rbp
0x18001c89f  lea     rbp, [rsp-57h]
0x18001c8a4  sub     rsp, 0A0h
0x18001c8ab  mov     rax, cs:__security_cookie
0x18001c8b2  xor     rax, rsp
0x18001c8b5  mov     [rbp+57h+var_8], rax
0x18001c8b9  mov     rdi, rcx
0x18001c8bc  xorps   xmm0, xmm0
0x18001c8bf  movups  [rbp+57h+var_58], xmm0
0x18001c8c3  mov     [rbp+57h+var_48], 0
0x18001c8cb  mov     [rbp+57h+var_40], 7
0x18001c8d3  xor     eax, eax
0x18001c8d5  mov     word ptr [rbp+57h+var_58], ax
0x18001c8d9  cmp     [rcx+10h], rax
0x18001c8dd  jz      short loc_18001C956
0x18001c8df  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18001c8e3  lea     rdx, [rbp+57h+SystemTime]
0x18001c8e7  call    ?ISO8601StringToSystemTime@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_SYSTEMTIME@@@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::ISO8601StringToSystemTime(std::wstring const &,_SYSTEMTIME &)
0x18001c8ec  mov     ebx, eax
0x18001c8ee  test    eax, eax
0x18001c8f0  js      short loc_18001C900
0x18001c8f2  mov     rdx, rdi
0x18001c8f5  lea     rcx, [rbp+57h+var_58]
0x18001c8f9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001c8fe  jmp     short loc_18001C94D
0x18001c900  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x18001c907  jz      short loc_18001C91F
0x18001c909  lea     r9, aConvertcontact; "ConvertContactTime"
0x18001c910  mov     r8d, ebx
0x18001c913  lea     rdx, AutopilotRestorationHardwareProcessRemediationFailure
0x18001c91a  call    McTemplateU0dz_EventWriteTransfer
0x18001c91f  mov     r8d, ebx; int
0x18001c922  lea     rdx, aConvertcontact; "ConvertContactTime"
0x18001c929  lea     rcx, aMicrosoftWindo; "Microsoft::Windows::Autopilot::Hardware"...
0x18001c930  call    ?LogAutopilotTelemetryEvent@HardwareInfo@Autopilot@Windows@Microsoft@@CAXPEBG0J@Z; Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(ushort const *,ushort const *,long)
0x18001c935  mov     rcx, [rbp+5Fh]; this
0x18001c939  mov     r9d, ebx; char *
0x18001c93c  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001c943  mov     edx, 310h; void *
0x18001c948  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001c94d  mov     r8, [rbp+57h+var_48]
0x18001c951  test    r8, r8
0x18001c954  jnz     short loc_18001C98B
0x18001c956  xorps   xmm0, xmm0
0x18001c959  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18001c95d  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18001c961  call    cs:__imp_GetSystemTime
0x18001c967  lea     rdx, [rbp+57h+var_58]
0x18001c96b  lea     rcx, [rbp+57h+SystemTime]
0x18001c96f  call    ?SystemTimeToISO8601String@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEBU_SYSTEMTIME@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::SystemTimeToISO8601String(_SYSTEMTIME const &,std::wstring &)
0x18001c974  mov     ebx, eax
0x18001c976  test    eax, eax
0x18001c978  jns     short loc_18001C987
0x18001c97a  mov     r9d, eax
0x18001c97d  mov     edx, 318h
0x18001c982  jmp     loc_18001CA11
0x18001c987  mov     r8, [rbp+57h+var_48]
0x18001c98b  lea     rax, [rbp+57h+var_80]
0x18001c98f  mov     [rbp+57h+var_60], rax
0x18001c993  xorps   xmm0, xmm0
0x18001c996  movups  [rbp+57h+var_80], xmm0
0x18001c99a  mov     [rbp+57h+var_70], 0
0x18001c9a2  mov     [rbp+57h+var_68], 0
0x18001c9aa  lea     rdx, [rbp+57h+var_58]
0x18001c9ae  cmp     [rbp+57h+var_40], 7
0x18001c9b3  cmova   rdx, qword ptr [rbp+57h+var_58]
0x18001c9b8  lea     rcx, [rbp+57h+var_80]
0x18001c9bc  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x18001c9c1  nop
0x18001c9c2  xorps   xmm0, xmm0
0x18001c9c5  movups  [rbp+57h+var_28], xmm0
0x18001c9c9  xorps   xmm1, xmm1
0x18001c9cc  movdqu  [rbp+57h+var_18], xmm1
0x18001c9d1  mov     r8d, 16h
0x18001c9d7  lea     rdx, aNextallowedcon; "NextAllowedContactTime"
0x18001c9de  lea     rcx, [rbp+57h+var_28]
0x18001c9e2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001c9e7  nop
0x18001c9e8  lea     r8, [rbp+57h+var_80]
0x18001c9ec  lea     rdx, [rbp+57h+var_28]
0x18001c9f0  mov     ecx, 1
0x18001c9f5  call    ?WriteStringToStorage@HardwareInfo@Autopilot@Windows@Microsoft@@SAJW4StorageMethod@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V67@@Z; Microsoft::Windows::Autopilot::HardwareInfo::WriteStringToStorage(Microsoft::Windows::Autopilot::StorageMethod,std::wstring const &,std::wstring)
0x18001c9fa  mov     ebx, eax
0x18001c9fc  lea     rcx, [rbp+57h+var_28]
0x18001ca00  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ca05  test    ebx, ebx
0x18001ca07  jns     short loc_18001CA23
0x18001ca09  mov     r9d, ebx; char *
0x18001ca0c  mov     edx, 31Bh; void *
0x18001ca11  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001ca18  mov     rcx, [rbp+5Fh]; this
0x18001ca1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ca21  jmp     short loc_18001CA25
0x18001ca23  xor     ebx, ebx
0x18001ca25  lea     rcx, [rbp+57h+var_58]
0x18001ca29  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ca2e  mov     eax, ebx
0x18001ca30  mov     rcx, [rbp+57h+var_8]
0x18001ca34  xor     rcx, rsp; StackCookie
0x18001ca37  call    __security_check_cookie
0x18001ca3c  lea     r11, [rsp+0A0h+var_s0]
0x18001ca44  mov     rbx, [r11+18h]
0x18001ca48  mov     rdi, [r11+20h]
0x18001ca4c  mov     rsp, r11
0x18001ca4f  pop     rbp
0x18001ca50  retn
```
