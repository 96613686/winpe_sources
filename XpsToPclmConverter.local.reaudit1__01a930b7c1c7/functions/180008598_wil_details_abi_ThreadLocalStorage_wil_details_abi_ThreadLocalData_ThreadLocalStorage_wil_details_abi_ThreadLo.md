# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180008598`
- end: `0x180008672`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800084e0`

## callees

- `0x180008598`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800085f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008624`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008642`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800085f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008624`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008642`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800085e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008616`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008634`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800085e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008616`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008634`

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
0x180008598  push    rbx
0x18000859a  push    rbp
0x18000859b  push    rsi
0x18000859c  push    rdi
0x18000859d  push    r12
0x18000859f  push    r13
0x1800085a1  push    r14
0x1800085a3  push    r15
0x1800085a5  sub     rsp, 28h
0x1800085a9  lea     r15, [rcx+50h]
0x1800085ad  mov     rdi, rcx
0x1800085b0  cmp     rcx, r15
0x1800085b3  jz      loc_180008661
0x1800085b9  mov     rsi, [rdi]
0x1800085bc  jmp     loc_180008648
0x1800085c1  mov     r13, rsi
0x1800085c4  mov     r12, rsi
0x1800085c7  mov     rsi, [rsi+8]
0x1800085cb  movzx   eax, word ptr [r13+30h]
0x1800085d0  mov     rbp, [r13+28h]
0x1800085d4  lea     r14, [rax+rax*4]
0x1800085d8  shl     r14, 4
0x1800085dc  add     r14, rbp
0x1800085df  jmp     short loc_18000860D
0x1800085e1  mov     rbx, [rbp+40h]
0x1800085e5  call    cs:__imp_GetProcessHeap
0x1800085eb  mov     r8, rbx; lpMem
0x1800085ee  xor     edx, edx; dwFlags
0x1800085f0  mov     rcx, rax; hHeap
0x1800085f3  call    cs:__imp_HeapFree
0x1800085f9  mov     qword ptr [rbp+40h], 0
0x180008601  mov     qword ptr [rbp+48h], 0
0x180008609  add     rbp, 50h ; 'P'
0x18000860d  cmp     rbp, r14
0x180008610  jnz     short loc_1800085E1
0x180008612  mov     rbx, [r13+28h]
0x180008616  call    cs:__imp_GetProcessHeap
0x18000861c  mov     r8, rbx; lpMem
0x18000861f  xor     edx, edx; dwFlags
0x180008621  mov     rcx, rax; hHeap
0x180008624  call    cs:__imp_HeapFree
0x18000862a  xor     eax, eax
0x18000862c  mov     [r13+30h], eax
0x180008630  mov     [r13+28h], rax
0x180008634  call    cs:__imp_GetProcessHeap
0x18000863a  mov     r8, r12; lpMem
0x18000863d  xor     edx, edx; dwFlags
0x18000863f  mov     rcx, rax; hHeap
0x180008642  call    cs:__imp_HeapFree
0x180008648  test    rsi, rsi
0x18000864b  jnz     loc_1800085C1
0x180008651  mov     [rdi], rsi
0x180008654  add     rdi, 8
0x180008658  cmp     rdi, r15
0x18000865b  jnz     loc_1800085B9
0x180008661  add     rsp, 28h
0x180008665  pop     r15
0x180008667  pop     r14
0x180008669  pop     r13
0x18000866b  pop     r12
0x18000866d  pop     rdi
0x18000866e  pop     rsi
0x18000866f  pop     rbp
0x180008670  pop     rbx
0x180008671  retn
```
