# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003cc0`
- end: `0x180003d3c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003b08`

## callees

- `0x180003cc0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cf3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d24`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cf3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ce5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ce5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d16`

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
0x180003cc0  push    rbx
0x180003cc2  push    rbp
0x180003cc3  push    rsi
0x180003cc4  push    rdi
0x180003cc5  sub     rsp, 28h
0x180003cc9  movzx   eax, word ptr [rcx+20h]
0x180003ccd  mov     rsi, rcx
0x180003cd0  mov     rdi, [rcx+18h]
0x180003cd4  lea     rbp, [rax+rax*4]
0x180003cd8  shl     rbp, 4
0x180003cdc  add     rbp, rdi
0x180003cdf  jmp     short loc_180003D0D
0x180003ce1  mov     rbx, [rdi+40h]
0x180003ce5  call    cs:__imp_GetProcessHeap
0x180003ceb  mov     r8, rbx; lpMem
0x180003cee  xor     edx, edx; dwFlags
0x180003cf0  mov     rcx, rax; hHeap
0x180003cf3  call    cs:__imp_HeapFree
0x180003cf9  mov     qword ptr [rdi+40h], 0
0x180003d01  mov     qword ptr [rdi+48h], 0
0x180003d09  add     rdi, 50h ; 'P'
0x180003d0d  cmp     rdi, rbp
0x180003d10  jnz     short loc_180003CE1
0x180003d12  mov     rbx, [rsi+18h]
0x180003d16  call    cs:__imp_GetProcessHeap
0x180003d1c  mov     r8, rbx; lpMem
0x180003d1f  xor     edx, edx; dwFlags
0x180003d21  mov     rcx, rax; hHeap
0x180003d24  call    cs:__imp_HeapFree
0x180003d2a  xor     eax, eax
0x180003d2c  mov     [rsi+20h], eax
0x180003d2f  mov     [rsi+18h], rax
0x180003d33  add     rsp, 28h
0x180003d37  pop     rdi
0x180003d38  pop     rsi
0x180003d39  pop     rbp
0x180003d3a  pop     rbx
0x180003d3b  retn
```
