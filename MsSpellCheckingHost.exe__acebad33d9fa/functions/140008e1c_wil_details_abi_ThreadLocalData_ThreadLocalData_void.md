# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140008e1c`
- end: `0x140008e98`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140008638`

## callees

- `0x140008e1c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008e4f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008e80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008e4f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008e80`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008e41`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008e72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008e41`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008e72`

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
0x140008e1c  push    rbx
0x140008e1e  push    rbp
0x140008e1f  push    rsi
0x140008e20  push    rdi
0x140008e21  sub     rsp, 28h
0x140008e25  movzx   eax, word ptr [rcx+20h]
0x140008e29  mov     rsi, rcx
0x140008e2c  mov     rdi, [rcx+18h]
0x140008e30  lea     rbp, [rax+rax*4]
0x140008e34  shl     rbp, 4
0x140008e38  add     rbp, rdi
0x140008e3b  jmp     short loc_140008E69
0x140008e3d  mov     rbx, [rdi+40h]
0x140008e41  call    cs:__imp_GetProcessHeap
0x140008e47  mov     r8, rbx; lpMem
0x140008e4a  xor     edx, edx; dwFlags
0x140008e4c  mov     rcx, rax; hHeap
0x140008e4f  call    cs:__imp_HeapFree
0x140008e55  mov     qword ptr [rdi+40h], 0
0x140008e5d  mov     qword ptr [rdi+48h], 0
0x140008e65  add     rdi, 50h ; 'P'
0x140008e69  cmp     rdi, rbp
0x140008e6c  jnz     short loc_140008E3D
0x140008e6e  mov     rbx, [rsi+18h]
0x140008e72  call    cs:__imp_GetProcessHeap
0x140008e78  mov     r8, rbx; lpMem
0x140008e7b  xor     edx, edx; dwFlags
0x140008e7d  mov     rcx, rax; hHeap
0x140008e80  call    cs:__imp_HeapFree
0x140008e86  xor     eax, eax
0x140008e88  mov     [rsi+20h], eax
0x140008e8b  mov     [rsi+18h], rax
0x140008e8f  add     rsp, 28h
0x140008e93  pop     rdi
0x140008e94  pop     rsi
0x140008e95  pop     rbp
0x140008e96  pop     rbx
0x140008e97  retn
```
