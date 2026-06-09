# [thunk]:CMigrationPlugin::get_PerUserSupport`adjustor{24}' (short *)

- ea: `0x1800141b0`
- end: `0x1800141b9`
- name: `?get_PerUserSupport@CMigrationPlugin@@WBI@EAAJPEAF@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180014170`

## pseudocode

```c
__int64 __fastcall CMigrationPlugin::get_PerUserSupport(__int64 a1, __int16 *a2)
{
  return CMigrationPlugin::get_PerUserSupport((CMigrationPlugin *)(a1 - 24), a2);
}

```

## disassembly

```asm
0x1800141b0  sub     rcx, 18h; this
0x1800141b4  jmp     ?get_PerUserSupport@CMigrationPlugin@@UEAAJPEAF@Z; CMigrationPlugin::get_PerUserSupport(short *)
```
