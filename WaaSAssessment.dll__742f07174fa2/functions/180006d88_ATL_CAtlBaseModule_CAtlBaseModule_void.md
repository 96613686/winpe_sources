# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180006d88`
- end: `0x180006dc0`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180019f60`

## callees

- `0x180006d88`

## import_xrefs

- `msvcrt!free` at `0x180006da4`
- `msvcrt!free` at `0x180006da4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006d95`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006d95`

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
0x180006d88  push    rbx
0x180006d8a  sub     rsp, 20h
0x180006d8e  mov     rbx, rcx
0x180006d91  add     rcx, 28h ; '('; lpCriticalSection
0x180006d95  call    cs:__imp_DeleteCriticalSection
0x180006d9b  mov     rcx, [rbx+50h]; Block
0x180006d9f  test    rcx, rcx
0x180006da2  jz      short loc_180006DB2
0x180006da4  call    cs:__imp_free
0x180006daa  mov     qword ptr [rbx+50h], 0
0x180006db2  mov     qword ptr [rbx+58h], 0
0x180006dba  add     rsp, 20h
0x180006dbe  pop     rbx
0x180006dbf  retn
```
