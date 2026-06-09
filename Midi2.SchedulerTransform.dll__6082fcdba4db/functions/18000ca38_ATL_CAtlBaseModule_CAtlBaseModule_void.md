# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18000ca38`
- end: `0x18000ca6f`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d4f0`

## callees

- `0x180002a44`
- `0x18000ca38`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ca45`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ca45`

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
0x18000ca38  push    rbx
0x18000ca3a  sub     rsp, 20h
0x18000ca3e  mov     rbx, rcx
0x18000ca41  add     rcx, 28h ; '('; lpCriticalSection
0x18000ca45  call    cs:__imp_DeleteCriticalSection
0x18000ca4b  mov     rcx, [rbx+50h]; Block
0x18000ca4f  test    rcx, rcx
0x18000ca52  jz      short loc_18000CA61
0x18000ca54  call    free
0x18000ca59  mov     qword ptr [rbx+50h], 0
0x18000ca61  mov     qword ptr [rbx+58h], 0
0x18000ca69  add     rsp, 20h
0x18000ca6d  pop     rbx
0x18000ca6e  retn
```
