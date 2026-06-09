# BthDevnodeUninstallDevice

- ea: `0x18002fdec`
- end: `0x18002ff40`
- name: `BthDevnodeUninstallDevice`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18002fb84`

## callees

- `0x180001790`
- `0x18002fdec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fefc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fefc`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x18002fe4c`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x18002fe4c`
- `DEVOBJ!DevObjUninstallDevice` at `0x18002feee`
- `DEVOBJ!DevObjUninstallDevice` at `0x18002feee`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiDestroyDeviceInfoList` at `0x18002fed8`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiDestroyDeviceInfoList` at `0x18002fed8`
- `ext-ms-win-setupapi-classinstallers-l1-1-1!SetupDiOpenDeviceInfoW` at `0x18002fea6`
- `ext-ms-win-setupapi-classinstallers-l1-1-1!SetupDiOpenDeviceInfoW` at `0x18002fea6`
- `ext-ms-win-setupapi-classinstallers-l1-1-1!SetupDiCreateDeviceInfoList` at `0x18002fe1b`
- `ext-ms-win-setupapi-classinstallers-l1-1-1!SetupDiCreateDeviceInfoList` at `0x18002fe1b`
- `ext-ms-win-newdev-config-l1-1-0!DiUninstallDevice` at `0x18002fecd`
- `ext-ms-win-newdev-config-l1-1-0!DiUninstallDevice` at `0x18002fecd`

## pseudocode

```c
__int64 __fastcall BthDevnodeUninstallDevice(__int64 a1, __int64 a2)
{
  HDEVINFO DeviceInfoList; // rdi
  BOOL v5; // esi
  signed int v6; // ebx
  signed int LastError; // eax
  signed int v8; // eax
  WINBOOL NeedReboot; // [rsp+30h] [rbp-278h] BYREF
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
0x18002fdec  mov     [rsp+arg_10], rbx
0x18002fdf1  push    rbp
0x18002fdf2  push    rsi
0x18002fdf3  push    rdi
0x18002fdf4  push    r12
0x18002fdf6  push    r14
0x18002fdf8  sub     rsp, 280h
0x18002fdff  mov     rax, cs:__security_cookie
0x18002fe06  xor     rax, rsp
0x18002fe09  mov     [rsp+2A8h+var_38], rax
0x18002fe11  mov     r14, rdx
0x18002fe14  mov     rbp, rcx
0x18002fe17  xor     edx, edx; hwndParent
0x18002fe19  xor     ecx, ecx; ClassGuid
0x18002fe1b  call    cs:__imp_SetupDiCreateDeviceInfoList
0x18002fe21  mov     rdi, rax
0x18002fe24  mov     r12d, 80004005h
0x18002fe2a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002fe2e  jz      loc_18002FEE2
0x18002fe34  xor     esi, esi
0x18002fe36  lea     r8, [rsp+2A8h+DeviceInstanceId]
0x18002fe3b  mov     r9d, 104h
0x18002fe41  mov     [rsp+2A8h+DeviceInfoData], rsi
0x18002fe46  mov     rdx, r14
0x18002fe49  mov     rcx, rbp
0x18002fe4c  call    cs:__imp_DevObjGetDeviceInstanceId
0x18002fe52  test    eax, eax
0x18002fe54  jz      short loc_18002FE5A
0x18002fe56  xor     ebx, ebx
0x18002fe58  jmp     short loc_18002FE75
0x18002fe5a  call    cs:__imp_GetLastError
0x18002fe60  mov     ebx, eax
0x18002fe62  test    eax, eax
0x18002fe64  jle     short loc_18002FE6F
0x18002fe66  movzx   ebx, ax
0x18002fe69  or      ebx, 80070000h
0x18002fe6f  test    ebx, ebx
0x18002fe71  cmovns  ebx, r12d
0x18002fe75  test    ebx, ebx
0x18002fe77  js      short loc_18002FED5
0x18002fe79  xorps   xmm0, xmm0
0x18002fe7c  mov     [rsp+2A8h+var_270.cbSize], 20h ; ' '
0x18002fe84  lea     rax, [rsp+2A8h+var_270]
0x18002fe89  xor     r9d, r9d; OpenFlags
0x18002fe8c  movups  xmmword ptr [rsp+2A8h+var_270.ClassGuid.Data1], xmm0
0x18002fe91  xor     r8d, r8d; hwndParent
0x18002fe94  mov     [rsp+2A8h+DeviceInfoData], rax; DeviceInfoData
0x18002fe99  lea     rdx, [rsp+2A8h+DeviceInstanceId]; DeviceInstanceId
0x18002fe9e  mov     rcx, rdi; DeviceInfoSet
0x18002fea1  movups  xmmword ptr [rsp+2A8h+var_270.ClassGuid.Data4+4], xmm0
0x18002fea6  call    cs:__imp_SetupDiOpenDeviceInfoW
0x18002feac  test    eax, eax
0x18002feae  jz      short loc_18002FED5
0x18002feb0  lea     rax, [rsp+2A8h+NeedReboot]
0x18002feb5  mov     [rsp+2A8h+NeedReboot], esi
0x18002feb9  xor     r9d, r9d; Flags
0x18002febc  mov     [rsp+2A8h+DeviceInfoData], rax; NeedReboot
0x18002fec1  lea     r8, [rsp+2A8h+var_270]; DeviceInfoData
0x18002fec6  mov     rdx, rdi; DeviceInfoSet
0x18002fec9  or      rcx, 0FFFFFFFFFFFFFFFFh; hwndParent
0x18002fecd  call    cs:__imp_DiUninstallDevice
0x18002fed3  mov     esi, eax
0x18002fed5  mov     rcx, rdi; DeviceInfoSet
0x18002fed8  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x18002fede  test    esi, esi
0x18002fee0  jnz     short loc_18002FF17
0x18002fee2  xor     r9d, r9d
0x18002fee5  xor     r8d, r8d
0x18002fee8  mov     rdx, r14
0x18002feeb  mov     rcx, rbp
0x18002feee  call    cs:__imp_DevObjUninstallDevice
0x18002fef4  test    eax, eax
0x18002fef6  jz      short loc_18002FEFC
0x18002fef8  xor     ebx, ebx
0x18002fefa  jmp     short loc_18002FF17
0x18002fefc  call    cs:__imp_GetLastError
0x18002ff02  mov     ebx, eax
0x18002ff04  test    eax, eax
0x18002ff06  jle     short loc_18002FF11
0x18002ff08  movzx   ebx, ax
0x18002ff0b  or      ebx, 80070000h
0x18002ff11  test    ebx, ebx
0x18002ff13  cmovns  ebx, r12d
0x18002ff17  mov     eax, ebx
0x18002ff19  mov     rcx, [rsp+2A8h+var_38]
0x18002ff21  xor     rcx, rsp; StackCookie
0x18002ff24  call    __security_check_cookie
0x18002ff29  mov     rbx, [rsp+2A8h+arg_10]
0x18002ff31  add     rsp, 280h
0x18002ff38  pop     r14
0x18002ff3a  pop     r12
0x18002ff3c  pop     rdi
0x18002ff3d  pop     rsi
0x18002ff3e  pop     rbp
0x18002ff3f  retn
```
