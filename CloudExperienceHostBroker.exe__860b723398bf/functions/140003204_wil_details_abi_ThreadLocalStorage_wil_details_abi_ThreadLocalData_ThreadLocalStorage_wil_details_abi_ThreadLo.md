# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x140003204`
- end: `0x1400032de`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000317c`

## callees

- `0x140003204`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003251`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003282`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400032a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003251`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003282`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400032a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000325f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003290`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400032ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000325f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003290`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400032ae`

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
0x140003204  push    rbx
0x140003206  push    rbp
0x140003207  push    rsi
0x140003208  push    rdi
0x140003209  push    r12
0x14000320b  push    r13
0x14000320d  push    r14
0x14000320f  push    r15
0x140003211  sub     rsp, 28h
0x140003215  lea     r15, [rcx+50h]
0x140003219  mov     rdi, rcx
0x14000321c  cmp     rcx, r15
0x14000321f  jz      loc_1400032CD
0x140003225  mov     rsi, [rdi]
0x140003228  jmp     loc_1400032B4
0x14000322d  mov     r13, rsi
0x140003230  mov     r12, rsi
0x140003233  mov     rsi, [rsi+8]
0x140003237  movzx   eax, word ptr [r13+30h]
0x14000323c  mov     rbp, [r13+28h]
0x140003240  lea     r14, [rax+rax*4]
0x140003244  shl     r14, 4
0x140003248  add     r14, rbp
0x14000324b  jmp     short loc_140003279
0x14000324d  mov     rbx, [rbp+40h]
0x140003251  call    cs:__imp_GetProcessHeap
0x140003257  mov     r8, rbx; lpMem
0x14000325a  xor     edx, edx; dwFlags
0x14000325c  mov     rcx, rax; hHeap
0x14000325f  call    cs:__imp_HeapFree
0x140003265  mov     qword ptr [rbp+40h], 0
0x14000326d  mov     qword ptr [rbp+48h], 0
0x140003275  add     rbp, 50h ; 'P'
0x140003279  cmp     rbp, r14
0x14000327c  jnz     short loc_14000324D
0x14000327e  mov     rbx, [r13+28h]
0x140003282  call    cs:__imp_GetProcessHeap
0x140003288  mov     r8, rbx; lpMem
0x14000328b  xor     edx, edx; dwFlags
0x14000328d  mov     rcx, rax; hHeap
0x140003290  call    cs:__imp_HeapFree
0x140003296  xor     eax, eax
0x140003298  mov     [r13+30h], eax
0x14000329c  mov     [r13+28h], rax
0x1400032a0  call    cs:__imp_GetProcessHeap
0x1400032a6  mov     r8, r12; lpMem
0x1400032a9  xor     edx, edx; dwFlags
0x1400032ab  mov     rcx, rax; hHeap
0x1400032ae  call    cs:__imp_HeapFree
0x1400032b4  test    rsi, rsi
0x1400032b7  jnz     loc_14000322D
0x1400032bd  mov     [rdi], rsi
0x1400032c0  add     rdi, 8
0x1400032c4  cmp     rdi, r15
0x1400032c7  jnz     loc_140003225
0x1400032cd  add     rsp, 28h
0x1400032d1  pop     r15
0x1400032d3  pop     r14
0x1400032d5  pop     r13
0x1400032d7  pop     r12
0x1400032d9  pop     rdi
0x1400032da  pop     rsi
0x1400032db  pop     rbp
0x1400032dc  pop     rbx
0x1400032dd  retn
```
