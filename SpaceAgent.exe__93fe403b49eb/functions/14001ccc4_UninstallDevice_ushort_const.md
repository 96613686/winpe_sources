# UninstallDevice(ushort const *)

- ea: `0x14001ccc4`
- end: `0x14001cde1`
- name: `?UninstallDevice@@YAHPEBG@Z`
- size: `285`
- prototype: `__int64 __fastcall(PCWSTR DevicePath)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140016cb0`
- `0x14001d7c0`

## callees

- `0x14001ccc4`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14001cdb7`
- `KERNEL32!SetLastError` at `0x14001cdb7`
- `KERNEL32!GetLastError` at `0x14001cd76`
- `KERNEL32!GetLastError` at `0x14001cd96`
- `KERNEL32!GetLastError` at `0x14001cdad`
- `KERNEL32!GetLastError` at `0x14001cd76`
- `KERNEL32!GetLastError` at `0x14001cd96`
- `KERNEL32!GetLastError` at `0x14001cdad`
- `SETUPAPI!SetupDiCreateDeviceInfoListExA` at `0x14001cd0c`
- `SETUPAPI!SetupDiCreateDeviceInfoListExA` at `0x14001cd0c`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x14001cd39`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x14001cd39`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x14001cda1`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x14001cda1`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x14001cd6a`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x14001cd6a`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x14001cd8e`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x14001cd8e`

## pseudocode

```c
__int64 __fastcall UninstallDevice(PCWSTR DevicePath)
{
  HDEVINFO DeviceInfoList; // rax
  void *v3; // rsi
  unsigned int DeviceInterfaceDetailW; // ebx
  DWORD LastError; // edi
  BOOL v6; // eax
  struct _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+30h] [rbp-58h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+50h] [rbp-38h] BYREF

  memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  DeviceInfoList = SetupDiCreateDeviceInfoListExA(0, 0, 0, 0);
  v3 = DeviceInfoList;
  if ( DeviceInfoList == (HDEVINFO)-1LL )
  {
    DeviceInterfaceDetailW = 0;
LABEL_9:
    LastError = GetLastError();
    goto LABEL_10;
  }
  DeviceInterfaceData.cbSize = 32;
  DeviceInterfaceDetailW = SetupDiOpenDeviceInterfaceW(DeviceInfoList, DevicePath, 0, &DeviceInterfaceData);
  if ( DeviceInterfaceDetailW )
  {
    DeviceInfoData.cbSize = 32;
    DeviceInterfaceDetailW = SetupDiGetDeviceInterfaceDetailW(v3, &DeviceInterfaceData, 0, 0, 0, &DeviceInfoData);
    if ( DeviceInterfaceDetailW || GetLastError() == 122 )
      DeviceInterfaceDetailW = SetupDiCallClassInstaller(5u, v3, &DeviceInfoData);
  }
  LastError = GetLastError();
  v6 = SetupDiDestroyDeviceInfoList(v3);
  if ( DeviceInterfaceDetailW )
  {
    DeviceInterfaceDetailW = v6;
    goto LABEL_9;
  }
LABEL_10:
  SetLastError(LastError);
  return DeviceInterfaceDetailW;
}

