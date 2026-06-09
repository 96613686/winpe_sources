# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x140005a9c`
- end: `0x140005aeb`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140019220`

## callees

- `0x140005a9c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005abd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005abd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005acb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005acb`

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
0x140005a9c  push    rbx
0x140005a9e  push    rbp
0x140005a9f  push    rsi
0x140005aa0  push    rdi
0x140005aa1  sub     rsp, 28h
0x140005aa5  lea     rbp, [rcx+50h]
0x140005aa9  mov     rdi, rcx
0x140005aac  cmp     rcx, rbp
0x140005aaf  jz      short loc_140005AE2
0x140005ab1  mov     rsi, [rdi]
0x140005ab4  jmp     short loc_140005AD1
0x140005ab6  mov     rbx, rsi
0x140005ab9  mov     rsi, [rsi+8]
0x140005abd  call    cs:__imp_GetProcessHeap
0x140005ac3  mov     r8, rbx; lpMem
0x140005ac6  xor     edx, edx; dwFlags
0x140005ac8  mov     rcx, rax; hHeap
0x140005acb  call    cs:__imp_HeapFree
0x140005ad1  test    rsi, rsi
0x140005ad4  jnz     short loc_140005AB6
0x140005ad6  mov     [rdi], rsi
0x140005ad9  add     rdi, 8
0x140005add  cmp     rdi, rbp
0x140005ae0  jnz     short loc_140005AB1
0x140005ae2  add     rsp, 28h
0x140005ae6  pop     rdi
0x140005ae7  pop     rsi
0x140005ae8  pop     rbp
0x140005ae9  pop     rbx
0x140005aea  retn
```
