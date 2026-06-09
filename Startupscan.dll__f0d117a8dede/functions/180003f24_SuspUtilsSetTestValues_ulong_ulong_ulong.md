# SuspUtilsSetTestValues(ulong,ulong,ulong)

- ea: `0x180003f24`
- end: `0x180004057`
- name: `?SuspUtilsSetTestValues@@YAKKKK@Z`
- size: `307`
- prototype: `__int64 __fastcall(int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003610`

## callees

- `0x180003f24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003fe2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000400c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004036`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003fe2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000400c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004036`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003f72`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003f72`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180003fae`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180003fae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004047`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004047`

## pseudocode

```c
__int64 __fastcall SuspUtilsSetTestValues(int a1, int a2, int a3)
{
  unsigned int ValueW; // ebx
  DWORD pcbData; // [rsp+40h] [rbp-10h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-8h] BYREF
  int Data; // [rsp+70h] [rbp+20h] BYREF
  int v8; // [rsp+78h] [rbp+28h] BYREF
  int v9; // [rsp+80h] [rbp+30h] BYREF
  int pvData; // [rsp+88h] [rbp+38h] BYREF

  v9 = a3;
  v8 = a2;
  Data = a1;
  hkey = 0;
  pcbData = 4;
  pvData = 0;
  ValueW = RegOpenKeyExW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\StartupNotify",
             0,
             0x2001Fu,
             &hkey);
  if ( !ValueW )
  {
    ValueW = RegGetValueW(hkey, 0, L"TestMode", 0x18u, 0, &pvData, &pcbData);
    if ( !ValueW && pvData == 1 )
    {
      ValueW = RegSetValueExW(hkey, L"UnSeenStartupEntries", 0, 4u, (const BYTE *)&Data, 4u);
      if ( !ValueW )
      {
        ValueW = RegSetValueExW(hkey, L"TotalStartupEntries", 0, 4u, (const BYTE *)&v8, 4u);
        if ( !ValueW )
          ValueW = RegSetValueExW(hkey, L"OEMStartupEntries", 0, 4u, (const BYTE *)&v9, 4u);
      }
    }
  }
  if ( hkey )
    RegCloseKey(hkey);
  return ValueW;
}

```

## disassembly

```asm
0x180003f24  mov     [rsp-18h+arg_10], r8d
0x180003f29  mov     [rsp-18h+arg_8], edx
0x180003f2d  mov     [rsp-18h+Data], ecx
0x180003f31  push    rbp
0x180003f32  push    rbx
0x180003f33  push    rsi
0x180003f34  mov     rbp, rsp
0x180003f37  sub     rsp, 50h
0x180003f3b  lea     rax, [rbp+hkey]
0x180003f3f  mov     [rbp+hkey], 0
0x180003f47  mov     esi, 4
0x180003f4c  mov     [rsp+50h+phkResult], rax; phkResult
0x180003f51  mov     r9d, 2001Fh; samDesired
0x180003f57  mov     [rbp+var_10], esi
0x180003f5a  xor     r8d, r8d; ulOptions
0x180003f5d  mov     [rbp+arg_18], 0
0x180003f64  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180003f6b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180003f72  call    cs:__imp_RegOpenKeyExW
0x180003f78  mov     ebx, eax
0x180003f7a  test    eax, eax
0x180003f7c  jnz     loc_18000403E
0x180003f82  mov     rcx, [rbp+hkey]; hkey
0x180003f86  lea     rax, [rbp+var_10]
0x180003f8a  mov     [rsp+50h+pcbData], rax; pcbData
0x180003f8f  lea     r9d, [rsi+14h]; dwFlags
0x180003f93  lea     rax, [rbp+arg_18]
0x180003f97  xor     edx, edx; lpSubKey
0x180003f99  mov     [rsp+50h+pvData], rax; pvData
0x180003f9e  lea     r8, Value; "TestMode"
0x180003fa5  mov     [rsp+50h+phkResult], 0; pdwType
0x180003fae  call    cs:__imp_RegGetValueW
0x180003fb4  mov     ebx, eax
0x180003fb6  test    eax, eax
0x180003fb8  jnz     loc_18000403E
0x180003fbe  cmp     [rbp+arg_18], 1
0x180003fc2  jnz     short loc_18000403E
0x180003fc4  mov     rcx, [rbp+hkey]; hKey
0x180003fc8  lea     rax, [rbp+Data]
0x180003fcc  mov     dword ptr [rsp+50h+pvData], esi; cbData
0x180003fd0  lea     rdx, aUnseenstartupe; "UnSeenStartupEntries"
0x180003fd7  mov     r9d, esi; dwType
0x180003fda  mov     [rsp+50h+phkResult], rax; lpData
0x180003fdf  xor     r8d, r8d; Reserved
0x180003fe2  call    cs:__imp_RegSetValueExW
0x180003fe8  mov     ebx, eax
0x180003fea  test    eax, eax
0x180003fec  jnz     short loc_18000403E
0x180003fee  mov     rcx, [rbp+hkey]; hKey
0x180003ff2  lea     rax, [rbp+arg_8]
0x180003ff6  mov     dword ptr [rsp+50h+pvData], esi; cbData
0x180003ffa  lea     rdx, aTotalstartupen; "TotalStartupEntries"
0x180004001  mov     r9d, esi; dwType
0x180004004  mov     [rsp+50h+phkResult], rax; lpData
0x180004009  xor     r8d, r8d; Reserved
0x18000400c  call    cs:__imp_RegSetValueExW
0x180004012  mov     ebx, eax
0x180004014  test    eax, eax
0x180004016  jnz     short loc_18000403E
0x180004018  mov     rcx, [rbp+hkey]; hKey
0x18000401c  lea     rax, [rbp+arg_10]
0x180004020  mov     dword ptr [rsp+50h+pvData], esi; cbData
0x180004024  lea     rdx, aOemstartupentr; "OEMStartupEntries"
0x18000402b  mov     r9d, esi; dwType
0x18000402e  mov     [rsp+50h+phkResult], rax; lpData
0x180004033  xor     r8d, r8d; Reserved
0x180004036  call    cs:__imp_RegSetValueExW
0x18000403c  mov     ebx, eax
0x18000403e  mov     rcx, [rbp+hkey]; hKey
0x180004042  test    rcx, rcx
0x180004045  jz      short loc_18000404D
0x180004047  call    cs:__imp_RegCloseKey
0x18000404d  mov     eax, ebx
0x18000404f  add     rsp, 50h
0x180004053  pop     rsi
0x180004054  pop     rbx
0x180004055  pop     rbp
0x180004056  retn
```
