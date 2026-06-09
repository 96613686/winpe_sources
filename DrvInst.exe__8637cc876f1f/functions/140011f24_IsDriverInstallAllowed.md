# IsDriverInstallAllowed

- ea: `0x140011f24`
- end: `0x140012045`
- name: `IsDriverInstallAllowed`
- size: `289`
- prototype: `_BOOL8 __fastcall(__int64, void *, WCHAR *, __int64, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14001190c`
- `0x140011a78`

## callees

- `0x140011638`
- `0x140011f24`
- `0x1400120a4`
- `0x140022330`
- `0x140024944`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011f71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001201e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011f71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001201e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140012028`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140012028`
- `DEVRTL!DevRtlWriteTextLog` at `0x140011fa0`
- `DEVRTL!DevRtlWriteTextLog` at `0x140011fa0`

## string_xrefs

- `0x140011f79`: `Installation of device is blocked by policy. Error = 0x%08X`
- `0x140011f86`: `Failed to determine device installation policy. Error = 0x%08X`
- `0x140011fe7`: `Failed to determine driver installation policy. Error = 0x%08X`

## pseudocode

```c
_BOOL8 __fastcall IsDriverInstallAllowed(
        __int64 a1,
        void *a2,
        WCHAR *a3,
        __int64 a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6)
{
  __int64 v8; // rcx
  DWORD LastError; // ebx
  const char *v10; // r9

  if ( !(unsigned int)PnpPolIsDeviceInstallAllowed(a2, a3, a5) )
  {
    LastError = GetLastError();
    v10 = "Installation of device is blocked by policy. Error = 0x%08X";
    if ( LastError != -536870328 )
      v10 = "Failed to determine device installation policy. Error = 0x%08X";
LABEL_4:
    DevRtlWriteTextLog(a1, 1, 1, v10, LastError);
    goto LABEL_13;
  }
  LastError = 0;
  if ( !(unsigned int)Feature_DeviceInstall_CheckDriverIntegrity__private_IsEnabledDeviceUsageNoInline(v8) )
    goto LABEL_13;
  if ( a6 )
  {
    if ( (unsigned int)DrvUtilsEnumDriversFromStrongNames(a6) )
      goto LABEL_13;
    LastError = 123;
    v10 = "Failed to determine driver installation policy. Error = 0x%08X";
    goto LABEL_4;
  }
  if ( a5 && !(unsigned int)ValidateDriverPolicy(a4, a5, 0, a1, 0) )
    LastError = GetLastError();
LABEL_13:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x140011f24  mov     r11, rsp
0x140011f27  mov     [r11+8], rbx
0x140011f2b  mov     [r11+10h], rbp
0x140011f2f  push    rdi
0x140011f30  sub     rsp, 50h
0x140011f34  mov     rdi, rcx
0x140011f37  mov     rax, r8
0x140011f3a  mov     r8, [rsp+58h+arg_20]; unsigned __int16 *
0x140011f42  xor     ecx, ecx
0x140011f44  mov     r10, rdx
0x140011f47  mov     [r11-38h], rcx
0x140011f4b  xorps   xmm0, xmm0
0x140011f4e  mov     rbp, r9
0x140011f51  mov     r9d, [rsp+58h+arg_30]
0x140011f59  mov     rdx, rax; pDeviceID
0x140011f5c  movups  [rsp+58h+var_28], xmm0
0x140011f61  mov     [r11-18h], rcx
0x140011f65  mov     rcx, r10; TokenHandle
0x140011f68  call    PnpPolIsDeviceInstallAllowed
0x140011f6d  test    eax, eax
0x140011f6f  jnz     short loc_140011FA8
0x140011f71  call    cs:__imp_GetLastError
0x140011f77  mov     ebx, eax
0x140011f79  lea     r9, aInstallationOf_0; "Installation of device is blocked by po"...
0x140011f80  cmp     ebx, 0E0000248h
0x140011f86  lea     rax, aFailedToDeterm_0; "Failed to determine device installation"...
0x140011f8d  cmovnz  r9, rax
0x140011f91  mov     edx, 1
0x140011f96  mov     [rsp+58h+var_38], ebx
0x140011f9a  mov     r8d, edx
0x140011f9d  mov     rcx, rdi
0x140011fa0  call    cs:__imp_DevRtlWriteTextLog
0x140011fa6  jmp     short loc_140012026
0x140011fa8  xor     ebx, ebx
0x140011faa  call    Feature_DeviceInstall_CheckDriverIntegrity__private_IsEnabledDeviceUsageNoInline
0x140011faf  test    eax, eax
0x140011fb1  jz      short loc_140012026
0x140011fb3  mov     rcx, [rsp+58h+arg_28]; unsigned __int16 *
0x140011fbb  test    rcx, rcx
0x140011fbe  jz      short loc_140011FFA
0x140011fc0  lea     r8, [rsp+58h+var_28]
0x140011fc5  mov     [rsp+58h+var_18], rbx
0x140011fca  lea     rdx, ValidateDriverPolicyCallback
0x140011fd1  mov     qword ptr [rsp+58h+var_28], rbp
0x140011fd6  mov     qword ptr [rsp+58h+var_28+8], rdi
0x140011fdb  call    DrvUtilsEnumDriversFromStrongNames
0x140011fe0  test    eax, eax
0x140011fe2  jnz     short loc_140011FF0
0x140011fe4  lea     ebx, [rax+7Bh]
0x140011fe7  lea     r9, aFailedToDeterm; "Failed to determine driver installation"...
0x140011fee  jmp     short loc_140011F91
0x140011ff0  mov     eax, dword ptr [rsp+58h+var_18]
0x140011ff4  test    eax, eax
0x140011ff6  jz      short loc_140012026
0x140011ff8  jmp     short loc_140012024
0x140011ffa  cmp     [rsp+58h+arg_20], rbx
0x140012002  jz      short loc_140012026
0x140012004  mov     rdx, [rsp+58h+arg_20]
0x14001200c  mov     r9, rdi
0x14001200f  xor     r8d, r8d
0x140012012  mov     rcx, rbp
0x140012015  call    ValidateDriverPolicy
0x14001201a  test    eax, eax
0x14001201c  jnz     short loc_140012026
0x14001201e  call    cs:__imp_GetLastError
0x140012024  mov     ebx, eax
0x140012026  mov     ecx, ebx; dwErrCode
0x140012028  call    cs:__imp_SetLastError
0x14001202e  mov     rbp, [rsp+58h+arg_8]
0x140012033  xor     eax, eax
0x140012035  test    ebx, ebx
0x140012037  mov     rbx, [rsp+58h+arg_0]
0x14001203c  setz    al
0x14001203f  add     rsp, 50h
0x140012043  pop     rdi
0x140012044  retn
```
