# RtlWriteULongToUser

- ea: `0x14000f77c`
- end: `0x14000f7ba`
- name: `RtlWriteULongToUser`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140007070`
- `0x140024e40`

## callees

- `0x1400034af`
- `0x14000f77c`

## pseudocode

```c
void __fastcall RtlWriteULongToUser(_DWORD *a1, int a2)
{
  ProbeForRead_0(a1, 4u, 1u);
  *a1 = a2;
}

```

## disassembly

```asm
0x14000f77c  mov     [rsp+arg_0], rbx
0x14000f781  push    rdi
0x14000f782  sub     rsp, 20h
0x14000f786  mov     rax, cs:qword_14000D590
0x14000f78d  mov     edi, edx
0x14000f78f  mov     rbx, rcx
0x14000f792  test    rax, rax
0x14000f795  jz      short loc_14000F79E
0x14000f797  call    rax ; qword_14000D590
0x14000f799  nop     dword ptr [rax]
0x14000f79c  jmp     short loc_14000F7AE
0x14000f79e  mov     edx, 4; Length
0x14000f7a3  lea     r8d, [rdx-3]; Alignment
0x14000f7a7  call    ProbeForRead_0
0x14000f7ac  mov     [rbx], edi
0x14000f7ae  mov     rbx, [rsp+28h+arg_0]
0x14000f7b3  add     rsp, 20h
0x14000f7b7  pop     rdi
0x14000f7b8  retn
```
