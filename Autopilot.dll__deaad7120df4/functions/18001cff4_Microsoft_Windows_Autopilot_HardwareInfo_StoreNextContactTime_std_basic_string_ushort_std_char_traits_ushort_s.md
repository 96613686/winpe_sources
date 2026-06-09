# Microsoft::Windows::Autopilot::HardwareInfo::StoreNextContactTime(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001cff4`
- end: `0x18001d1b8`
- name: `?StoreNextContactTime@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `452`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18001c448`

## callees

- `0x1800045d0`
- `0x180010764`
- `0x180013580`
- `0x180013de4`
- `0x180013f88`
- `0x180016350`
- `0x180017a20`
- `0x18001982c`
- `0x18001c070`
- `0x18001cff4`
- `0x18001d1c0`
- `0x1800211e8`
- `0x1800218f0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001d0c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001d0c1`

## string_xrefs

- `0x18001d09c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001d177`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::StoreNextContactTime(__int64 a1)
{
  int v2; // eax
  __int64 v3; // rcx
  __int64 v4; // r8
  unsigned int v5; // ebx
  unsigned __int64 v6; // r8
  int v7; // eax
  int v8; // ebx
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  __int128 *v11; // rdx
  __int128 v13; // [rsp+20h] [rbp-29h] BYREF
  __int64 v14; // [rsp+30h] [rbp-19h]
  __int64 v15; // [rsp+38h] [rbp-11h]
  __int128 *v16; // [rsp+40h] [rbp-9h]
  __int128 v17; // [rsp+48h] [rbp-1h] BYREF
  unsigned __int64 v18; // [rsp+58h] [rbp+Fh]
  unsigned __int64 v19; // [rsp+60h] [rbp+17h]
  struct _SYSTEMTIME SystemTime; // [rsp+68h] [rbp+1Fh] BYREF
  _OWORD v21[2]; // [rsp+78h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v17 = 0;
  v18 = 0;
  v19 = 7;
  LOWORD(v17) = 0;
  if ( !*(_QWORD *)(a1 + 16) )
    goto LABEL_8;
  SystemTime = 0;
  v2 = Microsoft::Windows::Autopilot::AutoPilotStateUtils::ISO8601StringToSystemTime((__int64 **)a1, &SystemTime);
  v5 = v2;
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
      v5);
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x310,
      (__int64)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)v5);
  }
  else
  {
    std::wstring::operator=((__int64)&v17, (_QWORD *)a1, v4);
  }
  v6 = v18;
  if ( !v18 )
  {
LABEL_8:
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    v7 = Microsoft::Windows::Autopilot::AutoPilotStateUtils::SystemTimeToISO8601String(&SystemTime, &v17);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = (unsigned int)v7;
      v10 = 792;
      goto LABEL_15;
    }
    v6 = v18;
  }
  v16 = &v13;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v11 = &v17;
  if ( v19 > 7 )
    v11 = (__int128 *)v17;
  std::wstring::_Construct<2,unsigned short const *>((__int64)&v13, v11, v6);
  memset(v21, 0, sizeof(v21));
  std::wstring::_Construct<1,unsigned short const *>(v21, L"NextAllowedContactTime", 0x16u);
  v8 = Microsoft::Windows::Autopilot::HardwareInfo::WriteStringToStorage(
         1,
         (__int64)v21,
         (const unsigned __int16 *)&v13);
  std::wstring::_Tidy_deallocate((char **)v21);
  if ( v8 >= 0 )
  {
    v8 = 0;
    goto LABEL_17;
  }
  v9 = (unsigned int)v8;
  v10 = 795;
LABEL_15:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
    (const char *)v9);
LABEL_17:
  std::wstring::_Tidy_deallocate((char **)&v17);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001cff4  mov     [rsp-8+arg_8], rbx
