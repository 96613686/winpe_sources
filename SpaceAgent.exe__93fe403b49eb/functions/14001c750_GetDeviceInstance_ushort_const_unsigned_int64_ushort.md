# GetDeviceInstance(ushort const *,unsigned __int64 *,ushort *)

- ea: `0x14001c750`
- end: `0x14001c89a`
- name: `?GetDeviceInstance@@YAHPEBGPEA_KPEAG@Z`
- size: `330`
- prototype: `__int64 __fastcall(PCWSTR DevicePath, unsigned __int64 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14001c8a0`

## callees

- `0x14001c750`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14001c878`
- `KERNEL32!SetLastError` at `0x14001c878`
- `KERNEL32!GetLastError` at `0x14001c7bf`
- `KERNEL32!GetLastError` at `0x14001c7ec`
- `KERNEL32!GetLastError` at `0x14001c828`
- `KERNEL32!GetLastError` at `0x14001c852`
- `KERNEL32!GetLastError` at `0x14001c7bf`
- `KERNEL32!GetLastError` at `0x14001c7ec`
- `KERNEL32!GetLastError` at `0x14001c828`
- `KERNEL32!GetLastError` at `0x14001c852`
- `SETUPAPI!SetupDiDeleteDeviceInterfaceData` at `0x14001c861`
- `SETUPAPI!SetupDiDeleteDeviceInterfaceData` at `0x14001c861`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x14001c7e0`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x14001c7e0`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x14001c86a`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x14001c86a`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x14001c81c`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x14001c81c`
- `SETUPAPI!SetupDiCreateDeviceInfoListExW` at `0x14001c7ae`
- `SETUPAPI!SetupDiCreateDeviceInfoListExW` at `0x14001c7ae`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x14001c84a`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x14001c84a`

## pseudocode

```c
__int64 __fastcall GetDeviceInstance(PCWSTR DevicePath, unsigned __int64 *a2, unsigned __int16 *a3)
{
  bool v3; // zf
  DWORD v4; // eax
  HDEVINFO DeviceInfoList; // rax
  void *v9; // rdi
  unsigned int DeviceInterfaceDetailW; // esi
  DWORD LastError; // ebx
  DWORD DeviceInstanceIdSize; // [rsp+30h] [rbp-50h] BYREF
  struct _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+38h] [rbp-48h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+58h] [rbp-28h] BYREF

  v3 = *a2 == 0;
  v4 = *(_DWORD *)a2;
  memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
  DeviceInstanceIdSize = v4;
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  if ( !v3 && a3 )
    *a3 = 0;
  DeviceInfoList = SetupDiCreateDeviceInfoListExW(0, 0, 0, 0);
  v9 = DeviceInfoList;
  if ( DeviceInfoList == (HDEVINFO)-1LL )
  {
    DeviceInterfaceDetailW = 0;
    LastError = GetLastError();
  }
  else
  {
    DeviceInterfaceData.cbSize = 32;
    if ( SetupDiOpenDeviceInterfaceW(DeviceInfoList, DevicePath, 0, &DeviceInterfaceData) )
    {
      DeviceInfoData.cbSize = 32;
      DeviceInterfaceDetailW = SetupDiGetDeviceInterfaceDetailW(v9, &DeviceInterfaceData, 0, 0, 0, &DeviceInfoData);
      if ( DeviceInterfaceDetailW || GetLastError() == 122 )
        DeviceInterfaceDetailW = SetupDiGetDeviceInstanceIdW(
                                   v9,
                                   &DeviceInfoData,
                                   a3,
                                   DeviceInstanceIdSize,
                                   &DeviceInstanceIdSize);
      LastError = GetLastError();
      SetupDiDeleteDeviceInterfaceData(v9, &DeviceInterfaceData);
    }
    else
    {
      DeviceInterfaceDetailW = 0;
      LastError = GetLastError();
    }
    SetupDiDestroyDeviceInfoList(v9);
  }
  *a2 = DeviceInstanceIdSize;
  SetLastError(LastError);
  return DeviceInterfaceDetailW;
}

