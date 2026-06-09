# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180003608`
- end: `0x180003695`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003194`
- `0x180005f80`
- `0x180006a90`
- `0x18000f730`

## callees

- `0x180003608`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000363a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000365f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003684`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000363a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000365f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003684`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000362c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003651`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003676`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000362c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003651`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003676`

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
0x180003608  mov     [rsp+arg_0], rbx
0x18000360d  push    rdi
0x18000360e  sub     rsp, 20h
0x180003612  mov     rdi, [rcx+0B0h]
0x180003619  mov     rbx, rcx
0x18000361c  mov     qword ptr [rcx+0B0h], 0
0x180003627  test    rdi, rdi
0x18000362a  jz      short loc_180003640
0x18000362c  call    cs:__imp_GetProcessHeap
0x180003632  mov     r8, rdi; lpMem
0x180003635  xor     edx, edx; dwFlags
0x180003637  mov     rcx, rax; hHeap
0x18000363a  call    cs:__imp_HeapFree
0x180003640  mov     rdi, [rbx+70h]
0x180003644  mov     qword ptr [rbx+70h], 0
0x18000364c  test    rdi, rdi
0x18000364f  jz      short loc_180003665
0x180003651  call    cs:__imp_GetProcessHeap
0x180003657  mov     r8, rdi; lpMem
0x18000365a  xor     edx, edx; dwFlags
0x18000365c  mov     rcx, rax; hHeap
0x18000365f  call    cs:__imp_HeapFree
0x180003665  mov     rdi, [rbx+30h]
0x180003669  mov     qword ptr [rbx+30h], 0
0x180003671  test    rdi, rdi
0x180003674  jz      short loc_18000368A
0x180003676  call    cs:__imp_GetProcessHeap
0x18000367c  mov     r8, rdi; lpMem
0x18000367f  xor     edx, edx; dwFlags
0x180003681  mov     rcx, rax; hHeap
0x180003684  call    cs:__imp_HeapFree
0x18000368a  mov     rbx, [rsp+28h+arg_0]
0x18000368f  add     rsp, 20h
0x180003693  pop     rdi
0x180003694  retn
```
