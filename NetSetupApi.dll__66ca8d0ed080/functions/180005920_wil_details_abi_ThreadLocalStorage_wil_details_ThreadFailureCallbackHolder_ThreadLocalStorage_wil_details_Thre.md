# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180005920`
- end: `0x18000596f`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014380`

## callees

- `0x180005920`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005941`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005941`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000594f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000594f`

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
0x180005920  push    rbx
0x180005922  push    rbp
0x180005923  push    rsi
0x180005924  push    rdi
0x180005925  sub     rsp, 28h
0x180005929  lea     rbp, [rcx+50h]
0x18000592d  mov     rdi, rcx
0x180005930  cmp     rcx, rbp
0x180005933  jz      short loc_180005966
0x180005935  mov     rsi, [rdi]
0x180005938  jmp     short loc_180005955
0x18000593a  mov     rbx, rsi
0x18000593d  mov     rsi, [rsi+8]
0x180005941  call    cs:__imp_GetProcessHeap
0x180005947  mov     r8, rbx; lpMem
0x18000594a  xor     edx, edx; dwFlags
0x18000594c  mov     rcx, rax; hHeap
0x18000594f  call    cs:__imp_HeapFree
0x180005955  test    rsi, rsi
0x180005958  jnz     short loc_18000593A
0x18000595a  mov     [rdi], rsi
0x18000595d  add     rdi, 8
0x180005961  cmp     rdi, rbp
0x180005964  jnz     short loc_180005935
0x180005966  add     rsp, 28h
0x18000596a  pop     rdi
0x18000596b  pop     rsi
0x18000596c  pop     rbp
0x18000596d  pop     rbx
0x18000596e  retn
```
