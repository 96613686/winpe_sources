# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140008480`
- end: `0x1400084fc`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140007eac`

## callees

- `0x140008480`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400084b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400084e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400084b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400084e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400084a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400084d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400084a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400084d6`

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
0x140008480  push    rbx
0x140008482  push    rbp
0x140008483  push    rsi
0x140008484  push    rdi
0x140008485  sub     rsp, 28h
0x140008489  movzx   eax, word ptr [rcx+20h]
0x14000848d  mov     rsi, rcx
0x140008490  mov     rdi, [rcx+18h]
0x140008494  lea     rbp, [rax+rax*4]
0x140008498  shl     rbp, 4
0x14000849c  add     rbp, rdi
0x14000849f  jmp     short loc_1400084CD
0x1400084a1  mov     rbx, [rdi+40h]
0x1400084a5  call    cs:__imp_GetProcessHeap
0x1400084ab  mov     r8, rbx; lpMem
0x1400084ae  xor     edx, edx; dwFlags
0x1400084b0  mov     rcx, rax; hHeap
0x1400084b3  call    cs:__imp_HeapFree
0x1400084b9  mov     qword ptr [rdi+40h], 0
0x1400084c1  mov     qword ptr [rdi+48h], 0
0x1400084c9  add     rdi, 50h ; 'P'
0x1400084cd  cmp     rdi, rbp
0x1400084d0  jnz     short loc_1400084A1
0x1400084d2  mov     rbx, [rsi+18h]
0x1400084d6  call    cs:__imp_GetProcessHeap
0x1400084dc  mov     r8, rbx; lpMem
0x1400084df  xor     edx, edx; dwFlags
0x1400084e1  mov     rcx, rax; hHeap
0x1400084e4  call    cs:__imp_HeapFree
0x1400084ea  xor     eax, eax
0x1400084ec  mov     [rsi+20h], eax
0x1400084ef  mov     [rsi+18h], rax
0x1400084f3  add     rsp, 28h
0x1400084f7  pop     rdi
0x1400084f8  pop     rsi
0x1400084f9  pop     rbp
0x1400084fa  pop     rbx
0x1400084fb  retn
```
