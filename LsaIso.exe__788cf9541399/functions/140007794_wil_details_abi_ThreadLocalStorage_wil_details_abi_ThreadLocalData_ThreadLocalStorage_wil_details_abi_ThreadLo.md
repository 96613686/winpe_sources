# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x140007794`
- end: `0x14000786e`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140007734`

## callees

- `0x140007794`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400077ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007820`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000783e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400077ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007820`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000783e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400077e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007812`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007830`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400077e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007812`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007830`

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
0x140007794  push    rbx
0x140007796  push    rbp
0x140007797  push    rsi
0x140007798  push    rdi
0x140007799  push    r12
0x14000779b  push    r13
0x14000779d  push    r14
0x14000779f  push    r15
0x1400077a1  sub     rsp, 28h
0x1400077a5  lea     r15, [rcx+50h]
0x1400077a9  mov     rdi, rcx
0x1400077ac  cmp     rcx, r15
0x1400077af  jz      loc_14000785D
0x1400077b5  mov     rsi, [rdi]
0x1400077b8  jmp     loc_140007844
0x1400077bd  mov     r13, rsi
0x1400077c0  mov     r12, rsi
0x1400077c3  mov     rsi, [rsi+8]
0x1400077c7  movzx   eax, word ptr [r13+30h]
0x1400077cc  mov     rbp, [r13+28h]
0x1400077d0  lea     r14, [rax+rax*4]
0x1400077d4  shl     r14, 4
0x1400077d8  add     r14, rbp
0x1400077db  jmp     short loc_140007809
0x1400077dd  mov     rbx, [rbp+40h]
0x1400077e1  call    cs:__imp_GetProcessHeap
0x1400077e7  mov     r8, rbx; lpMem
0x1400077ea  xor     edx, edx; dwFlags
0x1400077ec  mov     rcx, rax; hHeap
0x1400077ef  call    cs:__imp_HeapFree
0x1400077f5  mov     qword ptr [rbp+40h], 0
0x1400077fd  mov     qword ptr [rbp+48h], 0
0x140007805  add     rbp, 50h ; 'P'
0x140007809  cmp     rbp, r14
0x14000780c  jnz     short loc_1400077DD
0x14000780e  mov     rbx, [r13+28h]
0x140007812  call    cs:__imp_GetProcessHeap
0x140007818  mov     r8, rbx; lpMem
0x14000781b  xor     edx, edx; dwFlags
0x14000781d  mov     rcx, rax; hHeap
0x140007820  call    cs:__imp_HeapFree
0x140007826  xor     eax, eax
0x140007828  mov     [r13+30h], eax
0x14000782c  mov     [r13+28h], rax
0x140007830  call    cs:__imp_GetProcessHeap
0x140007836  mov     r8, r12; lpMem
0x140007839  xor     edx, edx; dwFlags
0x14000783b  mov     rcx, rax; hHeap
0x14000783e  call    cs:__imp_HeapFree
0x140007844  test    rsi, rsi
0x140007847  jnz     loc_1400077BD
0x14000784d  mov     [rdi], rsi
0x140007850  add     rdi, 8
0x140007854  cmp     rdi, r15
0x140007857  jnz     loc_1400077B5
0x14000785d  add     rsp, 28h
0x140007861  pop     r15
0x140007863  pop     r14
0x140007865  pop     r13
0x140007867  pop     r12
0x140007869  pop     rdi
0x14000786a  pop     rsi
0x14000786b  pop     rbp
0x14000786c  pop     rbx
0x14000786d  retn
```
