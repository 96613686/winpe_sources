# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180007780`
- end: `0x180007802`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011af0`

## callees

- `0x180007780`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800077e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800077e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800077f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800077f5`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(
        _QWORD *a1)
{
  _QWORD *v1; // rbp
  _QWORD *v2; // rbx
  _QWORD *v3; // rsi
  void *v4; // rdi
  HANDLE ProcessHeap; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = (_QWORD *)*v2;
    if ( *v2 )
    {
      do
      {
        v4 = v3;
        v3 = (_QWORD *)v3[1];
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v4);
      }
      while ( v3 );
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x180007780  mov     [rsp+arg_18], rbx
0x180007785  push    rbp
0x180007786  sub     rsp, 20h
0x18000778a  lea     rbp, [rcx+50h]
0x18000778e  mov     rbx, rcx
0x180007791  cmp     rcx, rbp
0x180007794  jz      short loc_1800077CB
0x180007796  mov     [rsp+28h+arg_0], rsi
0x18000779b  mov     [rsp+28h+arg_8], rdi
0x1800077a0  mov     [rsp+28h+arg_10], r14
0x1800077a5  xor     r14d, r14d
0x1800077a8  mov     rsi, [rbx]
0x1800077ab  test    rsi, rsi
0x1800077ae  jnz     short loc_1800077E0
0x1800077b0  mov     [rbx], r14
0x1800077b3  add     rbx, 8
0x1800077b7  cmp     rbx, rbp
0x1800077ba  jnz     short loc_1800077A8
0x1800077bc  mov     r14, [rsp+28h+arg_10]
0x1800077c1  mov     rdi, [rsp+28h+arg_8]
0x1800077c6  mov     rsi, [rsp+28h+arg_0]
0x1800077cb  mov     rbx, [rsp+28h+arg_18]
0x1800077d0  add     rsp, 20h
0x1800077d4  pop     rbp
0x1800077d5  retn
0x1800077e0  mov     rdi, rsi
0x1800077e3  mov     rsi, [rsi+8]
0x1800077e7  call    cs:__imp_GetProcessHeap
0x1800077ed  mov     r8, rdi; lpMem
0x1800077f0  xor     edx, edx; dwFlags
0x1800077f2  mov     rcx, rax; hHeap
0x1800077f5  call    cs:__imp_HeapFree
0x1800077fb  test    rsi, rsi
0x1800077fe  jz      short loc_1800077B0
0x180007800  jmp     short loc_1800077E0
```
