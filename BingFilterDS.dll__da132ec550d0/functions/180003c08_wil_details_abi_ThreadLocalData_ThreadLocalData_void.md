# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003c08`
- end: `0x180003c84`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a58`

## callees

- `0x180003c08`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c5e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c6c`

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
0x180003c08  push    rbx
0x180003c0a  push    rbp
0x180003c0b  push    rsi
0x180003c0c  push    rdi
0x180003c0d  sub     rsp, 28h
0x180003c11  movzx   eax, word ptr [rcx+20h]
0x180003c15  mov     rsi, rcx
0x180003c18  mov     rdi, [rcx+18h]
0x180003c1c  lea     rbp, [rax+rax*4]
0x180003c20  shl     rbp, 4
0x180003c24  add     rbp, rdi
0x180003c27  jmp     short loc_180003C55
0x180003c29  mov     rbx, [rdi+40h]
0x180003c2d  call    cs:__imp_GetProcessHeap
0x180003c33  mov     r8, rbx; lpMem
0x180003c36  xor     edx, edx; dwFlags
0x180003c38  mov     rcx, rax; hHeap
0x180003c3b  call    cs:__imp_HeapFree
0x180003c41  mov     qword ptr [rdi+40h], 0
0x180003c49  mov     qword ptr [rdi+48h], 0
0x180003c51  add     rdi, 50h ; 'P'
0x180003c55  cmp     rdi, rbp
0x180003c58  jnz     short loc_180003C29
0x180003c5a  mov     rbx, [rsi+18h]
0x180003c5e  call    cs:__imp_GetProcessHeap
0x180003c64  mov     r8, rbx; lpMem
0x180003c67  xor     edx, edx; dwFlags
0x180003c69  mov     rcx, rax; hHeap
0x180003c6c  call    cs:__imp_HeapFree
0x180003c72  xor     eax, eax
0x180003c74  mov     [rsi+20h], eax
0x180003c77  mov     [rsi+18h], rax
0x180003c7b  add     rsp, 28h
0x180003c7f  pop     rdi
0x180003c80  pop     rsi
0x180003c81  pop     rbp
0x180003c82  pop     rbx
0x180003c83  retn
```
