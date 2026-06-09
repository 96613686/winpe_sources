# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x1800139ac`
- end: `0x1800139fb`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180020b90`

## callees

- `0x1800139ac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800139cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800139cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800139db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800139db`

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
0x1800139ac  push    rbx
0x1800139ae  push    rbp
0x1800139af  push    rsi
0x1800139b0  push    rdi
0x1800139b1  sub     rsp, 28h
0x1800139b5  lea     rbp, [rcx+50h]
0x1800139b9  mov     rdi, rcx
0x1800139bc  cmp     rcx, rbp
0x1800139bf  jz      short loc_1800139F2
0x1800139c1  mov     rsi, [rdi]
0x1800139c4  jmp     short loc_1800139E1
0x1800139c6  mov     rbx, rsi
0x1800139c9  mov     rsi, [rsi+8]
0x1800139cd  call    cs:__imp_GetProcessHeap
0x1800139d3  mov     r8, rbx; lpMem
0x1800139d6  xor     edx, edx; dwFlags
0x1800139d8  mov     rcx, rax; hHeap
0x1800139db  call    cs:__imp_HeapFree
0x1800139e1  test    rsi, rsi
0x1800139e4  jnz     short loc_1800139C6
0x1800139e6  mov     [rdi], rsi
0x1800139e9  add     rdi, 8
0x1800139ed  cmp     rdi, rbp
0x1800139f0  jnz     short loc_1800139C1
0x1800139f2  add     rsp, 28h
0x1800139f6  pop     rdi
0x1800139f7  pop     rsi
0x1800139f8  pop     rbp
0x1800139f9  pop     rbx
0x1800139fa  retn
```
