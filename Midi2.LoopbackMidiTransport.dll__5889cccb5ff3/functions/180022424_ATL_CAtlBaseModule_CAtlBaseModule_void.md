# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180022424`
- end: `0x18002245b`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180031ed0`

## callees

- `0x180004fc4`
- `0x180022424`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022431`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022431`

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
0x180022424  push    rbx
0x180022426  sub     rsp, 20h
0x18002242a  mov     rbx, rcx
0x18002242d  add     rcx, 28h ; '('; lpCriticalSection
0x180022431  call    cs:__imp_DeleteCriticalSection
0x180022437  mov     rcx, [rbx+50h]; Block
0x18002243b  test    rcx, rcx
0x18002243e  jz      short loc_18002244D
0x180022440  call    free
0x180022445  mov     qword ptr [rbx+50h], 0
0x18002244d  mov     qword ptr [rbx+58h], 0
0x180022455  add     rsp, 20h
0x180022459  pop     rbx
0x18002245a  retn
```
