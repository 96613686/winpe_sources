# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x1800085e0`
- end: `0x1800086ba`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008528`

## callees

- `0x1800085e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000863b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000866c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000868a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000863b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000866c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000868a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000862d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000865e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000867c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000862d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000865e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000867c`

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
0x1800085e0  push    rbx
0x1800085e2  push    rbp
0x1800085e3  push    rsi
0x1800085e4  push    rdi
0x1800085e5  push    r12
0x1800085e7  push    r13
0x1800085e9  push    r14
0x1800085eb  push    r15
0x1800085ed  sub     rsp, 28h
0x1800085f1  lea     r15, [rcx+50h]
0x1800085f5  mov     rdi, rcx
0x1800085f8  cmp     rcx, r15
0x1800085fb  jz      loc_1800086A9
0x180008601  mov     rsi, [rdi]
0x180008604  jmp     loc_180008690
0x180008609  mov     r13, rsi
0x18000860c  mov     r12, rsi
0x18000860f  mov     rsi, [rsi+8]
0x180008613  movzx   eax, word ptr [r13+30h]
0x180008618  mov     rbp, [r13+28h]
0x18000861c  lea     r14, [rax+rax*4]
0x180008620  shl     r14, 4
0x180008624  add     r14, rbp
0x180008627  jmp     short loc_180008655
0x180008629  mov     rbx, [rbp+40h]
0x18000862d  call    cs:__imp_GetProcessHeap
0x180008633  mov     r8, rbx; lpMem
0x180008636  xor     edx, edx; dwFlags
0x180008638  mov     rcx, rax; hHeap
0x18000863b  call    cs:__imp_HeapFree
0x180008641  mov     qword ptr [rbp+40h], 0
0x180008649  mov     qword ptr [rbp+48h], 0
0x180008651  add     rbp, 50h ; 'P'
0x180008655  cmp     rbp, r14
0x180008658  jnz     short loc_180008629
0x18000865a  mov     rbx, [r13+28h]
0x18000865e  call    cs:__imp_GetProcessHeap
0x180008664  mov     r8, rbx; lpMem
0x180008667  xor     edx, edx; dwFlags
0x180008669  mov     rcx, rax; hHeap
0x18000866c  call    cs:__imp_HeapFree
0x180008672  xor     eax, eax
0x180008674  mov     [r13+30h], eax
0x180008678  mov     [r13+28h], rax
0x18000867c  call    cs:__imp_GetProcessHeap
0x180008682  mov     r8, r12; lpMem
0x180008685  xor     edx, edx; dwFlags
0x180008687  mov     rcx, rax; hHeap
0x18000868a  call    cs:__imp_HeapFree
0x180008690  test    rsi, rsi
0x180008693  jnz     loc_180008609
0x180008699  mov     [rdi], rsi
0x18000869c  add     rdi, 8
0x1800086a0  cmp     rdi, r15
0x1800086a3  jnz     loc_180008601
0x1800086a9  add     rsp, 28h
0x1800086ad  pop     r15
0x1800086af  pop     r14
0x1800086b1  pop     r13
0x1800086b3  pop     r12
0x1800086b5  pop     rdi
0x1800086b6  pop     rsi
0x1800086b7  pop     rbp
0x1800086b8  pop     rbx
0x1800086b9  retn
```
