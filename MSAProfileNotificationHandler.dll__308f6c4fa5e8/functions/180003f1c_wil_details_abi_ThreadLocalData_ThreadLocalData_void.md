# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003f1c`
- end: `0x180003f98`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003d74`

## callees

- `0x180003f1c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f41`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f41`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f72`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f4f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f4f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f80`

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
0x180003f1c  push    rbx
0x180003f1e  push    rbp
0x180003f1f  push    rsi
0x180003f20  push    rdi
0x180003f21  sub     rsp, 28h
0x180003f25  movzx   eax, word ptr [rcx+20h]
0x180003f29  mov     rsi, rcx
0x180003f2c  mov     rdi, [rcx+18h]
0x180003f30  lea     rbp, [rax+rax*4]
0x180003f34  shl     rbp, 4
0x180003f38  add     rbp, rdi
0x180003f3b  jmp     short loc_180003F69
0x180003f3d  mov     rbx, [rdi+40h]
0x180003f41  call    cs:__imp_GetProcessHeap
0x180003f47  mov     r8, rbx; lpMem
0x180003f4a  xor     edx, edx; dwFlags
0x180003f4c  mov     rcx, rax; hHeap
0x180003f4f  call    cs:__imp_HeapFree
0x180003f55  mov     qword ptr [rdi+40h], 0
0x180003f5d  mov     qword ptr [rdi+48h], 0
0x180003f65  add     rdi, 50h ; 'P'
0x180003f69  cmp     rdi, rbp
0x180003f6c  jnz     short loc_180003F3D
0x180003f6e  mov     rbx, [rsi+18h]
0x180003f72  call    cs:__imp_GetProcessHeap
0x180003f78  mov     r8, rbx; lpMem
0x180003f7b  xor     edx, edx; dwFlags
0x180003f7d  mov     rcx, rax; hHeap
0x180003f80  call    cs:__imp_HeapFree
0x180003f86  xor     eax, eax
0x180003f88  mov     [rsi+20h], eax
0x180003f8b  mov     [rsi+18h], rax
0x180003f8f  add     rsp, 28h
0x180003f93  pop     rdi
0x180003f94  pop     rsi
0x180003f95  pop     rbp
0x180003f96  pop     rbx
0x180003f97  retn
```
