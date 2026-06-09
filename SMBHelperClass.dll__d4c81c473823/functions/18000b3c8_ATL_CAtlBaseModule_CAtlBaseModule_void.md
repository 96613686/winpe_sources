# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18000b3c8`
- end: `0x18000b400`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011570`

## callees

- `0x18000b3c8`

## import_xrefs

- `msvcrt!free` at `0x18000b3e4`
- `msvcrt!free` at `0x18000b3e4`
- `KERNEL32!DeleteCriticalSection` at `0x18000b3d5`
- `KERNEL32!DeleteCriticalSection` at `0x18000b3d5`

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
0x18000b3c8  push    rbx
0x18000b3ca  sub     rsp, 20h
0x18000b3ce  mov     rbx, rcx
0x18000b3d1  add     rcx, 28h ; '('; lpCriticalSection
0x18000b3d5  call    cs:__imp_DeleteCriticalSection
0x18000b3db  mov     rcx, [rbx+50h]; Block
0x18000b3df  test    rcx, rcx
0x18000b3e2  jz      short loc_18000B3F2
0x18000b3e4  call    cs:__imp_free
0x18000b3ea  mov     qword ptr [rbx+50h], 0
0x18000b3f2  mov     qword ptr [rbx+58h], 0
0x18000b3fa  add     rsp, 20h
0x18000b3fe  pop     rbx
0x18000b3ff  retn
```
