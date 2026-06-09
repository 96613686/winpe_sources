# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800036d4`
- end: `0x180003750`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003608`

## callees

- `0x1800036d4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000372a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000372a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003707`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003738`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003707`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003738`

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
0x1800036d4  push    rbx
0x1800036d6  push    rbp
0x1800036d7  push    rsi
0x1800036d8  push    rdi
0x1800036d9  sub     rsp, 28h
0x1800036dd  movzx   eax, word ptr [rcx+20h]
0x1800036e1  mov     rsi, rcx
0x1800036e4  mov     rdi, [rcx+18h]
0x1800036e8  lea     rbp, [rax+rax*4]
0x1800036ec  shl     rbp, 4
0x1800036f0  add     rbp, rdi
0x1800036f3  jmp     short loc_180003721
0x1800036f5  mov     rbx, [rdi+40h]
0x1800036f9  call    cs:__imp_GetProcessHeap
0x1800036ff  mov     r8, rbx; lpMem
0x180003702  xor     edx, edx; dwFlags
0x180003704  mov     rcx, rax; hHeap
0x180003707  call    cs:__imp_HeapFree
0x18000370d  mov     qword ptr [rdi+40h], 0
0x180003715  mov     qword ptr [rdi+48h], 0
0x18000371d  add     rdi, 50h ; 'P'
0x180003721  cmp     rdi, rbp
0x180003724  jnz     short loc_1800036F5
0x180003726  mov     rbx, [rsi+18h]
0x18000372a  call    cs:__imp_GetProcessHeap
0x180003730  mov     r8, rbx; lpMem
0x180003733  xor     edx, edx; dwFlags
0x180003735  mov     rcx, rax; hHeap
0x180003738  call    cs:__imp_HeapFree
0x18000373e  xor     eax, eax
0x180003740  mov     [rsi+20h], eax
0x180003743  mov     [rsi+18h], rax
0x180003747  add     rsp, 28h
0x18000374b  pop     rdi
0x18000374c  pop     rsi
0x18000374d  pop     rbp
0x18000374e  pop     rbx
0x18000374f  retn
```
