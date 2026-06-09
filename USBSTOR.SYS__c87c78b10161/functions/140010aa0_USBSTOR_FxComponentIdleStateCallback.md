# USBSTOR_FxComponentIdleStateCallback

- ea: `0x140010aa0`
- end: `0x140010abd`
- name: `USBSTOR_FxComponentIdleStateCallback`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!PoFxCompleteIdleState` at `0x140010aab`
- `ntoskrnl!PoFxCompleteIdleState` at `0x140010aab`

## pseudocode

```c
__int64 __fastcall USBSTOR_FxComponentIdleStateCallback(__int64 a1)
{
  return PoFxCompleteIdleState(*(_QWORD *)(a1 + 1968));
}

```

## disassembly

```asm
0x140010aa0  sub     rsp, 28h
0x140010aa4  mov     rcx, [rcx+7B0h]
0x140010aab  call    cs:__imp_PoFxCompleteIdleState
0x140010ab2  nop     dword ptr [rax+rax+00h]
0x140010ab7  add     rsp, 28h
0x140010abb  retn
```
