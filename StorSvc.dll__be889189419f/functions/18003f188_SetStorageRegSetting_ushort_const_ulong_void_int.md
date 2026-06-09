# SetStorageRegSetting(ushort const *,ulong,void *,int)

- ea: `0x18003f188`
- end: `0x18003f2f3`
- name: `?SetStorageRegSetting@@YAJPEBGKPEAXH@Z`
- size: `363`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, DWORD cbData, BYTE *lpData, int)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180023bac`
- `0x18002535c`
- `0x180029aa8`
- `0x180037044`

## callees

- `0x18000d030`
- `0x18003f188`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18003f1f5`
- `ntdll!RtlGetPersistedStateLocation` at `0x18003f1f5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003f253`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003f253`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003f289`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003f289`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18003f2a8`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18003f2a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f2c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f2c4`

## string_xrefs

- `0x18003f1e2`: `StorageSenseParamsID`

## pseudocode

```c
__int64 __fastcall SetStorageRegSetting(LPCWSTR lpValueName, DWORD cbData, BYTE *lpData, int a4)
{
  int PersistedStateLocation; // eax
  signed int v9; // ebx
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  HKEY hKey; // [rsp+50h] [rbp-258h] BYREF
  int v15; // [rsp+58h] [rbp-250h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-248h] BYREF

  hKey = 0;
  v15 = 520;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"StorageSenseParamsID",
                             0,
                             L"Software\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters",
                             0,
                             SubKey,
                             520,
                             &v15);
  v9 = PersistedStateLocation;
  if ( PersistedStateLocation > 0 )
    v9 = (unsigned __int16)PersistedStateLocation | 0x80070000;
  if ( v9 >= 0 )
  {
    v10 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
    v9 = v10;
    if ( v10 > 0 )
      v9 = (unsigned __int16)v10 | 0x80070000;
    if ( v9 >= 0 )
    {
      v11 = RegSetValueExW(hKey, lpValueName, 0, 4 - (cbData != 4), lpData, cbData);
      v9 = v11;
      if ( v11 > 0 )
        v9 = (unsigned __int16)v11 | 0x80070000;
      if ( v9 >= 0 )
      {
        if ( a4 )
        {
          v12 = RegFlushKey(hKey);
          v9 = v12;
          if ( v12 > 0 )
            v9 = (unsigned __int16)v12 | 0x80070000;
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003f188  mov     [rsp+arg_18], rbx
0x18003f18d  push    rbp
0x18003f18e  push    rsi
0x18003f18f  push    rdi
0x18003f190  push    r12
0x18003f192  push    r14
0x18003f194  sub     rsp, 280h
0x18003f19b  mov     rax, cs:__security_cookie
0x18003f1a2  xor     rax, rsp
0x18003f1a5  mov     [rsp+2A8h+var_38], rax
0x18003f1ad  mov     rbp, rcx
0x18003f1b0  mov     [rsp+2A8h+hKey], 0
0x18003f1b9  mov     ecx, 208h
0x18003f1be  lea     rax, [rsp+2A8h+var_250]
0x18003f1c3  mov     [rsp+2A8h+lpSecurityAttributes], rax
0x18003f1c8  mov     esi, r9d
0x18003f1cb  mov     [rsp+2A8h+samDesired], ecx
0x18003f1cf  lea     rax, [rsp+2A8h+SubKey]
0x18003f1d4  mov     [rsp+2A8h+var_250], ecx
0x18003f1d8  mov     r14, r8
0x18003f1db  mov     edi, edx
0x18003f1dd  mov     qword ptr [rsp+2A8h+dwOptions], rax
0x18003f1e2  lea     rcx, aStoragesensepa; "StorageSenseParamsID"
0x18003f1e9  xor     r9d, r9d
0x18003f1ec  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003f1f3  xor     edx, edx
0x18003f1f5  call    cs:__imp_RtlGetPersistedStateLocation
0x18003f1fb  mov     ebx, eax
0x18003f1fd  mov     r12d, 80070000h
0x18003f203  test    eax, eax
0x18003f205  jle     short loc_18003F20D
0x18003f207  movzx   ebx, ax
0x18003f20a  or      ebx, r12d
0x18003f20d  test    ebx, ebx
0x18003f20f  js      loc_18003F2BA
0x18003f215  mov     [rsp+2A8h+lpdwDisposition], 0; lpdwDisposition
0x18003f21e  lea     rax, [rsp+2A8h+hKey]
0x18003f223  mov     [rsp+2A8h+phkResult], rax; phkResult
0x18003f228  lea     rdx, [rsp+2A8h+SubKey]; lpSubKey
0x18003f22d  mov     [rsp+2A8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003f236  xor     r9d, r9d; lpClass
0x18003f239  mov     [rsp+2A8h+samDesired], 20006h; samDesired
0x18003f241  xor     r8d, r8d; Reserved
0x18003f244  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003f24b  mov     [rsp+2A8h+dwOptions], 0; dwOptions
0x18003f253  call    cs:__imp_RegCreateKeyExW
0x18003f259  mov     ebx, eax
0x18003f25b  test    eax, eax
0x18003f25d  jle     short loc_18003F265
0x18003f25f  movzx   ebx, ax
0x18003f262  or      ebx, r12d
0x18003f265  test    ebx, ebx
0x18003f267  js      short loc_18003F2BA
0x18003f269  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18003f26e  lea     eax, [rdi-4]
0x18003f271  neg     eax
0x18003f273  mov     [rsp+2A8h+samDesired], edi; cbData
0x18003f277  mov     rdx, rbp; lpValueName
0x18003f27a  mov     qword ptr [rsp+2A8h+dwOptions], r14; lpData
0x18003f27f  sbb     r9d, r9d
0x18003f282  xor     r8d, r8d; Reserved
0x18003f285  add     r9d, 4; dwType
0x18003f289  call    cs:__imp_RegSetValueExW
0x18003f28f  mov     ebx, eax
0x18003f291  test    eax, eax
0x18003f293  jle     short loc_18003F29B
0x18003f295  movzx   ebx, ax
0x18003f298  or      ebx, r12d
0x18003f29b  test    ebx, ebx
0x18003f29d  js      short loc_18003F2BA
0x18003f29f  test    esi, esi
0x18003f2a1  jz      short loc_18003F2BA
0x18003f2a3  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18003f2a8  call    cs:__imp_RegFlushKey
0x18003f2ae  mov     ebx, eax
0x18003f2b0  test    eax, eax
0x18003f2b2  jle     short loc_18003F2BA
0x18003f2b4  movzx   ebx, ax
0x18003f2b7  or      ebx, r12d
0x18003f2ba  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18003f2bf  test    rcx, rcx
0x18003f2c2  jz      short loc_18003F2CA
0x18003f2c4  call    cs:__imp_RegCloseKey
0x18003f2ca  mov     eax, ebx
0x18003f2cc  mov     rcx, [rsp+2A8h+var_38]
0x18003f2d4  xor     rcx, rsp; StackCookie
0x18003f2d7  call    __security_check_cookie
0x18003f2dc  mov     rbx, [rsp+2A8h+arg_18]
0x18003f2e4  add     rsp, 280h
0x18003f2eb  pop     r14
0x18003f2ed  pop     r12
0x18003f2ef  pop     rdi
0x18003f2f0  pop     rsi
0x18003f2f1  pop     rbp
0x18003f2f2  retn
```
