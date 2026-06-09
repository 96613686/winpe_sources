# StatsEnabled(ushort const *)

- ea: `0x180042cf0`
- end: `0x180042dcb`
- name: `?StatsEnabled@@YAHPEBG@Z`
- size: `219`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18004fa44`
- `0x1800a5e3c`

## callees

- `0x180042cf0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180042d55`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180042d55`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042d92`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042d92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042db1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042db1`

## pseudocode

```c
__int64 __fastcall StatsEnabled(LPCWSTR lpSubKey)
{
  unsigned int v1; // ebx
  DWORD v3; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+18h] BYREF
  DWORD Type; // [rsp+80h] [rbp+20h] BYREF
  int Data; // [rsp+88h] [rbp+28h] BYREF

  hKey = 0;
  v1 = 0;
  v3 = 0;
  Data = 0;
  cbData = 0;
  Type = 0;
  if ( !RegCreateKeyExW(HKEY_CURRENT_USER, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, &v3) )
  {
    cbData = 4;
    Type = 4;
    if ( !RegQueryValueExW(hKey, L"Stats", 0, &Type, (LPBYTE)&Data, &cbData) )
      LOBYTE(v1) = Data != 0;
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v1;
}

```

## disassembly

```asm
0x180042cf0  mov     r11, rsp
0x180042cf3  mov     [r11+8], rbx
0x180042cf7  push    rbp
0x180042cf8  mov     rbp, rsp
0x180042cfb  sub     rsp, 60h
0x180042cff  lea     rax, [rbp+var_10]
0x180042d03  mov     [rbp+hKey], 0
0x180042d0b  mov     [r11-28h], rax
0x180042d0f  xor     ebx, ebx
0x180042d11  lea     rax, [rbp+hKey]
0x180042d15  mov     [rbp+var_10], 0
0x180042d1c  mov     [r11-30h], rax
0x180042d20  mov     rdx, rcx; lpSubKey
0x180042d23  mov     [r11-38h], rbx
0x180042d27  xor     r9d, r9d; lpClass
0x180042d2a  mov     [rsp+60h+samDesired], 2001Fh; samDesired
0x180042d32  xor     r8d, r8d; Reserved
0x180042d35  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180042d3c  mov     [rsp+60h+dwOptions], ebx; dwOptions
0x180042d40  mov     [rbp+Data], 0
0x180042d47  mov     [rbp+cbData], 0
0x180042d4e  mov     [rbp+Type], 0
0x180042d55  call    cs:__imp_RegCreateKeyExW
0x180042d5c  nop     dword ptr [rax+rax+00h]
0x180042d61  test    eax, eax
0x180042d63  jnz     short loc_180042DBD
0x180042d65  mov     rcx, [rbp+hKey]; hKey
0x180042d69  lea     eax, [rbx+4]
0x180042d6c  mov     [rbp+cbData], eax
0x180042d6f  lea     r9, [rbp+Type]; lpType
0x180042d73  mov     [rbp+Type], eax
0x180042d76  lea     rdx, aStats; "Stats"
0x180042d7d  lea     rax, [rbp+cbData]
0x180042d81  xor     r8d, r8d; lpReserved
0x180042d84  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x180042d89  lea     rax, [rbp+Data]
0x180042d8d  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180042d92  call    cs:__imp_RegQueryValueExW
0x180042d99  nop     dword ptr [rax+rax+00h]
0x180042d9e  test    eax, eax
0x180042da0  jnz     short loc_180042DA8
0x180042da2  cmp     [rbp+Data], ebx
0x180042da5  setnz   bl
0x180042da8  mov     rcx, [rbp+hKey]; hKey
0x180042dac  test    rcx, rcx
0x180042daf  jz      short loc_180042DBD
0x180042db1  call    cs:__imp_RegCloseKey
0x180042db8  nop     dword ptr [rax+rax+00h]
0x180042dbd  mov     eax, ebx
0x180042dbf  mov     rbx, [rsp+60h+arg_0]
0x180042dc4  add     rsp, 60h
0x180042dc8  pop     rbp
0x180042dc9  retn
```
