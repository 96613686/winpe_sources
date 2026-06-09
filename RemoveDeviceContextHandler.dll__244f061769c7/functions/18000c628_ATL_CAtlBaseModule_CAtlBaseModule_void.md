# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18000c628`
- end: `0x18000c660`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cff0`

## callees

- `0x18000c628`

## import_xrefs

- `msvcrt!free` at `0x18000c644`
- `msvcrt!free` at `0x18000c644`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c635`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c635`

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
0x18000c628  push    rbx
0x18000c62a  sub     rsp, 20h
0x18000c62e  mov     rbx, rcx
0x18000c631  add     rcx, 28h ; '('; lpCriticalSection
0x18000c635  call    cs:__imp_DeleteCriticalSection
0x18000c63b  mov     rcx, [rbx+50h]; Block
0x18000c63f  test    rcx, rcx
0x18000c642  jz      short loc_18000C652
0x18000c644  call    cs:__imp_free
0x18000c64a  mov     qword ptr [rbx+50h], 0
0x18000c652  mov     qword ptr [rbx+58h], 0
0x18000c65a  add     rsp, 20h
0x18000c65e  pop     rbx
0x18000c65f  retn
```
