# CLoggingMgrImpl::LogScpRegistrationFailed(ushort const *,ushort const *,_FILETIME,long)

- ea: `0x18012a3f0`
- end: `0x18012a789`
- name: `?LogScpRegistrationFailed@CLoggingMgrImpl@@UEAAJPEBG0U_FILETIME@@J@Z`
- size: `921`
- prototype: `__int64 __usercall@<rax>(CLoggingMgrImpl *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, struct _FILETIME@<r9>, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting`

## callees

- `0x1800024f0`
- `0x180003498`
- `0x180004374`
- `0x180004510`
- `0x180004874`
- `0x180008290`
- `0x1800083bc`
- `0x18001fc30`
- `0x18012637c`
- `0x18012647c`
- `0x180126710`
- `0x18012a3f0`
- `0x18012b4d0`
- `0x1801448c0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18012a66f`
- `ntdll!EtwEventWrite` at `0x18012a66f`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18012a5ab`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18012a5ab`

## pseudocode

```c

```
