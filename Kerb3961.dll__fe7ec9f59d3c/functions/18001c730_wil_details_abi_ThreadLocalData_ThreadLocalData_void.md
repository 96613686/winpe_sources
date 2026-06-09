# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x18001c730`
- end: `0x18001c7ac`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001c664`

## callees

- `0x18001c730`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c755`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c786`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c755`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c786`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c763`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c794`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c763`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c794`

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
0x18001c730  push    rbx
0x18001c732  push    rbp
0x18001c733  push    rsi
0x18001c734  push    rdi
0x18001c735  sub     rsp, 28h
0x18001c739  movzx   eax, word ptr [rcx+20h]
0x18001c73d  mov     rsi, rcx
0x18001c740  mov     rdi, [rcx+18h]
0x18001c744  lea     rbp, [rax+rax*4]
0x18001c748  shl     rbp, 4
0x18001c74c  add     rbp, rdi
0x18001c74f  jmp     short loc_18001C77D
0x18001c751  mov     rbx, [rdi+40h]
0x18001c755  call    cs:__imp_GetProcessHeap
0x18001c75b  mov     r8, rbx; lpMem
0x18001c75e  xor     edx, edx; dwFlags
0x18001c760  mov     rcx, rax; hHeap
0x18001c763  call    cs:__imp_HeapFree
0x18001c769  mov     qword ptr [rdi+40h], 0
0x18001c771  mov     qword ptr [rdi+48h], 0
0x18001c779  add     rdi, 50h ; 'P'
0x18001c77d  cmp     rdi, rbp
0x18001c780  jnz     short loc_18001C751
0x18001c782  mov     rbx, [rsi+18h]
0x18001c786  call    cs:__imp_GetProcessHeap
0x18001c78c  mov     r8, rbx; lpMem
0x18001c78f  xor     edx, edx; dwFlags
0x18001c791  mov     rcx, rax; hHeap
0x18001c794  call    cs:__imp_HeapFree
0x18001c79a  xor     eax, eax
0x18001c79c  mov     [rsi+20h], eax
0x18001c79f  mov     [rsi+18h], rax
0x18001c7a3  add     rsp, 28h
0x18001c7a7  pop     rdi
0x18001c7a8  pop     rsi
0x18001c7a9  pop     rbp
0x18001c7aa  pop     rbx
0x18001c7ab  retn
```
