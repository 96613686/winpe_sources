# _guard_dispatch_icall

- ea: `0x14000d830`
- end: `0x14000d836`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `46`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400013a0`
- `0x1400015cc`
- `0x1400019d0`
- `0x140002964`
- `0x140002a24`
- `0x140002b10`
- `0x140002bec`
- `0x140002cdc`
- `0x140002dd8`
- `0x140003618`
- `0x14000473c`
- `0x140004830`
- `0x14000492c`
- `0x140004a04`
- `0x140004adc`
- `0x140004bf8`
- `0x1400068cc`
- `0x140006a20`
- `0x140006ac0`
- `0x140006ce8`
- `0x140009098`
- `0x1400091b0`
- `0x1400092ec`
- `0x1400093e8`
- `0x140009504`
- `0x140009620`
- `0x140009760`
- `0x1400098a0`
- `0x14000998c`
- `0x14000b4d0`
- `0x14000b59c`
- `0x14000b710`
- `0x14000b89c`
- `0x14000b980`
- `0x14000bafc`
- `0x14000bca0`
- `0x14000bd7c`
- `0x14000c9f0`
- `0x14000cd68`
- `0x14000d370`
- `0x14000d560`
- `0x14000f010`
- `0x140015008`
- `0x1400150bc`
- `0x140015184`
- `0x1400152d0`

## callees

- `0x14000d860`

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
0x14000d830  jmp     cs:__guard_dispatch_icall_fptr
```
