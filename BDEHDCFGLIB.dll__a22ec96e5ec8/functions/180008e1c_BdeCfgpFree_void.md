# BdeCfgpFree(void *)

- ea: `0x180008e1c`
- end: `0x180008e43`
- name: `?BdeCfgpFree@@YAXPEAX@Z`
- size: `39`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180007070`
- `0x180007470`
- `0x180007bd0`
- `0x1800080f0`
- `0x1800083c4`
- `0x1800086f8`
- `0x180009000`
- `0x1800093e0`

## callees

- `0x180008e1c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180008e29`
- `KERNEL32!GetProcessHeap` at `0x180008e29`
- `KERNEL32!HeapFree` at `0x180008e37`
- `KERNEL32!HeapFree` at `0x180008e37`

## pseudocode

```c
void __fastcall BdeCfgpFree(void *lpMem)
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
0x180008e1c  test    rcx, rcx
0x180008e1f  jz      short locret_180008E42
0x180008e21  push    rbx
0x180008e22  sub     rsp, 20h
0x180008e26  mov     rbx, rcx
0x180008e29  call    cs:__imp_GetProcessHeap
0x180008e2f  mov     r8, rbx; lpMem
0x180008e32  xor     edx, edx; dwFlags
0x180008e34  mov     rcx, rax; hHeap
0x180008e37  call    cs:__imp_HeapFree
0x180008e3d  add     rsp, 20h
0x180008e41  pop     rbx
0x180008e42  retn
```
