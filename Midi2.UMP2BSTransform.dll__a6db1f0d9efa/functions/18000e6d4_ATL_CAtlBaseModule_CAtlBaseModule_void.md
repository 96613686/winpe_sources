# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18000e6d4`
- end: `0x18000e70b`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ed10`

## callees

- `0x180002934`
- `0x18000e6d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e6e1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e6e1`

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
0x18000e6d4  push    rbx
0x18000e6d6  sub     rsp, 20h
0x18000e6da  mov     rbx, rcx
0x18000e6dd  add     rcx, 28h ; '('; lpCriticalSection
0x18000e6e1  call    cs:__imp_DeleteCriticalSection
0x18000e6e7  mov     rcx, [rbx+50h]; Block
0x18000e6eb  test    rcx, rcx
0x18000e6ee  jz      short loc_18000E6FD
0x18000e6f0  call    free
0x18000e6f5  mov     qword ptr [rbx+50h], 0
0x18000e6fd  mov     qword ptr [rbx+58h], 0
0x18000e705  add     rsp, 20h
0x18000e709  pop     rbx
0x18000e70a  retn
```
