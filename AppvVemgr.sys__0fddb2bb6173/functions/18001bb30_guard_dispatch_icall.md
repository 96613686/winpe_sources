# _guard_dispatch_icall

- ea: `0x18001bb30`
- end: `0x18001bb36`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `97`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000129c`
- `0x180001598`
- `0x180001788`
- `0x18000199c`
- `0x180001c98`
- `0x180001d4c`
- `0x180001f78`
- `0x1800021d0`
- `0x1800030f4`
- `0x18000324c`
- `0x180003d74`
- `0x180003e74`
- `0x180003f50`
- `0x180003fd0`
- `0x180004a90`
- `0x180004d50`
- `0x180004e20`
- `0x180004fc8`
- `0x180005178`
- `0x180005200`
- `0x1800052e0`
- `0x180005388`
- `0x180005430`
- `0x1800054e8`
- `0x18000566c`
- `0x180005a30`
- `0x180005ec4`
- `0x180006880`
- `0x180006cac`
- `0x1800071a0`
- `0x180007840`
- `0x180007b88`
- `0x180007e10`
- `0x180008048`
- `0x180008358`
- `0x180008b90`
- `0x180008dd4`
- `0x180009208`
- `0x180009710`
- `0x1800099b4`
- `0x18000a218`
- `0x18000ac20`
- `0x18000ad50`
- `0x18000ade8`
- `0x18000b09c`
- `0x18000b478`
- `0x18000baf0`
- `0x18000bd30`
- `0x18000bf40`
- `0x18000bfb8`

## callees

- `0x18001bb60`

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
0x18001bb30  jmp     cs:__guard_dispatch_icall_fptr
```
