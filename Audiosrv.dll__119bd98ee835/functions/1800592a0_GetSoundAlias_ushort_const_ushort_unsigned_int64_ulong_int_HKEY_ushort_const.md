# _GetSoundAlias(ushort const *,ushort *,unsigned __int64,ulong &,int,HKEY__ *,ushort const *)

- ea: `0x1800592a0`
- end: `0x1800594ee`
- name: `?_GetSoundAlias@@YAHPEBGPEAG_KAEAKHPEAUHKEY__@@0@Z`
- size: `590`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, unsigned __int64@<r8>, unsigned int *@<r9>, int, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180081680`

## callees

- `0x18000b9b0`
- `0x1800592a0`
- `0x1800594f4`
- `0x1800cd8d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180059364`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800594a8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180059364`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800594a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180059478`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180059478`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800594bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800594bc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18005937a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18005937a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18005931c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18005931c`

## pseudocode

```c

```
