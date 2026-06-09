# InitializeUninstallVolume_IsVolumeHidden

- ea: `0x14001eaa4`
- end: `0x14001eb8d`
- name: `InitializeUninstallVolume_IsVolumeHidden`
- size: `233`
- prototype: `__int64 __fastcall(PCWSTR DevicePath)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14001e464`

## callees

- `0x14001eaa4`
- `0x14001ed86`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14001eb68`
- `KERNEL32!SetLastError` at `0x14001eb68`
- `KERNEL32!GetLastError` at `0x14001eaf6`
- `KERNEL32!GetLastError` at `0x14001eb42`
- `KERNEL32!GetLastError` at `0x14001eb5e`
- `KERNEL32!GetLastError` at `0x14001eaf6`
- `KERNEL32!GetLastError` at `0x14001eb42`
- `KERNEL32!GetLastError` at `0x14001eb5e`
- `SETUPAPI!SetupDiCreateDeviceInfoListExA` at `0x14001eae5`
- `SETUPAPI!SetupDiCreateDeviceInfoListExA` at `0x14001eae5`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x14001eb16`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x14001eb16`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x14001eb52`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x14001eb52`

## pseudocode

```c
__int64 __fastcall InitializeUninstallVolume_IsVolumeHidden(PCWSTR DevicePath, _DWORD *a2)
{
  HDEVINFO DeviceInfoList; // rax
  void *v5; // rsi
  unsigned int v6; // ebx
  DWORD LastError; // edi
  BOOL v8; // eax
  struct _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+20h] [rbp-38h] BYREF

  *a2 = 0;
  memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
  DeviceInfoList = SetupDiCreateDeviceInfoListExA(0, 0, 0, 0);
  v5 = DeviceInfoList;
  if ( DeviceInfoList == (HDEVINFO)-1LL )
  {
    v6 = 0;
    LastError = GetLastError();
LABEL_6:
    v8 = SetupDiDestroyDeviceInfoList(v5);
    if ( v6 )
    {
      v6 = v8;
      LastError = GetLastError();
    }
    goto LABEL_8;
  }
  DeviceInterfaceData.cbSize = 32;
  v6 = SetupDiOpenDeviceInterfaceW(DeviceInfoList, DevicePath, 0, &DeviceInterfaceData);
  if ( v6 )
    *a2 = memcmp_0(&DeviceInterfaceData.InterfaceClassGuid, &GUID_DEVINTERFACE_HIDDEN_VOLUME, 0x10u) == 0;
  LastError = GetLastError();
  if ( v5 )
    goto LABEL_6;
LABEL_8:
  SetLastError(LastError);
  return v6;
}

```

## disassembly

```asm
0x14001eaa4  mov     [rsp+arg_10], rbx
0x14001eaa9  mov     [rsp+arg_18], rsi
0x14001eaae  push    rdi
0x14001eaaf  sub     rsp, 50h
0x14001eab3  mov     rax, cs:__security_cookie
0x14001eaba  xor     rax, rsp
0x14001eabd  mov     [rsp+58h+var_18], rax
0x14001eac2  xorps   xmm0, xmm0
0x14001eac5  mov     dword ptr [rdx], 0
0x14001eacb  mov     rdi, rdx
0x14001eace  mov     rbx, rcx
0x14001ead1  xor     edx, edx; hwndParent
0x14001ead3  xor     ecx, ecx; ClassGuid
0x14001ead5  xor     r9d, r9d; Reserved
0x14001ead8  xor     r8d, r8d; MachineName
0x14001eadb  movups  xmmword ptr [rsp+58h+DeviceInterfaceData.cbSize], xmm0
0x14001eae0  movups  xmmword ptr [rsp+58h+DeviceInterfaceData.InterfaceClassGuid.Data4+4], xmm0
0x14001eae5  call    cs:__imp_SetupDiCreateDeviceInfoListExA
0x14001eaeb  mov     rsi, rax
0x14001eaee  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001eaf2  jnz     short loc_14001EB00
0x14001eaf4  xor     ebx, ebx
0x14001eaf6  call    cs:__imp_GetLastError
0x14001eafc  mov     edi, eax
0x14001eafe  jmp     short loc_14001EB4F
0x14001eb00  lea     r9, [rsp+58h+DeviceInterfaceData]; DeviceInterfaceData
0x14001eb05  mov     [rsp+58h+DeviceInterfaceData.cbSize], 20h ; ' '
0x14001eb0d  xor     r8d, r8d; OpenFlags
0x14001eb10  mov     rdx, rbx; DevicePath
0x14001eb13  mov     rcx, rsi; DeviceInfoSet
0x14001eb16  call    cs:__imp_SetupDiOpenDeviceInterfaceW
0x14001eb1c  mov     ebx, eax
0x14001eb1e  test    eax, eax
0x14001eb20  jz      short loc_14001EB42
0x14001eb22  mov     r8d, 10h; Size
0x14001eb28  lea     rdx, GUID_DEVINTERFACE_HIDDEN_VOLUME; Buf2
0x14001eb2f  lea     rcx, [rsp+58h+DeviceInterfaceData.InterfaceClassGuid]; Buf1
0x14001eb34  call    memcmp_0
0x14001eb39  xor     ecx, ecx
0x14001eb3b  test    eax, eax
0x14001eb3d  setz    cl
0x14001eb40  mov     [rdi], ecx
0x14001eb42  call    cs:__imp_GetLastError
0x14001eb48  mov     edi, eax
0x14001eb4a  test    rsi, rsi
0x14001eb4d  jz      short loc_14001EB66
0x14001eb4f  mov     rcx, rsi; DeviceInfoSet
0x14001eb52  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x14001eb58  test    ebx, ebx
0x14001eb5a  jz      short loc_14001EB66
0x14001eb5c  mov     ebx, eax
0x14001eb5e  call    cs:__imp_GetLastError
0x14001eb64  mov     edi, eax
0x14001eb66  mov     ecx, edi; dwErrCode
0x14001eb68  call    cs:__imp_SetLastError
0x14001eb6e  mov     eax, ebx
0x14001eb70  mov     rcx, [rsp+58h+var_18]
0x14001eb75  xor     rcx, rsp; StackCookie
0x14001eb78  call    __security_check_cookie
0x14001eb7d  mov     rbx, [rsp+58h+arg_10]
0x14001eb82  mov     rsi, [rsp+58h+arg_18]
0x14001eb87  add     rsp, 50h
0x14001eb8b  pop     rdi
0x14001eb8c  retn
```
