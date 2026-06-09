# Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)

- ea: `0x140006b54`
- end: `0x140006b70`
- name: `?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z`
- size: `28`
- prototype: `__int64 __fastcall(unsigned int *, __int64, unsigned int)`
- caller_count: `25`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140006810`
- `0x140008d38`
- `0x140008ef4`
- `0x140009784`
- `0x14000d910`
- `0x14000dbc8`
- `0x14000dd94`
- `0x14001093c`
- `0x140010acc`
- `0x1400156ac`
- `0x14001583c`
- `0x1400159e8`
- `0x140015b78`
- `0x140015d08`
- `0x140025fd8`
- `0x14002606c`
- `0x140026488`
- `0x1400266a4`
- `0x140026840`
- `0x1400269f0`
- `0x140026ad4`
- `0x140026bb8`
- `0x140026c70`
- `0x140026dc4`
- `0x14002ab0c`

## callees

- `0x140025d54`

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
0x140006b54  push    rbx
0x140006b56  sub     rsp, 20h
0x140006b5a  mov     rbx, rcx
0x140006b5d  mov     [rcx], r8d
0x140006b60  mov     rcx, rdx
0x140006b63  call    RtlReportErrorOrigination
0x140006b68  mov     eax, [rbx]
0x140006b6a  add     rsp, 20h
0x140006b6e  pop     rbx
0x140006b6f  retn
```
