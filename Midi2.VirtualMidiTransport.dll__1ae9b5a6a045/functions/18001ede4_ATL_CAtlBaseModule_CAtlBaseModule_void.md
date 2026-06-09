# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18001ede4`
- end: `0x18001ee1b`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180020e20`

## callees

- `0x180004664`
- `0x18001ede4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001edf1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001edf1`

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
0x18001ede4  push    rbx
0x18001ede6  sub     rsp, 20h
0x18001edea  mov     rbx, rcx
0x18001eded  add     rcx, 28h ; '('; lpCriticalSection
0x18001edf1  call    cs:__imp_DeleteCriticalSection
0x18001edf7  mov     rcx, [rbx+50h]; Block
0x18001edfb  test    rcx, rcx
0x18001edfe  jz      short loc_18001EE0D
0x18001ee00  call    free
0x18001ee05  mov     qword ptr [rbx+50h], 0
0x18001ee0d  mov     qword ptr [rbx+58h], 0
0x18001ee15  add     rsp, 20h
0x18001ee19  pop     rbx
0x18001ee1a  retn
```
