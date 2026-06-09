# IPxlatSvcControl::UpdateWinNatDriver(bool)

- ea: `0x18000bed4`
- end: `0x18000c14d`
- name: `?UpdateWinNatDriver@IPxlatSvcControl@@AEAAK_N@Z`
- size: `633`
- prototype: `__int64 __fastcall(IPxlatSvcControl *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000ba4c`

## callees

- `0x180001d40`
- `0x18000bed4`
- `0x18000c224`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c043`
- `ntdll!RtlAdjustPrivilege` at `0x18000bf81`
- `ntdll!RtlAdjustPrivilege` at `0x18000bfdf`
- `ntdll!RtlAdjustPrivilege` at `0x18000bf81`
- `ntdll!RtlAdjustPrivilege` at `0x18000bfdf`
- `ntdll!RtlNtStatusToDosError` at `0x18000bf12`
- `ntdll!RtlNtStatusToDosError` at `0x18000bf95`
- `ntdll!RtlNtStatusToDosError` at `0x18000bff5`
- `ntdll!RtlNtStatusToDosError` at `0x18000c078`
- `ntdll!RtlNtStatusToDosError` at `0x18000bf12`
- `ntdll!RtlNtStatusToDosError` at `0x18000bf95`
- `ntdll!RtlNtStatusToDosError` at `0x18000bff5`
- `ntdll!RtlNtStatusToDosError` at `0x18000c078`
- `ntdll!NtLoadDriver` at `0x18000bfbf`
- `ntdll!NtLoadDriver` at `0x18000bfbf`
- `ntdll!RtlImpersonateSelf` at `0x18000bf03`
- `ntdll!RtlImpersonateSelf` at `0x18000bf03`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000bf8d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000c039`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000bf8d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000c039`

## string_xrefs

- `0x18000bf24`: `Impersonation failed.`
- `0x18000c0a2`: `WinNat driver already in running state.`
- `0x18000c0db`: `Could not update WinNat driver state.`
- `0x18000c0f8`: `Successfully updated WinNat driver state.`

## pseudocode

```c
__int64 __fastcall IPxlatSvcControl::UpdateWinNatDriver(IPxlatSvcControl *this)
{
  int v2; // eax
  __int64 v3; // rcx
  __int64 v4; // r8
  ULONG LastError; // r14d
  const char *v6; // rax
  int v8; // edi
  int Driver; // r14d
  ULONG v10; // eax
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 *v13; // rdx
  __int64 v14; // r9
  unsigned __int8 OldValue[8]; // [rsp+30h] [rbp-50h] BYREF
  int v16; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v17[16]; // [rsp+40h] [rbp-40h] BYREF
  const char *v18; // [rsp+50h] [rbp-30h]
  __int64 v19; // [rsp+58h] [rbp-28h]
  int *v20; // [rsp+60h] [rbp-20h]
  __int64 v21; // [rsp+68h] [rbp-18h]

  v2 = RtlImpersonateSelf(SecurityImpersonation);
  if ( v2 < 0 )
  {
    LastError = RtlNtStatusToDosError(v2);
    if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) == 0 )
      return LastError;
    v6 = "Impersonation failed.";
    v19 = 22;
