# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180005494`
- end: `0x18000556e`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000540c`

## callees

- `0x180005494`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800054e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005512`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005530`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800054e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005512`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005530`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800054ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005520`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000553e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800054ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005520`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000553e`

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
0x180005494  push    rbx
0x180005496  push    rbp
0x180005497  push    rsi
0x180005498  push    rdi
0x180005499  push    r12
0x18000549b  push    r13
0x18000549d  push    r14
0x18000549f  push    r15
0x1800054a1  sub     rsp, 28h
0x1800054a5  lea     r15, [rcx+50h]
0x1800054a9  mov     rdi, rcx
0x1800054ac  cmp     rcx, r15
0x1800054af  jz      loc_18000555D
0x1800054b5  mov     rsi, [rdi]
0x1800054b8  jmp     loc_180005544
0x1800054bd  mov     r13, rsi
0x1800054c0  mov     r12, rsi
0x1800054c3  mov     rsi, [rsi+8]
0x1800054c7  movzx   eax, word ptr [r13+30h]
0x1800054cc  mov     rbp, [r13+28h]
0x1800054d0  lea     r14, [rax+rax*4]
0x1800054d4  shl     r14, 4
0x1800054d8  add     r14, rbp
0x1800054db  jmp     short loc_180005509
0x1800054dd  mov     rbx, [rbp+40h]
0x1800054e1  call    cs:__imp_GetProcessHeap
0x1800054e7  mov     r8, rbx; lpMem
0x1800054ea  xor     edx, edx; dwFlags
0x1800054ec  mov     rcx, rax; hHeap
0x1800054ef  call    cs:__imp_HeapFree
0x1800054f5  mov     qword ptr [rbp+40h], 0
0x1800054fd  mov     qword ptr [rbp+48h], 0
0x180005505  add     rbp, 50h ; 'P'
0x180005509  cmp     rbp, r14
0x18000550c  jnz     short loc_1800054DD
0x18000550e  mov     rbx, [r13+28h]
0x180005512  call    cs:__imp_GetProcessHeap
0x180005518  mov     r8, rbx; lpMem
0x18000551b  xor     edx, edx; dwFlags
0x18000551d  mov     rcx, rax; hHeap
0x180005520  call    cs:__imp_HeapFree
0x180005526  xor     eax, eax
0x180005528  mov     [r13+30h], eax
0x18000552c  mov     [r13+28h], rax
0x180005530  call    cs:__imp_GetProcessHeap
0x180005536  mov     r8, r12; lpMem
0x180005539  xor     edx, edx; dwFlags
0x18000553b  mov     rcx, rax; hHeap
0x18000553e  call    cs:__imp_HeapFree
0x180005544  test    rsi, rsi
0x180005547  jnz     loc_1800054BD
0x18000554d  mov     [rdi], rsi
0x180005550  add     rdi, 8
0x180005554  cmp     rdi, r15
0x180005557  jnz     loc_1800054B5
0x18000555d  add     rsp, 28h
0x180005561  pop     r15
0x180005563  pop     r14
0x180005565  pop     r13
0x180005567  pop     r12
0x180005569  pop     rdi
0x18000556a  pop     rsi
0x18000556b  pop     rbp
0x18000556c  pop     rbx
0x18000556d  retn
```
