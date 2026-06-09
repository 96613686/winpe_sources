# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180004754`
- end: `0x1800047a3`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b6c0`

## callees

- `0x180004754`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004775`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004775`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004783`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004783`

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
0x180004754  push    rbx
0x180004756  push    rbp
0x180004757  push    rsi
0x180004758  push    rdi
0x180004759  sub     rsp, 28h
0x18000475d  lea     rbp, [rcx+50h]
0x180004761  mov     rdi, rcx
0x180004764  cmp     rcx, rbp
0x180004767  jz      short loc_18000479A
0x180004769  mov     rsi, [rdi]
0x18000476c  jmp     short loc_180004789
0x18000476e  mov     rbx, rsi
0x180004771  mov     rsi, [rsi+8]
0x180004775  call    cs:__imp_GetProcessHeap
0x18000477b  mov     r8, rbx; lpMem
0x18000477e  xor     edx, edx; dwFlags
0x180004780  mov     rcx, rax; hHeap
0x180004783  call    cs:__imp_HeapFree
0x180004789  test    rsi, rsi
0x18000478c  jnz     short loc_18000476E
0x18000478e  mov     [rdi], rsi
0x180004791  add     rdi, 8
0x180004795  cmp     rdi, rbp
0x180004798  jnz     short loc_180004769
0x18000479a  add     rsp, 28h
0x18000479e  pop     rdi
0x18000479f  pop     rsi
0x1800047a0  pop     rbp
0x1800047a1  pop     rbx
0x1800047a2  retn
```
