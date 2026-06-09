# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x1800267d0`
- end: `0x180026807`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180028f90`

## callees

- `0x1800023d8`
- `0x1800267d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800267dd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800267dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800267d0  push    rbx
0x1800267d2  sub     rsp, 20h
0x1800267d6  mov     rbx, rcx
0x1800267d9  add     rcx, 28h ; '('; lpCriticalSection
0x1800267dd  call    cs:__imp_DeleteCriticalSection
0x1800267e3  mov     rcx, [rbx+50h]; Block
0x1800267e7  test    rcx, rcx
0x1800267ea  jz      short loc_1800267F9
0x1800267ec  call    free
0x1800267f1  mov     qword ptr [rbx+50h], 0
0x1800267f9  mov     qword ptr [rbx+58h], 0
0x180026801  add     rsp, 20h
0x180026805  pop     rbx
0x180026806  retn
```
