# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180022d04`
- end: `0x180022d3b`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800231d0`

## callees

- `0x180002258`
- `0x180022d04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022d11`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022d11`

## pseudocode

```c
void __fastcall ATL::CAtlBaseModule::~CAtlBaseModule(struct _RTL_CRITICAL_SECTION *this)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx

  DeleteCriticalSection(this + 1);
  DebugInfo = this[2].DebugInfo;
  if ( DebugInfo )
  {
    free(DebugInfo);
    this[2].DebugInfo = 0;
  }
  *(_QWORD *)&this[2].LockCount = 0;
}

```

## disassembly

```asm
0x180022d04  push    rbx
0x180022d06  sub     rsp, 20h
0x180022d0a  mov     rbx, rcx
0x180022d0d  add     rcx, 28h ; '('; lpCriticalSection
0x180022d11  call    cs:__imp_DeleteCriticalSection
0x180022d17  mov     rcx, [rbx+50h]; Block
0x180022d1b  test    rcx, rcx
0x180022d1e  jz      short loc_180022D2D
0x180022d20  call    free
0x180022d25  mov     qword ptr [rbx+50h], 0
0x180022d2d  mov     qword ptr [rbx+58h], 0
0x180022d35  add     rsp, 20h
0x180022d39  pop     rbx
0x180022d3a  retn
```
