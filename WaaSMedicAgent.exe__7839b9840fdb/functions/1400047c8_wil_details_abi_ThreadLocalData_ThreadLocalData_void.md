# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1400047c8`
- end: `0x140004844`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400045a0`

## callees

- `0x1400047c8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400047fb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000482c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400047fb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000482c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400047ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000481e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400047ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000481e`

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
0x1400047c8  push    rbx
0x1400047ca  push    rbp
0x1400047cb  push    rsi
0x1400047cc  push    rdi
0x1400047cd  sub     rsp, 28h
0x1400047d1  movzx   eax, word ptr [rcx+20h]
0x1400047d5  mov     rsi, rcx
0x1400047d8  mov     rdi, [rcx+18h]
0x1400047dc  lea     rbp, [rax+rax*4]
0x1400047e0  shl     rbp, 4
0x1400047e4  add     rbp, rdi
0x1400047e7  jmp     short loc_140004815
0x1400047e9  mov     rbx, [rdi+40h]
0x1400047ed  call    cs:__imp_GetProcessHeap
0x1400047f3  mov     r8, rbx; lpMem
0x1400047f6  xor     edx, edx; dwFlags
0x1400047f8  mov     rcx, rax; hHeap
0x1400047fb  call    cs:__imp_HeapFree
0x140004801  mov     qword ptr [rdi+40h], 0
0x140004809  mov     qword ptr [rdi+48h], 0
0x140004811  add     rdi, 50h ; 'P'
0x140004815  cmp     rdi, rbp
0x140004818  jnz     short loc_1400047E9
0x14000481a  mov     rbx, [rsi+18h]
0x14000481e  call    cs:__imp_GetProcessHeap
0x140004824  mov     r8, rbx; lpMem
0x140004827  xor     edx, edx; dwFlags
0x140004829  mov     rcx, rax; hHeap
0x14000482c  call    cs:__imp_HeapFree
0x140004832  xor     eax, eax
0x140004834  mov     [rsi+20h], eax
0x140004837  mov     [rsi+18h], rax
0x14000483b  add     rsp, 28h
0x14000483f  pop     rdi
0x140004840  pop     rsi
0x140004841  pop     rbp
0x140004842  pop     rbx
0x140004843  retn
```
