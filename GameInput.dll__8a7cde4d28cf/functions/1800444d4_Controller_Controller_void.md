# Controller::~Controller(void)

- ea: `0x1800444d4`
- end: `0x180044585`
- name: `??1Controller@@AEAA@XZ`
- size: `177`
- prototype: `void __fastcall(Controller *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180046d80`

## callees

- `0x1800444d4`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800444e1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800444e1`

## pseudocode

```c
void __fastcall Controller::~Controller(struct _RTL_CRITICAL_SECTION *this)
{
  ULONG_PTR SpinCount; // rcx
  HANDLE LockSemaphore; // rcx
  HANDLE OwningThread; // rcx
  __int64 v5; // rcx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx

  DeleteCriticalSection(this + 2);
  SpinCount = this[1].SpinCount;
  if ( SpinCount )
  {
    this[1].SpinCount = 0;
    (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)SpinCount + 16LL))(SpinCount);
  }
  LockSemaphore = this[1].LockSemaphore;
  if ( LockSemaphore )
  {
    this[1].LockSemaphore = 0;
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)LockSemaphore + 16LL))(LockSemaphore);
  }
  OwningThread = this[1].OwningThread;
  if ( OwningThread )
  {
    this[1].OwningThread = 0;
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)OwningThread + 16LL))(OwningThread);
  }
  v5 = *(_QWORD *)&this[1].LockCount;
  if ( v5 )
  {
    *(_QWORD *)&this[1].LockCount = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  DebugInfo = this[1].DebugInfo;
  if ( DebugInfo )
  {
    this[1].DebugInfo = 0;
    (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)&DebugInfo->Type + 16LL))(DebugInfo);
  }
}

```

## disassembly

```asm
0x1800444d4  push    rbx
0x1800444d6  sub     rsp, 20h
0x1800444da  mov     rbx, rcx
0x1800444dd  add     rcx, 50h ; 'P'; lpCriticalSection
0x1800444e1  call    cs:__imp_DeleteCriticalSection
0x1800444e8  nop     dword ptr [rax+rax+00h]
0x1800444ed  mov     rcx, [rbx+48h]
0x1800444f1  test    rcx, rcx
0x1800444f4  jz      short loc_18004450A
0x1800444f6  mov     qword ptr [rbx+48h], 0
0x1800444fe  mov     rax, [rcx]
0x180044501  mov     rax, [rax+10h]
0x180044505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004450a  mov     rcx, [rbx+40h]
0x18004450e  test    rcx, rcx
0x180044511  jz      short loc_180044527
0x180044513  mov     qword ptr [rbx+40h], 0
0x18004451b  mov     rax, [rcx]
0x18004451e  mov     rax, [rax+10h]
0x180044522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044527  mov     rcx, [rbx+38h]
0x18004452b  test    rcx, rcx
0x18004452e  jz      short loc_180044544
0x180044530  mov     qword ptr [rbx+38h], 0
0x180044538  mov     rax, [rcx]
0x18004453b  mov     rax, [rax+10h]
0x18004453f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044544  mov     rcx, [rbx+30h]
0x180044548  test    rcx, rcx
0x18004454b  jz      short loc_180044561
0x18004454d  mov     qword ptr [rbx+30h], 0
0x180044555  mov     rax, [rcx]
0x180044558  mov     rax, [rax+10h]
0x18004455c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044561  mov     rcx, [rbx+28h]
0x180044565  test    rcx, rcx
0x180044568  jz      short loc_18004457E
0x18004456a  mov     qword ptr [rbx+28h], 0
0x180044572  mov     rax, [rcx]
0x180044575  mov     rax, [rax+10h]
0x180044579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004457e  add     rsp, 20h
0x180044582  pop     rbx
0x180044583  retn
```
