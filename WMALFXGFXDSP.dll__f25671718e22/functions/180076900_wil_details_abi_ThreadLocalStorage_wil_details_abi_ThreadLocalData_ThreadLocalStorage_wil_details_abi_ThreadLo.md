# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180076900`
- end: `0x1800769da`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180076878`

## callees

- `0x180076900`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007694d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007697e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007699c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007694d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007697e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007699c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007695b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007698c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800769aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007695b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007698c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800769aa`

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
0x180076900  push    rbx
0x180076902  push    rbp
0x180076903  push    rsi
0x180076904  push    rdi
0x180076905  push    r12
0x180076907  push    r13
0x180076909  push    r14
0x18007690b  push    r15
0x18007690d  sub     rsp, 28h
0x180076911  lea     r15, [rcx+50h]
0x180076915  mov     rdi, rcx
0x180076918  cmp     rcx, r15
0x18007691b  jz      loc_1800769C9
0x180076921  mov     rsi, [rdi]
0x180076924  jmp     loc_1800769B0
0x180076929  mov     r13, rsi
0x18007692c  mov     r12, rsi
0x18007692f  mov     rsi, [rsi+8]
0x180076933  movzx   eax, word ptr [r13+30h]
0x180076938  mov     rbp, [r13+28h]
0x18007693c  lea     r14, [rax+rax*4]
0x180076940  shl     r14, 4
0x180076944  add     r14, rbp
0x180076947  jmp     short loc_180076975
0x180076949  mov     rbx, [rbp+40h]
0x18007694d  call    cs:__imp_GetProcessHeap
0x180076953  mov     r8, rbx; lpMem
0x180076956  xor     edx, edx; dwFlags
0x180076958  mov     rcx, rax; hHeap
0x18007695b  call    cs:__imp_HeapFree
0x180076961  mov     qword ptr [rbp+40h], 0
0x180076969  mov     qword ptr [rbp+48h], 0
0x180076971  add     rbp, 50h ; 'P'
0x180076975  cmp     rbp, r14
0x180076978  jnz     short loc_180076949
0x18007697a  mov     rbx, [r13+28h]
0x18007697e  call    cs:__imp_GetProcessHeap
0x180076984  mov     r8, rbx; lpMem
0x180076987  xor     edx, edx; dwFlags
0x180076989  mov     rcx, rax; hHeap
0x18007698c  call    cs:__imp_HeapFree
0x180076992  xor     eax, eax
0x180076994  mov     [r13+30h], eax
0x180076998  mov     [r13+28h], rax
0x18007699c  call    cs:__imp_GetProcessHeap
0x1800769a2  mov     r8, r12; lpMem
0x1800769a5  xor     edx, edx; dwFlags
0x1800769a7  mov     rcx, rax; hHeap
0x1800769aa  call    cs:__imp_HeapFree
0x1800769b0  test    rsi, rsi
0x1800769b3  jnz     loc_180076929
0x1800769b9  mov     [rdi], rsi
0x1800769bc  add     rdi, 8
0x1800769c0  cmp     rdi, r15
0x1800769c3  jnz     loc_180076921
0x1800769c9  add     rsp, 28h
0x1800769cd  pop     r15
0x1800769cf  pop     r14
0x1800769d1  pop     r13
0x1800769d3  pop     r12
0x1800769d5  pop     rdi
0x1800769d6  pop     rsi
0x1800769d7  pop     rbp
0x1800769d8  pop     rbx
0x1800769d9  retn
```
