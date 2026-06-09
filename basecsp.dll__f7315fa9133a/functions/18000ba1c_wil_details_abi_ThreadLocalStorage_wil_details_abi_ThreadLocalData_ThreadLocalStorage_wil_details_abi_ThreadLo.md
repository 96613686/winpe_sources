# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x18000ba1c`
- end: `0x18000baf6`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b964`

## callees

- `0x18000ba1c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ba77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000baa8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bac6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ba77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000baa8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bac6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bab8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bab8`

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
0x18000ba1c  push    rbx
0x18000ba1e  push    rbp
0x18000ba1f  push    rsi
0x18000ba20  push    rdi
0x18000ba21  push    r12
0x18000ba23  push    r13
0x18000ba25  push    r14
0x18000ba27  push    r15
0x18000ba29  sub     rsp, 28h
0x18000ba2d  lea     r15, [rcx+50h]
0x18000ba31  mov     rdi, rcx
0x18000ba34  cmp     rcx, r15
0x18000ba37  jz      loc_18000BAE5
0x18000ba3d  mov     rsi, [rdi]
0x18000ba40  jmp     loc_18000BACC
0x18000ba45  mov     r13, rsi
0x18000ba48  mov     r12, rsi
0x18000ba4b  mov     rsi, [rsi+8]
0x18000ba4f  movzx   eax, word ptr [r13+30h]
0x18000ba54  mov     rbp, [r13+28h]
0x18000ba58  lea     r14, [rax+rax*4]
0x18000ba5c  shl     r14, 4
0x18000ba60  add     r14, rbp
0x18000ba63  jmp     short loc_18000BA91
0x18000ba65  mov     rbx, [rbp+40h]
0x18000ba69  call    cs:__imp_GetProcessHeap
0x18000ba6f  mov     r8, rbx; lpMem
0x18000ba72  xor     edx, edx; dwFlags
0x18000ba74  mov     rcx, rax; hHeap
0x18000ba77  call    cs:__imp_HeapFree
0x18000ba7d  mov     qword ptr [rbp+40h], 0
0x18000ba85  mov     qword ptr [rbp+48h], 0
0x18000ba8d  add     rbp, 50h ; 'P'
0x18000ba91  cmp     rbp, r14
0x18000ba94  jnz     short loc_18000BA65
0x18000ba96  mov     rbx, [r13+28h]
0x18000ba9a  call    cs:__imp_GetProcessHeap
0x18000baa0  mov     r8, rbx; lpMem
0x18000baa3  xor     edx, edx; dwFlags
0x18000baa5  mov     rcx, rax; hHeap
0x18000baa8  call    cs:__imp_HeapFree
0x18000baae  xor     eax, eax
0x18000bab0  mov     [r13+30h], eax
0x18000bab4  mov     [r13+28h], rax
0x18000bab8  call    cs:__imp_GetProcessHeap
0x18000babe  mov     r8, r12; lpMem
0x18000bac1  xor     edx, edx; dwFlags
0x18000bac3  mov     rcx, rax; hHeap
0x18000bac6  call    cs:__imp_HeapFree
0x18000bacc  test    rsi, rsi
0x18000bacf  jnz     loc_18000BA45
0x18000bad5  mov     [rdi], rsi
0x18000bad8  add     rdi, 8
0x18000badc  cmp     rdi, r15
0x18000badf  jnz     loc_18000BA3D
0x18000bae5  add     rsp, 28h
0x18000bae9  pop     r15
0x18000baeb  pop     r14
0x18000baed  pop     r13
0x18000baef  pop     r12
0x18000baf1  pop     rdi
0x18000baf2  pop     rsi
0x18000baf3  pop     rbp
0x18000baf4  pop     rbx
0x18000baf5  retn
```
