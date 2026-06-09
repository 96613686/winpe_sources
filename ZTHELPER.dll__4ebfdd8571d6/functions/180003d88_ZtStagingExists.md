# ZtStagingExists

- ea: `0x180003d88`
- end: `0x180003df9`
- name: `ZtStagingExists`
- size: `113`
- prototype: `_BOOL8 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18000376c`

## callees

- `0x180003d88`
- `0x18000f670`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003deb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003deb`

## string_xrefs

- `0x180003da0`: `Parameters\ZTDNS\ZTStagingConfig`
- `0x180003daf`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x180003dbe`: `Dnscache`

## pseudocode

```c
_BOOL8 __fastcall ZtStagingExists(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  BOOL v4; // ebx
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF

  hKey = 0;
  v4 = CreatePersistedRegistryKeyHelper(
         (__int64)L"Dnscache",
         (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
         (__int64)L"Parameters\\ZTDNS\\ZTStagingConfig",
         a4,
         0x20019u,
         0,
         0,
         &hKey) == 0;
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x180003d88  mov     r11, rsp
0x180003d8b  push    rbx
0x180003d8c  sub     rsp, 40h
0x180003d90  lea     rax, [r11+8]
0x180003d94  mov     qword ptr [r11+8], 0
0x180003d9c  mov     [r11-10h], rax
0x180003da0  lea     r8, aParametersZtdn_0; "Parameters\\ZTDNS\\ZTStagingConfig"
0x180003da7  mov     [rsp+48h+var_18], 0
0x180003daf  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x180003db6  mov     qword ptr [r11-20h], 0
0x180003dbe  lea     rcx, aDnscache; "Dnscache"
0x180003dc5  mov     [rsp+48h+var_28], 20019h
0x180003dcd  call    CreatePersistedRegistryKeyHelper
0x180003dd2  xor     ebx, ebx
0x180003dd4  cmp     eax, 2
0x180003dd7  jz      short loc_180003DE1
0x180003dd9  test    eax, eax
0x180003ddb  lea     ecx, [rbx+1]
0x180003dde  cmovz   ebx, ecx
0x180003de1  mov     rcx, [rsp+48h+hKey]; hKey
0x180003de6  test    rcx, rcx
0x180003de9  jz      short loc_180003DF1
0x180003deb  call    cs:__imp_RegCloseKey
0x180003df1  mov     eax, ebx
0x180003df3  add     rsp, 40h
0x180003df7  pop     rbx
0x180003df8  retn
```
