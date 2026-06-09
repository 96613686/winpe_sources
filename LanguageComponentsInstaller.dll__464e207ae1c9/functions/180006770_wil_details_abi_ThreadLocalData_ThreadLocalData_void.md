# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180006770`
- end: `0x1800067ec`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000623c`

## callees

- `0x180006770`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800067a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800067d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800067a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800067d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006795`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006795`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067c6`

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
0x180006770  push    rbx
0x180006772  push    rbp
0x180006773  push    rsi
0x180006774  push    rdi
0x180006775  sub     rsp, 28h
0x180006779  movzx   eax, word ptr [rcx+20h]
0x18000677d  mov     rsi, rcx
0x180006780  mov     rdi, [rcx+18h]
0x180006784  lea     rbp, [rax+rax*4]
0x180006788  shl     rbp, 4
0x18000678c  add     rbp, rdi
0x18000678f  jmp     short loc_1800067BD
0x180006791  mov     rbx, [rdi+40h]
0x180006795  call    cs:__imp_GetProcessHeap
0x18000679b  mov     r8, rbx; lpMem
0x18000679e  xor     edx, edx; dwFlags
0x1800067a0  mov     rcx, rax; hHeap
0x1800067a3  call    cs:__imp_HeapFree
0x1800067a9  mov     qword ptr [rdi+40h], 0
0x1800067b1  mov     qword ptr [rdi+48h], 0
0x1800067b9  add     rdi, 50h ; 'P'
0x1800067bd  cmp     rdi, rbp
0x1800067c0  jnz     short loc_180006791
0x1800067c2  mov     rbx, [rsi+18h]
0x1800067c6  call    cs:__imp_GetProcessHeap
0x1800067cc  mov     r8, rbx; lpMem
0x1800067cf  xor     edx, edx; dwFlags
0x1800067d1  mov     rcx, rax; hHeap
0x1800067d4  call    cs:__imp_HeapFree
0x1800067da  xor     eax, eax
0x1800067dc  mov     [rsi+20h], eax
0x1800067df  mov     [rsi+18h], rax
0x1800067e3  add     rsp, 28h
0x1800067e7  pop     rdi
0x1800067e8  pop     rsi
0x1800067e9  pop     rbp
0x1800067ea  pop     rbx
0x1800067eb  retn
```
