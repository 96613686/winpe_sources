# operator delete(void *)

- ea: `0x1800070f4`
- end: `0x18000711b`
- name: `??3@YAXPEAX@Z`
- size: `39`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `20`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800011a0`
- `0x1800011e0`
- `0x180001930`
- `0x180001d90`
- `0x180001dbc`
- `0x180001eb0`
- `0x180002d70`
- `0x180002f90`
- `0x1800032f0`
- `0x180003470`
- `0x180003a30`
- `0x180003a70`
- `0x180003d28`
- `0x180003fb0`
- `0x180004074`
- `0x1800049f4`
- `0x180006150`
- `0x180006980`
- `0x18000ac04`
- `0x18000ac16`

## callees

- `0x1800070f4`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000710f`
- `KERNEL32!HeapFree` at `0x18000710f`
- `KERNEL32!GetProcessHeap` at `0x180007101`
- `KERNEL32!GetProcessHeap` at `0x180007101`

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
0x1800070f4  test    rcx, rcx
0x1800070f7  jz      short locret_18000711A
0x1800070f9  push    rbx
0x1800070fa  sub     rsp, 20h
0x1800070fe  mov     rbx, rcx
0x180007101  call    cs:__imp_GetProcessHeap
0x180007107  mov     r8, rbx; lpMem
0x18000710a  xor     edx, edx; dwFlags
0x18000710c  mov     rcx, rax; hHeap
0x18000710f  call    cs:__imp_HeapFree
0x180007115  add     rsp, 20h
0x180007119  pop     rbx
0x18000711a  retn
```
