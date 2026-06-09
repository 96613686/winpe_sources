# CleanupBufferedAsyncEprRequest

- ea: `0x180006c40`
- end: `0x180006cdb`
- name: `CleanupBufferedAsyncEprRequest`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004f94`
- `0x180006c40`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x180006c5b`
- `RPCRT4!UuidToStringW` at `0x180006c5b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180006c96`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180006c96`
- `RPCRT4!RpcStringFreeW` at `0x180006c8b`
- `RPCRT4!RpcStringFreeW` at `0x180006c8b`
- `RPCRT4!I_RpcFree` at `0x180006ca5`
- `RPCRT4!I_RpcFree` at `0x180006ca5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006cbd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ccf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006cbd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ccf`

## pseudocode

```c
BOOL __fastcall CleanupBufferedAsyncEprRequest(__int64 a1, __int64 a2)
{
  __int64 v3; // r8
  void *v4; // rcx
  void *v5; // r8
  RPC_WSTR StringUuid; // [rsp+38h] [rbp+10h] BYREF

  StringUuid = 0;
  if ( !UuidToStringW((const UUID *)(a2 + 8), &StringUuid) )
  {
    if ( (Microsoft_Windows_ServiceTriggerPerfEventProviderEnableBits & 1) != 0 )
      McTemplateU0zz_EtwEventWriteTransfer(
        &SERVICE_TRIGGER_PERF_EVENT_GUID_Context,
        &ServiceTriggerPerfServiceTimedOut,
        v3,
        StringUuid);
    RpcStringFreeW(&StringUuid);
  }
  RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)a2, 0);
  v4 = *(void **)(a2 + 64);
  if ( v4 )
    I_RpcFree(v4);
  v5 = *(void **)(a2 + 48);
  if ( v5 )
    HeapFree(hEpMapperHeap, 0, v5);
  return HeapFree(hEpMapperHeap, 0, (LPVOID)a2);
}

```

## disassembly

```asm
0x180006c40  push    rbx
0x180006c42  sub     rsp, 20h
0x180006c46  mov     rbx, rdx
0x180006c49  mov     [rsp+28h+StringUuid], 0
0x180006c52  lea     rcx, [rdx+8]; Uuid
0x180006c56  lea     rdx, [rsp+28h+StringUuid]; StringUuid
0x180006c5b  call    cs:__imp_UuidToStringW
0x180006c61  test    eax, eax
0x180006c63  jnz     short loc_180006C91
0x180006c65  test    cs:Microsoft_Windows_ServiceTriggerPerfEventProviderEnableBits, 1
0x180006c6c  jz      short loc_180006C86
0x180006c6e  mov     r9, [rsp+28h+StringUuid]
0x180006c73  lea     rdx, ServiceTriggerPerfServiceTimedOut
0x180006c7a  lea     rcx, SERVICE_TRIGGER_PERF_EVENT_GUID_Context
0x180006c81  call    McTemplateU0zz_EtwEventWriteTransfer
0x180006c86  lea     rcx, [rsp+28h+StringUuid]; String
0x180006c8b  call    cs:__imp_RpcStringFreeW
0x180006c91  mov     rcx, [rbx]; pAsync
0x180006c94  xor     edx, edx; Reply
0x180006c96  call    cs:__imp_RpcAsyncCompleteCall
0x180006c9c  mov     rcx, [rbx+40h]; Object
0x180006ca0  test    rcx, rcx
0x180006ca3  jz      short loc_180006CAB
0x180006ca5  call    cs:__imp_I_RpcFree
0x180006cab  mov     r8, [rbx+30h]; lpMem
0x180006caf  test    r8, r8
0x180006cb2  jz      short loc_180006CC3
0x180006cb4  mov     rcx, cs:hEpMapperHeap; hHeap
0x180006cbb  xor     edx, edx; dwFlags
0x180006cbd  call    cs:__imp_HeapFree
0x180006cc3  mov     rcx, cs:hEpMapperHeap; hHeap
0x180006cca  mov     r8, rbx; lpMem
0x180006ccd  xor     edx, edx; dwFlags
0x180006ccf  call    cs:__imp_HeapFree
0x180006cd5  add     rsp, 20h
0x180006cd9  pop     rbx
0x180006cda  retn
```
