# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x140004a2c`
- end: `0x140004a7b`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140011ce0`

## callees

- `0x140004a2c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004a5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004a5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004a4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004a4d`

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
0x140004a2c  push    rbx
0x140004a2e  push    rbp
0x140004a2f  push    rsi
0x140004a30  push    rdi
0x140004a31  sub     rsp, 28h
0x140004a35  lea     rbp, [rcx+50h]
0x140004a39  mov     rdi, rcx
0x140004a3c  cmp     rcx, rbp
0x140004a3f  jz      short loc_140004A72
0x140004a41  mov     rsi, [rdi]
0x140004a44  jmp     short loc_140004A61
0x140004a46  mov     rbx, rsi
0x140004a49  mov     rsi, [rsi+8]
0x140004a4d  call    cs:__imp_GetProcessHeap
0x140004a53  mov     r8, rbx; lpMem
0x140004a56  xor     edx, edx; dwFlags
0x140004a58  mov     rcx, rax; hHeap
0x140004a5b  call    cs:__imp_HeapFree
0x140004a61  test    rsi, rsi
0x140004a64  jnz     short loc_140004A46
0x140004a66  mov     [rdi], rsi
0x140004a69  add     rdi, 8
0x140004a6d  cmp     rdi, rbp
0x140004a70  jnz     short loc_140004A41
0x140004a72  add     rsp, 28h
0x140004a76  pop     rdi
0x140004a77  pop     rsi
0x140004a78  pop     rbp
0x140004a79  pop     rbx
0x140004a7a  retn
```
