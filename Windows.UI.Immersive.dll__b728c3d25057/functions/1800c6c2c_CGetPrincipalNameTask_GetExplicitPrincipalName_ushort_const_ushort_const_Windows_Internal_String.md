# CGetPrincipalNameTask::_GetExplicitPrincipalName(ushort const *,ushort const *,Windows::Internal::String &)

- ea: `0x1800c6c2c`
- end: `0x1800c6d1c`
- name: `?_GetExplicitPrincipalName@CGetPrincipalNameTask@@AEAAJPEBG0AEAVString@Internal@Windows@@@Z`
- size: `240`
- prototype: `int(CGetPrincipalNameTask *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct Windows::Internal::String *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c7248`

## callees

- `0x18006b560`
- `0x1800c6c2c`

## import_xrefs

- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x1800c6cfe`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x1800c6cfe`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x1800c6d09`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x1800c6d09`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x1800c6ca7`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x1800c6ca7`
- `NTDSAPI!DsBindW` at `0x1800c6c54`
- `NTDSAPI!DsBindW` at `0x1800c6c54`

## pseudocode

```c

```
