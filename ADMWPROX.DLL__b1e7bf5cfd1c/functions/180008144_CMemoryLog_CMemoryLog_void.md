# CMemoryLog::~CMemoryLog(void)

- ea: `0x180008144`
- end: `0x180008197`
- name: `??1CMemoryLog@@QEAA@XZ`
- size: `83`
- prototype: `void __fastcall(CMemoryLog *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002400`

## callees

- `0x1800073dc`
- `0x180008144`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180008175`
- `KERNEL32!DeleteCriticalSection` at `0x180008175`

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
  if ( BYTE4(this[1].LockSemaphore) )
    BUFFER::FreeMemoryInternal((BUFFER *)&this->LockSemaphore);
}

```

## disassembly

```asm
0x180008144  push    rbx
0x180008146  sub     rsp, 20h
0x18000814a  cmp     dword ptr [rcx+78h], 0
0x18000814e  mov     rbx, rcx
0x180008151  mov     qword ptr [rcx], 0
0x180008158  mov     qword ptr [rcx+8], 0
0x180008160  mov     qword ptr [rcx+10h], 0
0x180008168  mov     dword ptr [rcx+48h], 0
0x18000816f  jz      short loc_180008182
0x180008171  add     rcx, 50h ; 'P'; lpCriticalSection
0x180008175  call    cs:__imp_DeleteCriticalSection
0x18000817b  mov     dword ptr [rbx+78h], 0
0x180008182  lea     rcx, [rbx+18h]; this
0x180008186  cmp     byte ptr [rcx+2Ch], 0
0x18000818a  jz      short loc_180008191
0x18000818c  call    ?FreeMemoryInternal@BUFFER@@AEAAXXZ; BUFFER::FreeMemoryInternal(void)
0x180008191  add     rsp, 20h
0x180008195  pop     rbx
0x180008196  retn
```
