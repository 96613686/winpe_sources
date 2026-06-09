# GetTriggerArgument(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,MdmRegistrationTrigger &)

- ea: `0x180003d0c`
- end: `0x180004059`
- name: `?GetTriggerArgument@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAW4MdmRegistrationTrigger@@@Z`
- size: `845`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800040ec`
- `0x180004214`
- `0x1800042c0`

## callees

- `0x180003974`
- `0x180003d0c`
- `0x1800050b8`

## string_xrefs

- `0x180003d71`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\dll\devicedirectoryclient.cpp`

## pseudocode

```c
__int64 __fastcall GetTriggerArgument(__int64 a1, _DWORD *a2)
{
  int v4; // edx
  int v5; // ecx
  unsigned int v6; // ebx
  int v7; // edx
  int v8; // ecx
  int v9; // edx
  int v10; // ecx
  int v11; // edx
  int v12; // ecx
  int v13; // edx
  int v14; // ecx
  int v15; // edx
  int v16; // ecx
  int v17; // edx
  int v18; // ecx
  int v19; // edx
  int v20; // ecx
  int v21; // edx
  int v22; // ecx

  *a2 = 0;
  if ( ConfigurationArgumentPresent(a1, (__int64)L"-Periodic", 0, 1) )
  {
    if ( *a2 )
    {
      v6 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v5,
          v4,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\dll\\devicedirectoryclient.cpp",
          146,
          "CBR(eTrigger == MdmRegistrationTrigger_Unknown)");
      return v6;
    }
    *a2 = 2;
  }
  if ( ConfigurationArgumentPresent(a1, (__int64)L"-SettingChange", 0, 1) )
  {
    if ( *a2 )
    {
      v6 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v8,
          v7,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\dll\\devicedirectoryclient.cpp",
          152,
          "CBR(eTrigger == MdmRegistrationTrigger_Unknown)");
      return v6;
    }
    *a2 = 5;
  }
  if ( ConfigurationArgumentPresent(a1, (__int64)L"-AccountChange", 0, 1) )
  {
    if ( *a2 )
    {
      v6 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v10,
          v9,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\dll\\devicedirectoryclient.cpp",
          158,
          "CBR(eTrigger == MdmRegistrationTrigger_Unknown)");
      return v6;
    }
    *a2 = 6;
  }
  if ( ConfigurationArgumentPresent(a1, (__int64)L"-ConnectedToNetwork", 0, 1) )
  {
    if ( *a2 )
    {
      v6 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v12,
          v11,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\dll\\devicedirectoryclient.cpp",
          164,
          "CBR(eTrigger == MdmRegistrationTrigger_Unknown)");
      return v6;
    }
    *a2 = 7;
  }
  if ( ConfigurationArgumentPresent(a1, (__int64)L"-ScreenOnOff", 0, 1) )
  {
    if ( *a2 )
    {
      v6 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v14,
          v13,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\dll\\devicedirectoryclient.cpp",
          170,
          "CBR(eTrigger == MdmRegistrationTrigger_Unknown)");
      return v6;
    }
    *a2 = 8;
  }
  if ( ConfigurationArgumentPresent(a1, (__int64)L"-NewAccount", 0, 1) )
  {
    if ( *a2 )
    {
      v6 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v16,
          v15,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\dll\\devicedirectoryclient.cpp",
          176,
          "CBR(eTrigger == MdmRegistrationTrigger_Unknown)");
      return v6;
    }
    *a2 = 9;
  }
  if ( ConfigurationArgumentPresent(a1, (__int64)L"-FirstTimeSignIn", 0, 1) )
  {
    if ( *a2 )
    {
      v6 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v18,
          v17,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\dll\\devicedirectoryclient.cpp",
          182,
          "CBR(eTrigger == MdmRegistrationTrigger_Unknown)");
      return v6;
    }
    *a2 = 1;
  }
  if ( ConfigurationArgumentPresent(a1, (__int64)L"-SimCardChanged", 0, 1) )
  {
    if ( *a2 )
    {
      v6 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v20,
          v19,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\dll\\devicedirectoryclient.cpp",
          188,
          "CBR(eTrigger == MdmRegistrationTrigger_Unknown)");
      return v6;
    }
    *a2 = 3;
  }
  if ( ConfigurationArgumentPresent(a1, (__int64)L"-ProtectionStateChanged", 0, 1) )
  {
    if ( *a2 )
    {
      v6 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v22,
          v21,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\dll\\devicedirectoryclient.cpp",
          194,
          "CBR(eTrigger == MdmRegistrationTrigger_Unknown)");
      return v6;
    }
    *a2 = 10;
  }
  if ( *a2 )
  {
    return 0;
  }
  else
  {
    v6 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v22,
        v21,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\dll\\devicedirectoryclient.cpp",
        198,
        "CBR(eTrigger != MdmRegistrationTrigger_Unknown)");
  }
  return v6;
}

```

## disassembly

