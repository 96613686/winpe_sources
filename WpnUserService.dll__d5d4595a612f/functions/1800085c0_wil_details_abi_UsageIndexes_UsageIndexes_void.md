# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x1800085c0`
- end: `0x18000864d`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800082bc`
- `0x18000ac3c`
- `0x18000ba74`
- `0x18001105c`

## callees

- `0x1800085c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800085f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008617`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000863c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800085f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008617`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000863c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800085e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008609`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000862e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800085e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008609`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000862e`

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
0x1800085c0  mov     [rsp+arg_0], rbx
0x1800085c5  push    rdi
0x1800085c6  sub     rsp, 20h
0x1800085ca  mov     rdi, [rcx+0B0h]
0x1800085d1  mov     rbx, rcx
0x1800085d4  mov     qword ptr [rcx+0B0h], 0
0x1800085df  test    rdi, rdi
0x1800085e2  jz      short loc_1800085F8
0x1800085e4  call    cs:__imp_GetProcessHeap
0x1800085ea  mov     r8, rdi; lpMem
0x1800085ed  xor     edx, edx; dwFlags
0x1800085ef  mov     rcx, rax; hHeap
0x1800085f2  call    cs:__imp_HeapFree
0x1800085f8  mov     rdi, [rbx+70h]
0x1800085fc  mov     qword ptr [rbx+70h], 0
0x180008604  test    rdi, rdi
0x180008607  jz      short loc_18000861D
0x180008609  call    cs:__imp_GetProcessHeap
0x18000860f  mov     r8, rdi; lpMem
0x180008612  xor     edx, edx; dwFlags
0x180008614  mov     rcx, rax; hHeap
0x180008617  call    cs:__imp_HeapFree
0x18000861d  mov     rdi, [rbx+30h]
0x180008621  mov     qword ptr [rbx+30h], 0
0x180008629  test    rdi, rdi
0x18000862c  jz      short loc_180008642
0x18000862e  call    cs:__imp_GetProcessHeap
0x180008634  mov     r8, rdi; lpMem
0x180008637  xor     edx, edx; dwFlags
0x180008639  mov     rcx, rax; hHeap
0x18000863c  call    cs:__imp_HeapFree
0x180008642  mov     rbx, [rsp+28h+arg_0]
0x180008647  add     rsp, 20h
0x18000864b  pop     rdi
0x18000864c  retn
```
