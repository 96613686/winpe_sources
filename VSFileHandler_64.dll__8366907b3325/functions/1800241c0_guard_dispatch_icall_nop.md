# _guard_dispatch_icall_nop

- ea: `0x1800241c0`
- end: `0x1800241c2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `40`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800073e0`
- `0x180007578`
- `0x1800077e8`
- `0x180008000`
- `0x18000803c`
- `0x180008500`
- `0x180008cf0`
- `0x180009050`
- `0x180009408`
- `0x180009758`
- `0x18000a578`
- `0x18000b7dc`
- `0x18000b824`
- `0x18000b86c`
- `0x18000b8b4`
- `0x18000b908`
- `0x18000bdec`
- `0x18000d6ac`
- `0x18000d710`
- `0x18000d764`
- `0x18000d920`
- `0x18000daf8`
- `0x18000e380`
- `0x18000e744`
- `0x18000e7a8`
- `0x180013c30`
- `0x180013c80`
- `0x180013cbc`
- `0x180013d04`
- `0x180013d4c`
- `0x180013d94`
- `0x180013de8`
- `0x180013e4c`
- `0x180013f28`
- `0x18001403c`
- `0x1800140bc`
- `0x180014190`
- `0x180014424`
- `0x1800170d0`
- `0x1800241e0`

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
0x1800241c0  jmp     rax
```
