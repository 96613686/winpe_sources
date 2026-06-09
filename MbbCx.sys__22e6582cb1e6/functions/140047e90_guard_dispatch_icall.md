# _guard_dispatch_icall

- ea: `0x140047e90`
- end: `0x140047e96`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `310`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400018f0`
- `0x140001a20`
- `0x140001cb4`
- `0x140001cf8`
- `0x140001db8`
- `0x140001ea4`
- `0x140002024`
- `0x140002278`
- `0x1400024cc`
- `0x140003124`
- `0x140003534`
- `0x140003744`
- `0x140003ab0`
- `0x140003d30`
- `0x140004004`
- `0x14000431c`
- `0x14000459c`
- `0x140004844`
- `0x1400051ac`
- `0x1400052bc`
- `0x140005444`
- `0x140005534`
- `0x140005644`
- `0x140005778`
- `0x1400058f0`
- `0x1400059c4`
- `0x140005ac4`
- `0x140005c24`
- `0x140005df4`
- `0x1400061b0`
- `0x1400075c0`
- `0x140007674`
- `0x140007758`
- `0x14000783c`
- `0x14000792c`
- `0x140007a84`
- `0x140007c10`
- `0x140007cf4`
- `0x140007df4`
- `0x140007fe4`
- `0x1400080e4`
- `0x1400081e0`
- `0x1400082fc`
- `0x14000870c`
- `0x140008838`
- `0x140008918`
- `0x140008f40`
- `0x140008ff0`
- `0x1400090b0`
- `0x140009104`

## callees

- `0x140047ec0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x140047e90  jmp     cs:__guard_dispatch_icall_fptr
```
