# SetSystemRadioStateTimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x18001fd90`
- end: `0x18001fdac`
- name: `?SetSystemRadioStateTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `28`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001fc08`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x18001fd99`
- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x18001fd99`

## pseudocode

```c
void __fastcall SetSystemRadioStateTimerCallback(
        PTP_CALLBACK_INSTANCE Instance,
        struct RadioManager *Context,
        PTP_TIMER Timer)
{
  DisassociateCurrentThreadFromCallback(Instance);
  ReleaseSingleton(Context);
}

```

## disassembly

```asm
0x18001fd90  push    rbx
0x18001fd92  sub     rsp, 20h
0x18001fd96  mov     rbx, rdx
0x18001fd99  call    cs:__imp_DisassociateCurrentThreadFromCallback
0x18001fd9f  mov     rcx, rbx; struct RadioManager *
0x18001fda2  add     rsp, 20h
0x18001fda6  pop     rbx
0x18001fda7  jmp     ?ReleaseSingleton@@YAXPEAVRadioManager@@@Z; ReleaseSingleton(RadioManager *)
```
