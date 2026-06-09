# WnfHelper_PublishUsbXhciAudioOffloadState

- ea: `0x140081394`
- end: `0x1400813d0`
- name: `WnfHelper_PublishUsbXhciAudioOffloadState`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1400409c0`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400813be`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400813be`

## pseudocode

```c
__int64 __fastcall WnfHelper_PublishUsbXhciAudioOffloadState(char a1)
{
  char v2; // [rsp+50h] [rbp+8h] BYREF

  v2 = a1;
  return ZwUpdateWnfStateData(&WNF_USB_XHCI_AUDIO_OFFLOAD_STATE, &v2, 1, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x140081394  sub     rsp, 48h
0x140081398  xor     eax, eax
0x14008139a  mov     [rsp+48h+arg_0], cl
0x14008139e  mov     [rsp+48h+var_18], eax
0x1400813a2  lea     rdx, [rsp+48h+arg_0]
0x1400813a7  mov     [rsp+48h+var_20], eax
0x1400813ab  lea     rcx, WNF_USB_XHCI_AUDIO_OFFLOAD_STATE
0x1400813b2  xor     r9d, r9d
0x1400813b5  mov     [rsp+48h+var_28], rax
0x1400813ba  lea     r8d, [rax+1]
0x1400813be  call    cs:__imp_ZwUpdateWnfStateData
0x1400813c5  nop     dword ptr [rax+rax+00h]
0x1400813ca  add     rsp, 48h
0x1400813ce  retn
```
