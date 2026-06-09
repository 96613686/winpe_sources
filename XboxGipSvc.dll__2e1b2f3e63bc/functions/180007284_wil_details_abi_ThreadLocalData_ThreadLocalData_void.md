# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180007284`
- end: `0x180007300`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007098`

## callees

- `0x180007284`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800072b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800072e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800072b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800072e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800072a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800072da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800072a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800072da`

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
0x180007284  push    rbx
0x180007286  push    rbp
0x180007287  push    rsi
0x180007288  push    rdi
0x180007289  sub     rsp, 28h
0x18000728d  movzx   eax, word ptr [rcx+20h]
0x180007291  mov     rsi, rcx
0x180007294  mov     rdi, [rcx+18h]
0x180007298  lea     rbp, [rax+rax*4]
0x18000729c  shl     rbp, 4
0x1800072a0  add     rbp, rdi
0x1800072a3  jmp     short loc_1800072D1
0x1800072a5  mov     rbx, [rdi+40h]
0x1800072a9  call    cs:__imp_GetProcessHeap
0x1800072af  mov     r8, rbx; lpMem
0x1800072b2  xor     edx, edx; dwFlags
0x1800072b4  mov     rcx, rax; hHeap
0x1800072b7  call    cs:__imp_HeapFree
0x1800072bd  mov     qword ptr [rdi+40h], 0
0x1800072c5  mov     qword ptr [rdi+48h], 0
0x1800072cd  add     rdi, 50h ; 'P'
0x1800072d1  cmp     rdi, rbp
0x1800072d4  jnz     short loc_1800072A5
0x1800072d6  mov     rbx, [rsi+18h]
0x1800072da  call    cs:__imp_GetProcessHeap
0x1800072e0  mov     r8, rbx; lpMem
0x1800072e3  xor     edx, edx; dwFlags
0x1800072e5  mov     rcx, rax; hHeap
0x1800072e8  call    cs:__imp_HeapFree
0x1800072ee  xor     eax, eax
0x1800072f0  mov     [rsi+20h], eax
0x1800072f3  mov     [rsi+18h], rax
0x1800072f7  add     rsp, 28h
0x1800072fb  pop     rdi
0x1800072fc  pop     rsi
0x1800072fd  pop     rbp
0x1800072fe  pop     rbx
0x1800072ff  retn
```
