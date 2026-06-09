# BipEnergyBudgetAddRegOverrideImportantPackage

- ea: `0x180080e38`
- end: `0x180080f0b`
- name: `BipEnergyBudgetAddRegOverrideImportantPackage`
- size: `211`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800865dc`

## callees

- `0x180030a80`
- `0x180080e38`
- `0x180080f14`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180080ef3`
- `ntdll!RtlFreeUnicodeString` at `0x180080ef3`
- `ntdll!RtlInitUnicodeString` at `0x180080e69`
- `ntdll!RtlInitUnicodeString` at `0x180080e7a`
- `ntdll!RtlInitUnicodeString` at `0x180080e69`
- `ntdll!RtlInitUnicodeString` at `0x180080e7a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080ee9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080ee9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180080ea0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180080ea0`

## string_xrefs

- `0x180080e92`: `SYSTEM\CurrentControlSet\Services\BrokerInfrastructure\Parameters`

## pseudocode

```c
__int64 __fastcall BipEnergyBudgetAddRegOverrideImportantPackage(__int64 a1)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+18h] BYREF

  hKey = 0;
  DestinationString = 0;
  ValueName = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  RtlInitUnicodeString(&ValueName, L"EnergyBudgetAlwaysImportantPackages");
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\BrokerInfrastructure\\Parameters",
         0,
         1u,
         &hKey);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0xC0070000;
  }
  else if ( (int)BipReadRegMultiSz(hKey, &ValueName, &DestinationString) < 0 )
  {
    v3 = 0;
  }
  else
  {
    v3 = BipEnergyBudgetAddStringToAlwaysImportantAppTable(a1, &DestinationString);
  }
  if ( hKey )
    RegCloseKey(hKey);
  RtlFreeUnicodeString(&DestinationString);
  return v3;
}

```

## disassembly

```asm
0x180080e38  mov     [rsp-8+arg_0], rbx
0x180080e3d  mov     [rsp-8+arg_10], rdi
0x180080e42  push    rbp
0x180080e43  mov     rbp, rsp
0x180080e46  sub     rsp, 50h
0x180080e4a  mov     rdi, rcx
0x180080e4d  mov     [rbp+hKey], 0
0x180080e55  xorps   xmm0, xmm0
0x180080e58  lea     rcx, [rbp+DestinationString]; DestinationString
0x180080e5c  xorps   xmm1, xmm1
0x180080e5f  xor     edx, edx; SourceString
0x180080e61  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180080e65  movups  xmmword ptr [rbp+ValueName.Length], xmm1
0x180080e69  call    cs:__imp_RtlInitUnicodeString
0x180080e6f  lea     rdx, aEnergybudgetal; "EnergyBudgetAlwaysImportantPackages"
0x180080e76  lea     rcx, [rbp+ValueName]; DestinationString
0x180080e7a  call    cs:__imp_RtlInitUnicodeString
0x180080e80  lea     rax, [rbp+hKey]
0x180080e84  mov     r9d, 1; samDesired
0x180080e8a  xor     r8d, r8d; ulOptions
0x180080e8d  mov     [rsp+50h+phkResult], rax; phkResult
0x180080e92  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Br"...
0x180080e99  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180080ea0  call    cs:__imp_RegOpenKeyExW
0x180080ea6  mov     ebx, eax
0x180080ea8  test    eax, eax
0x180080eaa  jz      short loc_180080EB9
0x180080eac  jle     short loc_180080EE0
0x180080eae  movzx   ebx, ax
0x180080eb1  or      ebx, 0C0070000h
0x180080eb7  jmp     short loc_180080EE0
0x180080eb9  mov     rcx, [rbp+hKey]; KeyHandle
0x180080ebd  lea     r8, [rbp+DestinationString]; DestinationString
0x180080ec1  lea     rdx, [rbp+ValueName]; ValueName
0x180080ec5  call    BipReadRegMultiSz
0x180080eca  test    eax, eax
0x180080ecc  js      short loc_180080EDE
0x180080ece  lea     rdx, [rbp+DestinationString]
0x180080ed2  mov     rcx, rdi
0x180080ed5  call    BipEnergyBudgetAddStringToAlwaysImportantAppTable
0x180080eda  mov     ebx, eax
0x180080edc  jmp     short loc_180080EE0
0x180080ede  xor     ebx, ebx
0x180080ee0  mov     rcx, [rbp+hKey]; hKey
0x180080ee4  test    rcx, rcx
0x180080ee7  jz      short loc_180080EEF
0x180080ee9  call    cs:__imp_RegCloseKey
0x180080eef  lea     rcx, [rbp+DestinationString]; UnicodeString
0x180080ef3  call    cs:__imp_RtlFreeUnicodeString
0x180080ef9  mov     rdi, [rsp+50h+arg_10]
0x180080efe  mov     eax, ebx
0x180080f00  mov     rbx, [rsp+50h+arg_0]
0x180080f05  add     rsp, 50h
0x180080f09  pop     rbp
0x180080f0a  retn
```
