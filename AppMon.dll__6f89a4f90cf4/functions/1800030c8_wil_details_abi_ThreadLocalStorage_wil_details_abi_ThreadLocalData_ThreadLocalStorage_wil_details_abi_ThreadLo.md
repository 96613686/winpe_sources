# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x1800030c8`
- end: `0x1800031a2`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003040`

## callees

- `0x1800030c8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003123`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003154`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003172`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003123`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003154`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003172`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003115`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003146`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003164`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003115`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003146`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003164`

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
0x1800030c8  push    rbx
0x1800030ca  push    rbp
0x1800030cb  push    rsi
0x1800030cc  push    rdi
0x1800030cd  push    r12
0x1800030cf  push    r13
0x1800030d1  push    r14
0x1800030d3  push    r15
0x1800030d5  sub     rsp, 28h
0x1800030d9  lea     r15, [rcx+50h]
0x1800030dd  mov     rdi, rcx
0x1800030e0  cmp     rcx, r15
0x1800030e3  jz      loc_180003191
0x1800030e9  mov     rsi, [rdi]
0x1800030ec  jmp     loc_180003178
0x1800030f1  mov     r13, rsi
0x1800030f4  mov     r12, rsi
0x1800030f7  mov     rsi, [rsi+8]
0x1800030fb  movzx   eax, word ptr [r13+30h]
0x180003100  mov     rbp, [r13+28h]
0x180003104  lea     r14, [rax+rax*4]
0x180003108  shl     r14, 4
0x18000310c  add     r14, rbp
0x18000310f  jmp     short loc_18000313D
0x180003111  mov     rbx, [rbp+40h]
0x180003115  call    cs:__imp_GetProcessHeap
0x18000311b  mov     r8, rbx; lpMem
0x18000311e  xor     edx, edx; dwFlags
0x180003120  mov     rcx, rax; hHeap
0x180003123  call    cs:__imp_HeapFree
0x180003129  mov     qword ptr [rbp+40h], 0
0x180003131  mov     qword ptr [rbp+48h], 0
0x180003139  add     rbp, 50h ; 'P'
0x18000313d  cmp     rbp, r14
0x180003140  jnz     short loc_180003111
0x180003142  mov     rbx, [r13+28h]
0x180003146  call    cs:__imp_GetProcessHeap
0x18000314c  mov     r8, rbx; lpMem
0x18000314f  xor     edx, edx; dwFlags
0x180003151  mov     rcx, rax; hHeap
0x180003154  call    cs:__imp_HeapFree
0x18000315a  xor     eax, eax
0x18000315c  mov     [r13+30h], eax
0x180003160  mov     [r13+28h], rax
0x180003164  call    cs:__imp_GetProcessHeap
0x18000316a  mov     r8, r12; lpMem
0x18000316d  xor     edx, edx; dwFlags
0x18000316f  mov     rcx, rax; hHeap
0x180003172  call    cs:__imp_HeapFree
0x180003178  test    rsi, rsi
0x18000317b  jnz     loc_1800030F1
0x180003181  mov     [rdi], rsi
0x180003184  add     rdi, 8
0x180003188  cmp     rdi, r15
0x18000318b  jnz     loc_1800030E9
0x180003191  add     rsp, 28h
0x180003195  pop     r15
0x180003197  pop     r14
0x180003199  pop     r13
0x18000319b  pop     r12
0x18000319d  pop     rdi
0x18000319e  pop     rsi
0x18000319f  pop     rbp
0x1800031a0  pop     rbx
0x1800031a1  retn
```
