# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x1800047ac`
- end: `0x180004886`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800046f4`

## callees

- `0x1800047ac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000482a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004848`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000482a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004848`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004807`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004838`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004856`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004807`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004838`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004856`

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
0x1800047ac  push    rbx
0x1800047ae  push    rbp
0x1800047af  push    rsi
0x1800047b0  push    rdi
0x1800047b1  push    r12
0x1800047b3  push    r13
0x1800047b5  push    r14
0x1800047b7  push    r15
0x1800047b9  sub     rsp, 28h
0x1800047bd  lea     r15, [rcx+50h]
0x1800047c1  mov     rdi, rcx
0x1800047c4  cmp     rcx, r15
0x1800047c7  jz      loc_180004875
0x1800047cd  mov     rsi, [rdi]
0x1800047d0  jmp     loc_18000485C
0x1800047d5  mov     r13, rsi
0x1800047d8  mov     r12, rsi
0x1800047db  mov     rsi, [rsi+8]
0x1800047df  movzx   eax, word ptr [r13+30h]
0x1800047e4  mov     rbp, [r13+28h]
0x1800047e8  lea     r14, [rax+rax*4]
0x1800047ec  shl     r14, 4
0x1800047f0  add     r14, rbp
0x1800047f3  jmp     short loc_180004821
0x1800047f5  mov     rbx, [rbp+40h]
0x1800047f9  call    cs:__imp_GetProcessHeap
0x1800047ff  mov     r8, rbx; lpMem
0x180004802  xor     edx, edx; dwFlags
0x180004804  mov     rcx, rax; hHeap
0x180004807  call    cs:__imp_HeapFree
0x18000480d  mov     qword ptr [rbp+40h], 0
0x180004815  mov     qword ptr [rbp+48h], 0
0x18000481d  add     rbp, 50h ; 'P'
0x180004821  cmp     rbp, r14
0x180004824  jnz     short loc_1800047F5
0x180004826  mov     rbx, [r13+28h]
0x18000482a  call    cs:__imp_GetProcessHeap
0x180004830  mov     r8, rbx; lpMem
0x180004833  xor     edx, edx; dwFlags
0x180004835  mov     rcx, rax; hHeap
0x180004838  call    cs:__imp_HeapFree
0x18000483e  xor     eax, eax
0x180004840  mov     [r13+30h], eax
0x180004844  mov     [r13+28h], rax
0x180004848  call    cs:__imp_GetProcessHeap
0x18000484e  mov     r8, r12; lpMem
0x180004851  xor     edx, edx; dwFlags
0x180004853  mov     rcx, rax; hHeap
0x180004856  call    cs:__imp_HeapFree
0x18000485c  test    rsi, rsi
0x18000485f  jnz     loc_1800047D5
0x180004865  mov     [rdi], rsi
0x180004868  add     rdi, 8
0x18000486c  cmp     rdi, r15
0x18000486f  jnz     loc_1800047CD
0x180004875  add     rsp, 28h
0x180004879  pop     r15
0x18000487b  pop     r14
0x18000487d  pop     r13
0x18000487f  pop     r12
0x180004881  pop     rdi
0x180004882  pop     rsi
0x180004883  pop     rbp
0x180004884  pop     rbx
0x180004885  retn
```
