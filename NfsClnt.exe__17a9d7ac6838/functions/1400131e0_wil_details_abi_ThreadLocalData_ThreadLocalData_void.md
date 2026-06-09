# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1400131e0`
- end: `0x14001325c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140012d54`

## callees

- `0x1400131e0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140013213`
- `KERNEL32!HeapFree` at `0x140013244`
- `KERNEL32!HeapFree` at `0x140013213`
- `KERNEL32!HeapFree` at `0x140013244`
- `KERNEL32!GetProcessHeap` at `0x140013205`
- `KERNEL32!GetProcessHeap` at `0x140013236`
- `KERNEL32!GetProcessHeap` at `0x140013205`
- `KERNEL32!GetProcessHeap` at `0x140013236`

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
0x1400131e0  push    rbx
0x1400131e2  push    rbp
0x1400131e3  push    rsi
0x1400131e4  push    rdi
0x1400131e5  sub     rsp, 28h
0x1400131e9  movzx   eax, word ptr [rcx+20h]
0x1400131ed  mov     rsi, rcx
0x1400131f0  mov     rdi, [rcx+18h]
0x1400131f4  lea     rbp, [rax+rax*4]
0x1400131f8  shl     rbp, 4
0x1400131fc  add     rbp, rdi
0x1400131ff  jmp     short loc_14001322D
0x140013201  mov     rbx, [rdi+40h]
0x140013205  call    cs:__imp_GetProcessHeap
0x14001320b  mov     r8, rbx; lpMem
0x14001320e  xor     edx, edx; dwFlags
0x140013210  mov     rcx, rax; hHeap
0x140013213  call    cs:__imp_HeapFree
0x140013219  mov     qword ptr [rdi+40h], 0
0x140013221  mov     qword ptr [rdi+48h], 0
0x140013229  add     rdi, 50h ; 'P'
0x14001322d  cmp     rdi, rbp
0x140013230  jnz     short loc_140013201
0x140013232  mov     rbx, [rsi+18h]
0x140013236  call    cs:__imp_GetProcessHeap
0x14001323c  mov     r8, rbx; lpMem
0x14001323f  xor     edx, edx; dwFlags
0x140013241  mov     rcx, rax; hHeap
0x140013244  call    cs:__imp_HeapFree
0x14001324a  xor     eax, eax
0x14001324c  mov     [rsi+20h], eax
0x14001324f  mov     [rsi+18h], rax
0x140013253  add     rsp, 28h
0x140013257  pop     rdi
0x140013258  pop     rsi
0x140013259  pop     rbp
0x14001325a  pop     rbx
0x14001325b  retn
```
