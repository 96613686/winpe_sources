# Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)

- ea: `0x1400074c0`
- end: `0x1400074e6`
- name: `?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z`
- size: `38`
- prototype: ``
- caller_count: `16`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400067bc`
- `0x140006984`
- `0x140006c50`
- `0x1400074ec`
- `0x14000a714`
- `0x14000a8ac`
- `0x140012400`
- `0x140016870`
- `0x140024c94`
- `0x1400251e4`
- `0x140025cb4`
- `0x140025d80`
- `0x140025e0c`
- `0x140025fb0`
- `0x140027a20`
- `0x140027b78`

## callees

- `0x1400264e0`

## pseudocode

```c
__int64 __fastcall Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
        unsigned int *a1,
        __int64 a2,
        unsigned int a3)
{
  *a1 = a3;
  RtlReportErrorOrigination(a2, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627);
  return *a1;
}

```

## disassembly

```asm
0x1400074c0  push    rbx
0x1400074c2  sub     rsp, 20h
0x1400074c6  mov     rax, rdx
0x1400074c9  mov     [rcx], r8d
0x1400074cc  mov     rbx, rcx
0x1400074cf  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x1400074d6  mov     rcx, rax
0x1400074d9  call    RtlReportErrorOrigination
0x1400074de  mov     eax, [rbx]
0x1400074e0  add     rsp, 20h
0x1400074e4  pop     rbx
0x1400074e5  retn
```
