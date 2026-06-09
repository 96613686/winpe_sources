# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800044a0`
- end: `0x18000451c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800042e8`

## callees

- `0x1800044a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800044d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004504`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800044d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004504`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800044c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800044f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800044c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800044f6`

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
0x1800044a0  push    rbx
0x1800044a2  push    rbp
0x1800044a3  push    rsi
0x1800044a4  push    rdi
0x1800044a5  sub     rsp, 28h
0x1800044a9  movzx   eax, word ptr [rcx+20h]
0x1800044ad  mov     rsi, rcx
0x1800044b0  mov     rdi, [rcx+18h]
0x1800044b4  lea     rbp, [rax+rax*4]
0x1800044b8  shl     rbp, 4
0x1800044bc  add     rbp, rdi
0x1800044bf  jmp     short loc_1800044ED
0x1800044c1  mov     rbx, [rdi+40h]
0x1800044c5  call    cs:__imp_GetProcessHeap
0x1800044cb  mov     r8, rbx; lpMem
0x1800044ce  xor     edx, edx; dwFlags
0x1800044d0  mov     rcx, rax; hHeap
0x1800044d3  call    cs:__imp_HeapFree
0x1800044d9  mov     qword ptr [rdi+40h], 0
0x1800044e1  mov     qword ptr [rdi+48h], 0
0x1800044e9  add     rdi, 50h ; 'P'
0x1800044ed  cmp     rdi, rbp
0x1800044f0  jnz     short loc_1800044C1
0x1800044f2  mov     rbx, [rsi+18h]
0x1800044f6  call    cs:__imp_GetProcessHeap
0x1800044fc  mov     r8, rbx; lpMem
0x1800044ff  xor     edx, edx; dwFlags
0x180004501  mov     rcx, rax; hHeap
0x180004504  call    cs:__imp_HeapFree
0x18000450a  xor     eax, eax
0x18000450c  mov     [rsi+20h], eax
0x18000450f  mov     [rsi+18h], rax
0x180004513  add     rsp, 28h
0x180004517  pop     rdi
0x180004518  pop     rsi
0x180004519  pop     rbp
0x18000451a  pop     rbx
0x18000451b  retn
```
