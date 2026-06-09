# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003d60`
- end: `0x180003ddc`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ba8`

## callees

- `0x180003d60`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003db6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003db6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d93`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003dc4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d93`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003dc4`

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
0x180003d60  push    rbx
0x180003d62  push    rbp
0x180003d63  push    rsi
0x180003d64  push    rdi
0x180003d65  sub     rsp, 28h
0x180003d69  movzx   eax, word ptr [rcx+20h]
0x180003d6d  mov     rsi, rcx
0x180003d70  mov     rdi, [rcx+18h]
0x180003d74  lea     rbp, [rax+rax*4]
0x180003d78  shl     rbp, 4
0x180003d7c  add     rbp, rdi
0x180003d7f  jmp     short loc_180003DAD
0x180003d81  mov     rbx, [rdi+40h]
0x180003d85  call    cs:__imp_GetProcessHeap
0x180003d8b  mov     r8, rbx; lpMem
0x180003d8e  xor     edx, edx; dwFlags
0x180003d90  mov     rcx, rax; hHeap
0x180003d93  call    cs:__imp_HeapFree
0x180003d99  mov     qword ptr [rdi+40h], 0
0x180003da1  mov     qword ptr [rdi+48h], 0
0x180003da9  add     rdi, 50h ; 'P'
0x180003dad  cmp     rdi, rbp
0x180003db0  jnz     short loc_180003D81
0x180003db2  mov     rbx, [rsi+18h]
0x180003db6  call    cs:__imp_GetProcessHeap
0x180003dbc  mov     r8, rbx; lpMem
0x180003dbf  xor     edx, edx; dwFlags
0x180003dc1  mov     rcx, rax; hHeap
0x180003dc4  call    cs:__imp_HeapFree
0x180003dca  xor     eax, eax
0x180003dcc  mov     [rsi+20h], eax
0x180003dcf  mov     [rsi+18h], rax
0x180003dd3  add     rsp, 28h
0x180003dd7  pop     rdi
0x180003dd8  pop     rsi
0x180003dd9  pop     rbp
0x180003dda  pop     rbx
0x180003ddb  retn
```
