# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18000cacc`
- end: `0x18000cb03`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800144e0`

## callees

- `0x180002fd4`
- `0x18000cacc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cad9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cad9`

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
0x18000cacc  push    rbx
0x18000cace  sub     rsp, 20h
0x18000cad2  mov     rbx, rcx
0x18000cad5  add     rcx, 28h ; '('; lpCriticalSection
0x18000cad9  call    cs:__imp_DeleteCriticalSection
0x18000cadf  mov     rcx, [rbx+50h]; Block
0x18000cae3  test    rcx, rcx
0x18000cae6  jz      short loc_18000CAF5
0x18000cae8  call    free
0x18000caed  mov     qword ptr [rbx+50h], 0
0x18000caf5  mov     qword ptr [rbx+58h], 0
0x18000cafd  add     rsp, 20h
0x18000cb01  pop     rbx
0x18000cb02  retn
```
