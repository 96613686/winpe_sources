# WPP_SF_sq

- ea: `0x18002b6bc`
- end: `0x18002b709`
- name: `WPP_SF_sq`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, service_task`

## callers

- `0x180025bbc`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18002b6fe`
- `ntdll!EtwTraceMessage` at `0x18002b6fe`

## string_xrefs

- `0x18002b6e2`: `PENSERVICE_CServiceModule::ServiceMainBegin`

## pseudocode

```c
__int64 __fastcall WPP_SF_sq(__int64 a1)
{
  return EtwTraceMessage(a1, 43, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids);
}

```

## disassembly

```asm
0x18002b6bc  mov     r11, rsp
0x18002b6bf  sub     rsp, 58h
0x18002b6c3  mov     qword ptr [r11-18h], 0
0x18002b6cb  lea     rax, [r11+28h]
0x18002b6cf  mov     qword ptr [r11-20h], 8
0x18002b6d7  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18002b6de  mov     [r11-28h], rax
0x18002b6e2  lea     rax, aPenserviceCser_12; "PENSERVICE_CServiceModule::ServiceMainB"...
0x18002b6e9  movzx   r9d, dx
0x18002b6ed  mov     edx, 2Bh ; '+'
0x18002b6f2  mov     qword ptr [r11-30h], 2Ch ; ','
0x18002b6fa  mov     [r11-38h], rax
0x18002b6fe  call    cs:__imp_EtwTraceMessage
0x18002b704  add     rsp, 58h
0x18002b708  retn
```
