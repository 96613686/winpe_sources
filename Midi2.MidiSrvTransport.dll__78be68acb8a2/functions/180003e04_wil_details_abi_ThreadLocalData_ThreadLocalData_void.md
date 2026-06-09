# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003e04`
- end: `0x180003e80`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003b9c`

## callees

- `0x180003e04`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e68`

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
0x180003e04  push    rbx
0x180003e06  push    rbp
0x180003e07  push    rsi
0x180003e08  push    rdi
0x180003e09  sub     rsp, 28h
0x180003e0d  movzx   eax, word ptr [rcx+20h]
0x180003e11  mov     rsi, rcx
0x180003e14  mov     rdi, [rcx+18h]
0x180003e18  lea     rbp, [rax+rax*4]
0x180003e1c  shl     rbp, 4
0x180003e20  add     rbp, rdi
0x180003e23  jmp     short loc_180003E51
0x180003e25  mov     rbx, [rdi+40h]
0x180003e29  call    cs:__imp_GetProcessHeap
0x180003e2f  mov     r8, rbx; lpMem
0x180003e32  xor     edx, edx; dwFlags
0x180003e34  mov     rcx, rax; hHeap
0x180003e37  call    cs:__imp_HeapFree
0x180003e3d  mov     qword ptr [rdi+40h], 0
0x180003e45  mov     qword ptr [rdi+48h], 0
0x180003e4d  add     rdi, 50h ; 'P'
0x180003e51  cmp     rdi, rbp
0x180003e54  jnz     short loc_180003E25
0x180003e56  mov     rbx, [rsi+18h]
0x180003e5a  call    cs:__imp_GetProcessHeap
0x180003e60  mov     r8, rbx; lpMem
0x180003e63  xor     edx, edx; dwFlags
0x180003e65  mov     rcx, rax; hHeap
0x180003e68  call    cs:__imp_HeapFree
0x180003e6e  xor     eax, eax
0x180003e70  mov     [rsi+20h], eax
0x180003e73  mov     [rsi+18h], rax
0x180003e77  add     rsp, 28h
0x180003e7b  pop     rdi
0x180003e7c  pop     rsi
0x180003e7d  pop     rbp
0x180003e7e  pop     rbx
0x180003e7f  retn
```
