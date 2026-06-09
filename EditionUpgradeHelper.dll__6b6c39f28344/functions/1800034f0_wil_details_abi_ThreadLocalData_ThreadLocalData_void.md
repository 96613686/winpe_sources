# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800034f0`
- end: `0x18000356c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003064`

## callees

- `0x1800034f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003515`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003546`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003515`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003546`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003523`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003554`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003523`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003554`

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
0x1800034f0  push    rbx
0x1800034f2  push    rbp
0x1800034f3  push    rsi
0x1800034f4  push    rdi
0x1800034f5  sub     rsp, 28h
0x1800034f9  movzx   eax, word ptr [rcx+20h]
0x1800034fd  mov     rsi, rcx
0x180003500  mov     rdi, [rcx+18h]
0x180003504  lea     rbp, [rax+rax*4]
0x180003508  shl     rbp, 4
0x18000350c  add     rbp, rdi
0x18000350f  jmp     short loc_18000353D
0x180003511  mov     rbx, [rdi+40h]
0x180003515  call    cs:__imp_GetProcessHeap
0x18000351b  mov     r8, rbx; lpMem
0x18000351e  xor     edx, edx; dwFlags
0x180003520  mov     rcx, rax; hHeap
0x180003523  call    cs:__imp_HeapFree
0x180003529  mov     qword ptr [rdi+40h], 0
0x180003531  mov     qword ptr [rdi+48h], 0
0x180003539  add     rdi, 50h ; 'P'
0x18000353d  cmp     rdi, rbp
0x180003540  jnz     short loc_180003511
0x180003542  mov     rbx, [rsi+18h]
0x180003546  call    cs:__imp_GetProcessHeap
0x18000354c  mov     r8, rbx; lpMem
0x18000354f  xor     edx, edx; dwFlags
0x180003551  mov     rcx, rax; hHeap
0x180003554  call    cs:__imp_HeapFree
0x18000355a  xor     eax, eax
0x18000355c  mov     [rsi+20h], eax
0x18000355f  mov     [rsi+18h], rax
0x180003563  add     rsp, 28h
0x180003567  pop     rdi
0x180003568  pop     rsi
0x180003569  pop     rbp
0x18000356a  pop     rbx
0x18000356b  retn
```
