# CBdeCfgConsole::NotifyInitializationComplete(long)

- ea: `0x140002b90`
- end: `0x140002b9e`
- name: `?NotifyInitializationComplete@CBdeCfgConsole@@UEAAXJ@Z`
- size: `14`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!SetEvent` at `0x140002b97`

## pseudocode

```c
void __fastcall CBdeCfgConsole::NotifyInitializationComplete(HANDLE *this)
{
  SetEvent(this[180]);
}

```

## disassembly

```asm
0x140002b90  mov     rcx, [rcx+5A0h]
0x140002b97  jmp     cs:__imp_SetEvent
```
