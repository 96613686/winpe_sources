# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180011f50`
- end: `0x180011f87`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012be0`

## callees

- `0x1800039e4`
- `0x180011f50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011f5d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011f5d`

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
0x180011f50  push    rbx
0x180011f52  sub     rsp, 20h
0x180011f56  mov     rbx, rcx
0x180011f59  add     rcx, 28h ; '('; lpCriticalSection
0x180011f5d  call    cs:__imp_DeleteCriticalSection
0x180011f63  mov     rcx, [rbx+50h]; Block
0x180011f67  test    rcx, rcx
0x180011f6a  jz      short loc_180011F79
0x180011f6c  call    free
0x180011f71  mov     qword ptr [rbx+50h], 0
0x180011f79  mov     qword ptr [rbx+58h], 0
0x180011f81  add     rsp, 20h
0x180011f85  pop     rbx
0x180011f86  retn
```
