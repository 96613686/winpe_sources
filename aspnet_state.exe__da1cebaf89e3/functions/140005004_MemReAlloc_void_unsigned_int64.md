# MemReAlloc(void *,unsigned __int64)

- ea: `0x140005004`
- end: `0x14000505b`
- name: `?MemReAlloc@@YAPEAXPEAX_K@Z`
- size: `87`
- prototype: `LPVOID __fastcall(void *lpMem, SIZE_T dwBytes)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140003dec`
- `0x140004d3c`

## callees

- `0x140005004`
- `0x14000656d`

## import_xrefs

- `KERNEL32!HeapReAlloc` at `0x14000503f`
- `KERNEL32!HeapReAlloc` at `0x14000503f`
- `KERNEL32!HeapAlloc` at `0x14000504a`
- `KERNEL32!HeapAlloc` at `0x14000504a`

## pseudocode

```c
LPVOID __fastcall MemReAlloc(void *lpMem, SIZE_T dwBytes)
{
  HANDLE XSPHeap; // rax

  XSPHeap = g_hMyHeap;
  if ( !g_hMyHeap )
  {
    XSPHeap = GetXSPHeap();
    g_hMyHeap = XSPHeap;
  }
  if ( lpMem )
    return HeapReAlloc(XSPHeap, 8u, lpMem, dwBytes);
  else
    return HeapAlloc(XSPHeap, 8u, dwBytes);
}

```

## disassembly

```asm
0x140005004  mov     [rsp+arg_0], rbx
0x140005009  push    rdi
0x14000500a  sub     rsp, 20h
0x14000500e  mov     rax, cs:?g_hMyHeap@@3PEAXEA; void * g_hMyHeap
0x140005015  mov     rdi, rdx
0x140005018  mov     rbx, rcx
0x14000501b  test    rax, rax
0x14000501e  jnz     short loc_14000502C
0x140005020  call    ?GetXSPHeap@@YAPEAXXZ; GetXSPHeap(void)
0x140005025  mov     cs:?g_hMyHeap@@3PEAXEA, rax; void * g_hMyHeap
0x14000502c  mov     edx, 8; dwFlags
0x140005031  mov     rcx, rax; hHeap
0x140005034  test    rbx, rbx
0x140005037  jz      short loc_140005047
0x140005039  mov     r9, rdi; dwBytes
0x14000503c  mov     r8, rbx; lpMem
0x14000503f  call    cs:__imp_HeapReAlloc
0x140005045  jmp     short loc_140005050
0x140005047  mov     r8, rdi; dwBytes
0x14000504a  call    cs:__imp_HeapAlloc
0x140005050  mov     rbx, [rsp+28h+arg_0]
0x140005055  add     rsp, 20h
0x140005059  pop     rdi
0x14000505a  retn
```
