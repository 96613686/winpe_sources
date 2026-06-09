# RegisterInterface

- ea: `0x180038078`
- end: `0x1800381e2`
- name: `RegisterInterface`
- size: `362`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180040dd4`

## callees

- `0x180038078`
- `0x180038220`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003817e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800381cf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003817e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800381cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800380d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038125`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800380d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038125`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800380ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800380fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800380ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800380fd`

## pseudocode

```c
__int64 __fastcall RegisterInterface(HKEY hKey, __int64 a2)
{
  unsigned int v4; // ebx
  HKEY hKeya; // [rsp+70h] [rbp+18h] BYREF

  hKeya = 0;
  if ( !RegOpenKeyExW(hKey, L"Interface", 0, 0x2000000u, &hKeya)
    || (v4 = -2147319780, !RegCreateKeyExW(hKey, L"Interface", 0, 0, 0, 0x2000000u, 0, &hKeya, 0)) )
  {
    v4 = RegisterInterfaceWorker(hKeya, a2, 0x2000000);
    RegCloseKey(hKeya);
    if ( !v4 )
    {
      if ( !RegOpenKeyExW(hKey, L"Interface", 0, 0x2000200u, &hKeya)
        || (v4 = -2147319780, !RegCreateKeyExW(hKey, L"Interface", 0, 0, 0, 0x2000200u, 0, &hKeya, 0)) )
      {
        v4 = RegisterInterfaceWorker(hKeya, a2, 33554944);
        RegCloseKey(hKeya);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180038078  mov     r11, rsp
0x18003807b  mov     [r11+8], rbx
0x18003807f  mov     [r11+10h], rsi
0x180038083  push    rdi
0x180038084  sub     rsp, 50h
0x180038088  mov     rsi, rdx
0x18003808b  mov     qword ptr [r11+18h], 0
0x180038093  lea     rax, [r11+18h]
0x180038097  mov     r9d, 2000000h; samDesired
0x18003809d  lea     rdx, ?Interface@Constants@Catalog@Com@@3QBGB; "Interface"
0x1800380a4  mov     [r11-38h], rax
0x1800380a8  xor     r8d, r8d; ulOptions
0x1800380ab  mov     rdi, rcx
0x1800380ae  call    cs:__imp_RegOpenKeyExW
0x1800380b4  test    eax, eax
0x1800380b6  jnz     loc_18003813D
0x1800380bc  mov     rcx, [rsp+58h+hKey]
0x1800380c1  mov     r8d, 2000000h
0x1800380c7  mov     rdx, rsi
0x1800380ca  call    RegisterInterfaceWorker
0x1800380cf  mov     rcx, [rsp+58h+hKey]; hKey
0x1800380d4  mov     ebx, eax
0x1800380d6  call    cs:__imp_RegCloseKey
0x1800380dc  test    ebx, ebx
0x1800380de  jnz     short loc_18003812B
0x1800380e0  lea     rax, [rsp+58h+hKey]
0x1800380e5  mov     r9d, 2000200h; samDesired
0x1800380eb  xor     r8d, r8d; ulOptions
0x1800380ee  mov     [rsp+58h+phkResult], rax; phkResult
0x1800380f3  lea     rdx, ?Interface@Constants@Catalog@Com@@3QBGB; "Interface"
0x1800380fa  mov     rcx, rdi; hKey
0x1800380fd  call    cs:__imp_RegOpenKeyExW
0x180038103  test    eax, eax
0x180038105  jnz     loc_18003818E
0x18003810b  mov     rcx, [rsp+58h+hKey]
0x180038110  mov     r8d, 2000200h
0x180038116  mov     rdx, rsi
0x180038119  call    RegisterInterfaceWorker
0x18003811e  mov     rcx, [rsp+58h+hKey]; hKey
0x180038123  mov     ebx, eax
0x180038125  call    cs:__imp_RegCloseKey
0x18003812b  mov     rsi, [rsp+58h+arg_8]
0x180038130  mov     eax, ebx
0x180038132  mov     rbx, [rsp+58h+arg_0]
0x180038137  add     rsp, 50h
0x18003813b  pop     rdi
0x18003813c  retn
0x18003813d  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180038146  lea     rax, [rsp+58h+hKey]
0x18003814b  mov     [rsp+58h+var_20], rax; phkResult
0x180038150  lea     rdx, ?Interface@Constants@Catalog@Com@@3QBGB; "Interface"
0x180038157  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180038160  xor     r9d, r9d; lpClass
0x180038163  mov     [rsp+58h+samDesired], 2000000h; samDesired
0x18003816b  xor     r8d, r8d; Reserved
0x18003816e  mov     rcx, rdi; hKey
0x180038171  mov     dword ptr [rsp+58h+phkResult], 0; dwOptions
0x180038179  mov     ebx, 8002801Ch
0x18003817e  call    cs:__imp_RegCreateKeyExW
0x180038184  test    eax, eax
0x180038186  jz      loc_1800380BC
0x18003818c  jmp     short loc_18003812B
0x18003818e  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180038197  lea     rax, [rsp+58h+hKey]
0x18003819c  mov     [rsp+58h+var_20], rax; phkResult
0x1800381a1  lea     rdx, ?Interface@Constants@Catalog@Com@@3QBGB; "Interface"
0x1800381a8  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800381b1  xor     r9d, r9d; lpClass
0x1800381b4  mov     [rsp+58h+samDesired], 2000200h; samDesired
0x1800381bc  xor     r8d, r8d; Reserved
0x1800381bf  mov     rcx, rdi; hKey
0x1800381c2  mov     dword ptr [rsp+58h+phkResult], 0; dwOptions
0x1800381ca  mov     ebx, 8002801Ch
0x1800381cf  call    cs:__imp_RegCreateKeyExW
0x1800381d5  test    eax, eax
0x1800381d7  jz      loc_18003810B
0x1800381dd  jmp     loc_18003812B
```
