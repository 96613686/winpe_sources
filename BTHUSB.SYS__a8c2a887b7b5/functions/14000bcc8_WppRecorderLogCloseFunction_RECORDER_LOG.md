# WppRecorderLogCloseFunction(RECORDER_LOG__ *)

- ea: `0x14000bcc8`
- end: `0x14000bd06`
- name: `?WppRecorderLogCloseFunction@@YAXPEAURECORDER_LOG__@@@Z`
- size: `62`
- prototype: `void __fastcall(struct RECORDER_LOG__ *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14001868c`
- `0x140018764`
- `0x140019008`

## callees

- `0x14000bcc8`

## import_xrefs

- `WppRecorder!imp_WppRecorderLogDelete` at `0x14000bcf3`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x14000bcf3`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000bcd8`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000bcd8`

## pseudocode

```c
void __fastcall WppRecorderLogCloseFunction(struct RECORDER_LOG__ *a1)
{
  if ( a1 != (struct RECORDER_LOG__ *)imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control) )
    imp_WppRecorderLogDelete(WPP_GLOBAL_Control, a1);
}

```

## disassembly

```asm
0x14000bcc8  push    rbx
0x14000bcca  sub     rsp, 20h
0x14000bcce  mov     rbx, rcx
0x14000bcd1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bcd8  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000bcdf  nop     dword ptr [rax+rax+00h]
0x14000bce4  cmp     rbx, rax
0x14000bce7  jz      short loc_14000BCFF
0x14000bce9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bcf0  mov     rdx, rbx
0x14000bcf3  call    cs:__imp_imp_WppRecorderLogDelete
0x14000bcfa  nop     dword ptr [rax+rax+00h]
0x14000bcff  add     rsp, 20h
0x14000bd03  pop     rbx
0x14000bd04  retn
```
