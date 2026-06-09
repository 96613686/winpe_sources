# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180004e14`
- end: `0x180004e63`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b800`

## callees

- `0x180004e14`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004e43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004e43`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e35`

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
0x180004e14  push    rbx
0x180004e16  push    rbp
0x180004e17  push    rsi
0x180004e18  push    rdi
0x180004e19  sub     rsp, 28h
0x180004e1d  lea     rbp, [rcx+50h]
0x180004e21  mov     rdi, rcx
0x180004e24  cmp     rcx, rbp
0x180004e27  jz      short loc_180004E5A
0x180004e29  mov     rsi, [rdi]
0x180004e2c  jmp     short loc_180004E49
0x180004e2e  mov     rbx, rsi
0x180004e31  mov     rsi, [rsi+8]
0x180004e35  call    cs:__imp_GetProcessHeap
0x180004e3b  mov     r8, rbx; lpMem
0x180004e3e  xor     edx, edx; dwFlags
0x180004e40  mov     rcx, rax; hHeap
0x180004e43  call    cs:__imp_HeapFree
0x180004e49  test    rsi, rsi
0x180004e4c  jnz     short loc_180004E2E
0x180004e4e  mov     [rdi], rsi
0x180004e51  add     rdi, 8
0x180004e55  cmp     rdi, rbp
0x180004e58  jnz     short loc_180004E29
0x180004e5a  add     rsp, 28h
0x180004e5e  pop     rdi
0x180004e5f  pop     rsi
0x180004e60  pop     rbp
0x180004e61  pop     rbx
0x180004e62  retn
```
