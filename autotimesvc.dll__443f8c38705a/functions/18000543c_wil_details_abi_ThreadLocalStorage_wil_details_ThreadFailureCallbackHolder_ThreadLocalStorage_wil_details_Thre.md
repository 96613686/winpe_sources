# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x18000543c`
- end: `0x18000548b`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800117d0`

## callees

- `0x18000543c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000545d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000545d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000546b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000546b`

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
0x18000543c  push    rbx
0x18000543e  push    rbp
0x18000543f  push    rsi
0x180005440  push    rdi
0x180005441  sub     rsp, 28h
0x180005445  lea     rbp, [rcx+50h]
0x180005449  mov     rdi, rcx
0x18000544c  cmp     rcx, rbp
0x18000544f  jz      short loc_180005482
0x180005451  mov     rsi, [rdi]
0x180005454  jmp     short loc_180005471
0x180005456  mov     rbx, rsi
0x180005459  mov     rsi, [rsi+8]
0x18000545d  call    cs:__imp_GetProcessHeap
0x180005463  mov     r8, rbx; lpMem
0x180005466  xor     edx, edx; dwFlags
0x180005468  mov     rcx, rax; hHeap
0x18000546b  call    cs:__imp_HeapFree
0x180005471  test    rsi, rsi
0x180005474  jnz     short loc_180005456
0x180005476  mov     [rdi], rsi
0x180005479  add     rdi, 8
0x18000547d  cmp     rdi, rbp
0x180005480  jnz     short loc_180005451
0x180005482  add     rsp, 28h
0x180005486  pop     rdi
0x180005487  pop     rsi
0x180005488  pop     rbp
0x180005489  pop     rbx
0x18000548a  retn
```
