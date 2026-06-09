# FontSetCache::StartMonitorThread(void)

- ea: `0x180098ad0`
- end: `0x180098b32`
- name: `?StartMonitorThread@FontSetCache@@UEAAXXZ`
- size: `98`
- prototype: `void __fastcall(FontSetCache *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180063950`

## callees

- `0x18000d55c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180098b18`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180098b18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098b2b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098ae7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098ae7`

## pseudocode

```c
void __fastcall FontSetCache::StartMonitorThread(FontSetCache *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 216);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  *((_QWORD *)this + 3) = 1953066601;
  EventLogger::LogEvent<EventTag>((unsigned int *)this + 4, 0x746553746E6F46LL, 0x6574617473LL, 1953066601);
  ResumeThread(*((HANDLE *)this + 15));
  LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x180098ad0  mov     [rsp+arg_0], rbx
0x180098ad5  push    rdi
0x180098ad6  sub     rsp, 20h
0x180098ada  lea     rdi, [rcx+0D8h]
0x180098ae1  mov     rbx, rcx
0x180098ae4  mov     rcx, rdi; lpCriticalSection
0x180098ae7  call    cs:__imp_EnterCriticalSection
0x180098aed  mov     r9d, 74696E69h
0x180098af3  lea     rcx, [rbx+10h]
0x180098af7  mov     rdx, 746553746E6F46h
0x180098b01  mov     [rbx+18h], r9
0x180098b05  mov     r8, 6574617473h
0x180098b0f  call    ??$LogEvent@VEventTag@@@EventLogger@@QEBAXVEventTag@@00@Z; EventLogger::LogEvent<EventTag>(EventTag,EventTag,EventTag)
0x180098b14  mov     rcx, [rbx+78h]; hThread
0x180098b18  call    cs:__imp_ResumeThread
0x180098b1e  mov     rcx, rdi
0x180098b21  mov     rbx, [rsp+28h+arg_0]
0x180098b26  add     rsp, 20h
0x180098b2a  pop     rdi
0x180098b2b  jmp     cs:__imp_LeaveCriticalSection
```
