# CommonUtil::UtilWaitForServiceStatus(SC_HANDLE__ *,ulong,ulong,ulong,ulong,CommonUtil::IWaitForServiceCancellation const *)

- ea: `0x1800e1c74`
- end: `0x1800e1dd0`
- name: `?UtilWaitForServiceStatus@CommonUtil@@YAJPEAUSC_HANDLE__@@KKKKPEBUIWaitForServiceCancellation@1@@Z`
- size: `348`
- prototype: `__int64 __usercall@<rax>(SC_HANDLE hService@<rcx>, struct SC_HANDLE__ *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, unsigned int, const struct CommonUtil::IWaitForServiceCancellation *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004c0c0`

## callees

- `0x180004710`
- `0x18000d7fc`
- `0x1800e1b08`
- `0x1800e1c74`
- `0x1800e7010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1800e1ccd`
- `KERNEL32!GetTickCount` at `0x1800e1cd5`
- `KERNEL32!GetTickCount` at `0x1800e1ccd`
- `KERNEL32!GetTickCount` at `0x1800e1cd5`
- `KERNEL32!Sleep` at `0x1800e1d14`
- `KERNEL32!Sleep` at `0x1800e1d14`

## pseudocode

```c

```
