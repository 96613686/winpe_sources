# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180014fe0`
- end: `0x180015017`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180017df0`

## callees

- `0x180003254`
- `0x180014fe0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014fed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014fed`

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
0x180014fe0  push    rbx
0x180014fe2  sub     rsp, 20h
0x180014fe6  mov     rbx, rcx
0x180014fe9  add     rcx, 28h ; '('; lpCriticalSection
0x180014fed  call    cs:__imp_DeleteCriticalSection
0x180014ff3  mov     rcx, [rbx+50h]; Block
0x180014ff7  test    rcx, rcx
0x180014ffa  jz      short loc_180015009
0x180014ffc  call    free
0x180015001  mov     qword ptr [rbx+50h], 0
0x180015009  mov     qword ptr [rbx+58h], 0
0x180015011  add     rsp, 20h
0x180015015  pop     rbx
0x180015016  retn
```
