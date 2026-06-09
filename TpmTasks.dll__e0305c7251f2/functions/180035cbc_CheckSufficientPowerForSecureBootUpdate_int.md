# CheckSufficientPowerForSecureBootUpdate(int *)

- ea: `0x180035cbc`
- end: `0x180035d94`
- name: `?CheckSufficientPowerForSecureBootUpdate@@YAJPEAH@Z`
- size: `216`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180037338`

## callees

- `0x1800078b0`
- `0x180035cbc`
- `0x18003c0b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035cff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035cff`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x180035cf5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x180035cf5`

## string_xrefs

- `0x180035d16`: `CheckSufficientPowerForSecureBootUpdate: Failed to get power status, hr=0x%x`
- `0x180035d2d`: `CheckSufficientPowerForSecureBootUpdate: AC power detected, proceeding with update`
- `0x180035d56`: `CheckSufficientPowerForSecureBootUpdate: Battery at %d%%, sufficient for update`
- `0x180035d5f`: `CheckSufficientPowerForSecureBootUpdate: Battery at %d%%, insufficient for update (minimum 20%% required)`
- `0x180035d6d`: `CheckSufficientPowerForSecureBootUpdate: Unknown battery status, Proceeding with the update assuming enough power`

## pseudocode

```c
__int64 __fastcall CheckSufficientPowerForSecureBootUpdate(int *a1)
{
  signed int LastError; // eax
  unsigned int v4; // ebx
  unsigned int BatteryLifePercent; // eax
  _SYSTEM_POWER_STATUS SystemPowerStatus; // [rsp+20h] [rbp-28h] BYREF

  *(_QWORD *)&SystemPowerStatus.ACLineStatus = 0;
  SystemPowerStatus.BatteryFullLifeTime = 0;
  if ( !a1 )
    return 2147942487LL;
  *a1 = 0;
  if ( GetSystemPowerStatus(&SystemPowerStatus) )
  {
    if ( SystemPowerStatus.ACLineStatus == 1 )
    {
      *a1 = 1;
      SBServicingLogMessage((wchar_t *)L"CheckSufficientPowerForSecureBootUpdate: AC power detected, proceeding with update");
    }
    else
    {
      BatteryLifePercent = SystemPowerStatus.BatteryLifePercent;
      if ( SystemPowerStatus.BatteryLifePercent == 0xFF )
      {
        SBServicingLogMessage((wchar_t *)L"CheckSufficientPowerForSecureBootUpdate: Unknown battery status, Proceeding wit"
                                          "h the update assuming enough power");
        *a1 = 1;
      }
      else if ( SystemPowerStatus.BatteryLifePercent < 0x14u )
      {
        SBServicingLogMessage(
          (wchar_t *)L"CheckSufficientPowerForSecureBootUpdate: Battery at %d%%, insufficient for update (minimum 20%% required)",
          SystemPowerStatus.BatteryLifePercent);
      }
      else
      {
        *a1 = 1;
        SBServicingLogMessage(
          L"CheckSufficientPowerForSecureBootUpdate: Battery at %d%%, sufficient for update",
          BatteryLifePercent);
      }
    }
    return 0;
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    SBServicingLogMessage(
      (wchar_t *)L"CheckSufficientPowerForSecureBootUpdate: Failed to get power status, hr=0x%x",
      v4);
    return v4;
  }
}

```

## disassembly

```asm
0x180035cbc  push    rbx
0x180035cbe  sub     rsp, 40h
0x180035cc2  mov     rax, cs:__security_cookie
0x180035cc9  xor     rax, rsp
0x180035ccc  mov     [rsp+48h+var_18], rax
0x180035cd1  xor     eax, eax
0x180035cd3  mov     rbx, rcx
0x180035cd6  mov     qword ptr [rsp+48h+SystemPowerStatus.ACLineStatus], rax
0x180035cdb  mov     [rsp+48h+SystemPowerStatus.BatteryFullLifeTime], eax
0x180035cdf  test    rcx, rcx
0x180035ce2  jnz     short loc_180035CEE
0x180035ce4  mov     eax, 80070057h
0x180035ce9  jmp     loc_180035D81
0x180035cee  mov     [rcx], eax
0x180035cf0  lea     rcx, [rsp+48h+SystemPowerStatus]; lpSystemPowerStatus
0x180035cf5  call    cs:__imp_GetSystemPowerStatus
0x180035cfb  test    eax, eax
0x180035cfd  jnz     short loc_180035D26
0x180035cff  call    cs:__imp_GetLastError
0x180035d05  mov     ebx, eax
0x180035d07  test    eax, eax
0x180035d09  jle     short loc_180035D14
0x180035d0b  movzx   ebx, ax
0x180035d0e  or      ebx, 80070000h
0x180035d14  mov     edx, ebx
0x180035d16  lea     rcx, aChecksufficien; "CheckSufficientPowerForSecureBootUpdate"...
0x180035d1d  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180035d22  mov     eax, ebx
0x180035d24  jmp     short loc_180035D81
0x180035d26  cmp     [rsp+48h+SystemPowerStatus.ACLineStatus], 1
0x180035d2b  jnz     short loc_180035D41
0x180035d2d  lea     rcx, aChecksufficien_0; "CheckSufficientPowerForSecureBootUpdate"...
0x180035d34  mov     dword ptr [rbx], 1
0x180035d3a  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180035d3f  jmp     short loc_180035D7F
0x180035d41  movzx   eax, [rsp+48h+SystemPowerStatus.BatteryLifePercent]
0x180035d46  cmp     al, 0FFh
0x180035d48  jz      short loc_180035D6D
0x180035d4a  mov     edx, eax
0x180035d4c  cmp     al, 14h
0x180035d4e  jb      short loc_180035D5F
0x180035d50  mov     dword ptr [rbx], 1
0x180035d56  lea     rcx, aChecksufficien_3; "CheckSufficientPowerForSecureBootUpdate"...
0x180035d5d  jmp     short loc_180035D66
0x180035d5f  lea     rcx, aChecksufficien_1; "CheckSufficientPowerForSecureBootUpdate"...
0x180035d66  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180035d6b  jmp     short loc_180035D7F
0x180035d6d  lea     rcx, aChecksufficien_2; "CheckSufficientPowerForSecureBootUpdate"...
0x180035d74  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180035d79  mov     dword ptr [rbx], 1
0x180035d7f  xor     eax, eax
0x180035d81  mov     rcx, [rsp+48h+var_18]
0x180035d86  xor     rcx, rsp; StackCookie
0x180035d89  call    __security_check_cookie
0x180035d8e  add     rsp, 40h
0x180035d92  pop     rbx
0x180035d93  retn
```
