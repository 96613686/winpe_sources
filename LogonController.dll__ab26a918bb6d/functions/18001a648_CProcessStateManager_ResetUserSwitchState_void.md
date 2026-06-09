# CProcessStateManager::_ResetUserSwitchState(void)

- ea: `0x18001a648`
- end: `0x18001a779`
- name: `?_ResetUserSwitchState@CProcessStateManager@@AEAAXXZ`
- size: `305`
- prototype: `void __fastcall(CProcessStateManager *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001aad0`
- `0x18001ac90`
- `0x18004e9b0`

## callees

- `0x18001a648`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a6de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a76d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a6de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a76d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001a6ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001a75d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001a6ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001a75d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a69b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a731`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a69b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a731`

## string_xrefs

- `0x18001a6b9`: `UserSID`

## pseudocode

```c
void __fastcall CProcessStateManager::_ResetUserSwitchState(CProcessStateManager *this)
{
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  if ( !RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\UserSwitch",
          0,
          0,
          0,
          2u,
          0,
          &hKey,
          0) )
  {
    RegSetValueExW(hKey, L"UserSID", 0, 1u, (const BYTE *)&sourceString, 2u);
    if ( hKey != HKEY_LOCAL_MACHINE )
      RegCloseKey(hKey);
  }
  LODWORD(hKey) = 0;
  phkResult = 0;
  if ( !RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\UserSwitch",
          0,
          0,
          0,
          2u,
          0,
          &phkResult,
          0) )
  {
    RegSetValueExW(phkResult, L"Enabled", 0, 4u, (const BYTE *)&hKey, 4u);
    if ( phkResult != HKEY_LOCAL_MACHINE )
      RegCloseKey(phkResult);
  }
}

```

## disassembly

```asm
0x18001a648  mov     r11, rsp
0x18001a64b  mov     [r11+8], rcx
0x18001a64f  push    rdi
0x18001a650  sub     rsp, 50h
0x18001a654  mov     qword ptr [r11-18h], 0
0x18001a65c  lea     rax, [r11+8]
0x18001a660  mov     [r11-20h], rax
0x18001a664  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001a66b  mov     qword ptr [r11-28h], 0
0x18001a673  mov     rdi, 0FFFFFFFF80000002h
0x18001a67a  mov     [rsp+58h+samDesired], 2; samDesired
0x18001a682  xor     r9d, r9d; lpClass
0x18001a685  xor     r8d, r8d; Reserved
0x18001a688  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18001a690  mov     rcx, rdi; hKey
0x18001a693  mov     qword ptr [r11+8], 0
0x18001a69b  call    cs:__imp_RegCreateKeyExW
0x18001a6a1  test    eax, eax
0x18001a6a3  jnz     short loc_18001A6E4
0x18001a6a5  mov     rcx, [rsp+58h+hKey]; hKey
0x18001a6aa  lea     rax, sourceString
0x18001a6b1  mov     [rsp+58h+samDesired], 2; cbData
0x18001a6b9  lea     rdx, aUsersid; "UserSID"
0x18001a6c0  mov     r9d, 1; dwType
0x18001a6c6  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18001a6cb  xor     r8d, r8d; Reserved
0x18001a6ce  call    cs:__imp_RegSetValueExW
0x18001a6d4  mov     rcx, [rsp+58h+hKey]; hKey
0x18001a6d9  cmp     rcx, rdi
0x18001a6dc  jz      short loc_18001A6E4
0x18001a6de  call    cs:__imp_RegCloseKey
0x18001a6e4  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18001a6ed  lea     rax, [rsp+58h+arg_8]
0x18001a6f2  mov     [rsp+58h+phkResult], rax; phkResult
0x18001a6f7  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001a6fe  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001a707  xor     r9d, r9d; lpClass
0x18001a70a  mov     [rsp+58h+samDesired], 2; samDesired
0x18001a712  xor     r8d, r8d; Reserved
0x18001a715  mov     rcx, rdi; hKey
0x18001a718  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18001a720  mov     dword ptr [rsp+58h+hKey], 0
0x18001a728  mov     [rsp+58h+arg_8], 0
0x18001a731  call    cs:__imp_RegCreateKeyExW
0x18001a737  test    eax, eax
0x18001a739  jnz     short loc_18001A773
0x18001a73b  mov     rcx, [rsp+58h+arg_8]; hKey
0x18001a740  lea     r9d, [rax+4]; dwType
0x18001a744  lea     rax, [rsp+58h+hKey]
0x18001a749  mov     [rsp+58h+samDesired], r9d; cbData
0x18001a74e  xor     r8d, r8d; Reserved
0x18001a751  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18001a756  lea     rdx, aEnabled; "Enabled"
0x18001a75d  call    cs:__imp_RegSetValueExW
0x18001a763  mov     rcx, [rsp+58h+arg_8]; hKey
0x18001a768  cmp     rcx, rdi
0x18001a76b  jz      short loc_18001A773
0x18001a76d  call    cs:__imp_RegCloseKey
0x18001a773  add     rsp, 50h
0x18001a777  pop     rdi
0x18001a778  retn
```
