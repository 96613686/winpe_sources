# GetDeviceContainer(ushort const *,ushort *)

- ea: `0x14001c5d0`
- end: `0x14001c747`
- name: `?GetDeviceContainer@@YAHPEBGPEAG@Z`
- size: `375`
- prototype: `__int64 __fastcall(PCWSTR DeviceInstanceId, LPOLESTR lpsz)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14001c9d0`

## callees

- `0x14001c5d0`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14001c6d1`
- `KERNEL32!SetLastError` at `0x14001c71b`
- `KERNEL32!SetLastError` at `0x14001c6d1`
- `KERNEL32!SetLastError` at `0x14001c71b`
- `KERNEL32!GetLastError` at `0x14001c6df`
- `KERNEL32!GetLastError` at `0x14001c6fa`
- `KERNEL32!GetLastError` at `0x14001c711`
- `KERNEL32!GetLastError` at `0x14001c6df`
- `KERNEL32!GetLastError` at `0x14001c6fa`
- `KERNEL32!GetLastError` at `0x14001c711`
- `ole32!StringFromGUID2` at `0x14001c6bd`
- `ole32!StringFromGUID2` at `0x14001c6bd`
- `SETUPAPI!SetupDiDeleteDeviceInfo` at `0x14001c6ee`
- `SETUPAPI!SetupDiDeleteDeviceInfo` at `0x14001c6ee`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x14001c705`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x14001c705`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x14001c653`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x14001c653`
- `SETUPAPI!SetupDiCreateDeviceInfoListExW` at `0x14001c621`
- `SETUPAPI!SetupDiCreateDeviceInfoListExW` at `0x14001c621`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x14001c698`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x14001c698`

## pseudocode

```c
__int64 __fastcall GetDeviceContainer(PCWSTR DeviceInstanceId, LPOLESTR lpsz)
{
  HDEVINFO DeviceInfoList; // rsi
  unsigned int DevicePropertyW; // edi
  int v6; // ebx
  DWORD LastError; // ebx
  BOOL v8; // eax
  BOOL v9; // eax
  DEVPROPTYPE PropertyType; // [rsp+40h] [rbp-40h] BYREF
  BYTE PropertyBuffer[16]; // [rsp+48h] [rbp-38h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+58h] [rbp-28h] BYREF

  PropertyType = 0;
  *lpsz = 0;
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  *(_OWORD *)PropertyBuffer = 0;
  DeviceInfoList = SetupDiCreateDeviceInfoListExW(0, 0, 0, 0);
  if ( DeviceInfoList == (HDEVINFO)-1LL )
  {
    DevicePropertyW = 0;
LABEL_14:
    LastError = GetLastError();
    goto LABEL_15;
  }
  DeviceInfoData.cbSize = 32;
  if ( !SetupDiOpenDeviceInfoW(DeviceInfoList, DeviceInstanceId, 0, 0, &DeviceInfoData) )
  {
    DevicePropertyW = 0;
LABEL_11:
    LastError = GetLastError();
    goto LABEL_12;
  }
  DevicePropertyW = SetupDiGetDevicePropertyW(
                      DeviceInfoList,
                      &DeviceInfoData,
                      &DEVPKEY_Device_ContainerId,
                      &PropertyType,
                      PropertyBuffer,
                      0x10u,
                      0,
                      0);
  if ( DevicePropertyW && PropertyType == 13 && *(_DWORD *)PropertyBuffer )
  {
    v6 = StringFromGUID2((const GUID *const)PropertyBuffer, lpsz, 39);
    lpsz[38] = 0;
    SetLastError(0x57u);
    DevicePropertyW = v6 != 0;
  }
  LastError = GetLastError();
  v8 = SetupDiDeleteDeviceInfo(DeviceInfoList, &DeviceInfoData);
  if ( DevicePropertyW )
  {
    DevicePropertyW = v8;
    goto LABEL_11;
  }
LABEL_12:
  v9 = SetupDiDestroyDeviceInfoList(DeviceInfoList);
  if ( DevicePropertyW )
  {
    DevicePropertyW = v9;
    goto LABEL_14;
  }
LABEL_15:
  SetLastError(LastError);
  return DevicePropertyW;
}

