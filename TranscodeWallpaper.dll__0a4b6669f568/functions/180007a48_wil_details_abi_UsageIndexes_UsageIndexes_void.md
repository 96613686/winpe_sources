# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180007a48`
- end: `0x180007ad5`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180007744`
- `0x180009174`
- `0x180009c34`
- `0x18000e707`

## callees

- `0x180007a48`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ab6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ab6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a7a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ac4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a7a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ac4`

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
0x180007a48  mov     [rsp+arg_0], rbx
0x180007a4d  push    rdi
0x180007a4e  sub     rsp, 20h
0x180007a52  mov     rdi, [rcx+0B0h]
0x180007a59  mov     rbx, rcx
0x180007a5c  mov     qword ptr [rcx+0B0h], 0
0x180007a67  test    rdi, rdi
0x180007a6a  jz      short loc_180007A80
0x180007a6c  call    cs:__imp_GetProcessHeap
0x180007a72  mov     r8, rdi; lpMem
0x180007a75  xor     edx, edx; dwFlags
0x180007a77  mov     rcx, rax; hHeap
0x180007a7a  call    cs:__imp_HeapFree
0x180007a80  mov     rdi, [rbx+70h]
0x180007a84  mov     qword ptr [rbx+70h], 0
0x180007a8c  test    rdi, rdi
0x180007a8f  jz      short loc_180007AA5
0x180007a91  call    cs:__imp_GetProcessHeap
0x180007a97  mov     r8, rdi; lpMem
0x180007a9a  xor     edx, edx; dwFlags
0x180007a9c  mov     rcx, rax; hHeap
0x180007a9f  call    cs:__imp_HeapFree
0x180007aa5  mov     rdi, [rbx+30h]
0x180007aa9  mov     qword ptr [rbx+30h], 0
0x180007ab1  test    rdi, rdi
0x180007ab4  jz      short loc_180007ACA
0x180007ab6  call    cs:__imp_GetProcessHeap
0x180007abc  mov     r8, rdi; lpMem
0x180007abf  xor     edx, edx; dwFlags
0x180007ac1  mov     rcx, rax; hHeap
0x180007ac4  call    cs:__imp_HeapFree
0x180007aca  mov     rbx, [rsp+28h+arg_0]
0x180007acf  add     rsp, 20h
0x180007ad3  pop     rdi
0x180007ad4  retn
```
