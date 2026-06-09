# _NLG_Notify

- ea: `0x14000e0f0`
- end: `0x14000e108`
- name: `_NLG_Notify`
- size: `24`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14000bc38`
- `0x14000e170`
- `0x14000e1c0`
- `0x14000e1f0`
- `0x14000e220`

## callees

- `0x14000e110`

## pseudocode

```c
__int64 __fastcall NLG_Notify(__int64 a1, __int64 a2, __int64 a3)
{
  return _NLG_Dispatch2(a1, a2, a3, 429065504);
}

```

## disassembly

```asm
0x14000e0f0  mov     [rsp+arg_0], rcx
0x14000e0f5  mov     [rsp+arg_10], rdx
0x14000e0fa  mov     [rsp+arg_8], r8d
0x14000e0ff  mov     r9, 19930520h
0x14000e106  jmp     short __NLG_Dispatch2
```
