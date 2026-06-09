# _NLG_Notify

- ea: `0x18000b5a0`
- end: `0x18000b5bb`
- name: `_NLG_Notify`
- size: `27`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000906c`
- `0x18000b9b0`
- `0x18000b9f0`
- `0x18000ba20`
- `0x18000ba50`

## callees

- `0x18000b5c0`

## pseudocode

```c
__int64 __fastcall NLG_Notify(__int64 a1, __int64 a2, __int64 a3)
{
  return _NLG_Dispatch2(a1, a2, a3, 429065504);
}

```

## disassembly

```asm
0x18000b5a0  mov     [rsp+arg_0], rcx
0x18000b5a5  mov     [rsp+arg_10], rdx
0x18000b5aa  mov     [rsp+arg_8], r8d
0x18000b5af  mov     r9, 19930520h
0x18000b5b6  jmp     __NLG_Dispatch2
```
