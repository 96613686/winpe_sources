# GetPolicyInt(ushort const *,ushort const *,int *)

- ea: `0x180026bb8`
- end: `0x180026c44`
- name: `?GetPolicyInt@@YA_NPEBG0PEAH@Z`
- size: `140`
- prototype: `bool __fastcall(const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180020990`
- `0x1800211d8`
- `0x180026c4c`

## callees

- `0x180004928`
- `0x180012118`
- `0x180026bb8`

## import_xrefs

- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x180026be2`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x180026be2`

## string_xrefs

- `0x180026bf8`: `Failed to read MDM policy on this device: PolicyManager_GetPolicyIntPresent API not present.`
- `0x180026c1a`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`

## pseudocode

```c

```
