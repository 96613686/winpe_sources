# ControllerWatcher::~ControllerWatcher(void)

- ea: `0x18004458c`
- end: `0x1800446d0`
- name: `??1ControllerWatcher@@QEAA@XZ`
- size: `324`
- prototype: `void __fastcall(ControllerWatcher *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18002d6b0`
- `0x180045090`

## callees

- `0x18004458c`
- `0x1800446d8`
- `0x180046d80`
- `0x1800470b0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180044682`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180044682`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180044669`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180044669`

## pseudocode

```c
void __fastcall ControllerWatcher::~ControllerWatcher(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE *p_LockSemaphore; // rsi
  __int64 v3; // rbx
  _QWORD *v4; // rcx
  HANDLE LockSemaphore; // rcx
  ULONG_PTR SpinCount; // rcx
  ULONG_PTR v7; // rcx
  HANDLE v8; // rcx

  p_LockSemaphore = &this->LockSemaphore;
  if ( this->DebugInfo )
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)*p_LockSemaphore + 56LL))(*p_LockSemaphore);
  if ( *(_QWORD *)&this->LockCount )
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)*p_LockSemaphore + 72LL))(*p_LockSemaphore);
  if ( this->OwningThread )
    (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)this->SpinCount + 56LL))(this->SpinCount);
  while ( (struct _RTL_CRITICAL_SECTION *)this[2].DebugInfo != &this[2] )
  {
    v3 = *(_QWORD *)&this[2].LockCount;
    if ( *(struct _RTL_CRITICAL_SECTION **)v3 != &this[2] || (v4 = *(_QWORD **)(v3 + 8), *v4 != v3) )
      __fastfail(3u);
    *(_QWORD *)&this[2].LockCount = v4;
    *v4 = this + 2;
    Controller::StopWatcher((Controller *)(v3 - 16));
    Controller::Release((PVOID)(v3 - 16));
  }
  LockSemaphore = this->LockSemaphore;
  if ( LockSemaphore )
  {
    this->LockSemaphore = 0;
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)LockSemaphore + 16LL))(LockSemaphore);
  }
  SpinCount = this->SpinCount;
  if ( SpinCount )
  {
    this->SpinCount = 0;
    (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)SpinCount + 16LL))(SpinCount);
  }
  if ( LOBYTE(this[4].LockSemaphore) )
    RoUninitialize();
  FaultTracker::~FaultTracker((FaultTracker *)&this[2].OwningThread);
  DeleteCriticalSection(this + 1);
  v7 = this->SpinCount;
  if ( v7 )
  {
    this->SpinCount = 0;
    (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)v7 + 16LL))(v7);
  }
  v8 = *p_LockSemaphore;
  if ( *p_LockSemaphore )
  {
    *p_LockSemaphore = 0;
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v8 + 16LL))(v8);
  }
}

```

## disassembly

```asm
0x18004458c  push    rbx
0x18004458e  push    rbp
0x18004458f  push    rsi
0x180044590  push    rdi
0x180044591  sub     rsp, 28h
0x180044595  mov     rdx, [rcx]
0x180044598  lea     rsi, [rcx+18h]
0x18004459c  mov     rdi, rcx
0x18004459f  test    rdx, rdx
0x1800445a2  jz      short loc_1800445B3
0x1800445a4  mov     rcx, [rsi]
0x1800445a7  mov     rax, [rcx]
0x1800445aa  mov     rax, [rax+38h]
0x1800445ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445b3  mov     rdx, [rdi+8]
0x1800445b7  test    rdx, rdx
0x1800445ba  jz      short loc_1800445CB
0x1800445bc  mov     rcx, [rsi]
0x1800445bf  mov     rax, [rcx]
0x1800445c2  mov     rax, [rax+48h]
0x1800445c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445cb  mov     rdx, [rdi+10h]
0x1800445cf  test    rdx, rdx
0x1800445d2  jz      short loc_1800445E4
0x1800445d4  mov     rcx, [rdi+20h]
0x1800445d8  mov     rax, [rcx]
0x1800445db  mov     rax, [rax+38h]
0x1800445df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445e4  lea     rbp, [rdi+50h]
0x1800445e8  cmp     [rbp+0], rbp
0x1800445ec  jz      short loc_180044626
0x1800445ee  lea     rax, [rdi+50h]
0x1800445f2  mov     rbx, [rax+8]
0x1800445f6  cmp     [rbx], rax
0x1800445f9  jnz     short loc_18004461F
0x1800445fb  mov     rcx, [rbx+8]
0x1800445ff  cmp     [rcx], rbx
0x180044602  jnz     short loc_18004461F
0x180044604  mov     [rax+8], rcx
0x180044608  mov     [rcx], rax
0x18004460b  lea     rcx, [rbx-10h]; this
0x18004460f  call    ?StopWatcher@Controller@@QEAAXXZ; Controller::StopWatcher(void)
0x180044614  lea     rcx, [rbx-10h]; P
0x180044618  call    ?Release@Controller@@UEAAKXZ; Controller::Release(void)
0x18004461d  jmp     short loc_1800445E8
0x18004461f  mov     ecx, 3
0x180044624  int     29h; Win8: RtlFailFast(ecx)
0x180044626  mov     rcx, [rdi+18h]
0x18004462a  test    rcx, rcx
0x18004462d  jz      short loc_180044643
0x18004462f  mov     qword ptr [rdi+18h], 0
0x180044637  mov     rax, [rcx]
0x18004463a  mov     rax, [rax+10h]
0x18004463e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044643  mov     rcx, [rdi+20h]
0x180044647  test    rcx, rcx
0x18004464a  jz      short loc_180044660
0x18004464c  mov     qword ptr [rdi+20h], 0
0x180044654  mov     rax, [rcx]
0x180044657  mov     rax, [rax+10h]
0x18004465b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044660  cmp     byte ptr [rdi+0B8h], 0
0x180044667  jz      short loc_180044675
0x180044669  call    cs:__imp_RoUninitialize
0x180044670  nop     dword ptr [rax+rax+00h]
0x180044675  lea     rcx, [rdi+60h]; this
0x180044679  call    ??1FaultTracker@@QEAA@XZ; FaultTracker::~FaultTracker(void)
0x18004467e  lea     rcx, [rdi+28h]; lpCriticalSection
0x180044682  call    cs:__imp_DeleteCriticalSection
0x180044689  nop     dword ptr [rax+rax+00h]
0x18004468e  mov     rcx, [rdi+20h]
0x180044692  test    rcx, rcx
0x180044695  jz      short loc_1800446AB
0x180044697  mov     qword ptr [rdi+20h], 0
0x18004469f  mov     rax, [rcx]
0x1800446a2  mov     rax, [rax+10h]
0x1800446a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800446ab  mov     rcx, [rsi]
0x1800446ae  test    rcx, rcx
0x1800446b1  jz      short loc_1800446C6
0x1800446b3  mov     qword ptr [rsi], 0
0x1800446ba  mov     rax, [rcx]
0x1800446bd  mov     rax, [rax+10h]
0x1800446c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800446c6  add     rsp, 28h
0x1800446ca  pop     rdi
0x1800446cb  pop     rsi
0x1800446cc  pop     rbp
0x1800446cd  pop     rbx
0x1800446ce  retn
```