0x18001cff9  mov     [rsp-8+arg_10], rdi
0x18001cffe  push    rbp
0x18001cfff  lea     rbp, [rsp-57h]
0x18001d004  sub     rsp, 0A0h
0x18001d00b  mov     rax, cs:__security_cookie
0x18001d012  xor     rax, rsp
0x18001d015  mov     [rbp+57h+var_8], rax
0x18001d019  mov     rdi, rcx
0x18001d01c  xorps   xmm0, xmm0
0x18001d01f  movups  [rbp+57h+var_58], xmm0
0x18001d023  mov     [rbp+57h+var_48], 0
0x18001d02b  mov     [rbp+57h+var_40], 7
0x18001d033  xor     eax, eax
0x18001d035  mov     word ptr [rbp+57h+var_58], ax
0x18001d039  cmp     [rcx+10h], rax
0x18001d03d  jz      short loc_18001D0B6
0x18001d03f  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18001d043  lea     rdx, [rbp+57h+SystemTime]
0x18001d047  call    ?ISO8601StringToSystemTime@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_SYSTEMTIME@@@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::ISO8601StringToSystemTime(std::wstring const &,_SYSTEMTIME &)
0x18001d04c  mov     ebx, eax
0x18001d04e  test    eax, eax
0x18001d050  js      short loc_18001D060
0x18001d052  mov     rdx, rdi
0x18001d055  lea     rcx, [rbp+57h+var_58]
0x18001d059  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001d05e  jmp     short loc_18001D0AD
0x18001d060  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x18001d067  jz      short loc_18001D07F
0x18001d069  lea     r9, aConvertcontact; "ConvertContactTime"
0x18001d070  mov     r8d, ebx
0x18001d073  lea     rdx, AutopilotRestorationHardwareProcessRemediationFailure
0x18001d07a  call    McTemplateU0dz_EventWriteTransfer
0x18001d07f  mov     r8d, ebx; int
0x18001d082  lea     rdx, aConvertcontact; "ConvertContactTime"
0x18001d089  lea     rcx, aMicrosoftWindo; "Microsoft::Windows::Autopilot::Hardware"...
0x18001d090  call    ?LogAutopilotTelemetryEvent@HardwareInfo@Autopilot@Windows@Microsoft@@CAXPEBG0J@Z; Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(ushort const *,ushort const *,long)
0x18001d095  mov     rcx, [rbp+5Fh]; this
0x18001d099  mov     r9d, ebx; char *
0x18001d09c  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001d0a3  mov     edx, 310h; void *
0x18001d0a8  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001d0ad  mov     r8, [rbp+57h+var_48]
0x18001d0b1  test    r8, r8
0x18001d0b4  jnz     short loc_18001D0F1
0x18001d0b6  xorps   xmm0, xmm0
0x18001d0b9  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18001d0bd  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18001d0c1  call    cs:__imp_GetSystemTime
0x18001d0c8  nop     dword ptr [rax+rax+00h]
0x18001d0cd  lea     rdx, [rbp+57h+var_58]
0x18001d0d1  lea     rcx, [rbp+57h+SystemTime]
0x18001d0d5  call    ?SystemTimeToISO8601String@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEBU_SYSTEMTIME@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::SystemTimeToISO8601String(_SYSTEMTIME const &,std::wstring &)
0x18001d0da  mov     ebx, eax
0x18001d0dc  test    eax, eax
0x18001d0de  jns     short loc_18001D0ED
0x18001d0e0  mov     r9d, eax
0x18001d0e3  mov     edx, 318h
0x18001d0e8  jmp     loc_18001D177
0x18001d0ed  mov     r8, [rbp+57h+var_48]
0x18001d0f1  lea     rax, [rbp+57h+var_80]
0x18001d0f5  mov     [rbp+57h+var_60], rax
0x18001d0f9  xorps   xmm0, xmm0
0x18001d0fc  movups  [rbp+57h+var_80], xmm0
0x18001d100  mov     [rbp+57h+var_70], 0
0x18001d108  mov     [rbp+57h+var_68], 0
0x18001d110  lea     rdx, [rbp+57h+var_58]
0x18001d114  cmp     [rbp+57h+var_40], 7
0x18001d119  cmova   rdx, qword ptr [rbp+57h+var_58]
0x18001d11e  lea     rcx, [rbp+57h+var_80]
0x18001d122  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x18001d127  nop
0x18001d128  xorps   xmm0, xmm0
0x18001d12b  movups  [rbp+57h+var_28], xmm0
0x18001d12f  xorps   xmm1, xmm1
0x18001d132  movdqu  [rbp+57h+var_18], xmm1
0x18001d137  mov     r8d, 16h
0x18001d13d  lea     rdx, aNextallowedcon; "NextAllowedContactTime"
0x18001d144  lea     rcx, [rbp+57h+var_28]
0x18001d148  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001d14d  nop
0x18001d14e  lea     r8, [rbp+57h+var_80]
0x18001d152  lea     rdx, [rbp+57h+var_28]
0x18001d156  mov     ecx, 1
0x18001d15b  call    ?WriteStringToStorage@HardwareInfo@Autopilot@Windows@Microsoft@@SAJW4StorageMethod@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V67@@Z; Microsoft::Windows::Autopilot::HardwareInfo::WriteStringToStorage(Microsoft::Windows::Autopilot::StorageMethod,std::wstring const &,std::wstring)
0x18001d160  mov     ebx, eax
0x18001d162  lea     rcx, [rbp+57h+var_28]
0x18001d166  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d16b  test    ebx, ebx
0x18001d16d  jns     short loc_18001D189
0x18001d16f  mov     r9d, ebx; char *
0x18001d172  mov     edx, 31Bh; void *
0x18001d177  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001d17e  mov     rcx, [rbp+5Fh]; this
0x18001d182  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d187  jmp     short loc_18001D18B
0x18001d189  xor     ebx, ebx
0x18001d18b  lea     rcx, [rbp+57h+var_58]
0x18001d18f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d194  mov     eax, ebx
0x18001d196  mov     rcx, [rbp+57h+var_8]
0x18001d19a  xor     rcx, rsp; StackCookie
0x18001d19d  call    __security_check_cookie
0x18001d1a2  lea     r11, [rsp+0A0h+var_s0]
0x18001d1aa  mov     rbx, [r11+18h]
0x18001d1ae  mov     rdi, [r11+20h]
0x18001d1b2  mov     rsp, r11
0x18001d1b5  pop     rbp
0x18001d1b6  retn
```
