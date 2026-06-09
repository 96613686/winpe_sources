# SetUpdateTriggerRegistry(ulong)

- ea: `0x180039fa4`
- end: `0x18003a05f`
- name: `?SetUpdateTriggerRegistry@@YAJK@Z`
- size: `187`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x18001e5d0`
- `0x1800340f0`

## callees

- `0x180039fa4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a051`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a051`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003a02c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003a02c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039fef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039fef`

## string_xrefs

- `0x18003a018`: `AvailableUpdates`

## pseudocode

```c
__int64 __fastcall SetUpdateTriggerRegistry(int a1)
{
  LSTATUS v1; // eax
  signed int v2; // ebx
  LSTATUS v3; // eax
  int Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  Data = a1;
  hKey = 0;
  if ( (a1 & 0x19FE7) == 0 && a1 != 0x4000 )
    Data = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\SecureBoot", 0, 2u, &hKey);
  v2 = v1;
  if ( v1 > 0 )
    v2 = (unsigned __int16)v1 | 0x80070000;
  if ( v2 >= 0 )
  {
    v3 = RegSetValueExW(hKey, L"AvailableUpdates", 0, 4u, (const BYTE *)&Data, 4u);
    v2 = v3;
    if ( v3 > 0 )
      v2 = (unsigned __int16)v3 | 0x80070000;
    if ( v2 >= 0 )
      v2 = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180039fa4  mov     [rsp+Data], ecx
0x180039fa8  push    rbx
0x180039fa9  sub     rsp, 30h
0x180039fad  mov     [rsp+38h+hKey], 0
0x180039fb6  test    ecx, 19FE7h
0x180039fbc  jnz     short loc_180039FCE
0x180039fbe  cmp     ecx, 4000h
0x180039fc4  jz      short loc_180039FCE
0x180039fc6  mov     [rsp+38h+Data], 0
0x180039fce  lea     rax, [rsp+38h+hKey]
0x180039fd3  mov     r9d, 2; samDesired
0x180039fd9  xor     r8d, r8d; ulOptions
0x180039fdc  mov     [rsp+38h+phkResult], rax; phkResult
0x180039fe1  lea     rdx, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Control\\Sec"...
0x180039fe8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180039fef  call    cs:__imp_RegOpenKeyExW
0x180039ff5  mov     ebx, eax
0x180039ff7  test    eax, eax
0x180039ff9  jle     short loc_18003A004
0x180039ffb  movzx   ebx, ax
0x180039ffe  or      ebx, 80070000h
0x18003a004  test    ebx, ebx
0x18003a006  js      short loc_18003A047
0x18003a008  mov     rcx, [rsp+38h+hKey]; hKey
0x18003a00d  lea     rax, [rsp+38h+Data]
0x18003a012  mov     r9d, 4; dwType
0x18003a018  lea     rdx, aAvailableupdat; "AvailableUpdates"
0x18003a01f  mov     [rsp+38h+cbData], r9d; cbData
0x18003a024  xor     r8d, r8d; Reserved
0x18003a027  mov     [rsp+38h+phkResult], rax; lpData
0x18003a02c  call    cs:__imp_RegSetValueExW
0x18003a032  mov     ebx, eax
0x18003a034  test    eax, eax
0x18003a036  jle     short loc_18003A041
0x18003a038  movzx   ebx, ax
0x18003a03b  or      ebx, 80070000h
0x18003a041  test    ebx, ebx
0x18003a043  js      short loc_18003A047
0x18003a045  xor     ebx, ebx
0x18003a047  mov     rcx, [rsp+38h+hKey]; hKey
0x18003a04c  test    rcx, rcx
0x18003a04f  jz      short loc_18003A057
0x18003a051  call    cs:__imp_RegCloseKey
0x18003a057  mov     eax, ebx
0x18003a059  add     rsp, 30h
0x18003a05d  pop     rbx
0x18003a05e  retn
```
