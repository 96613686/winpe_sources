# BUFFER::FreeMemoryInternal(void)

- ea: `0x1800073dc`
- end: `0x180007400`
- name: `?FreeMemoryInternal@BUFFER@@AEAAXXZ`
- size: `36`
- prototype: `void __fastcall(BUFFER *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180007234`
- `0x180008144`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800073e6`
- `KERNEL32!GetProcessHeap` at `0x1800073e6`
- `KERNEL32!HeapFree` at `0x1800073f9`

## pseudocode

```c
void __fastcall BUFFER::FreeMemoryInternal(BUFFER *this)
{
  void *v1; // rbx
  HANDLE ProcessHeap; // rax

  v1 = (void *)*((_QWORD *)this + 4);
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v1);
}

```

## disassembly

```asm
0x1800073dc  push    rbx
0x1800073de  sub     rsp, 20h
0x1800073e2  mov     rbx, [rcx+20h]
0x1800073e6  call    cs:__imp_GetProcessHeap
0x1800073ec  mov     r8, rbx
0x1800073ef  xor     edx, edx
0x1800073f1  mov     rcx, rax
0x1800073f4  add     rsp, 20h
0x1800073f8  pop     rbx
0x1800073f9  jmp     cs:__imp_HeapFree
```
