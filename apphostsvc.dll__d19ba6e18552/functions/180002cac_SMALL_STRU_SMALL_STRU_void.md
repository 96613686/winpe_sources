# SMALL_STRU::~SMALL_STRU(void)

- ea: `0x180002cac`
- end: `0x180002ce7`
- name: `??1SMALL_STRU@@QEAA@XZ`
- size: `59`
- prototype: `void __fastcall(SMALL_STRU *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800090ed`
- `0x180009106`

## callees

- `0x180002cac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002cc1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002cc1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002ccf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002ccf`

## pseudocode

```c
void __fastcall SMALL_STRU::~SMALL_STRU(void **this)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax

  v1 = *this;
  if ( *this )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
    *this = 0;
  }
}

```

## disassembly

```asm
0x180002cac  mov     [rsp+arg_0], rbx
0x180002cb1  push    rdi
0x180002cb2  sub     rsp, 20h
0x180002cb6  mov     rdi, [rcx]
0x180002cb9  mov     rbx, rcx
0x180002cbc  test    rdi, rdi
0x180002cbf  jz      short loc_180002CDC
0x180002cc1  call    cs:__imp_GetProcessHeap
0x180002cc7  mov     r8, rdi; lpMem
0x180002cca  xor     edx, edx; dwFlags
0x180002ccc  mov     rcx, rax; hHeap
0x180002ccf  call    cs:__imp_HeapFree
0x180002cd5  mov     qword ptr [rbx], 0
0x180002cdc  mov     rbx, [rsp+28h+arg_0]
0x180002ce1  add     rsp, 20h
0x180002ce5  pop     rdi
0x180002ce6  retn
```
