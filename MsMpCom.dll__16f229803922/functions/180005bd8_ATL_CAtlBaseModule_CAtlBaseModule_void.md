# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180005bd8`
- end: `0x180005c10`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009c90`

## callees

- `0x180005bd8`

## import_xrefs

- `msvcrt!free` at `0x180005bf4`
- `msvcrt!free` at `0x180005bf4`
- `KERNEL32!DeleteCriticalSection` at `0x180005be5`
- `KERNEL32!DeleteCriticalSection` at `0x180005be5`

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
0x180005bd8  push    rbx
0x180005bda  sub     rsp, 20h
0x180005bde  mov     rbx, rcx
0x180005be1  add     rcx, 28h ; '('; lpCriticalSection
0x180005be5  call    cs:__imp_DeleteCriticalSection
0x180005beb  mov     rcx, [rbx+50h]; Block
0x180005bef  test    rcx, rcx
0x180005bf2  jz      short loc_180005C02
0x180005bf4  call    cs:__imp_free
0x180005bfa  mov     qword ptr [rbx+50h], 0
0x180005c02  mov     qword ptr [rbx+58h], 0
0x180005c0a  add     rsp, 20h
0x180005c0e  pop     rbx
0x180005c0f  retn
```
