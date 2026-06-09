# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003730`
- end: `0x1800037ac`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003510`

## callees

- `0x180003730`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003763`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003794`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003763`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003794`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003755`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003786`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003755`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003786`

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
0x180003730  push    rbx
0x180003732  push    rbp
0x180003733  push    rsi
0x180003734  push    rdi
0x180003735  sub     rsp, 28h
0x180003739  movzx   eax, word ptr [rcx+20h]
0x18000373d  mov     rsi, rcx
0x180003740  mov     rdi, [rcx+18h]
0x180003744  lea     rbp, [rax+rax*4]
0x180003748  shl     rbp, 4
0x18000374c  add     rbp, rdi
0x18000374f  jmp     short loc_18000377D
0x180003751  mov     rbx, [rdi+40h]
0x180003755  call    cs:__imp_GetProcessHeap
0x18000375b  mov     r8, rbx; lpMem
0x18000375e  xor     edx, edx; dwFlags
0x180003760  mov     rcx, rax; hHeap
0x180003763  call    cs:__imp_HeapFree
0x180003769  mov     qword ptr [rdi+40h], 0
0x180003771  mov     qword ptr [rdi+48h], 0
0x180003779  add     rdi, 50h ; 'P'
0x18000377d  cmp     rdi, rbp
0x180003780  jnz     short loc_180003751
0x180003782  mov     rbx, [rsi+18h]
0x180003786  call    cs:__imp_GetProcessHeap
0x18000378c  mov     r8, rbx; lpMem
0x18000378f  xor     edx, edx; dwFlags
0x180003791  mov     rcx, rax; hHeap
0x180003794  call    cs:__imp_HeapFree
0x18000379a  xor     eax, eax
0x18000379c  mov     [rsi+20h], eax
0x18000379f  mov     [rsi+18h], rax
0x1800037a3  add     rsp, 28h
0x1800037a7  pop     rdi
0x1800037a8  pop     rsi
0x1800037a9  pop     rbp
0x1800037aa  pop     rbx
0x1800037ab  retn
```
