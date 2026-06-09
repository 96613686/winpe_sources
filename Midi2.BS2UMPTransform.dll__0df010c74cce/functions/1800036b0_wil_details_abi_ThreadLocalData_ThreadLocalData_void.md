# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800036b0`
- end: `0x18000372c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003448`

## callees

- `0x1800036b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003706`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003706`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003714`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003714`

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
0x1800036b0  push    rbx
0x1800036b2  push    rbp
0x1800036b3  push    rsi
0x1800036b4  push    rdi
0x1800036b5  sub     rsp, 28h
0x1800036b9  movzx   eax, word ptr [rcx+20h]
0x1800036bd  mov     rsi, rcx
0x1800036c0  mov     rdi, [rcx+18h]
0x1800036c4  lea     rbp, [rax+rax*4]
0x1800036c8  shl     rbp, 4
0x1800036cc  add     rbp, rdi
0x1800036cf  jmp     short loc_1800036FD
0x1800036d1  mov     rbx, [rdi+40h]
0x1800036d5  call    cs:__imp_GetProcessHeap
0x1800036db  mov     r8, rbx; lpMem
0x1800036de  xor     edx, edx; dwFlags
0x1800036e0  mov     rcx, rax; hHeap
0x1800036e3  call    cs:__imp_HeapFree
0x1800036e9  mov     qword ptr [rdi+40h], 0
0x1800036f1  mov     qword ptr [rdi+48h], 0
0x1800036f9  add     rdi, 50h ; 'P'
0x1800036fd  cmp     rdi, rbp
0x180003700  jnz     short loc_1800036D1
0x180003702  mov     rbx, [rsi+18h]
0x180003706  call    cs:__imp_GetProcessHeap
0x18000370c  mov     r8, rbx; lpMem
0x18000370f  xor     edx, edx; dwFlags
0x180003711  mov     rcx, rax; hHeap
0x180003714  call    cs:__imp_HeapFree
0x18000371a  xor     eax, eax
0x18000371c  mov     [rsi+20h], eax
0x18000371f  mov     [rsi+18h], rax
0x180003723  add     rsp, 28h
0x180003727  pop     rdi
0x180003728  pop     rsi
0x180003729  pop     rbp
0x18000372a  pop     rbx
0x18000372b  retn
```
