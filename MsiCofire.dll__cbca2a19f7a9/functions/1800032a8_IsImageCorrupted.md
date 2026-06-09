# IsImageCorrupted

- ea: `0x1800032a8`
- end: `0x1800033ee`
- name: `IsImageCorrupted`
- size: `326`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800038cc`

## callees

- `0x180002590`
- `0x1800028dc`
- `0x1800032a8`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18000332d`
- `ADVAPI32!RegQueryValueExW` at `0x18000332d`
- `ADVAPI32!RegOpenKeyExW` at `0x1800032eb`
- `ADVAPI32!RegOpenKeyExW` at `0x1800032eb`
- `ADVAPI32!RegCloseKey` at `0x180003349`
- `ADVAPI32!RegCloseKey` at `0x180003366`
- `ADVAPI32!RegCloseKey` at `0x180003349`
- `ADVAPI32!RegCloseKey` at `0x180003366`
- `imagehlp!MapFileAndCheckSumW` at `0x180003389`
- `imagehlp!MapFileAndCheckSumW` at `0x180003389`

## string_xrefs

- `0x1800032dd`: `Software\Microsoft\Windows NT\CurrentVersion\MsiCorruptedFileRecovery`
- `0x1800033be`: `MSI-COFIRE ERROR: %s:%d - ret = 0x%08X\n`

## pseudocode

```c
__int64 __fastcall IsImageCorrupted(LPCWSTR lpFileName, _DWORD *a2)
{
  __int64 result; // rax
  DWORD HeaderSum; // [rsp+30h] [rbp-28h] BYREF
  DWORD CheckSum; // [rsp+34h] [rbp-24h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-18h] BYREF
  DWORD Type; // [rsp+70h] [rbp+18h] BYREF
  int Data; // [rsp+78h] [rbp+20h] BYREF

  *a2 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\MsiCorruptedFileRecovery",
          0,
          1u,
          &hKey) )
  {
    Type = 0;
    Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"SkipCorruptionCheck", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data )
    {
      RegCloseKey(hKey);
      *a2 = 1;
      return 0;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  HeaderSum = 0;
  CheckSum = 0;
  MapFileAndCheckSumW(lpFileName, &HeaderSum, &CheckSum);
  if ( HeaderSum && HeaderSum == CheckSum )
    return 0;
  result = CheckCertificateForCorruption(lpFileName);
  if ( (int)result < 0 )
  {
    DebugPrint(1u, "MSI-COFIRE ERROR: %s:%d - ret = 0x%08X\n", "IsImageCorrupted", 1228, result);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800032a8  mov     r11, rsp
0x1800032ab  mov     [r11+8], rbx
0x1800032af  mov     [r11+10h], rdx
0x1800032b3  push    rdi
0x1800032b4  sub     rsp, 50h
0x1800032b8  mov     rbx, rdx
0x1800032bb  mov     rdi, rcx
0x1800032be  mov     dword ptr [rdx], 0
0x1800032c4  mov     qword ptr [r11-18h], 0
0x1800032cc  lea     rax, [r11-18h]
0x1800032d0  mov     [r11-38h], rax
0x1800032d4  mov     r9d, 1; samDesired
0x1800032da  xor     r8d, r8d; ulOptions
0x1800032dd  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800032e4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800032eb  call    cs:__imp_RegOpenKeyExW
0x1800032f1  test    eax, eax
0x1800032f3  jnz     short loc_18000335C
0x1800032f5  mov     [rsp+58h+Type], eax
0x1800032f9  mov     [rsp+58h+Data], eax
0x1800032fd  mov     [rsp+58h+cbData], 4
0x180003305  lea     rax, [rsp+58h+cbData]
0x18000330a  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000330f  lea     rax, [rsp+58h+Data]
0x180003314  mov     [rsp+58h+lpData], rax; lpData
0x180003319  lea     r9, [rsp+58h+Type]; lpType
0x18000331e  xor     r8d, r8d; lpReserved
0x180003321  lea     rdx, ValueName; "SkipCorruptionCheck"
0x180003328  mov     rcx, [rsp+58h+hKey]; hKey
0x18000332d  call    cs:__imp_RegQueryValueExW
0x180003333  test    eax, eax
0x180003335  jnz     short loc_18000335C
0x180003337  cmp     [rsp+58h+Type], 4
0x18000333c  jnz     short loc_18000335C
0x18000333e  cmp     [rsp+58h+Data], eax
0x180003342  jz      short loc_18000335C
0x180003344  mov     rcx, [rsp+58h+hKey]; hKey
0x180003349  call    cs:__imp_RegCloseKey
0x18000334f  mov     dword ptr [rbx], 1
0x180003355  xor     eax, eax
0x180003357  jmp     loc_1800033E3
0x18000335c  mov     rcx, [rsp+58h+hKey]; hKey
0x180003361  test    rcx, rcx
0x180003364  jz      short loc_18000336C
0x180003366  call    cs:__imp_RegCloseKey
0x18000336c  mov     [rsp+58h+HeaderSum], 0
0x180003374  mov     [rsp+58h+CheckSum], 0
0x18000337c  lea     r8, [rsp+58h+CheckSum]; CheckSum
0x180003381  lea     rdx, [rsp+58h+HeaderSum]; HeaderSum
0x180003386  mov     rcx, rdi; Filename
0x180003389  call    cs:__imp_MapFileAndCheckSumW
0x18000338f  nop
0x180003390  mov     eax, [rsp+58h+HeaderSum]
0x180003394  test    eax, eax
0x180003396  jz      short loc_18000339E
0x180003398  cmp     eax, [rsp+58h+CheckSum]
0x18000339c  jz      short loc_180003355
0x18000339e  mov     rdx, rbx
0x1800033a1  mov     rcx, rdi; lpFileName
0x1800033a4  call    CheckCertificateForCorruption
0x1800033a9  test    eax, eax
0x1800033ab  jns     short loc_1800033E3
0x1800033ad  mov     dword ptr [rsp+58h+lpData], eax
0x1800033b1  mov     r9d, 4CCh
0x1800033b7  lea     r8, aIsimagecorrupt; "IsImageCorrupted"
0x1800033be  lea     rdx, aMsiCofireError_0; "MSI-COFIRE ERROR: %s:%d - ret = 0x%08X"...
0x1800033c5  mov     ecx, 1; Level
0x1800033ca  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x1800033cf  mov     eax, 1
0x1800033d4  jmp     short loc_1800033E3
0x1800033d6  mov     rax, [rsp+58h+arg_8]
0x1800033db  mov     dword ptr [rax], 1
0x1800033e1  xor     eax, eax
0x1800033e3  mov     rbx, [rsp+58h+arg_0]
0x1800033e8  add     rsp, 50h
0x1800033ec  pop     rdi
0x1800033ed  retn
0x180007436  push    rbp
0x180007438  sub     rsp, 30h
0x18000743c  mov     rbp, rdx
0x18000743f  mov     rax, [rcx]
0x180007442  xor     ecx, ecx
0x180007444  cmp     dword ptr [rax], 0C0000006h
0x18000744a  setz    cl
0x18000744d  mov     eax, ecx
0x18000744f  add     rsp, 30h
0x180007453  pop     rbp
0x180007454  retn
```
