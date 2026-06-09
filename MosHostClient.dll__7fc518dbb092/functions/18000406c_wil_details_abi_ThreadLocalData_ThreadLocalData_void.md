# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x18000406c`
- end: `0x1800040e8`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003da4`

## callees

- `0x18000406c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000409f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800040d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000409f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800040d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004091`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800040c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004091`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800040c2`

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
0x18000406c  push    rbx
0x18000406e  push    rbp
0x18000406f  push    rsi
0x180004070  push    rdi
0x180004071  sub     rsp, 28h
0x180004075  movzx   eax, word ptr [rcx+20h]
0x180004079  mov     rsi, rcx
0x18000407c  mov     rdi, [rcx+18h]
0x180004080  lea     rbp, [rax+rax*4]
0x180004084  shl     rbp, 4
0x180004088  add     rbp, rdi
0x18000408b  jmp     short loc_1800040B9
0x18000408d  mov     rbx, [rdi+40h]
0x180004091  call    cs:__imp_GetProcessHeap
0x180004097  mov     r8, rbx; lpMem
0x18000409a  xor     edx, edx; dwFlags
0x18000409c  mov     rcx, rax; hHeap
0x18000409f  call    cs:__imp_HeapFree
0x1800040a5  mov     qword ptr [rdi+40h], 0
0x1800040ad  mov     qword ptr [rdi+48h], 0
0x1800040b5  add     rdi, 50h ; 'P'
0x1800040b9  cmp     rdi, rbp
0x1800040bc  jnz     short loc_18000408D
0x1800040be  mov     rbx, [rsi+18h]
0x1800040c2  call    cs:__imp_GetProcessHeap
0x1800040c8  mov     r8, rbx; lpMem
0x1800040cb  xor     edx, edx; dwFlags
0x1800040cd  mov     rcx, rax; hHeap
0x1800040d0  call    cs:__imp_HeapFree
0x1800040d6  xor     eax, eax
0x1800040d8  mov     [rsi+20h], eax
0x1800040db  mov     [rsi+18h], rax
0x1800040df  add     rsp, 28h
0x1800040e3  pop     rdi
0x1800040e4  pop     rsi
0x1800040e5  pop     rbp
0x1800040e6  pop     rbx
0x1800040e7  retn
```
