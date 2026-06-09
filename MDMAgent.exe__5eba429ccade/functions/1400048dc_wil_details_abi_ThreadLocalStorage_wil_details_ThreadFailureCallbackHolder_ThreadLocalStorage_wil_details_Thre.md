# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x1400048dc`
- end: `0x14000492b`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140018ef0`

## callees

- `0x1400048dc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400048fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400048fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000490b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000490b`

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
0x1400048dc  push    rbx
0x1400048de  push    rbp
0x1400048df  push    rsi
0x1400048e0  push    rdi
0x1400048e1  sub     rsp, 28h
0x1400048e5  lea     rbp, [rcx+50h]
0x1400048e9  mov     rdi, rcx
0x1400048ec  cmp     rcx, rbp
0x1400048ef  jz      short loc_140004922
0x1400048f1  mov     rsi, [rdi]
0x1400048f4  jmp     short loc_140004911
0x1400048f6  mov     rbx, rsi
0x1400048f9  mov     rsi, [rsi+8]
0x1400048fd  call    cs:__imp_GetProcessHeap
0x140004903  mov     r8, rbx; lpMem
0x140004906  xor     edx, edx; dwFlags
0x140004908  mov     rcx, rax; hHeap
0x14000490b  call    cs:__imp_HeapFree
0x140004911  test    rsi, rsi
0x140004914  jnz     short loc_1400048F6
0x140004916  mov     [rdi], rsi
0x140004919  add     rdi, 8
0x14000491d  cmp     rdi, rbp
0x140004920  jnz     short loc_1400048F1
0x140004922  add     rsp, 28h
0x140004926  pop     rdi
0x140004927  pop     rsi
0x140004928  pop     rbp
0x140004929  pop     rbx
0x14000492a  retn
```
