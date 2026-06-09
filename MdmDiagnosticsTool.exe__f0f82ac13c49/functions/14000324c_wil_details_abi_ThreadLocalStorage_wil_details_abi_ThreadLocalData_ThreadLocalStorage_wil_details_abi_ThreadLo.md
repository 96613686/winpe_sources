# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x14000324c`
- end: `0x140003326`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400031c4`

## callees

- `0x14000324c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400032a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400032d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400032f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400032a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400032d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400032f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003299`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400032ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400032e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003299`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400032ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400032e8`

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
0x14000324c  push    rbx
0x14000324e  push    rbp
0x14000324f  push    rsi
0x140003250  push    rdi
0x140003251  push    r12
0x140003253  push    r13
0x140003255  push    r14
0x140003257  push    r15
0x140003259  sub     rsp, 28h
0x14000325d  lea     r15, [rcx+50h]
0x140003261  mov     rdi, rcx
0x140003264  cmp     rcx, r15
0x140003267  jz      loc_140003315
0x14000326d  mov     rsi, [rdi]
0x140003270  jmp     loc_1400032FC
0x140003275  mov     r13, rsi
0x140003278  mov     r12, rsi
0x14000327b  mov     rsi, [rsi+8]
0x14000327f  movzx   eax, word ptr [r13+30h]
0x140003284  mov     rbp, [r13+28h]
0x140003288  lea     r14, [rax+rax*4]
0x14000328c  shl     r14, 4
0x140003290  add     r14, rbp
0x140003293  jmp     short loc_1400032C1
0x140003295  mov     rbx, [rbp+40h]
0x140003299  call    cs:__imp_GetProcessHeap
0x14000329f  mov     r8, rbx; lpMem
0x1400032a2  xor     edx, edx; dwFlags
0x1400032a4  mov     rcx, rax; hHeap
0x1400032a7  call    cs:__imp_HeapFree
0x1400032ad  mov     qword ptr [rbp+40h], 0
0x1400032b5  mov     qword ptr [rbp+48h], 0
0x1400032bd  add     rbp, 50h ; 'P'
0x1400032c1  cmp     rbp, r14
0x1400032c4  jnz     short loc_140003295
0x1400032c6  mov     rbx, [r13+28h]
0x1400032ca  call    cs:__imp_GetProcessHeap
0x1400032d0  mov     r8, rbx; lpMem
0x1400032d3  xor     edx, edx; dwFlags
0x1400032d5  mov     rcx, rax; hHeap
0x1400032d8  call    cs:__imp_HeapFree
0x1400032de  xor     eax, eax
0x1400032e0  mov     [r13+30h], eax
0x1400032e4  mov     [r13+28h], rax
0x1400032e8  call    cs:__imp_GetProcessHeap
0x1400032ee  mov     r8, r12; lpMem
0x1400032f1  xor     edx, edx; dwFlags
0x1400032f3  mov     rcx, rax; hHeap
0x1400032f6  call    cs:__imp_HeapFree
0x1400032fc  test    rsi, rsi
0x1400032ff  jnz     loc_140003275
0x140003305  mov     [rdi], rsi
0x140003308  add     rdi, 8
0x14000330c  cmp     rdi, r15
0x14000330f  jnz     loc_14000326D
0x140003315  add     rsp, 28h
0x140003319  pop     r15
0x14000331b  pop     r14
0x14000331d  pop     r13
0x14000331f  pop     r12
0x140003321  pop     rdi
0x140003322  pop     rsi
0x140003323  pop     rbp
0x140003324  pop     rbx
0x140003325  retn
```
