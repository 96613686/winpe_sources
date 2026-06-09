# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800038a0`
- end: `0x18000391c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007c7c`

## callees

- `0x1800038a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003904`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003904`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038f6`

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
0x1800038a0  push    rbx
0x1800038a2  push    rbp
0x1800038a3  push    rsi
0x1800038a4  push    rdi
0x1800038a5  sub     rsp, 28h
0x1800038a9  movzx   eax, word ptr [rcx+20h]
0x1800038ad  mov     rsi, rcx
0x1800038b0  mov     rdi, [rcx+18h]
0x1800038b4  lea     rbp, [rax+rax*4]
0x1800038b8  shl     rbp, 4
0x1800038bc  add     rbp, rdi
0x1800038bf  jmp     short loc_1800038ED
0x1800038c1  mov     rbx, [rdi+40h]
0x1800038c5  call    cs:__imp_GetProcessHeap
0x1800038cb  mov     r8, rbx; lpMem
0x1800038ce  xor     edx, edx; dwFlags
0x1800038d0  mov     rcx, rax; hHeap
0x1800038d3  call    cs:__imp_HeapFree
0x1800038d9  mov     qword ptr [rdi+40h], 0
0x1800038e1  mov     qword ptr [rdi+48h], 0
0x1800038e9  add     rdi, 50h ; 'P'
0x1800038ed  cmp     rdi, rbp
0x1800038f0  jnz     short loc_1800038C1
0x1800038f2  mov     rbx, [rsi+18h]
0x1800038f6  call    cs:__imp_GetProcessHeap
0x1800038fc  mov     r8, rbx; lpMem
0x1800038ff  xor     edx, edx; dwFlags
0x180003901  mov     rcx, rax; hHeap
0x180003904  call    cs:__imp_HeapFree
0x18000390a  xor     eax, eax
0x18000390c  mov     [rsi+20h], eax
0x18000390f  mov     [rsi+18h], rax
0x180003913  add     rsp, 28h
0x180003917  pop     rdi
0x180003918  pop     rsi
0x180003919  pop     rbp
0x18000391a  pop     rbx
0x18000391b  retn
```
