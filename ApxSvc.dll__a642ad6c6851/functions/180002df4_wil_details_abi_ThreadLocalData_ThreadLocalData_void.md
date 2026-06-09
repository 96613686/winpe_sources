# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180002df4`
- end: `0x180002e70`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002c3c`

## callees

- `0x180002df4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002e27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002e58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002e27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002e58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002e19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002e4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002e19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002e4a`

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
0x180002df4  push    rbx
0x180002df6  push    rbp
0x180002df7  push    rsi
0x180002df8  push    rdi
0x180002df9  sub     rsp, 28h
0x180002dfd  movzx   eax, word ptr [rcx+20h]
0x180002e01  mov     rsi, rcx
0x180002e04  mov     rdi, [rcx+18h]
0x180002e08  lea     rbp, [rax+rax*4]
0x180002e0c  shl     rbp, 4
0x180002e10  add     rbp, rdi
0x180002e13  jmp     short loc_180002E41
0x180002e15  mov     rbx, [rdi+40h]
0x180002e19  call    cs:__imp_GetProcessHeap
0x180002e1f  mov     r8, rbx; lpMem
0x180002e22  xor     edx, edx; dwFlags
0x180002e24  mov     rcx, rax; hHeap
0x180002e27  call    cs:__imp_HeapFree
0x180002e2d  mov     qword ptr [rdi+40h], 0
0x180002e35  mov     qword ptr [rdi+48h], 0
0x180002e3d  add     rdi, 50h ; 'P'
0x180002e41  cmp     rdi, rbp
0x180002e44  jnz     short loc_180002E15
0x180002e46  mov     rbx, [rsi+18h]
0x180002e4a  call    cs:__imp_GetProcessHeap
0x180002e50  mov     r8, rbx; lpMem
0x180002e53  xor     edx, edx; dwFlags
0x180002e55  mov     rcx, rax; hHeap
0x180002e58  call    cs:__imp_HeapFree
0x180002e5e  xor     eax, eax
0x180002e60  mov     [rsi+20h], eax
0x180002e63  mov     [rsi+18h], rax
0x180002e67  add     rsp, 28h
0x180002e6b  pop     rdi
0x180002e6c  pop     rsi
0x180002e6d  pop     rbp
0x180002e6e  pop     rbx
0x180002e6f  retn
```
