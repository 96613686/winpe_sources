# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180011de0`
- end: `0x180011e17`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012630`

## callees

- `0x180004134`
- `0x180011de0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011ded`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011ded`

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
0x180011de0  push    rbx
0x180011de2  sub     rsp, 20h
0x180011de6  mov     rbx, rcx
0x180011de9  add     rcx, 28h ; '('; lpCriticalSection
0x180011ded  call    cs:__imp_DeleteCriticalSection
0x180011df3  mov     rcx, [rbx+50h]; Block
0x180011df7  test    rcx, rcx
0x180011dfa  jz      short loc_180011E09
0x180011dfc  call    free
0x180011e01  mov     qword ptr [rbx+50h], 0
0x180011e09  mov     qword ptr [rbx+58h], 0
0x180011e11  add     rsp, 20h
0x180011e15  pop     rbx
0x180011e16  retn
```
