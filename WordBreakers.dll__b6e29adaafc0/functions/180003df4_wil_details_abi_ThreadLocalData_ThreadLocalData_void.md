# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003df4`
- end: `0x180003e70`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003b3c`

## callees

- `0x180003df4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e58`

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
0x180003df4  push    rbx
0x180003df6  push    rbp
0x180003df7  push    rsi
0x180003df8  push    rdi
0x180003df9  sub     rsp, 28h
0x180003dfd  movzx   eax, word ptr [rcx+20h]
0x180003e01  mov     rsi, rcx
0x180003e04  mov     rdi, [rcx+18h]
0x180003e08  lea     rbp, [rax+rax*4]
0x180003e0c  shl     rbp, 4
0x180003e10  add     rbp, rdi
0x180003e13  jmp     short loc_180003E41
0x180003e15  mov     rbx, [rdi+40h]
0x180003e19  call    cs:__imp_GetProcessHeap
0x180003e1f  mov     r8, rbx; lpMem
0x180003e22  xor     edx, edx; dwFlags
0x180003e24  mov     rcx, rax; hHeap
0x180003e27  call    cs:__imp_HeapFree
0x180003e2d  mov     qword ptr [rdi+40h], 0
0x180003e35  mov     qword ptr [rdi+48h], 0
0x180003e3d  add     rdi, 50h ; 'P'
0x180003e41  cmp     rdi, rbp
0x180003e44  jnz     short loc_180003E15
0x180003e46  mov     rbx, [rsi+18h]
0x180003e4a  call    cs:__imp_GetProcessHeap
0x180003e50  mov     r8, rbx; lpMem
0x180003e53  xor     edx, edx; dwFlags
0x180003e55  mov     rcx, rax; hHeap
0x180003e58  call    cs:__imp_HeapFree
0x180003e5e  xor     eax, eax
0x180003e60  mov     [rsi+20h], eax
0x180003e63  mov     [rsi+18h], rax
0x180003e67  add     rsp, 28h
0x180003e6b  pop     rdi
0x180003e6c  pop     rsi
0x180003e6d  pop     rbp
0x180003e6e  pop     rbx
0x180003e6f  retn
```
