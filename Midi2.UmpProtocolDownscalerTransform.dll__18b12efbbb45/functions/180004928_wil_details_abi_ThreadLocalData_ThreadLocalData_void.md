# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180004928`
- end: `0x1800049a4`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800046c0`

## callees

- `0x180004928`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000494d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000497e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000494d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000497e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000495b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000498c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000495b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000498c`

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
0x180004928  push    rbx
0x18000492a  push    rbp
0x18000492b  push    rsi
0x18000492c  push    rdi
0x18000492d  sub     rsp, 28h
0x180004931  movzx   eax, word ptr [rcx+20h]
0x180004935  mov     rsi, rcx
0x180004938  mov     rdi, [rcx+18h]
0x18000493c  lea     rbp, [rax+rax*4]
0x180004940  shl     rbp, 4
0x180004944  add     rbp, rdi
0x180004947  jmp     short loc_180004975
0x180004949  mov     rbx, [rdi+40h]
0x18000494d  call    cs:__imp_GetProcessHeap
0x180004953  mov     r8, rbx; lpMem
0x180004956  xor     edx, edx; dwFlags
0x180004958  mov     rcx, rax; hHeap
0x18000495b  call    cs:__imp_HeapFree
0x180004961  mov     qword ptr [rdi+40h], 0
0x180004969  mov     qword ptr [rdi+48h], 0
0x180004971  add     rdi, 50h ; 'P'
0x180004975  cmp     rdi, rbp
0x180004978  jnz     short loc_180004949
0x18000497a  mov     rbx, [rsi+18h]
0x18000497e  call    cs:__imp_GetProcessHeap
0x180004984  mov     r8, rbx; lpMem
0x180004987  xor     edx, edx; dwFlags
0x180004989  mov     rcx, rax; hHeap
0x18000498c  call    cs:__imp_HeapFree
0x180004992  xor     eax, eax
0x180004994  mov     [rsi+20h], eax
0x180004997  mov     [rsi+18h], rax
0x18000499b  add     rsp, 28h
0x18000499f  pop     rdi
0x1800049a0  pop     rsi
0x1800049a1  pop     rbp
0x1800049a2  pop     rbx
0x1800049a3  retn
```
