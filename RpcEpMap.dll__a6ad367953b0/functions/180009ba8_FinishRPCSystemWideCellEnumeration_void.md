# FinishRPCSystemWideCellEnumeration(void * *)

- ea: `0x180009ba8`
- end: `0x180009bf0`
- name: `?FinishRPCSystemWideCellEnumeration@@YAXPEAPEAX@Z`
- size: `72`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800073a0`
- `0x1800073e0`

## callees

- `0x180002a00`
- `0x180009b54`
- `0x180009ba8`

## pseudocode

```c
void __fastcall FinishRPCSystemWideCellEnumeration(void ***a1)
{
  void **v1; // rbx
  void **v3; // rcx

  v1 = *a1;
  v3 = *a1 + 1;
  if ( *v3 )
    CloseRPCServerDebugInfo(v3);
  operator delete(*v1);
  *v1 = 0;
  operator delete(v1);
  *a1 = 0;
}

```

## disassembly

```asm
0x180009ba8  mov     [rsp+arg_0], rbx
0x180009bad  push    rdi
0x180009bae  sub     rsp, 20h
0x180009bb2  mov     rbx, [rcx]
0x180009bb5  mov     rdi, rcx
0x180009bb8  lea     rcx, [rbx+8]; void **
0x180009bbc  cmp     qword ptr [rcx], 0
0x180009bc0  jz      short loc_180009BC7
0x180009bc2  call    ?CloseRPCServerDebugInfo@@YAXPEAPEAX@Z; CloseRPCServerDebugInfo(void * *)
0x180009bc7  mov     rcx, [rbx]; void *
0x180009bca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009bcf  mov     rcx, rbx; void *
0x180009bd2  mov     qword ptr [rbx], 0
0x180009bd9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009bde  mov     rbx, [rsp+28h+arg_0]
0x180009be3  mov     qword ptr [rdi], 0
0x180009bea  add     rsp, 20h
0x180009bee  pop     rdi
0x180009bef  retn
```
