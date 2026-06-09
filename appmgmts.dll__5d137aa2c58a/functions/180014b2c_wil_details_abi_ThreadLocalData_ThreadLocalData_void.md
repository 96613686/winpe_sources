# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180014b2c`
- end: `0x180014ba8`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014558`

## callees

- `0x180014b2c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014b5f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014b90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014b5f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014b90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014b51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014b82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014b51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014b82`

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
0x180014b2c  push    rbx
0x180014b2e  push    rbp
0x180014b2f  push    rsi
0x180014b30  push    rdi
0x180014b31  sub     rsp, 28h
0x180014b35  movzx   eax, word ptr [rcx+20h]
0x180014b39  mov     rsi, rcx
0x180014b3c  mov     rdi, [rcx+18h]
0x180014b40  lea     rbp, [rax+rax*4]
0x180014b44  shl     rbp, 4
0x180014b48  add     rbp, rdi
0x180014b4b  jmp     short loc_180014B79
0x180014b4d  mov     rbx, [rdi+40h]
0x180014b51  call    cs:__imp_GetProcessHeap
0x180014b57  mov     r8, rbx; lpMem
0x180014b5a  xor     edx, edx; dwFlags
0x180014b5c  mov     rcx, rax; hHeap
0x180014b5f  call    cs:__imp_HeapFree
0x180014b65  mov     qword ptr [rdi+40h], 0
0x180014b6d  mov     qword ptr [rdi+48h], 0
0x180014b75  add     rdi, 50h ; 'P'
0x180014b79  cmp     rdi, rbp
0x180014b7c  jnz     short loc_180014B4D
0x180014b7e  mov     rbx, [rsi+18h]
0x180014b82  call    cs:__imp_GetProcessHeap
0x180014b88  mov     r8, rbx; lpMem
0x180014b8b  xor     edx, edx; dwFlags
0x180014b8d  mov     rcx, rax; hHeap
0x180014b90  call    cs:__imp_HeapFree
0x180014b96  xor     eax, eax
0x180014b98  mov     [rsi+20h], eax
0x180014b9b  mov     [rsi+18h], rax
0x180014b9f  add     rsp, 28h
0x180014ba3  pop     rdi
0x180014ba4  pop     rsi
0x180014ba5  pop     rbp
0x180014ba6  pop     rbx
0x180014ba7  retn
```
