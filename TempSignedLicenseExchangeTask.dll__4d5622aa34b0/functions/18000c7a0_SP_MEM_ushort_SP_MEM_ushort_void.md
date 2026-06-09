# SP_MEM<ushort *>::~SP_MEM<ushort *>(void)

- ea: `0x18000c7a0`
- end: `0x18000c7db`
- name: `??1?$SP_MEM@PEAG@@QEAA@XZ`
- size: `59`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e30`

## callees

- `0x18000c7a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c7c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c7c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c7b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c7b5`

## pseudocode

```c
void __fastcall SP_MEM<unsigned short *>::~SP_MEM<unsigned short *>(void **a1)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax

  v1 = *a1;
  if ( *a1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x18000c7a0  mov     [rsp+arg_0], rbx
0x18000c7a5  push    rdi
0x18000c7a6  sub     rsp, 20h
0x18000c7aa  mov     rdi, [rcx]
0x18000c7ad  mov     rbx, rcx
0x18000c7b0  test    rdi, rdi
0x18000c7b3  jz      short loc_18000C7D0
0x18000c7b5  call    cs:__imp_GetProcessHeap
0x18000c7bb  mov     r8, rdi; lpMem
0x18000c7be  xor     edx, edx; dwFlags
0x18000c7c0  mov     rcx, rax; hHeap
0x18000c7c3  call    cs:__imp_HeapFree
0x18000c7c9  mov     qword ptr [rbx], 0
0x18000c7d0  mov     rbx, [rsp+28h+arg_0]
0x18000c7d5  add     rsp, 20h
0x18000c7d9  pop     rdi
0x18000c7da  retn
```
