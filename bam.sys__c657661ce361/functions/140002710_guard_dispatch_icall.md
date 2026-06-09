# _guard_dispatch_icall

- ea: `0x140002710`
- end: `0x140002716`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001c58`
- `0x140001cd4`
- `0x140001dc4`
- `0x140003010`
- `0x14000cc54`
- `0x14000d224`
- `0x14000dd04`
- `0x140013094`
- `0x140013230`
- `0x140013740`
- `0x140015a70`

## callees

- `0x140002740`

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
0x140002710  jmp     cs:__guard_dispatch_icall_fptr
```
