# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18000b1d0`
- end: `0x18000b207`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b7c0`

## callees

- `0x1800028a4`
- `0x18000b1d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b1dd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b1dd`

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
0x18000b1d0  push    rbx
0x18000b1d2  sub     rsp, 20h
0x18000b1d6  mov     rbx, rcx
0x18000b1d9  add     rcx, 28h ; '('; lpCriticalSection
0x18000b1dd  call    cs:__imp_DeleteCriticalSection
0x18000b1e3  mov     rcx, [rbx+50h]; Block
0x18000b1e7  test    rcx, rcx
0x18000b1ea  jz      short loc_18000B1F9
0x18000b1ec  call    free
0x18000b1f1  mov     qword ptr [rbx+50h], 0
0x18000b1f9  mov     qword ptr [rbx+58h], 0
0x18000b201  add     rsp, 20h
0x18000b205  pop     rbx
0x18000b206  retn
```
