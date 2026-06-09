# operator delete(void *)

- ea: `0x18000a100`
- end: `0x18000a123`
- name: `??3@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(void *)`
- caller_count: `90`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001568`
- `0x180001840`
- `0x180001f34`
- `0x180003158`
- `0x180006b3c`
- `0x180007060`
- `0x180007fb8`
- `0x180008bb8`
- `0x180009d80`
- `0x180009e80`
- `0x18000a0d0`
- `0x18000a0dc`
- `0x18000a160`
- `0x18000a420`
- `0x18000a4b4`
- `0x18000a594`
- `0x18000a724`
- `0x18000a978`
- `0x18000b638`
- `0x18000b95c`
- `0x18000bad8`
- `0x18000bc28`
- `0x18000bcdc`
- `0x18000c930`
- `0x18000cb00`
- `0x18000cf54`
- `0x18000cfa0`
- `0x18000d050`
- `0x18000f980`
- `0x1800121bc`
- `0x180013f6c`
- `0x1800142d0`
- `0x180015768`
- `0x1800157bc`
- `0x18001590c`
- `0x180017864`
- `0x180017ef4`
- `0x180018130`
- `0x18001992c`
- `0x18001ab4c`
- `0x18001ab64`
- `0x18001bda4`
- `0x18001c43c`
- `0x18001c634`
- `0x18001c87c`
- `0x18001cb20`
- `0x18001d0f0`
- `0x18001d4f0`
- `0x18001d8d0`
- `0x18001e1e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a109`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a109`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a11c`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x18000a100  push    rbx
0x18000a102  sub     rsp, 20h
0x18000a106  mov     rbx, rcx
0x18000a109  call    cs:__imp_GetProcessHeap
0x18000a10f  mov     r8, rbx
0x18000a112  xor     edx, edx
0x18000a114  mov     rcx, rax
0x18000a117  add     rsp, 20h
0x18000a11b  pop     rbx
0x18000a11c  jmp     cs:__imp_HeapFree
```
