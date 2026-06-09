# winreSetRecoveryTimestamp

- ea: `0x18003307c`
- end: `0x18003319f`
- name: `winreSetRecoveryTimestamp`
- size: `291`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180024800`

## callees

- `0x1800059fc`
- `0x18003307c`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800330fe`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800330fe`
- `ADVAPI32!RegSetValueExW` at `0x180033146`
- `ADVAPI32!RegSetValueExW` at `0x180033146`
- `ADVAPI32!RegCreateKeyExW` at `0x1800330d1`
- `ADVAPI32!RegCreateKeyExW` at `0x1800330d1`
- `ADVAPI32!RegCloseKey` at `0x180033184`
- `ADVAPI32!RegCloseKey` at `0x180033184`

## string_xrefs

- `0x18003309d`: `System\Setup\BuildUpdate`
- `0x1800330de`: `System\Setup\BuildUpdate`
- `0x18003315b`: `System\Setup\BuildUpdate`
- `0x1800330e5`: `winreSetRecoveryTimestamp: Failed to create HKLM\%s: %u`

## pseudocode

```c
__int64 winreSetRecoveryTimestamp()
{
  unsigned int v0; // ebx
  unsigned int v1; // eax
  LSTATUS v2; // eax
  DWORD dwOptions[2]; // [rsp+20h] [rbp-58h]
  HKEY hKey; // [rsp+50h] [rbp-28h] BYREF
  __int64 Data; // [rsp+58h] [rbp-20h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp-18h] BYREF

  v0 = 0;
  hKey = 0;
  SystemTimeAsFileTime = 0;
  Data = 0;
  v1 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"System\\Setup\\BuildUpdate", 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
  if ( v1 )
  {
    UnattendLogW(1, L"winreSetRecoveryTimestamp: Failed to create HKLM\\%s: %u", L"System\\Setup\\BuildUpdate", v1);
  }
  else
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    Data = *(_QWORD *)&SystemTimeAsFileTime + 864000000000LL;
    v2 = RegSetValueExW(hKey, L"RecoveryDestination", 0, 0xBu, (const BYTE *)&Data, 8u);
    if ( v2 )
    {
      dwOptions[0] = v2;
      UnattendLogW(
        1,
        L"winreSetRecoveryTimestamp: Failed to set HKLM\\%s [%s]: %u",
        L"System\\Setup\\BuildUpdate",
        L"RecoveryDestination",
        *(_QWORD *)dwOptions);
    }
    else
    {
      v0 = 1;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x18003307c  mov     r11, rsp
0x18003307f  push    rbx
0x180033080  sub     rsp, 70h
0x180033084  mov     rax, cs:__security_cookie
0x18003308b  xor     rax, rsp
0x18003308e  mov     [rsp+78h+var_10], rax
0x180033093  xor     ebx, ebx
0x180033095  lea     rax, [r11-28h]
0x180033099  mov     [r11-38h], rbx
0x18003309d  lea     rdx, aSystemSetupBui; "System\\Setup\\BuildUpdate"
0x1800330a4  mov     [r11-40h], rax
0x1800330a8  xor     r9d, r9d; lpClass
0x1800330ab  mov     [r11-48h], rbx
0x1800330af  xor     r8d, r8d; Reserved
0x1800330b2  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x1800330ba  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800330c1  mov     [rsp+78h+dwOptions], ebx; dwOptions
0x1800330c5  mov     [r11-28h], rbx
0x1800330c9  mov     [r11-18h], rbx
0x1800330cd  mov     [r11-20h], rbx
0x1800330d1  call    cs:__imp_RegCreateKeyExW
0x1800330d7  test    eax, eax
0x1800330d9  jz      short loc_1800330F9
0x1800330db  mov     r9d, eax
0x1800330de  lea     r8, aSystemSetupBui; "System\\Setup\\BuildUpdate"
0x1800330e5  lea     rdx, aWinresetrecove_6; "winreSetRecoveryTimestamp: Failed to cr"...
0x1800330ec  lea     ecx, [rbx+1]
0x1800330ef  call    UnattendLogW
0x1800330f4  jmp     loc_18003317A
0x1800330f9  lea     rcx, [rsp+78h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800330fe  call    cs:__imp_GetSystemTimeAsFileTime
0x180033104  lea     rax, [rsp+78h+Data]
0x180033109  mov     [rsp+78h+samDesired], 8; cbData
0x180033111  mov     rcx, 0C92A69C000h
0x18003311b  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x180033120  add     rcx, qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime]
0x180033125  lea     rdx, aRecoverydestin; "RecoveryDestination"
0x18003312c  mov     dword ptr [rsp+78h+Data], ecx
0x180033130  mov     r9d, 0Bh; dwType
0x180033136  shr     rcx, 20h
0x18003313a  xor     r8d, r8d; Reserved
0x18003313d  mov     dword ptr [rsp+78h+Data+4], ecx
0x180033141  mov     rcx, [rsp+78h+hKey]; hKey
0x180033146  call    cs:__imp_RegSetValueExW
0x18003314c  test    eax, eax
0x18003314e  jz      short loc_180033175
0x180033150  lea     r9, aRecoverydestin; "RecoveryDestination"
0x180033157  mov     [rsp+78h+dwOptions], eax
0x18003315b  lea     r8, aSystemSetupBui; "System\\Setup\\BuildUpdate"
0x180033162  mov     ecx, 1
0x180033167  lea     rdx, aWinresetrecove_16; "winreSetRecoveryTimestamp: Failed to se"...
0x18003316e  call    UnattendLogW
0x180033173  jmp     short loc_18003317A
0x180033175  mov     ebx, 1
0x18003317a  mov     rcx, [rsp+78h+hKey]; hKey
0x18003317f  test    rcx, rcx
0x180033182  jz      short loc_18003318A
0x180033184  call    cs:__imp_RegCloseKey
0x18003318a  mov     eax, ebx
0x18003318c  mov     rcx, [rsp+78h+var_10]
0x180033191  xor     rcx, rsp; StackCookie
0x180033194  call    __security_check_cookie
0x180033199  add     rsp, 70h
0x18003319d  pop     rbx
0x18003319e  retn
```
