# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x140014a34`
- end: `0x140014a6b`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140015ce0`

## callees

- `0x140014a34`
- `0x140014afd`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140014a41`
- `KERNEL32!DeleteCriticalSection` at `0x140014a41`

## pseudocode

```c
void __fastcall ATL::CAtlBaseModule::~CAtlBaseModule(struct _RTL_CRITICAL_SECTION *this)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx

  DeleteCriticalSection(this + 1);
  DebugInfo = this[2].DebugInfo;
  if ( DebugInfo )
  {
    free_0(DebugInfo);
    this[2].DebugInfo = 0;
  }
  *(_QWORD *)&this[2].LockCount = 0;
}

```

## disassembly

```asm
0x140014a34  push    rbx
0x140014a36  sub     rsp, 20h
0x140014a3a  mov     rbx, rcx
0x140014a3d  add     rcx, 28h ; '('; lpCriticalSection
0x140014a41  call    cs:__imp_DeleteCriticalSection
0x140014a47  mov     rcx, [rbx+50h]; Block
0x140014a4b  test    rcx, rcx
0x140014a4e  jz      short loc_140014A5D
0x140014a50  call    free_0
0x140014a55  mov     qword ptr [rbx+50h], 0
0x140014a5d  mov     qword ptr [rbx+58h], 0
0x140014a65  add     rsp, 20h
0x140014a69  pop     rbx
0x140014a6a  retn
```
