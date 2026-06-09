# GetEffectPackDevNodeRegistryRoot(ushort const *,HKEY__ * *)

- ea: `0x1400840f0`
- end: `0x140084187`
- name: `?GetEffectPackDevNodeRegistryRoot@@YAJPEBGPEAPEAUHKEY__@@@Z`
- size: `151`
- prototype: `__int64 __fastcall(DEVINSTID_W pDeviceID, PHKEY phkDevice)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140052090`

## callees

- `0x1400690a0`
- `0x1400840f0`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x140084161`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x140084161`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x140084113`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x140084113`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x140084120`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x14008416e`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x140084120`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x14008416e`

## pseudocode

```c
int __fastcall GetEffectPackDevNodeRegistryRoot(DEVINSTID_W pDeviceID, PHKEY phkDevice)
{
  CONFIGRET v3; // eax
  DWORD v4; // eax
  __int64 v5; // rdx
  CONFIGRET v7; // eax
  unsigned int phkDevicea; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DEVNODE pdnDevInst; // [rsp+48h] [rbp+10h] BYREF

  *phkDevice = 0;
  pdnDevInst = 0;
  v3 = CM_Locate_DevNodeW(&pdnDevInst, pDeviceID, 0);
  v4 = CM_MapCrToWin32Err(v3, 0x507u);
  if ( v4 )
  {
    v5 = 40;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v5,
             (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\effectpackutil.cpp",
             (const char *)v4,
             phkDevicea);
  }
  v7 = CM_Open_DevNode_Key(pdnDevInst, 0x20019u, 0, 1u, phkDevice, 1u);
  v4 = CM_MapCrToWin32Err(v7, 0x507u);
  if ( v4 )
  {
    v5 = 41;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v5,
             (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\effectpackutil.cpp",
             (const char *)v4,
             phkDevicea);
  }
  return 0;
}

```

## disassembly

```asm
0x1400840f0  push    rbx
0x1400840f2  sub     rsp, 30h
0x1400840f6  mov     rbx, rdx
0x1400840f9  mov     qword ptr [rdx], 0
0x140084100  mov     rdx, rcx; pDeviceID
0x140084103  mov     [rsp+38h+pdnDevInst], 0
0x14008410b  lea     rcx, [rsp+38h+pdnDevInst]; pdnDevInst
0x140084110  xor     r8d, r8d; ulFlags
0x140084113  call    cs:__imp_CM_Locate_DevNodeW
0x140084119  mov     ecx, eax; CmReturnCode
0x14008411b  mov     edx, 507h; DefaultErr
0x140084120  call    cs:__imp_CM_MapCrToWin32Err
0x140084126  test    eax, eax
0x140084128  jz      short loc_140084145
0x14008412a  mov     edx, 28h ; '('; void *
0x14008412f  mov     rcx, [rsp+38h]; this
0x140084134  lea     r8, aAvcoreAudiocor_72; "avcore\\audiocore\\server\\lib\\audioen"...
0x14008413b  mov     r9d, eax; char *
0x14008413e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140084143  jmp     short loc_140084181
0x140084145  mov     ecx, [rsp+38h+pdnDevInst]; dnDevNode
0x140084149  mov     r9d, 1; Disposition
0x14008414f  mov     [rsp+38h+ulFlags], r9d; ulFlags
0x140084154  xor     r8d, r8d; ulHardwareProfile
0x140084157  mov     edx, 20019h; samDesired
0x14008415c  mov     [rsp+38h+phkDevice], rbx; phkDevice
0x140084161  call    cs:__imp_CM_Open_DevNode_Key
0x140084167  mov     ecx, eax; CmReturnCode
0x140084169  mov     edx, 507h; DefaultErr
0x14008416e  call    cs:__imp_CM_MapCrToWin32Err
0x140084174  test    eax, eax
0x140084176  jz      short loc_14008417F
0x140084178  mov     edx, 29h ; ')'
0x14008417d  jmp     short loc_14008412F
0x14008417f  xor     eax, eax
0x140084181  add     rsp, 30h
0x140084185  pop     rbx
0x140084186  retn
```
