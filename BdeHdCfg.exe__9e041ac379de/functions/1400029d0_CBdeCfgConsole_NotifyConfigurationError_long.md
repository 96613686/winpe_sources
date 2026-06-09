# CBdeCfgConsole::NotifyConfigurationError(long)

- ea: `0x1400029d0`
- end: `0x1400029f8`
- name: `?NotifyConfigurationError@CBdeCfgConsole@@UEAAXJ@Z`
- size: `40`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1400032b0`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1400029f1`

## pseudocode

```c
void __fastcall CBdeCfgConsole::NotifyConfigurationError(HANDLE *this)
{
  CBdeCfgConsole::PrintConsoleMessage((CBdeCfgConsole *)this, L"\r\n\r\n");
  SetEvent(this[180]);
}

```

## disassembly

```asm
0x1400029d0  push    rbx
0x1400029d2  sub     rsp, 20h
0x1400029d6  lea     rdx, asc_1400067C8; "\r\n\r\n"
0x1400029dd  mov     rbx, rcx
0x1400029e0  call    ?PrintConsoleMessage@CBdeCfgConsole@@AEAAJPEBGZZ; CBdeCfgConsole::PrintConsoleMessage(ushort const *,...)
0x1400029e5  mov     rcx, [rbx+5A0h]
0x1400029ec  add     rsp, 20h
0x1400029f0  pop     rbx
0x1400029f1  jmp     cs:__imp_SetEvent
```
