# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180009464`
- end: `0x18000953e`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009434`

## callees

- `0x180009464`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800094b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800094e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009500`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800094b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800094e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009500`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800094bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800094f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000950e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800094bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800094f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000950e`

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
0x180009464  push    rbx
0x180009466  push    rbp
0x180009467  push    rsi
0x180009468  push    rdi
0x180009469  push    r12
0x18000946b  push    r13
0x18000946d  push    r14
0x18000946f  push    r15
0x180009471  sub     rsp, 28h
0x180009475  lea     r15, [rcx+50h]
0x180009479  mov     rdi, rcx
0x18000947c  cmp     rcx, r15
0x18000947f  jz      loc_18000952D
0x180009485  mov     rsi, [rdi]
0x180009488  jmp     loc_180009514
0x18000948d  mov     r13, rsi
0x180009490  mov     r12, rsi
0x180009493  mov     rsi, [rsi+8]
0x180009497  movzx   eax, word ptr [r13+30h]
0x18000949c  mov     rbp, [r13+28h]
0x1800094a0  lea     r14, [rax+rax*4]
0x1800094a4  shl     r14, 4
0x1800094a8  add     r14, rbp
0x1800094ab  jmp     short loc_1800094D9
0x1800094ad  mov     rbx, [rbp+40h]
0x1800094b1  call    cs:__imp_GetProcessHeap
0x1800094b7  mov     r8, rbx; lpMem
0x1800094ba  xor     edx, edx; dwFlags
0x1800094bc  mov     rcx, rax; hHeap
0x1800094bf  call    cs:__imp_HeapFree
0x1800094c5  mov     qword ptr [rbp+40h], 0
0x1800094cd  mov     qword ptr [rbp+48h], 0
0x1800094d5  add     rbp, 50h ; 'P'
0x1800094d9  cmp     rbp, r14
0x1800094dc  jnz     short loc_1800094AD
0x1800094de  mov     rbx, [r13+28h]
0x1800094e2  call    cs:__imp_GetProcessHeap
0x1800094e8  mov     r8, rbx; lpMem
0x1800094eb  xor     edx, edx; dwFlags
0x1800094ed  mov     rcx, rax; hHeap
0x1800094f0  call    cs:__imp_HeapFree
0x1800094f6  xor     eax, eax
0x1800094f8  mov     [r13+30h], eax
0x1800094fc  mov     [r13+28h], rax
0x180009500  call    cs:__imp_GetProcessHeap
0x180009506  mov     r8, r12; lpMem
0x180009509  xor     edx, edx; dwFlags
0x18000950b  mov     rcx, rax; hHeap
0x18000950e  call    cs:__imp_HeapFree
0x180009514  test    rsi, rsi
0x180009517  jnz     loc_18000948D
0x18000951d  mov     [rdi], rsi
0x180009520  add     rdi, 8
0x180009524  cmp     rdi, r15
0x180009527  jnz     loc_180009485
0x18000952d  add     rsp, 28h
0x180009531  pop     r15
0x180009533  pop     r14
0x180009535  pop     r13
0x180009537  pop     r12
0x180009539  pop     rdi
0x18000953a  pop     rsi
0x18000953b  pop     rbp
0x18000953c  pop     rbx
0x18000953d  retn
```
