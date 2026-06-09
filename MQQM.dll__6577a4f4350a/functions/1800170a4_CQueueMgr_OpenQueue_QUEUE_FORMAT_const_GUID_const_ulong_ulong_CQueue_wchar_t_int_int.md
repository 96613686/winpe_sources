# CQueueMgr::OpenQueue(QUEUE_FORMAT const *,_GUID const &,ulong,ulong,CQueue * *,wchar_t * *,int *,int)

- ea: `0x1800170a4`
- end: `0x1800177be`
- name: `?OpenQueue@CQueueMgr@@QEAAJPEBUQUEUE_FORMAT@@AEBU_GUID@@KKPEAPEAVCQueue@@PEAPEA_WPEAHH@Z`
- size: `1818`
- prototype: `int(CQueueMgr *__hidden this, const struct QUEUE_FORMAT *, const struct _GUID *, unsigned int, unsigned int, struct CQueue **, wchar_t **, int *, int)`
- caller_count: `4`
- callee_count: `19`
- tags: `loader_planting`

## callers

- `0x180016c4c`
- `0x180016e00`
- `0x180036298`
- `0x18004d78c`

## callees

- `0x18000bab8`
- `0x18000f35c`
- `0x18000f430`
- `0x180011578`
- `0x180013304`
- `0x180013efc`
- `0x180016590`
- `0x1800165b8`
- `0x1800166ac`
- `0x1800170a4`
- `0x180018d2c`
- `0x180019364`
- `0x18002c61c`
- `0x180048b40`
- `0x18004d0cc`
- `0x18009bd1c`
- `0x1800ac430`
- `0x1800c6254`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!free` at `0x18001715f`
- `msvcrt!free` at `0x1800171fc`
- `msvcrt!free` at `0x18001726e`
- `msvcrt!free` at `0x18001734d`
- `msvcrt!free` at `0x180017374`
- `msvcrt!free` at `0x180017402`
- `msvcrt!free` at `0x180017479`
- `msvcrt!free` at `0x1800174e8`
- `msvcrt!free` at `0x18001754d`
- `msvcrt!free` at `0x180017561`
- `msvcrt!free` at `0x1800175fb`
- `msvcrt!free` at `0x180017623`
- `msvcrt!free` at `0x1800177b2`
- `msvcrt!free` at `0x18001715f`
- `msvcrt!free` at `0x1800171fc`
- `msvcrt!free` at `0x18001726e`
- `msvcrt!free` at `0x18001734d`
- `msvcrt!free` at `0x180017374`
- `msvcrt!free` at `0x180017402`
- `msvcrt!free` at `0x180017479`
- `msvcrt!free` at `0x1800174e8`
- `msvcrt!free` at `0x18001754d`
- `msvcrt!free` at `0x180017561`
- `msvcrt!free` at `0x1800175fb`
- `msvcrt!free` at `0x180017623`
- `msvcrt!free` at `0x1800177b2`
- `ntdll!NtDeviceIoControlFile` at `0x1800175d7`
- `ntdll!NtDeviceIoControlFile` at `0x1800176b9`
- `ntdll!NtDeviceIoControlFile` at `0x18001773c`
- `ntdll!NtDeviceIoControlFile` at `0x1800175d7`
- `ntdll!NtDeviceIoControlFile` at `0x1800176b9`
- `ntdll!NtDeviceIoControlFile` at `0x18001773c`
- `USER32!CharLowerW` at `0x180017570`
- `USER32!CharLowerW` at `0x180017570`

## pseudocode

```c

```
