# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x14000abb8`
- end: `0x14000ac07`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400077b0`

## callees

- `0x14000abb8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000abe7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000abe7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000abd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000abd9`

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
0x14000abb8  push    rbx
0x14000abba  push    rbp
0x14000abbb  push    rsi
0x14000abbc  push    rdi
0x14000abbd  sub     rsp, 28h
0x14000abc1  lea     rbp, [rcx+50h]
0x14000abc5  mov     rdi, rcx
0x14000abc8  cmp     rcx, rbp
0x14000abcb  jz      short loc_14000ABFE
0x14000abcd  mov     rsi, [rdi]
0x14000abd0  jmp     short loc_14000ABED
0x14000abd2  mov     rbx, rsi
0x14000abd5  mov     rsi, [rsi+8]
0x14000abd9  call    cs:__imp_GetProcessHeap
0x14000abdf  mov     r8, rbx; lpMem
0x14000abe2  xor     edx, edx; dwFlags
0x14000abe4  mov     rcx, rax; hHeap
0x14000abe7  call    cs:__imp_HeapFree
0x14000abed  test    rsi, rsi
0x14000abf0  jnz     short loc_14000ABD2
0x14000abf2  mov     [rdi], rsi
0x14000abf5  add     rdi, 8
0x14000abf9  cmp     rdi, rbp
0x14000abfc  jnz     short loc_14000ABCD
0x14000abfe  add     rsp, 28h
0x14000ac02  pop     rdi
0x14000ac03  pop     rsi
0x14000ac04  pop     rbp
0x14000ac05  pop     rbx
0x14000ac06  retn
```
