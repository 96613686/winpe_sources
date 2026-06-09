# IIS_LOGON_PROVIDER::InitializeInstance(void)

- ea: `0x18000570c`
- end: `0x1800057d6`
- name: `?InitializeInstance@IIS_LOGON_PROVIDER@@QEAAJXZ`
- size: `202`
- prototype: `__int64 __fastcall(wchar_t *Destination)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1800034c0`

## callees

- `0x1800022e0`
- `0x18000570c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005787`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005787`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005759`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005759`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800057a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800057a7`

## string_xrefs

- `0x180005752`: `System\CurrentControlSet\Services\inetinfo\Parameters`

## pseudocode

```c
__int64 __fastcall IIS_LOGON_PROVIDER::InitializeInstance(wchar_t *Destination)
{
  LSTATUS v2; // eax
  __int64 result; // rax
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD Type; // [rsp+58h] [rbp+18h] BYREF
  int Data; // [rsp+60h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF

  hKey = 0;
  Data = 0;
  Type = 0;
  cbData = 4;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\inetinfo\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    v2 = RegQueryValueExW(hKey, L"LastPriorityUPNLogon", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v2 && Type == 4 )
    {
      LOBYTE(v2) = Data != 0;
      *((_DWORD *)Destination + 641) = v2;
    }
    RegCloseKey(hKey);
    hKey = 0;
  }
  result = IIS_LOGON_PROVIDER::GetDefaultDomainName(Destination);
  if ( (int)result >= 0 )
    *((_DWORD *)Destination + 642) = 1;
  return result;
}

```

## disassembly

```asm
0x18000570c  mov     [rsp-8+arg_0], rbx
0x180005711  push    rbp
0x180005712  mov     rbp, rsp
0x180005715  sub     rsp, 40h
0x180005719  mov     rbx, rcx
0x18000571c  mov     [rbp+hKey], 0
0x180005724  lea     rax, [rbp+hKey]
0x180005728  mov     [rbp+Data], 0
0x18000572f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005736  mov     [rsp+40h+phkResult], rax; phkResult
0x18000573b  mov     r9d, 20019h; samDesired
0x180005741  mov     [rbp+Type], 0
0x180005748  xor     r8d, r8d; ulOptions
0x18000574b  mov     [rbp+cbData], 4
0x180005752  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\in"...
0x180005759  call    cs:__imp_RegOpenKeyExW
0x18000575f  test    eax, eax
0x180005761  jnz     short loc_1800057B5
0x180005763  mov     rcx, [rbp+hKey]; hKey
0x180005767  lea     rax, [rbp+cbData]
0x18000576b  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180005770  lea     r9, [rbp+Type]; lpType
0x180005774  lea     rax, [rbp+Data]
0x180005778  xor     r8d, r8d; lpReserved
0x18000577b  lea     rdx, ValueName; "LastPriorityUPNLogon"
0x180005782  mov     [rsp+40h+phkResult], rax; lpData
0x180005787  call    cs:__imp_RegQueryValueExW
0x18000578d  test    eax, eax
0x18000578f  jnz     short loc_1800057A3
0x180005791  cmp     [rbp+Type], 4
0x180005795  jnz     short loc_1800057A3
0x180005797  cmp     [rbp+Data], eax
0x18000579a  setnz   al
0x18000579d  mov     [rbx+0A04h], eax
0x1800057a3  mov     rcx, [rbp+hKey]; hKey
0x1800057a7  call    cs:__imp_RegCloseKey
0x1800057ad  mov     [rbp+hKey], 0
0x1800057b5  mov     rcx, rbx; Destination
0x1800057b8  call    ?GetDefaultDomainName@IIS_LOGON_PROVIDER@@AEAAJXZ; IIS_LOGON_PROVIDER::GetDefaultDomainName(void)
0x1800057bd  test    eax, eax
0x1800057bf  js      short loc_1800057CB
0x1800057c1  mov     dword ptr [rbx+0A08h], 1
0x1800057cb  mov     rbx, [rsp+40h+arg_0]
0x1800057d0  add     rsp, 40h
0x1800057d4  pop     rbp
0x1800057d5  retn
```
