# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x140004e04`
- end: `0x140004e3c`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140040740`

## callees

- `0x140004e04`

## import_xrefs

- `msvcrt!free` at `0x140004e20`
- `msvcrt!free` at `0x140004e20`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140004e11`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140004e11`

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
0x140004e04  push    rbx
0x140004e06  sub     rsp, 20h
0x140004e0a  mov     rbx, rcx
0x140004e0d  add     rcx, 28h ; '('; lpCriticalSection
0x140004e11  call    cs:__imp_DeleteCriticalSection
0x140004e17  mov     rcx, [rbx+50h]; Block
0x140004e1b  test    rcx, rcx
0x140004e1e  jz      short loc_140004E2E
0x140004e20  call    cs:__imp_free
0x140004e26  mov     qword ptr [rbx+50h], 0
0x140004e2e  mov     qword ptr [rbx+58h], 0
0x140004e36  add     rsp, 20h
0x140004e3a  pop     rbx
0x140004e3b  retn
```