```

## disassembly

```asm
0x14001c5d0  mov     [rsp-18h+arg_10], rbx
0x14001c5d5  mov     [rsp-18h+arg_18], rsi
0x14001c5da  push    rbp
0x14001c5db  push    rdi
0x14001c5dc  push    r14
0x14001c5de  mov     rbp, rsp
0x14001c5e1  sub     rsp, 80h
0x14001c5e8  mov     rax, cs:__security_cookie
0x14001c5ef  xor     rax, rsp
0x14001c5f2  mov     [rbp+var_8], rax
0x14001c5f6  xorps   xmm0, xmm0
0x14001c5f9  mov     [rbp+PropertyType], 0
0x14001c600  xor     eax, eax
0x14001c602  mov     r14, rdx
0x14001c605  mov     [rdx], ax
0x14001c608  mov     rbx, rcx
0x14001c60b  xor     edx, edx; hwndParent
0x14001c60d  xor     r9d, r9d; Reserved
0x14001c610  xor     r8d, r8d; MachineName
0x14001c613  xor     ecx, ecx; ClassGuid
0x14001c615  movups  xmmword ptr [rbp+var_28.cbSize], xmm0
0x14001c619  movups  xmmword ptr [rbp+var_28.ClassGuid.Data4+4], xmm0
0x14001c61d  movups  xmmword ptr [rbp+PropertyBuffer], xmm0
0x14001c621  call    cs:__imp_SetupDiCreateDeviceInfoListExW
0x14001c627  mov     rsi, rax
0x14001c62a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001c62e  jnz     short loc_14001C637
0x14001c630  xor     edi, edi
0x14001c632  jmp     loc_14001C711
0x14001c637  lea     rax, [rbp+var_28]
0x14001c63b  mov     [rbp+var_28.cbSize], 20h ; ' '
0x14001c642  xor     r9d, r9d; OpenFlags
0x14001c645  mov     [rsp+80h+DeviceInfoData], rax; DeviceInfoData
0x14001c64a  xor     r8d, r8d; hwndParent
0x14001c64d  mov     rdx, rbx; DeviceInstanceId
0x14001c650  mov     rcx, rsi; DeviceInfoSet
0x14001c653  call    cs:__imp_SetupDiOpenDeviceInfoW
0x14001c659  test    eax, eax
0x14001c65b  jnz     short loc_14001C664
0x14001c65d  xor     edi, edi
0x14001c65f  jmp     loc_14001C6FA
0x14001c664  mov     [rsp+80h+Flags], 0; Flags
0x14001c66c  lea     rax, [rbp+PropertyBuffer]
0x14001c670  mov     [rsp+80h+RequiredSize], 0; RequiredSize
0x14001c679  lea     r9, [rbp+PropertyType]; PropertyType
0x14001c67d  mov     [rsp+80h+PropertyBufferSize], 10h; PropertyBufferSize
0x14001c685  lea     r8, DEVPKEY_Device_ContainerId; PropertyKey
0x14001c68c  lea     rdx, [rbp+var_28]; DeviceInfoData
0x14001c690  mov     [rsp+80h+DeviceInfoData], rax; PropertyBuffer
0x14001c695  mov     rcx, rsi; DeviceInfoSet
0x14001c698  call    cs:__imp_SetupDiGetDevicePropertyW
0x14001c69e  mov     edi, eax
0x14001c6a0  test    eax, eax
0x14001c6a2  jz      short loc_14001C6DF
0x14001c6a4  cmp     [rbp+PropertyType], 0Dh
0x14001c6a8  jnz     short loc_14001C6DF
0x14001c6aa  cmp     dword ptr [rbp+PropertyBuffer], 0
0x14001c6ae  jz      short loc_14001C6DF
0x14001c6b0  mov     r8d, 27h ; '''; cchMax
0x14001c6b6  lea     rcx, [rbp+PropertyBuffer]; rguid
0x14001c6ba  mov     rdx, r14; lpsz
0x14001c6bd  call    cs:__imp_StringFromGUID2
0x14001c6c3  xor     ecx, ecx
0x14001c6c5  mov     ebx, eax
0x14001c6c7  mov     [r14+4Ch], cx
0x14001c6cc  mov     ecx, 57h ; 'W'; dwErrCode
0x14001c6d1  call    cs:__imp_SetLastError
0x14001c6d7  xor     edi, edi
0x14001c6d9  test    ebx, ebx
0x14001c6db  setnz   dil
0x14001c6df  call    cs:__imp_GetLastError
0x14001c6e5  lea     rdx, [rbp+var_28]; DeviceInfoData
0x14001c6e9  mov     rcx, rsi; DeviceInfoSet
0x14001c6ec  mov     ebx, eax
0x14001c6ee  call    cs:__imp_SetupDiDeleteDeviceInfo
0x14001c6f4  test    edi, edi
0x14001c6f6  jz      short loc_14001C702
0x14001c6f8  mov     edi, eax
0x14001c6fa  call    cs:__imp_GetLastError
0x14001c700  mov     ebx, eax
0x14001c702  mov     rcx, rsi; DeviceInfoSet
0x14001c705  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x14001c70b  test    edi, edi
0x14001c70d  jz      short loc_14001C719
0x14001c70f  mov     edi, eax
0x14001c711  call    cs:__imp_GetLastError
0x14001c717  mov     ebx, eax
0x14001c719  mov     ecx, ebx; dwErrCode
0x14001c71b  call    cs:__imp_SetLastError
0x14001c721  mov     eax, edi
0x14001c723  mov     rcx, [rbp+var_8]
0x14001c727  xor     rcx, rsp; StackCookie
0x14001c72a  call    __security_check_cookie
0x14001c72f  lea     r11, [rsp+80h+var_s0]
0x14001c737  mov     rbx, [r11+30h]
0x14001c73b  mov     rsi, [r11+38h]
0x14001c73f  mov     rsp, r11
0x14001c742  pop     r14
0x14001c744  pop     rdi
0x14001c745  pop     rbp
0x14001c746  retn
```
