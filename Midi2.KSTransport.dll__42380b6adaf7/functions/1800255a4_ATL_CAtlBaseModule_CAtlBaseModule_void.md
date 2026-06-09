# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x1800255a4`
- end: `0x1800255db`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180040910`

## callees

- `0x180005224`
- `0x1800255a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800255b1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800255b1`

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
0x1800255a4  push    rbx
0x1800255a6  sub     rsp, 20h
0x1800255aa  mov     rbx, rcx
0x1800255ad  add     rcx, 28h ; '('; lpCriticalSection
0x1800255b1  call    cs:__imp_DeleteCriticalSection
0x1800255b7  mov     rcx, [rbx+50h]; Block
0x1800255bb  test    rcx, rcx
0x1800255be  jz      short loc_1800255CD
0x1800255c0  call    free
0x1800255c5  mov     qword ptr [rbx+50h], 0
0x1800255cd  mov     qword ptr [rbx+58h], 0
0x1800255d5  add     rsp, 20h
0x1800255d9  pop     rbx
0x1800255da  retn
```
