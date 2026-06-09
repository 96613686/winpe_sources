# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18000e208`
- end: `0x18000e23c`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `52`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f320`

## callees

- `0x18000e0f0`
- `0x18000e208`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000e215`
- `KERNEL32!DeleteCriticalSection` at `0x18000e215`

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
  this[2].LockCount = 0;
  this[2].RecursionCount = 0;
}

```

## disassembly

```asm
0x18000e208  push    rbx
0x18000e20a  sub     rsp, 20h
0x18000e20e  mov     rbx, rcx
0x18000e211  add     rcx, 28h ; '('; lpCriticalSection
0x18000e215  call    cs:__imp_DeleteCriticalSection
0x18000e21b  mov     rcx, [rbx+50h]; Block
0x18000e21f  test    rcx, rcx
0x18000e222  jz      short loc_18000E22E
0x18000e224  call    free_0
0x18000e229  and     qword ptr [rbx+50h], 0
0x18000e22e  and     dword ptr [rbx+58h], 0
0x18000e232  and     dword ptr [rbx+5Ch], 0
0x18000e236  add     rsp, 20h
0x18000e23a  pop     rbx
0x18000e23b  retn
```
