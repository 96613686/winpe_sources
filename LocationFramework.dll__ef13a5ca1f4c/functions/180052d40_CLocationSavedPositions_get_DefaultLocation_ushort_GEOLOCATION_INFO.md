# CLocationSavedPositions::get_DefaultLocation(ushort *,GEOLOCATION_INFO *)

- ea: `0x180052d40`
- end: `0x180052fb4`
- name: `?get_DefaultLocation@CLocationSavedPositions@@UEAAJPEAGPEAUGEOLOCATION_INFO@@@Z`
- size: `628`
- prototype: `int(CLocationSavedPositions *__hidden this, unsigned __int16 *, struct GEOLOCATION_INFO *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x18001be08`
- `0x1800498bc`
- `0x180052d40`
- `0x18005c0c4`
- `0x1800a32fc`
- `0x1800d85f0`
- `0x1800d8780`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052eb6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052eb6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052d7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052d7d`
- `OLEAUT32!__imp_SysFreeString` at `0x180052d96`
- `OLEAUT32!__imp_SysFreeString` at `0x180052eac`
- `OLEAUT32!__imp_SysFreeString` at `0x180052fa8`
- `OLEAUT32!__imp_SysFreeString` at `0x180052d96`
- `OLEAUT32!__imp_SysFreeString` at `0x180052eac`
- `OLEAUT32!__imp_SysFreeString` at `0x180052fa8`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180052d9f`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180052d9f`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180052daa`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180052daa`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180052e1c`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180052e51`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180052e1c`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180052e51`

## string_xrefs

- `0x180052dd2`: `userSidStr.AssignBSTR(UserSid)`
- `0x180052f3a`: `SetDefaultLocation(UserSid, *pDefaultLocation, true)`

## pseudocode

```c

```
