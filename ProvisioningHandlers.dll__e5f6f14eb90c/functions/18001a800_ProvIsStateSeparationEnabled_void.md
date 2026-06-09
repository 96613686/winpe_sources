# ProvIsStateSeparationEnabled(void)

- ea: `0x18001a800`
- end: `0x18001a870`
- name: `?ProvIsStateSeparationEnabled@@YA_NXZ`
- size: `112`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fb6c`
- `0x18001c890`

## callees

- `0x18001a800`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a837`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a837`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a851`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a851`

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
0x18001a800  sub     rsp, 38h
0x18001a804  cmp     cs:?s_HasRun@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x18001a80b  jnz     short loc_18001A864
0x18001a80d  lea     rax, [rsp+38h+hKey]
0x18001a812  mov     [rsp+38h+hKey], 0
0x18001a81b  mov     r9d, 20119h; samDesired
0x18001a821  mov     [rsp+38h+phkResult], rax; phkResult
0x18001a826  xor     r8d, r8d; ulOptions
0x18001a829  lea     rdx, SubKey; "Software\\Microsoft\\Provisioning\\Stat"...
0x18001a830  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a837  call    cs:__imp_RegOpenKeyExW
0x18001a83e  nop     dword ptr [rax+rax+00h]
0x18001a843  mov     rcx, [rsp+38h+hKey]; hKey
0x18001a848  test    eax, eax
0x18001a84a  setz    cs:?s_Redirection@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x18001a851  call    cs:__imp_RegCloseKey
0x18001a858  nop     dword ptr [rax+rax+00h]
0x18001a85d  mov     cs:?s_HasRun@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x18001a864  mov     al, cs:?s_Redirection@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x18001a86a  add     rsp, 38h
0x18001a86e  retn
```
