# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18001ad58`
- end: `0x18001ad8c`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `52`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180025460`

## callees

- `0x18000bb08`
- `0x18001ad58`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001ad65`
- `KERNEL32!DeleteCriticalSection` at `0x18001ad65`

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
  this[2].LockCount = 0;
  this[2].RecursionCount = 0;
}

```

## disassembly

```asm
0x18001ad58  push    rbx
0x18001ad5a  sub     rsp, 20h
0x18001ad5e  mov     rbx, rcx
0x18001ad61  add     rcx, 28h ; '('; lpCriticalSection
0x18001ad65  call    cs:__imp_DeleteCriticalSection
0x18001ad6b  mov     rcx, [rbx+50h]; Block
0x18001ad6f  test    rcx, rcx
0x18001ad72  jz      short loc_18001AD7E
0x18001ad74  call    free
0x18001ad79  and     qword ptr [rbx+50h], 0
0x18001ad7e  and     dword ptr [rbx+58h], 0
0x18001ad82  and     dword ptr [rbx+5Ch], 0
0x18001ad86  add     rsp, 20h
0x18001ad8a  pop     rbx
0x18001ad8b  retn
```
