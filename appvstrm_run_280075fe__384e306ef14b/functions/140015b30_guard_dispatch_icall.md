# _guard_dispatch_icall

- ea: `0x140015b30`
- end: `0x140015b36`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `83`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400010b0`
- `0x140001204`
- `0x140001780`
- `0x140001aa0`
- `0x140001e30`
- `0x140001f40`
- `0x1400020c8`
- `0x140002298`
- `0x1400023d8`
- `0x140002710`
- `0x140002edc`
- `0x140003b50`
- `0x140003bd8`
- `0x140003d40`
- `0x14000404c`
- `0x1400041cc`
- `0x1400044a0`
- `0x1400048a8`
- `0x140004b80`
- `0x140004c40`
- `0x140004ef0`
- `0x1400053e8`
- `0x140005498`
- `0x140005640`
- `0x14000571c`
- `0x140005b20`
- `0x140005e3c`
- `0x14000600c`
- `0x140006158`
- `0x1400062bc`
- `0x140006c08`
- `0x140006fe0`
- `0x1400073b8`
- `0x1400075d0`
- `0x140007700`
- `0x140007a00`
- `0x140007c24`
- `0x140007fe4`
- `0x1400084b0`
- `0x1400086a8`
- `0x140008bdc`
- `0x140008dc4`
- `0x14000935c`
- `0x140009b58`
- `0x140009c1c`
- `0x140009d98`
- `0x14000a1f0`
- `0x14000a310`
- `0x14000abd8`
- `0x14000b0bc`

## callees

- `0x140015b60`

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
0x140015b30  jmp     cs:__guard_dispatch_icall_fptr
```
