# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180005e30`
- end: `0x180005e68`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800063e0`

## callees

- `0x180005e30`

## import_xrefs

- `msvcrt!free` at `0x180005e4c`
- `msvcrt!free` at `0x180005e4c`
- `KERNEL32!DeleteCriticalSection` at `0x180005e3d`
- `KERNEL32!DeleteCriticalSection` at `0x180005e3d`

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
0x180005e30  push    rbx
0x180005e32  sub     rsp, 20h
0x180005e36  mov     rbx, rcx
0x180005e39  add     rcx, 28h ; '('; lpCriticalSection
0x180005e3d  call    cs:__imp_DeleteCriticalSection
0x180005e43  mov     rcx, [rbx+50h]; Block
0x180005e47  test    rcx, rcx
0x180005e4a  jz      short loc_180005E5A
0x180005e4c  call    cs:__imp_free
0x180005e52  mov     qword ptr [rbx+50h], 0
0x180005e5a  mov     qword ptr [rbx+58h], 0
0x180005e62  add     rsp, 20h
0x180005e66  pop     rbx
0x180005e67  retn
```
