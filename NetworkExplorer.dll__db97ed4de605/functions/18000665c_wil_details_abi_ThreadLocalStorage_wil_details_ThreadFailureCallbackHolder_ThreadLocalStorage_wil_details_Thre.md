# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x18000665c`
- end: `0x1800066ab`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f7a0`

## callees

- `0x18000665c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800066a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800066a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006695`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006695`

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
0x18000665c  push    rbx
0x18000665e  push    rbp
0x18000665f  push    rsi
0x180006660  push    rdi
0x180006661  sub     rsp, 28h
0x180006665  lea     rbp, [rcx+50h]
0x180006669  mov     rdi, rcx
0x18000666c  cmp     rcx, rbp
0x18000666f  jz      short loc_180006685
0x180006671  mov     rsi, [rdi]
0x180006674  test    rsi, rsi
0x180006677  jnz     short loc_18000668E
0x180006679  mov     [rdi], rsi
0x18000667c  add     rdi, 8
0x180006680  cmp     rdi, rbp
0x180006683  jnz     short loc_180006671
0x180006685  add     rsp, 28h
0x180006689  pop     rdi
0x18000668a  pop     rsi
0x18000668b  pop     rbp
0x18000668c  pop     rbx
0x18000668d  retn
0x18000668e  mov     rbx, rsi
0x180006691  mov     rsi, [rsi+8]
0x180006695  call    cs:__imp_GetProcessHeap
0x18000669b  mov     r8, rbx; lpMem
0x18000669e  xor     edx, edx; dwFlags
0x1800066a0  mov     rcx, rax; hHeap
0x1800066a3  call    cs:__imp_HeapFree
0x1800066a9  jmp     short loc_180006674
```