```asm
0x180003d0c  mov     [rsp+arg_0], rbx
0x180003d11  mov     [rsp+arg_8], rbp
0x180003d16  push    rdi
0x180003d17  sub     rsp, 30h
0x180003d1b  mov     rbx, rdx
0x180003d1e  mov     dword ptr [rdx], 0
0x180003d24  mov     ebp, 1
0x180003d29  lea     rdx, aPeriodic; "-Periodic"
0x180003d30  mov     r9d, ebp
0x180003d33  xor     r8d, r8d
0x180003d36  mov     rdi, rcx
0x180003d39  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x180003d3e  test    eax, eax
0x180003d40  jz      short loc_180003D88
0x180003d42  cmp     dword ptr [rbx], 0
0x180003d45  jz      short loc_180003D82
0x180003d47  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, bpl
0x180003d4e  mov     r8d, 80070057h
0x180003d54  mov     ebx, r8d
0x180003d57  jz      loc_180004047
0x180003d5d  lea     rax, aCbrEtriggerMdm; "CBR(eTrigger == MdmRegistrationTrigger_"...
0x180003d64  mov     [rsp+38h+var_10], rax
0x180003d69  mov     [rsp+38h+var_18], 92h
0x180003d71  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180003d78  call    McTemplateU0dsqs_EventWriteTransfer
0x180003d7d  jmp     loc_180004047
0x180003d82  mov     dword ptr [rbx], 2
0x180003d88  mov     r9d, ebp
0x180003d8b  lea     rdx, aSettingchange; "-SettingChange"
0x180003d92  xor     r8d, r8d
0x180003d95  mov     rcx, rdi
0x180003d98  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x180003d9d  test    eax, eax
0x180003d9f  jz      short loc_180003DD8
0x180003da1  cmp     dword ptr [rbx], 0
0x180003da4  jz      short loc_180003DD2
0x180003da6  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, bpl
0x180003dad  mov     r8d, 80070057h
0x180003db3  mov     ebx, r8d
0x180003db6  jz      loc_180004047
0x180003dbc  lea     rax, aCbrEtriggerMdm; "CBR(eTrigger == MdmRegistrationTrigger_"...
0x180003dc3  mov     [rsp+38h+var_10], rax
0x180003dc8  mov     [rsp+38h+var_18], 98h
0x180003dd0  jmp     short loc_180003D71
0x180003dd2  mov     dword ptr [rbx], 5
0x180003dd8  mov     r9d, ebp
0x180003ddb  lea     rdx, aAccountchange; "-AccountChange"
0x180003de2  xor     r8d, r8d
0x180003de5  mov     rcx, rdi
0x180003de8  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x180003ded  test    eax, eax
0x180003def  jz      short loc_180003E2B
0x180003df1  cmp     dword ptr [rbx], 0
0x180003df4  jz      short loc_180003E25
0x180003df6  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, bpl
0x180003dfd  mov     r8d, 80070057h
0x180003e03  mov     ebx, r8d
0x180003e06  jz      loc_180004047
0x180003e0c  lea     rax, aCbrEtriggerMdm; "CBR(eTrigger == MdmRegistrationTrigger_"...
0x180003e13  mov     [rsp+38h+var_10], rax
0x180003e18  mov     [rsp+38h+var_18], 9Eh
0x180003e20  jmp     loc_180003D71
0x180003e25  mov     dword ptr [rbx], 6
0x180003e2b  mov     r9d, ebp
0x180003e2e  lea     rdx, aConnectedtonet; "-ConnectedToNetwork"
0x180003e35  xor     r8d, r8d
0x180003e38  mov     rcx, rdi
0x180003e3b  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x180003e40  test    eax, eax
0x180003e42  jz      short loc_180003E7E
0x180003e44  cmp     dword ptr [rbx], 0
0x180003e47  jz      short loc_180003E78
0x180003e49  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, bpl
0x180003e50  mov     r8d, 80070057h
0x180003e56  mov     ebx, r8d
0x180003e59  jz      loc_180004047
0x180003e5f  lea     rax, aCbrEtriggerMdm; "CBR(eTrigger == MdmRegistrationTrigger_"...
0x180003e66  mov     [rsp+38h+var_10], rax
0x180003e6b  mov     [rsp+38h+var_18], 0A4h
0x180003e73  jmp     loc_180003D71
0x180003e78  mov     dword ptr [rbx], 7
0x180003e7e  mov     r9d, ebp
0x180003e81  lea     rdx, aScreenonoff; "-ScreenOnOff"
0x180003e88  xor     r8d, r8d
0x180003e8b  mov     rcx, rdi
0x180003e8e  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x180003e93  test    eax, eax
0x180003e95  jz      short loc_180003ED1
0x180003e97  cmp     dword ptr [rbx], 0
0x180003e9a  jz      short loc_180003ECB
0x180003e9c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, bpl
0x180003ea3  mov     r8d, 80070057h
0x180003ea9  mov     ebx, r8d
0x180003eac  jz      loc_180004047
0x180003eb2  lea     rax, aCbrEtriggerMdm; "CBR(eTrigger == MdmRegistrationTrigger_"...
0x180003eb9  mov     [rsp+38h+var_10], rax
0x180003ebe  mov     [rsp+38h+var_18], 0AAh
0x180003ec6  jmp     loc_180003D71
0x180003ecb  mov     dword ptr [rbx], 8
0x180003ed1  mov     r9d, ebp
0x180003ed4  lea     rdx, aNewaccount; "-NewAccount"
0x180003edb  xor     r8d, r8d
0x180003ede  mov     rcx, rdi
0x180003ee1  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x180003ee6  test    eax, eax
0x180003ee8  jz      short loc_180003F24
0x180003eea  cmp     dword ptr [rbx], 0
0x180003eed  jz      short loc_180003F1E
0x180003eef  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, bpl
0x180003ef6  mov     r8d, 80070057h
0x180003efc  mov     ebx, r8d
0x180003eff  jz      loc_180004047
0x180003f05  lea     rax, aCbrEtriggerMdm; "CBR(eTrigger == MdmRegistrationTrigger_"...
0x180003f0c  mov     [rsp+38h+var_10], rax
0x180003f11  mov     [rsp+38h+var_18], 0B0h
0x180003f19  jmp     loc_180003D71
0x180003f1e  mov     dword ptr [rbx], 9
0x180003f24  mov     r9d, ebp
0x180003f27  lea     rdx, aFirsttimesigni; "-FirstTimeSignIn"
0x180003f2e  xor     r8d, r8d
0x180003f31  mov     rcx, rdi
0x180003f34  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x180003f39  test    eax, eax
0x180003f3b  jz      short loc_180003F73
0x180003f3d  cmp     dword ptr [rbx], 0
0x180003f40  jz      short loc_180003F71
0x180003f42  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, bpl
0x180003f49  mov     r8d, 80070057h
0x180003f4f  mov     ebx, r8d
0x180003f52  jz      loc_180004047
0x180003f58  lea     rax, aCbrEtriggerMdm; "CBR(eTrigger == MdmRegistrationTrigger_"...
0x180003f5f  mov     [rsp+38h+var_10], rax
0x180003f64  mov     [rsp+38h+var_18], 0B6h
0x180003f6c  jmp     loc_180003D71
0x180003f71  mov     [rbx], ebp
0x180003f73  mov     r9d, ebp
0x180003f76  lea     rdx, aSimcardchanged; "-SimCardChanged"
0x180003f7d  xor     r8d, r8d
0x180003f80  mov     rcx, rdi
0x180003f83  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x180003f88  test    eax, eax
0x180003f8a  jz      short loc_180003FC6
0x180003f8c  cmp     dword ptr [rbx], 0
0x180003f8f  jz      short loc_180003FC0
0x180003f91  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, bpl
0x180003f98  mov     r8d, 80070057h
0x180003f9e  mov     ebx, r8d
0x180003fa1  jz      loc_180004047
0x180003fa7  lea     rax, aCbrEtriggerMdm; "CBR(eTrigger == MdmRegistrationTrigger_"...
0x180003fae  mov     [rsp+38h+var_10], rax
0x180003fb3  mov     [rsp+38h+var_18], 0BCh
0x180003fbb  jmp     loc_180003D71
0x180003fc0  mov     dword ptr [rbx], 3
0x180003fc6  mov     r9d, ebp
0x180003fc9  lea     rdx, aProtectionstat; "-ProtectionStateChanged"
0x180003fd0  xor     r8d, r8d
0x180003fd3  mov     rcx, rdi
0x180003fd6  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x180003fdb  test    eax, eax
0x180003fdd  jz      short loc_180004015
0x180003fdf  cmp     dword ptr [rbx], 0
0x180003fe2  jz      short loc_18000400F
0x180003fe4  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, bpl
0x180003feb  mov     r8d, 80070057h
0x180003ff1  mov     ebx, r8d
0x180003ff4  jz      short loc_180004047
0x180003ff6  lea     rax, aCbrEtriggerMdm; "CBR(eTrigger == MdmRegistrationTrigger_"...
0x180003ffd  mov     [rsp+38h+var_10], rax
0x180004002  mov     [rsp+38h+var_18], 0C2h
0x18000400a  jmp     loc_180003D71
0x18000400f  mov     dword ptr [rbx], 0Ah
0x180004015  cmp     dword ptr [rbx], 0
0x180004018  jnz     short loc_180004045
0x18000401a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, bpl
0x180004021  mov     r8d, 80070057h
0x180004027  mov     ebx, r8d
0x18000402a  jz      short loc_180004047
0x18000402c  lea     rax, aCbrEtriggerMdm_0; "CBR(eTrigger != MdmRegistrationTrigger_"...
0x180004033  mov     [rsp+38h+var_10], rax
0x180004038  mov     [rsp+38h+var_18], 0C6h
0x180004040  jmp     loc_180003D71
0x180004045  xor     ebx, ebx
0x180004047  mov     rbp, [rsp+38h+arg_8]
0x18000404c  mov     eax, ebx
0x18000404e  mov     rbx, [rsp+38h+arg_0]
0x180004053  add     rsp, 30h
0x180004057  pop     rdi
0x180004058  retn
```
