# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180008588`
- end: `0x1800085d7`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014c80`

## callees

- `0x180008588`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800085b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800085b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800085a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800085a9`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(
        _QWORD *a1)
{
  _QWORD *v1; // rbp
  _QWORD *v2; // rdi
  _QWORD *v3; // rsi
  void *v4; // rbx
  HANDLE ProcessHeap; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = (_QWORD *)*v2;
    while ( v3 )
    {
      v4 = v3;
      v3 = (_QWORD *)v3[1];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x180008588  push    rbx
0x18000858a  push    rbp
0x18000858b  push    rsi
0x18000858c  push    rdi
0x18000858d  sub     rsp, 28h
0x180008591  lea     rbp, [rcx+50h]
0x180008595  mov     rdi, rcx
0x180008598  cmp     rcx, rbp
0x18000859b  jz      short loc_1800085CE
0x18000859d  mov     rsi, [rdi]
0x1800085a0  jmp     short loc_1800085BD
0x1800085a2  mov     rbx, rsi
0x1800085a5  mov     rsi, [rsi+8]
0x1800085a9  call    cs:__imp_GetProcessHeap
0x1800085af  mov     r8, rbx; lpMem
0x1800085b2  xor     edx, edx; dwFlags
0x1800085b4  mov     rcx, rax; hHeap
0x1800085b7  call    cs:__imp_HeapFree
0x1800085bd  test    rsi, rsi
0x1800085c0  jnz     short loc_1800085A2
0x1800085c2  mov     [rdi], rsi
0x1800085c5  add     rdi, 8
0x1800085c9  cmp     rdi, rbp
0x1800085cc  jnz     short loc_18000859D
0x1800085ce  add     rsp, 28h
0x1800085d2  pop     rdi
0x1800085d3  pop     rsi
0x1800085d4  pop     rbp
0x1800085d5  pop     rbx
0x1800085d6  retn
```
