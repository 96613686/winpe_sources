# FastWppCleanup

- ea: `0x180007124`
- end: `0x180007174`
- name: `FastWppCleanup`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180006e74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000715f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000715f`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000712f`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000712f`

## pseudocode

```c
void FastWppCleanup()
{
  EventUnregister(FastWppRegHandle);
  FastWppRegHandle = 0;
  g_rgFastWppLevelEnabledFlags = 0;
  *(_OWORD *)byte_180012690 = 0;
  *(_OWORD *)byte_1800126A0 = 0;
  DeleteCriticalSection(&FastWppCallbackLock);
  FastWppInitState = 0;
}

```

## disassembly

```asm
0x180007124  sub     rsp, 28h
0x180007128  mov     rcx, cs:FastWppRegHandle; RegHandle
0x18000712f  call    cs:__imp_EventUnregister
0x180007135  xorps   xmm0, xmm0
0x180007138  mov     cs:FastWppRegHandle, 0
0x180007143  lea     rcx, FastWppCallbackLock; lpCriticalSection
0x18000714a  movups  cs:g_rgFastWppLevelEnabledFlags, xmm0
0x180007151  movups  xmmword ptr cs:byte_180012690, xmm0
0x180007158  movups  xmmword ptr cs:byte_1800126A0, xmm0
0x18000715f  call    cs:__imp_DeleteCriticalSection
0x180007165  mov     cs:FastWppInitState, 0
0x18000716f  add     rsp, 28h
0x180007173  retn
```
