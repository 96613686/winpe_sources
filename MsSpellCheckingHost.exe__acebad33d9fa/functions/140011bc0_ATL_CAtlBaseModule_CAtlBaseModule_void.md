# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x140011bc0`
- end: `0x140011bf8`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140012820`

## callees

- `0x140011bc0`

## import_xrefs

- `msvcrt!free` at `0x140011bdc`
- `msvcrt!free` at `0x140011bdc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140011bcd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140011bcd`

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
0x140011bc0  push    rbx
0x140011bc2  sub     rsp, 20h
0x140011bc6  mov     rbx, rcx
0x140011bc9  add     rcx, 28h ; '('; lpCriticalSection
0x140011bcd  call    cs:__imp_DeleteCriticalSection
0x140011bd3  mov     rcx, [rbx+50h]; Block
0x140011bd7  test    rcx, rcx
0x140011bda  jz      short loc_140011BEA
0x140011bdc  call    cs:__imp_free
0x140011be2  mov     qword ptr [rbx+50h], 0
0x140011bea  mov     qword ptr [rbx+58h], 0
0x140011bf2  add     rsp, 20h
0x140011bf6  pop     rbx
0x140011bf7  retn
```
