# EnterpriseWorkerThread::ProcessDownloadedRequest(void)

- ea: `0x1800177d0`
- end: `0x1800180f6`
- name: `?ProcessDownloadedRequest@EnterpriseWorkerThread@@AEAAJXZ`
- size: `2342`
- prototype: `__int64 __fastcall(EnterpriseWorkerThread *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800175bc`

## callees

- `0x1800069dc`
- `0x180006ac0`
- `0x1800072ac`
- `0x1800137c8`
- `0x1800166d8`
- `0x180016a80`
- `0x1800177d0`
- `0x180019384`
- `0x18001a320`
- `0x18001ac50`
- `0x18001af58`
- `0x18001b63c`
- `0x18001b69c`
- `0x18001c550`
- `0x18001c5fc`
- `0x18001c818`
- `0x18001cc00`
- `0x18002a10c`
- `0x18002a4b0`
- `0x18002c194`
- `0x18006c8c6`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800180be`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800180be`
- `OLEAUT32!__imp_SysFreeString` at `0x180017f63`
- `OLEAUT32!__imp_SysFreeString` at `0x180017f72`
- `OLEAUT32!__imp_SysFreeString` at `0x180017fbd`
- `OLEAUT32!__imp_SysFreeString` at `0x180017fcc`
- `OLEAUT32!__imp_SysFreeString` at `0x180017fdb`
- `OLEAUT32!__imp_SysFreeString` at `0x18001800e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001801d`
- `OLEAUT32!__imp_SysFreeString` at `0x180018033`
- `OLEAUT32!__imp_SysFreeString` at `0x180018044`
- `OLEAUT32!__imp_SysFreeString` at `0x18001805b`
- `OLEAUT32!__imp_SysFreeString` at `0x180018069`
- `OLEAUT32!__imp_SysFreeString` at `0x18001807d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001808b`
- `OLEAUT32!__imp_SysFreeString` at `0x180018099`
- `OLEAUT32!__imp_SysFreeString` at `0x180017f63`
- `OLEAUT32!__imp_SysFreeString` at `0x180017f72`
- `OLEAUT32!__imp_SysFreeString` at `0x180017fbd`
- `OLEAUT32!__imp_SysFreeString` at `0x180017fcc`
- `OLEAUT32!__imp_SysFreeString` at `0x180017fdb`
- `OLEAUT32!__imp_SysFreeString` at `0x18001800e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001801d`
- `OLEAUT32!__imp_SysFreeString` at `0x180018033`
- `OLEAUT32!__imp_SysFreeString` at `0x180018044`
- `OLEAUT32!__imp_SysFreeString` at `0x18001805b`
- `OLEAUT32!__imp_SysFreeString` at `0x180018069`
- `OLEAUT32!__imp_SysFreeString` at `0x18001807d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001808b`
- `OLEAUT32!__imp_SysFreeString` at `0x180018099`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800180a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800180a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017836`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017836`

## string_xrefs

- `0x180017c26`: `ProductId was already in progress -- cannot install another productId until this one has completed`
- `0x180017c5d`: `Not allowed to install the same productId while a previous installation of that same ProductId is still on-going (wait for it to finish or cancel it).`

## pseudocode

```c

```
