# RtlSystemUtil::AutoCritSec::~AutoCritSec(void)

- ea: `0x18001f34c`
- end: `0x18001f385`
- name: `??1AutoCritSec@RtlSystemUtil@@QEAA@XZ`
- size: `57`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18009aff0`

## callees

- `0x18001f34c`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18001f35b`
- `ntdll!RtlDeleteCriticalSection` at `0x18001f35b`
- `ntdll!RtlRaiseStatus` at `0x18001f36d`
- `ntdll!RtlRaiseStatus` at `0x18001f36d`

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
0x18001f34c  push    rbx
0x18001f34e  sub     rsp, 20h
0x18001f352  cmp     byte ptr [rcx+28h], 0
0x18001f356  mov     rbx, rcx
0x18001f359  jz      short loc_18001F37E
0x18001f35b  call    cs:__imp_RtlDeleteCriticalSection
0x18001f362  nop     dword ptr [rax+rax+00h]
0x18001f367  test    eax, eax
0x18001f369  jns     short loc_18001F37A
0x18001f36b  mov     ecx, eax; Status
0x18001f36d  call    cs:__imp_RtlRaiseStatus
0x18001f374  nop     dword ptr [rax+rax+00h]
0x18001f379  int     3; Trap to Debugger
0x18001f37a  mov     byte ptr [rbx+28h], 0
0x18001f37e  add     rsp, 20h
0x18001f382  pop     rbx
0x18001f383  retn
```
