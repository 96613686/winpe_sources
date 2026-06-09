# MspInitializeLazyWriter(void)

- ea: `0x140127d78`
- end: `0x140128129`
- name: `?MspInitializeLazyWriter@@YAJXZ`
- size: `945`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140087ec0`

## callees

- `0x1400057f8`
- `0x14007e44c`
- `0x140086620`
- `0x1400ab158`
- `0x1400ab594`
- `0x140126ea4`
- `0x140127d78`

## import_xrefs

- `ntdll!RtlInitializeResource` at `0x140127d85`
- `ntdll!RtlInitializeResource` at `0x140127d85`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1401280be`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1401280be`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x14012807f`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x14012807f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 MspInitializeLazyWriter(void)
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  CmsVolume *v2; // rax
  CmsReferenced *v3; // rax
  __int64 result; // rax
  HANDLE WaitableTimerW; // rax
  void *v6; // rdx
  void (*v7)(void *); // rcx
  void **v8; // r8
  LARGE_INTEGER DueTime; // [rsp+60h] [rbp+8h] BYREF

  RtlInitializeResource(&VolumeLazyWriterResource);
  LazyWriterSpinLock = 0;
  DirtyPageCountSpinLock = 0;
  LazyWriterScanEvent = 0;
  qword_1402203C8 = 0;
  dword_1402203D2 = 0;
  word_1402203D6 = _mm_extract_epi16((__m128i)0LL, 7);
  word_1402203D0 = 256;
  StopDeferredIoThreadEvent = 0;
  qword_1402203E8 = 0;
  dword_1402203F2 = 0;
  word_1402203F6 = _mm_extract_epi16((__m128i)0LL, 7);
  word_1402203F0 = 256;
  DeferredIoThreadTerminatedEvent = 0;
  qword_140220418 = 0;
  dword_140220422 = 0;
  word_140220426 = _mm_extract_epi16((__m128i)0LL, 7);
  word_140220420 = 256;
  DeferredIoThreadReadyEvent = 0;
  xmmword_140220438 = 0;
  WORD4(xmmword_140220438) = 0;
  LazyWriterInitialized = 1;
  qword_140220450 = (__int64)&DirtyTableList;
  DirtyTableList = (struct _LIST_ENTRY *)&DirtyTableList;
  qword_140220400 = (__int64)&VolumeList;
  VolumeList.Flink = &VolumeList;
  memset_0(&NewDirtyPagesInfo, 0, 0x40u);
  NewDirtyPagesInfo = 1;
  if ( !dword_1402200AC )
    dword_1402200AC = 128;
  if ( !qword_1402200B0 )
    qword_1402200B0 = 5;
  if ( !dword_1402200B8 )
    dword_1402200B8 = 35;
  if ( !dword_1402200BC )
    dword_1402200BC = 55;
  if ( !dword_1402200C0 )
    dword_1402200C0 = 1500;
  if ( !dword_1402200C8 )
    dword_1402200C8 = 1600;
  if ( !dword_1402200CC )
    dword_1402200CC = 0x40000;
  LazyWriterQueueSpinLock = 0;
  dword_140220470 = 0;
  v0 = 0;
  v1 = 0;
  do
  {
    *(&WorkerEntriesQueue + v1 + 1) = (struct _LIST_ENTRY near *)&(&WorkerEntriesQueue)[v1];
    (&WorkerEntriesQueue)[v1] = (struct _LIST_ENTRY near *)&(&WorkerEntriesQueue)[v1];
    ++v0;
    v1 += 2;
  }
  while ( v0 != 3 );
  v2 = (CmsVolume *)CmsVolume::operator new(v1 * 8);
  DueTime.QuadPart = (LONGLONG)v2;
  if ( v2 )
    v3 = CmsVolume::CmsVolume(v2);
  else
    v3 = 0;
  VolumeListCursor = v3;
  if ( !v3 )
    return 3221225626LL;
  if ( !byte_14022007A )
    byte_14022007A = 50;
  if ( !byte_14022007B )
    byte_14022007B = 35;
  if ( !byte_14022007C )
    byte_14022007C = 5;
  if ( !byte_14022007D )
    byte_14022007D = 30;
  if ( !byte_140220080 )
    byte_140220080 = 30;
  if ( !byte_14022007E )
    byte_14022007E = 35;
  byte_14022007F = 0;
  if ( dword_14022008C )
    LazyWriterMaxWorkersPerVolume = dword_14022008C;
  if ( dword_140220090 )
    LazyWriterMaxLogWorkersPerVolume = dword_140220090;
  if ( dword_140220094 )
    LazyWriterMaxWorkersTotal = dword_140220094;
  if ( dword_140220098 )
    LazyWriterMaxLogWorkersTotal = dword_140220098;
  if ( dword_14022009C )
    LazyWriterScanThresholdPerVolume = dword_14022009C;
  if ( !dword_1402200A0 )
    dword_1402200A0 = 50;
  if ( !dword_1402200A4 )
    dword_1402200A4 = 0x8000;
  if ( !dword_1402200A8 )
    dword_1402200A8 = 4096;
  if ( HIBYTE(word_140220078) || (result = 0, (_BYTE)word_140220078) )
  {
    WaitableTimerW = CreateWaitableTimerW(0, 0, 0);
    PeriodicTimer = WaitableTimerW;
    if ( WaitableTimerW )
    {
      DueTime.QuadPart = -40000000;
      if ( !SetWaitableTimer(WaitableTimerW, &DueTime, 4000, 0, 0, 0) )
        return 3221225473LL;
      result = MsCreateSystemThread(v7, v6, v8);
      if ( (int)result >= 0 )
      {
        MsWaitForEvent((struct MS_EVENT_USERMODE *)&DeferredIoThreadReadyEvent, 0);
        result = UmeRegisterExternalCacheEx(MspExternalCacheCallbackEx, &ExternalCacheContextEx);
        if ( (int)result >= 0 )
        {
          LazyCheckpointingEnabled = HIBYTE(word_140220078);
          LazyWriterEnabled = word_140220078;
        }
      }
      return result;
    }
    return 3221225626LL;
  }
  return result;
}

