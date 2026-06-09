# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18000b284`
- end: `0x18000b2bc`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c290`

## callees

- `0x18000b284`

## import_xrefs

- `msvcrt!free` at `0x18000b2a0`
- `msvcrt!free` at `0x18000b2a0`
- `KERNEL32!DeleteCriticalSection` at `0x18000b291`
- `KERNEL32!DeleteCriticalSection` at `0x18000b291`

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
0x18000b284  push    rbx
0x18000b286  sub     rsp, 20h
0x18000b28a  mov     rbx, rcx
0x18000b28d  add     rcx, 28h ; '('; lpCriticalSection
0x18000b291  call    cs:__imp_DeleteCriticalSection
0x18000b297  mov     rcx, [rbx+50h]; Block
0x18000b29b  test    rcx, rcx
0x18000b29e  jz      short loc_18000B2AE
0x18000b2a0  call    cs:__imp_free
0x18000b2a6  mov     qword ptr [rbx+50h], 0
0x18000b2ae  mov     qword ptr [rbx+58h], 0
0x18000b2b6  add     rsp, 20h
0x18000b2ba  pop     rbx
0x18000b2bb  retn
```
