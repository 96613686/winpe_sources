# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x140005af4`
- end: `0x140005bce`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140005a3c`

## callees

- `0x140005af4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005b41`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005b72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005b90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005b41`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005b72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005b90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005b4f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005b80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005b9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005b4f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005b80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005b9e`

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
0x140005af4  push    rbx
0x140005af6  push    rbp
0x140005af7  push    rsi
0x140005af8  push    rdi
0x140005af9  push    r12
0x140005afb  push    r13
0x140005afd  push    r14
0x140005aff  push    r15
0x140005b01  sub     rsp, 28h
0x140005b05  lea     r15, [rcx+50h]
0x140005b09  mov     rdi, rcx
0x140005b0c  cmp     rcx, r15
0x140005b0f  jz      loc_140005BBD
0x140005b15  mov     rsi, [rdi]
0x140005b18  jmp     loc_140005BA4
0x140005b1d  mov     r13, rsi
0x140005b20  mov     r12, rsi
0x140005b23  mov     rsi, [rsi+8]
0x140005b27  movzx   eax, word ptr [r13+30h]
0x140005b2c  mov     rbp, [r13+28h]
0x140005b30  lea     r14, [rax+rax*4]
0x140005b34  shl     r14, 4
0x140005b38  add     r14, rbp
0x140005b3b  jmp     short loc_140005B69
0x140005b3d  mov     rbx, [rbp+40h]
0x140005b41  call    cs:__imp_GetProcessHeap
0x140005b47  mov     r8, rbx; lpMem
0x140005b4a  xor     edx, edx; dwFlags
0x140005b4c  mov     rcx, rax; hHeap
0x140005b4f  call    cs:__imp_HeapFree
0x140005b55  mov     qword ptr [rbp+40h], 0
0x140005b5d  mov     qword ptr [rbp+48h], 0
0x140005b65  add     rbp, 50h ; 'P'
0x140005b69  cmp     rbp, r14
0x140005b6c  jnz     short loc_140005B3D
0x140005b6e  mov     rbx, [r13+28h]
0x140005b72  call    cs:__imp_GetProcessHeap
0x140005b78  mov     r8, rbx; lpMem
0x140005b7b  xor     edx, edx; dwFlags
0x140005b7d  mov     rcx, rax; hHeap
0x140005b80  call    cs:__imp_HeapFree
0x140005b86  xor     eax, eax
0x140005b88  mov     [r13+30h], eax
0x140005b8c  mov     [r13+28h], rax
0x140005b90  call    cs:__imp_GetProcessHeap
0x140005b96  mov     r8, r12; lpMem
0x140005b99  xor     edx, edx; dwFlags
0x140005b9b  mov     rcx, rax; hHeap
0x140005b9e  call    cs:__imp_HeapFree
0x140005ba4  test    rsi, rsi
0x140005ba7  jnz     loc_140005B1D
0x140005bad  mov     [rdi], rsi
0x140005bb0  add     rdi, 8
0x140005bb4  cmp     rdi, r15
0x140005bb7  jnz     loc_140005B15
0x140005bbd  add     rsp, 28h
0x140005bc1  pop     r15
0x140005bc3  pop     r14
0x140005bc5  pop     r13
0x140005bc7  pop     r12
0x140005bc9  pop     rdi
0x140005bca  pop     rsi
0x140005bcb  pop     rbp
0x140005bcc  pop     rbx
0x140005bcd  retn
```
