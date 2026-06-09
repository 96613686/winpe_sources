# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180009d24`
- end: `0x180009db1`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180009944`
- `0x18000d220`
- `0x18000dbd0`
- `0x1800118ee`

## callees

- `0x180009d24`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009d56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009d7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009da0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009d56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009d7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009da0`

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
0x180009d24  mov     [rsp+arg_0], rbx
0x180009d29  push    rdi
0x180009d2a  sub     rsp, 20h
0x180009d2e  mov     rdi, [rcx+0B0h]
0x180009d35  mov     rbx, rcx
0x180009d38  mov     qword ptr [rcx+0B0h], 0
0x180009d43  test    rdi, rdi
0x180009d46  jz      short loc_180009D5C
0x180009d48  call    cs:__imp_GetProcessHeap
0x180009d4e  mov     r8, rdi; lpMem
0x180009d51  xor     edx, edx; dwFlags
0x180009d53  mov     rcx, rax; hHeap
0x180009d56  call    cs:__imp_HeapFree
0x180009d5c  mov     rdi, [rbx+70h]
0x180009d60  mov     qword ptr [rbx+70h], 0
0x180009d68  test    rdi, rdi
0x180009d6b  jz      short loc_180009D81
0x180009d6d  call    cs:__imp_GetProcessHeap
0x180009d73  mov     r8, rdi; lpMem
0x180009d76  xor     edx, edx; dwFlags
0x180009d78  mov     rcx, rax; hHeap
0x180009d7b  call    cs:__imp_HeapFree
0x180009d81  mov     rdi, [rbx+30h]
0x180009d85  mov     qword ptr [rbx+30h], 0
0x180009d8d  test    rdi, rdi
0x180009d90  jz      short loc_180009DA6
0x180009d92  call    cs:__imp_GetProcessHeap
0x180009d98  mov     r8, rdi; lpMem
0x180009d9b  xor     edx, edx; dwFlags
0x180009d9d  mov     rcx, rax; hHeap
0x180009da0  call    cs:__imp_HeapFree
0x180009da6  mov     rbx, [rsp+28h+arg_0]
0x180009dab  add     rsp, 20h
0x180009daf  pop     rdi
0x180009db0  retn
```
