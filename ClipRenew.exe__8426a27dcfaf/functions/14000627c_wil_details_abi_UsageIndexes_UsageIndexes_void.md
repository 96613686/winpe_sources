# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x14000627c`
- end: `0x140006309`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140005f0c`
- `0x1400104d0`
- `0x140010e70`

## callees

- `0x14000627c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400062a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400062c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400062ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400062a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400062c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400062ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400062ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400062d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400062f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400062ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400062d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400062f8`

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
0x14000627c  mov     [rsp+arg_0], rbx
0x140006281  push    rdi
0x140006282  sub     rsp, 20h
0x140006286  mov     rdi, [rcx+0B0h]
0x14000628d  mov     rbx, rcx
0x140006290  mov     qword ptr [rcx+0B0h], 0
0x14000629b  test    rdi, rdi
0x14000629e  jz      short loc_1400062B4
0x1400062a0  call    cs:__imp_GetProcessHeap
0x1400062a6  mov     r8, rdi; lpMem
0x1400062a9  xor     edx, edx; dwFlags
0x1400062ab  mov     rcx, rax; hHeap
0x1400062ae  call    cs:__imp_HeapFree
0x1400062b4  mov     rdi, [rbx+70h]
0x1400062b8  mov     qword ptr [rbx+70h], 0
0x1400062c0  test    rdi, rdi
0x1400062c3  jz      short loc_1400062D9
0x1400062c5  call    cs:__imp_GetProcessHeap
0x1400062cb  mov     r8, rdi; lpMem
0x1400062ce  xor     edx, edx; dwFlags
0x1400062d0  mov     rcx, rax; hHeap
0x1400062d3  call    cs:__imp_HeapFree
0x1400062d9  mov     rdi, [rbx+30h]
0x1400062dd  mov     qword ptr [rbx+30h], 0
0x1400062e5  test    rdi, rdi
0x1400062e8  jz      short loc_1400062FE
0x1400062ea  call    cs:__imp_GetProcessHeap
0x1400062f0  mov     r8, rdi; lpMem
0x1400062f3  xor     edx, edx; dwFlags
0x1400062f5  mov     rcx, rax; hHeap
0x1400062f8  call    cs:__imp_HeapFree
0x1400062fe  mov     rbx, [rsp+28h+arg_0]
0x140006303  add     rsp, 20h
0x140006307  pop     rdi
0x140006308  retn
```
