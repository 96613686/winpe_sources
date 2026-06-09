# ProvIsStateSeparationEnabled(void)

- ea: `0x180026084`
- end: `0x1800260e7`
- name: `?ProvIsStateSeparationEnabled@@YA_NXZ`
- size: `99`
- prototype: `bool(void)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028298`
- `0x180028974`
- `0x180028a38`
- `0x180029a78`

## callees

- `0x180026084`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800260bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800260bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800260cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800260cf`

## pseudocode

```c
char ProvIsStateSeparationEnabled(void)
{
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  if ( !`ProvIsStateSeparationEnabled'::`2'::s_HasRun )
  {
    hKey = 0;
    `ProvIsStateSeparationEnabled'::`2'::s_Redirection = RegOpenKeyExW(
                                                           HKEY_LOCAL_MACHINE,
                                                           L"Software\\Microsoft\\Provisioning\\StateSeparationMode",
                                                           0,
                                                           0x20119u,
                                                           &hKey) == 0;
    RegCloseKey(hKey);
    `ProvIsStateSeparationEnabled'::`2'::s_HasRun = 1;
  }
  return `ProvIsStateSeparationEnabled'::`2'::s_Redirection;
}

```

## disassembly

```asm
0x180026084  sub     rsp, 38h
0x180026088  cmp     cs:?s_HasRun@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x18002608f  jnz     short loc_1800260DC
0x180026091  lea     rax, [rsp+38h+hKey]
0x180026096  mov     [rsp+38h+hKey], 0
0x18002609f  mov     r9d, 20119h; samDesired
0x1800260a5  mov     [rsp+38h+phkResult], rax; phkResult
0x1800260aa  xor     r8d, r8d; ulOptions
0x1800260ad  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Provisioning\\Stat"...
0x1800260b4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800260bb  call    cs:__imp_RegOpenKeyExW
0x1800260c1  mov     rcx, [rsp+38h+hKey]; hKey
0x1800260c6  test    eax, eax
0x1800260c8  setz    cs:?s_Redirection@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x1800260cf  call    cs:__imp_RegCloseKey
0x1800260d5  mov     cs:?s_HasRun@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x1800260dc  mov     al, cs:?s_Redirection@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x1800260e2  add     rsp, 38h
0x1800260e6  retn
```
