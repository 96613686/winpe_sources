# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003eb4`
- end: `0x180003f30`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003c28`

## callees

- `0x180003eb4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ed9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ed9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f0a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ee7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ee7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f18`

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
0x180003eb4  push    rbx
0x180003eb6  push    rbp
0x180003eb7  push    rsi
0x180003eb8  push    rdi
0x180003eb9  sub     rsp, 28h
0x180003ebd  movzx   eax, word ptr [rcx+20h]
0x180003ec1  mov     rsi, rcx
0x180003ec4  mov     rdi, [rcx+18h]
0x180003ec8  lea     rbp, [rax+rax*4]
0x180003ecc  shl     rbp, 4
0x180003ed0  add     rbp, rdi
0x180003ed3  jmp     short loc_180003F01
0x180003ed5  mov     rbx, [rdi+40h]
0x180003ed9  call    cs:__imp_GetProcessHeap
0x180003edf  mov     r8, rbx; lpMem
0x180003ee2  xor     edx, edx; dwFlags
0x180003ee4  mov     rcx, rax; hHeap
0x180003ee7  call    cs:__imp_HeapFree
0x180003eed  mov     qword ptr [rdi+40h], 0
0x180003ef5  mov     qword ptr [rdi+48h], 0
0x180003efd  add     rdi, 50h ; 'P'
0x180003f01  cmp     rdi, rbp
0x180003f04  jnz     short loc_180003ED5
0x180003f06  mov     rbx, [rsi+18h]
0x180003f0a  call    cs:__imp_GetProcessHeap
0x180003f10  mov     r8, rbx; lpMem
0x180003f13  xor     edx, edx; dwFlags
0x180003f15  mov     rcx, rax; hHeap
0x180003f18  call    cs:__imp_HeapFree
0x180003f1e  xor     eax, eax
0x180003f20  mov     [rsi+20h], eax
0x180003f23  mov     [rsi+18h], rax
0x180003f27  add     rsp, 28h
0x180003f2b  pop     rdi
0x180003f2c  pop     rsi
0x180003f2d  pop     rbp
0x180003f2e  pop     rbx
0x180003f2f  retn
```
