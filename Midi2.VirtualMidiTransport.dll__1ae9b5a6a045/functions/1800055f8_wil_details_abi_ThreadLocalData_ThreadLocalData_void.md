# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800055f8`
- end: `0x180005674`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005390`

## callees

- `0x1800055f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000562b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000565c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000562b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000565c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000561d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000564e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000561d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000564e`

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
0x1800055f8  push    rbx
0x1800055fa  push    rbp
0x1800055fb  push    rsi
0x1800055fc  push    rdi
0x1800055fd  sub     rsp, 28h
0x180005601  movzx   eax, word ptr [rcx+20h]
0x180005605  mov     rsi, rcx
0x180005608  mov     rdi, [rcx+18h]
0x18000560c  lea     rbp, [rax+rax*4]
0x180005610  shl     rbp, 4
0x180005614  add     rbp, rdi
0x180005617  jmp     short loc_180005645
0x180005619  mov     rbx, [rdi+40h]
0x18000561d  call    cs:__imp_GetProcessHeap
0x180005623  mov     r8, rbx; lpMem
0x180005626  xor     edx, edx; dwFlags
0x180005628  mov     rcx, rax; hHeap
0x18000562b  call    cs:__imp_HeapFree
0x180005631  mov     qword ptr [rdi+40h], 0
0x180005639  mov     qword ptr [rdi+48h], 0
0x180005641  add     rdi, 50h ; 'P'
0x180005645  cmp     rdi, rbp
0x180005648  jnz     short loc_180005619
0x18000564a  mov     rbx, [rsi+18h]
0x18000564e  call    cs:__imp_GetProcessHeap
0x180005654  mov     r8, rbx; lpMem
0x180005657  xor     edx, edx; dwFlags
0x180005659  mov     rcx, rax; hHeap
0x18000565c  call    cs:__imp_HeapFree
0x180005662  xor     eax, eax
0x180005664  mov     [rsi+20h], eax
0x180005667  mov     [rsi+18h], rax
0x18000566b  add     rsp, 28h
0x18000566f  pop     rdi
0x180005670  pop     rsi
0x180005671  pop     rbp
0x180005672  pop     rbx
0x180005673  retn
```
