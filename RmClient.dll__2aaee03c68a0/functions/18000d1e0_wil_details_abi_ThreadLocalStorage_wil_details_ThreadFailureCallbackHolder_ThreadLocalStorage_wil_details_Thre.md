# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x18000d1e0`
- end: `0x18000d258`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d1c0`

## callees

- `0x18000d1e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d24b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d24b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d23d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d23d`

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
0x18000d1e0  mov     [rsp+arg_18], rbx
0x18000d1e5  push    rbp
0x18000d1e6  sub     rsp, 20h
0x18000d1ea  lea     rbp, [rcx+50h]
0x18000d1ee  mov     rbx, rcx
0x18000d1f1  cmp     rcx, rbp
0x18000d1f4  jz      short loc_18000D22B
0x18000d1f6  mov     [rsp+28h+arg_0], rsi
0x18000d1fb  mov     [rsp+28h+arg_8], rdi
0x18000d200  mov     [rsp+28h+arg_10], r14
0x18000d205  xor     r14d, r14d
0x18000d208  mov     rsi, [rbx]
0x18000d20b  test    rsi, rsi
0x18000d20e  jnz     short loc_18000D236
0x18000d210  mov     [rbx], r14
0x18000d213  add     rbx, 8
0x18000d217  cmp     rbx, rbp
0x18000d21a  jnz     short loc_18000D208
0x18000d21c  mov     r14, [rsp+28h+arg_10]
0x18000d221  mov     rdi, [rsp+28h+arg_8]
0x18000d226  mov     rsi, [rsp+28h+arg_0]
0x18000d22b  mov     rbx, [rsp+28h+arg_18]
0x18000d230  add     rsp, 20h
0x18000d234  pop     rbp
0x18000d235  retn
0x18000d236  mov     rdi, rsi
0x18000d239  mov     rsi, [rsi+8]
0x18000d23d  call    cs:__imp_GetProcessHeap
0x18000d243  mov     r8, rdi; lpMem
0x18000d246  xor     edx, edx; dwFlags
0x18000d248  mov     rcx, rax; hHeap
0x18000d24b  call    cs:__imp_HeapFree
0x18000d251  test    rsi, rsi
0x18000d254  jnz     short loc_18000D236
0x18000d256  jmp     short loc_18000D210
```
