# CTipPull::Pull(CTmProxyCore *,char *,ITipPullSink *,_GUID *)

- ea: `0x180040804`
- end: `0x180040a97`
- name: `?Pull@CTipPull@@QEAAJPEAVCTmProxyCore@@PEADPEAUITipPullSink@@PEAU_GUID@@@Z`
- size: `659`
- prototype: `__int64 __usercall@<rax>(CTipPull *__hidden this@<rcx>, struct CTmProxyCore *@<rdx>, char *@<r8>, struct ITipPullSink *@<r9>, struct _GUID *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800298d0`
- `0x180040670`

## callees

- `0x180019908`
- `0x18001d178`
- `0x180040804`
- `0x180040fc0`
- `0x1800410b8`
- `0x18007ccf4`
- `0x18007f7d8`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180040a24`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180040a24`
- `RPCRT4!UuidFromStringA` at `0x1800408cf`
- `RPCRT4!UuidFromStringA` at `0x1800408cf`
- `msvcrt!_strnicmp` at `0x1800408be`
- `msvcrt!_strnicmp` at `0x1800408be`

## string_xrefs

- `0x1800408e9`: `com\complus\dtc\dtc\msdtcprx\src\tiphelper.cpp`

## pseudocode

```c

```
