# pMemFree

- ea: `0x18002bb58`
- end: `0x18002bb94`
- name: `pMemFree`
- size: `60`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `152`
- callee_count: `2`
- tags: ``

## callers

- `0x180004394`
- `0x180004c3c`
- `0x180006308`
- `0x180009dd0`
- `0x18000a140`
- `0x18000a700`
- `0x18000aa00`
- `0x18000b4f0`
- `0x18000b960`
- `0x18000bf50`
- `0x18000c0d0`
- `0x18000c530`
- `0x18000c670`
- `0x18000c9a0`
- `0x18000cb20`
- `0x18000ceb0`
- `0x18000d130`
- `0x18000d560`
- `0x18000d680`
- `0x18000d900`
- `0x18000da10`
- `0x18000e040`
- `0x18000e170`
- `0x18000e400`
- `0x18000e550`
- `0x18000e830`
- `0x18000eb50`
- `0x18000ed50`
- `0x18000f540`
- `0x18000f6a0`
- `0x18000fd80`
- `0x18000fee0`
- `0x180010650`
- `0x180010b20`
- `0x180010f80`
- `0x180011640`
- `0x180011b60`
- `0x180011ed0`
- `0x180012260`
- `0x180012760`
- `0x1800129e0`
- `0x180012e20`
- `0x1800133d0`
- `0x180013d30`
- `0x180014fb0`
- `0x180015040`
- `0x1800154f0`
- `0x180015690`
- `0x18001618c`
- `0x180016964`

## callees

- `0x18002bb58`
- `0x18003e010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002bb82`
- `KERNEL32!HeapFree` at `0x18002bb82`

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
0x18002bb58  sub     rsp, 28h
0x18002bb5c  test    rcx, rcx
0x18002bb5f  jz      short loc_18002BB8E
0x18002bb61  mov     rax, cs:?pMemFreeUser@@3P6AXPEAX@ZEA; void (*pMemFreeUser)(void *)
0x18002bb68  test    rax, rax
0x18002bb6b  jz      short loc_18002BB76
0x18002bb6d  add     rsp, 28h
0x18002bb71  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb76  mov     r8, rcx; lpMem
0x18002bb79  xor     edx, edx; dwFlags
0x18002bb7b  mov     rcx, cs:hHeap; hHeap
0x18002bb82  call    cs:__imp_HeapFree
0x18002bb89  nop     dword ptr [rax+rax+00h]
0x18002bb8e  add     rsp, 28h
0x18002bb92  retn
```
