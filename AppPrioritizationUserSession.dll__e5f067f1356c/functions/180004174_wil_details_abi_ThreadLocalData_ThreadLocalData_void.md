# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180004174`
- end: `0x1800041f0`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003f88`

## callees

- `0x180004174`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004199`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800041ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004199`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800041ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041d8`

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
0x180004174  push    rbx
0x180004176  push    rbp
0x180004177  push    rsi
0x180004178  push    rdi
0x180004179  sub     rsp, 28h
0x18000417d  movzx   eax, word ptr [rcx+20h]
0x180004181  mov     rsi, rcx
0x180004184  mov     rdi, [rcx+18h]
0x180004188  lea     rbp, [rax+rax*4]
0x18000418c  shl     rbp, 4
0x180004190  add     rbp, rdi
0x180004193  jmp     short loc_1800041C1
0x180004195  mov     rbx, [rdi+40h]
0x180004199  call    cs:__imp_GetProcessHeap
0x18000419f  mov     r8, rbx; lpMem
0x1800041a2  xor     edx, edx; dwFlags
0x1800041a4  mov     rcx, rax; hHeap
0x1800041a7  call    cs:__imp_HeapFree
0x1800041ad  mov     qword ptr [rdi+40h], 0
0x1800041b5  mov     qword ptr [rdi+48h], 0
0x1800041bd  add     rdi, 50h ; 'P'
0x1800041c1  cmp     rdi, rbp
0x1800041c4  jnz     short loc_180004195
0x1800041c6  mov     rbx, [rsi+18h]
0x1800041ca  call    cs:__imp_GetProcessHeap
0x1800041d0  mov     r8, rbx; lpMem
0x1800041d3  xor     edx, edx; dwFlags
0x1800041d5  mov     rcx, rax; hHeap
0x1800041d8  call    cs:__imp_HeapFree
0x1800041de  xor     eax, eax
0x1800041e0  mov     [rsi+20h], eax
0x1800041e3  mov     [rsi+18h], rax
0x1800041e7  add     rsp, 28h
0x1800041eb  pop     rdi
0x1800041ec  pop     rsi
0x1800041ed  pop     rbp
0x1800041ee  pop     rbx
0x1800041ef  retn
```
