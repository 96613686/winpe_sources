# CIsapiReqInfo::SendClientResponse(int,_HSE_SEND_ENTIRE_RESPONSE_INFO *,WSABUF_VECTORS *,void (*)(void *),void *)

- ea: `0x180017fc0`
- end: `0x1800183e6`
- name: `?SendClientResponse@CIsapiReqInfo@@QEAAHHPEAU_HSE_SEND_ENTIRE_RESPONSE_INFO@@PEAUWSABUF_VECTORS@@P6AXPEAX@Z2@Z`
- size: `1062`
- prototype: `__int64 __usercall@<rax>(CIsapiReqInfo *__hidden this@<rcx>, int@<edx>, struct _HSE_SEND_ENTIRE_RESPONSE_INFO *@<r8>, struct WSABUF_VECTORS *@<r9>, void (*)(void *), void *)`
- caller_count: `4`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180017ac0`
- `0x180052ab0`
- `0x180052cb0`
- `0x18005316c`

## callees

- `0x18000f724`
- `0x180016a48`
- `0x180017fc0`
- `0x180023d86`
- `0x180023dd0`
- `0x180048a38`
- `0x180048b34`
- `0x180048d64`
- `0x1800494b8`
- `0x180049514`
- `0x180064010`

## import_xrefs

- `msvcrt!_stricmp` at `0x180018131`
- `msvcrt!_stricmp` at `0x18002e4f8`
- `msvcrt!_stricmp` at `0x180018131`
- `msvcrt!_stricmp` at `0x18002e4f8`
- `msvcrt!isdigit` at `0x18002e426`
- `msvcrt!isdigit` at `0x18002e434`
- `msvcrt!isdigit` at `0x18002e426`
- `msvcrt!isdigit` at `0x18002e434`
- `KERNEL32!HeapFree` at `0x180018365`
- `KERNEL32!HeapFree` at `0x18001837d`
- `KERNEL32!HeapFree` at `0x18002e989`
- `KERNEL32!HeapFree` at `0x180018365`
- `KERNEL32!HeapFree` at `0x18001837d`
- `KERNEL32!HeapFree` at `0x18002e989`
- `KERNEL32!HeapAlloc` at `0x18002e7f9`
- `KERNEL32!HeapAlloc` at `0x18002e7f9`
- `KERNEL32!SetLastError` at `0x18002e3b6`
- `KERNEL32!SetLastError` at `0x18002e495`
- `KERNEL32!SetLastError` at `0x18002e812`
- `KERNEL32!SetLastError` at `0x18002e3b6`
- `KERNEL32!SetLastError` at `0x18002e495`
- `KERNEL32!SetLastError` at `0x18002e812`
- `KERNEL32!GetLastError` at `0x18002e46e`
- `KERNEL32!GetLastError` at `0x18002e923`
- `KERNEL32!GetLastError` at `0x18002e946`
- `KERNEL32!GetLastError` at `0x18002e46e`
- `KERNEL32!GetLastError` at `0x18002e923`
- `KERNEL32!GetLastError` at `0x18002e946`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x1800180ba`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18002e3d1`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x1800180ba`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18002e3d1`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800180c5`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800180c5`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002e486`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002e486`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800180df`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180018121`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002e403`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002e4b1`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002e4e8`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800180df`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180018121`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002e403`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002e4b1`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002e4e8`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001814b`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002e457`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001814b`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002e457`

## string_xrefs

- `0x18002e3e3`: `SERVER_PROTOCOL`

## pseudocode

```c

```
