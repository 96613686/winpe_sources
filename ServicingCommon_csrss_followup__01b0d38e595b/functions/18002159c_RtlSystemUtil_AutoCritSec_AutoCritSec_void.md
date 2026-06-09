# RtlSystemUtil::AutoCritSec::~AutoCritSec(void)

- ea: `0x18002159c`
- end: `0x1800215d5`
- name: `??1AutoCritSec@RtlSystemUtil@@QEAA@XZ`
- size: `57`
- prototype: `void __fastcall(RtlSystemUtil::AutoCritSec *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180099160`

## callees

- `0x18002159c`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x1800215ab`
- `ntdll!RtlDeleteCriticalSection` at `0x1800215ab`
- `ntdll!RtlRaiseStatus` at `0x1800215bd`
- `ntdll!RtlRaiseStatus` at `0x1800215bd`

## pseudocode

```c
void __fastcall RtlSystemUtil::AutoCritSec::~AutoCritSec(struct _RTL_CRITICAL_SECTION *this)
{
  int v2; // eax

  if ( LOBYTE(this[1].DebugInfo) )
  {
    v2 = RtlDeleteCriticalSection(this);
    if ( v2 < 0 )
      RtlRaiseStatus(v2);
    LOBYTE(this[1].DebugInfo) = 0;
  }
}

```

## disassembly

```asm
0x18002159c  push    rbx
0x18002159e  sub     rsp, 20h
0x1800215a2  cmp     byte ptr [rcx+28h], 0
0x1800215a6  mov     rbx, rcx
0x1800215a9  jz      short loc_1800215CE
0x1800215ab  call    cs:__imp_RtlDeleteCriticalSection
0x1800215b2  nop     dword ptr [rax+rax+00h]
0x1800215b7  test    eax, eax
0x1800215b9  jns     short loc_1800215CA
0x1800215bb  mov     ecx, eax; Status
0x1800215bd  call    cs:__imp_RtlRaiseStatus
0x1800215c4  nop     dword ptr [rax+rax+00h]
0x1800215c9  int     3; Trap to Debugger
0x1800215ca  mov     byte ptr [rbx+28h], 0
0x1800215ce  add     rsp, 20h
0x1800215d2  pop     rbx
0x1800215d3  retn
```
