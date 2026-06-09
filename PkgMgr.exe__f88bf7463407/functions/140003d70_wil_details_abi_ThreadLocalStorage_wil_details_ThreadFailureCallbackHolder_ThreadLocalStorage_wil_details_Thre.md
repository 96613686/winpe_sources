# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x140003d70`
- end: `0x140003dbf`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140029e40`

## callees

- `0x140003d70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003d91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003d91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003d9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003d9f`

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
0x140003d70  push    rbx
0x140003d72  push    rbp
0x140003d73  push    rsi
0x140003d74  push    rdi
0x140003d75  sub     rsp, 28h
0x140003d79  lea     rbp, [rcx+50h]
0x140003d7d  mov     rdi, rcx
0x140003d80  cmp     rcx, rbp
0x140003d83  jz      short loc_140003DB6
0x140003d85  mov     rsi, [rdi]
0x140003d88  jmp     short loc_140003DA5
0x140003d8a  mov     rbx, rsi
0x140003d8d  mov     rsi, [rsi+8]
0x140003d91  call    cs:__imp_GetProcessHeap
0x140003d97  mov     r8, rbx; lpMem
0x140003d9a  xor     edx, edx; dwFlags
0x140003d9c  mov     rcx, rax; hHeap
0x140003d9f  call    cs:__imp_HeapFree
0x140003da5  test    rsi, rsi
0x140003da8  jnz     short loc_140003D8A
0x140003daa  mov     [rdi], rsi
0x140003dad  add     rdi, 8
0x140003db1  cmp     rdi, rbp
0x140003db4  jnz     short loc_140003D85
0x140003db6  add     rsp, 28h
0x140003dba  pop     rdi
0x140003dbb  pop     rsi
0x140003dbc  pop     rbp
0x140003dbd  pop     rbx
0x140003dbe  retn
```
