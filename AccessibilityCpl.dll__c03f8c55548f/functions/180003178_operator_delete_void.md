# operator delete(void *)

- ea: `0x180003178`
- end: `0x18000319f`
- name: `??3@YAXPEAX@Z`
- size: `39`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `24`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002024`
- `0x180002ff0`
- `0x180004ee0`
- `0x180004f0c`
- `0x180004f40`
- `0x180004f78`
- `0x180004fa0`
- `0x1800134a0`
- `0x18001c390`
- `0x18001c3d0`
- `0x18001c410`
- `0x18001cac0`
- `0x18001e190`
- `0x18001eb90`
- `0x18001ebd0`
- `0x18001f0a0`
- `0x18001ff40`
- `0x18001ff70`
- `0x18002a570`
- `0x18002b410`
- `0x18002cb38`
- `0x18002cbf4`
- `0x18002cc20`
- `0x18002d73b`

## callees

- `0x180003178`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003193`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003193`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003185`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003185`

## pseudocode

```c
void __fastcall operator delete(void *lpMem)
{
  HANDLE ProcessHeap; // rax

  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
}

```

## disassembly

```asm
0x180003178  test    rcx, rcx
0x18000317b  jz      short locret_18000319E
0x18000317d  push    rbx
0x18000317e  sub     rsp, 20h
0x180003182  mov     rbx, rcx
0x180003185  call    cs:__imp_GetProcessHeap
0x18000318b  mov     r8, rbx; lpMem
0x18000318e  xor     edx, edx; dwFlags
0x180003190  mov     rcx, rax; hHeap
0x180003193  call    cs:__imp_HeapFree
0x180003199  add     rsp, 20h
0x18000319d  pop     rbx
0x18000319e  retn
```
