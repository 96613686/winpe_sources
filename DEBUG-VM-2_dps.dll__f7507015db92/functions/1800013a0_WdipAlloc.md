# WdipAlloc

- ea: `0x1800013a0`
- end: `0x1800013c6`
- name: `WdipAlloc`
- size: `38`
- prototype: ``
- caller_count: `43`
- callee_count: `0`
- tags: ``

## callers

- `0x180001100`
- `0x180001830`
- `0x180002510`
- `0x180003020`
- `0x180004de4`
- `0x1800065b8`
- `0x180007adc`
- `0x180007e90`
- `0x1800083a8`
- `0x180008474`
- `0x18000934c`
- `0x1800096c0`
- `0x18000b2d0`
- `0x18000b6d8`
- `0x18000b7ec`
- `0x18000bdf4`
- `0x18000c21c`
- `0x18000c9cc`
- `0x18000ce94`
- `0x18000d880`
- `0x18000de94`
- `0x18000e4c8`
- `0x18000e9d4`
- `0x18000ed8c`
- `0x18000f534`
- `0x180010a00`
- `0x18001116c`
- `0x180011274`
- `0x180011580`
- `0x180011714`
- `0x1800118f0`
- `0x180011c6c`
- `0x180011eec`
- `0x180011fd4`
- `0x18001246c`
- `0x180013214`
- `0x180013b4c`
- `0x180014df0`
- `0x180016914`
- `0x1800178a8`
- `0x180017b20`
- `0x180017d7c`
- `0x180018680`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800013a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800013a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800013bf`

## pseudocode

```c
LPVOID __fastcall WdipAlloc(SIZE_T a1)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  return HeapAlloc(ProcessHeap, 8u, a1);
}

```

## disassembly

```asm
0x1800013a0  push    rbx
0x1800013a2  sub     rsp, 20h
0x1800013a6  mov     rbx, rcx
0x1800013a9  call    cs:__imp_GetProcessHeap
0x1800013af  mov     r8, rbx
0x1800013b2  mov     edx, 8
0x1800013b7  mov     rcx, rax
0x1800013ba  add     rsp, 20h
0x1800013be  pop     rbx
0x1800013bf  jmp     cs:__imp_HeapAlloc
```
