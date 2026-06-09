# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x1400031f4`
- end: `0x140003243`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140009e80`

## callees

- `0x1400031f4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003223`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003223`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003215`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003215`

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
0x1400031f4  push    rbx
0x1400031f6  push    rbp
0x1400031f7  push    rsi
0x1400031f8  push    rdi
0x1400031f9  sub     rsp, 28h
0x1400031fd  lea     rbp, [rcx+50h]
0x140003201  mov     rdi, rcx
0x140003204  cmp     rcx, rbp
0x140003207  jz      short loc_14000323A
0x140003209  mov     rsi, [rdi]
0x14000320c  jmp     short loc_140003229
0x14000320e  mov     rbx, rsi
0x140003211  mov     rsi, [rsi+8]
0x140003215  call    cs:__imp_GetProcessHeap
0x14000321b  mov     r8, rbx; lpMem
0x14000321e  xor     edx, edx; dwFlags
0x140003220  mov     rcx, rax; hHeap
0x140003223  call    cs:__imp_HeapFree
0x140003229  test    rsi, rsi
0x14000322c  jnz     short loc_14000320E
0x14000322e  mov     [rdi], rsi
0x140003231  add     rdi, 8
0x140003235  cmp     rdi, rbp
0x140003238  jnz     short loc_140003209
0x14000323a  add     rsp, 28h
0x14000323e  pop     rdi
0x14000323f  pop     rsi
0x140003240  pop     rbp
0x140003241  pop     rbx
0x140003242  retn
```
