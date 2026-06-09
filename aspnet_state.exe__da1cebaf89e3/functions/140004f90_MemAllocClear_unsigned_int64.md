# MemAllocClear(unsigned __int64)

- ea: `0x140004f90`
- end: `0x140004fc8`
- name: `?MemAllocClear@@YAPEAX_K@Z`
- size: `56`
- prototype: `LPVOID __fastcall(SIZE_T)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x140001994`
- `0x140001d64`
- `0x140002a78`
- `0x140003774`
- `0x140003a9c`
- `0x140003bb0`
- `0x1400044f0`
- `0x140004850`
- `0x140004ba4`
- `0x140004e5c`

## callees

- `0x140004f90`
- `0x14000656d`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140004fc1`

## pseudocode

```c
LPVOID __fastcall MemAllocClear(SIZE_T a1)
{
  HANDLE XSPHeap; // rax

  XSPHeap = g_hMyHeap;
  if ( !g_hMyHeap )
  {
    XSPHeap = GetXSPHeap();
    g_hMyHeap = XSPHeap;
  }
  return HeapAlloc(XSPHeap, 8u, a1);
}

```

## disassembly

```asm
0x140004f90  push    rbx
0x140004f92  sub     rsp, 20h
0x140004f96  mov     rax, cs:?g_hMyHeap@@3PEAXEA; void * g_hMyHeap
0x140004f9d  mov     rbx, rcx
0x140004fa0  test    rax, rax
0x140004fa3  jnz     short loc_140004FB1
0x140004fa5  call    ?GetXSPHeap@@YAPEAXXZ; GetXSPHeap(void)
0x140004faa  mov     cs:?g_hMyHeap@@3PEAXEA, rax; void * g_hMyHeap
0x140004fb1  mov     r8, rbx
0x140004fb4  mov     edx, 8
0x140004fb9  mov     rcx, rax
0x140004fbc  add     rsp, 20h
0x140004fc0  pop     rbx
0x140004fc1  jmp     cs:__imp_HeapAlloc
```
