# MemAlloc(unsigned __int64)

- ea: `0x140004f58`
- end: `0x140004f8d`
- name: `?MemAlloc@@YAPEAX_K@Z`
- size: `53`
- prototype: `LPVOID __fastcall(SIZE_T)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1400013c4`
- `0x1400017ac`
- `0x140004638`
- `0x140004850`
- `0x1400051ac`

## callees

- `0x140004f58`
- `0x14000656d`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140004f86`

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
0x140004f58  push    rbx
0x140004f5a  sub     rsp, 20h
0x140004f5e  mov     rax, cs:?g_hMyHeap@@3PEAXEA; void * g_hMyHeap
0x140004f65  mov     rbx, rcx
0x140004f68  test    rax, rax
0x140004f6b  jnz     short loc_140004F79
0x140004f6d  call    ?GetXSPHeap@@YAPEAXXZ; GetXSPHeap(void)
0x140004f72  mov     cs:?g_hMyHeap@@3PEAXEA, rax; void * g_hMyHeap
0x140004f79  mov     r8, rbx
0x140004f7c  xor     edx, edx
0x140004f7e  mov     rcx, rax
0x140004f81  add     rsp, 20h
0x140004f85  pop     rbx
0x140004f86  jmp     cs:__imp_HeapAlloc
```
