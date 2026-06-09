# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180005e6c`
- end: `0x180005ee8`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005898`

## callees

- `0x180005e6c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005e9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005ed0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005e9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005ed0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005e91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ec2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005e91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ec2`

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
0x180005e6c  push    rbx
0x180005e6e  push    rbp
0x180005e6f  push    rsi
0x180005e70  push    rdi
0x180005e71  sub     rsp, 28h
0x180005e75  movzx   eax, word ptr [rcx+20h]
0x180005e79  mov     rsi, rcx
0x180005e7c  mov     rdi, [rcx+18h]
0x180005e80  lea     rbp, [rax+rax*4]
0x180005e84  shl     rbp, 4
0x180005e88  add     rbp, rdi
0x180005e8b  jmp     short loc_180005EB9
0x180005e8d  mov     rbx, [rdi+40h]
0x180005e91  call    cs:__imp_GetProcessHeap
0x180005e97  mov     r8, rbx; lpMem
0x180005e9a  xor     edx, edx; dwFlags
0x180005e9c  mov     rcx, rax; hHeap
0x180005e9f  call    cs:__imp_HeapFree
0x180005ea5  mov     qword ptr [rdi+40h], 0
0x180005ead  mov     qword ptr [rdi+48h], 0
0x180005eb5  add     rdi, 50h ; 'P'
0x180005eb9  cmp     rdi, rbp
0x180005ebc  jnz     short loc_180005E8D
0x180005ebe  mov     rbx, [rsi+18h]
0x180005ec2  call    cs:__imp_GetProcessHeap
0x180005ec8  mov     r8, rbx; lpMem
0x180005ecb  xor     edx, edx; dwFlags
0x180005ecd  mov     rcx, rax; hHeap
0x180005ed0  call    cs:__imp_HeapFree
0x180005ed6  xor     eax, eax
0x180005ed8  mov     [rsi+20h], eax
0x180005edb  mov     [rsi+18h], rax
0x180005edf  add     rsp, 28h
0x180005ee3  pop     rdi
0x180005ee4  pop     rsi
0x180005ee5  pop     rbp
0x180005ee6  pop     rbx
0x180005ee7  retn
```
