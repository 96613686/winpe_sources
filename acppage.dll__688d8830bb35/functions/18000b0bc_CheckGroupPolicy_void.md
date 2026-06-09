# CheckGroupPolicy(void)

- ea: `0x18000b0bc`
- end: `0x18000b161`
- name: `?CheckGroupPolicy@@YAHXZ`
- size: `165`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c630`

## callees

- `0x18000b0bc`

## import_xrefs

- `KERNEL32!RegQueryValueExW` at `0x18000b138`
- `KERNEL32!RegQueryValueExW` at `0x18000b138`
- `KERNEL32!RegOpenKeyExW` at `0x18000b104`
- `KERNEL32!RegOpenKeyExW` at `0x18000b104`
- `KERNEL32!RegCloseKey` at `0x18000b144`
- `KERNEL32!RegCloseKey` at `0x18000b144`

## string_xrefs

- `0x18000b0ef`: `Software\Policies\Microsoft\Windows\AppCompat`

## pseudocode

```c
__int64 CheckGroupPolicy(void)
{
  LSTATUS v0; // ebx
  __int64 result; // rax
  int Data; // [rsp+50h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF
  DWORD Type; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  cbData = 4;
  Data = 0;
  Type = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Windows\\AppCompat", 0, 0x20019u, &hKey) )
    return 1;
  Data = 0;
  cbData = 4;
  v0 = RegQueryValueExW(hKey, L"DisablePropPage", 0, &Type, (LPBYTE)&Data, &cbData);
  RegCloseKey(hKey);
  if ( v0 )
    return 1;
  result = 0;
  if ( !Data )
    return 1;
  return result;
}

```

## disassembly

```asm
0x18000b0bc  push    rbp
0x18000b0be  push    rbx
0x18000b0bf  mov     rbp, rsp
0x18000b0c2  sub     rsp, 38h
0x18000b0c6  lea     rax, [rbp+hKey]
0x18000b0ca  mov     [rbp+hKey], 0
0x18000b0d2  mov     ebx, 4
0x18000b0d7  mov     [rsp+38h+phkResult], rax; phkResult
0x18000b0dc  mov     r9d, 20019h; samDesired
0x18000b0e2  mov     [rbp+cbData], ebx
0x18000b0e5  xor     r8d, r8d; ulOptions
0x18000b0e8  mov     [rbp+Data], 0
0x18000b0ef  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows"...
0x18000b0f6  mov     [rbp+Type], 0
0x18000b0fd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b104  call    cs:__imp_RegOpenKeyExW
0x18000b10a  test    eax, eax
0x18000b10c  jnz     short loc_18000B155
0x18000b10e  mov     rcx, [rbp+hKey]; hKey
0x18000b112  lea     r9, [rbp+Type]; lpType
0x18000b116  mov     [rbp+Data], eax
0x18000b119  lea     rdx, ValueName; "DisablePropPage"
0x18000b120  lea     rax, [rbp+cbData]
0x18000b124  mov     [rbp+cbData], ebx
0x18000b127  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000b12c  xor     r8d, r8d; lpReserved
0x18000b12f  lea     rax, [rbp+Data]
0x18000b133  mov     [rsp+38h+phkResult], rax; lpData
0x18000b138  call    cs:__imp_RegQueryValueExW
0x18000b13e  mov     rcx, [rbp+hKey]; hKey
0x18000b142  mov     ebx, eax
0x18000b144  call    cs:__imp_RegCloseKey
0x18000b14a  test    ebx, ebx
0x18000b14c  jnz     short loc_18000B155
0x18000b14e  xor     eax, eax
0x18000b150  cmp     [rbp+Data], eax
0x18000b153  jnz     short loc_18000B15A
0x18000b155  mov     eax, 1
0x18000b15a  add     rsp, 38h
0x18000b15e  pop     rbx
0x18000b15f  pop     rbp
0x18000b160  retn
```
