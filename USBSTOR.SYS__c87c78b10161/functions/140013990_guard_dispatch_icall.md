# _guard_dispatch_icall

- ea: `0x140013990`
- end: `0x140013996`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `34`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140008590`
- `0x14000b610`
- `0x14000d700`
- `0x14000e974`
- `0x14000fee8`
- `0x1400104c8`
- `0x140010530`
- `0x140010594`
- `0x1400105e8`
- `0x140010664`
- `0x140010c60`
- `0x140010cb4`
- `0x140010d10`
- `0x140010da4`
- `0x140010e18`
- `0x140010e74`
- `0x140010eb8`
- `0x140010f78`
- `0x14001100c`
- `0x140011080`
- `0x14001114c`
- `0x140012920`
- `0x140012994`
- `0x1400129fc`
- `0x140012a84`
- `0x140012f00`
- `0x140013230`
- `0x140013714`
- `0x140015010`
- `0x14001f374`
- `0x14001f84c`
- `0x14001f8d0`
- `0x140021090`
- `0x140026f6c`

## callees

- `0x1400139c0`

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
0x140013990  jmp     cs:__guard_dispatch_icall_fptr
```
