# _guard_dispatch_icall_nop

- ea: `0x18007a900`
- end: `0x18007a902`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `149`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180029f00`
- `0x18002c77c`
- `0x18002efb0`
- `0x18002f2a0`
- `0x18002f2e8`
- `0x18002f35c`
- `0x18002f460`
- `0x180033900`
- `0x180033970`
- `0x180033a00`
- `0x180033a20`
- `0x180033a50`
- `0x180034208`
- `0x180037830`
- `0x180039740`
- `0x18003995c`
- `0x180039a10`
- `0x180039e70`
- `0x180039f88`
- `0x18003ed00`
- `0x18003ed60`
- `0x18003ee90`
- `0x18003efa0`
- `0x18003f140`
- `0x18003f1c0`
- `0x18003f3e0`
- `0x18003f520`
- `0x18003f600`
- `0x18003f740`
- `0x18003f8f0`
- `0x18003f9e0`
- `0x18003fa00`
- `0x18003fb48`
- `0x1800417ac`
- `0x180042c40`
- `0x180043010`
- `0x18004333c`
- `0x1800454a0`
- `0x1800454c0`
- `0x180045780`
- `0x180046bd0`
- `0x180046f40`
- `0x180049818`
- `0x18004a680`
- `0x18004e070`
- `0x18004e230`
- `0x18004e2c0`
- `0x18004e2d0`
- `0x18004e370`
- `0x18004e3b0`

## pseudocode

```c
__int64 __fastcall guard_dispatch_icall_nop()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x18007a900  jmp     rax
```
