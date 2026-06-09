# MemAlloc(unsigned __int64)

- ea: `0x18000318c`
- end: `0x1800031c1`
- name: `?MemAlloc@@YAPEAX_K@Z`
- size: `53`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ba0`
- `0x180001ee8`

## callees

- `0x180002fa4`
- `0x18000318c`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800031ba`

## pseudocode

```c
LPVOID __fastcall MemAlloc(SIZE_T a1)
{
  HANDLE XSPHeap; // rax

  XSPHeap = g_hMyHeap;
  if ( !g_hMyHeap )
  {
    XSPHeap = GetXSPHeap();
    g_hMyHeap = XSPHeap;
  }
  return HeapAlloc(XSPHeap, 0, a1);
}

```

## disassembly

```asm
0x18000318c  push    rbx
0x18000318e  sub     rsp, 20h
0x180003192  mov     rax, cs:?g_hMyHeap@@3PEAXEA; void * g_hMyHeap
0x180003199  mov     rbx, rcx
0x18000319c  test    rax, rax
0x18000319f  jnz     short loc_1800031AD
0x1800031a1  call    ?GetXSPHeap@@YAPEAXXZ; GetXSPHeap(void)
0x1800031a6  mov     cs:?g_hMyHeap@@3PEAXEA, rax; void * g_hMyHeap
0x1800031ad  mov     r8, rbx
0x1800031b0  xor     edx, edx
0x1800031b2  mov     rcx, rax
0x1800031b5  add     rsp, 20h
0x1800031b9  pop     rbx
0x1800031ba  jmp     cs:__imp_HeapAlloc
```
