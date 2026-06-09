# WindowsPerformanceRecorder::CInstanceNameScopedData::~CInstanceNameScopedData(void)

- ea: `0x1800374dc`
- end: `0x18003753c`
- name: `??1CInstanceNameScopedData@WindowsPerformanceRecorder@@QEAA@XZ`
- size: `96`
- prototype: `void __fastcall(WindowsPerformanceRecorder::CInstanceNameScopedData *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180056110`

## callees

- `0x18001e6e0`
- `0x180037544`
- `0x180037634`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800374ed`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800374ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180037535`

## string_xrefs

- `0x1800374f6`: `InstanceNameScopedData deleted`

## pseudocode

```c
void __fastcall WindowsPerformanceRecorder::CInstanceNameScopedData::~CInstanceNameScopedData(
        struct _RTL_CRITICAL_SECTION *this)
{
  const char *v2; // [rsp+28h] [rbp-10h]

  SetEvent(this[2].LockSemaphore);
  WindowsPerformanceRecorder::TraceHR(
    (WindowsPerformanceRecorder *)4,
    "~CInstanceNameScopedData",
    (const char *)0x46,
    0,
    "InstanceNameScopedData deleted",
    v2);
  ATL::CHandle::~CHandle((ATL::CHandle *)&this[2].LockSemaphore);
  WindowsPerformanceRecorder::CProfilesCache::~CProfilesCache((WindowsPerformanceRecorder::CProfilesCache *)&this[1]);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x1800374dc  mov     [rsp+arg_0], rbx
0x1800374e1  push    rdi
0x1800374e2  sub     rsp, 30h
0x1800374e6  mov     rdi, rcx
0x1800374e9  mov     rcx, [rcx+68h]; hEvent
0x1800374ed  call    cs:__imp_SetEvent
0x1800374f3  xor     r9d, r9d; unsigned int
0x1800374f6  lea     rax, aInstancenamesc; "InstanceNameScopedData deleted"
0x1800374fd  lea     rdx, aCinstancenames; "~CInstanceNameScopedData"
0x180037504  mov     [rsp+38h+Format], rax; Format
0x180037509  lea     r8d, [r9+46h]; char *
0x18003750d  lea     ecx, [r9+4]; this
0x180037511  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180037516  lea     rcx, [rdi+68h]; this
0x18003751a  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x18003751f  lea     rcx, [rdi+28h]; this
0x180037523  call    ??1CProfilesCache@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::CProfilesCache::~CProfilesCache(void)
0x180037528  mov     rcx, rdi
0x18003752b  mov     rbx, [rsp+38h+arg_0]
0x180037530  add     rsp, 30h
0x180037534  pop     rdi
0x180037535  jmp     cs:__imp_DeleteCriticalSection
```
