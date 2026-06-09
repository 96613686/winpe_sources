# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800034e0`
- end: `0x18000355c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800030c8`

## callees

- `0x1800034e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003505`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003536`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003505`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003536`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003513`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003544`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003513`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003544`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::~ThreadLocalData(wil::details_abi::ThreadLocalData *this)
{
  __int64 v2; // rdi
  __int64 v3; // rbp
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  void *v6; // rbx
  HANDLE v7; // rax

  v2 = *((_QWORD *)this + 3);
  v3 = v2 + 80LL * *((unsigned __int16 *)this + 16);
  while ( v2 != v3 )
  {
    v4 = *(void **)(v2 + 64);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    *(_QWORD *)(v2 + 64) = 0;
    *(_QWORD *)(v2 + 72) = 0;
    v2 += 80;
  }
  v6 = (void *)*((_QWORD *)this + 3);
  v7 = GetProcessHeap();
  HeapFree(v7, 0, v6);
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x1800034e0  push    rbx
0x1800034e2  push    rbp
0x1800034e3  push    rsi
0x1800034e4  push    rdi
0x1800034e5  sub     rsp, 28h
0x1800034e9  movzx   eax, word ptr [rcx+20h]
0x1800034ed  mov     rsi, rcx
0x1800034f0  mov     rdi, [rcx+18h]
0x1800034f4  lea     rbp, [rax+rax*4]
0x1800034f8  shl     rbp, 4
0x1800034fc  add     rbp, rdi
0x1800034ff  jmp     short loc_18000352D
0x180003501  mov     rbx, [rdi+40h]
0x180003505  call    cs:__imp_GetProcessHeap
0x18000350b  mov     r8, rbx; lpMem
0x18000350e  xor     edx, edx; dwFlags
0x180003510  mov     rcx, rax; hHeap
0x180003513  call    cs:__imp_HeapFree
0x180003519  mov     qword ptr [rdi+40h], 0
0x180003521  mov     qword ptr [rdi+48h], 0
0x180003529  add     rdi, 50h ; 'P'
0x18000352d  cmp     rdi, rbp
0x180003530  jnz     short loc_180003501
0x180003532  mov     rbx, [rsi+18h]
0x180003536  call    cs:__imp_GetProcessHeap
0x18000353c  mov     r8, rbx; lpMem
0x18000353f  xor     edx, edx; dwFlags
0x180003541  mov     rcx, rax; hHeap
0x180003544  call    cs:__imp_HeapFree
0x18000354a  xor     eax, eax
0x18000354c  mov     [rsi+20h], eax
0x18000354f  mov     [rsi+18h], rax
0x180003553  add     rsp, 28h
0x180003557  pop     rdi
0x180003558  pop     rsi
0x180003559  pop     rbp
0x18000355a  pop     rbx
0x18000355b  retn
```
