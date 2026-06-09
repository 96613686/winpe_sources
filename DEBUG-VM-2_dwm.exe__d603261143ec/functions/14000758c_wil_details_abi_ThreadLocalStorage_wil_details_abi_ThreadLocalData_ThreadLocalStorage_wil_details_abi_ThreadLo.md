# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x14000758c`
- end: `0x140007666`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400074d4`

## callees

- `0x14000758c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400075d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000760a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007628`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400075d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000760a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007628`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400075e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007618`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007636`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400075e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007618`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007636`

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
0x14000758c  push    rbx
0x14000758e  push    rbp
0x14000758f  push    rsi
0x140007590  push    rdi
0x140007591  push    r12
0x140007593  push    r13
0x140007595  push    r14
0x140007597  push    r15
0x140007599  sub     rsp, 28h
0x14000759d  lea     r15, [rcx+50h]
0x1400075a1  mov     rdi, rcx
0x1400075a4  cmp     rcx, r15
0x1400075a7  jz      loc_140007655
0x1400075ad  mov     rsi, [rdi]
0x1400075b0  jmp     loc_14000763C
0x1400075b5  mov     r13, rsi
0x1400075b8  mov     r12, rsi
0x1400075bb  mov     rsi, [rsi+8]
0x1400075bf  movzx   eax, word ptr [r13+30h]
0x1400075c4  mov     rbp, [r13+28h]
0x1400075c8  lea     r14, [rax+rax*4]
0x1400075cc  shl     r14, 4
0x1400075d0  add     r14, rbp
0x1400075d3  jmp     short loc_140007601
0x1400075d5  mov     rbx, [rbp+40h]
0x1400075d9  call    cs:__imp_GetProcessHeap
0x1400075df  mov     r8, rbx; lpMem
0x1400075e2  xor     edx, edx; dwFlags
0x1400075e4  mov     rcx, rax; hHeap
0x1400075e7  call    cs:__imp_HeapFree
0x1400075ed  mov     qword ptr [rbp+40h], 0
0x1400075f5  mov     qword ptr [rbp+48h], 0
0x1400075fd  add     rbp, 50h ; 'P'
0x140007601  cmp     rbp, r14
0x140007604  jnz     short loc_1400075D5
0x140007606  mov     rbx, [r13+28h]
0x14000760a  call    cs:__imp_GetProcessHeap
0x140007610  mov     r8, rbx; lpMem
0x140007613  xor     edx, edx; dwFlags
0x140007615  mov     rcx, rax; hHeap
0x140007618  call    cs:__imp_HeapFree
0x14000761e  xor     eax, eax
0x140007620  mov     [r13+30h], eax
0x140007624  mov     [r13+28h], rax
0x140007628  call    cs:__imp_GetProcessHeap
0x14000762e  mov     r8, r12; lpMem
0x140007631  xor     edx, edx; dwFlags
0x140007633  mov     rcx, rax; hHeap
0x140007636  call    cs:__imp_HeapFree
0x14000763c  test    rsi, rsi
0x14000763f  jnz     loc_1400075B5
0x140007645  mov     [rdi], rsi
0x140007648  add     rdi, 8
0x14000764c  cmp     rdi, r15
0x14000764f  jnz     loc_1400075AD
0x140007655  add     rsp, 28h
0x140007659  pop     r15
0x14000765b  pop     r14
0x14000765d  pop     r13
0x14000765f  pop     r12
0x140007661  pop     rdi
0x140007662  pop     rsi
0x140007663  pop     rbp
0x140007664  pop     rbx
0x140007665  retn
```
