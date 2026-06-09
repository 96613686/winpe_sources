# av_frame_get_side_data

- ea: `0x18003b460`
- end: `0x18003b475`
- name: `av_frame_get_side_data`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180036840`

## callees

- `0x180050b00`

## pseudocode

```c
__int64 __fastcall av_frame_get_side_data(__int64 a1, unsigned int a2)
{
  return av_frame_side_data_get_c(*(_QWORD *)(a1 + 264), *(unsigned int *)(a1 + 272), a2);
}

```

## disassembly

```asm
0x18003b460  mov     r8d, edx
0x18003b463  mov     edx, [rcx+110h]
0x18003b469  mov     rcx, [rcx+108h]
0x18003b470  jmp     av_frame_side_data_get_c
```