LABEL_4:
    v18 = v6;
    v16 = LastError;
    v20 = &v16;
    v21 = 4;
    McGenEventWrite_EventWriteTransfer(v3, IPXLATCFG_ERROR_EVENT, v4, 3, v17);
    return LastError;
  }
  OldValue[0] = 0;
  v8 = RtlAdjustPrivilege(0xAu, 1u, 1u, OldValue);
  if ( v8 < 0 )
  {
    RevertToSelf();
    LastError = RtlNtStatusToDosError(v8);
    if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) == 0 )
      return LastError;
    v6 = "Could not enable load driver privelege.";
    v19 = 40;
    goto LABEL_4;
  }
  Driver = NtLoadDriver((PUNICODE_STRING)((char *)this + 56));
  if ( !OldValue[0] && RtlAdjustPrivilege(0xAu, 0, 1u, OldValue) < 0 && (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
  {
    v10 = RtlNtStatusToDosError(Driver);
    v19 = 41;
    v16 = v10;
    v21 = 4;
    v18 = "Could not disable load driver privelege.";
    v20 = &v16;
    McGenEventWrite_EventWriteTransfer(v11, IPXLATCFG_ERROR_EVENT, v12, 3, v17);
  }
  if ( !RevertToSelf() )
  {
    LastError = GetLastError();
    if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) == 0 )
      return LastError;
    v6 = "Could not RevertToSelf.";
    v19 = 24;
    goto LABEL_4;
  }
  if ( Driver >= 0 )
  {
    if ( (Microsoft_Windows_IPxlatCfgEnableBits & 2) != 0 )
    {
      v19 = 42;
      v18 = "Successfully updated WinNat driver state.";
      v13 = IPXLATCFG_INFO_EVENT;
      v14 = 2;
      goto LABEL_24;
    }
  }
  else
  {
    LastError = RtlNtStatusToDosError(Driver);
    if ( LastError != 1056 )
    {
      if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) == 0 )
        return LastError;
      v6 = "Could not update WinNat driver state.";
      v19 = 38;
      goto LABEL_4;
    }
    if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
    {
      v16 = 1056;
      v13 = IPXLATCFG_ERROR_EVENT;
      v19 = 40;
      v18 = "WinNat driver already in running state.";
      v14 = 3;
      v21 = 4;
      v20 = &v16;
LABEL_24:
      McGenEventWrite_EventWriteTransfer(v3, v13, v4, v14, v17);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000bed4  mov     [rsp-18h+arg_8], rsi
0x18000bed9  mov     [rsp-18h+arg_10], rdi
0x18000bede  push    rbp
0x18000bedf  push    r14
0x18000bee1  push    r15
0x18000bee3  mov     rbp, rsp
0x18000bee6  sub     rsp, 80h
0x18000beed  mov     rax, cs:__security_cookie
0x18000bef4  xor     rax, rsp
0x18000bef7  mov     [rbp+var_10], rax
0x18000befb  mov     rsi, rcx
0x18000befe  mov     ecx, 2; ImpersonationLevel
0x18000bf03  call    cs:__imp_RtlImpersonateSelf
0x18000bf09  xor     r15d, r15d
0x18000bf0c  test    eax, eax
0x18000bf0e  jns     short loc_18000BF6E
0x18000bf10  mov     ecx, eax; Status
0x18000bf12  call    cs:__imp_RtlNtStatusToDosError
0x18000bf18  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 1
0x18000bf1f  mov     r14d, eax
0x18000bf22  jz      short loc_18000BF66
0x18000bf24  lea     rax, aImpersonationF; "Impersonation failed."
0x18000bf2b  mov     [rbp+var_28], 16h
0x18000bf33  mov     r9d, 3
0x18000bf39  mov     [rbp+var_30], rax
0x18000bf3d  lea     rdx, IPXLATCFG_ERROR_EVENT
0x18000bf44  lea     rax, [rbp+var_48]
0x18000bf48  mov     [rbp+var_48], r14d
0x18000bf4c  mov     [rbp+var_20], rax
0x18000bf50  lea     rax, [rbp+var_40]
0x18000bf54  mov     [rsp+80h+var_60], rax
0x18000bf59  mov     [rbp+var_18], 4
0x18000bf61  call    McGenEventWrite_EventWriteTransfer
0x18000bf66  mov     eax, r14d
0x18000bf69  jmp     loc_18000C128
0x18000bf6e  mov     r8b, 1; ForThread
0x18000bf71  mov     [rbp+OldValue], r15b
0x18000bf75  mov     dl, r8b; NewValue
0x18000bf78  lea     r9, [rbp+OldValue]; OldValue
0x18000bf7c  mov     ecx, 0Ah; Privilege
0x18000bf81  call    cs:__imp_RtlAdjustPrivilege
0x18000bf87  mov     edi, eax
0x18000bf89  test    eax, eax
0x18000bf8b  jns     short loc_18000BFBB
0x18000bf8d  call    cs:__imp_RevertToSelf
0x18000bf93  mov     ecx, edi; Status
0x18000bf95  call    cs:__imp_RtlNtStatusToDosError
0x18000bf9b  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 1
0x18000bfa2  mov     r14d, eax
0x18000bfa5  jz      short loc_18000BF66
0x18000bfa7  lea     rax, aCouldNotEnable; "Could not enable load driver privelege."
0x18000bfae  mov     [rbp+var_28], 28h ; '('
0x18000bfb6  jmp     loc_18000BF33
0x18000bfbb  lea     rcx, [rsi+38h]; DriverServiceName
0x18000bfbf  call    cs:__imp_NtLoadDriver
0x18000bfc5  mov     esi, 3
0x18000bfca  mov     r14d, eax
0x18000bfcd  cmp     [rbp+OldValue], r15b
0x18000bfd1  jnz     short loc_18000C039
0x18000bfd3  lea     r9, [rbp+OldValue]; OldValue
0x18000bfd7  mov     r8b, 1; ForThread
0x18000bfda  xor     edx, edx; NewValue
0x18000bfdc  lea     ecx, [rsi+7]; Privilege
0x18000bfdf  call    cs:__imp_RtlAdjustPrivilege
0x18000bfe5  test    eax, eax
0x18000bfe7  jns     short loc_18000C039
0x18000bfe9  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 1
0x18000bff0  jz      short loc_18000C039
0x18000bff2  mov     ecx, r14d; Status
0x18000bff5  call    cs:__imp_RtlNtStatusToDosError
0x18000bffb  mov     r9d, esi
0x18000bffe  mov     [rbp+var_28], 29h ; ')'
0x18000c006  mov     [rbp+var_48], eax
0x18000c009  lea     rdx, IPXLATCFG_ERROR_EVENT
0x18000c010  lea     rax, aCouldNotDisabl; "Could not disable load driver privelege"...
0x18000c017  mov     [rbp+var_18], 4
0x18000c01f  mov     [rbp+var_30], rax
0x18000c023  lea     rax, [rbp+var_48]
0x18000c027  mov     [rbp+var_20], rax
0x18000c02b  lea     rax, [rbp+var_40]
0x18000c02f  mov     [rsp+80h+var_60], rax
0x18000c034  call    McGenEventWrite_EventWriteTransfer
0x18000c039  call    cs:__imp_RevertToSelf
0x18000c03f  test    eax, eax
0x18000c041  jnz     short loc_18000C070
0x18000c043  call    cs:__imp_GetLastError
0x18000c049  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 1
0x18000c050  mov     r14d, eax
0x18000c053  jz      loc_18000BF66
0x18000c059  lea     rax, aCouldNotRevert; "Could not RevertToSelf."
0x18000c060  mov     [rbp+var_28], 18h
0x18000c068  mov     r9d, esi
0x18000c06b  jmp     loc_18000BF39
0x18000c070  test    r14d, r14d
0x18000c073  jns     short loc_18000C0EF
0x18000c075  mov     ecx, r14d; Status
0x18000c078  call    cs:__imp_RtlNtStatusToDosError
0x18000c07e  mov     r14d, eax
0x18000c081  mov     eax, 420h
0x18000c086  cmp     r14d, eax
0x18000c089  jnz     short loc_18000C0CE
0x18000c08b  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 1
0x18000c092  jz      loc_18000C126
0x18000c098  mov     [rbp+var_48], eax
0x18000c09b  lea     rdx, IPXLATCFG_ERROR_EVENT
0x18000c0a2  lea     rax, aWinnatDriverAl; "WinNat driver already in running state."
0x18000c0a9  mov     [rbp+var_28], 28h ; '('
0x18000c0b1  mov     [rbp+var_30], rax
0x18000c0b5  mov     r9d, esi
0x18000c0b8  lea     rax, [rbp+var_48]
0x18000c0bc  mov     [rbp+var_18], 4
0x18000c0c4  mov     [rbp+var_20], rax
0x18000c0c8  lea     rax, [rbp+var_40]
0x18000c0cc  jmp     short loc_18000C11C
0x18000c0ce  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 1
0x18000c0d5  jz      loc_18000BF66
0x18000c0db  lea     rax, aCouldNotUpdate_1; "Could not update WinNat driver state."
0x18000c0e2  mov     [rbp+var_28], 26h ; '&'
0x18000c0ea  jmp     loc_18000C068
0x18000c0ef  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 2
0x18000c0f6  jz      short loc_18000C126
0x18000c0f8  lea     rax, aSuccessfullyUp; "Successfully updated WinNat driver stat"...
0x18000c0ff  mov     [rbp+var_28], 2Ah ; '*'
0x18000c107  mov     [rbp+var_30], rax
0x18000c10b  lea     rdx, IPXLATCFG_INFO_EVENT
0x18000c112  lea     rax, [rbp+var_40]
0x18000c116  mov     r9d, 2
0x18000c11c  mov     [rsp+80h+var_60], rax
0x18000c121  call    McGenEventWrite_EventWriteTransfer
0x18000c126  xor     eax, eax
0x18000c128  mov     rcx, [rbp+var_10]
0x18000c12c  xor     rcx, rsp; StackCookie
0x18000c12f  call    __security_check_cookie
0x18000c134  lea     r11, [rsp+80h+var_s0]
0x18000c13c  mov     rsi, [r11+28h]
0x18000c140  mov     rdi, [r11+30h]
0x18000c144  mov     rsp, r11
0x18000c147  pop     r15
0x18000c149  pop     r14
0x18000c14b  pop     rbp
0x18000c14c  retn
```
