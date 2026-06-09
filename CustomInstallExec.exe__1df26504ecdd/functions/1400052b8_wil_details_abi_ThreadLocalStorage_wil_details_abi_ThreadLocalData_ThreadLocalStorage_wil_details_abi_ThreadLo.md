# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x1400052b8`
- end: `0x140005392`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140005230`

## callees

- `0x1400052b8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005313`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005344`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005362`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005313`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005344`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005362`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005305`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005336`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005354`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005305`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005336`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005354`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        _QWORD *a1)
{
  _QWORD *v1; // r15
  _QWORD *v2; // rdi
  _QWORD *v3; // rsi
  _QWORD *v4; // r13
  void *v5; // r12
  __int64 v6; // rbp
  __int64 v7; // r14
  void *v8; // rbx
  HANDLE ProcessHeap; // rax
  void *v10; // rbx
  HANDLE v11; // rax
  HANDLE v12; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = (_QWORD *)*v2;
    while ( v3 )
    {
      v4 = v3;
      v5 = v3;
      v3 = (_QWORD *)v3[1];
      v6 = v4[5];
      v7 = v6 + 80LL * *((unsigned __int16 *)v4 + 24);
      while ( v6 != v7 )
      {
        v8 = *(void **)(v6 + 64);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v8);
        *(_QWORD *)(v6 + 64) = 0;
        *(_QWORD *)(v6 + 72) = 0;
        v6 += 80;
      }
      v10 = (void *)v4[5];
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v10);
      *((_DWORD *)v4 + 12) = 0;
      v4[5] = 0;
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v5);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x1400052b8  push    rbx
0x1400052ba  push    rbp
0x1400052bb  push    rsi
0x1400052bc  push    rdi
0x1400052bd  push    r12
0x1400052bf  push    r13
0x1400052c1  push    r14
0x1400052c3  push    r15
0x1400052c5  sub     rsp, 28h
0x1400052c9  lea     r15, [rcx+50h]
0x1400052cd  mov     rdi, rcx
0x1400052d0  cmp     rcx, r15
0x1400052d3  jz      loc_140005381
0x1400052d9  mov     rsi, [rdi]
0x1400052dc  jmp     loc_140005368
0x1400052e1  mov     r13, rsi
0x1400052e4  mov     r12, rsi
0x1400052e7  mov     rsi, [rsi+8]
0x1400052eb  movzx   eax, word ptr [r13+30h]
0x1400052f0  mov     rbp, [r13+28h]
0x1400052f4  lea     r14, [rax+rax*4]
0x1400052f8  shl     r14, 4
0x1400052fc  add     r14, rbp
0x1400052ff  jmp     short loc_14000532D
0x140005301  mov     rbx, [rbp+40h]
0x140005305  call    cs:__imp_GetProcessHeap
0x14000530b  mov     r8, rbx; lpMem
0x14000530e  xor     edx, edx; dwFlags
0x140005310  mov     rcx, rax; hHeap
0x140005313  call    cs:__imp_HeapFree
0x140005319  mov     qword ptr [rbp+40h], 0
0x140005321  mov     qword ptr [rbp+48h], 0
0x140005329  add     rbp, 50h ; 'P'
0x14000532d  cmp     rbp, r14
0x140005330  jnz     short loc_140005301
0x140005332  mov     rbx, [r13+28h]
0x140005336  call    cs:__imp_GetProcessHeap
0x14000533c  mov     r8, rbx; lpMem
0x14000533f  xor     edx, edx; dwFlags
0x140005341  mov     rcx, rax; hHeap
0x140005344  call    cs:__imp_HeapFree
0x14000534a  xor     eax, eax
0x14000534c  mov     [r13+30h], eax
0x140005350  mov     [r13+28h], rax
0x140005354  call    cs:__imp_GetProcessHeap
0x14000535a  mov     r8, r12; lpMem
0x14000535d  xor     edx, edx; dwFlags
0x14000535f  mov     rcx, rax; hHeap
0x140005362  call    cs:__imp_HeapFree
0x140005368  test    rsi, rsi
0x14000536b  jnz     loc_1400052E1
0x140005371  mov     [rdi], rsi
0x140005374  add     rdi, 8
0x140005378  cmp     rdi, r15
0x14000537b  jnz     loc_1400052D9
0x140005381  add     rsp, 28h
0x140005385  pop     r15
0x140005387  pop     r14
0x140005389  pop     r13
0x14000538b  pop     r12
0x14000538d  pop     rdi
0x14000538e  pop     rsi
0x14000538f  pop     rbp
0x140005390  pop     rbx
0x140005391  retn
```
