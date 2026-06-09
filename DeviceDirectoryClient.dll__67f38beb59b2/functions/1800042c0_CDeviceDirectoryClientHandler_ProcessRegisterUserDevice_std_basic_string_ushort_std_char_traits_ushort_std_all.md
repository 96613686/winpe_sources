# CDeviceDirectoryClientHandler::ProcessRegisterUserDevice(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,void *)

- ea: `0x1800042c0`
- end: `0x180004385`
- name: `?ProcessRegisterUserDevice@CDeviceDirectoryClientHandler@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `197`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004640`

## callees

- `0x180003974`
- `0x180003d0c`
- `0x1800042c0`
- `0x1800050b8`
- `0x18000ca4c`

## string_xrefs

- `0x18000436b`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\dll\devicedirectoryclient.cpp`
- `0x180004316`: `CHR(GetTriggerArgument(wstrConfiguration, eTrigger))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDeviceDirectoryClientHandler::ProcessRegisterUserDevice(__int64 a1, __int64 a2, __int64 a3)
{
  BOOL v6; // esi
  int v7; // edx
  int v8; // ecx
  int TriggerArgument; // ebx
  int v10; // edx
  int v11; // ecx
  unsigned int v13; // [rsp+78h] [rbp+20h] BYREF

  v13 = 0;
  v6 = ConfigurationArgumentPresent(a2, (__int64)L"-Full", 0, 1);
  TriggerArgument = GetTriggerArgument(a2, &v13);
  if ( TriggerArgument >= 0 )
  {
    TriggerArgument = DdcRegistrationController::RegisterUserDevice((a1 + 56) & -(__int64)(a1 != 0), v6, v13, a3);
    if ( TriggerArgument < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v11,
        v10,
        TriggerArgument,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\dll\\devicedirectoryclient.cpp",
        117,
        "CHR(DdcRegistrationController::RegisterUserDevice(this, fFullRefresh, eTrigger, pdcHandle))");
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v8,
      v7,
      TriggerArgument,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\dll\\devicedirectoryclient.cpp",
      116,
      "CHR(GetTriggerArgument(wstrConfiguration, eTrigger))");
  }
  return (unsigned int)TriggerArgument;
}

```

## disassembly

```asm
0x1800042c0  push    rbx
0x1800042c2  push    rbp
0x1800042c3  push    rsi
0x1800042c4  push    rdi
0x1800042c5  sub     rsp, 38h
0x1800042c9  mov     rbx, rdx
0x1800042cc  mov     [rsp+58h+arg_18], 0
0x1800042d4  mov     rbp, r8
0x1800042d7  lea     rdx, aFull; "-Full"
0x1800042de  mov     rdi, rcx
0x1800042e1  mov     r9d, 1
0x1800042e7  mov     rcx, rbx
0x1800042ea  xor     r8d, r8d
0x1800042ed  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x1800042f2  xor     esi, esi
0x1800042f4  lea     rdx, [rsp+58h+arg_18]
0x1800042f9  test    eax, eax
0x1800042fb  mov     rcx, rbx
0x1800042fe  setnz   sil
0x180004302  call    ?GetTriggerArgument@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAW4MdmRegistrationTrigger@@@Z; GetTriggerArgument(std::wstring &,MdmRegistrationTrigger &)
0x180004307  mov     ebx, eax
0x180004309  test    eax, eax
0x18000430b  jns     short loc_18000432C
0x18000430d  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180004314  jz      short loc_18000437A
0x180004316  lea     rax, aChrGettriggera; "CHR(GetTriggerArgument(wstrConfiguratio"...
0x18000431d  mov     [rsp+58h+var_30], rax
0x180004322  mov     [rsp+58h+var_38], 174h
0x18000432a  jmp     short loc_18000436B
0x18000432c  mov     r8d, [rsp+58h+arg_18]
0x180004331  lea     rax, [rdi+38h]
0x180004335  neg     rdi
0x180004338  mov     r9, rbp
0x18000433b  mov     edx, esi
0x18000433d  sbb     rcx, rcx
0x180004340  and     rcx, rax
0x180004343  call    ?RegisterUserDevice@DdcRegistrationController@@SAJPEAVIDdcStoppable@@HW4MdmRegistrationTrigger@@PEAX@Z; DdcRegistrationController::RegisterUserDevice(IDdcStoppable *,int,MdmRegistrationTrigger,void *)
0x180004348  mov     ebx, eax
0x18000434a  test    eax, eax
0x18000434c  jns     short loc_18000437A
0x18000434e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180004355  jz      short loc_18000437A
0x180004357  lea     rax, aChrDdcregistra; "CHR(DdcRegistrationController::Register"...
0x18000435e  mov     [rsp+58h+var_30], rax
0x180004363  mov     [rsp+58h+var_38], 175h
0x18000436b  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180004372  mov     r8d, ebx
0x180004375  call    McTemplateU0dsqs_EventWriteTransfer
0x18000437a  mov     eax, ebx
0x18000437c  add     rsp, 38h
0x180004380  pop     rdi
0x180004381  pop     rsi
0x180004382  pop     rbp
0x180004383  pop     rbx
0x180004384  retn
```
