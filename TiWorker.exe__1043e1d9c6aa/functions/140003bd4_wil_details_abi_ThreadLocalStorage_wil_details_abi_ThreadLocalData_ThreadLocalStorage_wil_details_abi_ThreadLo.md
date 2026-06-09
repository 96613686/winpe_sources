# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x140003bd4`
- end: `0x140003cae`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140003b4c`

## callees

- `0x140003bd4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c70`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c7e`

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
0x140003bd4  push    rbx
0x140003bd6  push    rbp
0x140003bd7  push    rsi
0x140003bd8  push    rdi
0x140003bd9  push    r12
0x140003bdb  push    r13
0x140003bdd  push    r14
0x140003bdf  push    r15
0x140003be1  sub     rsp, 28h
0x140003be5  lea     r15, [rcx+50h]
0x140003be9  mov     rdi, rcx
0x140003bec  cmp     rcx, r15
0x140003bef  jz      loc_140003C9D
0x140003bf5  mov     rsi, [rdi]
0x140003bf8  jmp     loc_140003C84
0x140003bfd  mov     r13, rsi
0x140003c00  mov     r12, rsi
0x140003c03  mov     rsi, [rsi+8]
0x140003c07  movzx   eax, word ptr [r13+30h]
0x140003c0c  mov     rbp, [r13+28h]
0x140003c10  lea     r14, [rax+rax*4]
0x140003c14  shl     r14, 4
0x140003c18  add     r14, rbp
0x140003c1b  jmp     short loc_140003C49
0x140003c1d  mov     rbx, [rbp+40h]
0x140003c21  call    cs:__imp_GetProcessHeap
0x140003c27  mov     r8, rbx; lpMem
0x140003c2a  xor     edx, edx; dwFlags
0x140003c2c  mov     rcx, rax; hHeap
0x140003c2f  call    cs:__imp_HeapFree
0x140003c35  mov     qword ptr [rbp+40h], 0
0x140003c3d  mov     qword ptr [rbp+48h], 0
0x140003c45  add     rbp, 50h ; 'P'
0x140003c49  cmp     rbp, r14
0x140003c4c  jnz     short loc_140003C1D
0x140003c4e  mov     rbx, [r13+28h]
0x140003c52  call    cs:__imp_GetProcessHeap
0x140003c58  mov     r8, rbx; lpMem
0x140003c5b  xor     edx, edx; dwFlags
0x140003c5d  mov     rcx, rax; hHeap
0x140003c60  call    cs:__imp_HeapFree
0x140003c66  xor     eax, eax
0x140003c68  mov     [r13+30h], eax
0x140003c6c  mov     [r13+28h], rax
0x140003c70  call    cs:__imp_GetProcessHeap
0x140003c76  mov     r8, r12; lpMem
0x140003c79  xor     edx, edx; dwFlags
0x140003c7b  mov     rcx, rax; hHeap
0x140003c7e  call    cs:__imp_HeapFree
0x140003c84  test    rsi, rsi
0x140003c87  jnz     loc_140003BFD
0x140003c8d  mov     [rdi], rsi
0x140003c90  add     rdi, 8
0x140003c94  cmp     rdi, r15
0x140003c97  jnz     loc_140003BF5
0x140003c9d  add     rsp, 28h
0x140003ca1  pop     r15
0x140003ca3  pop     r14
0x140003ca5  pop     r13
0x140003ca7  pop     r12
0x140003ca9  pop     rdi
0x140003caa  pop     rsi
0x140003cab  pop     rbp
0x140003cac  pop     rbx
0x140003cad  retn
```
