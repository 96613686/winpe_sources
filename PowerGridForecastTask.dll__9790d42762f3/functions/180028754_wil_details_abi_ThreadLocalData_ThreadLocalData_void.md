# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180028754`
- end: `0x1800287d0`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180027db8`

## callees

- `0x180028754`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028787`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800287b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028787`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800287b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028779`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800287aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028779`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800287aa`

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
0x180028754  push    rbx
0x180028756  push    rbp
0x180028757  push    rsi
0x180028758  push    rdi
0x180028759  sub     rsp, 28h
0x18002875d  movzx   eax, word ptr [rcx+20h]
0x180028761  mov     rsi, rcx
0x180028764  mov     rdi, [rcx+18h]
0x180028768  lea     rbp, [rax+rax*4]
0x18002876c  shl     rbp, 4
0x180028770  add     rbp, rdi
0x180028773  jmp     short loc_1800287A1
0x180028775  mov     rbx, [rdi+40h]
0x180028779  call    cs:__imp_GetProcessHeap
0x18002877f  mov     r8, rbx; lpMem
0x180028782  xor     edx, edx; dwFlags
0x180028784  mov     rcx, rax; hHeap
0x180028787  call    cs:__imp_HeapFree
0x18002878d  mov     qword ptr [rdi+40h], 0
0x180028795  mov     qword ptr [rdi+48h], 0
0x18002879d  add     rdi, 50h ; 'P'
0x1800287a1  cmp     rdi, rbp
0x1800287a4  jnz     short loc_180028775
0x1800287a6  mov     rbx, [rsi+18h]
0x1800287aa  call    cs:__imp_GetProcessHeap
0x1800287b0  mov     r8, rbx; lpMem
0x1800287b3  xor     edx, edx; dwFlags
0x1800287b5  mov     rcx, rax; hHeap
0x1800287b8  call    cs:__imp_HeapFree
0x1800287be  xor     eax, eax
0x1800287c0  mov     [rsi+20h], eax
0x1800287c3  mov     [rsi+18h], rax
0x1800287c7  add     rsp, 28h
0x1800287cb  pop     rdi
0x1800287cc  pop     rsi
0x1800287cd  pop     rbp
0x1800287ce  pop     rbx
0x1800287cf  retn
```
