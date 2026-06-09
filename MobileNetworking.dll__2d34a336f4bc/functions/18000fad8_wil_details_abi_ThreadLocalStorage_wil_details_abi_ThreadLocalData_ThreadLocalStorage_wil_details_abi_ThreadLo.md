# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x18000fad8`
- end: `0x18000fbb2`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000faa8`

## callees

- `0x18000fad8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fb25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fb56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fb74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fb25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fb56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fb74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fb33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fb64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fb82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fb33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fb64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fb82`

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
0x18000fad8  push    rbx
0x18000fada  push    rbp
0x18000fadb  push    rsi
0x18000fadc  push    rdi
0x18000fadd  push    r12
0x18000fadf  push    r13
0x18000fae1  push    r14
0x18000fae3  push    r15
0x18000fae5  sub     rsp, 28h
0x18000fae9  lea     r15, [rcx+50h]
0x18000faed  mov     rdi, rcx
0x18000faf0  cmp     rcx, r15
0x18000faf3  jz      loc_18000FBA1
0x18000faf9  mov     rsi, [rdi]
0x18000fafc  jmp     loc_18000FB88
0x18000fb01  mov     r13, rsi
0x18000fb04  mov     r12, rsi
0x18000fb07  mov     rsi, [rsi+8]
0x18000fb0b  movzx   eax, word ptr [r13+30h]
0x18000fb10  mov     rbp, [r13+28h]
0x18000fb14  lea     r14, [rax+rax*4]
0x18000fb18  shl     r14, 4
0x18000fb1c  add     r14, rbp
0x18000fb1f  jmp     short loc_18000FB4D
0x18000fb21  mov     rbx, [rbp+40h]
0x18000fb25  call    cs:__imp_GetProcessHeap
0x18000fb2b  mov     r8, rbx; lpMem
0x18000fb2e  xor     edx, edx; dwFlags
0x18000fb30  mov     rcx, rax; hHeap
0x18000fb33  call    cs:__imp_HeapFree
0x18000fb39  mov     qword ptr [rbp+40h], 0
0x18000fb41  mov     qword ptr [rbp+48h], 0
0x18000fb49  add     rbp, 50h ; 'P'
0x18000fb4d  cmp     rbp, r14
0x18000fb50  jnz     short loc_18000FB21
0x18000fb52  mov     rbx, [r13+28h]
0x18000fb56  call    cs:__imp_GetProcessHeap
0x18000fb5c  mov     r8, rbx; lpMem
0x18000fb5f  xor     edx, edx; dwFlags
0x18000fb61  mov     rcx, rax; hHeap
0x18000fb64  call    cs:__imp_HeapFree
0x18000fb6a  xor     eax, eax
0x18000fb6c  mov     [r13+30h], eax
0x18000fb70  mov     [r13+28h], rax
0x18000fb74  call    cs:__imp_GetProcessHeap
0x18000fb7a  mov     r8, r12; lpMem
0x18000fb7d  xor     edx, edx; dwFlags
0x18000fb7f  mov     rcx, rax; hHeap
0x18000fb82  call    cs:__imp_HeapFree
0x18000fb88  test    rsi, rsi
0x18000fb8b  jnz     loc_18000FB01
0x18000fb91  mov     [rdi], rsi
0x18000fb94  add     rdi, 8
0x18000fb98  cmp     rdi, r15
0x18000fb9b  jnz     loc_18000FAF9
0x18000fba1  add     rsp, 28h
0x18000fba5  pop     r15
0x18000fba7  pop     r14
0x18000fba9  pop     r13
0x18000fbab  pop     r12
0x18000fbad  pop     rdi
0x18000fbae  pop     rsi
0x18000fbaf  pop     rbp
0x18000fbb0  pop     rbx
0x18000fbb1  retn
```
