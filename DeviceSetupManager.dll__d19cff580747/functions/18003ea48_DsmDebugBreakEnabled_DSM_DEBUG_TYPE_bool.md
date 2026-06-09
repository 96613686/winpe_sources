# DsmDebugBreakEnabled(_DSM_DEBUG_TYPE,bool)

- ea: `0x18003ea48`
- end: `0x18003ebab`
- name: `?DsmDebugBreakEnabled@@YAHW4_DSM_DEBUG_TYPE@@_N@Z`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x1800238e8`

## callees

- `0x18000bfc0`
- `0x18003ea48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003eb97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003eb97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003eaf1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003eaf1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003eb26`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003eb26`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003eab5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003eab5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003eb8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003eb8f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003eb20`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003eb20`
- `ntdll!DbgPrintEx` at `0x18003eb06`
- `ntdll!DbgPrintEx` at `0x18003eb15`
- `ntdll!DbgPrintEx` at `0x18003eb79`
- `ntdll!DbgPrintEx` at `0x18003eb06`
- `ntdll!DbgPrintEx` at `0x18003eb15`
- `ntdll!DbgPrintEx` at `0x18003eb79`
- `ntdll!NtQuerySystemInformation` at `0x18003eb52`
- `ntdll!NtQuerySystemInformation` at `0x18003eb52`

## pseudocode

```c
_BOOL8 __fastcall DsmDebugBreakEnabled(__int64 a1, char a2)
{
  unsigned __int16 DeviceSetupKey; // ax
  LSTATUS v3; // ebx
  const CHAR *v4; // r8
  DWORD CurrentProcessId; // eax
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  __int16 SystemInformation; // [rsp+68h] [rbp+20h] BYREF
  DWORD Type; // [rsp+70h] [rbp+28h] BYREF
  int Data; // [rsp+78h] [rbp+30h] BYREF

  LOBYTE(SystemInformation) = a2;
  hKey = 0;
  Type = 0;
  cbData = 0;
  Data = 0;
  DeviceSetupKey = GetDeviceSetupKey(&hKey);
  v3 = DeviceSetupKey;
  if ( !DeviceSetupKey )
  {
    cbData = 4;
    v3 = RegQueryValueExW(hKey, L"DebugBreakOnStart", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v3 )
    {
      if ( Type != 4 )
      {
        v3 = 13;
        goto LABEL_20;
      }
      switch ( Data )
      {
        case 0:
          v3 = 50;
          break;
        case 1:
          SystemInformation = 0;
          if ( NtQuerySystemInformation(SystemKernelDebuggerInformation, &SystemInformation, 2u, 0) < 0
            || !(_BYTE)SystemInformation
            || HIBYTE(SystemInformation) )
          {
            v4 = "\nDSM: Kernel debugger NOT enabled.\n";
            goto LABEL_17;
          }
          break;
        case 2:
          CurrentProcessId = GetCurrentProcessId();
          DbgPrintEx(0x23u, 0, "\nDSM: Waiting for debugger on Process ID = %d ...", CurrentProcessId);
          while ( !IsDebuggerPresent() )
          {
            DbgPrintEx(0x23u, 0, ".");
            Sleep(0x3E8u);
          }
          DbgPrintEx(0x23u, 0, "DSM: Debugger detected!\n");
          break;
        default:
          v4 = "\nDSM: Unknown debug option, NOT breaking to debugger.\n";
LABEL_17:
          v3 = 50;
          DbgPrintEx(0x23u, 0, v4);
          break;
      }
    }
  }
LABEL_20:
  if ( hKey )
    RegCloseKey(hKey);
  SetLastError(v3);
  return v3 == 0;
}

```

## disassembly

