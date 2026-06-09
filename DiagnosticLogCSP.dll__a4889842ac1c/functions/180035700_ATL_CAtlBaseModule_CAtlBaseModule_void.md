# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180035700`
- end: `0x180035737`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180036f00`

## callees

- `0x1800025cc`
- `0x180035700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003570d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003570d`

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
0x180035700  push    rbx
0x180035702  sub     rsp, 20h
0x180035706  mov     rbx, rcx
0x180035709  add     rcx, 28h ; '('; lpCriticalSection
0x18003570d  call    cs:__imp_DeleteCriticalSection
0x180035713  mov     rcx, [rbx+50h]; Block
0x180035717  test    rcx, rcx
0x18003571a  jz      short loc_180035729
0x18003571c  call    free
0x180035721  mov     qword ptr [rbx+50h], 0
0x180035729  mov     qword ptr [rbx+58h], 0
0x180035731  add     rsp, 20h
0x180035735  pop     rbx
0x180035736  retn
```
