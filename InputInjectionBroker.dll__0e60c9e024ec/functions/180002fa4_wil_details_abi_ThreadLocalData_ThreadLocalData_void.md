# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180002fa4`
- end: `0x180003020`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002df4`

## callees

- `0x180002fa4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002fc9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002ffa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002fc9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002ffa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002fd7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003008`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002fd7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003008`

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
0x180002fa4  push    rbx
0x180002fa6  push    rbp
0x180002fa7  push    rsi
0x180002fa8  push    rdi
0x180002fa9  sub     rsp, 28h
0x180002fad  movzx   eax, word ptr [rcx+20h]
0x180002fb1  mov     rsi, rcx
0x180002fb4  mov     rdi, [rcx+18h]
0x180002fb8  lea     rbp, [rax+rax*4]
0x180002fbc  shl     rbp, 4
0x180002fc0  add     rbp, rdi
0x180002fc3  jmp     short loc_180002FF1
0x180002fc5  mov     rbx, [rdi+40h]
0x180002fc9  call    cs:__imp_GetProcessHeap
0x180002fcf  mov     r8, rbx; lpMem
0x180002fd2  xor     edx, edx; dwFlags
0x180002fd4  mov     rcx, rax; hHeap
0x180002fd7  call    cs:__imp_HeapFree
0x180002fdd  mov     qword ptr [rdi+40h], 0
0x180002fe5  mov     qword ptr [rdi+48h], 0
0x180002fed  add     rdi, 50h ; 'P'
0x180002ff1  cmp     rdi, rbp
0x180002ff4  jnz     short loc_180002FC5
0x180002ff6  mov     rbx, [rsi+18h]
0x180002ffa  call    cs:__imp_GetProcessHeap
0x180003000  mov     r8, rbx; lpMem
0x180003003  xor     edx, edx; dwFlags
0x180003005  mov     rcx, rax; hHeap
0x180003008  call    cs:__imp_HeapFree
0x18000300e  xor     eax, eax
0x180003010  mov     [rsi+20h], eax
0x180003013  mov     [rsi+18h], rax
0x180003017  add     rsp, 28h
0x18000301b  pop     rdi
0x18000301c  pop     rsi
0x18000301d  pop     rbp
0x18000301e  pop     rbx
0x18000301f  retn
```
