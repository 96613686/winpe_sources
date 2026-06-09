# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003584`
- end: `0x180003600`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002fb0`

## callees

- `0x180003584`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035da`

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
0x180003584  push    rbx
0x180003586  push    rbp
0x180003587  push    rsi
0x180003588  push    rdi
0x180003589  sub     rsp, 28h
0x18000358d  movzx   eax, word ptr [rcx+20h]
0x180003591  mov     rsi, rcx
0x180003594  mov     rdi, [rcx+18h]
0x180003598  lea     rbp, [rax+rax*4]
0x18000359c  shl     rbp, 4
0x1800035a0  add     rbp, rdi
0x1800035a3  jmp     short loc_1800035D1
0x1800035a5  mov     rbx, [rdi+40h]
0x1800035a9  call    cs:__imp_GetProcessHeap
0x1800035af  mov     r8, rbx; lpMem
0x1800035b2  xor     edx, edx; dwFlags
0x1800035b4  mov     rcx, rax; hHeap
0x1800035b7  call    cs:__imp_HeapFree
0x1800035bd  mov     qword ptr [rdi+40h], 0
0x1800035c5  mov     qword ptr [rdi+48h], 0
0x1800035cd  add     rdi, 50h ; 'P'
0x1800035d1  cmp     rdi, rbp
0x1800035d4  jnz     short loc_1800035A5
0x1800035d6  mov     rbx, [rsi+18h]
0x1800035da  call    cs:__imp_GetProcessHeap
0x1800035e0  mov     r8, rbx; lpMem
0x1800035e3  xor     edx, edx; dwFlags
0x1800035e5  mov     rcx, rax; hHeap
0x1800035e8  call    cs:__imp_HeapFree
0x1800035ee  xor     eax, eax
0x1800035f0  mov     [rsi+20h], eax
0x1800035f3  mov     [rsi+18h], rax
0x1800035f7  add     rsp, 28h
0x1800035fb  pop     rdi
0x1800035fc  pop     rsi
0x1800035fd  pop     rbp
0x1800035fe  pop     rbx
0x1800035ff  retn
```
