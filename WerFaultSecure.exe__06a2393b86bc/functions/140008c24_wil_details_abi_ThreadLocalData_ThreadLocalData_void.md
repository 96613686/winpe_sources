# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140008c24`
- end: `0x140008ca0`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000871c`

## callees

- `0x140008c24`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008c49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008c7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008c49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008c7a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008c57`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008c88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008c57`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008c88`

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
0x140008c24  push    rbx
0x140008c26  push    rbp
0x140008c27  push    rsi
0x140008c28  push    rdi
0x140008c29  sub     rsp, 28h
0x140008c2d  movzx   eax, word ptr [rcx+20h]
0x140008c31  mov     rsi, rcx
0x140008c34  mov     rdi, [rcx+18h]
0x140008c38  lea     rbp, [rax+rax*4]
0x140008c3c  shl     rbp, 4
0x140008c40  add     rbp, rdi
0x140008c43  jmp     short loc_140008C71
0x140008c45  mov     rbx, [rdi+40h]
0x140008c49  call    cs:__imp_GetProcessHeap
0x140008c4f  mov     r8, rbx; lpMem
0x140008c52  xor     edx, edx; dwFlags
0x140008c54  mov     rcx, rax; hHeap
0x140008c57  call    cs:__imp_HeapFree
0x140008c5d  mov     qword ptr [rdi+40h], 0
0x140008c65  mov     qword ptr [rdi+48h], 0
0x140008c6d  add     rdi, 50h ; 'P'
0x140008c71  cmp     rdi, rbp
0x140008c74  jnz     short loc_140008C45
0x140008c76  mov     rbx, [rsi+18h]
0x140008c7a  call    cs:__imp_GetProcessHeap
0x140008c80  mov     r8, rbx; lpMem
0x140008c83  xor     edx, edx; dwFlags
0x140008c85  mov     rcx, rax; hHeap
0x140008c88  call    cs:__imp_HeapFree
0x140008c8e  xor     eax, eax
0x140008c90  mov     [rsi+20h], eax
0x140008c93  mov     [rsi+18h], rax
0x140008c97  add     rsp, 28h
0x140008c9b  pop     rdi
0x140008c9c  pop     rsi
0x140008c9d  pop     rbp
0x140008c9e  pop     rbx
0x140008c9f  retn
```
