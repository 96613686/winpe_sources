# CloseRPCServerDebugInfo(void * *)

- ea: `0x180009b54`
- end: `0x180009ba1`
- name: `?CloseRPCServerDebugInfo@@YAXPEAPEAX@Z`
- size: `77`
- prototype: `void __fastcall(void **)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800073a0`
- `0x180007410`
- `0x180007600`
- `0x180009ba8`
- `0x180009ca4`

## callees

- `0x180002a00`
- `0x180009b54`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180009b76`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180009b76`

## pseudocode

```c
void __fastcall CloseRPCServerDebugInfo(void **a1)
{
  __int64 *v1; // rsi
  __int64 v3; // rbp
  __int64 v4; // rbx

  v1 = (__int64 *)*a1;
  v3 = *(_QWORD *)*a1;
  do
  {
    v4 = *(_QWORD *)(v3 + 40);
    VirtualFree(*(LPVOID *)(v3 + 32), 0, 0x8000u);
    operator delete((void *)v3);
    v3 = v4 - 40;
  }
  while ( v4 );
  operator delete(v1);
  *a1 = 0;
}

```

## disassembly

```asm
0x180009b54  push    rbx
0x180009b56  push    rbp
0x180009b57  push    rsi
0x180009b58  push    rdi
0x180009b59  sub     rsp, 28h
0x180009b5d  mov     rsi, [rcx]
0x180009b60  mov     rdi, rcx
0x180009b63  mov     rbp, [rsi]
0x180009b66  mov     rcx, [rbp+20h]; lpAddress
0x180009b6a  xor     edx, edx; dwSize
0x180009b6c  mov     rbx, [rbp+28h]
0x180009b70  mov     r8d, 8000h; dwFreeType
0x180009b76  call    cs:__imp_VirtualFree
0x180009b7c  mov     rcx, rbp; void *
0x180009b7f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009b84  lea     rbp, [rbx-28h]
0x180009b88  test    rbx, rbx
0x180009b8b  jnz     short loc_180009B66
0x180009b8d  mov     rcx, rsi; void *
0x180009b90  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009b95  mov     [rdi], rbx
0x180009b98  add     rsp, 28h
0x180009b9c  pop     rdi
0x180009b9d  pop     rsi
0x180009b9e  pop     rbp
0x180009b9f  pop     rbx
0x180009ba0  retn
```
