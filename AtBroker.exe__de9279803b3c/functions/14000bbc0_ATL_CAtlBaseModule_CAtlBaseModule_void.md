# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x14000bbc0`
- end: `0x14000bbf8`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140016290`

## callees

- `0x14000bbc0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000bbcd`
- `KERNEL32!DeleteCriticalSection` at `0x14000bbcd`
- `msvcrt!free` at `0x14000bbdc`
- `msvcrt!free` at `0x14000bbdc`

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
0x14000bbc0  push    rbx
0x14000bbc2  sub     rsp, 20h
0x14000bbc6  mov     rbx, rcx
0x14000bbc9  add     rcx, 28h ; '('; lpCriticalSection
0x14000bbcd  call    cs:__imp_DeleteCriticalSection
0x14000bbd3  mov     rcx, [rbx+50h]; Block
0x14000bbd7  test    rcx, rcx
0x14000bbda  jz      short loc_14000BBEA
0x14000bbdc  call    cs:__imp_free
0x14000bbe2  mov     qword ptr [rbx+50h], 0
0x14000bbea  mov     qword ptr [rbx+58h], 0
0x14000bbf2  add     rsp, 20h
0x14000bbf6  pop     rbx
0x14000bbf7  retn
```
