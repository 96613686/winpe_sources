# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x1800030e4`
- end: `0x180003171`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d94`
- `0x180005d60`
- `0x180006814`

## callees

- `0x1800030e4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003116`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000313b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003160`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003116`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000313b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003160`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003108`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000312d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003152`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003108`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000312d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003152`

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
0x1800030e4  mov     [rsp+arg_0], rbx
0x1800030e9  push    rdi
0x1800030ea  sub     rsp, 20h
0x1800030ee  mov     rdi, [rcx+0B0h]
0x1800030f5  mov     rbx, rcx
0x1800030f8  mov     qword ptr [rcx+0B0h], 0
0x180003103  test    rdi, rdi
0x180003106  jz      short loc_18000311C
0x180003108  call    cs:__imp_GetProcessHeap
0x18000310e  mov     r8, rdi; lpMem
0x180003111  xor     edx, edx; dwFlags
0x180003113  mov     rcx, rax; hHeap
0x180003116  call    cs:__imp_HeapFree
0x18000311c  mov     rdi, [rbx+70h]
0x180003120  mov     qword ptr [rbx+70h], 0
0x180003128  test    rdi, rdi
0x18000312b  jz      short loc_180003141
0x18000312d  call    cs:__imp_GetProcessHeap
0x180003133  mov     r8, rdi; lpMem
0x180003136  xor     edx, edx; dwFlags
0x180003138  mov     rcx, rax; hHeap
0x18000313b  call    cs:__imp_HeapFree
0x180003141  mov     rdi, [rbx+30h]
0x180003145  mov     qword ptr [rbx+30h], 0
0x18000314d  test    rdi, rdi
0x180003150  jz      short loc_180003166
0x180003152  call    cs:__imp_GetProcessHeap
0x180003158  mov     r8, rdi; lpMem
0x18000315b  xor     edx, edx; dwFlags
0x18000315d  mov     rcx, rax; hHeap
0x180003160  call    cs:__imp_HeapFree
0x180003166  mov     rbx, [rsp+28h+arg_0]
0x18000316b  add     rsp, 20h
0x18000316f  pop     rdi
0x180003170  retn
```
