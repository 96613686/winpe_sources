# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x1800103a0`
- end: `0x1800103ef`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800286c0`

## callees

- `0x1800103a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800103c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800103c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800103cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800103cf`

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
0x1800103a0  push    rbx
0x1800103a2  push    rbp
0x1800103a3  push    rsi
0x1800103a4  push    rdi
0x1800103a5  sub     rsp, 28h
0x1800103a9  lea     rbp, [rcx+50h]
0x1800103ad  mov     rdi, rcx
0x1800103b0  cmp     rcx, rbp
0x1800103b3  jz      short loc_1800103E6
0x1800103b5  mov     rsi, [rdi]
0x1800103b8  jmp     short loc_1800103D5
0x1800103ba  mov     rbx, rsi
0x1800103bd  mov     rsi, [rsi+8]
0x1800103c1  call    cs:__imp_GetProcessHeap
0x1800103c7  mov     r8, rbx; lpMem
0x1800103ca  xor     edx, edx; dwFlags
0x1800103cc  mov     rcx, rax; hHeap
0x1800103cf  call    cs:__imp_HeapFree
0x1800103d5  test    rsi, rsi
0x1800103d8  jnz     short loc_1800103BA
0x1800103da  mov     [rdi], rsi
0x1800103dd  add     rdi, 8
0x1800103e1  cmp     rdi, rbp
0x1800103e4  jnz     short loc_1800103B5
0x1800103e6  add     rsp, 28h
0x1800103ea  pop     rdi
0x1800103eb  pop     rsi
0x1800103ec  pop     rbp
0x1800103ed  pop     rbx
0x1800103ee  retn
```
