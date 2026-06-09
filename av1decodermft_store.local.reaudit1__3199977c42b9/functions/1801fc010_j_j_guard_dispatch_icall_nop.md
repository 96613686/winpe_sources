# j_j__guard_dispatch_icall_nop

- ea: `0x1801fc010`
- end: `0x1801fc015`
- name: `j_j__guard_dispatch_icall_nop`
- size: `5`
- prototype: ``
- caller_count: `75`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18017e6b8`
- `0x18017e85c`
- `0x18017ea40`
- `0x18017eb80`
- `0x18017ece8`
- `0x18017f17c`
- `0x18017f1c0`
- `0x18017f4f8`
- `0x18017f554`
- `0x180180370`
- `0x180180390`
- `0x180180c60`
- `0x180180e58`
- `0x1801825d0`
- `0x180182804`
- `0x180183f30`
- `0x180185a80`
- `0x180185bf0`
- `0x180186010`
- `0x1801863f0`
- `0x180186890`
- `0x180186db0`
- `0x180186e30`
- `0x180186e70`
- `0x180187190`
- `0x18018c570`
- `0x18018c5b0`
- `0x18018c850`
- `0x180191c70`
- `0x180196270`
- `0x180196550`
- `0x180198900`
- `0x18019da70`
- `0x18019fba0`
- `0x18019fd80`
- `0x1801a0330`
- `0x1801a0650`
- `0x1801b0f30`
- `0x1801b5ac0`
- `0x1801b8c80`
- `0x1801b9020`
- `0x1801b9870`
- `0x1801d16b0`
- `0x1801d1960`
- `0x1801d2980`
- `0x1801d4b30`
- `0x1801d6100`
- `0x1801d7a70`
- `0x1801d80e0`
- `0x1801d8590`

## callees

- `0x1801f9230`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall j_j__guard_dispatch_icall_nop()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x1801fc010  jmp     j__guard_dispatch_icall_nop
```
