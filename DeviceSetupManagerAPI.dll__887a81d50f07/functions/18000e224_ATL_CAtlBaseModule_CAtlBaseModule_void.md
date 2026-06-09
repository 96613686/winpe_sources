# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18000e224`
- end: `0x18000e25b`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e970`

## callees

- `0x180002534`
- `0x18000e224`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e231`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e231`

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
0x18000e224  push    rbx
0x18000e226  sub     rsp, 20h
0x18000e22a  mov     rbx, rcx
0x18000e22d  add     rcx, 28h ; '('; lpCriticalSection
0x18000e231  call    cs:__imp_DeleteCriticalSection
0x18000e237  mov     rcx, [rbx+50h]; Block
0x18000e23b  test    rcx, rcx
0x18000e23e  jz      short loc_18000E24D
0x18000e240  call    free
0x18000e245  mov     qword ptr [rbx+50h], 0
0x18000e24d  mov     qword ptr [rbx+58h], 0
0x18000e255  add     rsp, 20h
0x18000e259  pop     rbx
0x18000e25a  retn
```
