# RtlSystemUtil::AutoCritSec::~AutoCritSec(void)

- ea: `0x140006168`
- end: `0x140006194`
- name: `??1AutoCritSec@RtlSystemUtil@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140006240`

## callees

- `0x140006168`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x140006183`
- `ntdll!RtlRaiseStatus` at `0x140006183`
- `ntdll!RtlDeleteCriticalSection` at `0x140006177`
- `ntdll!RtlDeleteCriticalSection` at `0x140006177`

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
0x140006168  push    rbx
0x14000616a  sub     rsp, 20h
0x14000616e  cmp     byte ptr [rcx+28h], 0
0x140006172  mov     rbx, rcx
0x140006175  jz      short loc_14000618E
0x140006177  call    cs:__imp_RtlDeleteCriticalSection
0x14000617d  test    eax, eax
0x14000617f  jns     short loc_14000618A
0x140006181  mov     ecx, eax; Status
0x140006183  call    cs:__imp_RtlRaiseStatus
0x140006189  int     3; Trap to Debugger
0x14000618a  mov     byte ptr [rbx+28h], 0
0x14000618e  add     rsp, 20h
0x140006192  pop     rbx
0x140006193  retn
```
