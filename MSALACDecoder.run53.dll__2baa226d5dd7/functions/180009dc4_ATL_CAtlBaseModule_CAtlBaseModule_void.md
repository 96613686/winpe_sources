# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180009dc4`
- end: `0x180009dfb`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a270`

## callees

- `0x180001e94`
- `0x180009dc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009dd1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009dd1`

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
0x180009dc4  push    rbx
0x180009dc6  sub     rsp, 20h
0x180009dca  mov     rbx, rcx
0x180009dcd  add     rcx, 28h ; '('; lpCriticalSection
0x180009dd1  call    cs:__imp_DeleteCriticalSection
0x180009dd7  mov     rcx, [rbx+50h]; Block
0x180009ddb  test    rcx, rcx
0x180009dde  jz      short loc_180009DED
0x180009de0  call    free
0x180009de5  mov     qword ptr [rbx+50h], 0
0x180009ded  mov     qword ptr [rbx+58h], 0
0x180009df5  add     rsp, 20h
0x180009df9  pop     rbx
0x180009dfa  retn
```