```

## disassembly

```asm
0x14001ccc4  mov     [rsp+arg_8], rbx
0x14001ccc9  mov     [rsp+arg_10], rsi
0x14001ccce  push    rdi
0x14001cccf  sub     rsp, 80h
0x14001ccd6  mov     rax, cs:__security_cookie
0x14001ccdd  xor     rax, rsp
0x14001cce0  mov     [rsp+88h+var_18], rax
0x14001cce5  xorps   xmm0, xmm0
0x14001cce8  xorps   xmm1, xmm1
0x14001cceb  mov     rbx, rcx
0x14001ccee  xor     r9d, r9d; Reserved
0x14001ccf1  xor     ecx, ecx; ClassGuid
0x14001ccf3  xor     r8d, r8d; MachineName
0x14001ccf6  xor     edx, edx; hwndParent
0x14001ccf8  movups  xmmword ptr [rsp+88h+DeviceInterfaceData.cbSize], xmm0
0x14001ccfd  movups  xmmword ptr [rsp+88h+DeviceInterfaceData.InterfaceClassGuid.Data4+4], xmm0
0x14001cd02  movups  xmmword ptr [rsp+88h+var_38.cbSize], xmm1
0x14001cd07  movups  xmmword ptr [rsp+88h+var_38.ClassGuid.Data4+4], xmm1
0x14001cd0c  call    cs:__imp_SetupDiCreateDeviceInfoListExA
0x14001cd12  mov     rsi, rax
0x14001cd15  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001cd19  jnz     short loc_14001CD22
0x14001cd1b  xor     ebx, ebx
0x14001cd1d  jmp     loc_14001CDAD
0x14001cd22  mov     edi, 20h ; ' '
0x14001cd27  lea     r9, [rsp+88h+DeviceInterfaceData]; DeviceInterfaceData
0x14001cd2c  xor     r8d, r8d; OpenFlags
0x14001cd2f  mov     [rsp+88h+DeviceInterfaceData.cbSize], edi
0x14001cd33  mov     rdx, rbx; DevicePath
0x14001cd36  mov     rcx, rsi; DeviceInfoSet
0x14001cd39  call    cs:__imp_SetupDiOpenDeviceInterfaceW
0x14001cd3f  mov     ebx, eax
0x14001cd41  test    eax, eax
0x14001cd43  jz      short loc_14001CD96
0x14001cd45  lea     rax, [rsp+88h+var_38]
0x14001cd4a  mov     [rsp+88h+var_38.cbSize], edi
0x14001cd4e  mov     [rsp+88h+DeviceInfoData], rax; DeviceInfoData
0x14001cd53  lea     rdx, [rsp+88h+DeviceInterfaceData]; DeviceInterfaceData
0x14001cd58  xor     r9d, r9d; DeviceInterfaceDetailDataSize
0x14001cd5b  mov     [rsp+88h+RequiredSize], 0; RequiredSize
0x14001cd64  xor     r8d, r8d; DeviceInterfaceDetailData
0x14001cd67  mov     rcx, rsi; DeviceInfoSet
0x14001cd6a  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x14001cd70  mov     ebx, eax
0x14001cd72  test    eax, eax
0x14001cd74  jnz     short loc_14001CD81
0x14001cd76  call    cs:__imp_GetLastError
0x14001cd7c  cmp     eax, 7Ah ; 'z'
0x14001cd7f  jnz     short loc_14001CD96
0x14001cd81  lea     r8, [rsp+88h+var_38]; DeviceInfoData
0x14001cd86  mov     rdx, rsi; DeviceInfoSet
0x14001cd89  mov     ecx, 5; InstallFunction
0x14001cd8e  call    cs:__imp_SetupDiCallClassInstaller
0x14001cd94  mov     ebx, eax
0x14001cd96  call    cs:__imp_GetLastError
0x14001cd9c  mov     rcx, rsi; DeviceInfoSet
0x14001cd9f  mov     edi, eax
0x14001cda1  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x14001cda7  test    ebx, ebx
0x14001cda9  jz      short loc_14001CDB5
0x14001cdab  mov     ebx, eax
0x14001cdad  call    cs:__imp_GetLastError
0x14001cdb3  mov     edi, eax
0x14001cdb5  mov     ecx, edi; dwErrCode
0x14001cdb7  call    cs:__imp_SetLastError
0x14001cdbd  mov     eax, ebx
0x14001cdbf  mov     rcx, [rsp+88h+var_18]
0x14001cdc4  xor     rcx, rsp; StackCookie
0x14001cdc7  call    __security_check_cookie
0x14001cdcc  lea     r11, [rsp+88h+var_8]
0x14001cdd4  mov     rbx, [r11+18h]
0x14001cdd8  mov     rsi, [r11+20h]
0x14001cddc  mov     rsp, r11
0x14001cddf  pop     rdi
0x14001cde0  retn
```
