# SIDKeyProvAlloc(unsigned __int64)

- ea: `0x180010920`
- end: `0x180010946`
- name: `?SIDKeyProvAlloc@@YAPEAX_K@Z`
- size: `38`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `56`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x180002888`
- `0x180002a5c`
- `0x180002b28`
- `0x180002bf0`
- `0x180003160`
- `0x1800035a0`
- `0x1800038c0`
- `0x18000398c`
- `0x180003b1c`
- `0x180004350`
- `0x180004568`
- `0x180004624`
- `0x180004a00`
- `0x1800054e0`
- `0x180005934`
- `0x180005a24`
- `0x180006564`
- `0x180006908`
- `0x180006fb0`
- `0x180007354`
- `0x180008240`
- `0x180008570`
- `0x180009e04`
- `0x18000a878`
- `0x18000aef0`
- `0x18000b758`
- `0x18000b960`
- `0x18000bb30`
- `0x18000bd0c`
- `0x18000be6c`
- `0x18000bfd8`
- `0x18000c1fc`
- `0x18000ce40`
- `0x18000d6a0`
- `0x18000d9d0`
- `0x18000da88`
- `0x18000dc90`
- `0x18000de80`
- `0x18000dfc0`
- `0x18000e644`
- `0x18000eab8`
- `0x18000f1a8`
- `0x18000f47c`
- `0x18000fe30`
- `0x180010130`
- `0x180010304`
- `0x1800107e0`
- `0x180010850`
- `0x180010dcc`
- `0x180016b30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001093f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010929`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010929`

## pseudocode

```c
LPVOID __fastcall SIDKeyProvAlloc(SIZE_T a1)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  return HeapAlloc(ProcessHeap, 8u, a1);
}

```

## disassembly

```asm
0x180010920  push    rbx
0x180010922  sub     rsp, 20h
0x180010926  mov     rbx, rcx
0x180010929  call    cs:__imp_GetProcessHeap
0x18001092f  mov     r8, rbx
0x180010932  mov     edx, 8
0x180010937  mov     rcx, rax
0x18001093a  add     rsp, 20h
0x18001093e  pop     rbx
0x18001093f  jmp     cs:__imp_HeapAlloc
```
