# DbgThreadEnumHandle_rundown

- ea: `0x180007410`
- end: `0x180007433`
- name: `DbgThreadEnumHandle_rundown`
- size: `35`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800075b0`

## callees

- `0x180002a00`
- `0x180009b54`

## pseudocode

```c
void __fastcall DbgThreadEnumHandle_rundown(_QWORD *a1)
{
  CloseRPCServerDebugInfo((void **)(a1[1] + 8LL));
  operator delete(a1);
}

```

## disassembly

```asm
0x180007410  push    rbx
0x180007412  sub     rsp, 20h
0x180007416  mov     rbx, rcx
0x180007419  mov     rcx, [rcx+8]
0x18000741d  add     rcx, 8; void **
0x180007421  call    ?CloseRPCServerDebugInfo@@YAXPEAPEAX@Z; CloseRPCServerDebugInfo(void * *)
0x180007426  mov     rcx, rbx; void *
0x180007429  add     rsp, 20h
0x18000742d  pop     rbx
0x18000742e  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
