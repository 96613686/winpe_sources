# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x14000494c`
- end: `0x1400049c8`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004880`

## callees

- `0x14000494c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000497f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400049b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000497f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400049b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004971`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400049a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004971`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400049a2`

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
0x14000494c  push    rbx
0x14000494e  push    rbp
0x14000494f  push    rsi
0x140004950  push    rdi
0x140004951  sub     rsp, 28h
0x140004955  movzx   eax, word ptr [rcx+20h]
0x140004959  mov     rsi, rcx
0x14000495c  mov     rdi, [rcx+18h]
0x140004960  lea     rbp, [rax+rax*4]
0x140004964  shl     rbp, 4
0x140004968  add     rbp, rdi
0x14000496b  jmp     short loc_140004999
0x14000496d  mov     rbx, [rdi+40h]
0x140004971  call    cs:__imp_GetProcessHeap
0x140004977  mov     r8, rbx; lpMem
0x14000497a  xor     edx, edx; dwFlags
0x14000497c  mov     rcx, rax; hHeap
0x14000497f  call    cs:__imp_HeapFree
0x140004985  mov     qword ptr [rdi+40h], 0
0x14000498d  mov     qword ptr [rdi+48h], 0
0x140004995  add     rdi, 50h ; 'P'
0x140004999  cmp     rdi, rbp
0x14000499c  jnz     short loc_14000496D
0x14000499e  mov     rbx, [rsi+18h]
0x1400049a2  call    cs:__imp_GetProcessHeap
0x1400049a8  mov     r8, rbx; lpMem
0x1400049ab  xor     edx, edx; dwFlags
0x1400049ad  mov     rcx, rax; hHeap
0x1400049b0  call    cs:__imp_HeapFree
0x1400049b6  xor     eax, eax
0x1400049b8  mov     [rsi+20h], eax
0x1400049bb  mov     [rsi+18h], rax
0x1400049bf  add     rsp, 28h
0x1400049c3  pop     rdi
0x1400049c4  pop     rsi
0x1400049c5  pop     rbp
0x1400049c6  pop     rbx
0x1400049c7  retn
```
