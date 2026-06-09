# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003874`
- end: `0x1800038f0`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003120`

## callees

- `0x180003874`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003899`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003899`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038ca`

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
0x180003874  push    rbx
0x180003876  push    rbp
0x180003877  push    rsi
0x180003878  push    rdi
0x180003879  sub     rsp, 28h
0x18000387d  movzx   eax, word ptr [rcx+20h]
0x180003881  mov     rsi, rcx
0x180003884  mov     rdi, [rcx+18h]
0x180003888  lea     rbp, [rax+rax*4]
0x18000388c  shl     rbp, 4
0x180003890  add     rbp, rdi
0x180003893  jmp     short loc_1800038C1
0x180003895  mov     rbx, [rdi+40h]
0x180003899  call    cs:__imp_GetProcessHeap
0x18000389f  mov     r8, rbx; lpMem
0x1800038a2  xor     edx, edx; dwFlags
0x1800038a4  mov     rcx, rax; hHeap
0x1800038a7  call    cs:__imp_HeapFree
0x1800038ad  mov     qword ptr [rdi+40h], 0
0x1800038b5  mov     qword ptr [rdi+48h], 0
0x1800038bd  add     rdi, 50h ; 'P'
0x1800038c1  cmp     rdi, rbp
0x1800038c4  jnz     short loc_180003895
0x1800038c6  mov     rbx, [rsi+18h]
0x1800038ca  call    cs:__imp_GetProcessHeap
0x1800038d0  mov     r8, rbx; lpMem
0x1800038d3  xor     edx, edx; dwFlags
0x1800038d5  mov     rcx, rax; hHeap
0x1800038d8  call    cs:__imp_HeapFree
0x1800038de  xor     eax, eax
0x1800038e0  mov     [rsi+20h], eax
0x1800038e3  mov     [rsi+18h], rax
0x1800038e7  add     rsp, 28h
0x1800038eb  pop     rdi
0x1800038ec  pop     rsi
0x1800038ed  pop     rbp
0x1800038ee  pop     rbx
0x1800038ef  retn
```
