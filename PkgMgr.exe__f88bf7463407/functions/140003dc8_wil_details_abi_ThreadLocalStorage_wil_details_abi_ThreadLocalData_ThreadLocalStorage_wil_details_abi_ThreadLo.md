# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x140003dc8`
- end: `0x140003ea2`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140003d40`

## callees

- `0x140003dc8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003e15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003e46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003e64`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003e15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003e46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003e64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003e23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003e54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003e72`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003e23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003e54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003e72`

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
0x140003dc8  push    rbx
0x140003dca  push    rbp
0x140003dcb  push    rsi
0x140003dcc  push    rdi
0x140003dcd  push    r12
0x140003dcf  push    r13
0x140003dd1  push    r14
0x140003dd3  push    r15
0x140003dd5  sub     rsp, 28h
0x140003dd9  lea     r15, [rcx+50h]
0x140003ddd  mov     rdi, rcx
0x140003de0  cmp     rcx, r15
0x140003de3  jz      loc_140003E91
0x140003de9  mov     rsi, [rdi]
0x140003dec  jmp     loc_140003E78
0x140003df1  mov     r13, rsi
0x140003df4  mov     r12, rsi
0x140003df7  mov     rsi, [rsi+8]
0x140003dfb  movzx   eax, word ptr [r13+30h]
0x140003e00  mov     rbp, [r13+28h]
0x140003e04  lea     r14, [rax+rax*4]
0x140003e08  shl     r14, 4
0x140003e0c  add     r14, rbp
0x140003e0f  jmp     short loc_140003E3D
0x140003e11  mov     rbx, [rbp+40h]
0x140003e15  call    cs:__imp_GetProcessHeap
0x140003e1b  mov     r8, rbx; lpMem
0x140003e1e  xor     edx, edx; dwFlags
0x140003e20  mov     rcx, rax; hHeap
0x140003e23  call    cs:__imp_HeapFree
0x140003e29  mov     qword ptr [rbp+40h], 0
0x140003e31  mov     qword ptr [rbp+48h], 0
0x140003e39  add     rbp, 50h ; 'P'
0x140003e3d  cmp     rbp, r14
0x140003e40  jnz     short loc_140003E11
0x140003e42  mov     rbx, [r13+28h]
0x140003e46  call    cs:__imp_GetProcessHeap
0x140003e4c  mov     r8, rbx; lpMem
0x140003e4f  xor     edx, edx; dwFlags
0x140003e51  mov     rcx, rax; hHeap
0x140003e54  call    cs:__imp_HeapFree
0x140003e5a  xor     eax, eax
0x140003e5c  mov     [r13+30h], eax
0x140003e60  mov     [r13+28h], rax
0x140003e64  call    cs:__imp_GetProcessHeap
0x140003e6a  mov     r8, r12; lpMem
0x140003e6d  xor     edx, edx; dwFlags
0x140003e6f  mov     rcx, rax; hHeap
0x140003e72  call    cs:__imp_HeapFree
0x140003e78  test    rsi, rsi
0x140003e7b  jnz     loc_140003DF1
0x140003e81  mov     [rdi], rsi
0x140003e84  add     rdi, 8
0x140003e88  cmp     rdi, r15
0x140003e8b  jnz     loc_140003DE9
0x140003e91  add     rsp, 28h
0x140003e95  pop     r15
0x140003e97  pop     r14
0x140003e99  pop     r13
0x140003e9b  pop     r12
0x140003e9d  pop     rdi
0x140003e9e  pop     rsi
0x140003e9f  pop     rbp
0x140003ea0  pop     rbx
0x140003ea1  retn
```
