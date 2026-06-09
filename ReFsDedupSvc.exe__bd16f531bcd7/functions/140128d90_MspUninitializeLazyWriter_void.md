# MspUninitializeLazyWriter(void)

- ea: `0x140128d90`
- end: `0x140128e7b`
- name: `?MspUninitializeLazyWriter@@YAXXZ`
- size: `235`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140088170`

## callees

- `0x140082fe4`
- `0x140086d78`
- `0x1400ab1fc`
- `0x1400ab43c`
- `0x1400ab594`
- `0x140128d90`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x140128df4`
- `ntdll!RtlDeleteResource` at `0x140128df4`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x140128e0c`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x140128e0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140128e1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140128e1f`

## pseudocode

```c
void MspUninitializeLazyWriter(void)
{
  if ( LazyWriterInitialized )
  {
    if ( LazyWriterEnabled || LazyCheckpointingEnabled )
    {
      MsSetEvent((struct MS_EVENT_USERMODE *)&StopDeferredIoThreadEvent);
      MsWaitForEvent((struct MS_EVENT_USERMODE *)&DeferredIoThreadTerminatedEvent, 0);
    }
    MsDeleteEvent((struct MS_EVENT_USERMODE *)&LazyWriterScanEvent);
    MsDeleteEvent((struct MS_EVENT_USERMODE *)&StopDeferredIoThreadEvent);
    MsDeleteEvent((struct MS_EVENT_USERMODE *)&DeferredIoThreadTerminatedEvent);
    RtlDeleteResource(&VolumeLazyWriterResource);
  }
  if ( PeriodicTimer )
  {
    CancelWaitableTimer(PeriodicTimer);
    CloseHandle(PeriodicTimer);
    PeriodicTimer = 0;
  }
  if ( ExternalCacheContextEx )
  {
    UmeUnregisterExternalCache();
    ExternalCacheContextEx = 0;
  }
  if ( VolumeListCursor )
  {
    CmsReferenced::Release(VolumeListCursor);
    VolumeListCursor = 0;
  }
  LazyWriterInitialized = 0;
}

```

## disassembly

```asm
0x140128d90  sub     rsp, 28h
0x140128d94  cmp     cs:?LazyWriterInitialized@@3EA, 0; uchar LazyWriterInitialized
0x140128d9b  jz      short loc_140128E00
0x140128d9d  cmp     cs:?LazyWriterEnabled@@3EA, 0; uchar LazyWriterEnabled
0x140128da4  jnz     short loc_140128DAF
0x140128da6  cmp     cs:?LazyCheckpointingEnabled@@3EA, 0; uchar LazyCheckpointingEnabled
0x140128dad  jz      short loc_140128DC9
0x140128daf  lea     rcx, ?StopDeferredIoThreadEvent@@3UMS_EVENT_USERMODE@@A; struct MS_EVENT_USERMODE *
0x140128db6  call    ?MsSetEvent@@YAXPEAUMS_EVENT_USERMODE@@@Z; MsSetEvent(MS_EVENT_USERMODE *)
0x140128dbb  xor     edx, edx; union _LARGE_INTEGER *
0x140128dbd  lea     rcx, ?DeferredIoThreadTerminatedEvent@@3UMS_EVENT_USERMODE@@A; struct MS_EVENT_USERMODE *
0x140128dc4  call    ?MsWaitForEvent@@YAJPEAUMS_EVENT_USERMODE@@PEAT_LARGE_INTEGER@@@Z; MsWaitForEvent(MS_EVENT_USERMODE *,_LARGE_INTEGER *)
0x140128dc9  lea     rcx, ?LazyWriterScanEvent@@3UMS_EVENT_USERMODE@@A; struct MS_EVENT_USERMODE *
0x140128dd0  call    ?MsDeleteEvent@@YAXPEAUMS_EVENT_USERMODE@@@Z; MsDeleteEvent(MS_EVENT_USERMODE *)
0x140128dd5  lea     rcx, ?StopDeferredIoThreadEvent@@3UMS_EVENT_USERMODE@@A; struct MS_EVENT_USERMODE *
0x140128ddc  call    ?MsDeleteEvent@@YAXPEAUMS_EVENT_USERMODE@@@Z; MsDeleteEvent(MS_EVENT_USERMODE *)
0x140128de1  lea     rcx, ?DeferredIoThreadTerminatedEvent@@3UMS_EVENT_USERMODE@@A; struct MS_EVENT_USERMODE *
0x140128de8  call    ?MsDeleteEvent@@YAXPEAUMS_EVENT_USERMODE@@@Z; MsDeleteEvent(MS_EVENT_USERMODE *)
0x140128ded  lea     rcx, ?VolumeLazyWriterResource@@3U_RTL_RESOURCE@@A; Resource
0x140128df4  call    cs:__imp_RtlDeleteResource
0x140128dfb  nop     dword ptr [rax+rax+00h]
0x140128e00  mov     rcx, cs:?PeriodicTimer@@3PEAXEA; hTimer
0x140128e07  test    rcx, rcx
0x140128e0a  jz      short loc_140128E36
0x140128e0c  call    cs:__imp_CancelWaitableTimer
0x140128e13  nop     dword ptr [rax+rax+00h]
0x140128e18  mov     rcx, cs:?PeriodicTimer@@3PEAXEA; hObject
0x140128e1f  call    cs:__imp_CloseHandle
0x140128e26  nop     dword ptr [rax+rax+00h]
0x140128e2b  mov     cs:?PeriodicTimer@@3PEAXEA, 0; void * PeriodicTimer
0x140128e36  mov     rcx, cs:?ExternalCacheContextEx@@3PEAXEA; void * ExternalCacheContextEx
0x140128e3d  test    rcx, rcx
0x140128e40  jz      short loc_140128E52
0x140128e42  call    UmeUnregisterExternalCache
0x140128e47  mov     cs:?ExternalCacheContextEx@@3PEAXEA, 0; void * ExternalCacheContextEx
0x140128e52  mov     rcx, cs:?VolumeListCursor@@3PEAVCmsVolume@@EA; this
0x140128e59  test    rcx, rcx
0x140128e5c  jz      short loc_140128E6E
0x140128e5e  call    ?Release@CmsReferenced@@QEAAXXZ; CmsReferenced::Release(void)
0x140128e63  mov     cs:?VolumeListCursor@@3PEAVCmsVolume@@EA, 0; CmsVolume * VolumeListCursor
0x140128e6e  mov     cs:?LazyWriterInitialized@@3EA, 0; uchar LazyWriterInitialized
0x140128e75  add     rsp, 28h
0x140128e79  retn
```
