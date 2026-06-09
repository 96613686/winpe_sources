# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x18000acb4`
- end: `0x18000ad03`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007320`

## callees

- `0x18000acb4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000acd5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000acd5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ace3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ace3`

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
0x18000acb4  push    rbx
0x18000acb6  push    rbp
0x18000acb7  push    rsi
0x18000acb8  push    rdi
0x18000acb9  sub     rsp, 28h
0x18000acbd  lea     rbp, [rcx+50h]
0x18000acc1  mov     rdi, rcx
0x18000acc4  cmp     rcx, rbp
0x18000acc7  jz      short loc_18000ACFA
0x18000acc9  mov     rsi, [rdi]
0x18000accc  jmp     short loc_18000ACE9
0x18000acce  mov     rbx, rsi
0x18000acd1  mov     rsi, [rsi+8]
0x18000acd5  call    cs:__imp_GetProcessHeap
0x18000acdb  mov     r8, rbx; lpMem
0x18000acde  xor     edx, edx; dwFlags
0x18000ace0  mov     rcx, rax; hHeap
0x18000ace3  call    cs:__imp_HeapFree
0x18000ace9  test    rsi, rsi
0x18000acec  jnz     short loc_18000ACCE
0x18000acee  mov     [rdi], rsi
0x18000acf1  add     rdi, 8
0x18000acf5  cmp     rdi, rbp
0x18000acf8  jnz     short loc_18000ACC9
0x18000acfa  add     rsp, 28h
0x18000acfe  pop     rdi
0x18000acff  pop     rsi
0x18000ad00  pop     rbp
0x18000ad01  pop     rbx
0x18000ad02  retn
```
