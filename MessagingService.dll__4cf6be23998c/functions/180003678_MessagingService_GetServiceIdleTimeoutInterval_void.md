# MessagingService::_GetServiceIdleTimeoutInterval(void)

- ea: `0x180003678`
- end: `0x18000376b`
- name: `?_GetServiceIdleTimeoutInterval@MessagingService@@CAKXZ`
- size: `243`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003090`

## callees

- `0x180003678`
- `0x18000aa50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000373c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000373c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800036c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800036c2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003714`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003714`

## string_xrefs

- `0x1800036b4`: `Software\Microsoft\Messaging\Service`

## pseudocode

```c
__int64 MessagingService::_GetServiceIdleTimeoutInterval(void)
{
  LSTATUS v0; // eax
  bool v1; // sf
  HKEY v2; // rcx
  signed int v3; // ebx
  LSTATUS v4; // eax
  HKEY hKey; // [rsp+30h] [rbp-20h] BYREF
  DWORD Type; // [rsp+38h] [rbp-18h] BYREF
  BYTE Data[4]; // [rsp+3Ch] [rbp-14h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-10h] BYREF

  *(_DWORD *)Data = 0;
  hKey = 0;
  v0 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Messaging\\Service", 0, 0x20119u, &hKey);
  v1 = v0 < 0;
  if ( v0 > 0 )
    v1 = 1;
  if ( v1 )
    return 120000;
  v2 = hKey;
  v3 = -2147024809;
  if ( hKey )
  {
    Type = 0;
    cbData = 4;
    v4 = RegQueryValueExW(hKey, L"IdleTimeout(sec)", 0, &Type, Data, &cbData);
    v3 = v4;
    if ( v4 )
    {
      if ( v4 > 0 )
        goto LABEL_9;
    }
    else if ( Type != 4 )
    {
      LOWORD(v3) = 1629;
LABEL_9:
      v3 = (unsigned __int16)v3 | 0x80070000;
    }
    v2 = hKey;
  }
  RegCloseKey(v2);
  if ( v3 >= 0 )
    return (unsigned int)(1000 * *(_DWORD *)Data);
  return 120000;
}

```

## disassembly

```asm
0x180003678  mov     [rsp-8+arg_0], rbx
0x18000367d  push    rbp
0x18000367e  mov     rbp, rsp
0x180003681  sub     rsp, 50h
0x180003685  mov     rax, cs:__security_cookie
0x18000368c  xor     rax, rsp
0x18000368f  mov     [rbp+var_8], rax
0x180003693  lea     rax, [rbp+hKey]
0x180003697  mov     dword ptr [rbp+Data], 0
0x18000369e  mov     r9d, 20119h; samDesired
0x1800036a4  mov     [rsp+50h+phkResult], rax; phkResult
0x1800036a9  xor     r8d, r8d; ulOptions
0x1800036ac  mov     [rbp+hKey], 0
0x1800036b4  lea     rdx, SubKey; "Software\\Microsoft\\Messaging\\Service"
0x1800036bb  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800036c2  call    cs:__imp_RegOpenKeyExW
0x1800036c8  test    eax, eax
0x1800036ca  jle     short loc_1800036D6
0x1800036cc  movzx   eax, ax
0x1800036cf  or      eax, 80070000h
0x1800036d4  test    eax, eax
0x1800036d6  js      short loc_18000374F
0x1800036d8  mov     rcx, [rbp+hKey]; hKey
0x1800036dc  mov     ebx, 80070057h
0x1800036e1  test    rcx, rcx
0x1800036e4  jz      short loc_18000373C
0x1800036e6  lea     rax, [rbp+cbData]
0x1800036ea  mov     [rbp+Type], 0
0x1800036f1  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800036f6  lea     r9, [rbp+Type]; lpType
0x1800036fa  lea     rax, [rbp+Data]
0x1800036fe  mov     [rbp+cbData], 4
0x180003705  xor     r8d, r8d; lpReserved
0x180003708  mov     [rsp+50h+phkResult], rax; lpData
0x18000370d  lea     rdx, ValueName; "IdleTimeout(sec)"
0x180003714  call    cs:__imp_RegQueryValueExW
0x18000371a  mov     ebx, eax
0x18000371c  test    eax, eax
0x18000371e  jnz     short loc_18000372D
0x180003720  cmp     [rbp+Type], 4
0x180003724  jz      short loc_180003738
0x180003726  mov     ebx, 65Dh
0x18000372b  jmp     short loc_18000372F
0x18000372d  jle     short loc_180003738
0x18000372f  movzx   ebx, bx
0x180003732  or      ebx, 80070000h
0x180003738  mov     rcx, [rbp+hKey]; hKey
0x18000373c  call    cs:__imp_RegCloseKey
0x180003742  test    ebx, ebx
0x180003744  js      short loc_18000374F
0x180003746  imul    eax, dword ptr [rbp+Data], 3E8h
0x18000374d  jmp     short loc_180003754
0x18000374f  mov     eax, 1D4C0h
0x180003754  mov     rcx, [rbp+var_8]
0x180003758  xor     rcx, rsp; StackCookie
0x18000375b  call    __security_check_cookie
0x180003760  mov     rbx, [rsp+50h+arg_0]
0x180003765  add     rsp, 50h
0x180003769  pop     rbp
0x18000376a  retn
```
