# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180017a40`
- end: `0x180017abc`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180017888`

## callees

- `0x180017a40`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017a65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017a96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017a65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017a96`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017a73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017aa4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017a73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017aa4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180017a40  push    rbx
0x180017a42  push    rbp
0x180017a43  push    rsi
0x180017a44  push    rdi
0x180017a45  sub     rsp, 28h
0x180017a49  movzx   eax, word ptr [rcx+20h]
0x180017a4d  mov     rsi, rcx
0x180017a50  mov     rdi, [rcx+18h]
0x180017a54  lea     rbp, [rax+rax*4]
0x180017a58  shl     rbp, 4
0x180017a5c  add     rbp, rdi
0x180017a5f  jmp     short loc_180017A8D
0x180017a61  mov     rbx, [rdi+40h]
0x180017a65  call    cs:__imp_GetProcessHeap
0x180017a6b  mov     r8, rbx; lpMem
0x180017a6e  xor     edx, edx; dwFlags
0x180017a70  mov     rcx, rax; hHeap
0x180017a73  call    cs:__imp_HeapFree
0x180017a79  mov     qword ptr [rdi+40h], 0
0x180017a81  mov     qword ptr [rdi+48h], 0
0x180017a89  add     rdi, 50h ; 'P'
0x180017a8d  cmp     rdi, rbp
0x180017a90  jnz     short loc_180017A61
0x180017a92  mov     rbx, [rsi+18h]
0x180017a96  call    cs:__imp_GetProcessHeap
0x180017a9c  mov     r8, rbx; lpMem
0x180017a9f  xor     edx, edx; dwFlags
0x180017aa1  mov     rcx, rax; hHeap
0x180017aa4  call    cs:__imp_HeapFree
0x180017aaa  xor     eax, eax
0x180017aac  mov     [rsi+20h], eax
0x180017aaf  mov     [rsi+18h], rax
0x180017ab3  add     rsp, 28h
0x180017ab7  pop     rdi
0x180017ab8  pop     rsi
0x180017ab9  pop     rbp
0x180017aba  pop     rbx
0x180017abb  retn
```
