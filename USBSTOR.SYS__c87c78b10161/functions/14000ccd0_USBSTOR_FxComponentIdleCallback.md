# USBSTOR_FxComponentIdleCallback

- ea: `0x14000ccd0`
- end: `0x14000cced`
- name: `USBSTOR_FxComponentIdleCallback`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!PoFxCompleteIdleCondition` at `0x14000ccdb`
- `ntoskrnl!PoFxCompleteIdleCondition` at `0x14000ccdb`

## pseudocode

```c
__int64 __fastcall USBSTOR_FxComponentIdleCallback(__int64 a1)
{
  return PoFxCompleteIdleCondition(*(_QWORD *)(a1 + 1968));
}

```

## disassembly

```asm
0x14000ccd0  sub     rsp, 28h
0x14000ccd4  mov     rcx, [rcx+7B0h]
0x14000ccdb  call    cs:__imp_PoFxCompleteIdleCondition
0x14000cce2  nop     dword ptr [rax+rax+00h]
0x14000cce7  add     rsp, 28h
0x14000cceb  retn
```
