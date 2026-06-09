# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180018004`
- end: `0x180018099`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180017e2c`

## callees

- `0x180018004`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018029`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018066`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018029`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018066`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001803d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001807a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001803d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001807a`

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
0x180018004  push    rbx
0x180018006  push    rbp
0x180018007  push    rsi
0x180018008  push    rdi
0x180018009  sub     rsp, 28h
0x18001800d  movzx   eax, word ptr [rcx+20h]
0x180018011  mov     rsi, rcx
0x180018014  mov     rdi, [rcx+18h]
0x180018018  lea     rbp, [rax+rax*4]
0x18001801c  shl     rbp, 4
0x180018020  add     rbp, rdi
0x180018023  jmp     short loc_18001805D
0x180018025  mov     rbx, [rdi+40h]
0x180018029  call    cs:__imp_GetProcessHeap
0x180018030  nop     dword ptr [rax+rax+00h]
0x180018035  mov     r8, rbx; lpMem
0x180018038  xor     edx, edx; dwFlags
0x18001803a  mov     rcx, rax; hHeap
0x18001803d  call    cs:__imp_HeapFree
0x180018044  nop     dword ptr [rax+rax+00h]
0x180018049  mov     qword ptr [rdi+40h], 0
0x180018051  mov     qword ptr [rdi+48h], 0
0x180018059  add     rdi, 50h ; 'P'
0x18001805d  cmp     rdi, rbp
0x180018060  jnz     short loc_180018025
0x180018062  mov     rbx, [rsi+18h]
0x180018066  call    cs:__imp_GetProcessHeap
0x18001806d  nop     dword ptr [rax+rax+00h]
0x180018072  mov     r8, rbx; lpMem
0x180018075  xor     edx, edx; dwFlags
0x180018077  mov     rcx, rax; hHeap
0x18001807a  call    cs:__imp_HeapFree
0x180018081  nop     dword ptr [rax+rax+00h]
0x180018086  xor     eax, eax
0x180018088  mov     [rsi+20h], eax
0x18001808b  mov     [rsi+18h], rax
0x18001808f  add     rsp, 28h
0x180018093  pop     rdi
0x180018094  pop     rsi
0x180018095  pop     rbp
0x180018096  pop     rbx
0x180018097  retn
```
