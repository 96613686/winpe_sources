# CDeviceDirectoryClientHandler::ProcessRegisterDevice(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,void *)

- ea: `0x1800040ec`
- end: `0x18000420c`
- name: `?ProcessRegisterDevice@CDeviceDirectoryClientHandler@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `288`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004640`

## callees

- `0x180003974`
- `0x180003d0c`
- `0x1800040ec`
- `0x1800050b8`
- `0x18000c034`

## string_xrefs

- `0x1800041ee`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\dll\devicedirectoryclient.cpp`
- `0x18000418b`: `CHR(GetTriggerArgument(wstrConfiguration, eTrigger))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDeviceDirectoryClientHandler::ProcessRegisterDevice(__int64 a1, __int64 a2, __int64 a3)
{
  BOOL v6; // esi
  BOOL v7; // ebp
  BOOL v8; // r14d
  int v9; // edx
  int v10; // ecx
  int TriggerArgument; // ebx
  int v12; // edx
  int v13; // ecx
  int v15; // [rsp+88h] [rbp+20h] BYREF

  v15 = 0;
  v6 = ConfigurationArgumentPresent(a2, (__int64)L"-Full", 0, 1);
  v7 = ConfigurationArgumentPresent(a2, (__int64)L"-FreeNetworkOnly", 0, 1);
  v8 = ConfigurationArgumentPresent(a2, (__int64)L"-Light", 0, 1);
  TriggerArgument = GetTriggerArgument(a2, &v15);
  if ( TriggerArgument >= 0 )
  {
    TriggerArgument = DdcRegistrationController::RegisterDevice((a1 + 56) & -(__int64)(a1 != 0), v6, v7, v8, v15, a3);
    if ( TriggerArgument < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v13,
        v12,
        TriggerArgument,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\dll\\devicedirectoryclient.cpp",
        99,
        "CHR(DdcRegistrationController::RegisterDevice(this, fFullRefresh, fFreeNetworkOnly, fLight, eTrigger, pdcHandle))");
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v10,
      v9,
      TriggerArgument,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\dll\\devicedirectoryclient.cpp",
      98,
      "CHR(GetTriggerArgument(wstrConfiguration, eTrigger))");
  }
  return (unsigned int)TriggerArgument;
}

```

## disassembly

```asm
0x1800040ec  mov     rax, rsp
0x1800040ef  push    rbx
0x1800040f0  push    rbp
0x1800040f1  push    rsi
0x1800040f2  push    rdi
0x1800040f3  push    r14
0x1800040f5  push    r15
0x1800040f7  sub     rsp, 38h
0x1800040fb  mov     rbx, rdx
0x1800040fe  mov     dword ptr [rax+20h], 0
0x180004105  mov     r15, r8
0x180004108  lea     rdx, aFull; "-Full"
0x18000410f  mov     rdi, rcx
0x180004112  mov     r9d, 1
0x180004118  mov     rcx, rbx
0x18000411b  xor     r8d, r8d
0x18000411e  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x180004123  xor     esi, esi
0x180004125  lea     rdx, aFreenetworkonl; "-FreeNetworkOnly"
0x18000412c  test    eax, eax
0x18000412e  mov     r9d, 1
0x180004134  mov     rcx, rbx
0x180004137  setnz   sil
0x18000413b  xor     r8d, r8d
0x18000413e  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x180004143  xor     ebp, ebp
0x180004145  lea     rdx, aLight; "-Light"
0x18000414c  test    eax, eax
0x18000414e  mov     r9d, 1
0x180004154  mov     rcx, rbx
0x180004157  setnz   bpl
0x18000415b  xor     r8d, r8d
0x18000415e  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x180004163  xor     r14d, r14d
0x180004166  lea     rdx, [rsp+68h+arg_18]
0x18000416e  test    eax, eax
0x180004170  mov     rcx, rbx
0x180004173  setnz   r14b
0x180004177  call    ?GetTriggerArgument@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAW4MdmRegistrationTrigger@@@Z; GetTriggerArgument(std::wstring &,MdmRegistrationTrigger &)
0x18000417c  mov     ebx, eax
0x18000417e  test    eax, eax
0x180004180  jns     short loc_1800041A1
0x180004182  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180004189  jz      short loc_1800041FD
0x18000418b  lea     rax, aChrGettriggera; "CHR(GetTriggerArgument(wstrConfiguratio"...
0x180004192  mov     [rsp+68h+var_40], rax
0x180004197  mov     [rsp+68h+var_48], 162h
0x18000419f  jmp     short loc_1800041EE
0x1800041a1  lea     rax, [rdi+38h]
0x1800041a5  mov     [rsp+68h+var_40], r15
0x1800041aa  neg     rdi
0x1800041ad  mov     r9d, r14d
0x1800041b0  mov     r8d, ebp
0x1800041b3  mov     edx, esi
0x1800041b5  sbb     rcx, rcx
0x1800041b8  and     rcx, rax
0x1800041bb  mov     eax, [rsp+68h+arg_18]
0x1800041c2  mov     [rsp+68h+var_48], eax
0x1800041c6  call    ?RegisterDevice@DdcRegistrationController@@SAJPEAVIDdcStoppable@@HHHW4MdmRegistrationTrigger@@PEAX@Z; DdcRegistrationController::RegisterDevice(IDdcStoppable *,int,int,int,MdmRegistrationTrigger,void *)
0x1800041cb  mov     ebx, eax
0x1800041cd  test    eax, eax
0x1800041cf  jns     short loc_1800041FD
0x1800041d1  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800041d8  jz      short loc_1800041FD
0x1800041da  lea     rax, aChrDdcregistra_0; "CHR(DdcRegistrationController::Register"...
0x1800041e1  mov     [rsp+68h+var_40], rax
0x1800041e6  mov     [rsp+68h+var_48], 163h
0x1800041ee  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800041f5  mov     r8d, ebx
0x1800041f8  call    McTemplateU0dsqs_EventWriteTransfer
0x1800041fd  mov     eax, ebx
0x1800041ff  add     rsp, 38h
0x180004203  pop     r15
0x180004205  pop     r14
0x180004207  pop     rdi
0x180004208  pop     rsi
0x180004209  pop     rbp
0x18000420a  pop     rbx
0x18000420b  retn
```
