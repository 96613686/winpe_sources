# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003150`
- end: `0x1800031e5`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002dcc`

## callees

- `0x180003150`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180003175`
- `KERNEL32!GetProcessHeap` at `0x1800031b2`
- `KERNEL32!GetProcessHeap` at `0x180003175`
- `KERNEL32!GetProcessHeap` at `0x1800031b2`
- `KERNEL32!HeapFree` at `0x180003189`
- `KERNEL32!HeapFree` at `0x1800031c6`
- `KERNEL32!HeapFree` at `0x180003189`
- `KERNEL32!HeapFree` at `0x1800031c6`

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
0x180003150  push    rbx
0x180003152  push    rbp
0x180003153  push    rsi
0x180003154  push    rdi
0x180003155  sub     rsp, 28h
0x180003159  movzx   eax, word ptr [rcx+20h]
0x18000315d  mov     rsi, rcx
0x180003160  mov     rdi, [rcx+18h]
0x180003164  lea     rbp, [rax+rax*4]
0x180003168  shl     rbp, 4
0x18000316c  add     rbp, rdi
0x18000316f  jmp     short loc_1800031A9
0x180003171  mov     rbx, [rdi+40h]
0x180003175  call    cs:__imp_GetProcessHeap
0x18000317c  nop     dword ptr [rax+rax+00h]
0x180003181  mov     r8, rbx; lpMem
0x180003184  xor     edx, edx; dwFlags
0x180003186  mov     rcx, rax; hHeap
0x180003189  call    cs:__imp_HeapFree
0x180003190  nop     dword ptr [rax+rax+00h]
0x180003195  mov     qword ptr [rdi+40h], 0
0x18000319d  mov     qword ptr [rdi+48h], 0
0x1800031a5  add     rdi, 50h ; 'P'
0x1800031a9  cmp     rdi, rbp
0x1800031ac  jnz     short loc_180003171
0x1800031ae  mov     rbx, [rsi+18h]
0x1800031b2  call    cs:__imp_GetProcessHeap
0x1800031b9  nop     dword ptr [rax+rax+00h]
0x1800031be  mov     r8, rbx; lpMem
0x1800031c1  xor     edx, edx; dwFlags
0x1800031c3  mov     rcx, rax; hHeap
0x1800031c6  call    cs:__imp_HeapFree
0x1800031cd  nop     dword ptr [rax+rax+00h]
0x1800031d2  xor     eax, eax
0x1800031d4  mov     [rsi+20h], eax
0x1800031d7  mov     [rsi+18h], rax
0x1800031db  add     rsp, 28h
0x1800031df  pop     rdi
0x1800031e0  pop     rsi
0x1800031e1  pop     rbp
0x1800031e2  pop     rbx
0x1800031e3  retn
```
