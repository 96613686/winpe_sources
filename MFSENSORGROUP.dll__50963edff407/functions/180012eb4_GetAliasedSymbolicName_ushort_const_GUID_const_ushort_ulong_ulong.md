# GetAliasedSymbolicName(ushort const *,_GUID const &,ushort *,ulong,ulong *)

- ea: `0x180012eb4`
- end: `0x180013083`
- name: `?GetAliasedSymbolicName@@YAJPEBGAEBU_GUID@@PEAGKPEAK@Z`
- size: `463`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pszDeviceInterface@<rcx>, const struct _GUID *@<rdx>, unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x180012d34`
- `0x18001968c`

## callees

- `0x180003ce4`
- `0x180005fa0`
- `0x18000d1f0`
- `0x180012eb4`
- `0x180015e80`
- `0x180044f30`
- `0x180045900`

## import_xrefs

- `CFGMGR32!CM_Get_Device_Interface_AliasW` at `0x180012f56`
- `CFGMGR32!CM_Get_Device_Interface_AliasW` at `0x180012f56`

## pseudocode

```c

```
