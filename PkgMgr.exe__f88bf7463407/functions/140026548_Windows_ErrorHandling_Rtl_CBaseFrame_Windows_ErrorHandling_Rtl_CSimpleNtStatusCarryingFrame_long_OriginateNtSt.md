# Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)

- ea: `0x140026548`
- end: `0x14002656e`
- name: `?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z`
- size: `38`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x140026574`
- `0x140026694`
- `0x140026784`
- `0x140026b2c`
- `0x140026c54`
- `0x1400272fc`
- `0x14002750c`
- `0x1400276a8`
- `0x140027858`
- `0x14002793c`

## callees

- `0x1400264e0`

## pseudocode

```c
__int64 __fastcall Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
        unsigned int *a1,
        __int64 a2,
        unsigned int a3)
{
  *a1 = a3;
  RtlReportErrorOrigination(a2, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab);
  return *a1;
}

```

## disassembly

```asm
0x140026548  push    rbx
0x14002654a  sub     rsp, 20h
0x14002654e  mov     rax, rdx
0x140026551  mov     [rcx], r8d
0x140026554  mov     rbx, rcx
0x140026557  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x14002655e  mov     rcx, rax
0x140026561  call    RtlReportErrorOrigination
0x140026566  mov     eax, [rbx]
0x140026568  add     rsp, 20h
0x14002656c  pop     rbx
0x14002656d  retn
```
