# BdeSvcWorkTracking::~BdeSvcWorkTracking(void)

- ea: `0x18002f364`
- end: `0x18002f3ed`
- name: `??1BdeSvcWorkTracking@@QEAA@XZ`
- size: `137`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18007d640`

## callees

- `0x18002f364`
- `0x18002f3f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f36d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f36d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f3cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f3cd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002f3e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f391`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f3ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f391`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f3ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall BdeSvcWorkTracking::~BdeSvcWorkTracking(struct _RTL_CRITICAL_SECTION *this)
{
  void *v2; // rcx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx

  EnterCriticalSection(this);
  if ( this[1].LockSemaphore )
    this[1].LockSemaphore = 0;
  v2 = *(void **)&this[1].LockCount;
  if ( v2 )
  {
    CloseHandle(v2);
    *(_QWORD *)&this[1].LockCount = 0;
  }
  DebugInfo = this[2].DebugInfo;
  if ( DebugInfo )
  {
    CloseHandle(DebugInfo);
    this[2].DebugInfo = 0;
  }
  BdeSvcWorkTracking::CancelAndWaitForOutstandingWorkImpl((BdeSvcWorkTracking *)this);
  LeaveCriticalSection(this);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x18002f364  push    rbx
0x18002f366  sub     rsp, 20h
0x18002f36a  mov     rbx, rcx
0x18002f36d  call    cs:__imp_EnterCriticalSection
0x18002f374  nop     dword ptr [rax+rax+00h]
0x18002f379  cmp     qword ptr [rbx+40h], 0
0x18002f37e  jz      short loc_18002F388
0x18002f380  mov     qword ptr [rbx+40h], 0
0x18002f388  mov     rcx, [rbx+30h]; hObject
0x18002f38c  test    rcx, rcx
0x18002f38f  jz      short loc_18002F3A5
0x18002f391  call    cs:__imp_CloseHandle
0x18002f398  nop     dword ptr [rax+rax+00h]
0x18002f39d  mov     qword ptr [rbx+30h], 0
0x18002f3a5  mov     rcx, [rbx+50h]; hObject
0x18002f3a9  test    rcx, rcx
0x18002f3ac  jz      short loc_18002F3C2
0x18002f3ae  call    cs:__imp_CloseHandle
0x18002f3b5  nop     dword ptr [rax+rax+00h]
0x18002f3ba  mov     qword ptr [rbx+50h], 0
0x18002f3c2  mov     rcx, rbx; this
0x18002f3c5  call    ?CancelAndWaitForOutstandingWorkImpl@BdeSvcWorkTracking@@AEAAXXZ; BdeSvcWorkTracking::CancelAndWaitForOutstandingWorkImpl(void)
0x18002f3ca  mov     rcx, rbx; lpCriticalSection
0x18002f3cd  call    cs:__imp_LeaveCriticalSection
0x18002f3d4  nop     dword ptr [rax+rax+00h]
0x18002f3d9  mov     rcx, rbx
0x18002f3dc  add     rsp, 20h
0x18002f3e0  pop     rbx
0x18002f3e1  jmp     cs:__imp_DeleteCriticalSection
```
