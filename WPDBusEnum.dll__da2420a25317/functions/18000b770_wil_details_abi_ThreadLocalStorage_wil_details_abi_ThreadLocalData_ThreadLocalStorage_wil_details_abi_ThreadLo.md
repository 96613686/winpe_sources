# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x18000b770`
- end: `0x18000b84a`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b740`

## callees

- `0x18000b770`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b7cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b7fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b81a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b7cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b7fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b81a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b7bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b7ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b80c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b7bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b7ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b80c`

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
0x18000b770  push    rbx
0x18000b772  push    rbp
0x18000b773  push    rsi
0x18000b774  push    rdi
0x18000b775  push    r12
0x18000b777  push    r13
0x18000b779  push    r14
0x18000b77b  push    r15
0x18000b77d  sub     rsp, 28h
0x18000b781  lea     r15, [rcx+50h]
0x18000b785  mov     rdi, rcx
0x18000b788  cmp     rcx, r15
0x18000b78b  jz      loc_18000B839
0x18000b791  mov     rsi, [rdi]
0x18000b794  jmp     loc_18000B820
0x18000b799  mov     r13, rsi
0x18000b79c  mov     r12, rsi
0x18000b79f  mov     rsi, [rsi+8]
0x18000b7a3  movzx   eax, word ptr [r13+30h]
0x18000b7a8  mov     rbp, [r13+28h]
0x18000b7ac  lea     r14, [rax+rax*4]
0x18000b7b0  shl     r14, 4
0x18000b7b4  add     r14, rbp
0x18000b7b7  jmp     short loc_18000B7E5
0x18000b7b9  mov     rbx, [rbp+40h]
0x18000b7bd  call    cs:__imp_GetProcessHeap
0x18000b7c3  mov     r8, rbx; lpMem
0x18000b7c6  xor     edx, edx; dwFlags
0x18000b7c8  mov     rcx, rax; hHeap
0x18000b7cb  call    cs:__imp_HeapFree
0x18000b7d1  mov     qword ptr [rbp+40h], 0
0x18000b7d9  mov     qword ptr [rbp+48h], 0
0x18000b7e1  add     rbp, 50h ; 'P'
0x18000b7e5  cmp     rbp, r14
0x18000b7e8  jnz     short loc_18000B7B9
0x18000b7ea  mov     rbx, [r13+28h]
0x18000b7ee  call    cs:__imp_GetProcessHeap
0x18000b7f4  mov     r8, rbx; lpMem
0x18000b7f7  xor     edx, edx; dwFlags
0x18000b7f9  mov     rcx, rax; hHeap
0x18000b7fc  call    cs:__imp_HeapFree
0x18000b802  xor     eax, eax
0x18000b804  mov     [r13+30h], eax
0x18000b808  mov     [r13+28h], rax
0x18000b80c  call    cs:__imp_GetProcessHeap
0x18000b812  mov     r8, r12; lpMem
0x18000b815  xor     edx, edx; dwFlags
0x18000b817  mov     rcx, rax; hHeap
0x18000b81a  call    cs:__imp_HeapFree
0x18000b820  test    rsi, rsi
0x18000b823  jnz     loc_18000B799
0x18000b829  mov     [rdi], rsi
0x18000b82c  add     rdi, 8
0x18000b830  cmp     rdi, r15
0x18000b833  jnz     loc_18000B791
0x18000b839  add     rsp, 28h
0x18000b83d  pop     r15
0x18000b83f  pop     r14
0x18000b841  pop     r13
0x18000b843  pop     r12
0x18000b845  pop     rdi
0x18000b846  pop     rsi
0x18000b847  pop     rbp
0x18000b848  pop     rbx
0x18000b849  retn
```
