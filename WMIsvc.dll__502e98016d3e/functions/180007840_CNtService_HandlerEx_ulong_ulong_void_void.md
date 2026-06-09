# CNtService::_HandlerEx(ulong,ulong,void *,void *)

- ea: `0x180007840`
- end: `0x180007868`
- name: `?_HandlerEx@CNtService@@CAKKKPEAX0@Z`
- size: `40`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180020010`

## pseudocode

```c
__int64 __fastcall CNtService::_HandlerEx(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  return (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, LPVOID, LPVOID))(*(_QWORD *)lpContext + 64LL))(
           lpContext,
           dwControl,
           dwEventType,
           lpEventData,
           lpContext);
}

```

## disassembly

```asm
0x180007840  sub     rsp, 38h
0x180007844  mov     rax, [r9]
0x180007847  mov     r10, r9
0x18000784a  mov     [rsp+38h+var_18], r9
0x18000784f  mov     r9, r8
0x180007852  mov     r8d, edx
0x180007855  mov     edx, ecx
0x180007857  mov     rcx, r10
0x18000785a  mov     rax, [rax+40h]
0x18000785e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007863  add     rsp, 38h
0x180007867  retn
```
