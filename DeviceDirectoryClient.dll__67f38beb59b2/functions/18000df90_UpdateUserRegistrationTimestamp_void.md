# UpdateUserRegistrationTimestamp(void)

- ea: `0x18000df90`
- end: `0x18000e003`
- name: `?UpdateUserRegistrationTimestamp@@YAJXZ`
- size: `115`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000ca4c`

## callees

- `0x1800050b8`
- `0x18000df90`
- `0x18001be44`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000dfa4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000dfa4`

## string_xrefs

- `0x18000dfbd`: `SOFTWARE\Microsoft\DeviceDirectory`
- `0x18000dfe7`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcregistrationcontroller.cpp`
- `0x18000dfd8`: `CHR(DdcRegistry::SetByteValue( (( HKEY ) (ULONG_PTR)((LONG)0x80000001) ), REGISTRY_KEY_DEVICEDIRECTORY, REGISTRY_VALUE_LAST_USER_REGISTRATION_TIMESTAMP, (BYTE *)&ftNow, (DWORD)sizeof(FILETIMEEX)))`

## pseudocode

```c
__int64 UpdateUserRegistrationTimestamp(void)
{
  int v0; // edx
  int v1; // ecx
  int v2; // ebx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+8h] BYREF

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v2 = DdcRegistry::SetByteValue(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\DeviceDirectory",
         L"LastUserRegistrationTimestamp",
         (unsigned __int8 *)&SystemTimeAsFileTime);
  if ( v2 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      v1,
      v0,
      v2,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
      228,
      "CHR(DdcRegistry::SetByteValue( (( HKEY ) (ULONG_PTR)((LONG)0x80000001) ), REGISTRY_KEY_DEVICEDIRECTORY, REGISTRY_V"
      "ALUE_LAST_USER_REGISTRATION_TIMESTAMP, (BYTE *)&ftNow, (DWORD)sizeof(FILETIMEEX)))");
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000df90  push    rbx
0x18000df92  sub     rsp, 30h
0x18000df96  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000df9b  mov     qword ptr [rsp+38h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000dfa4  call    cs:__imp_GetSystemTimeAsFileTime
0x18000dfaa  lea     r9, [rsp+38h+SystemTimeAsFileTime]; unsigned __int8 *
0x18000dfaf  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x18000dfb6  lea     r8, aLastuserregist; "LastUserRegistrationTimestamp"
0x18000dfbd  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\DeviceDirectory"
0x18000dfc4  call    ?SetByteValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1PEAEKK@Z; DdcRegistry::SetByteValue(HKEY__ *,ushort const *,ushort const *,uchar *,ulong,ulong)
0x18000dfc9  mov     ebx, eax
0x18000dfcb  test    eax, eax
0x18000dfcd  jns     short loc_18000DFFB
0x18000dfcf  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000dfd6  jz      short loc_18000DFFB
0x18000dfd8  lea     rax, aChrDdcregistry_0; "CHR(DdcRegistry::SetByteValue( (( HKEY "...
0x18000dfdf  mov     r8d, ebx
0x18000dfe2  mov     [rsp+38h+var_10], rax
0x18000dfe7  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000dfee  mov     [rsp+38h+var_18], 0E4h
0x18000dff6  call    McTemplateU0dsqs_EventWriteTransfer
0x18000dffb  mov     eax, ebx
0x18000dffd  add     rsp, 30h
0x18000e001  pop     rbx
0x18000e002  retn
```
