# JitServiceDebugPrint(char const *,...)

- ea: `0x180007df4`
- end: `0x180007e04`
- name: `?JitServiceDebugPrint@@YAXPEBDZZ`
- size: `16`
- prototype: `void __fastcall(const char *)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x180006670`
- `0x180007e10`

## pseudocode

```c
void __fastcall JitServiceDebugPrint(const char *a1)
{
  ;
}

```

## disassembly

```asm
0x180007df4  mov     [rsp+arg_8], rdx
0x180007df9  mov     [rsp+arg_10], r8
0x180007dfe  mov     [rsp+arg_18], r9
0x180007e03  retn
```
