# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180002f0c`
- end: `0x180002f88`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d54`

## callees

- `0x180002f0c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f3f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f70`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f3f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f62`

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
0x180002f0c  push    rbx
0x180002f0e  push    rbp
0x180002f0f  push    rsi
0x180002f10  push    rdi
0x180002f11  sub     rsp, 28h
0x180002f15  movzx   eax, word ptr [rcx+20h]
0x180002f19  mov     rsi, rcx
0x180002f1c  mov     rdi, [rcx+18h]
0x180002f20  lea     rbp, [rax+rax*4]
0x180002f24  shl     rbp, 4
0x180002f28  add     rbp, rdi
0x180002f2b  jmp     short loc_180002F59
0x180002f2d  mov     rbx, [rdi+40h]
0x180002f31  call    cs:__imp_GetProcessHeap
0x180002f37  mov     r8, rbx; lpMem
0x180002f3a  xor     edx, edx; dwFlags
0x180002f3c  mov     rcx, rax; hHeap
0x180002f3f  call    cs:__imp_HeapFree
0x180002f45  mov     qword ptr [rdi+40h], 0
0x180002f4d  mov     qword ptr [rdi+48h], 0
0x180002f55  add     rdi, 50h ; 'P'
0x180002f59  cmp     rdi, rbp
0x180002f5c  jnz     short loc_180002F2D
0x180002f5e  mov     rbx, [rsi+18h]
0x180002f62  call    cs:__imp_GetProcessHeap
0x180002f68  mov     r8, rbx; lpMem
0x180002f6b  xor     edx, edx; dwFlags
0x180002f6d  mov     rcx, rax; hHeap
0x180002f70  call    cs:__imp_HeapFree
0x180002f76  xor     eax, eax
0x180002f78  mov     [rsi+20h], eax
0x180002f7b  mov     [rsi+18h], rax
0x180002f7f  add     rsp, 28h
0x180002f83  pop     rdi
0x180002f84  pop     rsi
0x180002f85  pop     rbp
0x180002f86  pop     rbx
0x180002f87  retn
```
