# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180003500`
- end: `0x18000354f`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009910`

## callees

- `0x180003500`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000352f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000352f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003521`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003521`

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
0x180003500  push    rbx
0x180003502  push    rbp
0x180003503  push    rsi
0x180003504  push    rdi
0x180003505  sub     rsp, 28h
0x180003509  lea     rbp, [rcx+50h]
0x18000350d  mov     rdi, rcx
0x180003510  cmp     rcx, rbp
0x180003513  jz      short loc_180003546
0x180003515  mov     rsi, [rdi]
0x180003518  jmp     short loc_180003535
0x18000351a  mov     rbx, rsi
0x18000351d  mov     rsi, [rsi+8]
0x180003521  call    cs:__imp_GetProcessHeap
0x180003527  mov     r8, rbx; lpMem
0x18000352a  xor     edx, edx; dwFlags
0x18000352c  mov     rcx, rax; hHeap
0x18000352f  call    cs:__imp_HeapFree
0x180003535  test    rsi, rsi
0x180003538  jnz     short loc_18000351A
0x18000353a  mov     [rdi], rsi
0x18000353d  add     rdi, 8
0x180003541  cmp     rdi, rbp
0x180003544  jnz     short loc_180003515
0x180003546  add     rsp, 28h
0x18000354a  pop     rdi
0x18000354b  pop     rsi
0x18000354c  pop     rbp
0x18000354d  pop     rbx
0x18000354e  retn
```