```asm
0x18003ea48  mov     byte ptr [rsp-10h+SystemInformation], dl
0x18003ea4c  mov     [rsp-10h+cbData], ecx
0x18003ea50  push    rbp
0x18003ea51  push    rbx
0x18003ea52  mov     rbp, rsp
0x18003ea55  sub     rsp, 48h
0x18003ea59  lea     rcx, [rbp+hKey]; phkResult
0x18003ea5d  mov     [rbp+hKey], 0
0x18003ea65  mov     [rbp+Type], 0
0x18003ea6c  mov     [rbp+cbData], 0
0x18003ea73  mov     [rbp+Data], 0
0x18003ea7a  call    ?GetDeviceSetupKey@@YAJPEAPEAUHKEY__@@@Z; GetDeviceSetupKey(HKEY__ * *)
0x18003ea7f  movzx   ebx, ax
0x18003ea82  test    ebx, ebx
0x18003ea84  jnz     loc_18003EB86
0x18003ea8a  mov     rdx, cs:lpValueName; lpValueName
0x18003ea91  lea     rax, [rbp+cbData]
0x18003ea95  mov     rcx, [rbp+hKey]; hKey
0x18003ea99  lea     r9, [rbp+Type]; lpType
0x18003ea9d  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18003eaa2  xor     r8d, r8d; lpReserved
0x18003eaa5  lea     rax, [rbp+Data]
0x18003eaa9  mov     [rbp+cbData], 4
0x18003eab0  mov     [rsp+48h+lpData], rax; lpData
0x18003eab5  call    cs:__imp_RegQueryValueExW
0x18003eabb  mov     ebx, eax
0x18003eabd  test    eax, eax
0x18003eabf  jnz     loc_18003EB86
0x18003eac5  cmp     [rbp+Type], 4
0x18003eac9  jz      short loc_18003EAD3
0x18003eacb  lea     ebx, [rax+0Dh]
0x18003eace  jmp     loc_18003EB86
0x18003ead3  mov     eax, [rbp+Data]
0x18003ead6  test    eax, eax
0x18003ead8  jz      loc_18003EB81
0x18003eade  sub     eax, 1
0x18003eae1  jz      short loc_18003EB3E
0x18003eae3  cmp     eax, 1
0x18003eae6  jz      short loc_18003EAF1
0x18003eae8  lea     r8, aDsmUnknownDebu; "\nDSM: Unknown debug option, NOT breaki"...
0x18003eaef  jmp     short loc_18003EB6F
0x18003eaf1  call    cs:__imp_GetCurrentProcessId
0x18003eaf7  xor     edx, edx; Level
0x18003eaf9  lea     r8, Format; "\nDSM: Waiting for debugger on Process "...
0x18003eb00  mov     r9d, eax
0x18003eb03  lea     ecx, [rdx+23h]; ComponentId
0x18003eb06  call    cs:__imp_DbgPrintEx
0x18003eb0c  jmp     short loc_18003EB26
0x18003eb0e  lea     r8, asc_18004E80C; "."
0x18003eb15  call    cs:__imp_DbgPrintEx
0x18003eb1b  mov     ecx, 3E8h; dwMilliseconds
0x18003eb20  call    cs:__imp_Sleep
0x18003eb26  call    cs:__imp_IsDebuggerPresent
0x18003eb2c  xor     edx, edx; Level
0x18003eb2e  lea     ecx, [rdx+23h]; ComponentId
0x18003eb31  test    eax, eax
0x18003eb33  jz      short loc_18003EB0E
0x18003eb35  lea     r8, aDsmDebuggerDet; "DSM: Debugger detected!\n"
0x18003eb3c  jmp     short loc_18003EB79
0x18003eb3e  xor     eax, eax
0x18003eb40  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x18003eb44  xor     r9d, r9d; ReturnLength
0x18003eb47  mov     [rbp+SystemInformation], ax
0x18003eb4b  lea     r8d, [rax+2]; SystemInformationLength
0x18003eb4f  lea     ecx, [rax+23h]; SystemInformationClass
0x18003eb52  call    cs:__imp_NtQuerySystemInformation
0x18003eb58  test    eax, eax
0x18003eb5a  js      short loc_18003EB68
0x18003eb5c  cmp     byte ptr [rbp+SystemInformation], 0
0x18003eb60  jz      short loc_18003EB68
0x18003eb62  cmp     byte ptr [rbp+SystemInformation+1], 0
0x18003eb66  jz      short loc_18003EB86
0x18003eb68  lea     r8, aDsmKernelDebug; "\nDSM: Kernel debugger NOT enabled.\n"
0x18003eb6f  mov     ebx, 32h ; '2'
0x18003eb74  xor     edx, edx; Level
0x18003eb76  lea     ecx, [rbx-0Fh]; ComponentId
0x18003eb79  call    cs:__imp_DbgPrintEx
0x18003eb7f  jmp     short loc_18003EB86
0x18003eb81  mov     ebx, 32h ; '2'
0x18003eb86  mov     rcx, [rbp+hKey]; hKey
0x18003eb8a  test    rcx, rcx
0x18003eb8d  jz      short loc_18003EB95
0x18003eb8f  call    cs:__imp_RegCloseKey
0x18003eb95  mov     ecx, ebx; dwErrCode
0x18003eb97  call    cs:__imp_SetLastError
0x18003eb9d  xor     eax, eax
0x18003eb9f  test    ebx, ebx
0x18003eba1  setz    al
0x18003eba4  add     rsp, 48h
0x18003eba8  pop     rbx
0x18003eba9  pop     rbp
0x18003ebaa  retn
```
