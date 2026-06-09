# CMemoryLog::~CMemoryLog(void)

- ea: `0x1800348c4`
- end: `0x180034910`
- name: `??1CMemoryLog@@QEAA@XZ`
- size: `76`
- prototype: `void __fastcall(CMemoryLog *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800133cc`

## callees

- `0x180001fb0`
- `0x1800348c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800348f5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800348f5`

## pseudocode

```c
void __fastcall CMemoryLog::~CMemoryLog(struct _RTL_CRITICAL_SECTION *this)
{
  bool v1; // zf

  v1 = LODWORD(this[3].DebugInfo) == 0;
  this->DebugInfo = 0;
  *(_QWORD *)&this->LockCount = 0;
  this->OwningThread = 0;
  LODWORD(this[1].SpinCount) = 0;
  if ( !v1 )
  {
    DeleteCriticalSection(this + 2);
    LODWORD(this[3].DebugInfo) = 0;
  }
  BUFFER::~BUFFER((BUFFER *)&this->LockSemaphore);
}

```

## disassembly

```asm
0x1800348c4  push    rbx
0x1800348c6  sub     rsp, 20h
0x1800348ca  cmp     dword ptr [rcx+78h], 0
0x1800348ce  mov     rbx, rcx
0x1800348d1  mov     qword ptr [rcx], 0
0x1800348d8  mov     qword ptr [rcx+8], 0
0x1800348e0  mov     qword ptr [rcx+10h], 0
0x1800348e8  mov     dword ptr [rcx+48h], 0
0x1800348ef  jz      short loc_180034902
0x1800348f1  add     rcx, 50h ; 'P'; lpCriticalSection
0x1800348f5  call    cs:__imp_DeleteCriticalSection
0x1800348fb  mov     dword ptr [rbx+78h], 0
0x180034902  lea     rcx, [rbx+18h]; this
0x180034906  add     rsp, 20h
0x18003490a  pop     rbx
0x18003490b  jmp     ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
```
