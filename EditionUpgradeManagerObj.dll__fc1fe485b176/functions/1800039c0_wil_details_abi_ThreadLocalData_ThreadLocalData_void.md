# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800039c0`
- end: `0x180003a3c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800033e8`

## callees

- `0x1800039c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800039f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a24`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800039f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800039e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800039e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a16`

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
0x1800039c0  push    rbx
0x1800039c2  push    rbp
0x1800039c3  push    rsi
0x1800039c4  push    rdi
0x1800039c5  sub     rsp, 28h
0x1800039c9  movzx   eax, word ptr [rcx+20h]
0x1800039cd  mov     rsi, rcx
0x1800039d0  mov     rdi, [rcx+18h]
0x1800039d4  lea     rbp, [rax+rax*4]
0x1800039d8  shl     rbp, 4
0x1800039dc  add     rbp, rdi
0x1800039df  jmp     short loc_180003A0D
0x1800039e1  mov     rbx, [rdi+40h]
0x1800039e5  call    cs:__imp_GetProcessHeap
0x1800039eb  mov     r8, rbx; lpMem
0x1800039ee  xor     edx, edx; dwFlags
0x1800039f0  mov     rcx, rax; hHeap
0x1800039f3  call    cs:__imp_HeapFree
0x1800039f9  mov     qword ptr [rdi+40h], 0
0x180003a01  mov     qword ptr [rdi+48h], 0
0x180003a09  add     rdi, 50h ; 'P'
0x180003a0d  cmp     rdi, rbp
0x180003a10  jnz     short loc_1800039E1
0x180003a12  mov     rbx, [rsi+18h]
0x180003a16  call    cs:__imp_GetProcessHeap
0x180003a1c  mov     r8, rbx; lpMem
0x180003a1f  xor     edx, edx; dwFlags
0x180003a21  mov     rcx, rax; hHeap
0x180003a24  call    cs:__imp_HeapFree
0x180003a2a  xor     eax, eax
0x180003a2c  mov     [rsi+20h], eax
0x180003a2f  mov     [rsi+18h], rax
0x180003a33  add     rsp, 28h
0x180003a37  pop     rdi
0x180003a38  pop     rsi
0x180003a39  pop     rbp
0x180003a3a  pop     rbx
0x180003a3b  retn
```
