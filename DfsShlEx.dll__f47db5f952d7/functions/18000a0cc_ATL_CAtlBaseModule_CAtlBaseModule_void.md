# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18000a0cc`
- end: `0x18000a104`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b2e0`

## callees

- `0x18000a0cc`

## import_xrefs

- `msvcrt!free` at `0x18000a0e8`
- `msvcrt!free` at `0x18000a0e8`
- `KERNEL32!DeleteCriticalSection` at `0x18000a0d9`
- `KERNEL32!DeleteCriticalSection` at `0x18000a0d9`

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
0x18000a0cc  push    rbx
0x18000a0ce  sub     rsp, 20h
0x18000a0d2  mov     rbx, rcx
0x18000a0d5  add     rcx, 28h ; '('; lpCriticalSection
0x18000a0d9  call    cs:__imp_DeleteCriticalSection
0x18000a0df  mov     rcx, [rbx+50h]; Block
0x18000a0e3  test    rcx, rcx
0x18000a0e6  jz      short loc_18000A0F6
0x18000a0e8  call    cs:__imp_free
0x18000a0ee  mov     qword ptr [rbx+50h], 0
0x18000a0f6  mov     qword ptr [rbx+58h], 0
0x18000a0fe  add     rsp, 20h
0x18000a102  pop     rbx
0x18000a103  retn
```
