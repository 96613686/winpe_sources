# Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)

- ea: `0x1400183c0`
- end: `0x1400183f0`
- name: `?OriginateNtStatus@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z`
- size: `48`
- prototype: `__int64 __fastcall(unsigned int *, __int64, NTSTATUS)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140016a40`
- `0x140016bfc`
- `0x140016ce8`
- `0x140016de8`
- `0x140016fb4`
- `0x140017144`
- `0x140019a00`
- `0x14001b2ac`
- `0x14001b43c`
- `0x14001b5e8`
- `0x14001b778`
- `0x14001b908`
- `0x1400228d8`
- `0x1400246c0`

## callees

- `0x140008138`
- `0x140025d98`

## pseudocode

```c
__int64 __fastcall Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(
        unsigned int *a1,
        __int64 a2,
        NTSTATUS a3)
{
  unsigned int v5; // eax

  v5 = ConvertNtStatusToHResult(a3);
  return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
           a1,
           a2,
           v5);
}

```

## disassembly

```asm
0x1400183c0  mov     [rsp+arg_0], rbx
0x1400183c5  push    rdi
0x1400183c6  sub     rsp, 20h
0x1400183ca  mov     rdi, rcx
0x1400183cd  mov     rbx, rdx
0x1400183d0  mov     ecx, r8d; Status
0x1400183d3  call    ConvertNtStatusToHResult
0x1400183d8  mov     r8d, eax
0x1400183db  mov     rdx, rbx
0x1400183de  mov     rcx, rdi
0x1400183e1  mov     rbx, [rsp+28h+arg_0]
0x1400183e6  add     rsp, 20h
0x1400183ea  pop     rdi
0x1400183eb  jmp     ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
```
