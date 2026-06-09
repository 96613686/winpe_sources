# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x1800039e4`
- end: `0x180003a71`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003570`
- `0x180006320`
- `0x180006e30`
- `0x18000e64b`

## callees

- `0x1800039e4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a16`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a16`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a60`

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
0x1800039e4  mov     [rsp+arg_0], rbx
0x1800039e9  push    rdi
0x1800039ea  sub     rsp, 20h
0x1800039ee  mov     rdi, [rcx+0B0h]
0x1800039f5  mov     rbx, rcx
0x1800039f8  mov     qword ptr [rcx+0B0h], 0
0x180003a03  test    rdi, rdi
0x180003a06  jz      short loc_180003A1C
0x180003a08  call    cs:__imp_GetProcessHeap
0x180003a0e  mov     r8, rdi; lpMem
0x180003a11  xor     edx, edx; dwFlags
0x180003a13  mov     rcx, rax; hHeap
0x180003a16  call    cs:__imp_HeapFree
0x180003a1c  mov     rdi, [rbx+70h]
0x180003a20  mov     qword ptr [rbx+70h], 0
0x180003a28  test    rdi, rdi
0x180003a2b  jz      short loc_180003A41
0x180003a2d  call    cs:__imp_GetProcessHeap
0x180003a33  mov     r8, rdi; lpMem
0x180003a36  xor     edx, edx; dwFlags
0x180003a38  mov     rcx, rax; hHeap
0x180003a3b  call    cs:__imp_HeapFree
0x180003a41  mov     rdi, [rbx+30h]
0x180003a45  mov     qword ptr [rbx+30h], 0
0x180003a4d  test    rdi, rdi
0x180003a50  jz      short loc_180003A66
0x180003a52  call    cs:__imp_GetProcessHeap
0x180003a58  mov     r8, rdi; lpMem
0x180003a5b  xor     edx, edx; dwFlags
0x180003a5d  mov     rcx, rax; hHeap
0x180003a60  call    cs:__imp_HeapFree
0x180003a66  mov     rbx, [rsp+28h+arg_0]
0x180003a6b  add     rsp, 20h
0x180003a6f  pop     rdi
0x180003a70  retn
```
