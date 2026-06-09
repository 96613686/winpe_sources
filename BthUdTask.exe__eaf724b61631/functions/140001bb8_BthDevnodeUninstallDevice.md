# BthDevnodeUninstallDevice

- ea: `0x140001bb8`
- end: `0x140001d0c`
- name: `BthDevnodeUninstallDevice`
- size: `340`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140001950`

## callees

- `0x140001bb8`
- `0x140002010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140001c26`
- `KERNEL32!GetLastError` at `0x140001cc8`
- `KERNEL32!GetLastError` at `0x140001c26`
- `KERNEL32!GetLastError` at `0x140001cc8`
- `newdev!DiUninstallDevice` at `0x140001c99`
- `newdev!DiUninstallDevice` at `0x140001c99`
- `DEVOBJ!DevObjUninstallDevice` at `0x140001cba`
- `DEVOBJ!DevObjUninstallDevice` at `0x140001cba`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x140001c18`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x140001c18`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiDestroyDeviceInfoList` at `0x140001ca4`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiDestroyDeviceInfoList` at `0x140001ca4`
- `ext-ms-win-setupapi-classinstallers-l1-1-1!SetupDiOpenDeviceInfoW` at `0x140001c72`
- `ext-ms-win-setupapi-classinstallers-l1-1-1!SetupDiOpenDeviceInfoW` at `0x140001c72`
- `ext-ms-win-setupapi-classinstallers-l1-1-1!SetupDiCreateDeviceInfoList` at `0x140001be7`
- `ext-ms-win-setupapi-classinstallers-l1-1-1!SetupDiCreateDeviceInfoList` at `0x140001be7`

## pseudocode

```c
__int64 __fastcall BthDevnodeUninstallDevice(__int64 a1, __int64 a2)
{
  HDEVINFO DeviceInfoList; // rdi
  BOOL v5; // esi
  signed int v6; // ebx
  signed int LastError; // eax
  signed int v8; // eax
  BOOL NeedReboot; // [rsp+30h] [rbp-278h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+38h] [rbp-270h] BYREF
  WCHAR DeviceInstanceId[264]; // [rsp+60h] [rbp-248h] BYREF

  DeviceInfoList = SetupDiCreateDeviceInfoList(0, 0);
  if ( DeviceInfoList == (HDEVINFO)-1LL )
    goto LABEL_21;
  v5 = 0;
  if ( (unsigned int)DevObjGetDeviceInstanceId(a1, a2, DeviceInstanceId, 260, 0) )
  {
    v6 = 0;
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147467259;
  }
  if ( v6 >= 0 )
  {
    DeviceInfoData.cbSize = 32;
    memset(&DeviceInfoData.ClassGuid, 0, 28);
    if ( SetupDiOpenDeviceInfoW(DeviceInfoList, DeviceInstanceId, 0, 0, &DeviceInfoData) )
    {
      NeedReboot = 0;
      v5 = DiUninstallDevice(HWND_MESSAGE|0x2LL, DeviceInfoList, &DeviceInfoData, 0, &NeedReboot);
    }
  }
  SetupDiDestroyDeviceInfoList(DeviceInfoList);
  if ( !v5 )
  {
LABEL_21:
    if ( (unsigned int)DevObjUninstallDevice(a1, a2, 0, 0) )
    {
      return 0;
    }
    else
    {
      v8 = GetLastError();
      v6 = v8;
      if ( v8 > 0 )
        v6 = (unsigned __int16)v8 | 0x80070000;
      if ( v6 >= 0 )
        return (unsigned int)-2147467259;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140001bb8  mov     [rsp+arg_10], rbx
0x140001bbd  push    rbp
0x140001bbe  push    rsi
0x140001bbf  push    rdi
0x140001bc0  push    r12
0x140001bc2  push    r14
0x140001bc4  sub     rsp, 280h
0x140001bcb  mov     rax, cs:__security_cookie
0x140001bd2  xor     rax, rsp
0x140001bd5  mov     [rsp+2A8h+var_38], rax
0x140001bdd  mov     r14, rdx
0x140001be0  mov     rbp, rcx
0x140001be3  xor     edx, edx; hwndParent
0x140001be5  xor     ecx, ecx; ClassGuid
0x140001be7  call    cs:__imp_SetupDiCreateDeviceInfoList
0x140001bed  mov     rdi, rax
0x140001bf0  mov     r12d, 80004005h
0x140001bf6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140001bfa  jz      loc_140001CAE
0x140001c00  xor     esi, esi
0x140001c02  lea     r8, [rsp+2A8h+DeviceInstanceId]
0x140001c07  mov     r9d, 104h
0x140001c0d  mov     [rsp+2A8h+DeviceInfoData], rsi
0x140001c12  mov     rdx, r14
0x140001c15  mov     rcx, rbp
0x140001c18  call    cs:__imp_DevObjGetDeviceInstanceId
0x140001c1e  test    eax, eax
0x140001c20  jz      short loc_140001C26
0x140001c22  xor     ebx, ebx
0x140001c24  jmp     short loc_140001C41
0x140001c26  call    cs:__imp_GetLastError
0x140001c2c  mov     ebx, eax
0x140001c2e  test    eax, eax
0x140001c30  jle     short loc_140001C3B
0x140001c32  movzx   ebx, ax
0x140001c35  or      ebx, 80070000h
0x140001c3b  test    ebx, ebx
0x140001c3d  cmovns  ebx, r12d
0x140001c41  test    ebx, ebx
0x140001c43  js      short loc_140001CA1
0x140001c45  xorps   xmm0, xmm0
0x140001c48  mov     [rsp+2A8h+var_270.cbSize], 20h ; ' '
0x140001c50  lea     rax, [rsp+2A8h+var_270]
0x140001c55  xor     r9d, r9d; OpenFlags
0x140001c58  movups  xmmword ptr [rsp+2A8h+var_270.ClassGuid.Data1], xmm0
0x140001c5d  xor     r8d, r8d; hwndParent
0x140001c60  mov     [rsp+2A8h+DeviceInfoData], rax; DeviceInfoData
0x140001c65  lea     rdx, [rsp+2A8h+DeviceInstanceId]; DeviceInstanceId
0x140001c6a  mov     rcx, rdi; DeviceInfoSet
0x140001c6d  movups  xmmword ptr [rsp+2A8h+var_270.ClassGuid.Data4+4], xmm0
0x140001c72  call    cs:__imp_SetupDiOpenDeviceInfoW
0x140001c78  test    eax, eax
0x140001c7a  jz      short loc_140001CA1
0x140001c7c  lea     rax, [rsp+2A8h+NeedReboot]
0x140001c81  mov     [rsp+2A8h+NeedReboot], esi
0x140001c85  xor     r9d, r9d; Flags
0x140001c88  mov     [rsp+2A8h+DeviceInfoData], rax; NeedReboot
0x140001c8d  lea     r8, [rsp+2A8h+var_270]; DeviceInfoData
0x140001c92  mov     rdx, rdi; DeviceInfoSet
0x140001c95  or      rcx, 0FFFFFFFFFFFFFFFFh; hwndParent
0x140001c99  call    cs:__imp_DiUninstallDevice
0x140001c9f  mov     esi, eax
0x140001ca1  mov     rcx, rdi; DeviceInfoSet
0x140001ca4  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x140001caa  test    esi, esi
0x140001cac  jnz     short loc_140001CE3
0x140001cae  xor     r9d, r9d
0x140001cb1  xor     r8d, r8d
0x140001cb4  mov     rdx, r14
0x140001cb7  mov     rcx, rbp
0x140001cba  call    cs:__imp_DevObjUninstallDevice
0x140001cc0  test    eax, eax
0x140001cc2  jz      short loc_140001CC8
0x140001cc4  xor     ebx, ebx
0x140001cc6  jmp     short loc_140001CE3
0x140001cc8  call    cs:__imp_GetLastError
0x140001cce  mov     ebx, eax
0x140001cd0  test    eax, eax
0x140001cd2  jle     short loc_140001CDD
0x140001cd4  movzx   ebx, ax
0x140001cd7  or      ebx, 80070000h
0x140001cdd  test    ebx, ebx
0x140001cdf  cmovns  ebx, r12d
0x140001ce3  mov     eax, ebx
0x140001ce5  mov     rcx, [rsp+2A8h+var_38]
0x140001ced  xor     rcx, rsp; StackCookie
0x140001cf0  call    __security_check_cookie
0x140001cf5  mov     rbx, [rsp+2A8h+arg_10]
0x140001cfd  add     rsp, 280h
0x140001d04  pop     r14
0x140001d06  pop     r12
0x140001d08  pop     rdi
0x140001d09  pop     rsi
0x140001d0a  pop     rbp
0x140001d0b  retn
```
