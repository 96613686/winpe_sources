# Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)

- ea: `0x140009784`
- end: `0x1400097b4`
- name: `?OriginateNtStatus@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z`
- size: `48`
- prototype: `__int64 __fastcall(unsigned int *, __int64, NTSTATUS)`
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140008d38`
- `0x140008ef4`
- `0x140009c48`
- `0x14000d910`
- `0x14000dac8`
- `0x14000dbc8`
- `0x14000dd94`
- `0x14001093c`
- `0x140010acc`
- `0x14001219c`
- `0x1400156ac`
- `0x14001583c`
- `0x1400159e8`
- `0x140015b78`
- `0x140015d08`

## callees

- `0x140006b54`
- `0x140025924`

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
0x140009784  mov     [rsp+arg_0], rbx
0x140009789  push    rdi
0x14000978a  sub     rsp, 20h
0x14000978e  mov     rdi, rcx
0x140009791  mov     rbx, rdx
0x140009794  mov     ecx, r8d; Status
0x140009797  call    ConvertNtStatusToHResult
0x14000979c  mov     r8d, eax
0x14000979f  mov     rdx, rbx
0x1400097a2  mov     rcx, rdi
0x1400097a5  mov     rbx, [rsp+28h+arg_0]
0x1400097aa  add     rsp, 20h
0x1400097ae  pop     rdi
0x1400097af  jmp     ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
```
