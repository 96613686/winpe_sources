# WaasMedic::TasksHelper::SetTaskFolderSecurityDescriptor(ushort const *)

- ea: `0x180032f6c`
- end: `0x180033006`
- name: `?SetTaskFolderSecurityDescriptor@TasksHelper@WaasMedic@@QEAAJPEBG@Z`
- size: `154`
- prototype: `int(WaasMedic::TasksHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18001fe68`
- `0x180067020`

## callees

- `0x18000bbd4`
- `0x18002e81c`
- `0x180032f6c`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180032f88`
- `OLEAUT32!__imp_SysAllocString` at `0x180032f88`
- `OLEAUT32!__imp_SysFreeString` at `0x180032ff3`
- `OLEAUT32!__imp_SysFreeString` at `0x180032ff3`

## string_xrefs

- `0x180032fa9`: `onecore\enduser\waasmedic\lib\util\taskshelper.cpp`
- `0x180032fde`: `Failed to set task folder security descriptor. hr = 0x%08x`

## pseudocode

```c

```
