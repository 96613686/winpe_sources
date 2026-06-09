# av_frame_copy_props

- ea: `0x18003b2e0`
- end: `0x18003b2eb`
- name: `av_frame_copy_props`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18003bfe0`

## pseudocode

```c
__int64 __fastcall av_frame_copy_props(__int64 a1, __int64 a2)
{
  return sub_18003BFE0(a1, a2, 1);
}

```

## disassembly

```asm
0x18003b2e0  mov     r8d, 1
0x18003b2e6  jmp     sub_18003BFE0
```
