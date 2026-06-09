# ProcessMonitor::~ProcessMonitor(void)

- ea: `0x180004e34`
- end: `0x180004f19`
- name: `??1ProcessMonitor@@UEAA@XZ`
- size: `229`
- prototype: `void __fastcall(ProcessMonitor *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180004fa4`
- `0x180005600`
- `0x18000eeed`

## callees

- `0x1800046f4`
- `0x180004e34`
- `0x180004f20`
- `0x180005144`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004e93`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004e9c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004ed4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004f06`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004e93`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004e9c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004ed4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004f06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ec1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ec1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004edc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004edc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004eb2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004eb2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004e59`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004e59`

## pseudocode

```c
void __fastcall ProcessMonitor::~ProcessMonitor(ProcessMonitor *this)
{
  char *v1; // r14
  RTL_SRWLOCK *v3; // rbp
  __int64 v4; // rdx
  void *v5; // rbx
  void *v6; // rsi
  void *v7; // r15
  wil::details::event_watcher_state *v8; // rsi
  DWORD LastError; // ebx
  void *v10; // rbx

  v1 = (char *)this + 24;
  *(_QWORD *)this = &ProcessMonitor::`vftable';
  v3 = (RTL_SRWLOCK *)((char *)this + 40);
  AcquireSRWLockExclusive((PSRWLOCK)this + 5);
  v5 = **(void ***)v1;
  **(_QWORD **)v1 = *(_QWORD *)v1;
  *(_QWORD *)(*(_QWORD *)v1 + 8LL) = *(_QWORD *)v1;
  *((_QWORD *)v1 + 1) = 0;
  if ( v5 != *(void **)v1 )
  {
    do
    {
      v6 = (void *)*((_QWORD *)v5 + 2);
      v7 = *(void **)v5;
      if ( v6 )
      {
        ProcessWatcherDesc::~ProcessWatcherDesc(*((ProcessWatcherDesc **)v5 + 2), v4);
        operator delete(v6);
      }
      operator delete(v5);
      v5 = v7;
    }
    while ( v7 != *(void **)v1 );
  }
  if ( v3 )
    ReleaseSRWLockExclusive(v3);
  v8 = (wil::details::event_watcher_state *)*((_QWORD *)this + 2);
  if ( v8 )
  {
    LastError = GetLastError();
    wil::details::event_watcher_state::~event_watcher_state(v8);
    operator delete(v8);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 2) = 0;
  std::list<std::unique_ptr<ProcessWatcherDesc>>::~list<std::unique_ptr<ProcessWatcherDesc>>(v1);
  v10 = (void *)*((_QWORD *)this + 2);
  if ( v10 )
  {
    wil::details::event_watcher_state::~event_watcher_state(*((wil::details::event_watcher_state **)this + 2));
    operator delete(v10);
  }
}

```

## disassembly

```asm
0x180004e34  push    rbx
0x180004e36  push    rbp
0x180004e37  push    rsi
0x180004e38  push    rdi
0x180004e39  push    r14
0x180004e3b  push    r15
0x180004e3d  sub     rsp, 28h
0x180004e41  lea     r14, [rcx+18h]
0x180004e45  mov     rdi, rcx
0x180004e48  lea     rax, ??_7ProcessMonitor@@6B@; const ProcessMonitor::`vftable'
0x180004e4f  mov     [rcx], rax
0x180004e52  lea     rbp, [r14+10h]
0x180004e56  mov     rcx, rbp; SRWLock
0x180004e59  call    cs:__imp_AcquireSRWLockExclusive
0x180004e5f  mov     rax, [r14]
0x180004e62  mov     rbx, [rax]
0x180004e65  mov     [rax], rax
0x180004e68  mov     rax, [r14]
0x180004e6b  mov     [rax+8], rax
0x180004e6f  mov     qword ptr [r14+8], 0
0x180004e77  cmp     rbx, [r14]
0x180004e7a  jz      short loc_180004EAA
0x180004e7c  mov     rsi, [rbx+10h]
0x180004e80  mov     r15, [rbx]
0x180004e83  test    rsi, rsi
0x180004e86  jz      short loc_180004E99
0x180004e88  mov     rcx, rsi; this
0x180004e8b  call    ??1ProcessWatcherDesc@@QEAA@XZ; ProcessWatcherDesc::~ProcessWatcherDesc(void)
0x180004e90  mov     rcx, rsi
0x180004e93  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004e99  mov     rcx, rbx
0x180004e9c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004ea2  mov     rbx, r15
0x180004ea5  cmp     r15, [r14]
0x180004ea8  jnz     short loc_180004E7C
0x180004eaa  test    rbp, rbp
0x180004ead  jz      short loc_180004EB8
0x180004eaf  mov     rcx, rbp; SRWLock
0x180004eb2  call    cs:__imp_ReleaseSRWLockExclusive
0x180004eb8  mov     rsi, [rdi+10h]
0x180004ebc  test    rsi, rsi
0x180004ebf  jz      short loc_180004EE2
0x180004ec1  call    cs:__imp_GetLastError
0x180004ec7  mov     rcx, rsi; this
0x180004eca  mov     ebx, eax
0x180004ecc  call    ??1event_watcher_state@details@wil@@QEAA@XZ; wil::details::event_watcher_state::~event_watcher_state(void)
0x180004ed1  mov     rcx, rsi
0x180004ed4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004eda  mov     ecx, ebx; dwErrCode
0x180004edc  call    cs:__imp_SetLastError
0x180004ee2  mov     rcx, r14
0x180004ee5  mov     qword ptr [rdi+10h], 0
0x180004eed  call    ??1?$list@V?$unique_ptr@VProcessWatcherDesc@@U?$default_delete@VProcessWatcherDesc@@@std@@@std@@V?$allocator@V?$unique_ptr@VProcessWatcherDesc@@U?$default_delete@VProcessWatcherDesc@@@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::unique_ptr<ProcessWatcherDesc>>::~list<std::unique_ptr<ProcessWatcherDesc>>(void)
0x180004ef2  mov     rbx, [rdi+10h]
0x180004ef6  test    rbx, rbx
0x180004ef9  jz      short loc_180004F0C
0x180004efb  mov     rcx, rbx; this
0x180004efe  call    ??1event_watcher_state@details@wil@@QEAA@XZ; wil::details::event_watcher_state::~event_watcher_state(void)
0x180004f03  mov     rcx, rbx
0x180004f06  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004f0c  add     rsp, 28h
0x180004f10  pop     r15
0x180004f12  pop     r14
0x180004f14  pop     rdi
0x180004f15  pop     rsi
0x180004f16  pop     rbp
0x180004f17  pop     rbx
0x180004f18  retn
```
