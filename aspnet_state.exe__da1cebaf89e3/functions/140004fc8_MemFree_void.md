# MemFree(void *)

- ea: `0x140004fc8`
- end: `0x140005002`
- name: `?MemFree@@YAXPEAX@Z`
- size: `58`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x140001394`
- `0x1400017ac`
- `0x140001a20`
- `0x140002a78`
- `0x140003588`
- `0x1400036a0`
- `0x1400036e0`
- `0x140003730`
- `0x140004638`
- `0x140004850`
- `0x1400051ac`
- `0x1400056d0`

## callees

- `0x140004fc8`
- `0x14000656d`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140004ff6`
- `KERNEL32!HeapFree` at `0x140004ff6`

## pseudocode

```c
void __fastcall MemFree(void *lpMem)
{
  HANDLE XSPHeap; // rax

  XSPHeap = g_hMyHeap;
  if ( !g_hMyHeap )
  {
    XSPHeap = GetXSPHeap();
    g_hMyHeap = XSPHeap;
  }
  if ( lpMem )
    HeapFree(XSPHeap, 0, lpMem);
}

```

## disassembly

```asm
0x140004fc8  push    rbx
0x140004fca  sub     rsp, 20h
0x140004fce  mov     rax, cs:?g_hMyHeap@@3PEAXEA; void * g_hMyHeap
0x140004fd5  mov     rbx, rcx
0x140004fd8  test    rax, rax
0x140004fdb  jnz     short loc_140004FE9
0x140004fdd  call    ?GetXSPHeap@@YAPEAXXZ; GetXSPHeap(void)
0x140004fe2  mov     cs:?g_hMyHeap@@3PEAXEA, rax; void * g_hMyHeap
0x140004fe9  test    rbx, rbx
0x140004fec  jz      short loc_140004FFC
0x140004fee  mov     r8, rbx; lpMem
0x140004ff1  xor     edx, edx; dwFlags
0x140004ff3  mov     rcx, rax; hHeap
0x140004ff6  call    cs:__imp_HeapFree
0x140004ffc  add     rsp, 20h
0x140005000  pop     rbx
0x140005001  retn
```
