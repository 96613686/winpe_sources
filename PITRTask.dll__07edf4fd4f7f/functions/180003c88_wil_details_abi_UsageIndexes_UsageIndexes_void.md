# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180003c88`
- end: `0x180003d15`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003898`
- `0x18000722c`
- `0x180007a00`
- `0x180010c0c`

## callees

- `0x180003c88`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cd1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cf6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cd1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cf6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cdf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cdf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d04`

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
0x180003c88  mov     [rsp+arg_0], rbx
0x180003c8d  push    rdi
0x180003c8e  sub     rsp, 20h
0x180003c92  mov     rdi, [rcx+0B0h]
0x180003c99  mov     rbx, rcx
0x180003c9c  mov     qword ptr [rcx+0B0h], 0
0x180003ca7  test    rdi, rdi
0x180003caa  jz      short loc_180003CC0
0x180003cac  call    cs:__imp_GetProcessHeap
0x180003cb2  mov     r8, rdi; lpMem
0x180003cb5  xor     edx, edx; dwFlags
0x180003cb7  mov     rcx, rax; hHeap
0x180003cba  call    cs:__imp_HeapFree
0x180003cc0  mov     rdi, [rbx+70h]
0x180003cc4  mov     qword ptr [rbx+70h], 0
0x180003ccc  test    rdi, rdi
0x180003ccf  jz      short loc_180003CE5
0x180003cd1  call    cs:__imp_GetProcessHeap
0x180003cd7  mov     r8, rdi; lpMem
0x180003cda  xor     edx, edx; dwFlags
0x180003cdc  mov     rcx, rax; hHeap
0x180003cdf  call    cs:__imp_HeapFree
0x180003ce5  mov     rdi, [rbx+30h]
0x180003ce9  mov     qword ptr [rbx+30h], 0
0x180003cf1  test    rdi, rdi
0x180003cf4  jz      short loc_180003D0A
0x180003cf6  call    cs:__imp_GetProcessHeap
0x180003cfc  mov     r8, rdi; lpMem
0x180003cff  xor     edx, edx; dwFlags
0x180003d01  mov     rcx, rax; hHeap
0x180003d04  call    cs:__imp_HeapFree
0x180003d0a  mov     rbx, [rsp+28h+arg_0]
0x180003d0f  add     rsp, 20h
0x180003d13  pop     rdi
0x180003d14  retn
```
