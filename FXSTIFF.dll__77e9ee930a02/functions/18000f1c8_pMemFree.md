# pMemFree

- ea: `0x18000f1c8`
- end: `0x18000f204`
- name: `pMemFree`
- size: `60`
- prototype: `void __fastcall(LPVOID lpMem)`
- caller_count: `26`
- callee_count: `2`
- tags: ``

## callers

- `0x180004050`
- `0x18000438c`
- `0x180004420`
- `0x180004f30`
- `0x180005ed0`
- `0x180006bb0`
- `0x180007fd0`
- `0x180008070`
- `0x180008b70`
- `0x180009600`
- `0x180009d40`
- `0x18000e268`
- `0x18000e784`
- `0x18000f20c`
- `0x18000f550`
- `0x18000f710`
- `0x180016ff0`
- `0x180017098`
- `0x18001716c`
- `0x180017618`
- `0x180017744`
- `0x180017aa0`
- `0x180017cb0`
- `0x180018000`
- `0x180018130`
- `0x180018580`

## callees

- `0x18000f1c8`
- `0x180019010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000f1f2`
- `KERNEL32!HeapFree` at `0x18000f1f2`

## pseudocode

```c
void __fastcall pMemFree(LPVOID lpMem)
{
  if ( lpMem )
  {
    if ( pMemFreeUser )
      pMemFreeUser(lpMem);
    else
      HeapFree(hHeap, 0, lpMem);
  }
}

```

## disassembly

```asm
0x18000f1c8  sub     rsp, 28h
0x18000f1cc  test    rcx, rcx
0x18000f1cf  jz      short loc_18000F1FE
0x18000f1d1  mov     rax, cs:?pMemFreeUser@@3P6AXPEAX@ZEA; void (*pMemFreeUser)(void *)
0x18000f1d8  test    rax, rax
0x18000f1db  jz      short loc_18000F1E6
0x18000f1dd  add     rsp, 28h
0x18000f1e1  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1e6  mov     r8, rcx; lpMem
0x18000f1e9  xor     edx, edx; dwFlags
0x18000f1eb  mov     rcx, cs:hHeap; hHeap
0x18000f1f2  call    cs:__imp_HeapFree
0x18000f1f9  nop     dword ptr [rax+rax+00h]
0x18000f1fe  add     rsp, 28h
0x18000f202  retn
```
