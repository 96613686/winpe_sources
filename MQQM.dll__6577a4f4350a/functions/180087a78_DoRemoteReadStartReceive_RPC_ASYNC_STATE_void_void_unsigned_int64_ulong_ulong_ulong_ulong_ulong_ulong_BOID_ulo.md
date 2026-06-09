# DoRemoteReadStartReceive(_RPC_ASYNC_STATE *,void *,void *,unsigned __int64,ulong,ulong,ulong,ulong,ulong,ulong,BOID *,ulong *,unsigned __int64 *,ulong *,_SectionBuffer * *)

- ea: `0x180087a78`
- end: `0x180087fdd`
- name: `?DoRemoteReadStartReceive@@YAXPEAU_RPC_ASYNC_STATE@@PEAX1_KKKKKKKPEAUBOID@@PEAKPEA_K4PEAPEAU_SectionBuffer@@@Z`
- size: `1381`
- prototype: `void __usercall(struct _RPC_ASYNC_STATE *@<rcx>, void *@<rdx>, CRemoteReadCtx *this@<r8>, unsigned __int64@<r9>, char, char, char, char, char, char, struct BOID *, unsigned int *, unsigned __int64 *, unsigned int *, struct _SectionBuffer **)`
- caller_count: `4`
- callee_count: `20`
- tags: ``

## callers

- `0x1800060e0`
- `0x180006170`
- `0x18008af60`
- `0x18008b000`

## callees

- `0x180009924`
- `0x18000d1f0`
- `0x18000f35c`
- `0x18000f430`
- `0x1800129cc`
- `0x18004101c`
- `0x18004556c`
- `0x180085194`
- `0x1800852a4`
- `0x180086120`
- `0x180086b10`
- `0x180087a78`
- `0x18008810c`
- `0x1800885d4`
- `0x1800889b0`
- `0x180088f60`
- `0x180089288`
- `0x1800892e4`
- `0x18008b174`
- `0x18009bd1c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180087db7`
- `KERNEL32!LeaveCriticalSection` at `0x180087eb8`
- `KERNEL32!LeaveCriticalSection` at `0x180087f33`
- `KERNEL32!LeaveCriticalSection` at `0x180087f55`
- `KERNEL32!LeaveCriticalSection` at `0x180087db7`
- `KERNEL32!LeaveCriticalSection` at `0x180087eb8`
- `KERNEL32!LeaveCriticalSection` at `0x180087f33`
- `KERNEL32!LeaveCriticalSection` at `0x180087f55`

## string_xrefs

- `0x180087aa4`: `DoRemoteReadStartReceive`

## pseudocode

```c

```
