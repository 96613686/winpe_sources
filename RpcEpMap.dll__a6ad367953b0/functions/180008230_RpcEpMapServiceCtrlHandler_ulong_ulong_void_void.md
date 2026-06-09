# RpcEpMapServiceCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x180008230`
- end: `0x180008233`
- name: `?RpcEpMapServiceCtrlHandler@@YAKKKPEAX0@Z`
- size: `3`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task`

## pseudocode

```c
__int64 __fastcall RpcEpMapServiceCtrlHandler(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  return 0;
}

```

## disassembly

```asm
0x180008230  xor     eax, eax
0x180008232  retn
```
