# ReinstallDevice(void *,_SP_DEVINFO_DATA *,int)

- ea: `0x180039c78`
- end: `0x180039d7f`
- name: `?ReinstallDevice@@YAHPEAXPEAU_SP_DEVINFO_DATA@@H@Z`
- size: `263`
- prototype: `__int64 __fastcall(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180039e40`

## callees

- `0x180039bc4`
- `0x180039c78`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180039cea`
- `KERNEL32!GetLastError` at `0x180039cea`
- `KERNEL32!SetLastError` at `0x180039d62`
- `KERNEL32!SetLastError` at `0x180039d62`
- `SETUPAPI!CM_Get_DevNode_Status` at `0x180039cb5`
- `SETUPAPI!CM_Get_DevNode_Status` at `0x180039cb5`
- `NEWDEV!DiInstallDevice` at `0x180039ce0`
- `NEWDEV!DiInstallDevice` at `0x180039ce0`

## string_xrefs

- `0x180039cf0`: `Device failed reinstall, error 0x%08X`
- `0x180039cfd`: `ReinstallDevice`
- `0x180039d25`: `ReinstallDevice`
- `0x180039d42`: `ReinstallDevice`
- `0x180039d18`: `Device successfully reinstalled`

## pseudocode

```c
_BOOL8 __fastcall ReinstallDevice(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData, int a3)
{
  DWORD DevInst; // r8d
  WINBOOL *NeedReboot; // rcx
  DWORD LastError; // ebx
  int v10; // [rsp+30h] [rbp-18h] BYREF
  ULONG v11; // [rsp+58h] [rbp+10h] BYREF
  ULONG v12; // [rsp+68h] [rbp+20h] BYREF

  v12 = 0;
  DevInst = DeviceInfoData->DevInst;
  v11 = 0;
  v10 = 0;
  if ( CM_Get_DevNode_Status(&v12, &v11, DevInst, 0) )
  {
    AslLogCallPrintf(0, "ReinstallDevice", 455, "Device not present");
    MarkDeviceForReinstall(DeviceInfoSet, DeviceInfoData);
    LastError = 1248;
  }
  else
  {
    NeedReboot = &v10;
    if ( a3 )
      NeedReboot = 0;
    if ( DiInstallDevice(0, DeviceInfoSet, DeviceInfoData, 0, 0, NeedReboot) )
    {
      LastError = 0;
      AslLogCallPrintf(0, "ReinstallDevice", 452, "Device successfully reinstalled");
    }
    else
    {
      LastError = GetLastError();
      AslLogCallPrintf(1, "ReinstallDevice", 449, "Device failed reinstall, error 0x%08X", LastError);
    }
  }
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x180039c78  mov     rax, rsp
0x180039c7b  mov     [rax+8], rbx
0x180039c7f  mov     [rax+18h], rsi
0x180039c83  push    rdi
0x180039c84  sub     rsp, 40h
0x180039c88  mov     esi, r8d
0x180039c8b  mov     dword ptr [rax+20h], 0
0x180039c92  mov     r8d, [rdx+14h]; dnDevInst
0x180039c96  mov     rbx, rdx
0x180039c99  mov     rdi, rcx
0x180039c9c  mov     dword ptr [rax+10h], 0
0x180039ca3  lea     rdx, [rax+10h]; pulProblemNumber
0x180039ca7  mov     dword ptr [rax-18h], 0
0x180039cae  xor     r9d, r9d; ulFlags
0x180039cb1  lea     rcx, [rax+20h]; pulStatus
0x180039cb5  call    cs:__imp_CM_Get_DevNode_Status
0x180039cbb  test    eax, eax
0x180039cbd  jnz     short loc_180039D35
0x180039cbf  xor     eax, eax
0x180039cc1  lea     rcx, [rsp+48h+var_18]
0x180039cc6  test    esi, esi
0x180039cc8  mov     r8, rbx; DeviceInfoData
0x180039ccb  mov     rdx, rdi; DeviceInfoSet
0x180039cce  cmovnz  rcx, rax
0x180039cd2  xor     r9d, r9d; DriverInfoData
0x180039cd5  mov     [rsp+48h+NeedReboot], rcx; NeedReboot
0x180039cda  xor     ecx, ecx; hwndParent
0x180039cdc  mov     [rsp+48h+Flags], eax; Flags
0x180039ce0  call    cs:__imp_DiInstallDevice
0x180039ce6  test    eax, eax
0x180039ce8  jnz     short loc_180039D16
0x180039cea  call    cs:__imp_GetLastError
0x180039cf0  lea     r9, aDeviceFailedRe; "Device failed reinstall, error 0x%08X"
0x180039cf7  mov     r8d, 1C1h
0x180039cfd  lea     rdx, aReinstalldevic; "ReinstallDevice"
0x180039d04  mov     [rsp+48h+Flags], eax
0x180039d08  mov     ecx, 1
0x180039d0d  mov     ebx, eax
0x180039d0f  call    AslLogCallPrintf
0x180039d14  jmp     short loc_180039D60
0x180039d16  xor     ebx, ebx
0x180039d18  lea     r9, aDeviceSuccessf; "Device successfully reinstalled"
0x180039d1f  mov     r8d, 1C4h
0x180039d25  lea     rdx, aReinstalldevic; "ReinstallDevice"
0x180039d2c  xor     ecx, ecx
0x180039d2e  call    AslLogCallPrintf
0x180039d33  jmp     short loc_180039D60
0x180039d35  lea     r9, aDeviceNotPrese; "Device not present"
0x180039d3c  mov     r8d, 1C7h
0x180039d42  lea     rdx, aReinstalldevic; "ReinstallDevice"
0x180039d49  xor     ecx, ecx
0x180039d4b  call    AslLogCallPrintf
0x180039d50  mov     rdx, rbx; DeviceInfoData
0x180039d53  mov     rcx, rdi; DeviceInfoSet
0x180039d56  call    ?MarkDeviceForReinstall@@YAKPEAXPEAU_SP_DEVINFO_DATA@@@Z; MarkDeviceForReinstall(void *,_SP_DEVINFO_DATA *)
0x180039d5b  mov     ebx, 4E0h
0x180039d60  mov     ecx, ebx; dwErrCode
0x180039d62  call    cs:__imp_SetLastError
0x180039d68  mov     rsi, [rsp+48h+arg_10]
0x180039d6d  xor     eax, eax
0x180039d6f  test    ebx, ebx
0x180039d71  mov     rbx, [rsp+48h+arg_0]
0x180039d76  setz    al
0x180039d79  add     rsp, 40h
0x180039d7d  pop     rdi
0x180039d7e  retn
```
