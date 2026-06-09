# SetUEFICA2023Status

- ea: `0x180057ca0`
- end: `0x180057d43`
- name: `SetUEFICA2023Status`
- size: `163`
- prototype: `__int64 __fastcall(BYTE *lpData)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180057a18`

## callees

- `0x18003c0b8`
- `0x180057ca0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057d32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057d32`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180057d27`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180057d27`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180057ceb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180057ceb`

## pseudocode

```c
LSTATUS __fastcall SetUEFICA2023Status(BYTE *lpData)
{
  LSTATUS result; // eax
  __int64 v3; // rax
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  SBServicingLogMessage(
    (wchar_t *)L"Setting reg:%ls to %ls",
    L"SYSTEM\\CurrentControlSet\\Control\\SecureBoot\\Servicing\\UEFICA2023Status",
    lpData);
  hKey = 0;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Control\\SecureBoot\\Servicing",
             0,
             0xF003Fu,
             &hKey);
  if ( !result )
  {
    v3 = -1;
    do
      ++v3;
    while ( *(_WORD *)&lpData[2 * v3] );
    RegSetValueExW(hKey, L"UEFICA2023Status", 0, 1u, lpData, 2 * v3 + 2);
    return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x180057ca0  mov     [rsp+arg_0], rbx
0x180057ca5  push    rdi
0x180057ca6  sub     rsp, 30h
0x180057caa  mov     rbx, rcx
0x180057cad  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Sec"...
0x180057cb4  mov     r8, rcx
0x180057cb7  lea     rcx, aSettingRegLsTo; "Setting reg:%ls to %ls"
0x180057cbe  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180057cc3  lea     rax, [rsp+38h+hKey]
0x180057cc8  xor     edi, edi
0x180057cca  mov     r9d, 0F003Fh; samDesired
0x180057cd0  mov     [rsp+38h+phkResult], rax; phkResult
0x180057cd5  xor     r8d, r8d; ulOptions
0x180057cd8  mov     [rsp+38h+hKey], rdi
0x180057cdd  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Control\\Sec"...
0x180057ce4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180057ceb  call    cs:__imp_RegOpenKeyExW
0x180057cf1  test    eax, eax
0x180057cf3  jnz     short loc_180057D38
0x180057cf5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180057cf9  inc     rax
0x180057cfc  cmp     [rbx+rax*2], di
0x180057d00  jnz     short loc_180057CF9
0x180057d02  mov     rcx, [rsp+38h+hKey]; hKey
0x180057d07  lea     eax, ds:2[rax*2]
0x180057d0e  mov     [rsp+38h+cbData], eax; cbData
0x180057d12  lea     rdx, aUefica2023stat; "UEFICA2023Status"
0x180057d19  mov     r9d, 1; dwType
0x180057d1f  mov     [rsp+38h+phkResult], rbx; lpData
0x180057d24  xor     r8d, r8d; Reserved
0x180057d27  call    cs:__imp_RegSetValueExW
0x180057d2d  mov     rcx, [rsp+38h+hKey]; hKey
0x180057d32  call    cs:__imp_RegCloseKey
0x180057d38  mov     rbx, [rsp+38h+arg_0]
0x180057d3d  add     rsp, 30h
0x180057d41  pop     rdi
0x180057d42  retn
```
