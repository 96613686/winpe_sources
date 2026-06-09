# _NLG_Notify

- ea: `0x18000b130`
- end: `0x18000b14b`
- name: `_NLG_Notify`
- size: `27`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180008c3c`
- `0x18000b4c0`
- `0x18000b500`
- `0x18000b530`
- `0x18000b560`

## callees

- `0x18000b150`

## pseudocode

```c
__int64 __fastcall NLG_Notify(__int64 a1, __int64 a2, __int64 a3)
{
  return _NLG_Dispatch2(a1, a2, a3, 429065504);
}

```

## disassembly

```asm
0x18000b130  mov     [rsp+arg_0], rcx
0x18000b135  mov     [rsp+arg_10], rdx
0x18000b13a  mov     [rsp+arg_8], r8d
0x18000b13f  mov     r9, 19930520h
0x18000b146  jmp     __NLG_Dispatch2
```
