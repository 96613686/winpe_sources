# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180036e28`
- end: `0x180036e66`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `62`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800386d0`

## callees

- `0x1800025fc`
- `0x180036e28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036e35`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036e35`

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
0x180036e28  push    rbx
0x180036e2a  sub     rsp, 20h
0x180036e2e  mov     rbx, rcx
0x180036e31  add     rcx, 28h ; '('; lpCriticalSection
0x180036e35  call    cs:__imp_DeleteCriticalSection
0x180036e3c  nop     dword ptr [rax+rax+00h]
0x180036e41  mov     rcx, [rbx+50h]; Block
0x180036e45  test    rcx, rcx
0x180036e48  jz      short loc_180036E57
0x180036e4a  call    free
0x180036e4f  mov     qword ptr [rbx+50h], 0
0x180036e57  mov     qword ptr [rbx+58h], 0
0x180036e5f  add     rsp, 20h
0x180036e63  pop     rbx
0x180036e64  retn
```
