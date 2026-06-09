# CfSetAppPolicy

- ea: `0x180003af0`
- end: `0x180003b7f`
- name: `CfSetAppPolicy`
- size: `143`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180003af0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003b52`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003b52`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003b15`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003b15`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003b71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003b71`

## pseudocode

```c
__int64 __fastcall CfSetAppPolicy(HKEY a1, const WCHAR *a2, int a3)
{
  LSTATUS v3; // eax
  signed int v4; // ebx
  LSTATUS v5; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+50h] [rbp+18h] BYREF

  Data = a3;
  hKey = 0;
  v3 = RegOpenKeyExW(a1, a2, 0, 0x20006u, &hKey);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 >= 0 )
  {
    v5 = RegSetValueExW(hKey, L"Enabled", 0, 4u, (const BYTE *)&Data, 4u);
    v4 = v5;
    if ( v5 > 0 )
      v4 = (unsigned __int16)v5 | 0x80070000;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180003af0  mov     r11, rsp
0x180003af3  mov     [r11+18h], r8d
0x180003af7  push    rbx
0x180003af8  sub     rsp, 30h
0x180003afc  lea     rax, [r11+8]
0x180003b00  mov     qword ptr [r11+8], 0
0x180003b08  mov     r9d, 20006h; samDesired
0x180003b0e  mov     [r11-18h], rax
0x180003b12  xor     r8d, r8d; ulOptions
0x180003b15  call    cs:__imp_RegOpenKeyExW
0x180003b1b  mov     ebx, eax
0x180003b1d  test    eax, eax
0x180003b1f  jle     short loc_180003B2A
0x180003b21  movzx   ebx, ax
0x180003b24  or      ebx, 80070000h
0x180003b2a  test    ebx, ebx
0x180003b2c  js      short loc_180003B67
0x180003b2e  mov     rcx, [rsp+38h+hKey]; hKey
0x180003b33  lea     rax, [rsp+38h+Data]
0x180003b38  mov     r9d, 4; dwType
0x180003b3e  lea     rdx, ValueName; "Enabled"
0x180003b45  mov     [rsp+38h+cbData], r9d; cbData
0x180003b4a  xor     r8d, r8d; Reserved
0x180003b4d  mov     [rsp+38h+lpData], rax; lpData
0x180003b52  call    cs:__imp_RegSetValueExW
0x180003b58  mov     ebx, eax
0x180003b5a  test    eax, eax
0x180003b5c  jle     short loc_180003B67
0x180003b5e  movzx   ebx, ax
0x180003b61  or      ebx, 80070000h
0x180003b67  mov     rcx, [rsp+38h+hKey]; hKey
0x180003b6c  test    rcx, rcx
0x180003b6f  jz      short loc_180003B77
0x180003b71  call    cs:__imp_RegCloseKey
0x180003b77  mov     eax, ebx
0x180003b79  add     rsp, 30h
0x180003b7d  pop     rbx
0x180003b7e  retn
```
