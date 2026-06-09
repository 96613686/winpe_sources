# operator delete(void *)

- ea: `0x1800026f0`
- end: `0x180002717`
- name: `??3@YAXPEAX@Z`
- size: `39`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `17`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002b48`
- `0x1800068e0`
- `0x180007350`
- `0x180007390`
- `0x180007950`
- `0x180008e50`
- `0x180008e90`
- `0x180008ed0`
- `0x180008f10`
- `0x180008f50`
- `0x18000af60`
- `0x18000cf10`
- `0x18000d5a4`
- `0x18000eee0`
- `0x18000f1c0`
- `0x18000f1d2`
- `0x18000f53d`

## callees

- `0x1800026f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000270b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000270b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800026fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800026fd`

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
0x1800026f0  test    rcx, rcx
0x1800026f3  jz      short locret_180002716
0x1800026f5  push    rbx
0x1800026f6  sub     rsp, 20h
0x1800026fa  mov     rbx, rcx
0x1800026fd  call    cs:__imp_GetProcessHeap
0x180002703  mov     r8, rbx; lpMem
0x180002706  xor     edx, edx; dwFlags
0x180002708  mov     rcx, rax; hHeap
0x18000270b  call    cs:__imp_HeapFree
0x180002711  add     rsp, 20h
0x180002715  pop     rbx
0x180002716  retn
```
