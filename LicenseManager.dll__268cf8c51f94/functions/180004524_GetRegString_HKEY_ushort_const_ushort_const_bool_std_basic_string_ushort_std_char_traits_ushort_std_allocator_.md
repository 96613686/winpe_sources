# GetRegString(HKEY__ *,ushort const *,ushort const *,bool &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180004524`
- end: `0x18000463e`
- name: `?GetRegString@@YA_NPEAUHKEY__@@PEBG1AEA_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `282`
- prototype: `__int64 __usercall@<rax>(HKEY hkey@<rcx>, LPCWSTR lpSubKey@<rdx>, LPCWSTR lpValue@<r8>, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005914`

## callees

- `0x180004524`
- `0x1800178e0`
- `0x180090f34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004563`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800045cb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004563`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800045cb`

## string_xrefs

- `0x1800045da`: `onecoreuap\enduser\winstore\licensemanager\lib\registry.cpp`

## pseudocode

```c

```
