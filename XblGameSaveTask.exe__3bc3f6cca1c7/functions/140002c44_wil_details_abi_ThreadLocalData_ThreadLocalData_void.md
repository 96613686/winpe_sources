# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140002c44`
- end: `0x140002cc0`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002a8c`

## callees

- `0x140002c44`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002c77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002ca8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002c77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002ca8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002c69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002c9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002c69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002c9a`

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
0x140002c44  push    rbx
0x140002c46  push    rbp
0x140002c47  push    rsi
0x140002c48  push    rdi
0x140002c49  sub     rsp, 28h
0x140002c4d  movzx   eax, word ptr [rcx+20h]
0x140002c51  mov     rsi, rcx
0x140002c54  mov     rdi, [rcx+18h]
0x140002c58  lea     rbp, [rax+rax*4]
0x140002c5c  shl     rbp, 4
0x140002c60  add     rbp, rdi
0x140002c63  jmp     short loc_140002C91
0x140002c65  mov     rbx, [rdi+40h]
0x140002c69  call    cs:__imp_GetProcessHeap
0x140002c6f  mov     r8, rbx; lpMem
0x140002c72  xor     edx, edx; dwFlags
0x140002c74  mov     rcx, rax; hHeap
0x140002c77  call    cs:__imp_HeapFree
0x140002c7d  mov     qword ptr [rdi+40h], 0
0x140002c85  mov     qword ptr [rdi+48h], 0
0x140002c8d  add     rdi, 50h ; 'P'
0x140002c91  cmp     rdi, rbp
0x140002c94  jnz     short loc_140002C65
0x140002c96  mov     rbx, [rsi+18h]
0x140002c9a  call    cs:__imp_GetProcessHeap
0x140002ca0  mov     r8, rbx; lpMem
0x140002ca3  xor     edx, edx; dwFlags
0x140002ca5  mov     rcx, rax; hHeap
0x140002ca8  call    cs:__imp_HeapFree
0x140002cae  xor     eax, eax
0x140002cb0  mov     [rsi+20h], eax
0x140002cb3  mov     [rsi+18h], rax
0x140002cb7  add     rsp, 28h
0x140002cbb  pop     rdi
0x140002cbc  pop     rsi
0x140002cbd  pop     rbp
0x140002cbe  pop     rbx
0x140002cbf  retn
```
