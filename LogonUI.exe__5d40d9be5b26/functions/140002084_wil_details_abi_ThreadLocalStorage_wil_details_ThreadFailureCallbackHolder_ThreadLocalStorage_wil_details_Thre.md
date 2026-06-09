# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x140002084`
- end: `0x1400020d3`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140007a60`

## callees

- `0x140002084`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400020a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400020a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400020b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400020b3`

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
0x140002084  push    rbx
0x140002086  push    rbp
0x140002087  push    rsi
0x140002088  push    rdi
0x140002089  sub     rsp, 28h
0x14000208d  lea     rbp, [rcx+50h]
0x140002091  mov     rdi, rcx
0x140002094  cmp     rcx, rbp
0x140002097  jz      short loc_1400020CA
0x140002099  mov     rsi, [rdi]
0x14000209c  jmp     short loc_1400020B9
0x14000209e  mov     rbx, rsi
0x1400020a1  mov     rsi, [rsi+8]
0x1400020a5  call    cs:__imp_GetProcessHeap
0x1400020ab  mov     r8, rbx; lpMem
0x1400020ae  xor     edx, edx; dwFlags
0x1400020b0  mov     rcx, rax; hHeap
0x1400020b3  call    cs:__imp_HeapFree
0x1400020b9  test    rsi, rsi
0x1400020bc  jnz     short loc_14000209E
0x1400020be  mov     [rdi], rsi
0x1400020c1  add     rdi, 8
0x1400020c5  cmp     rdi, rbp
0x1400020c8  jnz     short loc_140002099
0x1400020ca  add     rsp, 28h
0x1400020ce  pop     rdi
0x1400020cf  pop     rsi
0x1400020d0  pop     rbp
0x1400020d1  pop     rbx
0x1400020d2  retn
```