```

## disassembly

```asm
0x140127d78  push    rbx
0x140127d7a  sub     rsp, 50h
0x140127d7e  lea     rcx, ?VolumeLazyWriterResource@@3U_RTL_RESOURCE@@A; Resource
0x140127d85  call    cs:__imp_RtlInitializeResource
0x140127d8c  nop     dword ptr [rax+rax+00h]
0x140127d91  xor     ebx, ebx
0x140127d93  mov     cs:?LazyWriterSpinLock@@3JA, ebx; long LazyWriterSpinLock
0x140127d99  mov     cs:?DirtyPageCountSpinLock@@3JA, ebx; long DirtyPageCountSpinLock
0x140127d9f  xorps   xmm0, xmm0
0x140127da2  movups  [rsp+58h+var_18], xmm0
0x140127da7  movups  cs:?LazyWriterScanEvent@@3UMS_EVENT_USERMODE@@A, xmm0; MS_EVENT_USERMODE LazyWriterScanEvent
0x140127dae  movsd   cs:qword_1402203C8, xmm0
0x140127db6  mov     eax, dword ptr [rsp+58h+var_18+0Ah]
0x140127dba  mov     cs:dword_1402203D2, eax
0x140127dc0  pextrw  eax, xmm0, 7
0x140127dc5  mov     cs:word_1402203D6, ax
0x140127dcc  mov     cs:word_1402203D0, 100h
0x140127dd5  movups  [rsp+58h+var_18], xmm0
0x140127dda  movups  cs:?StopDeferredIoThreadEvent@@3UMS_EVENT_USERMODE@@A, xmm0; MS_EVENT_USERMODE StopDeferredIoThreadEvent
0x140127de1  movsd   cs:qword_1402203E8, xmm0
0x140127de9  mov     eax, dword ptr [rsp+58h+var_18+0Ah]
0x140127ded  mov     cs:dword_1402203F2, eax
0x140127df3  pextrw  eax, xmm0, 7
0x140127df8  mov     cs:word_1402203F6, ax
0x140127dff  mov     cs:word_1402203F0, 100h
0x140127e08  movups  [rsp+58h+var_18], xmm0
0x140127e0d  movups  cs:?DeferredIoThreadTerminatedEvent@@3UMS_EVENT_USERMODE@@A, xmm0; MS_EVENT_USERMODE DeferredIoThreadTerminatedEvent
0x140127e14  movsd   cs:qword_140220418, xmm0
0x140127e1c  mov     eax, dword ptr [rsp+58h+var_18+0Ah]
0x140127e20  mov     cs:dword_140220422, eax
0x140127e26  pextrw  eax, xmm0, 7
0x140127e2b  mov     cs:word_140220426, ax
0x140127e32  mov     cs:word_140220420, 100h
0x140127e3b  movups  cs:?DeferredIoThreadReadyEvent@@3UMS_EVENT_USERMODE@@A, xmm0; MS_EVENT_USERMODE DeferredIoThreadReadyEvent
0x140127e42  movups  cs:xmmword_140220438, xmm0
0x140127e49  mov     word ptr cs:xmmword_140220438+8, bx
0x140127e50  mov     cs:?LazyWriterInitialized@@3EA, 1; uchar LazyWriterInitialized
0x140127e57  lea     rax, ?DirtyTableList@@3U_LIST_ENTRY@@A; _LIST_ENTRY DirtyTableList
0x140127e5e  mov     cs:qword_140220450, rax
0x140127e65  mov     cs:?DirtyTableList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY DirtyTableList
0x140127e6c  lea     rax, ?VolumeList@@3U_LIST_ENTRY@@A; _LIST_ENTRY VolumeList
0x140127e73  mov     cs:qword_140220400, rax
0x140127e7a  mov     cs:?VolumeList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY VolumeList
0x140127e81  xor     edx, edx; Val
0x140127e83  lea     r8d, [rbx+40h]; Size
0x140127e87  lea     rcx, ?NewDirtyPagesInfo@@3U_CC_DIRTY_PAGES_INFO_COPY@@A; void *
0x140127e8e  call    memset_0
0x140127e93  mov     cs:?NewDirtyPagesInfo@@3U_CC_DIRTY_PAGES_INFO_COPY@@A, 1; _CC_DIRTY_PAGES_INFO_COPY NewDirtyPagesInfo
0x140127e9d  cmp     cs:dword_1402200AC, ebx
0x140127ea3  jnz     short loc_140127EAF
0x140127ea5  mov     cs:dword_1402200AC, 80h
0x140127eaf  cmp     cs:qword_1402200B0, rbx
0x140127eb6  jnz     short loc_140127EC3
0x140127eb8  mov     cs:qword_1402200B0, 5
0x140127ec3  cmp     cs:dword_1402200B8, ebx
0x140127ec9  jnz     short loc_140127ED5
0x140127ecb  mov     cs:dword_1402200B8, 23h ; '#'
0x140127ed5  cmp     cs:dword_1402200BC, ebx
0x140127edb  jnz     short loc_140127EE7
0x140127edd  mov     cs:dword_1402200BC, 37h ; '7'
0x140127ee7  cmp     cs:dword_1402200C0, ebx
0x140127eed  jnz     short loc_140127EF9
0x140127eef  mov     cs:dword_1402200C0, 5DCh
0x140127ef9  cmp     cs:dword_1402200C8, ebx
0x140127eff  jnz     short loc_140127F0B
0x140127f01  mov     cs:dword_1402200C8, 640h
0x140127f0b  cmp     cs:dword_1402200CC, ebx
0x140127f11  jnz     short loc_140127F1D
0x140127f13  mov     cs:dword_1402200CC, 40000h
0x140127f1d  mov     cs:?LazyWriterQueueSpinLock@@3PAJA, rbx; long near * LazyWriterQueueSpinLock
0x140127f24  mov     cs:dword_140220470, ebx
0x140127f2a  mov     rdx, rbx
0x140127f2d  mov     rcx, rbx
0x140127f30  lea     r8, ?WorkerEntriesQueue@@3PAU_LIST_ENTRY@@A; _LIST_ENTRY near * WorkerEntriesQueue
0x140127f37  lea     rax, [rcx+r8]
0x140127f3b  mov     [rcx+r8+8], rax
0x140127f40  mov     [rax], rax
0x140127f43  inc     rdx
0x140127f46  lea     rcx, [rcx+10h]; unsigned __int64
0x140127f4a  cmp     rdx, 3
0x140127f4e  jnz     short loc_140127F37
0x140127f50  call    ??2CmsVolume@@SAPEAX_K@Z; CmsVolume::operator new(unsigned __int64)
0x140127f55  mov     qword ptr [rsp+58h+DueTime], rax
0x140127f5a  test    rax, rax
0x140127f5d  jz      short loc_140127F69
0x140127f5f  mov     rcx, rax; this
0x140127f62  call    ??0CmsVolume@@QEAA@XZ; CmsVolume::CmsVolume(void)
0x140127f67  jmp     short loc_140127F6C
0x140127f69  mov     rax, rbx
0x140127f6c  mov     cs:?VolumeListCursor@@3PEAVCmsVolume@@EA, rax; CmsVolume * VolumeListCursor
0x140127f73  test    rax, rax
0x140127f76  jz      loc_14012811D
0x140127f7c  cmp     cs:byte_14022007A, bl
0x140127f82  jnz     short loc_140127F8B
0x140127f84  mov     cs:byte_14022007A, 32h ; '2'
0x140127f8b  cmp     cs:byte_14022007B, bl
0x140127f91  jnz     short loc_140127F9A
0x140127f93  mov     cs:byte_14022007B, 23h ; '#'
0x140127f9a  cmp     cs:byte_14022007C, bl
0x140127fa0  jnz     short loc_140127FA9
0x140127fa2  mov     cs:byte_14022007C, 5
0x140127fa9  cmp     cs:byte_14022007D, bl
0x140127faf  jnz     short loc_140127FB8
0x140127fb1  mov     cs:byte_14022007D, 1Eh
0x140127fb8  cmp     cs:byte_140220080, bl
0x140127fbe  jnz     short loc_140127FC7
0x140127fc0  mov     cs:byte_140220080, 1Eh
0x140127fc7  cmp     cs:byte_14022007E, bl
0x140127fcd  jnz     short loc_140127FD6
0x140127fcf  mov     cs:byte_14022007E, 23h ; '#'
0x140127fd6  mov     cs:byte_14022007F, bl
0x140127fdc  mov     eax, cs:dword_14022008C
0x140127fe2  test    eax, eax
0x140127fe4  jz      short loc_140127FEC
0x140127fe6  mov     cs:?LazyWriterMaxWorkersPerVolume@@3JA, eax; long LazyWriterMaxWorkersPerVolume
0x140127fec  mov     eax, cs:dword_140220090
0x140127ff2  test    eax, eax
0x140127ff4  jz      short loc_140127FFC
0x140127ff6  mov     cs:?LazyWriterMaxLogWorkersPerVolume@@3JA, eax; long LazyWriterMaxLogWorkersPerVolume
0x140127ffc  mov     eax, cs:dword_140220094
0x140128002  test    eax, eax
0x140128004  jz      short loc_14012800C
0x140128006  mov     cs:?LazyWriterMaxWorkersTotal@@3JA, eax; long LazyWriterMaxWorkersTotal
0x14012800c  mov     eax, cs:dword_140220098
0x140128012  test    eax, eax
0x140128014  jz      short loc_14012801C
0x140128016  mov     cs:?LazyWriterMaxLogWorkersTotal@@3JA, eax; long LazyWriterMaxLogWorkersTotal
0x14012801c  mov     eax, cs:dword_14022009C
0x140128022  test    eax, eax
0x140128024  jz      short loc_14012802C
0x140128026  mov     cs:?LazyWriterScanThresholdPerVolume@@3JA, eax; long LazyWriterScanThresholdPerVolume
0x14012802c  cmp     cs:dword_1402200A0, ebx
0x140128032  jnz     short loc_14012803E
0x140128034  mov     cs:dword_1402200A0, 32h ; '2'
0x14012803e  cmp     cs:dword_1402200A4, ebx
0x140128044  jnz     short loc_140128050
0x140128046  mov     cs:dword_1402200A4, 8000h
0x140128050  cmp     cs:dword_1402200A8, ebx
0x140128056  jnz     short loc_140128062
0x140128058  mov     cs:dword_1402200A8, 1000h
0x140128062  cmp     byte ptr cs:word_140220078+1, bl
0x140128068  jnz     short loc_140128078
0x14012806a  mov     eax, ebx
0x14012806c  cmp     byte ptr cs:word_140220078, bl
0x140128072  jz      loc_140128122
0x140128078  xor     r8d, r8d; lpTimerName
0x14012807b  xor     edx, edx; bManualReset
0x14012807d  xor     ecx, ecx; lpTimerAttributes
0x14012807f  call    cs:__imp_CreateWaitableTimerW
0x140128086  nop     dword ptr [rax+rax+00h]
0x14012808b  mov     cs:?PeriodicTimer@@3PEAXEA, rax; void * PeriodicTimer
0x140128092  test    rax, rax
0x140128095  jz      loc_14012811D
0x14012809b  mov     qword ptr [rsp+58h+DueTime], 0FFFFFFFFFD9DA600h
0x1401280a4  mov     [rsp+58h+fResume], ebx; fResume
0x1401280a8  mov     [rsp+58h+lpArgToCompletionRoutine], rbx; lpArgToCompletionRoutine
0x1401280ad  xor     r9d, r9d; pfnCompletionRoutine
0x1401280b0  mov     r8d, 0FA0h; lPeriod
0x1401280b6  lea     rdx, [rsp+58h+DueTime]; lpDueTime
0x1401280bb  mov     rcx, rax; hTimer
0x1401280be  call    cs:__imp_SetWaitableTimer
0x1401280c5  nop     dword ptr [rax+rax+00h]
0x1401280ca  test    eax, eax
0x1401280cc  jnz     short loc_1401280D5
0x1401280ce  mov     eax, 0C0000001h
0x1401280d3  jmp     short loc_140128122
0x1401280d5  call    ?MsCreateSystemThread@@YAJP6AXPEAX@Z0PEAPEAX@Z; MsCreateSystemThread(void (*)(void *),void *,void * *)
0x1401280da  test    eax, eax
0x1401280dc  js      short loc_140128122
0x1401280de  xor     edx, edx; union _LARGE_INTEGER *
0x1401280e0  lea     rcx, ?DeferredIoThreadReadyEvent@@3UMS_EVENT_USERMODE@@A; struct MS_EVENT_USERMODE *
0x1401280e7  call    ?MsWaitForEvent@@YAJPEAUMS_EVENT_USERMODE@@PEAT_LARGE_INTEGER@@@Z; MsWaitForEvent(MS_EVENT_USERMODE *,_LARGE_INTEGER *)
0x1401280ec  lea     rdx, ?ExternalCacheContextEx@@3PEAXEA; void * ExternalCacheContextEx
0x1401280f3  lea     rcx, ?MspExternalCacheCallbackEx@@YAXPEAXPEAU_CC_DIRTY_PAGES_INFO_COPY@@@Z; MspExternalCacheCallbackEx(void *,_CC_DIRTY_PAGES_INFO_COPY *)
0x1401280fa  call    UmeRegisterExternalCacheEx
0x1401280ff  test    eax, eax
0x140128101  js      short loc_140128122
0x140128103  mov     cl, byte ptr cs:word_140220078
0x140128109  mov     cs:?LazyWriterEnabled@@3EA, cl; uchar LazyWriterEnabled
0x14012810f  mov     cl, byte ptr cs:word_140220078+1
0x140128115  mov     cs:?LazyCheckpointingEnabled@@3EA, cl; uchar LazyCheckpointingEnabled
0x14012811b  jmp     short loc_140128122
0x14012811d  mov     eax, 0C000009Ah
0x140128122  add     rsp, 50h
0x140128126  pop     rbx
0x140128127  retn
```
