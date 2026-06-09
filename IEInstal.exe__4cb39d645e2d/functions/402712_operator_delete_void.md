# operator delete(void *)

- ea: `0x402712`
- end: `0x402731`
- name: `??3@YAXPAX@Z`
- size: `31`
- prototype: `void __cdecl(void *lpMem)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x402c40`
- `0x404864`
- `0x405a14`
- `0x405ba0`
- `0x405be0`
- `0x405c60`
- `0x408d50`
- `0x40eb05`

## callees

- `0x402712`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x402722`
- `KERNEL32!GetProcessHeap` at `0x402722`
- `KERNEL32!HeapFree` at `0x402729`
- `KERNEL32!HeapFree` at `0x402729`

## pseudocode

```c
void __cdecl operator delete(void *lpMem)
{
  HANDLE ProcessHeap; // eax

  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
}

```

## disassembly

```asm
0x402712  mov     edi, edi
0x402714  push    ebp
0x402715  mov     ebp, esp
0x402717  cmp     [ebp+lpMem], 0
0x40271b  jz      short loc_40272F
0x40271d  push    [ebp+lpMem]; lpMem
0x402720  push    0; dwFlags
0x402722  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x402728  push    eax; hHeap
0x402729  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x40272f  pop     ebp
0x402730  retn
```
