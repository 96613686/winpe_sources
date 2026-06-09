# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800034d8`
- end: `0x180003554`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003328`

## callees

- `0x1800034d8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000350b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000353c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000350b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000353c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000352e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000352e`

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
0x1800034d8  push    rbx
0x1800034da  push    rbp
0x1800034db  push    rsi
0x1800034dc  push    rdi
0x1800034dd  sub     rsp, 28h
0x1800034e1  movzx   eax, word ptr [rcx+20h]
0x1800034e5  mov     rsi, rcx
0x1800034e8  mov     rdi, [rcx+18h]
0x1800034ec  lea     rbp, [rax+rax*4]
0x1800034f0  shl     rbp, 4
0x1800034f4  add     rbp, rdi
0x1800034f7  jmp     short loc_180003525
0x1800034f9  mov     rbx, [rdi+40h]
0x1800034fd  call    cs:__imp_GetProcessHeap
0x180003503  mov     r8, rbx; lpMem
0x180003506  xor     edx, edx; dwFlags
0x180003508  mov     rcx, rax; hHeap
0x18000350b  call    cs:__imp_HeapFree
0x180003511  mov     qword ptr [rdi+40h], 0
0x180003519  mov     qword ptr [rdi+48h], 0
0x180003521  add     rdi, 50h ; 'P'
0x180003525  cmp     rdi, rbp
0x180003528  jnz     short loc_1800034F9
0x18000352a  mov     rbx, [rsi+18h]
0x18000352e  call    cs:__imp_GetProcessHeap
0x180003534  mov     r8, rbx; lpMem
0x180003537  xor     edx, edx; dwFlags
0x180003539  mov     rcx, rax; hHeap
0x18000353c  call    cs:__imp_HeapFree
0x180003542  xor     eax, eax
0x180003544  mov     [rsi+20h], eax
0x180003547  mov     [rsi+18h], rax
0x18000354b  add     rsp, 28h
0x18000354f  pop     rdi
0x180003550  pop     rsi
0x180003551  pop     rbp
0x180003552  pop     rbx
0x180003553  retn
```
