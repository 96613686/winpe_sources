# _GetSoundAlias(ushort const *,ushort *,unsigned __int64,ulong &,int,HKEY__ *,ushort const *)

- ea: `0x180059730`
- end: `0x18005997e`
- name: `?_GetSoundAlias@@YAHPEBGPEAG_KAEAKHPEAUHKEY__@@0@Z`
- size: `590`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, unsigned __int64@<r8>, unsigned int *@<r9>, int, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180081b80`

## callees

- `0x18000b860`
- `0x180059730`
- `0x180059984`
- `0x1800cf8c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800597f4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180059938`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800597f4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180059938`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180059908`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180059908`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005994c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005994c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18005980a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18005980a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800597ac`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800597ac`

## pseudocode

```c

```
