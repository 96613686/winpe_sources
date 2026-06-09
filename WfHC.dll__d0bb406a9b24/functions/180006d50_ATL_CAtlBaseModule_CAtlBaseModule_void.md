# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180006d50`
- end: `0x180006d88`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cf60`

## callees

- `0x180006d50`

## import_xrefs

- `msvcrt!free` at `0x180006d6c`
- `msvcrt!free` at `0x180006d6c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006d5d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006d5d`

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
0x180006d50  push    rbx
0x180006d52  sub     rsp, 20h
0x180006d56  mov     rbx, rcx
0x180006d59  add     rcx, 28h ; '('; lpCriticalSection
0x180006d5d  call    cs:__imp_DeleteCriticalSection
0x180006d63  mov     rcx, [rbx+50h]; Block
0x180006d67  test    rcx, rcx
0x180006d6a  jz      short loc_180006D7A
0x180006d6c  call    cs:__imp_free
0x180006d72  mov     qword ptr [rbx+50h], 0
0x180006d7a  mov     qword ptr [rbx+58h], 0
0x180006d82  add     rsp, 20h
0x180006d86  pop     rbx
0x180006d87  retn
```
