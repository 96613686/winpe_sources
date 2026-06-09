# HfCreateFactory

- ea: `0x180008150`
- end: `0x1800081ba`
- name: `HfCreateFactory`
- size: `106`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003920`

## callees

- `0x180007120`
- `0x180008150`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008196`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008196`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000815d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008188`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000815d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008188`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000816e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000816e`

## pseudocode

```c
__int64 __fastcall HfCreateFactory(__int64 a1, _QWORD *a2)
{
  HANDLE ProcessHeap; // rax
  LPVOID v4; // rax
  void *v5; // rbx
  HANDLE v6; // rax

  ProcessHeap = GetProcessHeap();
  v4 = HeapAlloc(ProcessHeap, 0, 0x88u);
  v5 = v4;
  if ( !v4 )
    goto LABEL_4;
  if ( (unsigned int)constructHandleFactory(v4) )
  {
    v6 = GetProcessHeap();
    HeapFree(v6, 0, v5);
LABEL_4:
    *a2 = 0;
    return 8;
  }
  *a2 = v5;
  return 0;
}

```

## disassembly

```asm
0x180008150  mov     [rsp+arg_0], rbx
0x180008155  push    rdi
0x180008156  sub     rsp, 20h
0x18000815a  mov     rdi, rdx
0x18000815d  call    cs:__imp_GetProcessHeap
0x180008163  xor     edx, edx; dwFlags
0x180008165  mov     r8d, 88h; dwBytes
0x18000816b  mov     rcx, rax; hHeap
0x18000816e  call    cs:__imp_HeapAlloc
0x180008174  mov     rbx, rax
0x180008177  test    rax, rax
0x18000817a  jz      short loc_18000819C
0x18000817c  mov     rcx, rax
0x18000817f  call    constructHandleFactory
0x180008184  test    eax, eax
0x180008186  jz      short loc_1800081B3
0x180008188  call    cs:__imp_GetProcessHeap
0x18000818e  mov     r8, rbx; lpMem
0x180008191  xor     edx, edx; dwFlags
0x180008193  mov     rcx, rax; hHeap
0x180008196  call    cs:__imp_HeapFree
0x18000819c  mov     qword ptr [rdi], 0
0x1800081a3  mov     eax, 8
0x1800081a8  mov     rbx, [rsp+28h+arg_0]
0x1800081ad  add     rsp, 20h
0x1800081b1  pop     rdi
0x1800081b2  retn
0x1800081b3  mov     [rdi], rbx
0x1800081b6  xor     eax, eax
0x1800081b8  jmp     short loc_1800081A8
```
