# IsAnyEhStorDevicePresent

- ea: `0x180001320`
- end: `0x1800013d9`
- name: `IsAnyEhStorDevicePresent`
- size: `185`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180001090`
- `0x18000adb4`

## callees

- `0x180001320`
- `0x18000b630`

## import_xrefs

- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1800013cf`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1800013cf`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x1800013bf`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x1800013bf`
- `SETUPAPI!SetupDiGetClassDevsExW` at `0x180001361`
- `SETUPAPI!SetupDiGetClassDevsExW` at `0x180001361`

## pseudocode

```c
__int64 IsAnyEhStorDevicePresent()
{
  HDEVINFO ClassDevs; // rdi
  unsigned int v2; // ebx
  _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+40h] [rbp-38h] BYREF

  ClassDevs = SetupDiGetClassDevsExW(&GUID_EHSTOR_CONTROL_INTERFACE, 0, 0, 0x12u, 0, 0, 0);
  if ( ClassDevs == (HDEVINFO)-1LL )
    return 0;
  memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
  DeviceInterfaceData.cbSize = 32;
  v2 = SetupDiEnumDeviceInterfaces(ClassDevs, 0, &GUID_EHSTOR_CONTROL_INTERFACE, 0, &DeviceInterfaceData);
  SetupDiDestroyDeviceInfoList(ClassDevs);
  return v2;
}

```

## disassembly

```asm
0x180001320  mov     [rsp+arg_0], rbx
0x180001325  mov     [rsp+arg_8], rsi
0x18000132a  push    rdi
0x18000132b  sub     rsp, 70h
0x18000132f  mov     rax, cs:__security_cookie
0x180001336  xor     rax, rsp
0x180001339  mov     [rsp+78h+var_18], rax
0x18000133e  xor     esi, esi
0x180001340  lea     rcx, GUID_EHSTOR_CONTROL_INTERFACE; ClassGuid
0x180001347  mov     [rsp+78h+Reserved], rsi; Reserved
0x18000134c  mov     r9d, 12h; Flags
0x180001352  mov     [rsp+78h+MachineName], rsi; MachineName
0x180001357  xor     r8d, r8d; hwndParent
0x18000135a  xor     edx, edx; Enumerator
0x18000135c  mov     [rsp+78h+DeviceInfoSet], rsi; DeviceInfoSet
0x180001361  call    cs:__imp_SetupDiGetClassDevsExW
0x180001367  mov     rdi, rax
0x18000136a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000136e  jnz     short loc_180001391
0x180001370  mov     eax, esi
0x180001372  mov     rcx, [rsp+78h+var_18]
0x180001377  xor     rcx, rsp; StackCookie
0x18000137a  call    __security_check_cookie
0x18000137f  lea     r11, [rsp+78h+var_8]
0x180001384  mov     rbx, [r11+10h]
0x180001388  mov     rsi, [r11+18h]
0x18000138c  mov     rsp, r11
0x18000138f  pop     rdi
0x180001390  retn
0x180001391  xorps   xmm0, xmm0
0x180001394  lea     rax, [rsp+78h+DeviceInterfaceData]
0x180001399  movups  xmmword ptr [rsp+78h+DeviceInterfaceData.cbSize], xmm0
0x18000139e  xor     r9d, r9d; MemberIndex
0x1800013a1  mov     [rsp+78h+DeviceInterfaceData.cbSize], 20h ; ' '
0x1800013a9  lea     r8, GUID_EHSTOR_CONTROL_INTERFACE; InterfaceClassGuid
0x1800013b0  mov     [rsp+78h+DeviceInfoSet], rax; DeviceInterfaceData
0x1800013b5  xor     edx, edx; DeviceInfoData
0x1800013b7  mov     rcx, rdi; DeviceInfoSet
0x1800013ba  movups  xmmword ptr [rsp+78h+DeviceInterfaceData.InterfaceClassGuid.Data4+4], xmm0
0x1800013bf  call    cs:__imp_SetupDiEnumDeviceInterfaces
0x1800013c5  mov     ebx, esi
0x1800013c7  mov     rcx, rdi; DeviceInfoSet
0x1800013ca  test    eax, eax
0x1800013cc  setnz   bl
0x1800013cf  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x1800013d5  mov     eax, ebx
0x1800013d7  jmp     short loc_180001372
```