```

## disassembly

```asm
0x14001c750  push    rbp
0x14001c752  push    rbx
0x14001c753  push    rsi
0x14001c754  push    rdi
0x14001c755  push    r14
0x14001c757  mov     rbp, rsp
0x14001c75a  sub     rsp, 80h
0x14001c761  mov     rax, cs:__security_cookie
0x14001c768  xor     rax, rsp
0x14001c76b  mov     [rbp+var_8], rax
0x14001c76f  cmp     qword ptr [rdx], 0
0x14001c773  xorps   xmm0, xmm0
0x14001c776  mov     eax, [rdx]
0x14001c778  xorps   xmm1, xmm1
0x14001c77b  movups  xmmword ptr [rbp+DeviceInterfaceData.cbSize], xmm0
0x14001c77f  mov     rbx, r8
0x14001c782  mov     r14, rdx
0x14001c785  movups  xmmword ptr [rbp+DeviceInterfaceData.InterfaceClassGuid.Data4+4], xmm0
0x14001c789  mov     rsi, rcx
0x14001c78c  mov     [rbp+DeviceInstanceIdSize], eax
0x14001c78f  movups  xmmword ptr [rbp+var_28.cbSize], xmm1
0x14001c793  movups  xmmword ptr [rbp+var_28.ClassGuid.Data4+4], xmm1
0x14001c797  jbe     short loc_14001C7A4
0x14001c799  test    rbx, rbx
0x14001c79c  jz      short loc_14001C7A4
0x14001c79e  xor     eax, eax
0x14001c7a0  mov     [r8], ax
0x14001c7a4  xor     r9d, r9d; Reserved
0x14001c7a7  xor     r8d, r8d; MachineName
0x14001c7aa  xor     edx, edx; hwndParent
0x14001c7ac  xor     ecx, ecx; ClassGuid
0x14001c7ae  call    cs:__imp_SetupDiCreateDeviceInfoListExW
0x14001c7b4  mov     rdi, rax
0x14001c7b7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001c7bb  jnz     short loc_14001C7CC
0x14001c7bd  xor     esi, esi
0x14001c7bf  call    cs:__imp_GetLastError
0x14001c7c5  mov     ebx, eax
0x14001c7c7  jmp     loc_14001C870
0x14001c7cc  lea     r9, [rbp+DeviceInterfaceData]; DeviceInterfaceData
0x14001c7d0  mov     [rbp+DeviceInterfaceData.cbSize], 20h ; ' '
0x14001c7d7  xor     r8d, r8d; OpenFlags
0x14001c7da  mov     rdx, rsi; DevicePath
0x14001c7dd  mov     rcx, rdi; DeviceInfoSet
0x14001c7e0  call    cs:__imp_SetupDiOpenDeviceInterfaceW
0x14001c7e6  test    eax, eax
0x14001c7e8  jnz     short loc_14001C7F6
0x14001c7ea  xor     esi, esi
0x14001c7ec  call    cs:__imp_GetLastError
0x14001c7f2  mov     ebx, eax
0x14001c7f4  jmp     short loc_14001C867
0x14001c7f6  lea     rax, [rbp+var_28]
0x14001c7fa  mov     [rbp+var_28.cbSize], 20h ; ' '
0x14001c801  mov     [rsp+80h+DeviceInfoData], rax; DeviceInfoData
0x14001c806  lea     rdx, [rbp+DeviceInterfaceData]; DeviceInterfaceData
0x14001c80a  xor     r9d, r9d; DeviceInterfaceDetailDataSize
0x14001c80d  mov     [rsp+80h+RequiredSize], 0; RequiredSize
0x14001c816  xor     r8d, r8d; DeviceInterfaceDetailData
0x14001c819  mov     rcx, rdi; DeviceInfoSet
0x14001c81c  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x14001c822  mov     esi, eax
0x14001c824  test    eax, eax
0x14001c826  jnz     short loc_14001C833
0x14001c828  call    cs:__imp_GetLastError
0x14001c82e  cmp     eax, 7Ah ; 'z'
0x14001c831  jnz     short loc_14001C852
0x14001c833  mov     r9d, [rbp+DeviceInstanceIdSize]; DeviceInstanceIdSize
0x14001c837  lea     rax, [rbp+DeviceInstanceIdSize]
0x14001c83b  mov     r8, rbx; DeviceInstanceId
0x14001c83e  mov     [rsp+80h+RequiredSize], rax; RequiredSize
0x14001c843  lea     rdx, [rbp+var_28]; DeviceInfoData
0x14001c847  mov     rcx, rdi; DeviceInfoSet
0x14001c84a  call    cs:__imp_SetupDiGetDeviceInstanceIdW
0x14001c850  mov     esi, eax
0x14001c852  call    cs:__imp_GetLastError
0x14001c858  lea     rdx, [rbp+DeviceInterfaceData]; DeviceInterfaceData
0x14001c85c  mov     rcx, rdi; DeviceInfoSet
0x14001c85f  mov     ebx, eax
0x14001c861  call    cs:__imp_SetupDiDeleteDeviceInterfaceData
0x14001c867  mov     rcx, rdi; DeviceInfoSet
0x14001c86a  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x14001c870  mov     eax, [rbp+DeviceInstanceIdSize]
0x14001c873  mov     ecx, ebx; dwErrCode
0x14001c875  mov     [r14], rax
0x14001c878  call    cs:__imp_SetLastError
0x14001c87e  mov     eax, esi
0x14001c880  mov     rcx, [rbp+var_8]
0x14001c884  xor     rcx, rsp; StackCookie
0x14001c887  call    __security_check_cookie
0x14001c88c  add     rsp, 80h
0x14001c893  pop     r14
0x14001c895  pop     rdi
0x14001c896  pop     rsi
0x14001c897  pop     rbx
0x14001c898  pop     rbp
0x14001c899  retn
```
