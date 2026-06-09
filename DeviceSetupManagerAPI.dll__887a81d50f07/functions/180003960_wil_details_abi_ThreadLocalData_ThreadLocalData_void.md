# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003960`
- end: `0x1800039dc`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003374`

## callees

- `0x180003960`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003985`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800039b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003985`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800039b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003993`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800039c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003993`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800039c4`

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
0x180003960  push    rbx
0x180003962  push    rbp
0x180003963  push    rsi
0x180003964  push    rdi
0x180003965  sub     rsp, 28h
0x180003969  movzx   eax, word ptr [rcx+20h]
0x18000396d  mov     rsi, rcx
0x180003970  mov     rdi, [rcx+18h]
0x180003974  lea     rbp, [rax+rax*4]
0x180003978  shl     rbp, 4
0x18000397c  add     rbp, rdi
0x18000397f  jmp     short loc_1800039AD
0x180003981  mov     rbx, [rdi+40h]
0x180003985  call    cs:__imp_GetProcessHeap
0x18000398b  mov     r8, rbx; lpMem
0x18000398e  xor     edx, edx; dwFlags
0x180003990  mov     rcx, rax; hHeap
0x180003993  call    cs:__imp_HeapFree
0x180003999  mov     qword ptr [rdi+40h], 0
0x1800039a1  mov     qword ptr [rdi+48h], 0
0x1800039a9  add     rdi, 50h ; 'P'
0x1800039ad  cmp     rdi, rbp
0x1800039b0  jnz     short loc_180003981
0x1800039b2  mov     rbx, [rsi+18h]
0x1800039b6  call    cs:__imp_GetProcessHeap
0x1800039bc  mov     r8, rbx; lpMem
0x1800039bf  xor     edx, edx; dwFlags
0x1800039c1  mov     rcx, rax; hHeap
0x1800039c4  call    cs:__imp_HeapFree
0x1800039ca  xor     eax, eax
0x1800039cc  mov     [rsi+20h], eax
0x1800039cf  mov     [rsi+18h], rax
0x1800039d3  add     rsp, 28h
0x1800039d7  pop     rdi
0x1800039d8  pop     rsi
0x1800039d9  pop     rbp
0x1800039da  pop     rbx
0x1800039db  retn
```
