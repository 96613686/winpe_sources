# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x18000477c`
- end: `0x180004809`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004308`
- `0x180007560`
- `0x18000807c`
- `0x18001802f`

## callees

- `0x18000477c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800047ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800047d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800047f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800047ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800047d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800047f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047ea`

## pseudocode

```c
void __fastcall wil::details_abi::UsageIndexes::~UsageIndexes(wil::details_abi::UsageIndexes *this)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax
  void *v4; // rdi
  HANDLE v5; // rax
  void *v6; // rdi
  HANDLE v7; // rax

  v1 = (void *)*((_QWORD *)this + 22);
  *((_QWORD *)this + 22) = 0;
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
  v4 = (void *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = 0;
  if ( v4 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v4);
  }
  v6 = (void *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
  }
}

```

## disassembly

```asm
0x18000477c  mov     [rsp+arg_0], rbx
0x180004781  push    rdi
0x180004782  sub     rsp, 20h
0x180004786  mov     rdi, [rcx+0B0h]
0x18000478d  mov     rbx, rcx
0x180004790  mov     qword ptr [rcx+0B0h], 0
0x18000479b  test    rdi, rdi
0x18000479e  jz      short loc_1800047B4
0x1800047a0  call    cs:__imp_GetProcessHeap
0x1800047a6  mov     r8, rdi; lpMem
0x1800047a9  xor     edx, edx; dwFlags
0x1800047ab  mov     rcx, rax; hHeap
0x1800047ae  call    cs:__imp_HeapFree
0x1800047b4  mov     rdi, [rbx+70h]
0x1800047b8  mov     qword ptr [rbx+70h], 0
0x1800047c0  test    rdi, rdi
0x1800047c3  jz      short loc_1800047D9
0x1800047c5  call    cs:__imp_GetProcessHeap
0x1800047cb  mov     r8, rdi; lpMem
0x1800047ce  xor     edx, edx; dwFlags
0x1800047d0  mov     rcx, rax; hHeap
0x1800047d3  call    cs:__imp_HeapFree
0x1800047d9  mov     rdi, [rbx+30h]
0x1800047dd  mov     qword ptr [rbx+30h], 0
0x1800047e5  test    rdi, rdi
0x1800047e8  jz      short loc_1800047FE
0x1800047ea  call    cs:__imp_GetProcessHeap
0x1800047f0  mov     r8, rdi; lpMem
0x1800047f3  xor     edx, edx; dwFlags
0x1800047f5  mov     rcx, rax; hHeap
0x1800047f8  call    cs:__imp_HeapFree
0x1800047fe  mov     rbx, [rsp+28h+arg_0]
0x180004803  add     rsp, 20h
0x180004807  pop     rdi
0x180004808  retn
```
