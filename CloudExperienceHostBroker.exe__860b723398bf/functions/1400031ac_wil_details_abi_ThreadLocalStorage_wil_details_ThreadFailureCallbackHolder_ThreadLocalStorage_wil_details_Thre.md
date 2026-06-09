# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x1400031ac`
- end: `0x1400031fb`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140009a90`

## callees

- `0x1400031ac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400031cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400031cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400031db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400031db`

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
0x1400031ac  push    rbx
0x1400031ae  push    rbp
0x1400031af  push    rsi
0x1400031b0  push    rdi
0x1400031b1  sub     rsp, 28h
0x1400031b5  lea     rbp, [rcx+50h]
0x1400031b9  mov     rdi, rcx
0x1400031bc  cmp     rcx, rbp
0x1400031bf  jz      short loc_1400031F2
0x1400031c1  mov     rsi, [rdi]
0x1400031c4  jmp     short loc_1400031E1
0x1400031c6  mov     rbx, rsi
0x1400031c9  mov     rsi, [rsi+8]
0x1400031cd  call    cs:__imp_GetProcessHeap
0x1400031d3  mov     r8, rbx; lpMem
0x1400031d6  xor     edx, edx; dwFlags
0x1400031d8  mov     rcx, rax; hHeap
0x1400031db  call    cs:__imp_HeapFree
0x1400031e1  test    rsi, rsi
0x1400031e4  jnz     short loc_1400031C6
0x1400031e6  mov     [rdi], rsi
0x1400031e9  add     rdi, 8
0x1400031ed  cmp     rdi, rbp
0x1400031f0  jnz     short loc_1400031C1
0x1400031f2  add     rsp, 28h
0x1400031f6  pop     rdi
0x1400031f7  pop     rsi
0x1400031f8  pop     rbp
0x1400031f9  pop     rbx
0x1400031fa  retn
```
