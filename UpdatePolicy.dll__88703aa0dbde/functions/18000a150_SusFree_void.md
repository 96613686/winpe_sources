# SusFree(void *)

- ea: `0x18000a150`
- end: `0x18000a177`
- name: `?SusFree@@YAXPEAX@Z`
- size: `39`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003914`
- `0x18000d538`
- `0x18000d7f0`
- `0x18000e488`
- `0x18000e8a8`
- `0x180016bb0`

## callees

- `0x18000a150`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a15d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a15d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a16b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a16b`

## pseudocode

```c
void __fastcall SusFree(void *lpMem)
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
0x18000a150  test    rcx, rcx
0x18000a153  jz      short locret_18000A176
0x18000a155  push    rbx
0x18000a156  sub     rsp, 20h
0x18000a15a  mov     rbx, rcx
0x18000a15d  call    cs:__imp_GetProcessHeap
0x18000a163  mov     r8, rbx; lpMem
0x18000a166  xor     edx, edx; dwFlags
0x18000a168  mov     rcx, rax; hHeap
0x18000a16b  call    cs:__imp_HeapFree
0x18000a171  add     rsp, 20h
0x18000a175  pop     rbx
0x18000a176  retn
```
