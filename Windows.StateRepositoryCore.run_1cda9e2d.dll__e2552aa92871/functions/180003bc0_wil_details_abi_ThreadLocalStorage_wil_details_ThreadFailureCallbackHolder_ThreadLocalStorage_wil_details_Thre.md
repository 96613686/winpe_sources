# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180003bc0`
- end: `0x180003c0f`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800102b0`

## callees

- `0x180003bc0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003bef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003bef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003be1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003be1`

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
0x180003bc0  push    rbx
0x180003bc2  push    rbp
0x180003bc3  push    rsi
0x180003bc4  push    rdi
0x180003bc5  sub     rsp, 28h
0x180003bc9  lea     rbp, [rcx+50h]
0x180003bcd  mov     rdi, rcx
0x180003bd0  cmp     rcx, rbp
0x180003bd3  jz      short loc_180003C06
0x180003bd5  mov     rsi, [rdi]
0x180003bd8  jmp     short loc_180003BF5
0x180003bda  mov     rbx, rsi
0x180003bdd  mov     rsi, [rsi+8]
0x180003be1  call    cs:__imp_GetProcessHeap
0x180003be7  mov     r8, rbx; lpMem
0x180003bea  xor     edx, edx; dwFlags
0x180003bec  mov     rcx, rax; hHeap
0x180003bef  call    cs:__imp_HeapFree
0x180003bf5  test    rsi, rsi
0x180003bf8  jnz     short loc_180003BDA
0x180003bfa  mov     [rdi], rsi
0x180003bfd  add     rdi, 8
0x180003c01  cmp     rdi, rbp
0x180003c04  jnz     short loc_180003BD5
0x180003c06  add     rsp, 28h
0x180003c0a  pop     rdi
0x180003c0b  pop     rsi
0x180003c0c  pop     rbp
0x180003c0d  pop     rbx
0x180003c0e  retn
```
