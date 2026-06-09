# Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)

- ea: `0x140008138`
- end: `0x140008154`
- name: `?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z`
- size: `28`
- prototype: `__int64 __fastcall(unsigned int *, __int64, unsigned int)`
- caller_count: `21`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140007210`
- `0x140016a40`
- `0x140016de8`
- `0x140016fb4`
- `0x140017144`
- `0x1400183c0`
- `0x140019a00`
- `0x14001b2ac`
- `0x14001b43c`
- `0x14001b5e8`
- `0x14001b778`
- `0x14001b908`
- `0x140025c08`
- `0x140025cc0`
- `0x14002627c`
- `0x140026498`
- `0x140026634`
- `0x1400267e4`
- `0x1400268c8`
- `0x1400269ac`
- `0x140026b00`

## callees

- `0x140025ba0`

## pseudocode

```c
__int64 __fastcall Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
        unsigned int *a1,
        __int64 a2,
        unsigned int a3)
{
  *a1 = a3;
  RtlReportErrorOrigination(a2);
  return *a1;
}

```

## disassembly

```asm
0x140008138  push    rbx
0x14000813a  sub     rsp, 20h
0x14000813e  mov     rbx, rcx
0x140008141  mov     [rcx], r8d
0x140008144  mov     rcx, rdx
0x140008147  call    RtlReportErrorOrigination
0x14000814c  mov     eax, [rbx]
0x14000814e  add     rsp, 20h
0x140008152  pop     rbx
0x140008153  retn
```
