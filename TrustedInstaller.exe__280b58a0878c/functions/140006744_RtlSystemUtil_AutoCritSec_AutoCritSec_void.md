# RtlSystemUtil::AutoCritSec::~AutoCritSec(void)

- ea: `0x140006744`
- end: `0x140006770`
- name: `??1AutoCritSec@RtlSystemUtil@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000692c`

## callees

- `0x140006744`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x140006753`
- `ntdll!RtlDeleteCriticalSection` at `0x140006753`
- `ntdll!RtlRaiseStatus` at `0x14000675f`
- `ntdll!RtlRaiseStatus` at `0x14000675f`

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
0x140006744  push    rbx
0x140006746  sub     rsp, 20h
0x14000674a  cmp     byte ptr [rcx+28h], 0
0x14000674e  mov     rbx, rcx
0x140006751  jz      short loc_14000676A
0x140006753  call    cs:__imp_RtlDeleteCriticalSection
0x140006759  test    eax, eax
0x14000675b  jns     short loc_140006766
0x14000675d  mov     ecx, eax; Status
0x14000675f  call    cs:__imp_RtlRaiseStatus
0x140006765  int     3; Trap to Debugger
0x140006766  mov     byte ptr [rbx+28h], 0
0x14000676a  add     rsp, 20h
0x14000676e  pop     rbx
0x14000676f  retn
```
