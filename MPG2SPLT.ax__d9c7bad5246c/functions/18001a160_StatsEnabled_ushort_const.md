# StatsEnabled(ushort const *)

- ea: `0x18001a160`
- end: `0x18001a228`
- name: `?StatsEnabled@@YAHPEBG@Z`
- size: `200`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800156e4`
- `0x180015a0c`

## callees

- `0x18001a160`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18001a215`
- `ADVAPI32!RegCloseKey` at `0x18001a215`
- `ADVAPI32!RegCreateKeyExW` at `0x18001a1c5`
- `ADVAPI32!RegCreateKeyExW` at `0x18001a1c5`
- `ADVAPI32!RegQueryValueExW` at `0x18001a1fc`
- `ADVAPI32!RegQueryValueExW` at `0x18001a1fc`

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
0x18001a160  mov     r11, rsp
0x18001a163  mov     [r11+8], rbx
0x18001a167  push    rbp
0x18001a168  mov     rbp, rsp
0x18001a16b  sub     rsp, 60h
0x18001a16f  lea     rax, [rbp+var_10]
0x18001a173  mov     [rbp+hKey], 0
0x18001a17b  mov     [r11-28h], rax
0x18001a17f  xor     ebx, ebx
0x18001a181  lea     rax, [rbp+hKey]
0x18001a185  mov     [rbp+var_10], 0
0x18001a18c  mov     [r11-30h], rax
0x18001a190  mov     rdx, rcx; lpSubKey
0x18001a193  mov     [r11-38h], rbx
0x18001a197  xor     r9d, r9d; lpClass
0x18001a19a  mov     [rsp+60h+samDesired], 2001Fh; samDesired
0x18001a1a2  xor     r8d, r8d; Reserved
0x18001a1a5  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001a1ac  mov     [rsp+60h+dwOptions], ebx; dwOptions
0x18001a1b0  mov     [rbp+Data], 0
0x18001a1b7  mov     [rbp+cbData], 0
0x18001a1be  mov     [rbp+Type], 0
0x18001a1c5  call    cs:__imp_RegCreateKeyExW
0x18001a1cb  test    eax, eax
0x18001a1cd  jnz     short loc_18001A21B
0x18001a1cf  mov     rcx, [rbp+hKey]; hKey
0x18001a1d3  lea     eax, [rbx+4]
0x18001a1d6  mov     [rbp+cbData], eax
0x18001a1d9  lea     r9, [rbp+Type]; lpType
0x18001a1dd  mov     [rbp+Type], eax
0x18001a1e0  lea     rdx, aStats; "Stats"
0x18001a1e7  lea     rax, [rbp+cbData]
0x18001a1eb  xor     r8d, r8d; lpReserved
0x18001a1ee  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x18001a1f3  lea     rax, [rbp+Data]
0x18001a1f7  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x18001a1fc  call    cs:__imp_RegQueryValueExW
0x18001a202  test    eax, eax
0x18001a204  jnz     short loc_18001A20C
0x18001a206  cmp     [rbp+Data], ebx
0x18001a209  setnz   bl
0x18001a20c  mov     rcx, [rbp+hKey]; hKey
0x18001a210  test    rcx, rcx
0x18001a213  jz      short loc_18001A21B
0x18001a215  call    cs:__imp_RegCloseKey
0x18001a21b  mov     eax, ebx
0x18001a21d  mov     rbx, [rsp+60h+arg_0]
0x18001a222  add     rsp, 60h
0x18001a226  pop     rbp
0x18001a227  retn
```
