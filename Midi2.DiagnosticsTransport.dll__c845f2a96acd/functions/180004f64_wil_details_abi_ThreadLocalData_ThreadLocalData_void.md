# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180004f64`
- end: `0x180004fe0`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004cfc`

## callees

- `0x180004f64`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004fba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004fba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004fc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004fc8`

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
0x180004f64  push    rbx
0x180004f66  push    rbp
0x180004f67  push    rsi
0x180004f68  push    rdi
0x180004f69  sub     rsp, 28h
0x180004f6d  movzx   eax, word ptr [rcx+20h]
0x180004f71  mov     rsi, rcx
0x180004f74  mov     rdi, [rcx+18h]
0x180004f78  lea     rbp, [rax+rax*4]
0x180004f7c  shl     rbp, 4
0x180004f80  add     rbp, rdi
0x180004f83  jmp     short loc_180004FB1
0x180004f85  mov     rbx, [rdi+40h]
0x180004f89  call    cs:__imp_GetProcessHeap
0x180004f8f  mov     r8, rbx; lpMem
0x180004f92  xor     edx, edx; dwFlags
0x180004f94  mov     rcx, rax; hHeap
0x180004f97  call    cs:__imp_HeapFree
0x180004f9d  mov     qword ptr [rdi+40h], 0
0x180004fa5  mov     qword ptr [rdi+48h], 0
0x180004fad  add     rdi, 50h ; 'P'
0x180004fb1  cmp     rdi, rbp
0x180004fb4  jnz     short loc_180004F85
0x180004fb6  mov     rbx, [rsi+18h]
0x180004fba  call    cs:__imp_GetProcessHeap
0x180004fc0  mov     r8, rbx; lpMem
0x180004fc3  xor     edx, edx; dwFlags
0x180004fc5  mov     rcx, rax; hHeap
0x180004fc8  call    cs:__imp_HeapFree
0x180004fce  xor     eax, eax
0x180004fd0  mov     [rsi+20h], eax
0x180004fd3  mov     [rsi+18h], rax
0x180004fd7  add     rsp, 28h
0x180004fdb  pop     rdi
0x180004fdc  pop     rsi
0x180004fdd  pop     rbp
0x180004fde  pop     rbx
0x180004fdf  retn
```
