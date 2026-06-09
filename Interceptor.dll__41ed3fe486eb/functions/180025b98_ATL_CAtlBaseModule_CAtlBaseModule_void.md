# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180025b98`
- end: `0x180025bcf`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002cb20`

## callees

- `0x180025b98`
- `0x18002a933`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180025ba5`
- `KERNEL32!DeleteCriticalSection` at `0x180025ba5`

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
0x180025b98  push    rbx
0x180025b9a  sub     rsp, 20h
0x180025b9e  mov     rbx, rcx
0x180025ba1  add     rcx, 28h ; '('; lpCriticalSection
0x180025ba5  call    cs:__imp_DeleteCriticalSection
0x180025bab  mov     rcx, [rbx+50h]; Block
0x180025baf  test    rcx, rcx
0x180025bb2  jz      short loc_180025BC1
0x180025bb4  call    free_0
0x180025bb9  mov     qword ptr [rbx+50h], 0
0x180025bc1  mov     qword ptr [rbx+58h], 0
0x180025bc9  add     rsp, 20h
0x180025bcd  pop     rbx
0x180025bce  retn
```
