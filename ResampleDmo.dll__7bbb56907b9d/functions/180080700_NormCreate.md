# NormCreate

- ea: `0x180080700`
- end: `0x18008072c`
- name: `NormCreate`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000abfc`
- `0x18000b79c`

## pseudocode

```c
void *NormCreate()
{
  void *v0; // rbx

  v0 = operator new(0x20F8u);
  memset_0(v0, 0, 0x20F8u);
  return v0;
}

```

## disassembly

```asm
0x180080700  push    rbx
0x180080702  sub     rsp, 20h
0x180080706  mov     ecx, 20F8h; Size
0x18008070b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180080710  xor     edx, edx; Val
0x180080712  mov     r8d, 20F8h; Size
0x180080718  mov     rcx, rax; void *
0x18008071b  mov     rbx, rax
0x18008071e  call    memset_0
0x180080723  mov     rax, rbx
0x180080726  add     rsp, 20h
0x18008072a  pop     rbx
0x18008072b  retn
```
