# CDeviceDirectoryClientHandler::ProcessRegisterPhone(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,void *)

- ea: `0x180004214`
- end: `0x1800042b8`
- name: `?ProcessRegisterPhone@CDeviceDirectoryClientHandler@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `164`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004640`

## callees

- `0x180003974`
- `0x180003d0c`
- `0x180004214`
- `0x1800050b8`

## string_xrefs

- `0x18000429c`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\dll\devicedirectoryclient.cpp`
- `0x18000428d`: `CHR(GetTriggerArgument(wstrConfiguration, eTrigger))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDeviceDirectoryClientHandler::ProcessRegisterPhone(__int64 a1, __int64 a2, __int64 a3)
{
  int v4; // edx
  int v5; // ecx
  int TriggerArgument; // ebx
  int v8; // [rsp+50h] [rbp+18h] BYREF
  int v9; // [rsp+54h] [rbp+1Ch]

  v9 = HIDWORD(a3);
  v8 = 0;
  ConfigurationArgumentPresent(a2, (__int64)L"-Full", 0, 1);
  ConfigurationArgumentPresent(a2, (__int64)L"-FreeNetworkOnly", 0, 1);
  ConfigurationArgumentPresent(a2, (__int64)L"-Upgrade", 0, 1);
  TriggerArgument = GetTriggerArgument(a2, &v8);
  if ( TriggerArgument < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      v5,
      v4,
      TriggerArgument,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\dll\\devicedirectoryclient.cpp",
      148,
      "CHR(GetTriggerArgument(wstrConfiguration, eTrigger))");
  return (unsigned int)TriggerArgument;
}

```

## disassembly

```asm
0x180004214  mov     [rsp+arg_10], r8
0x180004219  push    rbx
0x18000421a  sub     rsp, 30h
0x18000421e  mov     rbx, rdx
0x180004221  mov     dword ptr [rsp+38h+arg_10], 0
0x180004229  mov     rcx, rbx
0x18000422c  lea     rdx, aFull; "-Full"
0x180004233  mov     r9d, 1
0x180004239  xor     r8d, r8d
0x18000423c  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x180004241  mov     r9d, 1
0x180004247  lea     rdx, aFreenetworkonl; "-FreeNetworkOnly"
0x18000424e  xor     r8d, r8d
0x180004251  mov     rcx, rbx
0x180004254  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x180004259  mov     r9d, 1
0x18000425f  lea     rdx, aUpgrade; "-Upgrade"
0x180004266  xor     r8d, r8d
0x180004269  mov     rcx, rbx
0x18000426c  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x180004271  lea     rdx, [rsp+38h+arg_10]
0x180004276  mov     rcx, rbx
0x180004279  call    ?GetTriggerArgument@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAW4MdmRegistrationTrigger@@@Z; GetTriggerArgument(std::wstring &,MdmRegistrationTrigger &)
0x18000427e  mov     ebx, eax
0x180004280  test    eax, eax
0x180004282  jns     short loc_1800042B0
0x180004284  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000428b  jz      short loc_1800042B0
0x18000428d  lea     rax, aChrGettriggera; "CHR(GetTriggerArgument(wstrConfiguratio"...
0x180004294  mov     r8d, ebx
0x180004297  mov     [rsp+38h+var_10], rax
0x18000429c  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800042a3  mov     [rsp+38h+var_18], 194h
0x1800042ab  call    McTemplateU0dsqs_EventWriteTransfer
0x1800042b0  mov     eax, ebx
0x1800042b2  add     rsp, 30h
0x1800042b6  pop     rbx
0x1800042b7  retn
```
