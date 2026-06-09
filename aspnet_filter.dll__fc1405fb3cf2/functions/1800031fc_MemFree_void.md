# MemFree(void *)

- ea: `0x1800031fc`
- end: `0x180003236`
- name: `?MemFree@@YAXPEAX@Z`
- size: `58`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ba0`
- `0x180001ee8`
- `0x180002048`
- `0x1800028d0`
- `0x1800030cc`

## callees

- `0x180002fa4`
- `0x1800031fc`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000322a`
- `KERNEL32!HeapFree` at `0x18000322a`

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
0x1800031fc  push    rbx
0x1800031fe  sub     rsp, 20h
0x180003202  mov     rax, cs:?g_hMyHeap@@3PEAXEA; void * g_hMyHeap
0x180003209  mov     rbx, rcx
0x18000320c  test    rax, rax
0x18000320f  jnz     short loc_18000321D
0x180003211  call    ?GetXSPHeap@@YAPEAXXZ; GetXSPHeap(void)
0x180003216  mov     cs:?g_hMyHeap@@3PEAXEA, rax; void * g_hMyHeap
0x18000321d  test    rbx, rbx
0x180003220  jz      short loc_180003230
0x180003222  mov     r8, rbx; lpMem
0x180003225  xor     edx, edx; dwFlags
0x180003227  mov     rcx, rax; hHeap
0x18000322a  call    cs:__imp_HeapFree
0x180003230  add     rsp, 20h
0x180003234  pop     rbx
0x180003235  retn
```
