# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18002ccf0`
- end: `0x18002cd27`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800343b0`

## callees

- `0x180002624`
- `0x18002ccf0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002ccfd`
- `KERNEL32!DeleteCriticalSection` at `0x18002ccfd`

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
0x18002ccf0  push    rbx
0x18002ccf2  sub     rsp, 20h
0x18002ccf6  mov     rbx, rcx
0x18002ccf9  add     rcx, 28h ; '('; lpCriticalSection
0x18002ccfd  call    cs:__imp_DeleteCriticalSection
0x18002cd03  mov     rcx, [rbx+50h]; Block
0x18002cd07  test    rcx, rcx
0x18002cd0a  jz      short loc_18002CD19
0x18002cd0c  call    free
0x18002cd11  mov     qword ptr [rbx+50h], 0
0x18002cd19  mov     qword ptr [rbx+58h], 0
0x18002cd21  add     rsp, 20h
0x18002cd25  pop     rbx
0x18002cd26  retn
```
