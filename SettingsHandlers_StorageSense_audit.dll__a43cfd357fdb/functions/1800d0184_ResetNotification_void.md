# ResetNotification(void)

- ea: `0x1800d0184`
- end: `0x1800d0230`
- name: `?ResetNotification@@YAJXZ`
- size: `172`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d2c1c`

## callees

- `0x1800d0184`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d01bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d01bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0222`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0222`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d01fb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d01fb`

## pseudocode

```c
__int64 ResetNotification(void)
{
  LSTATUS v0; // eax
  signed int v1; // ebx
  LSTATUS v2; // eax
  int Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  Data = 0;
  v0 = RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\StartupNotify",
         0,
         0x20006u,
         &hKey);
  v1 = v0;
  if ( !v0 )
    goto LABEL_5;
  if ( v0 > 0 )
    v1 = (unsigned __int16)v0 | 0x80070000;
  if ( v1 >= 0 )
  {
LABEL_5:
    v2 = RegSetValueExW(hKey, L"EnableStartupAppNotification", 0, 4u, (const BYTE *)&Data, 4u);
    v1 = v2;
    if ( !v2 )
      goto LABEL_9;
    if ( v2 > 0 )
      v1 = (unsigned __int16)v2 | 0x80070000;
    if ( v1 >= 0 )
LABEL_9:
      v1 = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800d0184  push    rbx
0x1800d0186  sub     rsp, 30h
0x1800d018a  lea     rax, [rsp+38h+hKey]
0x1800d018f  mov     [rsp+38h+hKey], 0
0x1800d0198  mov     r9d, 20006h; samDesired
0x1800d019e  mov     [rsp+38h+phkResult], rax; phkResult
0x1800d01a3  xor     r8d, r8d; ulOptions
0x1800d01a6  mov     [rsp+38h+Data], 0
0x1800d01ae  lea     rdx, aSoftwareMicros_20; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800d01b5  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800d01bc  call    cs:__imp_RegOpenKeyExW
0x1800d01c2  mov     ebx, eax
0x1800d01c4  test    eax, eax
0x1800d01c6  jz      short loc_1800D01D7
0x1800d01c8  jle     short loc_1800D01D3
0x1800d01ca  movzx   ebx, ax
0x1800d01cd  or      ebx, 80070000h
0x1800d01d3  test    ebx, ebx
0x1800d01d5  js      short loc_1800D0218
0x1800d01d7  mov     rcx, [rsp+38h+hKey]; hKey
0x1800d01dc  lea     rax, [rsp+38h+Data]
0x1800d01e1  mov     r9d, 4; dwType
0x1800d01e7  lea     rdx, aEnablestartupa; "EnableStartupAppNotification"
0x1800d01ee  mov     [rsp+38h+cbData], r9d; cbData
0x1800d01f3  xor     r8d, r8d; Reserved
0x1800d01f6  mov     [rsp+38h+phkResult], rax; lpData
0x1800d01fb  call    cs:__imp_RegSetValueExW
0x1800d0201  mov     ebx, eax
0x1800d0203  test    eax, eax
0x1800d0205  jz      short loc_1800D0216
0x1800d0207  jle     short loc_1800D0212
0x1800d0209  movzx   ebx, ax
0x1800d020c  or      ebx, 80070000h
0x1800d0212  test    ebx, ebx
0x1800d0214  js      short loc_1800D0218
0x1800d0216  xor     ebx, ebx
0x1800d0218  mov     rcx, [rsp+38h+hKey]; hKey
0x1800d021d  test    rcx, rcx
0x1800d0220  jz      short loc_1800D0228
0x1800d0222  call    cs:__imp_RegCloseKey
0x1800d0228  mov     eax, ebx
0x1800d022a  add     rsp, 30h
0x1800d022e  pop     rbx
0x1800d022f  retn
```
