# Tracker::staticInit(void)

- ea: `0x140004e5c`
- end: `0x140004eee`
- name: `?staticInit@Tracker@@SAJXZ`
- size: `146`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000248c`

## callees

- `0x14000355c`
- `0x140004e5c`
- `0x140004f2c`
- `0x140004f90`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x140004e6e`
- `KERNEL32!CreateEventW` at `0x140004e6e`

## pseudocode

```c
__int64 Tracker::staticInit(void)
{
  unsigned int v0; // ebx
  HANDLE EventW; // rax
  TrackerList *v2; // rax
  TrackerList *v3; // rax

  v0 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    Tracker::s_eventZeroTrackers = EventW;
    v2 = (TrackerList *)MemAllocClear(0x28u);
    if ( v2 )
    {
      Tracker::s_pTrackerList = TrackerList::TrackerList(v2);
      if ( Tracker::s_pTrackerList )
      {
        v3 = (TrackerList *)MemAllocClear(0x28u);
        if ( v3 )
        {
          Tracker::s_pTrackerListenerList = TrackerList::TrackerList(v3);
          if ( Tracker::s_pTrackerListenerList )
            return v0;
        }
        else
        {
          Tracker::s_pTrackerListenerList = 0;
        }
      }
    }
    else
    {
      Tracker::s_pTrackerList = 0;
    }
    return (unsigned int)-2147024882;
  }
  return (unsigned int)GetLastWin32Error();
}

```

## disassembly

```asm
0x140004e5c  push    rbx
0x140004e5e  sub     rsp, 20h
0x140004e62  xor     r9d, r9d; lpName
0x140004e65  xor     r8d, r8d; bInitialState
0x140004e68  xor     edx, edx; bManualReset
0x140004e6a  xor     ecx, ecx; lpEventAttributes
0x140004e6c  xor     ebx, ebx
0x140004e6e  call    cs:__imp_CreateEventW
0x140004e74  test    rax, rax
0x140004e77  jnz     short loc_140004E82
0x140004e79  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x140004e7e  mov     ebx, eax
0x140004e80  jmp     short loc_140004EE6
0x140004e82  mov     ecx, 28h ; '('; unsigned __int64
0x140004e87  mov     cs:?s_eventZeroTrackers@Tracker@@0PEAXEA, rax; void * Tracker::s_eventZeroTrackers
0x140004e8e  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x140004e93  test    rax, rax
0x140004e96  jz      short loc_140004EDA
0x140004e98  mov     rcx, rax; this
0x140004e9b  call    ??0TrackerList@@QEAA@XZ; TrackerList::TrackerList(void)
0x140004ea0  mov     cs:?s_pTrackerList@Tracker@@0PEAVTrackerList@@EA, rax; TrackerList * Tracker::s_pTrackerList
0x140004ea7  test    rax, rax
0x140004eaa  jz      short loc_140004EE1
0x140004eac  mov     ecx, 28h ; '('; unsigned __int64
0x140004eb1  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x140004eb6  test    rax, rax
0x140004eb9  jz      short loc_140004ED1
0x140004ebb  mov     rcx, rax; this
0x140004ebe  call    ??0TrackerList@@QEAA@XZ; TrackerList::TrackerList(void)
0x140004ec3  mov     cs:?s_pTrackerListenerList@Tracker@@0PEAVTrackerList@@EA, rax; TrackerList * Tracker::s_pTrackerListenerList
0x140004eca  test    rax, rax
0x140004ecd  jnz     short loc_140004EE6
0x140004ecf  jmp     short loc_140004EE1
0x140004ed1  mov     cs:?s_pTrackerListenerList@Tracker@@0PEAVTrackerList@@EA, rbx; TrackerList * Tracker::s_pTrackerListenerList
0x140004ed8  jmp     short loc_140004EE1
0x140004eda  mov     cs:?s_pTrackerList@Tracker@@0PEAVTrackerList@@EA, rbx; TrackerList * Tracker::s_pTrackerList
0x140004ee1  mov     ebx, 8007000Eh
0x140004ee6  mov     eax, ebx
0x140004ee8  add     rsp, 20h
0x140004eec  pop     rbx
0x140004eed  retn
```
