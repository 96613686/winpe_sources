# I_ReaderListFreeItem

- ea: `0x180017178`
- end: `0x1800171bb`
- name: `I_ReaderListFreeItem`
- size: `67`
- prototype: `BOOL __fastcall(LPVOID *lpMem)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001714c`
- `0x18001ae54`
- `0x18001c158`

## callees

- `0x180017178`
- `0x1800171c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001719d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800171af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001719d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800171af`

## pseudocode

```c
BOOL __fastcall I_ReaderListFreeItem(LPVOID *lpMem)
{
  BOOL result; // eax

  if ( lpMem )
  {
    I_ReaderListFreeItemCommon(lpMem, 0);
    if ( *lpMem )
      HeapFree(hHeap, 0, *lpMem);
    return HeapFree(hHeap, 0, lpMem);
  }
  return result;
}

```

## disassembly

```asm
0x180017178  test    rcx, rcx
0x18001717b  jz      short locret_1800171BA
0x18001717d  push    rbx
0x18001717e  sub     rsp, 20h
0x180017182  xor     edx, edx
0x180017184  mov     rbx, rcx
0x180017187  call    I_ReaderListFreeItemCommon
0x18001718c  mov     r8, [rbx]; lpMem
0x18001718f  test    r8, r8
0x180017192  jz      short loc_1800171A3
0x180017194  mov     rcx, cs:hHeap; hHeap
0x18001719b  xor     edx, edx; dwFlags
0x18001719d  call    cs:__imp_HeapFree
0x1800171a3  mov     rcx, cs:hHeap; hHeap
0x1800171aa  mov     r8, rbx; lpMem
0x1800171ad  xor     edx, edx; dwFlags
0x1800171af  call    cs:__imp_HeapFree
0x1800171b5  add     rsp, 20h
0x1800171b9  pop     rbx
0x1800171ba  retn
```
