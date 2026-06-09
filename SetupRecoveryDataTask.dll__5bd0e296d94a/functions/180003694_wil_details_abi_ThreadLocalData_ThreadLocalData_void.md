# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003694`
- end: `0x180003710`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002f7c`

## callees

- `0x180003694`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036ea`

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
0x180003694  push    rbx
0x180003696  push    rbp
0x180003697  push    rsi
0x180003698  push    rdi
0x180003699  sub     rsp, 28h
0x18000369d  movzx   eax, word ptr [rcx+20h]
0x1800036a1  mov     rsi, rcx
0x1800036a4  mov     rdi, [rcx+18h]
0x1800036a8  lea     rbp, [rax+rax*4]
0x1800036ac  shl     rbp, 4
0x1800036b0  add     rbp, rdi
0x1800036b3  jmp     short loc_1800036E1
0x1800036b5  mov     rbx, [rdi+40h]
0x1800036b9  call    cs:__imp_GetProcessHeap
0x1800036bf  mov     r8, rbx; lpMem
0x1800036c2  xor     edx, edx; dwFlags
0x1800036c4  mov     rcx, rax; hHeap
0x1800036c7  call    cs:__imp_HeapFree
0x1800036cd  mov     qword ptr [rdi+40h], 0
0x1800036d5  mov     qword ptr [rdi+48h], 0
0x1800036dd  add     rdi, 50h ; 'P'
0x1800036e1  cmp     rdi, rbp
0x1800036e4  jnz     short loc_1800036B5
0x1800036e6  mov     rbx, [rsi+18h]
0x1800036ea  call    cs:__imp_GetProcessHeap
0x1800036f0  mov     r8, rbx; lpMem
0x1800036f3  xor     edx, edx; dwFlags
0x1800036f5  mov     rcx, rax; hHeap
0x1800036f8  call    cs:__imp_HeapFree
0x1800036fe  xor     eax, eax
0x180003700  mov     [rsi+20h], eax
0x180003703  mov     [rsi+18h], rax
0x180003707  add     rsp, 28h
0x18000370b  pop     rdi
0x18000370c  pop     rsi
0x18000370d  pop     rbp
0x18000370e  pop     rbx
0x18000370f  retn
```
