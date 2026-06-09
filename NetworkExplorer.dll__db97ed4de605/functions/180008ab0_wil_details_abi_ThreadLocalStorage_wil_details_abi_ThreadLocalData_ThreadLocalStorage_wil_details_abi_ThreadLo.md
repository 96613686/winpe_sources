# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180008ab0`
- end: `0x180008b8a`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008a80`

## callees

- `0x180008ab0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008b0b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008b3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008b5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008b0b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008b3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008b5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008afd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b4c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008afd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b4c`

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
0x180008ab0  push    rbx
0x180008ab2  push    rbp
0x180008ab3  push    rsi
0x180008ab4  push    rdi
0x180008ab5  push    r12
0x180008ab7  push    r13
0x180008ab9  push    r14
0x180008abb  push    r15
0x180008abd  sub     rsp, 28h
0x180008ac1  lea     r15, [rcx+50h]
0x180008ac5  mov     rdi, rcx
0x180008ac8  cmp     rcx, r15
0x180008acb  jz      loc_180008B79
0x180008ad1  mov     rsi, [rdi]
0x180008ad4  jmp     loc_180008B60
0x180008ad9  mov     r13, rsi
0x180008adc  mov     r12, rsi
0x180008adf  mov     rsi, [rsi+8]
0x180008ae3  movzx   eax, word ptr [r13+30h]
0x180008ae8  mov     rbp, [r13+28h]
0x180008aec  lea     r14, [rax+rax*4]
0x180008af0  shl     r14, 4
0x180008af4  add     r14, rbp
0x180008af7  jmp     short loc_180008B25
0x180008af9  mov     rbx, [rbp+40h]
0x180008afd  call    cs:__imp_GetProcessHeap
0x180008b03  mov     r8, rbx; lpMem
0x180008b06  xor     edx, edx; dwFlags
0x180008b08  mov     rcx, rax; hHeap
0x180008b0b  call    cs:__imp_HeapFree
0x180008b11  mov     qword ptr [rbp+40h], 0
0x180008b19  mov     qword ptr [rbp+48h], 0
0x180008b21  add     rbp, 50h ; 'P'
0x180008b25  cmp     rbp, r14
0x180008b28  jnz     short loc_180008AF9
0x180008b2a  mov     rbx, [r13+28h]
0x180008b2e  call    cs:__imp_GetProcessHeap
0x180008b34  mov     r8, rbx; lpMem
0x180008b37  xor     edx, edx; dwFlags
0x180008b39  mov     rcx, rax; hHeap
0x180008b3c  call    cs:__imp_HeapFree
0x180008b42  xor     eax, eax
0x180008b44  mov     [r13+30h], eax
0x180008b48  mov     [r13+28h], rax
0x180008b4c  call    cs:__imp_GetProcessHeap
0x180008b52  mov     r8, r12; lpMem
0x180008b55  xor     edx, edx; dwFlags
0x180008b57  mov     rcx, rax; hHeap
0x180008b5a  call    cs:__imp_HeapFree
0x180008b60  test    rsi, rsi
0x180008b63  jnz     loc_180008AD9
0x180008b69  mov     [rdi], rsi
0x180008b6c  add     rdi, 8
0x180008b70  cmp     rdi, r15
0x180008b73  jnz     loc_180008AD1
0x180008b79  add     rsp, 28h
0x180008b7d  pop     r15
0x180008b7f  pop     r14
0x180008b81  pop     r13
0x180008b83  pop     r12
0x180008b85  pop     rdi
0x180008b86  pop     rsi
0x180008b87  pop     rbp
0x180008b88  pop     rbx
0x180008b89  retn
```
