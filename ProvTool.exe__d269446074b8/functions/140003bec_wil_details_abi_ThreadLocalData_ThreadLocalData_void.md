# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140003bec`
- end: `0x140003c68`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400037c0`

## callees

- `0x140003bec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c42`

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
0x140003bec  push    rbx
0x140003bee  push    rbp
0x140003bef  push    rsi
0x140003bf0  push    rdi
0x140003bf1  sub     rsp, 28h
0x140003bf5  movzx   eax, word ptr [rcx+20h]
0x140003bf9  mov     rsi, rcx
0x140003bfc  mov     rdi, [rcx+18h]
0x140003c00  lea     rbp, [rax+rax*4]
0x140003c04  shl     rbp, 4
0x140003c08  add     rbp, rdi
0x140003c0b  jmp     short loc_140003C39
0x140003c0d  mov     rbx, [rdi+40h]
0x140003c11  call    cs:__imp_GetProcessHeap
0x140003c17  mov     r8, rbx; lpMem
0x140003c1a  xor     edx, edx; dwFlags
0x140003c1c  mov     rcx, rax; hHeap
0x140003c1f  call    cs:__imp_HeapFree
0x140003c25  mov     qword ptr [rdi+40h], 0
0x140003c2d  mov     qword ptr [rdi+48h], 0
0x140003c35  add     rdi, 50h ; 'P'
0x140003c39  cmp     rdi, rbp
0x140003c3c  jnz     short loc_140003C0D
0x140003c3e  mov     rbx, [rsi+18h]
0x140003c42  call    cs:__imp_GetProcessHeap
0x140003c48  mov     r8, rbx; lpMem
0x140003c4b  xor     edx, edx; dwFlags
0x140003c4d  mov     rcx, rax; hHeap
0x140003c50  call    cs:__imp_HeapFree
0x140003c56  xor     eax, eax
0x140003c58  mov     [rsi+20h], eax
0x140003c5b  mov     [rsi+18h], rax
0x140003c5f  add     rsp, 28h
0x140003c63  pop     rdi
0x140003c64  pop     rsi
0x140003c65  pop     rbp
0x140003c66  pop     rbx
0x140003c67  retn
```
