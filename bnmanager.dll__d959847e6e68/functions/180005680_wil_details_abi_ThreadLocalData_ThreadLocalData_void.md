# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180005680`
- end: `0x1800056fc`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005024`

## callees

- `0x180005680`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800056b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800056e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800056b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800056e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800056a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800056d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800056a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800056d6`

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
0x180005680  push    rbx
0x180005682  push    rbp
0x180005683  push    rsi
0x180005684  push    rdi
0x180005685  sub     rsp, 28h
0x180005689  movzx   eax, word ptr [rcx+20h]
0x18000568d  mov     rsi, rcx
0x180005690  mov     rdi, [rcx+18h]
0x180005694  lea     rbp, [rax+rax*4]
0x180005698  shl     rbp, 4
0x18000569c  add     rbp, rdi
0x18000569f  jmp     short loc_1800056CD
0x1800056a1  mov     rbx, [rdi+40h]
0x1800056a5  call    cs:__imp_GetProcessHeap
0x1800056ab  mov     r8, rbx; lpMem
0x1800056ae  xor     edx, edx; dwFlags
0x1800056b0  mov     rcx, rax; hHeap
0x1800056b3  call    cs:__imp_HeapFree
0x1800056b9  mov     qword ptr [rdi+40h], 0
0x1800056c1  mov     qword ptr [rdi+48h], 0
0x1800056c9  add     rdi, 50h ; 'P'
0x1800056cd  cmp     rdi, rbp
0x1800056d0  jnz     short loc_1800056A1
0x1800056d2  mov     rbx, [rsi+18h]
0x1800056d6  call    cs:__imp_GetProcessHeap
0x1800056dc  mov     r8, rbx; lpMem
0x1800056df  xor     edx, edx; dwFlags
0x1800056e1  mov     rcx, rax; hHeap
0x1800056e4  call    cs:__imp_HeapFree
0x1800056ea  xor     eax, eax
0x1800056ec  mov     [rsi+20h], eax
0x1800056ef  mov     [rsi+18h], rax
0x1800056f3  add     rsp, 28h
0x1800056f7  pop     rdi
0x1800056f8  pop     rsi
0x1800056f9  pop     rbp
0x1800056fa  pop     rbx
0x1800056fb  retn
```
